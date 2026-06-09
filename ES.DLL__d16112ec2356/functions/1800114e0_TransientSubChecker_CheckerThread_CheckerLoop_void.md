# TransientSubChecker::CheckerThread::CheckerLoop(void)

- ea: `0x1800114e0`
- end: `0x1800116cf`
- name: `?CheckerLoop@CheckerThread@TransientSubChecker@@AEAAXXZ`
- size: `495`
- prototype: `void __fastcall(TransientSubChecker::CheckerThread *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800271b0`

## callees

- `0x180003d54`
- `0x180009034`
- `0x180010410`
- `0x1800114e0`
- `0x1800116d8`
- `0x180012654`
- `0x18003ecb0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180011502`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180011502`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18001151c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18001151c`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180011656`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180011656`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001159d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800115db`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001165f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001159d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800115db`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001165f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011589`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011589`
- `OLEAUT32!__imp_SysFreeString` at `0x180011627`
- `OLEAUT32!__imp_SysFreeString` at `0x180011627`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011630`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011630`

## string_xrefs

- `0x18001153f`: `com\complus\src\events\tier2\notify.cpp`
- `0x18001167d`: `com\complus\src\events\Shared\UTSem.h`
- `0x1800116a0`: `com\complus\src\events\Shared\UTSem.h`

## pseudocode

```c
void __fastcall TransientSubChecker::CheckerThread::CheckerLoop(TransientSubChecker::CheckerThread *this)
{
  DWORD v2; // ebx
  struct TransientSubChecker::CheckerThread::CheckerArgs *v3; // rdi
  struct TransientSubChecker::CheckerThread::CheckerArgs *v4; // rsi
  HANDLE *v5; // [rsp+88h] [rbp+20h]

  v5 = (HANDLE *)((char *)this + 8);
  SetEvent(*((HANDLE *)this + 1));
  while ( 1 )
  {
    do
    {
      v2 = WaitForSingleObjectEx(*((HANDLE *)this + 10), 0x1D4C0u, 0);
      if ( v2 == -1 )
        InternalError_Win32(L"com\\complus\\src\\events\\tier2\\notify.cpp", 0x6E7u, 0x11u, L"WaitForSingleObjectEx");
      if ( !v2 )
      {
        v3 = 0;
        CSemExclusiveES::Lock((TransientSubChecker::CheckerThread *)((char *)this + 32));
        if ( *((_QWORD *)this + 11) )
        {
          v3 = (struct TransientSubChecker::CheckerThread::CheckerArgs *)*((_QWORD *)this + 11);
          *((_QWORD *)this + 11) = 0;
          *((_QWORD *)this + 12) = 0;
        }
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
        while ( v3 )
        {
          v4 = *(struct TransientSubChecker::CheckerThread::CheckerArgs **)v3;
          *(_QWORD *)v3 = 0;
          TransientSubChecker::CheckerThread::ProcessCheckerArgs(this, v3);
          SysFreeString(*((BSTR *)v3 + 1));
          CoTaskMemFree(v3);
          v3 = v4;
        }
      }
    }
    while ( v2 != 258 && !*((_DWORD *)this + 6) );
    if ( this == (TransientSubChecker::CheckerThread *)-104LL )
      InternalError(L"com\\complus\\src\\events\\Shared\\UTSem.h", 0x154u, 0x80001203, 0x10u);
    if ( !*((_DWORD *)this + 36) )
      InternalAssert(L"com\\complus\\src\\events\\Shared\\UTSem.h", 0x12Eu, 0x10u, L"m_fInitialized");
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 104));
    if ( *((_DWORD *)this + 6) )
      break;
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 104));
  }
  *((_DWORD *)this + 38) = 1;
  ResetEvent(*v5);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 104));
}

```

## disassembly

```asm
0x1800114e0  mov     [rsp+arg_0], rcx
0x1800114e5  push    rbx
0x1800114e6  push    rsi
0x1800114e7  push    rdi
0x1800114e8  push    r14
0x1800114ea  push    r15
0x1800114ec  sub     rsp, 40h
0x1800114f0  mov     r14, rcx
0x1800114f3  add     rcx, 8
0x1800114f7  mov     [rsp+68h+arg_18], rcx
0x1800114ff  mov     rcx, [rcx]; hEvent
0x180011502  call    cs:__imp_SetEvent
0x180011508  xor     r15d, r15d
0x18001150b  nop     dword ptr [rax+rax+00h]
0x180011510  xor     r8d, r8d; bAlertable
0x180011513  mov     edx, 1D4C0h; dwMilliseconds
0x180011518  mov     rcx, [r14+50h]; hHandle
0x18001151c  call    cs:__imp_WaitForSingleObjectEx
0x180011522  mov     ebx, eax
0x180011524  mov     [rsp+68h+arg_8], eax
0x180011528  cmp     eax, 0FFFFFFFFh
0x18001152b  jnz     short loc_18001154B
0x18001152d  mov     r8d, 11h; unsigned __int16
0x180011533  lea     r9, aWaitforsingleo_0; "WaitForSingleObjectEx"
0x18001153a  mov     edx, 6E7h; unsigned int
0x18001153f  lea     rcx, aComComplusSrcE_7; "com\\complus\\src\\events\\tier2\\notif"...
0x180011546  call    ?InternalError_Win32@@YA_NPEBGKG0@Z; InternalError_Win32(ushort const *,ulong,ushort,ushort const *)
0x18001154b  test    ebx, ebx
0x18001154d  jz      short loc_1800115AD
0x18001154f  cmp     ebx, 102h
0x180011555  jz      short loc_180011562
0x180011557  cmp     dword ptr [r14+18h], 0
0x18001155c  jz      loc_1800116B1
0x180011562  mov     [rsp+68h+var_38], 1
0x18001156a  lea     rbx, [r14+68h]
0x18001156e  mov     [rsp+68h+var_30], rbx
0x180011573  test    rbx, rbx
0x180011576  jz      loc_18001166C
0x18001157c  cmp     dword ptr [rbx+28h], 0
0x180011580  jz      loc_18001168E
0x180011586  mov     rcx, rbx; lpCriticalSection
0x180011589  call    cs:__imp_EnterCriticalSection
0x18001158f  cmp     dword ptr [r14+18h], 0
0x180011594  jnz     loc_180011640
0x18001159a  mov     rcx, rbx; lpCriticalSection
0x18001159d  call    cs:__imp_LeaveCriticalSection
0x1800115a3  mov     [rsp+68h+var_38], r15d
0x1800115a8  jmp     loc_1800116B1
0x1800115ad  mov     rdi, r15
0x1800115b0  mov     [rsp+68h+var_40], r15
0x1800115b5  lea     rcx, [r14+20h]; this
0x1800115b9  call    ?Lock@CSemExclusiveES@@QEAAXXZ; CSemExclusiveES::Lock(void)
0x1800115be  mov     rax, [r14+58h]
0x1800115c2  test    rax, rax
0x1800115c5  jz      short loc_1800115D7
0x1800115c7  mov     rdi, rax
0x1800115ca  mov     [rsp+68h+var_40], rax
0x1800115cf  mov     [r14+58h], r15
0x1800115d3  mov     [r14+60h], r15
0x1800115d7  lea     rcx, [r14+20h]; lpCriticalSection
0x1800115db  call    cs:__imp_LeaveCriticalSection
0x1800115e1  test    rdi, rdi
0x1800115e4  jz      loc_18001154F
0x1800115ea  mov     [rsp+68h+var_48], r15d
0x1800115ef  mov     rsi, [rdi]
0x1800115f2  mov     [rsp+68h+arg_10], rsi
0x1800115fa  mov     [rdi], r15
0x1800115fd  mov     rdx, rdi; struct TransientSubChecker::CheckerThread::CheckerArgs *
0x180011600  mov     rcx, r14; this
0x180011603  call    ?ProcessCheckerArgs@CheckerThread@TransientSubChecker@@AEAAJPEAUCheckerArgs@12@@Z; TransientSubChecker::CheckerThread::ProcessCheckerArgs(TransientSubChecker::CheckerThread::CheckerArgs *)
0x180011608  jmp     short loc_180011623
0x18001160a  xor     r15d, r15d
0x18001160d  mov     r14, [rsp+68h+arg_0]
0x180011612  mov     ebx, [rsp+68h+arg_8]
0x180011616  mov     rdi, [rsp+68h+var_40]
0x18001161b  mov     rsi, [rsp+68h+arg_10]
0x180011623  mov     rcx, [rdi+8]; bstrString
0x180011627  call    cs:__imp_SysFreeString
0x18001162d  mov     rcx, rdi; pv
0x180011630  call    cs:__imp_CoTaskMemFree
0x180011636  mov     rdi, rsi
0x180011639  mov     [rsp+68h+var_40], rsi
0x18001163e  jmp     short loc_1800115E1
0x180011640  mov     dword ptr [r14+98h], 1
0x18001164b  mov     rcx, [rsp+68h+arg_18]
0x180011653  mov     rcx, [rcx]; hEvent
0x180011656  call    cs:__imp_ResetEvent
0x18001165c  mov     rcx, rbx; lpCriticalSection
0x18001165f  call    cs:__imp_LeaveCriticalSection
0x180011665  mov     [rsp+68h+var_38], r15d
0x18001166a  jmp     short loc_1800116C3
0x18001166c  mov     edx, 154h; unsigned int
0x180011671  mov     r9d, 10h; unsigned __int16
0x180011677  mov     r8d, 80001203h; unsigned int
0x18001167d  lea     rcx, aComComplusSrcE_4; "com\\complus\\src\\events\\Shared\\UTSe"...
0x180011684  call    ?InternalError@@YA_NPEBGKKG@Z; InternalError(ushort const *,ulong,ulong,ushort)
0x180011689  jmp     loc_18001157C
0x18001168e  mov     r8d, 10h; unsigned __int16
0x180011694  lea     r9, aMFinitialized; "m_fInitialized"
0x18001169b  mov     edx, 12Eh; unsigned int
0x1800116a0  lea     rcx, aComComplusSrcE_4; "com\\complus\\src\\events\\Shared\\UTSe"...
0x1800116a7  call    ?InternalAssert@@YA_NPEBGKG0@Z; InternalAssert(ushort const *,ulong,ushort,ushort const *)
0x1800116ac  jmp     loc_180011586
0x1800116b1  jmp     loc_180011510
0x1800116b6  xor     r15d, r15d
0x1800116b9  mov     r14, [rsp+68h+arg_0]
0x1800116be  jmp     loc_180011510
0x1800116c3  add     rsp, 40h
0x1800116c7  pop     r15
0x1800116c9  pop     r14
0x1800116cb  pop     rdi
0x1800116cc  pop     rsi
0x1800116cd  pop     rbx
0x1800116ce  retn
0x180043ef0  push    rbp
0x180043ef2  sub     rsp, 20h
0x180043ef6  mov     rbp, rdx
0x180043ef9  lea     rdx, [rbp+20h]; int *
0x180043efd  call    ?ExceptionFilter@@YAKPEAU_EXCEPTION_POINTERS@@AEAJ@Z; ExceptionFilter(_EXCEPTION_POINTERS *,long &)
0x180043f02  nop
0x180043f03  add     rsp, 20h
0x180043f07  pop     rbp
0x180043f08  retn
0x180043f0a  push    rbp
0x180043f0c  sub     rsp, 20h
0x180043f10  mov     rbp, rdx
0x180043f13  lea     rdx, [rbp+24h]; int *
0x180043f17  call    ?ExceptionFilter@@YAKPEAU_EXCEPTION_POINTERS@@AEAJ@Z; ExceptionFilter(_EXCEPTION_POINTERS *,long &)
0x180043f1c  nop
0x180043f1d  add     rsp, 20h
0x180043f21  pop     rbp
0x180043f22  retn
```
