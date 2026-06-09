# CWaitThreadList::Wait(void *)

- ea: `0x14002c8dc`
- end: `0x14002c9ff`
- name: `?Wait@CWaitThreadList@@QEAAXPEAX@Z`
- size: `291`
- prototype: `void(CWaitThreadList *__hidden this, void *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x140024efc`

## callees

- `0x14000348c`
- `0x14001ba3c`
- `0x140021bdc`
- `0x14002be14`
- `0x14002c094`
- `0x14002c128`
- `0x14002c394`
- `0x14002c68c`
- `0x14002c8dc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14002c9c7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14002c9d1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14002c9c7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14002c9d1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14002c99d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14002c99d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14002c905`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14002c905`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CWaitThreadList::Wait(CWaitThreadList *this, void *a2)
{
  volatile signed __int32 *v4; // rdi
  CThreadSmartWait *v5; // rax
  unsigned int v6; // edx
  CThreadSmartWait *v7; // rbx
  CThreadSmartWait *v8; // [rsp+50h] [rbp+8h] BYREF
  CThreadSmartWait *v9; // [rsp+60h] [rbp+18h] BYREF

  v9 = 0;
  LODWORD(v8) = GetCurrentThreadId();
  v4 = (volatile signed __int32 *)((char *)this + 8);
  CSyncReadWrite::GetWriteAccess((CWaitThreadList *)((char *)this + 8));
  if ( (unsigned int)TKeyedLiteSList<unsigned long,CThreadSmartWait,TPointer<CThreadSmartWait>>::LookupByKey(
                       this,
                       &v8,
                       &v9) )
  {
    v7 = v9;
  }
  else
  {
    v5 = (CThreadSmartWait *)operator new(0x38u, (const struct std::nothrow_t *)&std::nothrow);
    v8 = v5;
    if ( v5 )
      v7 = CThreadSmartWait::CThreadSmartWait(v5, *((_DWORD *)this + 30));
    else
      v7 = 0;
    v8 = v7;
    if ( v7 )
    {
      v8 = 0;
      *(_QWORD *)v7 = *(_QWORD *)this;
      *((_QWORD *)v7 + 1) = v7;
      *(_QWORD *)this = v7;
      ++*((_DWORD *)this + 31);
    }
    TPointer<CThreadSmartWait>::~TPointer<CThreadSmartWait>(&v8, v6);
  }
  if ( v7 )
    *((_BYTE *)v7 + 28) = 1;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  if ( *v4 == 1 )
    *((_DWORD *)this + 3) = -1;
  _InterlockedDecrement(v4);
  CSyncReadWrite::LokInitReadEvent((CWaitThreadList *)((char *)this + 8));
  CEventSem::Set(*((CEventSem **)this + 13));
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  if ( v7 )
    CThreadSmartWait::Wait(v7, a2, *((_DWORD *)this + 31));
}

```

## disassembly

```asm
0x14002c8dc  mov     rax, rsp
0x14002c8df  push    rsi
0x14002c8e0  push    rdi
0x14002c8e1  push    r14
0x14002c8e3  sub     rsp, 30h
0x14002c8e7  mov     qword ptr [rax-28h], 0FFFFFFFFFFFFFFFEh
0x14002c8ef  mov     [rax+10h], rbx
0x14002c8f3  mov     [rax+20h], rbp
0x14002c8f7  mov     r14, rdx
0x14002c8fa  mov     rsi, rcx
0x14002c8fd  mov     qword ptr [rax+18h], 0
0x14002c905  call    cs:__imp_GetCurrentThreadId
0x14002c90b  mov     dword ptr [rsp+48h+arg_0], eax
0x14002c90f  lea     rdi, [rsi+8]
0x14002c913  mov     rcx, rdi; this
0x14002c916  call    ?GetWriteAccess@CSyncReadWrite@@QEAAXXZ; CSyncReadWrite::GetWriteAccess(void)
0x14002c91b  lea     r8, [rsp+48h+arg_10]
0x14002c920  lea     rdx, [rsp+48h+arg_0]
0x14002c925  mov     rcx, rsi
0x14002c928  call    ?LookupByKey@?$TKeyedLiteSList@KVCThreadSmartWait@@V?$TPointer@VCThreadSmartWait@@@@@@QEAAHPEBKPEAPEAVCThreadSmartWait@@@Z; TKeyedLiteSList<ulong,CThreadSmartWait,TPointer<CThreadSmartWait>>::LookupByKey(ulong const *,CThreadSmartWait * *)
0x14002c92d  test    eax, eax
0x14002c92f  jnz     short loc_14002C98B
0x14002c931  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14002c938  lea     ecx, [rax+38h]; unsigned __int64
0x14002c93b  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14002c940  mov     [rsp+48h+arg_0], rax
0x14002c945  test    rax, rax
0x14002c948  jz      short loc_14002C95A
0x14002c94a  mov     edx, [rsi+78h]; unsigned int
0x14002c94d  mov     rcx, rax; this
0x14002c950  call    ??0CThreadSmartWait@@QEAA@K@Z; CThreadSmartWait::CThreadSmartWait(ulong)
0x14002c955  mov     rbx, rax
0x14002c958  jmp     short loc_14002C95C
0x14002c95a  xor     ebx, ebx
0x14002c95c  mov     [rsp+48h+arg_0], rbx
0x14002c961  test    rbx, rbx
0x14002c964  jz      short loc_14002C97F
0x14002c966  mov     [rsp+48h+arg_0], 0
0x14002c96f  mov     rax, [rsi]
0x14002c972  mov     [rbx], rax
0x14002c975  mov     [rbx+8], rbx
0x14002c979  mov     [rsi], rbx
0x14002c97c  inc     dword ptr [rsi+7Ch]
0x14002c97f  lea     rcx, [rsp+48h+arg_0]
0x14002c984  call    ??1?$TPointer@VCThreadSmartWait@@@@QEAA@XZ; TPointer<CThreadSmartWait>::~TPointer<CThreadSmartWait>(void)
0x14002c989  jmp     short loc_14002C990
0x14002c98b  mov     rbx, [rsp+48h+arg_10]
0x14002c990  test    rbx, rbx
0x14002c993  jz      short loc_14002C999
0x14002c995  mov     byte ptr [rbx+1Ch], 1
0x14002c999  lea     rcx, [rdi+38h]; lpCriticalSection
0x14002c99d  call    cs:__imp_EnterCriticalSection
0x14002c9a3  cmp     dword ptr [rdi], 1
0x14002c9a6  jnz     short loc_14002C9AF
0x14002c9a8  mov     dword ptr [rdi+4], 0FFFFFFFFh
0x14002c9af  lock dec dword ptr [rdi]
0x14002c9b2  mov     rcx, rdi; this
0x14002c9b5  call    ?LokInitReadEvent@CSyncReadWrite@@AEAAXXZ; CSyncReadWrite::LokInitReadEvent(void)
0x14002c9ba  mov     rcx, [rdi+60h]; this
0x14002c9be  call    ?Set@CEventSem@@QEAAXXZ; CEventSem::Set(void)
0x14002c9c3  lea     rcx, [rdi+38h]; lpCriticalSection
0x14002c9c7  call    cs:__imp_LeaveCriticalSection
0x14002c9cd  lea     rcx, [rdi+10h]; lpCriticalSection
0x14002c9d1  call    cs:__imp_LeaveCriticalSection
0x14002c9d7  nop
0x14002c9d8  test    rbx, rbx
0x14002c9db  jz      short loc_14002C9EC
0x14002c9dd  mov     r8d, [rsi+7Ch]; unsigned int
0x14002c9e1  mov     rdx, r14; void *
0x14002c9e4  mov     rcx, rbx; this
0x14002c9e7  call    ?Wait@CThreadSmartWait@@QEAAXPEAXK@Z; CThreadSmartWait::Wait(void *,ulong)
0x14002c9ec  mov     rbx, [rsp+48h+arg_8]
0x14002c9f1  mov     rbp, [rsp+48h+arg_18]
0x14002c9f6  add     rsp, 30h
0x14002c9fa  pop     r14
0x14002c9fc  pop     rdi
0x14002c9fd  pop     rsi
0x14002c9fe  retn
```
