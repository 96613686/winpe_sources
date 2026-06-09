# CSmStoreTransaction::EndTransaction(int)

- ea: `0x1800178d8`
- end: `0x1800179a4`
- name: `?EndTransaction@CSmStoreTransaction@@QEAAJH@Z`
- size: `204`
- prototype: `__int64 __fastcall(CSmStoreTransaction *__hidden this, int)`
- caller_count: `49`
- callee_count: `7`
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
- `0x180017854`
- `0x180019310`
- `0x18001ad50`
- `0x18001b180`
- `0x18001f570`
- `0x18001fea0`
- `0x1800211b0`
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
- `0x1800178d8`
- `0x1800179e0`
- `0x180017a18`
- `0x180017a70`
- `0x1800c50ec`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800178f2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180017916`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800178f2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180017916`

## pseudocode

```c
__int64 __fastcall CSmStoreTransaction::EndTransaction(CSmStoreTransaction *this, unsigned int a2)
{
  __int64 v4; // rcx
  _QWORD *v5; // rdi
  int v6; // eax
  unsigned int v7; // esi

  if ( *((_DWORD *)this + 6) )
  {
    if ( CSmStoreTransaction::m_storeLockOwningThread != GetCurrentThreadId() )
    {
      Log_AssertionEvent_3(v4, "onecoreuap\\base\\appmodel\\messagingom\\src\\storetransaction.cpp", 57);
      if ( CSmStoreTransaction::m_storeLockOwningThread != GetCurrentThreadId() )
        MicrosoftTelemetryAssertTriggeredNoArgs();
    }
    _InterlockedExchange((volatile __int32 *)&CSmStoreTransaction::m_storeLockOwningThread, 0);
    *((_DWORD *)this + 6) = 0;
    auto_threadpriority::Reset((CSmStoreTransaction *)((char *)this + 16));
  }
  v5 = (_QWORD *)((char *)this + 8);
  if ( *((_DWORD *)this + 7) )
  {
    v6 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v5 + 640LL))(*v5, a2);
    v7 = v6;
    if ( v6 < 0 )
    {
      Log_HREvent_3(v6);
      return v7;
    }
    *((_DWORD *)this + 7) = 0;
  }
  if ( *v5 )
    ATL::AtlComPtrAssign((struct IUnknown **)this + 1, 0);
  return 0;
}

```

## disassembly

```asm
0x1800178d8  mov     [rsp+arg_0], rbx
0x1800178dd  mov     [rsp+arg_8], rsi
0x1800178e2  push    rdi
0x1800178e3  sub     rsp, 30h
0x1800178e7  cmp     dword ptr [rcx+18h], 0
0x1800178eb  mov     esi, edx
0x1800178ed  mov     rbx, rcx
0x1800178f0  jz      short loc_180017943
0x1800178f2  call    cs:__imp_GetCurrentThreadId
0x1800178f8  mov     r8d, cs:?m_storeLockOwningThread@CSmStoreTransaction@@1KC; ulong volatile CSmStoreTransaction::m_storeLockOwningThread
0x1800178ff  cmp     r8d, eax
0x180017902  jz      short loc_18001792B
0x180017904  mov     r8d, 39h ; '9'
0x18001790a  lea     rdx, aOnecoreuapBase_46; "onecoreuap\\base\\appmodel\\messagingom"...
0x180017911  call    Log_AssertionEvent_3
0x180017916  call    cs:__imp_GetCurrentThreadId
0x18001791c  mov     ecx, cs:?m_storeLockOwningThread@CSmStoreTransaction@@1KC; ulong volatile CSmStoreTransaction::m_storeLockOwningThread
0x180017922  cmp     ecx, eax
0x180017924  jz      short loc_18001792B
0x180017926  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001792b  xor     eax, eax
0x18001792d  lea     rcx, [rbx+10h]; this
0x180017931  xchg    eax, cs:?m_storeLockOwningThread@CSmStoreTransaction@@1KC; ulong volatile CSmStoreTransaction::m_storeLockOwningThread
0x180017937  mov     dword ptr [rbx+18h], 0
0x18001793e  call    ?Reset@auto_threadpriority@@QEAAXXZ; auto_threadpriority::Reset(void)
0x180017943  cmp     dword ptr [rbx+1Ch], 0
0x180017947  lea     rdi, [rbx+8]
0x18001794b  jz      short loc_180017982
0x18001794d  mov     rcx, [rdi]
0x180017950  mov     edx, esi
0x180017952  mov     rax, [rcx]
0x180017955  mov     rax, [rax+280h]
0x18001795c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017961  mov     esi, eax
0x180017963  test    eax, eax
0x180017965  jns     short loc_18001797B
0x180017967  mov     edx, 1
0x18001796c  mov     ecx, eax; int
0x18001796e  lea     r9d, [rdx+41h]
0x180017972  call    Log_HREvent_3
0x180017977  mov     eax, esi
0x180017979  jmp     short loc_180017994
0x18001797b  mov     dword ptr [rbx+1Ch], 0
0x180017982  cmp     qword ptr [rdi], 0
0x180017986  jz      short loc_180017992
0x180017988  xor     edx, edx; struct IUnknown *
0x18001798a  mov     rcx, rdi; struct IUnknown **
0x18001798d  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x180017992  xor     eax, eax
0x180017994  mov     rbx, [rsp+38h+arg_0]
0x180017999  mov     rsi, [rsp+38h+arg_8]
0x18001799e  add     rsp, 30h
0x1800179a2  pop     rdi
0x1800179a3  retn
```
