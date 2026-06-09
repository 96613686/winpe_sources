# tip2::details::merged_data<AIFabricTipTest::_tip_ModelCacheManagerPackageCacheGenerationTest,AIFabricTipTest::_tip_ModelCacheManagerPackageCacheGenerationTest>::deserialize(tson::input_archive &)

- ea: `0x1800097e0`
- end: `0x18000980b`
- name: `?deserialize@?$merged_data@U_tip_ModelCacheManagerPackageCacheGenerationTest@AIFabricTipTest@@U12@@details@tip2@@EEAAXAEAVinput_archive@tson@@@Z`
- size: `43`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18000bf10`

## pseudocode

```c
__int64 __fastcall tip2::details::merged_data<AIFabricTipTest::_tip_ModelCacheManagerPackageCacheGenerationTest,AIFabricTipTest::_tip_ModelCacheManagerPackageCacheGenerationTest>::deserialize(
        __int64 a1,
        __int64 a2)
{
  __int64 v3; // rdx

  *(_QWORD *)(a2 + 16) = "test";
  v3 = a1 + 248;
  if ( !a1 )
    v3 = 0;
  *(_BYTE *)(a2 + 24) = 4;
  return tson::input_archive::process<AIFabricTipTest::_tip_ModelCacheManagerPackageCacheGenerationTest &>(
           (tson::input_archive *)a2,
           v3);
}

```

## disassembly

```asm
0x1800097e0  mov     rax, rdx
0x1800097e3  xor     r8d, r8d
0x1800097e6  test    rcx, rcx
0x1800097e9  lea     rdx, aTest; "test"
0x1800097f0  mov     [rax+10h], rdx
0x1800097f4  lea     rdx, [rcx+0F8h]
0x1800097fb  cmovz   rdx, r8
0x1800097ff  mov     byte ptr [rax+18h], 4
0x180009803  mov     rcx, rax
0x180009806  jmp     ??$process@AEAU_tip_ModelCacheManagerPackageCacheGenerationTest@AIFabricTipTest@@@input_archive@tson@@AEAAXAEAU_tip_ModelCacheManagerPackageCacheGenerationTest@AIFabricTipTest@@@Z; tson::input_archive::process<AIFabricTipTest::_tip_ModelCacheManagerPackageCacheGenerationTest &>(AIFabricTipTest::_tip_ModelCacheManagerPackageCacheGenerationTest &)
```
