# CSmStoreTransaction::StartTransaction(ISmStore *)

- ea: `0x180017aa4`
- end: `0x180017bf9`
- name: `?StartTransaction@CSmStoreTransaction@@QEAAJPEAUISmStore@@@Z`
- size: `341`
- prototype: `int(CSmStoreTransaction *__hidden this, struct ISmStore *)`
- caller_count: `48`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000d500`
- `0x18000d670`
- `0x18000d7e0`
- `0x18000da70`
- `0x18000e220`
- `0x18000e620`
- `0x18000e7c0`
- `0x18000e9c0`
- `0x18000f6d0`
- `0x18000f7f0`
- `0x180012ae0`
- `0x180012fc0`
- `0x180013240`
- `0x180019310`
- `0x18001ad50`
- `0x18001f570`
- `0x18001fea0`
- `0x1800211b0`
- `0x180021ae0`
- `0x180021ba0`
- `0x180023578`
- `0x180029c98`
- `0x180029ef4`
- `0x18002a110`
- `0x18002a6f0`
- `0x18002b3d0`
- `0x180032494`
- `0x180032848`
- `0x180032a80`
- `0x180034924`
- `0x180034c78`
- `0x1800356d8`
- `0x180035934`
- `0x180038010`
- `0x1800381d0`
- `0x180038b10`
- `0x18003bcb0`
- `0x18003c110`
- `0x18003c310`
- `0x18003c4e0`
- `0x18003c8c0`
- `0x18003d150`
- `0x18003d9a0`
- `0x18003f418`
- `0x18003fc94`
- `0x180043ee0`
- `0x180044ca0`
- `0x180045390`

## callees

- `0x1800065c8`
- `0x1800179e0`
- `0x180017a18`
- `0x180017aa4`
- `0x1800c50ec`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180017ab9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180017ad1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180017bdb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180017ab9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180017ad1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180017bdb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180017b7f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180017b95`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180017b7f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180017b95`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180017ba0`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180017ba0`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x180017b88`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x180017b88`

## pseudocode

```c
__int64 __fastcall CSmStoreTransaction::StartTransaction(CSmStoreTransaction *this, struct IUnknown *a2)
{
  signed __int32 v4; // ebx
  __int64 v5; // rcx
  _QWORD *v6; // rbx
  int v7; // ebx
  __int64 v9; // rcx
  HANDLE CurrentThread; // rax
  int ThreadPriority; // eax
  __int64 v12; // rcx
  HANDLE v13; // rax

  v4 = _InterlockedCompareExchange(
         (volatile signed __int32 *)&CSmStoreTransaction::m_storeLockOwningThread,
         CSmStoreTransaction::m_storeLockOwningThread,
         GetCurrentThreadId());
  if ( v4 != GetCurrentThreadId() )
  {
    v6 = (_QWORD *)((char *)this + 8);
    if ( *((_QWORD *)this + 1) )
    {
      Log_AssertionEvent_3(v5, "onecoreuap\\base\\appmodel\\messagingom\\src\\storetransaction.cpp", 29);
      if ( *v6 )
      {
        MicrosoftTelemetryAssertTriggeredNoArgs();
        if ( *v6 )
        {
          v7 = -2147467259;
LABEL_6:
          Log_HREvent_3(v7);
          return (unsigned int)v7;
        }
      }
    }
    if ( a2 )
      ATL::AtlComPtrAssign((struct IUnknown **)this + 1, a2);
    v7 = (*(__int64 (__fastcall **)(_QWORD, char *))(*(_QWORD *)*v6 + 632LL))(*v6, (char *)this + 28);
    if ( v7 < 0 )
      goto LABEL_6;
    if ( *((_DWORD *)this + 5) )
    {
      Log_AssertionEvent_3(v9, "onecoreuap\\private\\base\\inc\\UserDataPlatformHelper.h", 780);
      if ( *((_DWORD *)this + 5) )
        MicrosoftTelemetryAssertTriggeredNoArgs();
    }
    CurrentThread = GetCurrentThread();
    ThreadPriority = GetThreadPriority(CurrentThread);
    *((_DWORD *)this + 4) = ThreadPriority;
    if ( ThreadPriority < 0 )
    {
      v13 = GetCurrentThread();
      *((_DWORD *)this + 5) = SetThreadPriority(v13, 0);
    }
    *((_DWORD *)this + 6) = 1;
    if ( CSmStoreTransaction::m_storeLockOwningThread )
    {
      Log_AssertionEvent_3(v12, "onecoreuap\\base\\appmodel\\messagingom\\src\\storetransaction.cpp", 45);
      if ( CSmStoreTransaction::m_storeLockOwningThread )
        MicrosoftTelemetryAssertTriggeredNoArgs();
    }
    _InterlockedExchange((volatile __int32 *)&CSmStoreTransaction::m_storeLockOwningThread, GetCurrentThreadId());
  }
  return 0;
}

```

## disassembly

```asm
0x180017aa4  mov     [rsp+arg_0], rbx
0x180017aa9  mov     [rsp+arg_8], rsi
0x180017aae  push    rdi
0x180017aaf  sub     rsp, 30h
0x180017ab3  mov     rsi, rdx
0x180017ab6  mov     rdi, rcx
0x180017ab9  call    cs:__imp_GetCurrentThreadId
0x180017abf  mov     r8d, cs:?m_storeLockOwningThread@CSmStoreTransaction@@1KC; ulong volatile CSmStoreTransaction::m_storeLockOwningThread
0x180017ac6  lock cmpxchg cs:?m_storeLockOwningThread@CSmStoreTransaction@@1KC, r8d; ulong volatile CSmStoreTransaction::m_storeLockOwningThread
0x180017acf  mov     ebx, eax
0x180017ad1  call    cs:__imp_GetCurrentThreadId
0x180017ad7  cmp     ebx, eax
0x180017ad9  jz      loc_180017BE7
0x180017adf  lea     rbx, [rdi+8]
0x180017ae3  cmp     qword ptr [rbx], 0
0x180017ae7  jz      short loc_180017B25
0x180017ae9  mov     r8d, 1Dh
0x180017aef  lea     rdx, aOnecoreuapBase_46; "onecoreuap\\base\\appmodel\\messagingom"...
0x180017af6  call    Log_AssertionEvent_3
0x180017afb  cmp     qword ptr [rbx], 0
0x180017aff  jz      short loc_180017B25
0x180017b01  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180017b06  cmp     qword ptr [rbx], 0
0x180017b0a  jz      short loc_180017B25
0x180017b0c  xor     edx, edx
0x180017b0e  mov     ebx, 80004005h
0x180017b13  lea     r9d, [rdx+1Eh]
0x180017b17  mov     ecx, ebx; int
0x180017b19  call    Log_HREvent_3
0x180017b1e  mov     eax, ebx
0x180017b20  jmp     loc_180017BE9
0x180017b25  test    rsi, rsi
0x180017b28  jz      short loc_180017B35
0x180017b2a  mov     rdx, rsi; struct IUnknown *
0x180017b2d  mov     rcx, rbx; struct IUnknown **
0x180017b30  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x180017b35  mov     rcx, [rbx]
0x180017b38  lea     rdx, [rdi+1Ch]
0x180017b3c  mov     rax, [rcx]
0x180017b3f  mov     rax, [rax+278h]
0x180017b46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017b4b  mov     ebx, eax
0x180017b4d  test    eax, eax
0x180017b4f  jns     short loc_180017B5C
0x180017b51  mov     edx, 1
0x180017b56  lea     r9d, [rdx+20h]
0x180017b5a  jmp     short loc_180017B17
0x180017b5c  cmp     dword ptr [rdi+14h], 0
0x180017b60  jz      short loc_180017B7F
0x180017b62  mov     r8d, 30Ch
0x180017b68  lea     rdx, aOnecoreuapPriv_0; "onecoreuap\\private\\base\\inc\\UserDat"...
0x180017b6f  call    Log_AssertionEvent_3
0x180017b74  cmp     dword ptr [rdi+14h], 0
0x180017b78  jz      short loc_180017B7F
0x180017b7a  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180017b7f  call    cs:__imp_GetCurrentThread
0x180017b85  mov     rcx, rax; hThread
0x180017b88  call    cs:__imp_GetThreadPriority
0x180017b8e  mov     [rdi+10h], eax
0x180017b91  test    eax, eax
0x180017b93  jns     short loc_180017BA9
0x180017b95  call    cs:__imp_GetCurrentThread
0x180017b9b  mov     rcx, rax; hThread
0x180017b9e  xor     edx, edx; nPriority
0x180017ba0  call    cs:__imp_SetThreadPriority
0x180017ba6  mov     [rdi+14h], eax
0x180017ba9  mov     dword ptr [rdi+18h], 1
0x180017bb0  mov     eax, cs:?m_storeLockOwningThread@CSmStoreTransaction@@1KC; ulong volatile CSmStoreTransaction::m_storeLockOwningThread
0x180017bb6  test    eax, eax
0x180017bb8  jz      short loc_180017BDB
0x180017bba  mov     r8d, 2Dh ; '-'
0x180017bc0  lea     rdx, aOnecoreuapBase_46; "onecoreuap\\base\\appmodel\\messagingom"...
0x180017bc7  call    Log_AssertionEvent_3
0x180017bcc  mov     eax, cs:?m_storeLockOwningThread@CSmStoreTransaction@@1KC; ulong volatile CSmStoreTransaction::m_storeLockOwningThread
0x180017bd2  test    eax, eax
0x180017bd4  jz      short loc_180017BDB
0x180017bd6  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180017bdb  call    cs:__imp_GetCurrentThreadId
0x180017be1  xchg    eax, cs:?m_storeLockOwningThread@CSmStoreTransaction@@1KC; ulong volatile CSmStoreTransaction::m_storeLockOwningThread
0x180017be7  xor     eax, eax
0x180017be9  mov     rbx, [rsp+38h+arg_0]
0x180017bee  mov     rsi, [rsp+38h+arg_8]
0x180017bf3  add     rsp, 30h
0x180017bf7  pop     rdi
0x180017bf8  retn
```
