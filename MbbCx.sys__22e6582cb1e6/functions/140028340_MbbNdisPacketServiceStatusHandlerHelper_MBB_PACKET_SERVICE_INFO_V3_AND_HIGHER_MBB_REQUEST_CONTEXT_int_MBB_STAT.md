# MbbNdisPacketServiceStatusHandlerHelper<_MBB_PACKET_SERVICE_INFO_V3_AND_HIGHER>(_MBB_REQUEST_CONTEXT *,int,_MBB_STATUS,uchar *,ulong)

- ea: `0x140028340`
- end: `0x1400287a7`
- name: `??$MbbNdisPacketServiceStatusHandlerHelper@U_MBB_PACKET_SERVICE_INFO_V3_AND_HIGHER@@@@YAHPEAU_MBB_REQUEST_CONTEXT@@HW4_MBB_STATUS@@PEAEK@Z`
- size: `1127`
- prototype: `__int64 __fastcall(struct _MBB_REQUEST_CONTEXT *, int, unsigned int, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x140031cc0`

## callees

- `0x140001db8`
- `0x1400051ac`
- `0x140005644`
- `0x140028340`
- `0x14002ec90`
- `0x14003f7e4`
- `0x140047530`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400283f4`
- `ntoskrnl!ExAllocatePool2` at `0x1400283f4`

## pseudocode

```c
__int64 __fastcall MbbNdisPacketServiceStatusHandlerHelper<_MBB_PACKET_SERVICE_INFO_V3_AND_HIGHER>(
        struct _MBB_REQUEST_CONTEXT *a1,
        int a2,
        unsigned int a3,
        __int64 a4,
        unsigned int a5)
{
  unsigned int v7; // ebp
  __int64 v9; // r13
  unsigned int v10; // r12d
  int v11; // edx
  unsigned int v12; // ebp
  __int64 Pool2; // rax
  _DWORD *v14; // r14
  struct _MBB_TLV_IE *v15; // r13
  struct _MBB_TLV_IE *v16; // rax
  struct _MBB_TLV_IE *v17; // rbp
  int v18; // eax
  unsigned int v19; // eax
  char v20; // al
  int v21; // r9d
  int v23; // [rsp+28h] [rbp-70h]
  char v24; // [rsp+30h] [rbp-68h]
  __int64 v25[11]; // [rsp+40h] [rbp-58h] BYREF
  unsigned __int8 *v26; // [rsp+A0h] [rbp+8h] BYREF
  unsigned int v27; // [rsp+A8h] [rbp+10h] BYREF
  unsigned int v28; // [rsp+B0h] [rbp+18h]
  __int64 v29; // [rsp+B8h] [rbp+20h]

  v28 = a3;
  v7 = a3;
  v9 = **((_QWORD **)a1 + 6);
  v29 = v9;
  v10 = MbbUtilMbbToWwanStatus(a3);
  v11 = 3;
  if ( a2 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v11) = 2;
      WPP_RECORDER_SF_DD(
        WPP_GLOBAL_Control->DeviceExtension,
        v11,
        3,
        93,
        (__int64)WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids,
        *((_DWORD *)a1 + 4),
        a2);
    }
LABEL_46:
    if ( v10 )
      v10 = MbbUtilMbbToWwanStatus(v7);
    goto LABEL_48;
  }
  v12 = a5;
  if ( !a4 || a5 < 0x2C )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v11) = 2;
      WPP_RECORDER_SF_Ddd(
        WPP_GLOBAL_Control->DeviceExtension,
        v11,
        3,
        94,
        (__int64)WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids,
        *((_DWORD *)a1 + 4),
        a5,
        44);
    }
    a2 = -1073676267;
    goto LABEL_45;
  }
  Pool2 = ExAllocatePool2(64, 44, 1683505741);
  v14 = (_DWORD *)Pool2;
  if ( !Pool2 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v11) = 2;
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        v11,
        3,
        95,
        (__int64)WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids,
        *((_DWORD *)a1 + 4));
    }
    a2 = -1073741670;
    goto LABEL_45;
  }
  *(_QWORD *)(Pool2 + 4) = 0;
  *(_QWORD *)(Pool2 + 12) = 0;
  *(_DWORD *)Pool2 = 2884480;
  *(_DWORD *)(Pool2 + 20) = *(_DWORD *)(a4 + 8);
  *(_DWORD *)(Pool2 + 24) = *(_DWORD *)(a4 + 28);
  *(_DWORD *)(Pool2 + 28) = *(_DWORD *)(a4 + 32);
  *(_WORD *)(Pool2 + 32) = *(_WORD *)(a4 + 36);
  *(_WORD *)(Pool2 + 34) = *(_WORD *)(a4 + 38);
  *(_DWORD *)(Pool2 + 36) = *(_DWORD *)(a4 + 40);
  *(_DWORD *)(Pool2 + 40) = -1;
  if ( *(_WORD *)(v9 + 82) < 0x400u )
    goto LABEL_37;
  v27 = 0;
  v25[0] = a4 + 44;
  v15 = 0;
  LODWORD(v26) = v12 - 44;
  if ( v12 == 44 )
    goto LABEL_36;
  while ( 1 )
  {
    v16 = mbbcx_p::ExtractValidateNextTlv((mbbcx_p *)v25, &v26, &v27, 0);
    v17 = v16;
    if ( !v16 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_35;
      v21 = 96;
      v24 = v27;
      v23 = *((_DWORD *)a1 + 4);
      goto LABEL_34;
    }
    v18 = *(unsigned __int16 *)v16;
    if ( v18 != 19 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v11) = 3;
        WPP_RECORDER_SF_DD(
          WPP_GLOBAL_Control->DeviceExtension,
          v11,
          9,
          100,
          (__int64)WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids,
          *((_DWORD *)a1 + 4),
          v18);
      }
      goto LABEL_23;
    }
    if ( v15 )
      break;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v11) = 4;
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        v11,
        9,
        98,
        (__int64)WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids,
        *((_DWORD *)a1 + 4));
    }
    v19 = *((_DWORD *)v17 + 1);
    if ( !v19 )
    {
      v20 = 15;
LABEL_28:
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_35;
      v24 = v20;
      v21 = 99;
      v23 = *((_DWORD *)a1 + 4);
LABEL_34:
      LOBYTE(v11) = 2;
      WPP_RECORDER_SF_DD(
        WPP_GLOBAL_Control->DeviceExtension,
        v11,
        9,
        v21,
        (__int64)WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids,
        v23,
        v24);
      goto LABEL_35;
    }
    if ( v19 > 4 )
    {
      v20 = 7;
      goto LABEL_28;
    }
    if ( *((_BYTE *)v17 + 3) )
    {
      v20 = 4;
      goto LABEL_28;
    }
    v15 = v17;
    v14[10] = *((_DWORD *)v17 + 2);
    v27 = 0;
LABEL_23:
    if ( !(_DWORD)v26 )
      goto LABEL_36;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v11) = 2;
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v11,
      9,
      97,
      (__int64)WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids,
      *((_DWORD *)a1 + 4));
  }
LABEL_35:
  a2 = -1073676267;
LABEL_36:
  v9 = v29;
LABEL_37:
  *((_DWORD *)a1 + 183) = 44;
  *((_QWORD *)a1 + 92) = v14;
  v14[2] = *(_DWORD *)a4;
  v14[1] = v10;
  if ( !v10 )
  {
    v14[3] = *(_DWORD *)(a4 + 4);
    *(_QWORD *)(v9 + 1056) = *(_QWORD *)(a4 + 12);
    *(_QWORD *)(v9 + 1064) = *(_QWORD *)(a4 + 20);
    if ( *(_BYTE *)(v9 + 1072) )
    {
      *((_DWORD *)a1 + 182) |= 1u;
      *((_DWORD *)a1 + 186) = *(_DWORD *)(v9 + 1076);
    }
  }
  if ( a2 )
  {
LABEL_45:
    v7 = v28;
    goto LABEL_46;
  }
LABEL_48:
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v11) = 4;
    WPP_RECORDER_SF_DD(
      WPP_GLOBAL_Control->DeviceExtension,
      v11,
      3,
      101,
      (__int64)WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids,
      *((_DWORD *)a1 + 4),
      v10);
  }
  MbbNdisIndicatePacketService(a1, a2, v10);
  return 0;
}

```

## disassembly

```asm
0x140028340  mov     [rsp+arg_10], r8d
0x140028345  push    rbx
0x140028346  push    rbp
0x140028347  push    rsi
0x140028348  push    rdi
0x140028349  push    r12
0x14002834b  push    r13
0x14002834d  push    r14
0x14002834f  push    r15
0x140028351  sub     rsp, 58h
0x140028355  mov     rax, [rcx+30h]
0x140028359  mov     rdi, rcx
0x14002835c  mov     ecx, r8d
0x14002835f  mov     r15, r9
0x140028362  mov     ebp, r8d
0x140028365  mov     ebx, edx
0x140028367  mov     r13, [rax]
0x14002836a  mov     [rsp+98h+arg_18], r13
0x140028372  call    ?MbbUtilMbbToWwanStatus@@YAKW4_MBB_STATUS@@@Z; MbbUtilMbbToWwanStatus(_MBB_STATUS)
0x140028377  lea     rcx, WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids
0x14002837e  mov     r12d, eax
0x140028381  mov     edx, 3
0x140028386  test    ebx, ebx
0x140028388  jz      short loc_1400283CC
0x14002838a  lea     rsi, WPP_RECORDER_INITIALIZED
0x140028391  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140028398  jz      loc_14002873A
0x14002839e  mov     eax, [rdi+10h]
0x1400283a1  lea     r9d, [rdx+5Ah]
0x1400283a5  mov     dword ptr [rsp+98h+var_68], ebx
0x1400283a9  mov     r8d, edx
0x1400283ac  mov     [rsp+98h+var_70], eax
0x1400283b0  mov     dl, 2
0x1400283b2  mov     [rsp+98h+var_78], rcx
0x1400283b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400283be  mov     rcx, [rcx+40h]
0x1400283c2  call    WPP_RECORDER_SF_DD
0x1400283c7  jmp     loc_14002873A
0x1400283cc  mov     ebp, [rsp+98h+arg_20]
0x1400283d3  mov     eax, 2Ch ; ','
0x1400283d8  test    r15, r15
0x1400283db  jz      loc_1400286EF
0x1400283e1  cmp     ebp, eax
0x1400283e3  jb      loc_1400286EF
0x1400283e9  mov     r8d, 6458424Dh
0x1400283ef  lea     ecx, [rax+14h]
0x1400283f2  mov     edx, eax
0x1400283f4  call    cs:__imp_ExAllocatePool2
0x1400283fb  nop     dword ptr [rax+rax+00h]
0x140028400  mov     r14, rax
0x140028403  test    rax, rax
0x140028406  jnz     short loc_14002844F
0x140028408  lea     rsi, WPP_RECORDER_INITIALIZED
0x14002840f  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140028416  jz      short loc_140028445
0x140028418  mov     rcx, cs:WPP_GLOBAL_Control
0x14002841f  lea     r9d, [rax+5Fh]
0x140028423  mov     eax, [rdi+10h]
0x140028426  lea     r8d, [r14+3]
0x14002842a  mov     [rsp+98h+var_70], eax
0x14002842e  mov     dl, 2
0x140028430  lea     rax, WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids
0x140028437  mov     rcx, [rcx+40h]
0x14002843b  mov     [rsp+98h+var_78], rax
0x140028440  call    WPP_RECORDER_SF_d
0x140028445  mov     ebx, 0C000009Ah
0x14002844a  jmp     loc_140028733
0x14002844f  mov     qword ptr [rax+4], 0
0x140028457  lea     rsi, WPP_RECORDER_INITIALIZED
0x14002845e  mov     qword ptr [rax+0Ch], 0
0x140028466  mov     dword ptr [rax], 2C0380h
0x14002846c  mov     eax, [r15+8]
0x140028470  mov     [r14+14h], eax
0x140028474  mov     eax, [r15+1Ch]
0x140028478  mov     [r14+18h], eax
0x14002847c  mov     eax, [r15+20h]
0x140028480  mov     [r14+1Ch], eax
0x140028484  movzx   eax, word ptr [r15+24h]
0x140028489  mov     [r14+20h], ax
0x14002848e  movzx   eax, word ptr [r15+26h]
0x140028493  mov     [r14+22h], ax
0x140028498  mov     eax, [r15+28h]
0x14002849c  mov     [r14+24h], eax
0x1400284a0  mov     eax, 400h
0x1400284a5  mov     dword ptr [r14+28h], 0FFFFFFFFh
0x1400284ad  cmp     [r13+52h], ax
0x1400284b2  jb      loc_14002868D
0x1400284b8  lea     rax, [r15+2Ch]
0x1400284bc  mov     [rsp+98h+arg_8], 0
0x1400284c7  mov     [rsp+98h+var_58], rax
0x1400284cc  xor     r13d, r13d
0x1400284cf  lea     eax, [rbp-2Ch]
0x1400284d2  mov     dword ptr [rsp+98h+arg_0], eax
0x1400284d9  test    eax, eax
0x1400284db  jz      loc_140028685
0x1400284e1  xor     r9d, r9d; enum mbbcx_p::MbbTlvError *
0x1400284e4  lea     r8, [rsp+98h+arg_8]; unsigned int *
0x1400284ec  lea     rdx, [rsp+98h+arg_0]; unsigned __int8 **
0x1400284f4  lea     rcx, [rsp+98h+var_58]; this
0x1400284f9  call    ?ExtractValidateNextTlv@mbbcx_p@@YAPEAU_MBB_TLV_IE@@AEAPEAEAEAKAEAW4MbbTlvError@1@G@Z; mbbcx_p::ExtractValidateNextTlv(uchar * &,ulong &,mbbcx_p::MbbTlvError &,ushort)
0x1400284fe  mov     rbp, rax
0x140028501  test    rax, rax
0x140028504  jz      loc_14002863B
0x14002850a  movzx   eax, word ptr [rax]
0x14002850d  cmp     eax, 13h
0x140028510  jnz     short loc_14002857A
0x140028512  test    r13, r13
0x140028515  jnz     loc_140028601
0x14002851b  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140028522  lea     r13, WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids
0x140028529  jz      short loc_140028551
0x14002852b  mov     rcx, cs:WPP_GLOBAL_Control
0x140028532  lea     r9d, [rax+4Fh]
0x140028536  mov     eax, [rdi+10h]
0x140028539  lea     r8d, [r9-59h]
0x14002853d  mov     [rsp+98h+var_70], eax
0x140028541  mov     dl, 4
0x140028543  mov     [rsp+98h+var_78], r13
0x140028548  mov     rcx, [rcx+40h]
0x14002854c  call    WPP_RECORDER_SF_d
0x140028551  mov     eax, [rbp+4]
0x140028554  test    eax, eax
0x140028556  jz      short loc_1400285D7
0x140028558  cmp     eax, 4
0x14002855b  ja      short loc_1400285D0
0x14002855d  cmp     byte ptr [rbp+3], 0
0x140028561  jnz     short loc_1400285C9
0x140028563  mov     eax, [rbp+8]
0x140028566  mov     r13, rbp
0x140028569  mov     [r14+28h], eax
0x14002856d  mov     [rsp+98h+arg_8], 0
0x140028578  jmp     short loc_1400285B6
0x14002857a  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140028581  jz      short loc_1400285B6
0x140028583  mov     rcx, cs:WPP_GLOBAL_Control
0x14002858a  mov     r9d, 64h ; 'd'
0x140028590  mov     dword ptr [rsp+98h+var_68], eax
0x140028594  mov     dl, 3
0x140028596  mov     eax, [rdi+10h]
0x140028599  mov     [rsp+98h+var_70], eax
0x14002859d  lea     rax, WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids
0x1400285a4  mov     rcx, [rcx+40h]
0x1400285a8  lea     r8d, [r9-5Bh]
0x1400285ac  mov     [rsp+98h+var_78], rax
0x1400285b1  call    WPP_RECORDER_SF_DD
0x1400285b6  cmp     dword ptr [rsp+98h+arg_0], 0
0x1400285be  jnz     loc_1400284E1
0x1400285c4  jmp     loc_140028685
0x1400285c9  mov     eax, 4
0x1400285ce  jmp     short loc_1400285DC
0x1400285d0  mov     eax, 7
0x1400285d5  jmp     short loc_1400285DC
0x1400285d7  mov     eax, 0Fh
0x1400285dc  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1400285e3  jz      loc_140028680
0x1400285e9  mov     dword ptr [rsp+98h+var_68], eax
0x1400285ed  mov     r9d, 63h ; 'c'
0x1400285f3  mov     eax, [rdi+10h]
0x1400285f6  mov     [rsp+98h+var_70], eax
0x1400285fa  mov     [rsp+98h+var_78], r13
0x1400285ff  jmp     short loc_140028668
0x140028601  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140028608  jz      short loc_140028680
0x14002860a  mov     eax, [rdi+10h]
0x14002860d  mov     r9d, 61h ; 'a'
0x140028613  mov     rcx, cs:WPP_GLOBAL_Control
0x14002861a  mov     dl, 2
0x14002861c  mov     [rsp+98h+var_70], eax
0x140028620  lea     rax, WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids
0x140028627  mov     [rsp+98h+var_78], rax
0x14002862c  lea     r8d, [r9-58h]
0x140028630  mov     rcx, [rcx+40h]
0x140028634  call    WPP_RECORDER_SF_d
0x140028639  jmp     short loc_140028680
0x14002863b  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140028642  jz      short loc_140028680
0x140028644  mov     eax, [rsp+98h+arg_8]
0x14002864b  mov     r9d, 60h ; '`'
0x140028651  mov     dword ptr [rsp+98h+var_68], eax
0x140028655  mov     eax, [rdi+10h]
0x140028658  mov     [rsp+98h+var_70], eax
0x14002865c  lea     rax, WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids
0x140028663  mov     [rsp+98h+var_78], rax
0x140028668  mov     rcx, cs:WPP_GLOBAL_Control
0x14002866f  mov     r8d, 9
0x140028675  mov     dl, 2
0x140028677  mov     rcx, [rcx+40h]
0x14002867b  call    WPP_RECORDER_SF_DD
0x140028680  mov     ebx, 0C0010015h
0x140028685  mov     r13, [rsp+98h+arg_18]
0x14002868d  mov     dword ptr [rdi+2DCh], 2Ch ; ','
0x140028697  mov     [rdi+2E0h], r14
0x14002869e  mov     eax, [r15]
0x1400286a1  mov     [r14+8], eax
0x1400286a5  mov     [r14+4], r12d
0x1400286a9  test    r12d, r12d
0x1400286ac  jnz     short loc_1400286E9
0x1400286ae  mov     eax, [r15+4]
0x1400286b2  mov     [r14+0Ch], eax
0x1400286b6  mov     rax, [r15+0Ch]
0x1400286ba  mov     [r13+420h], rax
0x1400286c1  mov     rax, [r15+14h]
0x1400286c5  mov     [r13+428h], rax
0x1400286cc  cmp     [r13+430h], r12b
0x1400286d3  jz      short loc_1400286E9
0x1400286d5  or      dword ptr [rdi+2D8h], 1
0x1400286dc  mov     eax, [r13+434h]
0x1400286e3  mov     [rdi+2E8h], eax
0x1400286e9  test    ebx, ebx
0x1400286eb  jz      short loc_140028749
0x1400286ed  jmp     short loc_140028733
0x1400286ef  lea     rsi, WPP_RECORDER_INITIALIZED
0x1400286f6  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1400286fd  jz      short loc_14002872E
0x1400286ff  mov     [rsp+98h+var_60], eax
0x140028703  mov     r8d, edx
0x140028706  mov     eax, [rdi+10h]
0x140028709  mov     r9d, 5Eh ; '^'
0x14002870f  mov     dword ptr [rsp+98h+var_68], ebp
0x140028713  mov     dl, 2
0x140028715  mov     [rsp+98h+var_70], eax
0x140028719  mov     [rsp+98h+var_78], rcx
0x14002871e  mov     rcx, cs:WPP_GLOBAL_Control
0x140028725  mov     rcx, [rcx+40h]
0x140028729  call    WPP_RECORDER_SF_Ddd
0x14002872e  mov     ebx, 0C0010015h
0x140028733  mov     ebp, [rsp+98h+arg_10]
0x14002873a  test    r12d, r12d
0x14002873d  jz      short loc_140028749
0x14002873f  mov     ecx, ebp
0x140028741  call    ?MbbUtilMbbToWwanStatus@@YAKW4_MBB_STATUS@@@Z; MbbUtilMbbToWwanStatus(_MBB_STATUS)
0x140028746  mov     r12d, eax
0x140028749  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140028750  jz      short loc_140028786
0x140028752  mov     eax, [rdi+10h]
0x140028755  mov     r9d, 65h ; 'e'
0x14002875b  mov     rcx, cs:WPP_GLOBAL_Control
0x140028762  mov     dl, 4
0x140028764  mov     dword ptr [rsp+98h+var_68], r12d
0x140028769  mov     [rsp+98h+var_70], eax
0x14002876d  lea     rax, WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids
0x140028774  lea     r8d, [r9-62h]
0x140028778  mov     [rsp+98h+var_78], rax
0x14002877d  mov     rcx, [rcx+40h]
0x140028781  call    WPP_RECORDER_SF_DD
0x140028786  mov     r8d, r12d; unsigned int
0x140028789  mov     edx, ebx; int
0x14002878b  mov     rcx, rdi; struct _MBB_REQUEST_CONTEXT *
0x14002878e  call    ?MbbNdisIndicatePacketService@@YAXPEAU_MBB_REQUEST_CONTEXT@@HK@Z; MbbNdisIndicatePacketService(_MBB_REQUEST_CONTEXT *,int,ulong)
0x140028793  xor     eax, eax
0x140028795  add     rsp, 58h
0x140028799  pop     r15
0x14002879b  pop     r14
0x14002879d  pop     r13
0x14002879f  pop     r12
0x1400287a1  pop     rdi
0x1400287a2  pop     rsi
0x1400287a3  pop     rbp
0x1400287a4  pop     rbx
0x1400287a5  retn
```
