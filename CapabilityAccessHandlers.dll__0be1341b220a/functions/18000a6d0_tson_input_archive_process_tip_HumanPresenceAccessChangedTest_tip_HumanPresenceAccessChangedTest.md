# tson::input_archive::process<_tip_HumanPresenceAccessChangedTest &>(_tip_HumanPresenceAccessChangedTest &)

- ea: `0x18000a6d0`
- end: `0x18000a767`
- name: `??$process@AEAU_tip_HumanPresenceAccessChangedTest@@@input_archive@tson@@AEAAXAEAU_tip_HumanPresenceAccessChangedTest@@@Z`
- size: `151`
- prototype: `void __fastcall(tson::input_archive *this, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000d350`

## callees

- `0x18000aa6c`
- `0x18000ab28`
- `0x18000debc`
- `0x18000eed0`

## pseudocode

```c
void __fastcall tson::input_archive::process<_tip_HumanPresenceAccessChangedTest &>(
        tson::input_archive *this,
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

  tson::input_archive::startNode(this);
  v8 = 29;
  v7 = "customCapabilityRevokeEndTime";
  v11 = 23;
  v9 = a2 + 32;
  v5 = 9;
  v10 = "capabilityRevokeEndTime";
  v12 = a2 + 24;
  v4 = "startTime";
  v6 = a2 + 16;
  tson::input_archive::process<tson::nvp<unsigned __int64 &>>(this, &v4);
  tson::input_archive::process<tson::nvp<unsigned __int64 &>,tson::nvp<unsigned __int64 &>>(this, &v10, &v7);
  tson::input_archive::finishNode(this);
}

```

## disassembly

```asm
0x18000a6d0  mov     [rsp-8+arg_0], rbx
0x18000a6d5  mov     [rsp-8+arg_8], rdi
0x18000a6da  push    rbp
0x18000a6db  mov     rbp, rsp
0x18000a6de  sub     rsp, 70h
0x18000a6e2  mov     rbx, rdx
0x18000a6e5  mov     rdi, rcx
0x18000a6e8  call    ?startNode@input_archive@tson@@QEAAXXZ; tson::input_archive::startNode(void)
0x18000a6ed  lea     rax, aCustomcapabili; "customCapabilityRevokeEndTime"
0x18000a6f4  mov     [rbp+var_30], 1Dh
0x18000a6f8  mov     [rbp+var_38], rax
0x18000a6fc  lea     rdx, [rbp+var_50]
0x18000a700  lea     rax, [rbx+20h]
0x18000a704  mov     [rbp+var_18], 17h
0x18000a708  mov     [rbp+var_28], rax
0x18000a70c  mov     rcx, rdi
0x18000a70f  lea     rax, aCapabilityrevo; "capabilityRevokeEndTime"
0x18000a716  mov     [rbp+var_48], 9
0x18000a71a  mov     [rbp+var_20], rax
0x18000a71e  lea     rax, [rbx+18h]
0x18000a722  mov     [rbp+var_10], rax
0x18000a726  lea     rax, aStarttime; "startTime"
0x18000a72d  mov     [rbp+var_50], rax
0x18000a731  lea     rax, [rbx+10h]
0x18000a735  mov     [rbp+var_40], rax
0x18000a739  call    ??$process@V?$nvp@AEA_K@tson@@@input_archive@tson@@AEAAX$$QEAV?$nvp@AEA_K@1@@Z; tson::input_archive::process<tson::nvp<unsigned __int64 &>>(tson::nvp<unsigned __int64 &> &&)
0x18000a73e  lea     r8, [rbp+var_38]
0x18000a742  mov     rcx, rdi
0x18000a745  lea     rdx, [rbp+var_20]
0x18000a749  call    ??$process@V?$nvp@AEA_K@tson@@V12@@input_archive@tson@@AEAAX$$QEAV?$nvp@AEA_K@1@0@Z; tson::input_archive::process<tson::nvp<unsigned __int64 &>,tson::nvp<unsigned __int64 &>>(tson::nvp<unsigned __int64 &> &&,tson::nvp<unsigned __int64 &> &&)
0x18000a74e  mov     rcx, rdi; this
0x18000a751  lea     r11, [rsp+70h+var_s0]
0x18000a756  mov     rbx, [r11+10h]
0x18000a75a  mov     rdi, [r11+18h]
0x18000a75e  mov     rsp, r11
0x18000a761  pop     rbp
0x18000a762  jmp     ?finishNode@input_archive@tson@@QEAAXXZ; tson::input_archive::finishNode(void)
```
