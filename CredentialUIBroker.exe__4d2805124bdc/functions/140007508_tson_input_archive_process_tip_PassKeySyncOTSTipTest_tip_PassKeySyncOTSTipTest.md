# tson::input_archive::process<_tip_PassKeySyncOTSTipTest &>(_tip_PassKeySyncOTSTipTest &)

- ea: `0x140007508`
- end: `0x1400075ed`
- name: `??$process@AEAU_tip_PassKeySyncOTSTipTest@@@input_archive@tson@@AEAAXAEAU_tip_PassKeySyncOTSTipTest@@@Z`
- size: `229`
- prototype: `__int64 __fastcall(tson::input_archive *this, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1400192f0`

## callees

- `0x140007508`
- `0x1400076f4`
- `0x14001925c`
- `0x14001aa04`
- `0x14001b580`

## string_xrefs

- `0x140007555`: `passkeySyncOTSThroughBrokerFailed`
- `0x14000756c`: `controllerInstanceNotCreated`

## pseudocode

```c
__int64 __fastcall tson::input_archive::process<_tip_PassKeySyncOTSTipTest &>(tson::input_archive *this, __int64 a2)
{
  __int64 result; // rax
  __int64 v5; // rdx
  __int64 v6; // rax
  __int64 v7; // rax
  const char *v8; // [rsp+20h] [rbp-50h] BYREF
  char v9; // [rsp+28h] [rbp-48h]
  __int64 v10; // [rsp+30h] [rbp-40h]
  const char *v11; // [rsp+38h] [rbp-38h] BYREF
  char v12; // [rsp+40h] [rbp-30h]
  __int64 v13; // [rsp+48h] [rbp-28h]
  const char *v14; // [rsp+50h] [rbp-20h] BYREF
  char v15; // [rsp+58h] [rbp-18h]
  __int64 v16; // [rsp+60h] [rbp-10h]

  tson::input_archive::search(this);
  if ( !*((_BYTE *)this + 25) )
    tson::input_archive::push_node(this);
  v15 = 21;
  v14 = "shellHostLaunchFailed";
  v12 = 33;
  v16 = a2 + 24;
  v9 = 28;
  v11 = "passkeySyncOTSThroughBrokerFailed";
  v13 = a2 + 20;
  v8 = "controllerInstanceNotCreated";
  v10 = a2 + 16;
  tson::input_archive::process<tson::nvp<long &>>(this, &v8);
  tson::input_archive::process<tson::nvp<long &>>(this, &v11);
  result = tson::input_archive::process<tson::nvp<long &>>(this, &v14);
  if ( !*((_BYTE *)this + 25) )
  {
    v6 = *((_QWORD *)this + 17);
    if ( v6 )
    {
      v7 = v6 - 1;
      *((_QWORD *)this + 17) = v7;
      if ( *((_DWORD *)this + v7 + 9) == 1 )
      {
        LOBYTE(v5) = 4;
LABEL_9:
        result = tson::input_archive::consume_expected_marker(this, v5, 2147944029LL);
        goto LABEL_10;
      }
    }
    else
    {
      *((_BYTE *)this + 32) = 1;
    }
    LOBYTE(v5) = 2;
    goto LABEL_9;
  }
LABEL_10:
  *((_BYTE *)this + 25) = 0;
  return result;
}

```

## disassembly

```asm
0x140007508  mov     [rsp-8+arg_0], rbx
0x14000750d  mov     [rsp-8+arg_8], rdi
0x140007512  push    rbp
0x140007513  mov     rbp, rsp
0x140007516  sub     rsp, 70h
0x14000751a  mov     rdi, rdx
0x14000751d  mov     rbx, rcx
0x140007520  call    ?search@input_archive@tson@@AEAA_NXZ; tson::input_archive::search(void)
0x140007525  cmp     byte ptr [rbx+19h], 0
0x140007529  jnz     short loc_140007533
0x14000752b  mov     rcx, rbx; this
0x14000752e  call    ?push_node@input_archive@tson@@AEAAXXZ; tson::input_archive::push_node(void)
0x140007533  lea     rax, aShellhostlaunc; "shellHostLaunchFailed"
0x14000753a  mov     [rbp+var_18], 15h
0x14000753e  mov     [rbp+var_20], rax
0x140007542  lea     rdx, [rbp+var_50]
0x140007546  lea     rax, [rdi+18h]
0x14000754a  mov     [rbp+var_30], 21h ; '!'
0x14000754e  mov     [rbp+var_10], rax
0x140007552  mov     rcx, rbx
0x140007555  lea     rax, aPasskeysyncots; "passkeySyncOTSThroughBrokerFailed"
0x14000755c  mov     [rbp+var_48], 1Ch
0x140007560  mov     [rbp+var_38], rax
0x140007564  lea     rax, [rdi+14h]
0x140007568  mov     [rbp+var_28], rax
0x14000756c  lea     rax, aControllerinst; "controllerInstanceNotCreated"
0x140007573  mov     [rbp+var_50], rax
0x140007577  lea     rax, [rdi+10h]
0x14000757b  mov     [rbp+var_40], rax
0x14000757f  call    ??$process@V?$nvp@AEAJ@tson@@@input_archive@tson@@AEAAX$$QEAV?$nvp@AEAJ@1@@Z; tson::input_archive::process<tson::nvp<long &>>(tson::nvp<long &> &&)
0x140007584  lea     rdx, [rbp+var_38]
0x140007588  mov     rcx, rbx
0x14000758b  call    ??$process@V?$nvp@AEAJ@tson@@@input_archive@tson@@AEAAX$$QEAV?$nvp@AEAJ@1@@Z; tson::input_archive::process<tson::nvp<long &>>(tson::nvp<long &> &&)
0x140007590  lea     rdx, [rbp+var_20]
0x140007594  mov     rcx, rbx
0x140007597  call    ??$process@V?$nvp@AEAJ@tson@@@input_archive@tson@@AEAAX$$QEAV?$nvp@AEAJ@1@@Z; tson::input_archive::process<tson::nvp<long &>>(tson::nvp<long &> &&)
0x14000759c  cmp     byte ptr [rbx+19h], 0
0x1400075a0  jnz     short loc_1400075D7
0x1400075a2  mov     rax, [rbx+88h]
0x1400075a9  test    rax, rax
0x1400075ac  jz      short loc_1400075C3
0x1400075ae  dec     rax
0x1400075b1  mov     [rbx+88h], rax
0x1400075b8  cmp     dword ptr [rbx+rax*4+24h], 1
0x1400075bd  jnz     short loc_1400075C7
0x1400075bf  mov     dl, 4
0x1400075c1  jmp     short loc_1400075C9
0x1400075c3  mov     byte ptr [rbx+20h], 1
0x1400075c7  mov     dl, 2
0x1400075c9  mov     r8d, 8007065Dh
0x1400075cf  mov     rcx, rbx
0x1400075d2  call    ?consume_expected_marker@input_archive@tson@@AEAA_NW4archive_marker@details@2@J@Z; tson::input_archive::consume_expected_marker(tson::details::archive_marker,long)
0x1400075d7  lea     r11, [rsp+70h+var_s0]
0x1400075dc  mov     byte ptr [rbx+19h], 0
0x1400075e0  mov     rbx, [r11+10h]
0x1400075e4  mov     rdi, [r11+18h]
0x1400075e8  mov     rsp, r11
0x1400075eb  pop     rbp
0x1400075ec  retn
```
