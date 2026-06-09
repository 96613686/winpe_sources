# ??$start_and_watch_errors@V?$tip_test@V?$merged_data@U_tip_UQIServiceInitializationTipTest@@U1@@details@tip2@@@tip2@@@tip2@@YA?A_PXZ

- ea: `0x18001ac5c`
- end: `0x18001ad5f`
- name: `??$start_and_watch_errors@V?$tip_test@V?$merged_data@U_tip_UQIServiceInitializationTipTest@@U1@@details@tip2@@@tip2@@@tip2@@YA?A_PXZ`
- size: `259`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001b234`

## callees

- `0x180008320`
- `0x180013c48`
- `0x180018e64`
- `0x18001ac5c`
- `0x18001ae20`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001ad12`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001ad12`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001aca7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ad46`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001aca7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ad46`

## pseudocode

```c
__int64 __fastcall tip2::start_and_watch_errors<tip2::tip_test<tip2::details::merged_data<_tip_UQIServiceInitializationTipTest,_tip_UQIServiceInitializationTipTest>>>(
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

  v2 = (volatile signed __int32 **)tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_UQIServiceInitializationTipTest,_tip_UQIServiceInitializationTipTest>,>(&pv);
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
0x18001ac5c  mov     [rsp+arg_10], rbx
0x18001ac61  mov     [rsp+arg_18], rsi
0x18001ac66  push    rdi
0x18001ac67  sub     rsp, 30h
0x18001ac6b  mov     rsi, rcx
0x18001ac6e  lea     rcx, [rsp+38h+pv]
0x18001ac73  call    ??$tip_make_shared_nothrow@V?$merged_data@U_tip_UQIServiceInitializationTipTest@@U1@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_UQIServiceInitializationTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_UQIServiceInitializationTipTest,_tip_UQIServiceInitializationTipTest>,>(void)
0x18001ac78  mov     rbx, [rax]
0x18001ac7b  mov     qword ptr [rax], 0
0x18001ac82  mov     rdi, [rsp+38h+pv]
0x18001ac87  test    rdi, rdi
0x18001ac8a  jz      short loc_18001ACAD
0x18001ac8c  or      eax, 0FFFFFFFFh
0x18001ac8f  lock xadd [rdi+110h], eax
0x18001ac97  cmp     eax, 1
0x18001ac9a  jnz     short loc_18001ACAD
0x18001ac9c  mov     rcx, rdi
0x18001ac9f  call    ??1?$merged_data@U_tip_UQIGetOrCreateDatabaseTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>::~merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>(void)
0x18001aca4  mov     rcx, rdi; pv
0x18001aca7  call    cs:__imp_CoTaskMemFree
0x18001acad  lea     rcx, [rbx+8]
0x18001acb1  lea     rdx, [rsp+38h+var_18]
0x18001acb6  call    ?start@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ; tip2::details::shared_data<0,0,0>::start(void)
0x18001acbb  lea     rax, ??_7?$test_watcher@V?$merged_data@U_tip_UQIWnfCallbackExecutionTipTest@@U1@@details@tip2@@@tip2@@6B@; const tip2::test_watcher<tip2::details::merged_data<_tip_UQIWnfCallbackExecutionTipTest,_tip_UQIWnfCallbackExecutionTipTest>>::`vftable'
0x18001acc2  mov     [rsi], rax
0x18001acc5  lea     rdi, [rsi+8]
0x18001acc9  mov     qword ptr [rdi], 0
0x18001acd0  mov     [rdi+8], rsi
0x18001acd4  mov     qword ptr [rdi+10h], 0
0x18001acdc  mov     dword ptr [rdi+18h], 0
0x18001ace3  mov     qword ptr [rdi+20h], 0
0x18001aceb  mov     byte ptr [rdi+28h], 0
0x18001acef  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18001acf7  jz      short loc_18001AD1B
0x18001acf9  mov     dl, 1
0x18001acfb  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x18001ad00  mov     [rdi], rax
0x18001ad03  test    rax, rax
0x18001ad06  jz      short loc_18001AD1B
0x18001ad08  mov     rcx, [rax]
0x18001ad0b  mov     [rdi+10h], rcx
0x18001ad0f  mov     [rax], rdi
0x18001ad12  call    cs:__imp_GetCurrentThreadId
0x18001ad18  mov     [rdi+18h], eax
0x18001ad1b  mov     [rsi+38h], rbx
0x18001ad1f  test    rbx, rbx
0x18001ad22  jz      short loc_18001AD4C
0x18001ad24  lock inc dword ptr [rbx+110h]
0x18001ad2b  or      eax, 0FFFFFFFFh
0x18001ad2e  lock xadd [rbx+110h], eax
0x18001ad36  cmp     eax, 1
0x18001ad39  jnz     short loc_18001AD4C
0x18001ad3b  mov     rcx, rbx
0x18001ad3e  call    ??1?$merged_data@U_tip_UQIGetOrCreateDatabaseTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>::~merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>(void)
0x18001ad43  mov     rcx, rbx; pv
0x18001ad46  call    cs:__imp_CoTaskMemFree
0x18001ad4c  mov     rax, rsi
0x18001ad4f  mov     rbx, [rsp+38h+arg_10]
0x18001ad54  mov     rsi, [rsp+38h+arg_18]
0x18001ad59  add     rsp, 30h
0x18001ad5d  pop     rdi
0x18001ad5e  retn
```
