# tip2::test_data_control<tip2::details::merged_data<_tip_WaitForOOBEOrNDUPTipTest,_tip_WaitForOOBEOrNDUPTipTest>>::~test_data_control<tip2::details::merged_data<_tip_WaitForOOBEOrNDUPTipTest,_tip_WaitForOOBEOrNDUPTipTest>>(void)

- ea: `0x180013d90`
- end: `0x180013e12`
- name: `??1?$test_data_control@V?$merged_data@U_tip_WaitForOOBEOrNDUPTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ`
- size: `130`
- prototype: `void __fastcall(__int64 *)`
- caller_count: `6`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800146c0`
- `0x180014760`
- `0x18001bde0`
- `0x18001be80`
- `0x18001f604`
- `0x18001f998`

## callees

- `0x180013b6c`
- `0x180013d90`
- `0x180021ecc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013dd8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013e01`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013dd8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013e01`

## pseudocode

```c
void __fastcall tip2::test_data_control<tip2::details::merged_data<_tip_WaitForOOBEOrNDUPTipTest,_tip_WaitForOOBEOrNDUPTipTest>>::~test_data_control<tip2::details::merged_data<_tip_WaitForOOBEOrNDUPTipTest,_tip_WaitForOOBEOrNDUPTipTest>>(
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
        tip2::details::merged_data<_tip_WaitForOOBEOrNDUPTipTest,_tip_WaitForOOBEOrNDUPTipTest>::~merged_data<_tip_WaitForOOBEOrNDUPTipTest,_tip_WaitForOOBEOrNDUPTipTest>((struct _RTL_CRITICAL_SECTION *)v3);
        CoTaskMemFree((LPVOID)v3);
      }
    }
  }
  v4 = *a1;
  if ( *a1 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v4 + 280), 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<_tip_WaitForOOBEOrNDUPTipTest,_tip_WaitForOOBEOrNDUPTipTest>::~merged_data<_tip_WaitForOOBEOrNDUPTipTest,_tip_WaitForOOBEOrNDUPTipTest>((struct _RTL_CRITICAL_SECTION *)v4);
      CoTaskMemFree((LPVOID)v4);
    }
  }
}

```

## disassembly

```asm
0x180013d90  mov     [rsp+arg_8], rbx
0x180013d95  push    rdi
0x180013d96  sub     rsp, 20h
0x180013d9a  mov     rdi, rcx
0x180013d9d  mov     rcx, [rcx]
0x180013da0  test    rcx, rcx
0x180013da3  jz      short loc_180013DDE
0x180013da5  add     rcx, 8
0x180013da9  call    ?end_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ; tip2::details::shared_data<0,0,0>::end_update(void)
0x180013dae  mov     rbx, [rdi]
0x180013db1  mov     qword ptr [rdi], 0
0x180013db8  test    rbx, rbx
0x180013dbb  jz      short loc_180013DDE
0x180013dbd  or      eax, 0FFFFFFFFh
0x180013dc0  lock xadd [rbx+118h], eax
0x180013dc8  cmp     eax, 1
0x180013dcb  jnz     short loc_180013DDE
0x180013dcd  mov     rcx, rbx
0x180013dd0  call    ??1?$merged_data@U_tip_WaitForOOBEOrNDUPTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_WaitForOOBEOrNDUPTipTest,_tip_WaitForOOBEOrNDUPTipTest>::~merged_data<_tip_WaitForOOBEOrNDUPTipTest,_tip_WaitForOOBEOrNDUPTipTest>(void)
0x180013dd5  mov     rcx, rbx; pv
0x180013dd8  call    cs:__imp_CoTaskMemFree
0x180013dde  mov     rbx, [rdi]
0x180013de1  test    rbx, rbx
0x180013de4  jz      short loc_180013E07
0x180013de6  or      eax, 0FFFFFFFFh
0x180013de9  lock xadd [rbx+118h], eax
0x180013df1  cmp     eax, 1
0x180013df4  jnz     short loc_180013E07
0x180013df6  mov     rcx, rbx
0x180013df9  call    ??1?$merged_data@U_tip_WaitForOOBEOrNDUPTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_WaitForOOBEOrNDUPTipTest,_tip_WaitForOOBEOrNDUPTipTest>::~merged_data<_tip_WaitForOOBEOrNDUPTipTest,_tip_WaitForOOBEOrNDUPTipTest>(void)
0x180013dfe  mov     rcx, rbx; pv
0x180013e01  call    cs:__imp_CoTaskMemFree
0x180013e07  mov     rbx, [rsp+28h+arg_8]
0x180013e0c  add     rsp, 20h
0x180013e10  pop     rdi
0x180013e11  retn
```
