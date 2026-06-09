# tip2::details::merged_data<_tip_HumanPresenceAccessChangedTest,_tip_HumanPresenceAccessChangedTest>::deserialize(tson::input_archive &)

- ea: `0x18000d350`
- end: `0x18000d37a`
- name: `?deserialize@?$merged_data@U_tip_HumanPresenceAccessChangedTest@@U1@@details@tip2@@EEAAXAEAVinput_archive@tson@@@Z`
- size: `42`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18000a6d0`

## pseudocode

```c
void __fastcall tip2::details::merged_data<_tip_HumanPresenceAccessChangedTest,_tip_HumanPresenceAccessChangedTest>::deserialize(
        __int64 a1,
        __int64 a2)
{
  *(_BYTE *)(a2 + 24) = 4;
  *(_QWORD *)(a2 + 16) = "test";
  tson::input_archive::process<_tip_HumanPresenceAccessChangedTest &>(
    (tson::input_archive *)a2,
    (a1 + 256) & -(__int64)(a1 != 0));
}

```

## disassembly

```asm
0x18000d350  mov     r8, rdx
0x18000d353  mov     byte ptr [rdx+18h], 4
0x18000d357  lea     rax, aTest; "test"
0x18000d35e  mov     [rdx+10h], rax
0x18000d362  lea     rax, [rcx+100h]
0x18000d369  neg     rcx
0x18000d36c  mov     rcx, r8; this
0x18000d36f  sbb     rdx, rdx
0x18000d372  and     rdx, rax
0x18000d375  jmp     ??$process@AEAU_tip_HumanPresenceAccessChangedTest@@@input_archive@tson@@AEAAXAEAU_tip_HumanPresenceAccessChangedTest@@@Z; tson::input_archive::process<_tip_HumanPresenceAccessChangedTest &>(_tip_HumanPresenceAccessChangedTest &)
```
