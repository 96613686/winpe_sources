# ??$start_and_watch_errors@V?$tip_test@V?$merged_data@U_tip_UQIWnfSubscriptionCreationTipTest@@U1@@details@tip2@@@tip2@@@tip2@@YA?A_PXZ

- ea: `0x180012aa4`
- end: `0x180012ba7`
- name: `??$start_and_watch_errors@V?$tip_test@V?$merged_data@U_tip_UQIWnfSubscriptionCreationTipTest@@U1@@details@tip2@@@tip2@@@tip2@@YA?A_PXZ`
- size: `259`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180014c40`
- `0x18001c64c`

## callees

- `0x180008320`
- `0x180012aa4`
- `0x180012c70`
- `0x180013c48`
- `0x180018e64`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180012b5a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180012b5a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012aef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012b8e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012aef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012b8e`

## pseudocode

```c
__int64 __fastcall tip2::start_and_watch_errors<tip2::tip_test<tip2::details::merged_data<_tip_UQIWnfSubscriptionCreationTipTest,_tip_UQIWnfSubscriptionCreationTipTest>>>(
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

  v2 = (volatile signed __int32 **)tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_UQIWnfSubscriptionCreationTipTest,_tip_UQIWnfSubscriptionCreationTipTest>,>(&pv);
  v3 = *v2;
  *v2 = 0;
  v4 = pv;
  if ( pv && _InterlockedExchangeAdd((volatile signed __int32 *)pv + 68, 0xFFFFFFFF) == 1 )
  {
    tip2::details::merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>::~merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>(v4);
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
    _InterlockedIncrement(v3 + 68);
    if ( _InterlockedExchangeAdd(v3 + 68, 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>::~merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>(v3);
      CoTaskMemFree((LPVOID)v3);
    }
  }
  return a1;
}

```

## disassembly

```asm
0x180012aa4  mov     [rsp+arg_10], rbx
0x180012aa9  mov     [rsp+arg_18], rsi
0x180012aae  push    rdi
0x180012aaf  sub     rsp, 30h
0x180012ab3  mov     rsi, rcx
0x180012ab6  lea     rcx, [rsp+38h+pv]
0x180012abb  call    ??$tip_make_shared_nothrow@V?$merged_data@U_tip_UQIWnfSubscriptionCreationTipTest@@U1@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_UQIWnfSubscriptionCreationTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_UQIWnfSubscriptionCreationTipTest,_tip_UQIWnfSubscriptionCreationTipTest>,>(void)
0x180012ac0  mov     rbx, [rax]
0x180012ac3  mov     qword ptr [rax], 0
0x180012aca  mov     rdi, [rsp+38h+pv]
0x180012acf  test    rdi, rdi
0x180012ad2  jz      short loc_180012AF5
0x180012ad4  or      eax, 0FFFFFFFFh
0x180012ad7  lock xadd [rdi+110h], eax
0x180012adf  cmp     eax, 1
0x180012ae2  jnz     short loc_180012AF5
0x180012ae4  mov     rcx, rdi
0x180012ae7  call    ??1?$merged_data@U_tip_UQIGetOrCreateDatabaseTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>::~merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>(void)
0x180012aec  mov     rcx, rdi; pv
0x180012aef  call    cs:__imp_CoTaskMemFree
0x180012af5  lea     rcx, [rbx+8]
0x180012af9  lea     rdx, [rsp+38h+var_18]
0x180012afe  call    ?start@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ; tip2::details::shared_data<0,0,0>::start(void)
0x180012b03  lea     rax, ??_7?$test_watcher@V?$merged_data@U_tip_UQIWnfCallbackExecutionTipTest@@U1@@details@tip2@@@tip2@@6B@; const tip2::test_watcher<tip2::details::merged_data<_tip_UQIWnfCallbackExecutionTipTest,_tip_UQIWnfCallbackExecutionTipTest>>::`vftable'
0x180012b0a  mov     [rsi], rax
0x180012b0d  lea     rdi, [rsi+8]
0x180012b11  mov     qword ptr [rdi], 0
0x180012b18  mov     [rdi+8], rsi
0x180012b1c  mov     qword ptr [rdi+10h], 0
0x180012b24  mov     dword ptr [rdi+18h], 0
0x180012b2b  mov     qword ptr [rdi+20h], 0
0x180012b33  mov     byte ptr [rdi+28h], 0
0x180012b37  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180012b3f  jz      short loc_180012B63
0x180012b41  mov     dl, 1
0x180012b43  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x180012b48  mov     [rdi], rax
0x180012b4b  test    rax, rax
0x180012b4e  jz      short loc_180012B63
0x180012b50  mov     rcx, [rax]
0x180012b53  mov     [rdi+10h], rcx
0x180012b57  mov     [rax], rdi
0x180012b5a  call    cs:__imp_GetCurrentThreadId
0x180012b60  mov     [rdi+18h], eax
0x180012b63  mov     [rsi+38h], rbx
0x180012b67  test    rbx, rbx
0x180012b6a  jz      short loc_180012B94
0x180012b6c  lock inc dword ptr [rbx+110h]
0x180012b73  or      eax, 0FFFFFFFFh
0x180012b76  lock xadd [rbx+110h], eax
0x180012b7e  cmp     eax, 1
0x180012b81  jnz     short loc_180012B94
0x180012b83  mov     rcx, rbx
0x180012b86  call    ??1?$merged_data@U_tip_UQIGetOrCreateDatabaseTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>::~merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>(void)
0x180012b8b  mov     rcx, rbx; pv
0x180012b8e  call    cs:__imp_CoTaskMemFree
0x180012b94  mov     rax, rsi
0x180012b97  mov     rbx, [rsp+38h+arg_10]
0x180012b9c  mov     rsi, [rsp+38h+arg_18]
0x180012ba1  add     rsp, 30h
0x180012ba5  pop     rdi
0x180012ba6  retn
```
