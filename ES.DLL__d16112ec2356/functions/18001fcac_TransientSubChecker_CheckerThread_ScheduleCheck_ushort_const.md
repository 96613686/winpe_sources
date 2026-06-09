# TransientSubChecker::CheckerThread::ScheduleCheck(ushort const *)

- ea: `0x18001fcac`
- end: `0x18001fde1`
- name: `?ScheduleCheck@CheckerThread@TransientSubChecker@@QEAAXPEBG@Z`
- size: `309`
- prototype: `void __fastcall(TransientSubChecker::CheckerThread *__hidden this, OLECHAR *psz)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001f9e0`
- `0x18001fb30`

## callees

- `0x180003d54`
- `0x180010410`
- `0x18001fcac`
- `0x18001fde8`
- `0x18001fe08`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001fcf2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001fcf2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001fcff`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001fcff`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18001fd93`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18001fd93`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001fdd2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001fdd2`
- `OLEAUT32!__imp_SysAllocString` at `0x18001fd18`
- `OLEAUT32!__imp_SysAllocString` at `0x18001fd18`
- `OLEAUT32!__imp_SysFreeString` at `0x18001fd39`
- `OLEAUT32!__imp_SysFreeString` at `0x18001fd39`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001fd2b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001fd2b`

## string_xrefs

- `0x18001fdb5`: `com\complus\src\events\Shared\UTSem.h`

## pseudocode

```c
void __fastcall TransientSubChecker::CheckerThread::ScheduleCheck(HANDLE *this, OLECHAR *psz)
{
  CSemExclusiveES *v2; // rdi
  OLECHAR *v5; // rsi
  struct TransientSubChecker::CheckerThread::CheckerArgs *v6; // rax
  HANDLE v7; // rax
  int v8; // [rsp+30h] [rbp-18h] BYREF
  char *v9; // [rsp+38h] [rbp-10h]
  DWORD ThreadId; // [rsp+50h] [rbp+8h] BYREF

  v2 = (CSemExclusiveES *)(this + 13);
  v8 = 1;
  v9 = (char *)(this + 13);
  if ( this == (HANDLE *)-104LL )
    InternalError(L"com\\complus\\src\\events\\Shared\\UTSem.h", 0x154u, 0x80001203, 0x10u);
  CSemExclusiveES::Lock(v2);
  if ( *((_DWORD *)this + 38) )
  {
    if ( *this )
    {
      CloseHandle(*this);
      *this = 0;
    }
    ThreadId = 0;
    v7 = CreateThread(0, 0, TransientSubChecker::CheckerThread::ThreadMain, this, 0, &ThreadId);
    *this = v7;
    if ( !v7 )
      goto LABEL_9;
    *((_DWORD *)this + 38) = 0;
  }
  if ( WaitForSingleObject(this[1], 0xFFFFFFFF) )
  {
LABEL_5:
    LeaveCriticalSection((LPCRITICAL_SECTION)v2);
    return;
  }
  v5 = SysAllocString(psz);
  if ( v5 )
  {
    v6 = (struct TransientSubChecker::CheckerThread::CheckerArgs *)CoTaskMemAlloc(0x10u);
    if ( v6 )
    {
      *(_QWORD *)v6 = 0;
      *((_QWORD *)v6 + 1) = v5;
      TransientSubChecker::CheckerThread::PostCheckerArgs((TransientSubChecker::CheckerThread *)this, v6);
      goto LABEL_5;
    }
    SysFreeString(v5);
  }
LABEL_9:
  CLockES::~CLockES((CLockES *)&v8);
}

```

## disassembly

```asm
0x18001fcac  mov     rax, rsp
0x18001fcaf  mov     [rax+10h], rbx
0x18001fcb3  mov     [rax+18h], rsi
0x18001fcb7  push    rdi
0x18001fcb8  sub     rsp, 40h
0x18001fcbc  lea     rdi, [rcx+68h]
0x18001fcc0  mov     dword ptr [rax-18h], 1
0x18001fcc7  mov     [rax-10h], rdi
0x18001fccb  mov     rsi, rdx
0x18001fcce  mov     rbx, rcx
0x18001fcd1  test    rdi, rdi
0x18001fcd4  jz      loc_18001FDB0
0x18001fcda  mov     rcx, rdi; this
0x18001fcdd  call    ?Lock@CSemExclusiveES@@QEAAXXZ; CSemExclusiveES::Lock(void)
0x18001fce2  cmp     dword ptr [rbx+98h], 0
0x18001fce9  jnz     short loc_18001FD63
0x18001fceb  mov     rcx, [rbx+8]; hHandle
0x18001fcef  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18001fcf2  call    cs:__imp_WaitForSingleObject
0x18001fcf8  test    eax, eax
0x18001fcfa  jz      short loc_18001FD15
0x18001fcfc  mov     rcx, rdi; lpCriticalSection
0x18001fcff  call    cs:__imp_LeaveCriticalSection
0x18001fd05  mov     rbx, [rsp+48h+arg_8]
0x18001fd0a  mov     rsi, [rsp+48h+arg_10]
0x18001fd0f  add     rsp, 40h
0x18001fd13  pop     rdi
0x18001fd14  retn
0x18001fd15  mov     rcx, rsi; psz
0x18001fd18  call    cs:__imp_SysAllocString
0x18001fd1e  mov     rsi, rax
0x18001fd21  test    rax, rax
0x18001fd24  jz      short loc_18001FD3F
0x18001fd26  mov     ecx, 10h; cb
0x18001fd2b  call    cs:__imp_CoTaskMemAlloc
0x18001fd31  test    rax, rax
0x18001fd34  jnz     short loc_18001FD4B
0x18001fd36  mov     rcx, rsi; bstrString
0x18001fd39  call    cs:__imp_SysFreeString
0x18001fd3f  lea     rcx, [rsp+48h+var_18]; this
0x18001fd44  call    ??1CLockES@@QEAA@XZ; CLockES::~CLockES(void)
0x18001fd49  jmp     short loc_18001FD05
0x18001fd4b  mov     rdx, rax; struct TransientSubChecker::CheckerThread::CheckerArgs *
0x18001fd4e  mov     qword ptr [rax], 0
0x18001fd55  mov     rcx, rbx; this
0x18001fd58  mov     [rax+8], rsi
0x18001fd5c  call    ?PostCheckerArgs@CheckerThread@TransientSubChecker@@AEAAXPEAUCheckerArgs@12@@Z; TransientSubChecker::CheckerThread::PostCheckerArgs(TransientSubChecker::CheckerThread::CheckerArgs *)
0x18001fd61  jmp     short loc_18001FCFC
0x18001fd63  mov     rcx, [rbx]; hObject
0x18001fd66  test    rcx, rcx
0x18001fd69  jnz     short loc_18001FDD2
0x18001fd6b  lea     rax, [rsp+48h+ThreadId]
0x18001fd70  mov     [rsp+48h+ThreadId], 0
0x18001fd78  mov     [rsp+48h+lpThreadId], rax; lpThreadId
0x18001fd7d  lea     r8, ?ThreadMain@CheckerThread@TransientSubChecker@@CAKPEAX@Z; lpStartAddress
0x18001fd84  mov     r9, rbx; lpParameter
0x18001fd87  mov     [rsp+48h+dwCreationFlags], 0; dwCreationFlags
0x18001fd8f  xor     edx, edx; dwStackSize
0x18001fd91  xor     ecx, ecx; lpThreadAttributes
0x18001fd93  call    cs:__imp_CreateThread
0x18001fd99  mov     [rbx], rax
0x18001fd9c  test    rax, rax
0x18001fd9f  jz      short loc_18001FD3F
0x18001fda1  mov     dword ptr [rbx+98h], 0
0x18001fdab  jmp     loc_18001FCEB
0x18001fdb0  mov     edx, 154h; unsigned int
0x18001fdb5  lea     rcx, aComComplusSrcE_4; "com\\complus\\src\\events\\Shared\\UTSe"...
0x18001fdbc  mov     r9d, 10h; unsigned __int16
0x18001fdc2  mov     r8d, 80001203h; unsigned int
0x18001fdc8  call    ?InternalError@@YA_NPEBGKKG@Z; InternalError(ushort const *,ulong,ulong,ushort)
0x18001fdcd  jmp     loc_18001FCDA
0x18001fdd2  call    cs:__imp_CloseHandle
0x18001fdd8  mov     qword ptr [rbx], 0
0x18001fddf  jmp     short loc_18001FD6B
```
