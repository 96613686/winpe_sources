# tip2::test_data_control<tip2::details::merged_data<AIFabricTipTest::_tip_ModelCacheManagerPackageCacheGenerationTest,AIFabricTipTest::_tip_ModelCacheManagerPackageCacheGenerationTest>>::~test_data_control<tip2::details::merged_data<AIFabricTipTest::_tip_ModelCacheManagerPackageCacheGenerationTest,AIFabricTipTest::_tip_ModelCacheManagerPackageCacheGenerationTest>>(void)

- ea: `0x180008480`
- end: `0x1800084c6`
- name: `??1?$test_data_control@V?$merged_data@U_tip_ModelCacheManagerPackageCacheGenerationTest@AIFabricTipTest@@U12@@details@tip2@@@tip2@@QEAA@XZ`
- size: `70`
- prototype: `__int64 __fastcall(LPVOID *)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x18001dfbc`

## callees

- `0x180008480`
- `0x180009e10`
- `0x18000a770`

## pseudocode

```c
__int64 __fastcall tip2::test_data_control<tip2::details::merged_data<AIFabricTipTest::_tip_ModelCacheManagerPackageCacheGenerationTest,AIFabricTipTest::_tip_ModelCacheManagerPackageCacheGenerationTest>>::~test_data_control<tip2::details::merged_data<AIFabricTipTest::_tip_ModelCacheManagerPackageCacheGenerationTest,AIFabricTipTest::_tip_ModelCacheManagerPackageCacheGenerationTest>>(
        LPVOID *a1)
{
  char *v2; // rcx
  __int64 result; // rax
  void *v4; // rcx

  v2 = (char *)*a1;
  if ( v2 )
  {
    result = tip2::details::shared_data<0,0,0>::end_update(v2 + 8);
    v4 = *a1;
    *a1 = 0;
    if ( v4 )
      result = tip2::details::merged_data<AIFabricTipTest::_tip_ModelCacheManagerPackageCacheGenerationTest,AIFabricTipTest::_tip_ModelCacheManagerPackageCacheGenerationTest>::Release(v4);
  }
  if ( *a1 )
    return tip2::details::merged_data<AIFabricTipTest::_tip_ModelCacheManagerPackageCacheGenerationTest,AIFabricTipTest::_tip_ModelCacheManagerPackageCacheGenerationTest>::Release(*a1);
  return result;
}

```

## disassembly

```asm
0x180008480  push    rbx
0x180008482  sub     rsp, 20h
0x180008486  mov     rbx, rcx
0x180008489  mov     rcx, [rcx]
0x18000848c  test    rcx, rcx
0x18000848f  jz      short loc_1800084AE
0x180008491  add     rcx, 8
0x180008495  call    ?end_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ; tip2::details::shared_data<0,0,0>::end_update(void)
0x18000849a  mov     rcx, [rbx]; pv
0x18000849d  mov     qword ptr [rbx], 0
0x1800084a4  test    rcx, rcx
0x1800084a7  jz      short loc_1800084AE
0x1800084a9  call    ?Release@?$merged_data@U_tip_ModelCacheManagerPackageCacheGenerationTest@AIFabricTipTest@@U12@@details@tip2@@AEAAKXZ; tip2::details::merged_data<AIFabricTipTest::_tip_ModelCacheManagerPackageCacheGenerationTest,AIFabricTipTest::_tip_ModelCacheManagerPackageCacheGenerationTest>::Release(void)
0x1800084ae  mov     rcx, [rbx]; pv
0x1800084b1  test    rcx, rcx
0x1800084b4  jz      short loc_1800084C0
0x1800084b6  add     rsp, 20h
0x1800084ba  pop     rbx
0x1800084bb  jmp     ?Release@?$merged_data@U_tip_ModelCacheManagerPackageCacheGenerationTest@AIFabricTipTest@@U12@@details@tip2@@AEAAKXZ; tip2::details::merged_data<AIFabricTipTest::_tip_ModelCacheManagerPackageCacheGenerationTest,AIFabricTipTest::_tip_ModelCacheManagerPackageCacheGenerationTest>::Release(void)
0x1800084c0  add     rsp, 20h
0x1800084c4  pop     rbx
0x1800084c5  retn
```
