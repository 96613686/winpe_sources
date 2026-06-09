# HNS::Service::Core::StorageManager::Stop(void)

- ea: `0x1800b3ae0`
- end: `0x1800b3c48`
- name: `?Stop@StorageManager@Core@Service@HNS@@UEAAXXZ`
- size: `360`
- prototype: `void __fastcall(HNS::Service::Core::StorageManager *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x180075040`

## callees

- `0x180075520`
- `0x1800759d8`
- `0x180075aac`
- `0x1800b3ae0`
- `0x1801a0b1c`
- `0x1801a0c64`
- `0x1802b7010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800b3bbd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800b3bbd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b3b8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b3b8e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800b3b13`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800b3b74`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800b3b9e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800b3b13`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800b3b74`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800b3b9e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x1800b3b22`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x1800b3bac`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x1800b3b22`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x1800b3bac`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800b3bb5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800b3bb5`

## string_xrefs

- `0x1800b3af1`: `HNS::Service::Core::StorageManager::Stop`
- `0x1800b3c33`: `HNS::Service::Core::StorageManager::Stop`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall HNS::Service::Core::StorageManager::Stop(PTP_WAIT *this)
{
  struct _TP_WAIT *v2; // rbp
  DWORD LastError; // ebx
  volatile signed __int32 *v4; // rbx

  HNSTraceProvider::TraceEnter("HNS::Service::Core::StorageManager::Stop", 0x86u);
  if ( *((_DWORD *)this + 20) == 2 )
  {
    SetThreadpoolWait(this[702], 0, 0);
    WaitForThreadpoolWaitCallbacks(this[702], 0);
    if ( *((_DWORD *)this + 20) == 2 )
      HNSObjectStorage::FlushObjects((HNSObjectStorage *)(this + 13), 1u);
    HNS::Service::Interface::IManager::Stop((HNS::Service::Interface::IManager *)this);
    v2 = this[702];
    if ( v2 )
    {
      LastError = GetLastError();
      SetThreadpoolWait(v2, 0, 0);
      WaitForThreadpoolWaitCallbacks(v2, 1);
      CloseThreadpoolWait(v2);
      SetLastError(LastError);
    }
    this[702] = 0;
    HNSObjectStorage::Close((HNSObjectStorage *)(this + 13));
    HNS::Service::Core::StorageManager::m_instance = 0;
    v4 = (volatile signed __int32 *)qword_1803A5C40;
    qword_1803A5C40 = 0;
    if ( v4 && _InterlockedExchangeAdd(v4 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v4)(v4);
      if ( _InterlockedExchangeAdd(v4 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v4 + 8LL))(v4);
    }
    HNSTraceProvider::TraceSuccess("HNS::Service::Core::StorageManager::Stop", 0x9Cu);
  }
}

```

## disassembly

```asm
0x1800b3ae0  push    rbx
0x1800b3ae2  push    rbp
0x1800b3ae3  push    rsi
0x1800b3ae4  push    rdi
0x1800b3ae5  sub     rsp, 48h
0x1800b3ae9  mov     rdi, rcx
0x1800b3aec  mov     edx, 86h; unsigned int
0x1800b3af1  lea     rcx, aHnsServiceCore_122; "HNS::Service::Core::StorageManager::Sto"...
0x1800b3af8  call    ?TraceEnter@HNSTraceProvider@@SAXPEBDI@Z; HNSTraceProvider::TraceEnter(char const *,uint)
0x1800b3afd  cmp     dword ptr [rdi+50h], 2
0x1800b3b01  jnz     loc_1800B3C3F
0x1800b3b07  xor     r8d, r8d; pftTimeout
0x1800b3b0a  xor     edx, edx; h
0x1800b3b0c  mov     rcx, [rdi+15F0h]; pwa
0x1800b3b13  call    cs:__imp_SetThreadpoolWait
0x1800b3b19  xor     edx, edx; fCancelPendingCallbacks
0x1800b3b1b  mov     rcx, [rdi+15F0h]; pwa
0x1800b3b22  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x1800b3b28  mov     [rsp+68h+arg_0], 1
0x1800b3b2d  cmp     dword ptr [rdi+50h], 2
0x1800b3b31  jz      short loc_1800B3B39
0x1800b3b33  lea     rsi, [rdi+68h]
0x1800b3b37  jmp     short loc_1800B3B7A
0x1800b3b39  lea     rax, [rsp+68h+arg_0]
0x1800b3b3e  mov     [rsp+68h+var_48], rax
0x1800b3b43  mov     [rsp+68h+var_40], rdi
0x1800b3b48  mov     [rsp+68h+var_38], 1
0x1800b3b4d  lea     rsi, [rdi+68h]
0x1800b3b51  mov     dl, 1; unsigned __int8
0x1800b3b53  mov     rcx, rsi; this
0x1800b3b56  call    ?FlushObjects@HNSObjectStorage@@QEAAXE@Z; HNSObjectStorage::FlushObjects(uchar)
0x1800b3b5b  nop
0x1800b3b5c  cmp     [rsp+68h+arg_0], 0
0x1800b3b61  jnz     short loc_1800B3B7A
0x1800b3b63  xor     r8d, r8d; pftTimeout
0x1800b3b66  mov     rdx, [rdi+15E8h]; h
0x1800b3b6d  mov     rcx, [rdi+15F0h]; pwa
0x1800b3b74  call    cs:__imp_SetThreadpoolWait
0x1800b3b7a  mov     rcx, rdi; this
0x1800b3b7d  call    ?Stop@IManager@Interface@Service@HNS@@UEAAXXZ; HNS::Service::Interface::IManager::Stop(void)
0x1800b3b82  mov     rbp, [rdi+15F0h]
0x1800b3b89  test    rbp, rbp
0x1800b3b8c  jz      short loc_1800B3BC3
0x1800b3b8e  call    cs:__imp_GetLastError
0x1800b3b94  mov     ebx, eax
0x1800b3b96  xor     r8d, r8d; pftTimeout
0x1800b3b99  xor     edx, edx; h
0x1800b3b9b  mov     rcx, rbp; pwa
0x1800b3b9e  call    cs:__imp_SetThreadpoolWait
0x1800b3ba4  mov     edx, 1; fCancelPendingCallbacks
0x1800b3ba9  mov     rcx, rbp; pwa
0x1800b3bac  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x1800b3bb2  mov     rcx, rbp; pwa
0x1800b3bb5  call    cs:__imp_CloseThreadpoolWait
0x1800b3bbb  mov     ecx, ebx; dwErrCode
0x1800b3bbd  call    cs:__imp_SetLastError
0x1800b3bc3  mov     qword ptr [rdi+15F0h], 0
0x1800b3bce  mov     rcx, rsi; this
0x1800b3bd1  call    ?Close@HNSObjectStorage@@QEAAJXZ; HNSObjectStorage::Close(void)
0x1800b3bd6  mov     cs:?m_instance@StorageManager@Core@Service@HNS@@0V?$shared_ptr@VStorageManager@Core@Service@HNS@@@std@@A, 0; std::shared_ptr<HNS::Service::Core::StorageManager> HNS::Service::Core::StorageManager::m_instance
0x1800b3be1  mov     rbx, cs:qword_1803A5C40
0x1800b3be8  mov     cs:qword_1803A5C40, 0
0x1800b3bf3  test    rbx, rbx
0x1800b3bf6  jz      short loc_1800B3C2E
0x1800b3bf8  or      edi, 0FFFFFFFFh
0x1800b3bfb  mov     eax, edi
0x1800b3bfd  lock xadd [rbx+8], eax
0x1800b3c02  add     eax, edi
0x1800b3c04  jnz     short loc_1800B3C2E
0x1800b3c06  mov     rax, [rbx]
0x1800b3c09  mov     rcx, rbx
0x1800b3c0c  mov     rax, [rax]
0x1800b3c0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3c14  mov     eax, edi
0x1800b3c16  lock xadd [rbx+0Ch], eax
0x1800b3c1b  add     eax, edi
0x1800b3c1d  jnz     short loc_1800B3C2E
0x1800b3c1f  mov     rax, [rbx]
0x1800b3c22  mov     rcx, rbx
0x1800b3c25  mov     rax, [rax+8]
0x1800b3c29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3c2e  mov     edx, 9Ch; unsigned int
0x1800b3c33  lea     rcx, aHnsServiceCore_122; "HNS::Service::Core::StorageManager::Sto"...
0x1800b3c3a  call    ?TraceSuccess@HNSTraceProvider@@SAXPEBDI@Z; HNSTraceProvider::TraceSuccess(char const *,uint)
0x1800b3c3f  add     rsp, 48h
0x1800b3c43  pop     rdi
0x1800b3c44  pop     rsi
0x1800b3c45  pop     rbp
0x1800b3c46  pop     rbx
0x1800b3c47  retn
```
