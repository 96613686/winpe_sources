# tip2::open<tip2::tip_test<tip2::details::merged_data<_tip_MercuryExtendedAppsBackupV2Success_attributes,tip2::test_data_basic>>>(void)

- ea: `0x180031910`
- end: `0x1800319aa`
- name: `??$open@V?$tip_test@V?$merged_data@U_tip_MercuryExtendedAppsBackupV2Success_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@@tip2@@YA?AV?$tip_test@V?$merged_data@U_tip_MercuryExtendedAppsBackupV2Success_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@0@XZ`
- size: `154`
- prototype: `volatile signed __int32 **__fastcall(volatile signed __int32 **)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180031dd0`

## callees

- `0x18001359c`
- `0x180031910`
- `0x1800319b0`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18003196b`
- `ole32!CoTaskMemFree` at `0x180031996`
- `ole32!CoTaskMemFree` at `0x18003196b`
- `ole32!CoTaskMemFree` at `0x180031996`

## pseudocode

```c
volatile signed __int32 **__fastcall tip2::open<tip2::tip_test<tip2::details::merged_data<_tip_MercuryExtendedAppsBackupV2Success_attributes,tip2::test_data_basic>>>(
        volatile signed __int32 **a1)
{
  volatile signed __int32 **v2; // rax
  volatile signed __int32 *v3; // rdx
  volatile signed __int32 *v4; // rbx
  void *v5; // rbx
  __int64 v7; // [rsp+30h] [rbp+8h] BYREF
  LPVOID pv; // [rsp+38h] [rbp+10h] BYREF

  *a1 = 0;
  v7 = 0;
  v2 = (volatile signed __int32 **)tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_MercuryExtendedAppsBackupV2Success_attributes,tip2::test_data_basic>,_GUID * &>(
                                     &pv,
                                     &v7);
  v3 = *v2;
  *v2 = 0;
  v4 = *a1;
  *a1 = v3;
  if ( v4 && _InterlockedExchangeAdd(v4 + 84, 0xFFFFFFFF) == 1 )
  {
    tip2::details::merged_data<_tip_MercuryExtendedAppsBackupV2Success_attributes,tip2::test_data_basic>::~merged_data<_tip_MercuryExtendedAppsBackupV2Success_attributes,tip2::test_data_basic>(v4);
    CoTaskMemFree((LPVOID)v4);
  }
  v5 = pv;
  if ( pv && _InterlockedExchangeAdd((volatile signed __int32 *)pv + 84, 0xFFFFFFFF) == 1 )
  {
    tip2::details::merged_data<_tip_MercuryExtendedAppsBackupV2Success_attributes,tip2::test_data_basic>::~merged_data<_tip_MercuryExtendedAppsBackupV2Success_attributes,tip2::test_data_basic>(v5);
    CoTaskMemFree(v5);
  }
  return a1;
}

```

## disassembly

```asm
0x180031910  mov     rax, rsp
0x180031913  mov     [rax+18h], rbx
0x180031917  push    rdi
0x180031918  sub     rsp, 20h
0x18003191c  mov     rdi, rcx
0x18003191f  mov     qword ptr [rcx], 0
0x180031926  lea     rcx, [rax+10h]
0x18003192a  mov     qword ptr [rax+8], 0
0x180031932  lea     rdx, [rax+8]
0x180031936  call    ??$tip_make_shared_nothrow@V?$merged_data@U_tip_MercuryExtendedAppsBackupV2Success_attributes@@Vtest_data_basic@tip2@@@details@tip2@@AEAPEAU_GUID@@@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_MercuryExtendedAppsBackupV2Success_attributes@@Vtest_data_basic@tip2@@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@AEAPEAU_GUID@@@Z; tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_MercuryExtendedAppsBackupV2Success_attributes,tip2::test_data_basic>,_GUID * &>(_GUID * &)
0x18003193b  mov     rdx, [rax]
0x18003193e  mov     qword ptr [rax], 0
0x180031945  mov     rbx, [rdi]
0x180031948  mov     [rdi], rdx
0x18003194b  test    rbx, rbx
0x18003194e  jz      short loc_180031971
0x180031950  or      eax, 0FFFFFFFFh
0x180031953  lock xadd [rbx+150h], eax
0x18003195b  cmp     eax, 1
0x18003195e  jnz     short loc_180031971
0x180031960  mov     rcx, rbx
0x180031963  call    ??1?$merged_data@U_tip_MercuryExtendedAppsBackupV2Success_attributes@@Vtest_data_basic@tip2@@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_MercuryExtendedAppsBackupV2Success_attributes,tip2::test_data_basic>::~merged_data<_tip_MercuryExtendedAppsBackupV2Success_attributes,tip2::test_data_basic>(void)
0x180031968  mov     rcx, rbx; pv
0x18003196b  call    cs:__imp_CoTaskMemFree
0x180031971  mov     rbx, [rsp+28h+pv]
0x180031976  test    rbx, rbx
0x180031979  jz      short loc_18003199C
0x18003197b  or      eax, 0FFFFFFFFh
0x18003197e  lock xadd [rbx+150h], eax
0x180031986  cmp     eax, 1
0x180031989  jnz     short loc_18003199C
0x18003198b  mov     rcx, rbx
0x18003198e  call    ??1?$merged_data@U_tip_MercuryExtendedAppsBackupV2Success_attributes@@Vtest_data_basic@tip2@@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_MercuryExtendedAppsBackupV2Success_attributes,tip2::test_data_basic>::~merged_data<_tip_MercuryExtendedAppsBackupV2Success_attributes,tip2::test_data_basic>(void)
0x180031993  mov     rcx, rbx; pv
0x180031996  call    cs:__imp_CoTaskMemFree
0x18003199c  mov     rbx, [rsp+28h+arg_10]
0x1800319a1  mov     rax, rdi
0x1800319a4  add     rsp, 20h
0x1800319a8  pop     rdi
0x1800319a9  retn
```
