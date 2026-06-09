# tip2::test_data_control<tip2::details::merged_data<_tip_A9PolicyTaskTipTest,_tip_A9PolicyTaskTipTest>>::~test_data_control<tip2::details::merged_data<_tip_A9PolicyTaskTipTest,_tip_A9PolicyTaskTipTest>>(void)

- ea: `0x180027e78`
- end: `0x180027efa`
- name: `??1?$test_data_control@V?$merged_data@U_tip_A9PolicyTaskTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ`
- size: `130`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18002a69c`
- `0x18002d050`

## callees

- `0x180021ecc`
- `0x180027bf4`
- `0x180027e78`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180027ec0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180027ee9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180027ec0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180027ee9`

## pseudocode

```c
void __fastcall tip2::test_data_control<tip2::details::merged_data<_tip_A9PolicyTaskTipTest,_tip_A9PolicyTaskTipTest>>::~test_data_control<tip2::details::merged_data<_tip_A9PolicyTaskTipTest,_tip_A9PolicyTaskTipTest>>(
        __int64 *a1)
{
  __int64 v2; // rcx
  __int64 v3; // rbx
  __int64 v4; // rbx

  v2 = *a1;
  if ( v2 )
  {
    tip2::details::shared_data<0,0,0>::end_update(v2 + 8);
    v3 = *a1;
    *a1 = 0;
    if ( v3 )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v3 + 280), 0xFFFFFFFF) == 1 )
      {
        tip2::details::merged_data<_tip_A9PolicyTaskTipTest,_tip_A9PolicyTaskTipTest>::~merged_data<_tip_A9PolicyTaskTipTest,_tip_A9PolicyTaskTipTest>((struct _RTL_CRITICAL_SECTION *)v3);
        CoTaskMemFree((LPVOID)v3);
      }
    }
  }
  v4 = *a1;
  if ( *a1 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v4 + 280), 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<_tip_A9PolicyTaskTipTest,_tip_A9PolicyTaskTipTest>::~merged_data<_tip_A9PolicyTaskTipTest,_tip_A9PolicyTaskTipTest>((struct _RTL_CRITICAL_SECTION *)v4);
      CoTaskMemFree((LPVOID)v4);
    }
  }
}

```

## disassembly

```asm
0x180027e78  mov     [rsp+arg_8], rbx
0x180027e7d  push    rdi
0x180027e7e  sub     rsp, 20h
0x180027e82  mov     rdi, rcx
0x180027e85  mov     rcx, [rcx]
0x180027e88  test    rcx, rcx
0x180027e8b  jz      short loc_180027EC6
0x180027e8d  add     rcx, 8
0x180027e91  call    ?end_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ; tip2::details::shared_data<0,0,0>::end_update(void)
0x180027e96  mov     rbx, [rdi]
0x180027e99  mov     qword ptr [rdi], 0
0x180027ea0  test    rbx, rbx
0x180027ea3  jz      short loc_180027EC6
0x180027ea5  or      eax, 0FFFFFFFFh
0x180027ea8  lock xadd [rbx+118h], eax
0x180027eb0  cmp     eax, 1
0x180027eb3  jnz     short loc_180027EC6
0x180027eb5  mov     rcx, rbx
0x180027eb8  call    ??1?$merged_data@U_tip_A9PolicyTaskTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_A9PolicyTaskTipTest,_tip_A9PolicyTaskTipTest>::~merged_data<_tip_A9PolicyTaskTipTest,_tip_A9PolicyTaskTipTest>(void)
0x180027ebd  mov     rcx, rbx; pv
0x180027ec0  call    cs:__imp_CoTaskMemFree
0x180027ec6  mov     rbx, [rdi]
0x180027ec9  test    rbx, rbx
0x180027ecc  jz      short loc_180027EEF
0x180027ece  or      eax, 0FFFFFFFFh
0x180027ed1  lock xadd [rbx+118h], eax
0x180027ed9  cmp     eax, 1
0x180027edc  jnz     short loc_180027EEF
0x180027ede  mov     rcx, rbx
0x180027ee1  call    ??1?$merged_data@U_tip_A9PolicyTaskTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_A9PolicyTaskTipTest,_tip_A9PolicyTaskTipTest>::~merged_data<_tip_A9PolicyTaskTipTest,_tip_A9PolicyTaskTipTest>(void)
0x180027ee6  mov     rcx, rbx; pv
0x180027ee9  call    cs:__imp_CoTaskMemFree
0x180027eef  mov     rbx, [rsp+28h+arg_8]
0x180027ef4  add     rsp, 20h
0x180027ef8  pop     rdi
0x180027ef9  retn
```
