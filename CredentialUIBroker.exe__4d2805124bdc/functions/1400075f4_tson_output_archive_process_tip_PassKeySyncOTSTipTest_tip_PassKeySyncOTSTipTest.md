# tson::output_archive::process<_tip_PassKeySyncOTSTipTest &>(_tip_PassKeySyncOTSTipTest &)

- ea: `0x1400075f4`
- end: `0x140007693`
- name: `??$process@AEAU_tip_PassKeySyncOTSTipTest@@@output_archive@tson@@AEAAXAEAU_tip_PassKeySyncOTSTipTest@@@Z`
- size: `159`
- prototype: `void __fastcall(tson::output_archive *this, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14001b680`

## callees

- `0x140007768`
- `0x140019a5c`
- `0x14001bae8`

## string_xrefs

- `0x140007633`: `passkeySyncOTSThroughBrokerFailed`
- `0x14000764a`: `controllerInstanceNotCreated`

## pseudocode

```c
void __fastcall tson::output_archive::process<_tip_PassKeySyncOTSTipTest &>(tson::output_archive *this, __int64 a2)
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
  v11 = 21;
  v10 = "shellHostLaunchFailed";
  v8 = 33;
  v12 = a2 + 24;
  v5 = 28;
  v7 = "passkeySyncOTSThroughBrokerFailed";
  v9 = a2 + 20;
  v4 = "controllerInstanceNotCreated";
  v6 = a2 + 16;
  tson::output_archive::process<tson::nvp<long &>>(this, &v4);
  tson::output_archive::process<tson::nvp<long &>>(this, &v7);
  tson::output_archive::process<tson::nvp<long &>>(this, &v10);
  tson::output_archive::finishNode(this);
}

```

## disassembly

```asm
0x1400075f4  mov     [rsp-8+arg_0], rbx
0x1400075f9  mov     [rsp-8+arg_8], rdi
0x1400075fe  push    rbp
0x1400075ff  mov     rbp, rsp
0x140007602  sub     rsp, 70h
0x140007606  mov     rbx, rdx
0x140007609  mov     rdi, rcx
0x14000760c  call    ?startNode@output_archive@tson@@QEAAXXZ; tson::output_archive::startNode(void)
0x140007611  lea     rax, aShellhostlaunc; "shellHostLaunchFailed"
0x140007618  mov     [rbp+var_18], 15h
0x14000761c  mov     [rbp+var_20], rax
0x140007620  lea     rdx, [rbp+var_50]
0x140007624  lea     rax, [rbx+18h]
0x140007628  mov     [rbp+var_30], 21h ; '!'
0x14000762c  mov     [rbp+var_10], rax
0x140007630  mov     rcx, rdi
0x140007633  lea     rax, aPasskeysyncots; "passkeySyncOTSThroughBrokerFailed"
0x14000763a  mov     [rbp+var_48], 1Ch
0x14000763e  mov     [rbp+var_38], rax
0x140007642  lea     rax, [rbx+14h]
0x140007646  mov     [rbp+var_28], rax
0x14000764a  lea     rax, aControllerinst; "controllerInstanceNotCreated"
0x140007651  mov     [rbp+var_50], rax
0x140007655  lea     rax, [rbx+10h]
0x140007659  mov     [rbp+var_40], rax
0x14000765d  call    ??$process@V?$nvp@AEAJ@tson@@@output_archive@tson@@AEAAX$$QEAV?$nvp@AEAJ@1@@Z; tson::output_archive::process<tson::nvp<long &>>(tson::nvp<long &> &&)
0x140007662  lea     rdx, [rbp+var_38]
0x140007666  mov     rcx, rdi
0x140007669  call    ??$process@V?$nvp@AEAJ@tson@@@output_archive@tson@@AEAAX$$QEAV?$nvp@AEAJ@1@@Z; tson::output_archive::process<tson::nvp<long &>>(tson::nvp<long &> &&)
0x14000766e  lea     rdx, [rbp+var_20]
0x140007672  mov     rcx, rdi
0x140007675  call    ??$process@V?$nvp@AEAJ@tson@@@output_archive@tson@@AEAAX$$QEAV?$nvp@AEAJ@1@@Z; tson::output_archive::process<tson::nvp<long &>>(tson::nvp<long &> &&)
0x14000767a  mov     rcx, rdi; this
0x14000767d  lea     r11, [rsp+70h+var_s0]
0x140007682  mov     rbx, [r11+10h]
0x140007686  mov     rdi, [r11+18h]
0x14000768a  mov     rsp, r11
0x14000768d  pop     rbp
0x14000768e  jmp     ?finishNode@output_archive@tson@@QEAAXXZ; tson::output_archive::finishNode(void)
```
