# CHandlerInfo::Synchronize(bool,HWND__ *,bool,IUnknown *,ushort const * *,uint,SYNCMGR_SYNC_CONTROL_FLAGS,ISyncMgrSyncResult *)

- ea: `0x180017838`
- end: `0x1800179b3`
- name: `?Synchronize@CHandlerInfo@@QEAAJ_NPEAUHWND__@@0PEAUIUnknown@@PEAPEBGIW4SYNCMGR_SYNC_CONTROL_FLAGS@@PEAUISyncMgrSyncResult@@@Z`
- size: `379`
- prototype: `__int64 __usercall@<rax>(CHandlerInfo *__hidden this@<rcx>, bool@<dl>, HWND@<r8>, bool@<r9b>, struct IUnknown *, const unsigned __int16 **, unsigned int, enum SYNCMGR_SYNC_CONTROL_FLAGS, struct ISyncMgrSyncResult *)`
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180009078`
- `0x180015020`

## callees

- `0x1800074a4`
- `0x18000a714`
- `0x180012e54`
- `0x180017838`
- `0x180019f8c`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017892`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001798f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017892`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001798f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180017855`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180017910`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180017855`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180017910`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180017967`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180017967`

## pseudocode

```c
__int64 __fastcall CHandlerInfo::Synchronize(
        CHandlerInfo *this,
        bool a2,
        HWND a3,
        bool a4,
        struct IUnknown *a5,
        const unsigned __int16 **a6,
        unsigned int a7,
        enum SYNCMGR_SYNC_CONTROL_FLAGS a8,
        struct ISyncMgrSyncResult *a9)
{
  bool v13; // di
  bool v14; // si
  int Error; // edi
  char v16; // si
  int *v17; // rax
  __int64 v18; // rcx
  HANDLE Thread; // rax

  EnterCriticalSection(*((LPCRITICAL_SECTION *)this + 1));
  v13 = (**((int (__fastcall ***)(char *))this + 5))((char *)this + 40) >= 4 && (*((_DWORD *)this + 222) & 0x400) != 0;
  v14 = *((_DWORD *)this + 502) == 1;
  LeaveCriticalSection(*((LPCRITICAL_SECTION *)this + 1));
  if ( v13 )
  {
    Error = CHandlerInfo::_QueueSyncRequest(this, v14, v13, a2, a3, a4, a5, a6, a7, a8, a9);
    if ( Error >= 0 )
    {
      v16 = 0;
      EnterCriticalSection(*((LPCRITICAL_SECTION *)this + 1));
      v17 = (int *)*((_QWORD *)this + 255);
      if ( v17 )
      {
        if ( *v17 > 0 && !*((_QWORD *)this + 256) )
        {
          v18 = *((_QWORD *)this + 2);
          _InterlockedExchange((volatile __int32 *)(v18 + 96), 0);
          _InterlockedIncrement((volatile signed __int32 *)(v18 + 396));
          _InterlockedIncrement((volatile signed __int32 *)this + 519);
          Thread = CreateThread(0, 0, CHandlerInfo::s_SyncThreadProc, this, 0, 0);
          *((_QWORD *)this + 256) = Thread;
          if ( !Thread )
          {
            Error = ResultFromKnownLastError();
            v16 = 1;
            CHandlerInfo::Release(this);
          }
        }
      }
      LeaveCriticalSection(*((LPCRITICAL_SECTION *)this + 1));
      if ( v16 == 1 )
        CHandlerCache::Release(*((CHandlerCache **)this + 2));
    }
  }
  else
  {
    return (unsigned int)-2147024891;
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180017838  push    rbx
0x18001783a  push    rbp
0x18001783b  push    rsi
0x18001783c  push    rdi
0x18001783d  push    r14
0x18001783f  push    r15
0x180017841  sub     rsp, 68h
0x180017845  mov     rbx, rcx
0x180017848  mov     bpl, r9b
0x18001784b  mov     rcx, [rcx+8]; lpCriticalSection
0x18001784f  mov     r14, r8
0x180017852  mov     r15b, dl
0x180017855  call    cs:__imp_EnterCriticalSection
0x18001785b  lea     rcx, [rbx+28h]
0x18001785f  mov     rax, [rcx]
0x180017862  mov     rax, [rax]
0x180017865  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001786a  cmp     eax, 4
0x18001786d  jl      short loc_180017880
0x18001786f  test    dword ptr [rbx+378h], 400h
0x180017879  jz      short loc_180017880
0x18001787b  mov     dil, 1
0x18001787e  jmp     short loc_180017883
0x180017880  xor     dil, dil
0x180017883  cmp     dword ptr [rbx+7D8h], 1
0x18001788a  mov     rcx, [rbx+8]; lpCriticalSection
0x18001788e  setz    sil
0x180017892  call    cs:__imp_LeaveCriticalSection
0x180017898  test    dil, dil
0x18001789b  jnz     short loc_1800178A7
0x18001789d  mov     edi, 80070005h
0x1800178a2  jmp     loc_1800179A4
0x1800178a7  mov     rax, [rsp+98h+arg_40]
0x1800178af  mov     r9b, r15b; bool
0x1800178b2  mov     [rsp+98h+var_48], rax; struct ISyncMgrSyncResult *
0x1800178b7  mov     r8b, dil; bool
0x1800178ba  mov     eax, [rsp+98h+arg_38]
0x1800178c1  mov     dl, sil; bool
0x1800178c4  mov     [rsp+98h+var_50], eax; enum SYNCMGR_SYNC_CONTROL_FLAGS
0x1800178c8  mov     rcx, rbx; this
0x1800178cb  mov     eax, [rsp+98h+arg_30]
0x1800178d2  mov     [rsp+98h+var_58], eax; unsigned int
0x1800178d6  mov     rax, [rsp+98h+arg_28]
0x1800178de  mov     [rsp+98h+var_60], rax; unsigned __int16 **
0x1800178e3  mov     rax, [rsp+98h+arg_20]
0x1800178eb  mov     [rsp+98h+var_68], rax; struct IUnknown *
0x1800178f0  mov     byte ptr [rsp+98h+lpThreadId], bpl; bool
0x1800178f5  mov     qword ptr [rsp+98h+dwCreationFlags], r14; HWND
0x1800178fa  call    ?_QueueSyncRequest@CHandlerInfo@@AEAAJ_N00PEAUHWND__@@0PEAUIUnknown@@PEAPEBGIW4SYNCMGR_SYNC_CONTROL_FLAGS@@PEAUISyncMgrSyncResult@@@Z; CHandlerInfo::_QueueSyncRequest(bool,bool,bool,HWND__ *,bool,IUnknown *,ushort const * *,uint,SYNCMGR_SYNC_CONTROL_FLAGS,ISyncMgrSyncResult *)
0x1800178ff  mov     edi, eax
0x180017901  test    eax, eax
0x180017903  js      loc_1800179A4
0x180017909  mov     rcx, [rbx+8]; lpCriticalSection
0x18001790d  xor     sil, sil
0x180017910  call    cs:__imp_EnterCriticalSection
0x180017916  mov     rax, [rbx+7F8h]
0x18001791d  test    rax, rax
0x180017920  jz      short loc_18001798B
0x180017922  cmp     dword ptr [rax], 0
0x180017925  jle     short loc_18001798B
0x180017927  cmp     qword ptr [rbx+800h], 0
0x18001792f  jnz     short loc_18001798B
0x180017931  mov     rcx, [rbx+10h]
0x180017935  xor     eax, eax
0x180017937  xchg    eax, [rcx+60h]
0x18001793a  lock inc dword ptr [rcx+18Ch]
0x180017941  lock inc dword ptr [rbx+81Ch]
0x180017948  mov     [rsp+98h+lpThreadId], 0; lpThreadId
0x180017951  lea     r8, ?s_SyncThreadProc@CHandlerInfo@@CAKPEAX@Z; lpStartAddress
0x180017958  mov     r9, rbx; lpParameter
0x18001795b  mov     [rsp+98h+dwCreationFlags], 0; dwCreationFlags
0x180017963  xor     edx, edx; dwStackSize
0x180017965  xor     ecx, ecx; lpThreadAttributes
0x180017967  call    cs:__imp_CreateThread
0x18001796d  mov     [rbx+800h], rax
0x180017974  test    rax, rax
0x180017977  jnz     short loc_18001798B
0x180017979  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18001797e  mov     rcx, rbx; this
0x180017981  mov     edi, eax
0x180017983  mov     sil, 1
0x180017986  call    ?Release@CHandlerInfo@@QEAAKXZ; CHandlerInfo::Release(void)
0x18001798b  mov     rcx, [rbx+8]; lpCriticalSection
0x18001798f  call    cs:__imp_LeaveCriticalSection
0x180017995  cmp     sil, 1
0x180017999  jnz     short loc_1800179A4
0x18001799b  mov     rcx, [rbx+10h]; this
0x18001799f  call    ?Release@CHandlerCache@@QEAAJXZ; CHandlerCache::Release(void)
0x1800179a4  mov     eax, edi
0x1800179a6  add     rsp, 68h
0x1800179aa  pop     r15
0x1800179ac  pop     r14
0x1800179ae  pop     rdi
0x1800179af  pop     rsi
0x1800179b0  pop     rbp
0x1800179b1  pop     rbx
0x1800179b2  retn
```
