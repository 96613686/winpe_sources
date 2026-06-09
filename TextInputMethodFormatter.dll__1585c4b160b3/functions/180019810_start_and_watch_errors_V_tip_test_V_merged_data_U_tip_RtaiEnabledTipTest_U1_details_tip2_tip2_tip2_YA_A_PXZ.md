# ??$start_and_watch_errors@V?$tip_test@V?$merged_data@U_tip_RtaiEnabledTipTest@@U1@@details@tip2@@@tip2@@@tip2@@YA?A_PXZ

- ea: `0x180019810`
- end: `0x180019913`
- name: `??$start_and_watch_errors@V?$tip_test@V?$merged_data@U_tip_RtaiEnabledTipTest@@U1@@details@tip2@@@tip2@@@tip2@@YA?A_PXZ`
- size: `259`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180025460`

## callees

- `0x1800058fc`
- `0x180019810`
- `0x18001991c`
- `0x18001a0ac`
- `0x1800280f4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001985b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800198fa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001985b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800198fa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800198c6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800198c6`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall tip2::start_and_watch_errors<tip2::tip_test<tip2::details::merged_data<_tip_RtaiEnabledTipTest,_tip_RtaiEnabledTipTest>>>(
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

  v2 = (volatile signed __int32 **)tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_RtaiEnabledTipTest,_tip_RtaiEnabledTipTest>,>(&pv);
  v3 = *v2;
  *v2 = 0;
  v4 = pv;
  if ( pv && _InterlockedExchangeAdd((volatile signed __int32 *)pv + 68, 0xFFFFFFFF) == 1 )
  {
    tip2::details::merged_data<_tip_RtaiEnabledTipTest,_tip_RtaiEnabledTipTest>::~merged_data<_tip_RtaiEnabledTipTest,_tip_RtaiEnabledTipTest>(v4);
    CoTaskMemFree(v4);
  }
  tip2::details::shared_data<0,0,0>::start(v3 + 2, v10);
  *(_QWORD *)a1 = &tip2::test_watcher<tip2::details::merged_data<_tip_RtaiEnabledTipTest,_tip_RtaiEnabledTipTest>>::`vftable';
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
      tip2::details::merged_data<_tip_RtaiEnabledTipTest,_tip_RtaiEnabledTipTest>::~merged_data<_tip_RtaiEnabledTipTest,_tip_RtaiEnabledTipTest>(v3);
      CoTaskMemFree((LPVOID)v3);
    }
  }
  return a1;
}

```

## disassembly

```asm
0x180019810  mov     [rsp+arg_10], rbx
0x180019815  mov     [rsp+arg_18], rsi
0x18001981a  push    rdi
0x18001981b  sub     rsp, 30h
0x18001981f  mov     rsi, rcx
0x180019822  lea     rcx, [rsp+38h+pv]
0x180019827  call    ??$tip_make_shared_nothrow@V?$merged_data@U_tip_RtaiEnabledTipTest@@U1@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_RtaiEnabledTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_RtaiEnabledTipTest,_tip_RtaiEnabledTipTest>,>(void)
0x18001982c  mov     rbx, [rax]
0x18001982f  mov     qword ptr [rax], 0
0x180019836  mov     rdi, [rsp+38h+pv]
0x18001983b  test    rdi, rdi
0x18001983e  jz      short loc_180019861
0x180019840  or      eax, 0FFFFFFFFh
0x180019843  lock xadd [rdi+110h], eax
0x18001984b  cmp     eax, 1
0x18001984e  jnz     short loc_180019861
0x180019850  mov     rcx, rdi
0x180019853  call    ??1?$merged_data@U_tip_RtaiEnabledTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_RtaiEnabledTipTest,_tip_RtaiEnabledTipTest>::~merged_data<_tip_RtaiEnabledTipTest,_tip_RtaiEnabledTipTest>(void)
0x180019858  mov     rcx, rdi; pv
0x18001985b  call    cs:__imp_CoTaskMemFree
0x180019861  lea     rcx, [rbx+8]
0x180019865  lea     rdx, [rsp+38h+var_18]
0x18001986a  call    ?start@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ; tip2::details::shared_data<0,0,0>::start(void)
0x18001986f  lea     rax, ??_7?$test_watcher@V?$merged_data@U_tip_RtaiEnabledTipTest@@U1@@details@tip2@@@tip2@@6B@; const tip2::test_watcher<tip2::details::merged_data<_tip_RtaiEnabledTipTest,_tip_RtaiEnabledTipTest>>::`vftable'
0x180019876  mov     [rsi], rax
0x180019879  lea     rdi, [rsi+8]
0x18001987d  mov     qword ptr [rdi], 0
0x180019884  mov     [rdi+8], rsi
0x180019888  mov     qword ptr [rdi+10h], 0
0x180019890  mov     dword ptr [rdi+18h], 0
0x180019897  mov     qword ptr [rdi+20h], 0
0x18001989f  mov     byte ptr [rdi+28h], 0
0x1800198a3  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800198ab  jz      short loc_1800198CF
0x1800198ad  mov     dl, 1
0x1800198af  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x1800198b4  mov     [rdi], rax
0x1800198b7  test    rax, rax
0x1800198ba  jz      short loc_1800198CF
0x1800198bc  mov     rcx, [rax]
0x1800198bf  mov     [rdi+10h], rcx
0x1800198c3  mov     [rax], rdi
0x1800198c6  call    cs:__imp_GetCurrentThreadId
0x1800198cc  mov     [rdi+18h], eax
0x1800198cf  mov     [rsi+38h], rbx
0x1800198d3  test    rbx, rbx
0x1800198d6  jz      short loc_180019900
0x1800198d8  lock inc dword ptr [rbx+110h]
0x1800198df  or      eax, 0FFFFFFFFh
0x1800198e2  lock xadd [rbx+110h], eax
0x1800198ea  cmp     eax, 1
0x1800198ed  jnz     short loc_180019900
0x1800198ef  mov     rcx, rbx
0x1800198f2  call    ??1?$merged_data@U_tip_RtaiEnabledTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_RtaiEnabledTipTest,_tip_RtaiEnabledTipTest>::~merged_data<_tip_RtaiEnabledTipTest,_tip_RtaiEnabledTipTest>(void)
0x1800198f7  mov     rcx, rbx; pv
0x1800198fa  call    cs:__imp_CoTaskMemFree
0x180019900  mov     rax, rsi
0x180019903  mov     rbx, [rsp+38h+arg_10]
0x180019908  mov     rsi, [rsp+38h+arg_18]
0x18001990d  add     rsp, 30h
0x180019911  pop     rdi
0x180019912  retn
```
