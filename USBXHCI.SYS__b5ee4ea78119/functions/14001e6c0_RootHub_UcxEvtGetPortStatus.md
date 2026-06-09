# RootHub_UcxEvtGetPortStatus

- ea: `0x14001e6c0`
- end: `0x14001f32c`
- name: `RootHub_UcxEvtGetPortStatus`
- size: `3180`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `loader_planting`

## callees

- `0x140002568`
- `0x140019d6c`
- `0x14001ac48`
- `0x14001ad0c`
- `0x14001d02c`
- `0x14001d154`
- `0x14001e6c0`
- `0x14001f830`
- `0x14003b7d0`
- `0x140046070`
- `0x14004b624`
- `0x140059970`
- `0x1400599b0`

## import_xrefs

- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x14001ece1`
- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x14001ece1`
- `ntoskrnl!KeGetCurrentIrql` at `0x14001ecc0`
- `ntoskrnl!KeGetCurrentIrql` at `0x14001ecc0`

## string_xrefs

- `0x14001f000`: `Code Path Requires Passive Level`

## pseudocode

```c
__int64 __fastcall RootHub_UcxEvtGetPortStatus(__int64 a1, __int64 a2)
{
  __int64 v3; // r14
  __int64 v4; // rcx
  __int64 v5; // rbx
  __int16 v6; // ax
  int v7; // edx
  __int64 v8; // r15
  __int64 v9; // rdi
  char v10; // cl
  int v11; // edx
  int v12; // ecx
  unsigned int v13; // r9d
  unsigned int v14; // ebp
  __int64 v15; // r15
  __int64 v16; // r13
  __int64 v17; // rdx
  unsigned int Ulong; // ebx
  char v19; // cl
  unsigned int v20; // esi
  int v21; // eax
  unsigned __int16 *v23; // r9
  __int16 v24; // cx
  int v25; // r15d
  unsigned int v26; // edx
  __int16 v27; // ax
  __int16 v28; // cx
  unsigned __int16 v29; // r8
  int v30; // eax
  __int16 v31; // cx
  __int16 v32; // dx
  __int16 v33; // dx
  __int16 v34; // ax
  unsigned __int16 v35; // cx
  __int64 v36; // rdx
  int v37; // edx
  __int16 v38; // cx
  __int16 v39; // ax
  __int16 v40; // cx
  int v41; // edx
  __int16 v42; // cx
  __int16 v43; // ax
  int v44; // edx
  __int16 v45; // cx
  __int16 v46; // ax
  __int16 v47; // cx
  __int16 v48; // ax
  __int16 v49; // cx
  __int16 v50; // ax
  unsigned int v51; // eax
  int v52; // edx
  unsigned int v53; // ecx
  int v54; // eax
  int v55; // edx
  int v56; // r8d
  int v57; // r9d
  unsigned __int16 v58; // cx
  __int16 v59; // dx
  char v60; // al
  int v61; // edx
  int v62; // edx
  int v63; // edx
  int v64; // r9d
  int v65; // edx
  char v66; // [rsp+28h] [rbp-C0h]
  unsigned __int16 *v67; // [rsp+70h] [rbp-78h]
  __int64 v68; // [rsp+70h] [rbp-78h]
  __int64 v69; // [rsp+78h] [rbp-70h]
  __int128 v70; // [rsp+80h] [rbp-68h] BYREF
  __int128 v71; // [rsp+90h] [rbp-58h]
  __int64 v72; // [rsp+A0h] [rbp-48h]

  v72 = 0;
  v70 = 0;
  v71 = 0;
  v3 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01033 + 1616))(
         WdfDriverGlobals,
         a1,
         off_14006C130);
  v4 = *(_QWORD *)(v3 + 8);
  v5 = *(_QWORD *)(v4 + 88);
  v69 = v5;
  if ( *(_BYTE *)(v4 + 1041) && KeGetCurrentIrql() )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_sds(WPP_GLOBAL_Control->DeviceExtension, v55, v56, v57);
    if ( !KdRefreshDebuggerNotPresent() )
      __debugbreak();
  }
  v70 = 0;
  v72 = 0;
  v71 = 0;
  if ( WdfClientVersionHigherThanFramework )
  {
    if ( (unsigned int)WdfStructureCount > 0x33 )
    {
      LOWORD(v70) = *(_WORD *)(WdfStructures + 408);
      goto LABEL_5;
    }
    v6 = -1;
  }
  else
  {
    v6 = 40;
  }
  LOWORD(v70) = v6;
LABEL_5:
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int128 *))(WdfFunctions_01033 + 2128))(
    WdfDriverGlobals,
    a2,
    &v70);
  v8 = *(_QWORD *)(v3 + 8);
  v9 = *((_QWORD *)&v70 + 1);
  v10 = *(_BYTE *)(*(_QWORD *)(v8 + 88) + 16LL);
  if ( !v10 || *(_BYTE *)(v8 + 797) )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v7) = 2;
      WPP_RECORDER_SF_DD(
        *(_QWORD *)(v8 + 72),
        v7,
        4,
        254,
        (__int64)WPP_fc7190ad091936951f4a59c8b46d7948_Traceguids,
        v10,
        *(_BYTE *)(v8 + 797));
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v65) = 2;
        WPP_RECORDER_SF_(
          *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
          v65,
          11,
          108,
          (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids);
      }
    }
    goto LABEL_99;
  }
  v11 = *(unsigned __int16 *)(*((_QWORD *)&v70 + 1) + 130LL);
  v12 = 8;
  v13 = *(unsigned __int16 *)(*((_QWORD *)&v70 + 1) + 132LL);
  if ( v11 != 2 )
    v12 = 4;
  if ( *(_WORD *)(*((_QWORD *)&v70 + 1) + 128LL) != 163
    || (v11 & 0xFFFD) != 0
    || (v14 = *(unsigned __int16 *)(*((_QWORD *)&v70 + 1) + 132LL), !*(_WORD *)(*((_QWORD *)&v70 + 1) + 132LL))
    || v13 > *(_DWORD *)(v3 + 16)
    || *(unsigned __int16 *)(*((_QWORD *)&v70 + 1) + 134LL) != v12 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      WPP_RECORDER_SF_DDDDDDDD(*(_QWORD *)(v8 + 72), v11, (unsigned __int8)v13, 109);
      v21 = -1073741820;
      v20 = -1073741823;
      goto LABEL_19;
    }
    goto LABEL_18;
  }
  v15 = 16LL * (v13 - 1);
  v16 = 120LL * (v13 - 1);
  Ulong = XilRegister_ReadUlong(v5, v15 + *(_QWORD *)(v3 + 40));
  v19 = *(_BYTE *)(*(_QWORD *)(v3 + 48) + v16 + 13);
  if ( v19 != 2 )
  {
    if ( v19 != 3 )
      goto LABEL_16;
    if ( Ulong != -1 )
    {
      v20 = 0;
      v68 = *(_QWORD *)(v9 + 40);
      *(_DWORD *)v68 = 0;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v17) = 4;
        WPP_RECORDER_SF_dD(
          *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
          v17,
          11,
          117,
          (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids,
          v14,
          Ulong);
      }
      if ( (unsigned __int8)RootHub_HideInvalidDebugPortStatusAndChange(v3, v14) )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v37) = 4;
          WPP_RECORDER_SF_d(
            *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
            v37,
            11,
            118,
            (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids,
            v14);
        }
        v58 = *(_WORD *)v68 & 0xFC04 | 0x2A0;
        *(_WORD *)(v68 + 2) &= 0xFF06u;
        v59 = *(_WORD *)(v68 + 2);
        *(_WORD *)v68 = v58;
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          v60 = v59;
          v61 = v58;
          LOBYTE(v61) = 4;
          WPP_RECORDER_SF_DD(
            *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
            v61,
            11,
            119,
            (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids,
            v58,
            v60);
        }
      }
      else
      {
        HIWORD(v41) = HIWORD(Ulong);
        v38 = *(_WORD *)v68 ^ ((unsigned __int8)*(_WORD *)v68 ^ (unsigned __int8)Ulong) & 1;
        v39 = v38 ^ ((unsigned __int8)v38 ^ (unsigned __int8)(2 * (Ulong >> 1))) & 2;
        v40 = v39 ^ ((unsigned __int8)v39 ^ Ulong & 0xF8) & 8;
        LOWORD(v41) = v40 ^ ((unsigned __int8)v40 ^ Ulong & 0xF0) & 0x10;
        v42 = v41 ^ (v41 ^ (32 * (Ulong >> 5))) & 0x1E0;
        *(_WORD *)v68 = v42;
        if ( ((Ulong >> 5) & 0xF) == 0xF )
        {
          v42 = v42 & 0xFE1F | 0x100;
          *(_WORD *)v68 = v42;
        }
        if ( (Ulong & 0x1000000) != 0 )
        {
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v41) = 4;
            WPP_RECORDER_SF_(
              *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
              v41,
              11,
              120,
              (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids);
          }
          v42 = *(_WORD *)v68 & 0xFE1F | 0x140;
        }
        v43 = *(_WORD *)(v68 + 2);
        LOWORD(v44) = v42 ^ (v42 ^ Ulong & 0xFE00) & 0x200;
        *(_WORD *)v68 = v44;
        v45 = v43 ^ ((unsigned __int8)v43 ^ (unsigned __int8)(Ulong >> 17)) & 1;
        v46 = v45 ^ ((unsigned __int8)v45 ^ (unsigned __int8)(8 * (Ulong >> 20))) & 8;
        v47 = v46 ^ ((unsigned __int8)v46 ^ (unsigned __int8)(16 * (Ulong >> 21))) & 0x10;
        v48 = v47 ^ ((unsigned __int8)v47 ^ (unsigned __int8)(32 * (Ulong >> 19))) & 0x20;
        v49 = v48 ^ ((unsigned __int8)v48 ^ (unsigned __int8)((unsigned __int8)(Ulong >> 22) << 6)) & 0x40;
        v50 = v49 ^ (v49 ^ (Ulong >> 23 << 7)) & 0x80;
        *(_WORD *)(v68 + 2) = v50;
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          v44 = (unsigned __int16)v44;
          v66 = v44;
          LOBYTE(v44) = 4;
          WPP_RECORDER_SF_DD(
            *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
            v44,
            11,
            121,
            (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids,
            v66,
            v50);
        }
        if ( *(_DWORD *)(*(_QWORD *)(v3 + 48) + v16 + 108) && (Ulong & 0x1E0) == 0xC0 && (Ulong & 0x400000) != 0 )
          *(_WORD *)(v68 + 2) |= 0x80u;
        if ( *(_WORD *)(v9 + 130) == 2 )
        {
          v51 = XilRegister_ReadUlong(v69, v15 + *(_QWORD *)(v3 + 40) + 8LL);
          *(_DWORD *)(v68 + 4) = 0;
          if ( *(_WORD *)(*(_QWORD *)(v3 + 48) + v16 + 54) || (v52 = 1024, (Ulong & 0x3C00) != 0x400) )
            v53 = (Ulong & 0x3C00 | (Ulong >> 4) & 0x3C0) >> 6;
          else
            v53 = 68;
          v54 = v53 | (v51 >> 8) & 0xFF00;
          *(_DWORD *)(v68 + 4) = v54;
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v52) = 4;
            WPP_RECORDER_SF_D(
              *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
              v52,
              11,
              122,
              (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids,
              v54);
          }
        }
      }
      goto LABEL_41;
    }
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_82;
    v64 = 116;
    goto LABEL_81;
  }
  if ( *(_WORD *)(v9 + 130) )
  {
LABEL_16:
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_DDDDDDDD(
        *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
        *(unsigned __int8 *)(v9 + 134),
        *(unsigned __int8 *)(v9 + 133),
        123);
LABEL_18:
    v20 = -1073741823;
    v21 = -1073741820;
    goto LABEL_19;
  }
  if ( Ulong == -1 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
LABEL_82:
      LOBYTE(v17) = 1;
      Controller_SetControllerGone(*(_QWORD *)(v3 + 8), v17);
LABEL_99:
      v20 = -1073741810;
      v21 = -1073713152;
      goto LABEL_19;
    }
    v64 = 110;
LABEL_81:
    LOBYTE(v17) = 2;
    WPP_RECORDER_SF_(
      *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
      v17,
      11,
      v64,
      (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids);
    goto LABEL_82;
  }
  v23 = *(unsigned __int16 **)(v9 + 40);
  v20 = 0;
  v67 = v23;
  *(_DWORD *)v23 = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v17) = 4;
    WPP_RECORDER_SF_dD(
      *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
      v17,
      11,
      111,
      (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids,
      v14,
      Ulong);
    v23 = v67;
  }
  v26 = Ulong >> 1;
  v24 = *v23 ^ ((unsigned __int8)*v23 ^ (unsigned __int8)Ulong) & 1;
  v25 = (Ulong >> 5) & 0xF;
  LOWORD(v26) = v24 ^ ((unsigned __int8)v24 ^ (unsigned __int8)(2 * (Ulong >> 1))) & 2;
  if ( v25 == 2 )
  {
    LOWORD(v26) = v26 | 0x20;
  }
  else
  {
    if ( ((Ulong >> 5) & 0xF) == 3 )
    {
LABEL_64:
      LOWORD(v26) = v26 | 4;
      goto LABEL_28;
    }
    if ( ((Ulong >> 5) & 0xF) != 0xB )
    {
      if ( ((Ulong >> 5) & 0xF) != 0xF )
        goto LABEL_28;
      goto LABEL_64;
    }
    LOWORD(v26) = v26 | 0x800;
    *v23 = v26;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v26) = 2;
      WPP_RECORDER_SF_d(
        *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
        v26,
        11,
        112,
        (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids,
        v14);
      v23 = v67;
      LOWORD(v26) = *v67;
    }
  }
LABEL_28:
  v27 = v26 ^ ((unsigned __int8)v26 ^ Ulong & 0xF8) & 8;
  v28 = v27 ^ ((unsigned __int8)v27 ^ Ulong & 0xF0) & 0x10;
  v29 = v28 ^ (v28 ^ ((unsigned __int16)(Ulong >> 9) << 8)) & 0x100;
  v30 = Ulong & 0x3C00;
  *v23 = v29;
  if ( v30 == 2048 )
  {
    v29 |= 0x200u;
  }
  else
  {
    if ( v30 != 3072 )
      goto LABEL_33;
    v29 |= 0x400u;
  }
  *v23 = v29;
LABEL_33:
  if ( (Ulong & 0xC000) != 0 )
  {
    v29 |= 0x1000u;
    *v23 = v29;
  }
  v31 = v23[1] ^ ((unsigned __int8)v23[1] ^ (unsigned __int8)(Ulong >> 17)) & 1;
  v32 = v31 ^ ((unsigned __int8)v31 ^ (unsigned __int8)(2 * (Ulong >> 18))) & 2;
  if ( v25 == 15 )
    v33 = v32 & 0xFFFB;
  else
    v33 = ((unsigned __int8)v32 ^ (unsigned __int8)(4 * (Ulong >> 22))) & 4 ^ v32;
  v34 = v33 ^ ((unsigned __int8)v33 ^ (unsigned __int8)(8 * (Ulong >> 20))) & 8;
  v35 = v34 ^ ((unsigned __int8)v34 ^ (unsigned __int8)(16 * (Ulong >> 21))) & 0x10;
  v23[1] = v35;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v62 = v29;
    LOBYTE(v62) = 4;
    WPP_RECORDER_SF_DD(
      *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
      v62,
      11,
      113,
      (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids,
      v29,
      v35);
  }
  v36 = v16 + *(_QWORD *)(v3 + 48);
  if ( v25 == 15 )
  {
    _InterlockedOr((volatile signed __int32 *)(v36 + 64), 1u);
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, __int64))(WdfFunctions_01033 + 2552))(
      WdfDriverGlobals,
      *(_QWORD *)(*(_QWORD *)(v3 + 48) + v16 + 80),
      -100000000);
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, __int64))(WdfFunctions_01033 + 2552))(
      WdfDriverGlobals,
      *(_QWORD *)(*(_QWORD *)(v3 + 48) + v16 + 72),
      -10000000);
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v63) = 4;
      WPP_RECORDER_SF_dD(
        *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
        v63,
        11,
        114,
        (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids,
        v14,
        Ulong);
    }
    v21 = 1;
  }
  else
  {
    _m_prefetchw((const void *)(v36 + 64));
    if ( (_InterlockedAnd((volatile signed __int32 *)(v36 + 64), 0xFFFFFFFE) & 1) == 0 )
    {
LABEL_41:
      v21 = 0;
      goto LABEL_19;
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v36) = 4;
      WPP_RECORDER_SF_dD(
        *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
        v36,
        11,
        115,
        (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids,
        v14,
        Ulong);
    }
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, _QWORD))(WdfFunctions_01033 + 2560))(
      WdfDriverGlobals,
      *(_QWORD *)(*(_QWORD *)(v3 + 48) + v16 + 80),
      0);
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, _QWORD))(WdfFunctions_01033 + 2560))(
      WdfDriverGlobals,
      *(_QWORD *)(*(_QWORD *)(v3 + 48) + v16 + 72),
      0);
    v21 = 0;
  }
LABEL_19:
  *(_DWORD *)(v9 + 4) = v21;
  return (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD))(WdfFunctions_01033 + 2104))(
           WdfDriverGlobals,
           a2,
           v20);
}

```

## disassembly

```asm
0x14001e6c0  mov     r11, rsp
0x14001e6c3  push    rbx
0x14001e6c4  push    rsi
0x14001e6c5  push    rdi
0x14001e6c6  push    r12
0x14001e6c8  push    r14
0x14001e6ca  push    r15
0x14001e6cc  sub     rsp, 0B8h
0x14001e6d3  mov     rax, cs:__security_cookie
0x14001e6da  xor     rax, rsp
0x14001e6dd  mov     [rsp+0E8h+var_40], rax
0x14001e6e5  mov     r8, cs:off_14006C130
0x14001e6ec  xor     eax, eax
0x14001e6ee  mov     [r11-48h], rax
0x14001e6f2  xorps   xmm0, xmm0
0x14001e6f5  mov     rax, cs:WdfFunctions_01033
0x14001e6fc  mov     r12, rdx
0x14001e6ff  movups  xmmword ptr [r11-68h], xmm0
0x14001e704  mov     rdx, rcx
0x14001e707  mov     rcx, cs:WdfDriverGlobals
0x14001e70e  movups  xmmword ptr [r11-58h], xmm0
0x14001e713  mov     rax, [rax+650h]
0x14001e71a  call    _guard_dispatch_icall
0x14001e71f  mov     r14, rax
0x14001e722  lea     rsi, WPP_RECORDER_INITIALIZED
0x14001e729  mov     rcx, [rax+8]
0x14001e72d  cmp     byte ptr [rcx+411h], 0
0x14001e734  mov     rbx, [rcx+58h]
0x14001e738  mov     [rsp+0E8h+var_70], rbx
0x14001e73d  jnz     loc_14001ECC0
0x14001e743  xor     eax, eax
0x14001e745  xorps   xmm0, xmm0
0x14001e748  cmp     cs:WdfClientVersionHigherThanFramework, al
0x14001e74e  movups  [rsp+0E8h+var_68], xmm0
0x14001e756  mov     [rsp+0E8h+var_48], rax
0x14001e75e  movups  [rsp+0E8h+var_58], xmm0
0x14001e766  jnz     loc_14001F02E
0x14001e76c  mov     eax, 28h ; '('
0x14001e771  mov     word ptr [rsp+0E8h+var_68], ax
0x14001e779  mov     rax, cs:WdfFunctions_01033
0x14001e780  lea     r8, [rsp+0E8h+var_68]
0x14001e788  mov     rcx, cs:WdfDriverGlobals
0x14001e78f  mov     rdx, r12
0x14001e792  mov     [rsp+0E8h+arg_10], rbp
0x14001e79a  mov     [rsp+0E8h+var_38], r13
0x14001e7a2  mov     rax, [rax+850h]
0x14001e7a9  call    _guard_dispatch_icall
0x14001e7ae  mov     r15, [r14+8]
0x14001e7b2  mov     rdi, qword ptr [rsp+0E8h+var_68+8]
0x14001e7ba  mov     rax, [r15+58h]
0x14001e7be  movzx   ecx, byte ptr [rax+10h]
0x14001e7c2  test    cl, cl
0x14001e7c4  jz      loc_14001F2B1
0x14001e7ca  cmp     byte ptr [r15+31Dh], 0
0x14001e7d2  jnz     loc_14001F2B1
0x14001e7d8  movzx   edx, word ptr [rdi+82h]
0x14001e7df  mov     ecx, 8
0x14001e7e4  movzx   r13d, byte ptr [rdi+80h]
0x14001e7ec  cmp     edx, 2
0x14001e7ef  movzx   r9d, word ptr [rdi+84h]
0x14001e7f7  mov     r8d, 4
0x14001e7fd  cmovnz  ecx, r8d
0x14001e801  cmp     r13b, 0A3h
0x14001e805  jnz     loc_14001ECFB
0x14001e80b  cmp     byte ptr [rdi+81h], 0
0x14001e812  jnz     loc_14001ECFB
0x14001e818  mov     eax, 0FFFDh
0x14001e81d  test    ax, dx
0x14001e820  jnz     loc_14001ECFB
0x14001e826  mov     ebp, r9d
0x14001e829  test    r9d, r9d
0x14001e82c  jz      loc_14001ECFB
0x14001e832  cmp     r9d, [r14+10h]
0x14001e836  ja      loc_14001ECFB
0x14001e83c  movzx   eax, word ptr [rdi+86h]
0x14001e843  cmp     eax, ecx
0x14001e845  jnz     loc_14001ECFB
0x14001e84b  mov     rdx, [r14+28h]
0x14001e84f  lea     eax, [r9-1]
0x14001e853  mov     r15d, eax
0x14001e856  mov     rcx, rbx
0x14001e859  shl     r15, 4
0x14001e85d  add     rdx, r15
0x14001e860  mov     esi, eax
0x14001e862  call    XilRegister_ReadUlong
0x14001e867  imul    r13, rsi, 78h ; 'x'
0x14001e86b  mov     ebx, eax
0x14001e86d  mov     rax, [r14+30h]
0x14001e871  movzx   ecx, byte ptr [rax+r13+0Dh]
0x14001e877  cmp     cl, 2
0x14001e87a  jz      short loc_14001E8F8
0x14001e87c  cmp     cl, 3
0x14001e87f  jz      loc_14001EAAB
0x14001e885  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14001e88c  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001e893  jnz     loc_14001F23B
0x14001e899  mov     esi, 0C0000001h
0x14001e89e  mov     eax, 0C0000004h
0x14001e8a3  mov     [rdi+4], eax
0x14001e8a6  mov     r8d, esi
0x14001e8a9  mov     rax, cs:WdfFunctions_01033
0x14001e8b0  mov     rdx, r12
0x14001e8b3  mov     rcx, cs:WdfDriverGlobals
0x14001e8ba  mov     rax, [rax+838h]
0x14001e8c1  call    _guard_dispatch_icall
0x14001e8c6  mov     r13, [rsp+0E8h+var_38]
0x14001e8ce  mov     rbp, [rsp+0E8h+arg_10]
0x14001e8d6  mov     rcx, [rsp+0E8h+var_40]
0x14001e8de  xor     rcx, rsp; StackCookie
0x14001e8e1  call    __security_check_cookie
0x14001e8e6  add     rsp, 0B8h
0x14001e8ed  pop     r15
0x14001e8ef  pop     r14
0x14001e8f1  pop     r12
0x14001e8f3  pop     rdi
0x14001e8f4  pop     rsi
0x14001e8f5  pop     rbx
0x14001e8f6  retn
0x14001e8f8  cmp     word ptr [rdi+82h], 0
0x14001e900  jnz     short loc_14001E885
0x14001e902  cmp     ebx, 0FFFFFFFFh
0x14001e905  jz      loc_14001F05C
0x14001e90b  mov     r9, [rdi+28h]
0x14001e90f  xor     esi, esi
0x14001e911  mov     [rsp+0E8h+var_78], r9
0x14001e916  mov     [r9], esi
0x14001e919  lea     r11, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14001e920  cmp     cs:WPP_RECORDER_INITIALIZED, r11
0x14001e927  lea     r10, WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids
0x14001e92e  jnz     loc_14001EE97
0x14001e934  movzx   eax, word ptr [r9]
0x14001e938  movzx   ecx, bx
0x14001e93b  xor     cx, ax
0x14001e93e  mov     edx, ebx
0x14001e940  shr     edx, 1
0x14001e942  and     cx, 1
0x14001e946  xor     cx, ax
0x14001e949  add     dx, dx
0x14001e94c  xor     dx, cx
0x14001e94f  mov     r15d, ebx
0x14001e952  shr     r15d, 5
0x14001e956  and     dx, 2
0x14001e95a  and     r15d, 0Fh
0x14001e95e  xor     dx, cx
0x14001e961  mov     eax, r15d
0x14001e964  sub     eax, 2
0x14001e967  jz      loc_14001F101
0x14001e96d  sub     eax, 1
0x14001e970  jz      loc_14001ED74
0x14001e976  sub     eax, 8
0x14001e979  jz      loc_14001F0AB
0x14001e97f  cmp     eax, 4
0x14001e982  jz      loc_14001ED74
0x14001e988  mov     eax, ebx
0x14001e98a  mov     ecx, ebx
0x14001e98c  and     ax, 0FFF8h
0x14001e990  and     cx, 0FFF0h
0x14001e995  xor     ax, dx
0x14001e998  mov     r8d, ebx
0x14001e99b  and     ax, 8
0x14001e99f  shr     r8d, 9
0x14001e9a3  xor     ax, dx
0x14001e9a6  shl     r8w, 8
0x14001e9ab  xor     cx, ax
0x14001e9ae  and     cx, 10h
0x14001e9b2  xor     cx, ax
0x14001e9b5  mov     eax, 100h
0x14001e9ba  xor     r8w, cx
0x14001e9be  and     r8w, ax
0x14001e9c2  mov     eax, ebx
0x14001e9c4  xor     r8w, cx
0x14001e9c8  and     eax, 3C00h
0x14001e9cd  mov     [r9], r8w
0x14001e9d1  cmp     eax, 800h
0x14001e9d6  jz      short loc_14001E9E7
0x14001e9d8  cmp     eax, 0C00h
0x14001e9dd  jnz     short loc_14001E9F1
0x14001e9df  or      r8w, 400h
0x14001e9e5  jmp     short loc_14001E9ED
0x14001e9e7  or      r8w, 200h
0x14001e9ed  mov     [r9], r8w
0x14001e9f1  test    ebx, 0C000h
0x14001e9f7  jnz     loc_14001F10A
0x14001e9fd  movzx   eax, word ptr [r9+2]
0x14001ea02  mov     ecx, ebx
0x14001ea04  shr     ecx, 11h
0x14001ea07  mov     edx, ebx
0x14001ea09  shr     edx, 12h
0x14001ea0c  xor     cx, ax
0x14001ea0f  add     dx, dx
0x14001ea12  and     cx, 1
0x14001ea16  xor     cx, ax
0x14001ea19  xor     dx, cx
0x14001ea1c  and     dx, 2
0x14001ea20  xor     dx, cx
0x14001ea23  cmp     r15d, 0Fh
0x14001ea27  jz      loc_14001EF79
0x14001ea2d  mov     eax, ebx
0x14001ea2f  shr     eax, 16h
0x14001ea32  shl     ax, 2
0x14001ea36  xor     ax, dx
0x14001ea39  and     ax, 4
0x14001ea3d  xor     dx, ax
0x14001ea40  mov     eax, ebx
0x14001ea42  mov     ecx, ebx
0x14001ea44  shr     eax, 14h
0x14001ea47  shl     ax, 3
0x14001ea4b  shr     ecx, 15h
0x14001ea4e  xor     ax, dx
0x14001ea51  shl     cx, 4
0x14001ea55  and     ax, 8
0x14001ea59  xor     ax, dx
0x14001ea5c  xor     cx, ax
0x14001ea5f  and     cx, 10h
0x14001ea63  xor     cx, ax
0x14001ea66  mov     [r9+2], cx
0x14001ea6b  cmp     cs:WPP_RECORDER_INITIALIZED, r11; __annotation("TMF:",
0x14001ea72  jnz     loc_14001EE5C
0x14001ea78  mov     rdx, [r14+30h]
0x14001ea7c  add     rdx, r13
0x14001ea7f  cmp     r15d, 0Fh
0x14001ea83  jz      loc_14001EED7
0x14001ea89  prefetchw byte ptr [rdx+40h]
0x14001ea8d  mov     eax, [rdx+40h]
0x14001ea90  mov     ecx, eax
0x14001ea92  and     ecx, 0FFFFFFFEh
0x14001ea95  lock cmpxchg [rdx+40h], ecx
0x14001ea9a  jnz     short loc_14001EA90
0x14001ea9c  test    al, 1
0x14001ea9e  jnz     loc_14001EDFC
0x14001eaa4  mov     eax, esi
0x14001eaa6  jmp     loc_14001E8A3
0x14001eaab  cmp     ebx, 0FFFFFFFFh
0x14001eaae  jz      loc_14001F14D
0x14001eab4  mov     rax, [rdi+28h]
0x14001eab8  xor     esi, esi
0x14001eaba  mov     [rsp+0E8h+var_78], rax
0x14001eabf  mov     [rax], esi
0x14001eac1  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14001eac8  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14001eacf  lea     rax, WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids
0x14001ead6  jnz     loc_14001EF86
0x14001eadc  mov     edx, ebp
0x14001eade  mov     rcx, r14
0x14001eae1  call    RootHub_HideInvalidDebugPortStatusAndChange
0x14001eae6  test    al, al
0x14001eae8  jnz     loc_14001ED7D
0x14001eaee  mov     rbp, [rsp+0E8h+var_78]
0x14001eaf3  movzx   ecx, bx
0x14001eaf6  mov     edx, ebx
0x14001eaf8  mov     r8d, 1E0h
0x14001eafe  and     dx, 0FFF0h
0x14001eb03  movzx   eax, word ptr [rbp+0]
0x14001eb07  xor     cx, ax
0x14001eb0a  and     cx, 1
0x14001eb0e  xor     cx, ax
0x14001eb11  mov     eax, ebx
0x14001eb13  shr     eax, 1
0x14001eb15  add     ax, ax
0x14001eb18  xor     ax, cx
0x14001eb1b  and     ax, 2
0x14001eb1f  xor     ax, cx
0x14001eb22  mov     ecx, ebx
0x14001eb24  and     cx, 0FFF8h
0x14001eb29  xor     cx, ax
0x14001eb2c  and     cx, 8
0x14001eb30  xor     cx, ax
0x14001eb33  mov     eax, ebx
0x14001eb35  xor     dx, cx
0x14001eb38  shr     eax, 5
0x14001eb3b  and     dx, 10h
0x14001eb3f  xor     dx, cx
0x14001eb42  movzx   ecx, ax
0x14001eb45  shl     cx, 5
0x14001eb49  and     al, 0Fh
0x14001eb4b  xor     cx, dx
0x14001eb4e  and     cx, r8w
0x14001eb52  xor     cx, dx
0x14001eb55  mov     [rbp+0], cx
0x14001eb59  cmp     al, 0Fh
0x14001eb5b  jz      loc_14001F18F
0x14001eb61  bt      ebx, 18h
0x14001eb65  jb      loc_14001F1A5
0x14001eb6b  mov     eax, 200h
0x14001eb70  mov     edx, ebx
0x14001eb72  and     dx, 0FE00h
0x14001eb77  mov     r9d, 80h
0x14001eb7d  xor     dx, cx
0x14001eb80  and     dx, ax
0x14001eb83  movzx   eax, word ptr [rbp+2]
0x14001eb87  xor     dx, cx
0x14001eb8a  mov     ecx, ebx
0x14001eb8c  shr     ecx, 11h
0x14001eb8f  xor     cx, ax
0x14001eb92  mov     [rbp+0], dx
0x14001eb96  and     cx, 1
0x14001eb9a  xor     cx, ax
0x14001eb9d  mov     eax, ebx
0x14001eb9f  shr     eax, 14h
0x14001eba2  shl     ax, 3
  ... truncated ...
```
