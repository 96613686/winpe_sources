# tip2::tip_test<tip2::details::merged_data<_tip_MercuryExtendedAppsBackupV2Success_attributes,tip2::test_data_basic>>::~tip_test<tip2::details::merged_data<_tip_MercuryExtendedAppsBackupV2Success_attributes,tip2::test_data_basic>>(void)

- ea: `0x18001366c`
- end: `0x1800136a1`
- name: `??1?$tip_test@V?$merged_data@U_tip_MercuryExtendedAppsBackupV2Success_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@QEAA@XZ`
- size: `53`
- prototype: `void __fastcall(__int64 *)`
- caller_count: `5`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x1800e7140`
- `0x1800e7188`
- `0x1800e75ae`
- `0x1800e75c0`
- `0x1800e80c9`

## callees

- `0x18001359c`
- `0x18001366c`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180013695`
- `ole32!CoTaskMemFree` at `0x180013695`

## pseudocode

```c
void __fastcall tip2::tip_test<tip2::details::merged_data<_tip_MercuryExtendedAppsBackupV2Success_attributes,tip2::test_data_basic>>::~tip_test<tip2::details::merged_data<_tip_MercuryExtendedAppsBackupV2Success_attributes,tip2::test_data_basic>>(
        __int64 *a1)
{
  __int64 v1; // rbx

  v1 = *a1;
  if ( *a1 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v1 + 336), 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<_tip_MercuryExtendedAppsBackupV2Success_attributes,tip2::test_data_basic>::~merged_data<_tip_MercuryExtendedAppsBackupV2Success_attributes,tip2::test_data_basic>((struct _RTL_CRITICAL_SECTION *)v1);
      CoTaskMemFree((LPVOID)v1);
    }
  }
}

```

## disassembly

```asm
0x18001366c  push    rbx
0x18001366e  sub     rsp, 20h
0x180013672  mov     rbx, [rcx]
0x180013675  test    rbx, rbx
0x180013678  jz      short loc_18001369B
0x18001367a  or      eax, 0FFFFFFFFh
0x18001367d  lock xadd [rbx+150h], eax
0x180013685  cmp     eax, 1
0x180013688  jnz     short loc_18001369B
0x18001368a  mov     rcx, rbx
0x18001368d  call    ??1?$merged_data@U_tip_MercuryExtendedAppsBackupV2Success_attributes@@Vtest_data_basic@tip2@@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_MercuryExtendedAppsBackupV2Success_attributes,tip2::test_data_basic>::~merged_data<_tip_MercuryExtendedAppsBackupV2Success_attributes,tip2::test_data_basic>(void)
0x180013692  mov     rcx, rbx; pv
0x180013695  call    cs:__imp_CoTaskMemFree
0x18001369b  add     rsp, 20h
0x18001369f  pop     rbx
0x1800136a0  retn
```
