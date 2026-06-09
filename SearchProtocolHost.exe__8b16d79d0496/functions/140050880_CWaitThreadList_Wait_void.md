# CWaitThreadList::Wait(void *)

- ea: `0x140050880`
- end: `0x1400509a3`
- name: `?Wait@CWaitThreadList@@QEAAXPEAX@Z`
- size: `291`
- prototype: `void(CWaitThreadList *__hidden this, void *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x140032394`

## callees

- `0x1400055b4`
- `0x14000eb38`
- `0x14002004c`
- `0x14004fc7c`
- `0x14004ff64`
- `0x14004fff8`
- `0x140050338`
- `0x140050630`
- `0x140050880`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140050941`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140050941`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14005096b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140050975`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14005096b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140050975`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400508a9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400508a9`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CWaitThreadList::Wait(CWaitThreadList *this, void *a2)
{
  volatile signed __int32 *v4; // rdi
  CThreadSmartWait *v5; // rax
  CThreadSmartWait *v6; // rbx
  CThreadSmartWait *v7; // [rsp+50h] [rbp+8h] BYREF
  CThreadSmartWait *v8; // [rsp+60h] [rbp+18h] BYREF

  v8 = 0;
  LODWORD(v7) = GetCurrentThreadId();
  v4 = (volatile signed __int32 *)((char *)this + 8);
  CSyncReadWrite::GetWriteAccess((CWaitThreadList *)((char *)this + 8));
  if ( (unsigned int)TKeyedLiteSList<unsigned long,CThreadSmartWait,TPointer<CThreadSmartWait>>::LookupByKey(
                       this,
                       &v7,
                       &v8) )
  {
    v6 = v8;
  }
  else
  {
    v5 = (CThreadSmartWait *)operator new(0x38u, (const struct std::nothrow_t *)&std::nothrow);
    v7 = v5;
    if ( v5 )
      v6 = CThreadSmartWait::CThreadSmartWait(v5, *((_DWORD *)this + 30));
    else
      v6 = 0;
    v7 = v6;
    if ( v6 )
    {
      v7 = 0;
      *(_QWORD *)v6 = *(_QWORD *)this;
      *((_QWORD *)v6 + 1) = v6;
      *(_QWORD *)this = v6;
      ++*((_DWORD *)this + 31);
    }
    TPointer<CThreadSmartWait>::~TPointer<CThreadSmartWait>(&v7);
  }
  if ( v6 )
    *((_BYTE *)v6 + 28) = 1;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  if ( *v4 == 1 )
    *((_DWORD *)this + 3) = -1;
  _InterlockedDecrement(v4);
  CSyncReadWrite::LokInitReadEvent((CWaitThreadList *)((char *)this + 8));
  CEventSem::Set(*((CEventSem **)this + 13));
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  if ( v6 )
    CThreadSmartWait::Wait(v6, a2, *((_DWORD *)this + 31));
}

```

## disassembly

```asm
0x140050880  mov     rax, rsp
0x140050883  push    rsi
0x140050884  push    rdi
0x140050885  push    r14
0x140050887  sub     rsp, 30h
0x14005088b  mov     qword ptr [rax-28h], 0FFFFFFFFFFFFFFFEh
0x140050893  mov     [rax+10h], rbx
0x140050897  mov     [rax+20h], rbp
0x14005089b  mov     r14, rdx
0x14005089e  mov     rsi, rcx
0x1400508a1  mov     qword ptr [rax+18h], 0
0x1400508a9  call    cs:__imp_GetCurrentThreadId
0x1400508af  mov     dword ptr [rsp+48h+arg_0], eax
0x1400508b3  lea     rdi, [rsi+8]
0x1400508b7  mov     rcx, rdi; this
0x1400508ba  call    ?GetWriteAccess@CSyncReadWrite@@QEAAXXZ; CSyncReadWrite::GetWriteAccess(void)
0x1400508bf  lea     r8, [rsp+48h+arg_10]
0x1400508c4  lea     rdx, [rsp+48h+arg_0]
0x1400508c9  mov     rcx, rsi
0x1400508cc  call    ?LookupByKey@?$TKeyedLiteSList@KVCThreadSmartWait@@V?$TPointer@VCThreadSmartWait@@@@@@QEAAHPEBKPEAPEAVCThreadSmartWait@@@Z; TKeyedLiteSList<ulong,CThreadSmartWait,TPointer<CThreadSmartWait>>::LookupByKey(ulong const *,CThreadSmartWait * *)
0x1400508d1  test    eax, eax
0x1400508d3  jnz     short loc_14005092F
0x1400508d5  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400508dc  lea     ecx, [rax+38h]; unsigned __int64
0x1400508df  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1400508e4  mov     [rsp+48h+arg_0], rax
0x1400508e9  test    rax, rax
0x1400508ec  jz      short loc_1400508FE
0x1400508ee  mov     edx, [rsi+78h]; unsigned int
0x1400508f1  mov     rcx, rax; this
0x1400508f4  call    ??0CThreadSmartWait@@QEAA@K@Z; CThreadSmartWait::CThreadSmartWait(ulong)
0x1400508f9  mov     rbx, rax
0x1400508fc  jmp     short loc_140050900
0x1400508fe  xor     ebx, ebx
0x140050900  mov     [rsp+48h+arg_0], rbx
0x140050905  test    rbx, rbx
0x140050908  jz      short loc_140050923
0x14005090a  mov     [rsp+48h+arg_0], 0
0x140050913  mov     rax, [rsi]
0x140050916  mov     [rbx], rax
0x140050919  mov     [rbx+8], rbx
0x14005091d  mov     [rsi], rbx
0x140050920  inc     dword ptr [rsi+7Ch]
0x140050923  lea     rcx, [rsp+48h+arg_0]
0x140050928  call    ??1?$TPointer@VCThreadSmartWait@@@@QEAA@XZ; TPointer<CThreadSmartWait>::~TPointer<CThreadSmartWait>(void)
0x14005092d  jmp     short loc_140050934
0x14005092f  mov     rbx, [rsp+48h+arg_10]
0x140050934  test    rbx, rbx
0x140050937  jz      short loc_14005093D
0x140050939  mov     byte ptr [rbx+1Ch], 1
0x14005093d  lea     rcx, [rdi+38h]; lpCriticalSection
0x140050941  call    cs:__imp_EnterCriticalSection
0x140050947  cmp     dword ptr [rdi], 1
0x14005094a  jnz     short loc_140050953
0x14005094c  mov     dword ptr [rdi+4], 0FFFFFFFFh
0x140050953  lock dec dword ptr [rdi]
0x140050956  mov     rcx, rdi; this
0x140050959  call    ?LokInitReadEvent@CSyncReadWrite@@AEAAXXZ; CSyncReadWrite::LokInitReadEvent(void)
0x14005095e  mov     rcx, [rdi+60h]; this
0x140050962  call    ?Set@CEventSem@@QEAAXXZ; CEventSem::Set(void)
0x140050967  lea     rcx, [rdi+38h]; lpCriticalSection
0x14005096b  call    cs:__imp_LeaveCriticalSection
0x140050971  lea     rcx, [rdi+10h]; lpCriticalSection
0x140050975  call    cs:__imp_LeaveCriticalSection
0x14005097b  nop
0x14005097c  test    rbx, rbx
0x14005097f  jz      short loc_140050990
0x140050981  mov     r8d, [rsi+7Ch]; unsigned int
0x140050985  mov     rdx, r14; void *
0x140050988  mov     rcx, rbx; this
0x14005098b  call    ?Wait@CThreadSmartWait@@QEAAXPEAXK@Z; CThreadSmartWait::Wait(void *,ulong)
0x140050990  mov     rbx, [rsp+48h+arg_8]
0x140050995  mov     rbp, [rsp+48h+arg_18]
0x14005099a  add     rsp, 30h
0x14005099e  pop     r14
0x1400509a0  pop     rdi
0x1400509a1  pop     rsi
0x1400509a2  retn
```
