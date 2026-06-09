# CommonUtil::MpEnsureProcessMitigationPolicy(ulong)

- ea: `0x140021424`
- end: `0x140021786`
- name: `?MpEnsureProcessMitigationPolicy@CommonUtil@@YAJK@Z`
- size: `866`
- prototype: `__int64 __fastcall(CommonUtil *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x14001d700`

## callees

- `0x140004b1c`
- `0x14001da4c`
- `0x14001da70`
- `0x140020b08`
- `0x140020c7c`
- `0x140020de0`
- `0x140020f38`
- `0x14002109c`
- `0x1400211ec`
- `0x1400212c0`
- `0x140021424`
- `0x140021788`
- `0x140021964`
- `0x140021abc`
- `0x140021d78`
- `0x140021de0`

## pseudocode

```c
__int64 __fastcall CommonUtil::MpEnsureProcessMitigationPolicy(CommonUtil *this)
{
  int v1; // ebx
  unsigned int *v2; // r8
  int v3; // eax
  unsigned int *v4; // r8
  int v5; // eax
  unsigned int *v6; // r8
  int v7; // eax
  unsigned int *v8; // r8
  int v9; // eax
  unsigned int *v10; // r8
  int v11; // eax
  unsigned int *v12; // r8
  int v13; // eax
  CommonUtil *v14; // rcx
  unsigned int *v15; // r8
  int v16; // eax
  unsigned int *v17; // r8
  _QWORD *v18; // rcx
  int v19; // eax
  int v20; // eax
  int v21; // eax
  unsigned int v23; // [rsp+58h] [rbp+28h] BYREF
  unsigned int v24; // [rsp+60h] [rbp+30h] BYREF

  v1 = (int)this;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      55,
      &WPP_d1ba5309cc45319bcbd4e2e17652be78_Traceguids,
      (unsigned int)this);
  v24 = 0;
  v23 = 0;
  if ( !(unsigned int)MpIsWindowsRedstone3OrGreater() )
    return 0;
  v3 = CommonUtil::MpEnsureProcessDEPPolicy((CommonUtil *)&v24, &v23, v2);
  if ( v3 < 0 && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      56,
      &WPP_d1ba5309cc45319bcbd4e2e17652be78_Traceguids,
      (unsigned int)v3);
  v5 = CommonUtil::MpEnsureProcessASLRPolicy((CommonUtil *)&v24, &v23, v4);
  if ( v5 < 0 && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      57,
      &WPP_d1ba5309cc45319bcbd4e2e17652be78_Traceguids,
      (unsigned int)v5);
  v7 = CommonUtil::MpEnsureProcessStrictHandleCheckPolicy((CommonUtil *)&v24, &v23, v6);
  if ( v7 < 0 && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      58,
      &WPP_d1ba5309cc45319bcbd4e2e17652be78_Traceguids,
      (unsigned int)v7);
  v9 = CommonUtil::MpEnsureProcessExtensionPointDisablePolicy((CommonUtil *)&v24, &v23, v8);
  if ( v9 < 0 && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      59,
      &WPP_d1ba5309cc45319bcbd4e2e17652be78_Traceguids,
      (unsigned int)v9);
  v11 = CommonUtil::MpEnsureProcessControlFlowGuardPolicy((CommonUtil *)&v24, &v23, v10);
  if ( v11 < 0
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      60,
      &WPP_d1ba5309cc45319bcbd4e2e17652be78_Traceguids,
      (unsigned int)v11);
  }
  v13 = CommonUtil::MpEnsureProcessSignaturePolicy((CommonUtil *)&v24, &v23, v12);
  if ( v13 < 0 )
  {
    v14 = (CommonUtil *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        61,
        &WPP_d1ba5309cc45319bcbd4e2e17652be78_Traceguids,
        (unsigned int)v13);
  }
  v16 = CommonUtil::MpEnsureProcessFontDisablePolicy(v14, &v23, v15);
  if ( v16 >= 0 )
    goto LABEL_33;
  v18 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      62,
      &WPP_d1ba5309cc45319bcbd4e2e17652be78_Traceguids,
      (unsigned int)v16);
LABEL_33:
    v18 = WPP_GLOBAL_Control;
  }
  if ( (v1 & 1) != 0 )
  {
    if ( v18 != &WPP_GLOBAL_Control && (*((_BYTE *)v18 + 28) & 4) != 0 )
    {
      WPP_SF_(v18[2], 64, &WPP_d1ba5309cc45319bcbd4e2e17652be78_Traceguids);
      goto LABEL_42;
    }
  }
  else
  {
    v19 = CommonUtil::MpEnsureProcessDynamicCodePolicy((CommonUtil *)&v24, &v23, v17);
    if ( v19 >= 0 )
    {
LABEL_42:
      v18 = WPP_GLOBAL_Control;
      goto LABEL_43;
    }
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        63,
        &WPP_d1ba5309cc45319bcbd4e2e17652be78_Traceguids,
        (unsigned int)v19);
      goto LABEL_42;
    }
  }
LABEL_43:
  if ( (v1 & 4) != 0 )
  {
    if ( v18 != &WPP_GLOBAL_Control && (*((_BYTE *)v18 + 28) & 4) != 0 )
    {
      WPP_SF_(v18[2], 66, &WPP_d1ba5309cc45319bcbd4e2e17652be78_Traceguids);
      goto LABEL_51;
    }
  }
  else
  {
    v20 = CommonUtil::MpEnsureProcessSystemCallDisablePolicy((CommonUtil *)&v24, &v23, v17);
    if ( v20 >= 0 )
    {
LABEL_51:
      v18 = WPP_GLOBAL_Control;
      goto LABEL_52;
    }
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        65,
        &WPP_d1ba5309cc45319bcbd4e2e17652be78_Traceguids,
        (unsigned int)v20);
      goto LABEL_51;
    }
  }
LABEL_52:
  if ( (v1 & 2) != 0 )
  {
    if ( v18 != &WPP_GLOBAL_Control && (*((_BYTE *)v18 + 28) & 4) != 0 )
    {
      WPP_SF_(v18[2], 68, &WPP_d1ba5309cc45319bcbd4e2e17652be78_Traceguids);
      goto LABEL_60;
    }
  }
  else
  {
    v21 = CommonUtil::MpEnsureProcessImageLoadPolicy((CommonUtil *)&v24, &v23, v17);
    if ( v21 >= 0 )
    {
LABEL_60:
      v18 = WPP_GLOBAL_Control;
      goto LABEL_61;
    }
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        67,
        &WPP_d1ba5309cc45319bcbd4e2e17652be78_Traceguids,
        (unsigned int)v21);
      goto LABEL_60;
    }
  }
LABEL_61:
  if ( !v24 )
  {
    if ( v18 != &WPP_GLOBAL_Control && (*((_BYTE *)v18 + 28) & 2) != 0 )
      WPP_SF_DL(v18[2], v24, v17, v23, v1);
    return 0;
  }
  if ( v18 != &WPP_GLOBAL_Control && (*((_BYTE *)v18 + 28) & 2) != 0 )
    WPP_SF_DLD(v18[2], v24, v17, v23, v1, v24);
  return 1;
}

```

## disassembly

```asm
0x140021424  mov     [rsp-18h+arg_0], rbx
0x140021429  push    rbp
0x14002142a  push    rdi
0x14002142b  push    r14
0x14002142d  mov     rbp, rsp
0x140021430  sub     rsp, 30h
0x140021434  mov     ebx, ecx
0x140021436  mov     rcx, cs:WPP_GLOBAL_Control
0x14002143d  lea     rdi, WPP_GLOBAL_Control
0x140021444  lea     r14, WPP_d1ba5309cc45319bcbd4e2e17652be78_Traceguids
0x14002144b  cmp     rcx, rdi
0x14002144e  jz      short loc_14002146A
0x140021450  test    byte ptr [rcx+1Ch], 4
0x140021454  jz      short loc_14002146A
0x140021456  mov     rcx, [rcx+10h]
0x14002145a  mov     edx, 37h ; '7'
0x14002145f  mov     r9d, ebx
0x140021462  mov     r8, r14
0x140021465  call    WPP_SF_d
0x14002146a  mov     [rbp+arg_10], 0
0x140021471  mov     [rbp+arg_8], 0
0x140021478  call    MpIsWindowsRedstone3OrGreater
0x14002147d  test    eax, eax
0x14002147f  jz      loc_140021776
0x140021485  lea     rdx, [rbp+arg_8]; unsigned int *
0x140021489  lea     rcx, [rbp+arg_10]; this
0x14002148d  call    ?MpEnsureProcessDEPPolicy@CommonUtil@@YAJAEAK0@Z; CommonUtil::MpEnsureProcessDEPPolicy(ulong &,ulong &)
0x140021492  test    eax, eax
0x140021494  jns     short loc_1400214BC
0x140021496  mov     rcx, cs:WPP_GLOBAL_Control
0x14002149d  cmp     rcx, rdi
0x1400214a0  jz      short loc_1400214BC
0x1400214a2  test    byte ptr [rcx+1Ch], 2
0x1400214a6  jz      short loc_1400214BC
0x1400214a8  mov     rcx, [rcx+10h]
0x1400214ac  mov     edx, 38h ; '8'
0x1400214b1  mov     r9d, eax
0x1400214b4  mov     r8, r14
0x1400214b7  call    WPP_SF_d
0x1400214bc  lea     rdx, [rbp+arg_8]; unsigned int *
0x1400214c0  lea     rcx, [rbp+arg_10]; this
0x1400214c4  call    ?MpEnsureProcessASLRPolicy@CommonUtil@@YAJAEAK0@Z; CommonUtil::MpEnsureProcessASLRPolicy(ulong &,ulong &)
0x1400214c9  test    eax, eax
0x1400214cb  jns     short loc_1400214F3
0x1400214cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400214d4  cmp     rcx, rdi
0x1400214d7  jz      short loc_1400214F3
0x1400214d9  test    byte ptr [rcx+1Ch], 2
0x1400214dd  jz      short loc_1400214F3
0x1400214df  mov     rcx, [rcx+10h]
0x1400214e3  mov     edx, 39h ; '9'
0x1400214e8  mov     r9d, eax
0x1400214eb  mov     r8, r14
0x1400214ee  call    WPP_SF_d
0x1400214f3  lea     rdx, [rbp+arg_8]; unsigned int *
0x1400214f7  lea     rcx, [rbp+arg_10]; this
0x1400214fb  call    ?MpEnsureProcessStrictHandleCheckPolicy@CommonUtil@@YAJAEAK0@Z; CommonUtil::MpEnsureProcessStrictHandleCheckPolicy(ulong &,ulong &)
0x140021500  test    eax, eax
0x140021502  jns     short loc_14002152A
0x140021504  mov     rcx, cs:WPP_GLOBAL_Control
0x14002150b  cmp     rcx, rdi
0x14002150e  jz      short loc_14002152A
0x140021510  test    byte ptr [rcx+1Ch], 2
0x140021514  jz      short loc_14002152A
0x140021516  mov     rcx, [rcx+10h]
0x14002151a  mov     edx, 3Ah ; ':'
0x14002151f  mov     r9d, eax
0x140021522  mov     r8, r14
0x140021525  call    WPP_SF_d
0x14002152a  lea     rdx, [rbp+arg_8]; unsigned int *
0x14002152e  lea     rcx, [rbp+arg_10]; this
0x140021532  call    ?MpEnsureProcessExtensionPointDisablePolicy@CommonUtil@@YAJAEAK0@Z; CommonUtil::MpEnsureProcessExtensionPointDisablePolicy(ulong &,ulong &)
0x140021537  test    eax, eax
0x140021539  jns     short loc_140021561
0x14002153b  mov     rcx, cs:WPP_GLOBAL_Control
0x140021542  cmp     rcx, rdi
0x140021545  jz      short loc_140021561
0x140021547  test    byte ptr [rcx+1Ch], 2
0x14002154b  jz      short loc_140021561
0x14002154d  mov     rcx, [rcx+10h]
0x140021551  mov     edx, 3Bh ; ';'
0x140021556  mov     r9d, eax
0x140021559  mov     r8, r14
0x14002155c  call    WPP_SF_d
0x140021561  lea     rdx, [rbp+arg_8]; unsigned int *
0x140021565  lea     rcx, [rbp+arg_10]; this
0x140021569  call    ?MpEnsureProcessControlFlowGuardPolicy@CommonUtil@@YAJAEAK0@Z; CommonUtil::MpEnsureProcessControlFlowGuardPolicy(ulong &,ulong &)
0x14002156e  test    eax, eax
0x140021570  jns     short loc_140021598
0x140021572  mov     rcx, cs:WPP_GLOBAL_Control
0x140021579  cmp     rcx, rdi
0x14002157c  jz      short loc_140021598
0x14002157e  test    byte ptr [rcx+1Ch], 2
0x140021582  jz      short loc_140021598
0x140021584  mov     rcx, [rcx+10h]
0x140021588  mov     edx, 3Ch ; '<'
0x14002158d  mov     r9d, eax
0x140021590  mov     r8, r14
0x140021593  call    WPP_SF_d
0x140021598  lea     rdx, [rbp+arg_8]; unsigned int *
0x14002159c  lea     rcx, [rbp+arg_10]; this
0x1400215a0  call    ?MpEnsureProcessSignaturePolicy@CommonUtil@@YAJAEAK0@Z; CommonUtil::MpEnsureProcessSignaturePolicy(ulong &,ulong &)
0x1400215a5  test    eax, eax
0x1400215a7  jns     short loc_1400215CF
0x1400215a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400215b0  cmp     rcx, rdi
0x1400215b3  jz      short loc_1400215CF
0x1400215b5  test    byte ptr [rcx+1Ch], 2
0x1400215b9  jz      short loc_1400215CF
0x1400215bb  mov     rcx, [rcx+10h]
0x1400215bf  mov     edx, 3Dh ; '='
0x1400215c4  mov     r9d, eax
0x1400215c7  mov     r8, r14
0x1400215ca  call    WPP_SF_d
0x1400215cf  lea     rdx, [rbp+arg_8]; unsigned int *
0x1400215d3  call    ?MpEnsureProcessFontDisablePolicy@CommonUtil@@YAJAEAK0@Z; CommonUtil::MpEnsureProcessFontDisablePolicy(ulong &,ulong &)
0x1400215d8  test    eax, eax
0x1400215da  jns     short loc_140021602
0x1400215dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400215e3  cmp     rcx, rdi
0x1400215e6  jz      short loc_140021609
0x1400215e8  test    byte ptr [rcx+1Ch], 2
0x1400215ec  jz      short loc_140021609
0x1400215ee  mov     rcx, [rcx+10h]
0x1400215f2  mov     edx, 3Eh ; '>'
0x1400215f7  mov     r9d, eax
0x1400215fa  mov     r8, r14
0x1400215fd  call    WPP_SF_d
0x140021602  mov     rcx, cs:WPP_GLOBAL_Control
0x140021609  test    bl, 1
0x14002160c  jnz     short loc_140021647
0x14002160e  lea     rdx, [rbp+arg_8]; unsigned int *
0x140021612  lea     rcx, [rbp+arg_10]; this
0x140021616  call    ?MpEnsureProcessDynamicCodePolicy@CommonUtil@@YAJAEAK0@Z; CommonUtil::MpEnsureProcessDynamicCodePolicy(ulong &,ulong &)
0x14002161b  test    eax, eax
0x14002161d  jns     short loc_140021663
0x14002161f  mov     rcx, cs:WPP_GLOBAL_Control
0x140021626  cmp     rcx, rdi
0x140021629  jz      short loc_14002166A
0x14002162b  test    byte ptr [rcx+1Ch], 2
0x14002162f  jz      short loc_14002166A
0x140021631  mov     rcx, [rcx+10h]
0x140021635  mov     edx, 3Fh ; '?'
0x14002163a  mov     r9d, eax
0x14002163d  mov     r8, r14
0x140021640  call    WPP_SF_d
0x140021645  jmp     short loc_140021663
0x140021647  cmp     rcx, rdi
0x14002164a  jz      short loc_14002166A
0x14002164c  test    byte ptr [rcx+1Ch], 4
0x140021650  jz      short loc_14002166A
0x140021652  mov     rcx, [rcx+10h]
0x140021656  mov     edx, 40h ; '@'
0x14002165b  mov     r8, r14
0x14002165e  call    WPP_SF_
0x140021663  mov     rcx, cs:WPP_GLOBAL_Control
0x14002166a  test    bl, 4
0x14002166d  jnz     short loc_1400216A8
0x14002166f  lea     rdx, [rbp+arg_8]; unsigned int *
0x140021673  lea     rcx, [rbp+arg_10]; this
0x140021677  call    ?MpEnsureProcessSystemCallDisablePolicy@CommonUtil@@YAJAEAK0@Z; CommonUtil::MpEnsureProcessSystemCallDisablePolicy(ulong &,ulong &)
0x14002167c  test    eax, eax
0x14002167e  jns     short loc_1400216C4
0x140021680  mov     rcx, cs:WPP_GLOBAL_Control
0x140021687  cmp     rcx, rdi
0x14002168a  jz      short loc_1400216CB
0x14002168c  test    byte ptr [rcx+1Ch], 2
0x140021690  jz      short loc_1400216CB
0x140021692  mov     rcx, [rcx+10h]
0x140021696  mov     edx, 41h ; 'A'
0x14002169b  mov     r9d, eax
0x14002169e  mov     r8, r14
0x1400216a1  call    WPP_SF_d
0x1400216a6  jmp     short loc_1400216C4
0x1400216a8  cmp     rcx, rdi
0x1400216ab  jz      short loc_1400216CB
0x1400216ad  test    byte ptr [rcx+1Ch], 4
0x1400216b1  jz      short loc_1400216CB
0x1400216b3  mov     rcx, [rcx+10h]
0x1400216b7  mov     edx, 42h ; 'B'
0x1400216bc  mov     r8, r14
0x1400216bf  call    WPP_SF_
0x1400216c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400216cb  test    bl, 2
0x1400216ce  jnz     short loc_140021709
0x1400216d0  lea     rdx, [rbp+arg_8]; unsigned int *
0x1400216d4  lea     rcx, [rbp+arg_10]; this
0x1400216d8  call    ?MpEnsureProcessImageLoadPolicy@CommonUtil@@YAJAEAK0@Z; CommonUtil::MpEnsureProcessImageLoadPolicy(ulong &,ulong &)
0x1400216dd  test    eax, eax
0x1400216df  jns     short loc_140021725
0x1400216e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400216e8  cmp     rcx, rdi
0x1400216eb  jz      short loc_14002172C
0x1400216ed  test    byte ptr [rcx+1Ch], 2
0x1400216f1  jz      short loc_14002172C
0x1400216f3  mov     rcx, [rcx+10h]
0x1400216f7  mov     edx, 43h ; 'C'
0x1400216fc  mov     r9d, eax
0x1400216ff  mov     r8, r14
0x140021702  call    WPP_SF_d
0x140021707  jmp     short loc_140021725
0x140021709  cmp     rcx, rdi
0x14002170c  jz      short loc_14002172C
0x14002170e  test    byte ptr [rcx+1Ch], 4
0x140021712  jz      short loc_14002172C
0x140021714  mov     rcx, [rcx+10h]
0x140021718  mov     edx, 44h ; 'D'
0x14002171d  mov     r8, r14
0x140021720  call    WPP_SF_
0x140021725  mov     rcx, cs:WPP_GLOBAL_Control
0x14002172c  mov     edx, [rbp+arg_10]
0x14002172f  test    edx, edx
0x140021731  jz      short loc_14002175A
0x140021733  cmp     rcx, rdi
0x140021736  jz      short loc_140021753
0x140021738  test    byte ptr [rcx+1Ch], 2
0x14002173c  jz      short loc_140021753
0x14002173e  mov     r9d, [rbp+arg_8]
0x140021742  mov     rcx, [rcx+10h]
0x140021746  mov     [rsp+30h+var_8], edx
0x14002174a  mov     [rsp+30h+var_10], ebx
0x14002174e  call    WPP_SF_DLD
0x140021753  mov     eax, 1
0x140021758  jmp     short loc_140021778
0x14002175a  cmp     rcx, rdi
0x14002175d  jz      short loc_140021776
0x14002175f  test    byte ptr [rcx+1Ch], 2
0x140021763  jz      short loc_140021776
0x140021765  mov     r9d, [rbp+arg_8]
0x140021769  mov     rcx, [rcx+10h]
0x14002176d  mov     [rsp+30h+var_10], ebx
0x140021771  call    WPP_SF_DL
0x140021776  xor     eax, eax
0x140021778  mov     rbx, [rsp+30h+arg_0]
0x14002177d  add     rsp, 30h
0x140021781  pop     r14
0x140021783  pop     rdi
0x140021784  pop     rbp
0x140021785  retn
```
