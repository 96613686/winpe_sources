# tip2::test_data_control<tip2::details::merged_data<_tip_UQISaveFactsToFactStoreTipTest,_tip_UQISaveFactsToFactStoreTipTest>>::~test_data_control<tip2::details::merged_data<_tip_UQISaveFactsToFactStoreTipTest,_tip_UQISaveFactsToFactStoreTipTest>>(void)

- ea: `0x180013e44`
- end: `0x180013ec6`
- name: `??1?$test_data_control@V?$merged_data@U_tip_UQISaveFactsToFactStoreTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ`
- size: `130`
- prototype: `void __fastcall(__int64 *)`
- caller_count: `5`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180014c40`
- `0x18001c64c`
- `0x18004c184`
- `0x1800e6bb8`
- `0x1800e75bc`

## callees

- `0x180013c48`
- `0x180013e44`
- `0x180016ff4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013e8c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013eb5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013e8c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013eb5`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall tip2::test_data_control<tip2::details::merged_data<_tip_UQISaveFactsToFactStoreTipTest,_tip_UQISaveFactsToFactStoreTipTest>>::~test_data_control<tip2::details::merged_data<_tip_UQISaveFactsToFactStoreTipTest,_tip_UQISaveFactsToFactStoreTipTest>>(
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
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v3 + 272), 0xFFFFFFFF) == 1 )
      {
        tip2::details::merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>::~merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>((struct _RTL_CRITICAL_SECTION *)v3);
        CoTaskMemFree((LPVOID)v3);
      }
    }
  }
  v4 = *a1;
  if ( *a1 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v4 + 272), 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>::~merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>((struct _RTL_CRITICAL_SECTION *)v4);
      CoTaskMemFree((LPVOID)v4);
    }
  }
}

```

## disassembly

```asm
0x180013e44  mov     [rsp+arg_8], rbx
0x180013e49  push    rdi
0x180013e4a  sub     rsp, 20h
0x180013e4e  mov     rdi, rcx
0x180013e51  mov     rcx, [rcx]
0x180013e54  test    rcx, rcx
0x180013e57  jz      short loc_180013E92
0x180013e59  add     rcx, 8
0x180013e5d  call    ?end_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ; tip2::details::shared_data<0,0,0>::end_update(void)
0x180013e62  mov     rbx, [rdi]
0x180013e65  mov     qword ptr [rdi], 0
0x180013e6c  test    rbx, rbx
0x180013e6f  jz      short loc_180013E92
0x180013e71  or      eax, 0FFFFFFFFh
0x180013e74  lock xadd [rbx+110h], eax
0x180013e7c  cmp     eax, 1
0x180013e7f  jnz     short loc_180013E92
0x180013e81  mov     rcx, rbx
0x180013e84  call    ??1?$merged_data@U_tip_UQIGetOrCreateDatabaseTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>::~merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>(void)
0x180013e89  mov     rcx, rbx; pv
0x180013e8c  call    cs:__imp_CoTaskMemFree
0x180013e92  mov     rbx, [rdi]
0x180013e95  test    rbx, rbx
0x180013e98  jz      short loc_180013EBB
0x180013e9a  or      eax, 0FFFFFFFFh
0x180013e9d  lock xadd [rbx+110h], eax
0x180013ea5  cmp     eax, 1
0x180013ea8  jnz     short loc_180013EBB
0x180013eaa  mov     rcx, rbx
0x180013ead  call    ??1?$merged_data@U_tip_UQIGetOrCreateDatabaseTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>::~merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>(void)
0x180013eb2  mov     rcx, rbx; pv
0x180013eb5  call    cs:__imp_CoTaskMemFree
0x180013ebb  mov     rbx, [rsp+28h+arg_8]
0x180013ec0  add     rsp, 20h
0x180013ec4  pop     rdi
0x180013ec5  retn
```
