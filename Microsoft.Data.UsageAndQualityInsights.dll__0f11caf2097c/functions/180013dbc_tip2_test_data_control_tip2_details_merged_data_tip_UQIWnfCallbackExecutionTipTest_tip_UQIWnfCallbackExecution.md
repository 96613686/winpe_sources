# tip2::test_data_control<tip2::details::merged_data<_tip_UQIWnfCallbackExecutionTipTest,_tip_UQIWnfCallbackExecutionTipTest>>::~test_data_control<tip2::details::merged_data<_tip_UQIWnfCallbackExecutionTipTest,_tip_UQIWnfCallbackExecutionTipTest>>(void)

- ea: `0x180013dbc`
- end: `0x180013e3e`
- name: `??1?$test_data_control@V?$merged_data@U_tip_UQIWnfCallbackExecutionTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ`
- size: `130`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180015930`
- `0x18001d95c`

## callees

- `0x180013bbc`
- `0x180013dbc`
- `0x180016ff4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013e04`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013e2d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013e04`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013e2d`

## pseudocode

```c
void __fastcall tip2::test_data_control<tip2::details::merged_data<_tip_UQIWnfCallbackExecutionTipTest,_tip_UQIWnfCallbackExecutionTipTest>>::~test_data_control<tip2::details::merged_data<_tip_UQIWnfCallbackExecutionTipTest,_tip_UQIWnfCallbackExecutionTipTest>>(
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
        tip2::details::merged_data<_tip_UQIWnfCallbackExecutionTipTest,_tip_UQIWnfCallbackExecutionTipTest>::~merged_data<_tip_UQIWnfCallbackExecutionTipTest,_tip_UQIWnfCallbackExecutionTipTest>((struct _RTL_CRITICAL_SECTION *)v3);
        CoTaskMemFree((LPVOID)v3);
      }
    }
  }
  v4 = *a1;
  if ( *a1 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v4 + 280), 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<_tip_UQIWnfCallbackExecutionTipTest,_tip_UQIWnfCallbackExecutionTipTest>::~merged_data<_tip_UQIWnfCallbackExecutionTipTest,_tip_UQIWnfCallbackExecutionTipTest>((struct _RTL_CRITICAL_SECTION *)v4);
      CoTaskMemFree((LPVOID)v4);
    }
  }
}

```

## disassembly

```asm
0x180013dbc  mov     [rsp+arg_8], rbx
0x180013dc1  push    rdi
0x180013dc2  sub     rsp, 20h
0x180013dc6  mov     rdi, rcx
0x180013dc9  mov     rcx, [rcx]
0x180013dcc  test    rcx, rcx
0x180013dcf  jz      short loc_180013E0A
0x180013dd1  add     rcx, 8
0x180013dd5  call    ?end_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ; tip2::details::shared_data<0,0,0>::end_update(void)
0x180013dda  mov     rbx, [rdi]
0x180013ddd  mov     qword ptr [rdi], 0
0x180013de4  test    rbx, rbx
0x180013de7  jz      short loc_180013E0A
0x180013de9  or      eax, 0FFFFFFFFh
0x180013dec  lock xadd [rbx+118h], eax
0x180013df4  cmp     eax, 1
0x180013df7  jnz     short loc_180013E0A
0x180013df9  mov     rcx, rbx
0x180013dfc  call    ??1?$merged_data@U_tip_UQIWnfCallbackExecutionTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_UQIWnfCallbackExecutionTipTest,_tip_UQIWnfCallbackExecutionTipTest>::~merged_data<_tip_UQIWnfCallbackExecutionTipTest,_tip_UQIWnfCallbackExecutionTipTest>(void)
0x180013e01  mov     rcx, rbx; pv
0x180013e04  call    cs:__imp_CoTaskMemFree
0x180013e0a  mov     rbx, [rdi]
0x180013e0d  test    rbx, rbx
0x180013e10  jz      short loc_180013E33
0x180013e12  or      eax, 0FFFFFFFFh
0x180013e15  lock xadd [rbx+118h], eax
0x180013e1d  cmp     eax, 1
0x180013e20  jnz     short loc_180013E33
0x180013e22  mov     rcx, rbx
0x180013e25  call    ??1?$merged_data@U_tip_UQIWnfCallbackExecutionTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_UQIWnfCallbackExecutionTipTest,_tip_UQIWnfCallbackExecutionTipTest>::~merged_data<_tip_UQIWnfCallbackExecutionTipTest,_tip_UQIWnfCallbackExecutionTipTest>(void)
0x180013e2a  mov     rcx, rbx; pv
0x180013e2d  call    cs:__imp_CoTaskMemFree
0x180013e33  mov     rbx, [rsp+28h+arg_8]
0x180013e38  add     rsp, 20h
0x180013e3c  pop     rdi
0x180013e3d  retn
```
