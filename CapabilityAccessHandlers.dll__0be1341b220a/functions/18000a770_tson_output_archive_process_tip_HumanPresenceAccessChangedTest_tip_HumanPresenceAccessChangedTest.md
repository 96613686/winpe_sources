# tson::output_archive::process<_tip_HumanPresenceAccessChangedTest &>(_tip_HumanPresenceAccessChangedTest &)

- ea: `0x18000a770`
- end: `0x18000a807`
- name: `??$process@AEAU_tip_HumanPresenceAccessChangedTest@@@output_archive@tson@@AEAAXAEAU_tip_HumanPresenceAccessChangedTest@@@Z`
- size: `151`
- prototype: `void __fastcall(tson::output_archive *this, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000e9f0`

## callees

- `0x18000aad0`
- `0x18000ab58`
- `0x18000df0c`
- `0x18000ef58`

## pseudocode

```c
void __fastcall tson::output_archive::process<_tip_HumanPresenceAccessChangedTest &>(
        tson::output_archive *this,
        __int64 a2)
{
  const char *v4; // [rsp+20h] [rbp-50h] BYREF
  char v5; // [rsp+28h] [rbp-48h]
  __int64 v6; // [rsp+30h] [rbp-40h]
  const char *v7; // [rsp+38h] [rbp-38h] BYREF
  char v8; // [rsp+40h] [rbp-30h]
  __int64 v9; // [rsp+48h] [rbp-28h]
  const char *v10; // [rsp+50h] [rbp-20h] BYREF
  char v11; // [rsp+58h] [rbp-18h]
  __int64 v12; // [rsp+60h] [rbp-10h]

  tson::output_archive::startNode(this);
  v8 = 29;
  v7 = "customCapabilityRevokeEndTime";
  v11 = 23;
  v9 = a2 + 32;
  v5 = 9;
  v10 = "capabilityRevokeEndTime";
  v12 = a2 + 24;
  v4 = "startTime";
  v6 = a2 + 16;
  tson::output_archive::process<tson::nvp<unsigned __int64 &>>(this, &v4);
  tson::output_archive::process<tson::nvp<unsigned __int64 &>,tson::nvp<unsigned __int64 &>>(this, &v10, &v7);
  tson::output_archive::finishNode(this);
}

```

## disassembly

```asm
0x18000a770  mov     [rsp-8+arg_0], rbx
0x18000a775  mov     [rsp-8+arg_8], rdi
0x18000a77a  push    rbp
0x18000a77b  mov     rbp, rsp
0x18000a77e  sub     rsp, 70h
0x18000a782  mov     rbx, rdx
0x18000a785  mov     rdi, rcx
0x18000a788  call    ?startNode@output_archive@tson@@QEAAXXZ; tson::output_archive::startNode(void)
0x18000a78d  lea     rax, aCustomcapabili; "customCapabilityRevokeEndTime"
0x18000a794  mov     [rbp+var_30], 1Dh
0x18000a798  mov     [rbp+var_38], rax
0x18000a79c  lea     rdx, [rbp+var_50]
0x18000a7a0  lea     rax, [rbx+20h]
0x18000a7a4  mov     [rbp+var_18], 17h
0x18000a7a8  mov     [rbp+var_28], rax
0x18000a7ac  mov     rcx, rdi
0x18000a7af  lea     rax, aCapabilityrevo; "capabilityRevokeEndTime"
0x18000a7b6  mov     [rbp+var_48], 9
0x18000a7ba  mov     [rbp+var_20], rax
0x18000a7be  lea     rax, [rbx+18h]
0x18000a7c2  mov     [rbp+var_10], rax
0x18000a7c6  lea     rax, aStarttime; "startTime"
0x18000a7cd  mov     [rbp+var_50], rax
0x18000a7d1  lea     rax, [rbx+10h]
0x18000a7d5  mov     [rbp+var_40], rax
0x18000a7d9  call    ??$process@V?$nvp@AEA_K@tson@@@output_archive@tson@@AEAAX$$QEAV?$nvp@AEA_K@1@@Z; tson::output_archive::process<tson::nvp<unsigned __int64 &>>(tson::nvp<unsigned __int64 &> &&)
0x18000a7de  lea     r8, [rbp+var_38]
0x18000a7e2  mov     rcx, rdi
0x18000a7e5  lea     rdx, [rbp+var_20]
0x18000a7e9  call    ??$process@V?$nvp@AEA_K@tson@@V12@@output_archive@tson@@AEAAX$$QEAV?$nvp@AEA_K@1@0@Z; tson::output_archive::process<tson::nvp<unsigned __int64 &>,tson::nvp<unsigned __int64 &>>(tson::nvp<unsigned __int64 &> &&,tson::nvp<unsigned __int64 &> &&)
0x18000a7ee  mov     rcx, rdi; this
0x18000a7f1  lea     r11, [rsp+70h+var_s0]
0x18000a7f6  mov     rbx, [r11+10h]
0x18000a7fa  mov     rdi, [r11+18h]
0x18000a7fe  mov     rsp, r11
0x18000a801  pop     rbp
0x18000a802  jmp     ?finishNode@output_archive@tson@@QEAAXXZ; tson::output_archive::finishNode(void)
```
