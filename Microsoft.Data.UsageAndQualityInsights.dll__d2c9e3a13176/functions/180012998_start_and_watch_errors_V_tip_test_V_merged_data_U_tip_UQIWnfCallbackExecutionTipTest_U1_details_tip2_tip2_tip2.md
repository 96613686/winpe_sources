# ??$start_and_watch_errors@V?$tip_test@V?$merged_data@U_tip_UQIWnfCallbackExecutionTipTest@@U1@@details@tip2@@@tip2@@@tip2@@YA?A_PXZ

- ea: `0x180012998`
- end: `0x180012a9b`
- name: `??$start_and_watch_errors@V?$tip_test@V?$merged_data@U_tip_UQIWnfCallbackExecutionTipTest@@U1@@details@tip2@@@tip2@@@tip2@@YA?A_PXZ`
- size: `259`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180015930`
- `0x18001d95c`

## callees

- `0x180008320`
- `0x180012998`
- `0x180012bb0`
- `0x180013bbc`
- `0x180018e64`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180012a4e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180012a4e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800129e3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012a82`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800129e3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012a82`

## pseudocode

```c
__int64 __fastcall tip2::start_and_watch_errors<tip2::tip_test<tip2::details::merged_data<_tip_UQIWnfCallbackExecutionTipTest,_tip_UQIWnfCallbackExecutionTipTest>>>(
        __int64 a1)
{
  volatile signed __int32 **v2; // rax
  volatile signed __int32 *v3; // rbx
  void *v4; // rdi
  __int64 v5; // rdx
  __int64 v6; // rcx
  _QWORD *v7; // rdi
  _QWORD *Local; // rax
  _BYTE v10[24]; // [rsp+20h] [rbp-18h] BYREF
  LPVOID pv; // [rsp+48h] [rbp+10h] BYREF

  v2 = (volatile signed __int32 **)tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_UQIWnfCallbackExecutionTipTest,_tip_UQIWnfCallbackExecutionTipTest>,>(&pv);
  v3 = *v2;
  *v2 = 0;
  v4 = pv;
  if ( pv && _InterlockedExchangeAdd((volatile signed __int32 *)pv + 70, 0xFFFFFFFF) == 1 )
  {
    tip2::details::merged_data<_tip_UQIWnfCallbackExecutionTipTest,_tip_UQIWnfCallbackExecutionTipTest>::~merged_data<_tip_UQIWnfCallbackExecutionTipTest,_tip_UQIWnfCallbackExecutionTipTest>(v4);
    CoTaskMemFree(v4);
  }
  tip2::details::shared_data<0,0,0>::start(v3 + 2, v10);
  *(_QWORD *)a1 = &tip2::test_watcher<tip2::details::merged_data<_tip_UQIWnfCallbackExecutionTipTest,_tip_UQIWnfCallbackExecutionTipTest>>::`vftable';
  v7 = (_QWORD *)(a1 + 8);
  *(_QWORD *)(a1 + 8) = 0;
  *(_QWORD *)(a1 + 16) = a1;
  *(_QWORD *)(a1 + 24) = 0;
  *(_DWORD *)(a1 + 32) = 0;
  *(_QWORD *)(a1 + 40) = 0;
  *(_BYTE *)(a1 + 48) = 0;
  if ( wil::details::g_pThreadFailureCallbacks )
  {
    LOBYTE(v5) = 1;
    Local = (_QWORD *)wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
                        v6,
                        v5);
    *v7 = Local;
    if ( Local )
    {
      *(_QWORD *)(a1 + 24) = *Local;
      *Local = v7;
      *(_DWORD *)(a1 + 32) = GetCurrentThreadId();
    }
  }
  *(_QWORD *)(a1 + 56) = v3;
  if ( v3 )
  {
    _InterlockedIncrement(v3 + 70);
    if ( _InterlockedExchangeAdd(v3 + 70, 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<_tip_UQIWnfCallbackExecutionTipTest,_tip_UQIWnfCallbackExecutionTipTest>::~merged_data<_tip_UQIWnfCallbackExecutionTipTest,_tip_UQIWnfCallbackExecutionTipTest>(v3);
      CoTaskMemFree((LPVOID)v3);
    }
  }
  return a1;
}

```

## disassembly

```asm
0x180012998  mov     [rsp+arg_10], rbx
0x18001299d  mov     [rsp+arg_18], rsi
0x1800129a2  push    rdi
0x1800129a3  sub     rsp, 30h
0x1800129a7  mov     rsi, rcx
0x1800129aa  lea     rcx, [rsp+38h+pv]
0x1800129af  call    ??$tip_make_shared_nothrow@V?$merged_data@U_tip_UQIWnfCallbackExecutionTipTest@@U1@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_UQIWnfCallbackExecutionTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_UQIWnfCallbackExecutionTipTest,_tip_UQIWnfCallbackExecutionTipTest>,>(void)
0x1800129b4  mov     rbx, [rax]
0x1800129b7  mov     qword ptr [rax], 0
0x1800129be  mov     rdi, [rsp+38h+pv]
0x1800129c3  test    rdi, rdi
0x1800129c6  jz      short loc_1800129E9
0x1800129c8  or      eax, 0FFFFFFFFh
0x1800129cb  lock xadd [rdi+118h], eax
0x1800129d3  cmp     eax, 1
0x1800129d6  jnz     short loc_1800129E9
0x1800129d8  mov     rcx, rdi
0x1800129db  call    ??1?$merged_data@U_tip_UQIWnfCallbackExecutionTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_UQIWnfCallbackExecutionTipTest,_tip_UQIWnfCallbackExecutionTipTest>::~merged_data<_tip_UQIWnfCallbackExecutionTipTest,_tip_UQIWnfCallbackExecutionTipTest>(void)
0x1800129e0  mov     rcx, rdi; pv
0x1800129e3  call    cs:__imp_CoTaskMemFree
0x1800129e9  lea     rcx, [rbx+8]
0x1800129ed  lea     rdx, [rsp+38h+var_18]
0x1800129f2  call    ?start@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ; tip2::details::shared_data<0,0,0>::start(void)
0x1800129f7  lea     rax, ??_7?$test_watcher@V?$merged_data@U_tip_UQIWnfCallbackExecutionTipTest@@U1@@details@tip2@@@tip2@@6B@; const tip2::test_watcher<tip2::details::merged_data<_tip_UQIWnfCallbackExecutionTipTest,_tip_UQIWnfCallbackExecutionTipTest>>::`vftable'
0x1800129fe  mov     [rsi], rax
0x180012a01  lea     rdi, [rsi+8]
0x180012a05  mov     qword ptr [rdi], 0
0x180012a0c  mov     [rdi+8], rsi
0x180012a10  mov     qword ptr [rdi+10h], 0
0x180012a18  mov     dword ptr [rdi+18h], 0
0x180012a1f  mov     qword ptr [rdi+20h], 0
0x180012a27  mov     byte ptr [rdi+28h], 0
0x180012a2b  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180012a33  jz      short loc_180012A57
0x180012a35  mov     dl, 1
0x180012a37  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x180012a3c  mov     [rdi], rax
0x180012a3f  test    rax, rax
0x180012a42  jz      short loc_180012A57
0x180012a44  mov     rcx, [rax]
0x180012a47  mov     [rdi+10h], rcx
0x180012a4b  mov     [rax], rdi
0x180012a4e  call    cs:__imp_GetCurrentThreadId
0x180012a54  mov     [rdi+18h], eax
0x180012a57  mov     [rsi+38h], rbx
0x180012a5b  test    rbx, rbx
0x180012a5e  jz      short loc_180012A88
0x180012a60  lock inc dword ptr [rbx+118h]
0x180012a67  or      eax, 0FFFFFFFFh
0x180012a6a  lock xadd [rbx+118h], eax
0x180012a72  cmp     eax, 1
0x180012a75  jnz     short loc_180012A88
0x180012a77  mov     rcx, rbx
0x180012a7a  call    ??1?$merged_data@U_tip_UQIWnfCallbackExecutionTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_UQIWnfCallbackExecutionTipTest,_tip_UQIWnfCallbackExecutionTipTest>::~merged_data<_tip_UQIWnfCallbackExecutionTipTest,_tip_UQIWnfCallbackExecutionTipTest>(void)
0x180012a7f  mov     rcx, rbx; pv
0x180012a82  call    cs:__imp_CoTaskMemFree
0x180012a88  mov     rax, rsi
0x180012a8b  mov     rbx, [rsp+38h+arg_10]
0x180012a90  mov     rsi, [rsp+38h+arg_18]
0x180012a95  add     rsp, 30h
0x180012a99  pop     rdi
0x180012a9a  retn
```
