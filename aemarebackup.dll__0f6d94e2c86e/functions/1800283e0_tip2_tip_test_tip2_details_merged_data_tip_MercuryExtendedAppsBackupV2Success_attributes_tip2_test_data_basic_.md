# tip2::tip_test<tip2::details::merged_data<_tip_MercuryExtendedAppsBackupV2Success_attributes,tip2::test_data_basic>>::ensure_data(void)

- ea: `0x1800283e0`
- end: `0x18002846c`
- name: `?ensure_data@?$tip_test@V?$merged_data@U_tip_MercuryExtendedAppsBackupV2Success_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_MercuryExtendedAppsBackupV2Success_attributes@@Vtest_data_basic@tip2@@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ`
- size: `140`
- prototype: `__int64 *__fastcall(__int64 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180026a18`
- `0x180031dd0`

## callees

- `0x180011ea8`
- `0x18001359c`
- `0x1800283e0`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18002842d`
- `ole32!CoTaskMemFree` at `0x180028458`
- `ole32!CoTaskMemFree` at `0x18002842d`
- `ole32!CoTaskMemFree` at `0x180028458`

## pseudocode

```c
__int64 *__fastcall tip2::tip_test<tip2::details::merged_data<_tip_MercuryExtendedAppsBackupV2Success_attributes,tip2::test_data_basic>>::ensure_data(
        __int64 *a1)
{
  __int64 *v2; // rax
  __int64 v3; // rdx
  __int64 v4; // rbx
  struct _RTL_CRITICAL_SECTION *v5; // rbx
  LPVOID pv; // [rsp+38h] [rbp+10h] BYREF

  if ( !*a1 )
  {
    v2 = tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_MercuryExtendedAppsBackupV2Success_attributes,tip2::test_data_basic>,>(&pv);
    v3 = *v2;
    *v2 = 0;
    v4 = *a1;
    *a1 = v3;
    if ( v4 && _InterlockedExchangeAdd((volatile signed __int32 *)(v4 + 336), 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<_tip_MercuryExtendedAppsBackupV2Success_attributes,tip2::test_data_basic>::~merged_data<_tip_MercuryExtendedAppsBackupV2Success_attributes,tip2::test_data_basic>((struct _RTL_CRITICAL_SECTION *)v4);
      CoTaskMemFree((LPVOID)v4);
    }
    v5 = (struct _RTL_CRITICAL_SECTION *)pv;
    if ( pv && _InterlockedExchangeAdd((volatile signed __int32 *)pv + 84, 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<_tip_MercuryExtendedAppsBackupV2Success_attributes,tip2::test_data_basic>::~merged_data<_tip_MercuryExtendedAppsBackupV2Success_attributes,tip2::test_data_basic>(v5);
      CoTaskMemFree(v5);
    }
  }
  return a1;
}

```

## disassembly

```asm
0x1800283e0  mov     [rsp+arg_10], rbx
0x1800283e5  push    rdi
0x1800283e6  sub     rsp, 20h
0x1800283ea  cmp     qword ptr [rcx], 0
0x1800283ee  mov     rdi, rcx
0x1800283f1  jnz     short loc_18002845E
0x1800283f3  lea     rcx, [rsp+28h+pv]
0x1800283f8  call    ??$tip_make_shared_nothrow@V?$merged_data@U_tip_MercuryExtendedAppsBackupV2Success_attributes@@Vtest_data_basic@tip2@@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_MercuryExtendedAppsBackupV2Success_attributes@@Vtest_data_basic@tip2@@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_MercuryExtendedAppsBackupV2Success_attributes,tip2::test_data_basic>,>(void)
0x1800283fd  mov     rdx, [rax]
0x180028400  mov     qword ptr [rax], 0
0x180028407  mov     rbx, [rdi]
0x18002840a  mov     [rdi], rdx
0x18002840d  test    rbx, rbx
0x180028410  jz      short loc_180028433
0x180028412  or      eax, 0FFFFFFFFh
0x180028415  lock xadd [rbx+150h], eax
0x18002841d  cmp     eax, 1
0x180028420  jnz     short loc_180028433
0x180028422  mov     rcx, rbx
0x180028425  call    ??1?$merged_data@U_tip_MercuryExtendedAppsBackupV2Success_attributes@@Vtest_data_basic@tip2@@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_MercuryExtendedAppsBackupV2Success_attributes,tip2::test_data_basic>::~merged_data<_tip_MercuryExtendedAppsBackupV2Success_attributes,tip2::test_data_basic>(void)
0x18002842a  mov     rcx, rbx; pv
0x18002842d  call    cs:__imp_CoTaskMemFree
0x180028433  mov     rbx, [rsp+28h+pv]
0x180028438  test    rbx, rbx
0x18002843b  jz      short loc_18002845E
0x18002843d  or      eax, 0FFFFFFFFh
0x180028440  lock xadd [rbx+150h], eax
0x180028448  cmp     eax, 1
0x18002844b  jnz     short loc_18002845E
0x18002844d  mov     rcx, rbx
0x180028450  call    ??1?$merged_data@U_tip_MercuryExtendedAppsBackupV2Success_attributes@@Vtest_data_basic@tip2@@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_MercuryExtendedAppsBackupV2Success_attributes,tip2::test_data_basic>::~merged_data<_tip_MercuryExtendedAppsBackupV2Success_attributes,tip2::test_data_basic>(void)
0x180028455  mov     rcx, rbx; pv
0x180028458  call    cs:__imp_CoTaskMemFree
0x18002845e  mov     rbx, [rsp+28h+arg_10]
0x180028463  mov     rax, rdi
0x180028466  add     rsp, 20h
0x18002846a  pop     rdi
0x18002846b  retn
```
