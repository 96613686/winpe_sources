# CBSSEntry::SetChannelAndPhyID(bool,CAdapterPropertyCache *,uint,_WDI_BAND_ID)

- ea: `0x14000e3f0`
- end: `0x14000ee87`
- name: `?SetChannelAndPhyID@CBSSEntry@@QEAAX_NPEAVCAdapterPropertyCache@@IW4_WDI_BAND_ID@@@Z`
- size: `2711`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD)`
- caller_count: `4`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x1400051e0`
- `0x14000d750`
- `0x140017590`
- `0x1400868e8`

## callees

- `0x14000393c`
- `0x140009420`
- `0x14000c778`
- `0x14000d054`
- `0x14000e3f0`
- `0x14000f830`
- `0x140024a20`
- `0x14005ab30`
- `0x1400684cc`
- `0x1400dfd40`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000ee76`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ee76`

## pseudocode

```c
void __fastcall CBSSEntry::SetChannelAndPhyID(__int64 a1, char a2, __int64 a3, unsigned int a4, int a5)
{
  int v5; // r10d
  int v7; // eax
  int v9; // r8d
  unsigned __int16 v10; // r8
  __int16 v11; // ax
  _QWORD *v12; // r14
  int v13; // edx
  int v14; // r10d
  __int64 v15; // r10
  bool v16; // cc
  int v17; // edx
  __int64 v18; // r12
  __int64 v19; // rax
  int v20; // r13d
  __int64 *i; // r12
  bool v22; // zf
  _DWORD *v23; // rax
  __int64 v24; // rcx
  _QWORD *v25; // rax
  unsigned int v26; // edx
  _QWORD *v27; // r13
  __int64 v28; // rbp
  int v29; // r10d
  __int64 v30; // rax
  __int64 v31; // rax
  int v32; // r12d
  int v33; // ecx
  char v34; // al
  int v35; // ebx
  int v36; // r8d
  unsigned __int8 *v37; // r12
  int v38; // edx
  __int64 v39; // r9
  unsigned int v40; // r8d
  int v41; // ecx
  int v42; // r9d
  void **v43; // [rsp+28h] [rbp-60h]
  char v44; // [rsp+28h] [rbp-60h]
  void *v45; // [rsp+90h] [rbp+8h] BYREF

  v5 = *(_DWORD *)(a1 + 776);
  v7 = a5;
  *(_DWORD *)(a1 + 680) = a4;
  *(_DWORD *)(a1 + 684) = v7;
  if ( v5 == a4 )
  {
    v9 = *(_DWORD *)(a1 + 780);
    if ( v9 == v7 )
    {
      if ( v5 && (v13 = *(_DWORD *)(a1 + 792)) != 0 )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
          && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
        {
          LOBYTE(v13) = 5;
          WPP_RECORDER_SF_ddddd(
            WPP_GLOBAL_Control->DeviceExtension,
            v13,
            v9,
            79,
            (__int64)WPP_3599b95ca20c3e0ba686e8b05788690d_Traceguids,
            v9,
            v5,
            *(_DWORD *)(a1 + 788),
            *(_DWORD *)(a1 + 792),
            *(_BYTE *)(a1 + 784));
        }
        *(_BYTE *)(a1 + 784) = 1;
      }
      else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        WPP_RECORDER_SF_dddd(
          WPP_GLOBAL_Control->DeviceExtension,
          2,
          v9,
          80,
          (__int64)WPP_3599b95ca20c3e0ba686e8b05788690d_Traceguids,
          v9,
          v5,
          *(_DWORD *)(a1 + 788),
          *(_DWORD *)(a1 + 792));
      }
      return;
    }
  }
  v10 = *(_WORD *)(a1 + 600);
  if ( *(_DWORD *)(a1 + 780) == 3 )
  {
    v14 = 2 - (v10 != 0);
    v12 = 0;
  }
  else
  {
    v11 = *(_WORD *)(a1 + 640);
    if ( !v10 )
    {
      if ( !v11 )
        goto LABEL_21;
      v12 = 0;
      goto LABEL_19;
    }
    v12 = 0;
    if ( !v11 )
    {
LABEL_42:
      v15 = *(_QWORD *)(a1 + 608);
      goto LABEL_20;
    }
    v14 = *(_QWORD *)(a1 + 632) > *(_QWORD *)(a1 + 672);
  }
  if ( v14 )
  {
    if ( v14 != 1 )
      goto LABEL_21;
    goto LABEL_42;
  }
LABEL_19:
  v15 = *(_QWORD *)(a1 + 648);
  v10 = *(_WORD *)(a1 + 640);
LABEL_20:
  if ( v15 && v10 )
  {
    if ( a2 )
    {
      if ( (g_Test_FeatureMask & 0x20) != 0 && a4 < 0xE )
      {
        LOBYTE(a5) = 0;
        v45 = 0;
        if ( !(unsigned int)Dot11GetInfoElementFromIEBlob(
                              (unsigned __int8 *)(v15 + 12),
                              (unsigned int)v10 - 12,
                              3,
                              0,
                              (unsigned __int8 *)&a5,
                              &v45) )
        {
          v37 = (unsigned __int8 *)v45;
          if ( v45 )
          {
            if ( (_BYTE)a5 == 1 )
            {
              v38 = *(_DWORD *)(a1 + 680);
              if ( v38 != *(unsigned __int8 *)v45 )
              {
                if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
                  && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
                {
                  LOBYTE(v38) = 5;
                  WPP_RECORDER_SF_Ld(
                    WPP_GLOBAL_Control->DeviceExtension,
                    v38,
                    v36,
                    82,
                    (__int64)WPP_3599b95ca20c3e0ba686e8b05788690d_Traceguids,
                    *(_DWORD *)(a1 + 680),
                    *(_BYTE *)v45);
                }
                *(_DWORD *)(a1 + 680) = *v37;
              }
            }
          }
        }
      }
    }
    v16 = *(_DWORD *)(a3 + 8) <= 2u;
    v17 = *(_DWORD *)(a1 + 684);
    v18 = 0;
    a5 = v17;
    if ( v16 )
    {
      v20 = -1073741811;
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_71;
      LODWORD(v43) = 2;
      LOBYTE(v17) = 2;
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        v17,
        1,
        19,
        (__int64)WPP_3ddeec0b7fee33ed2b3cc846f6231af9_Traceguids,
        v43);
      v17 = a5;
    }
    else
    {
      v19 = *(_QWORD *)(a3 + 16);
      if ( *(_BYTE *)(v19 + 120) )
      {
        v18 = v19 + 112;
      }
      else
      {
        if ( !*(_QWORD *)(v19 + 160) )
        {
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LODWORD(v43) = 2;
            LOBYTE(v17) = 4;
            WPP_RECORDER_SF_d(
              WPP_GLOBAL_Control->DeviceExtension,
              v17,
              1,
              20,
              (__int64)WPP_3ddeec0b7fee33ed2b3cc846f6231af9_Traceguids,
              v43);
            v17 = a5;
          }
          v20 = -1073741436;
          goto LABEL_30;
        }
        v18 = *(_QWORD *)(v19 + 160);
      }
      v20 = 0;
    }
LABEL_30:
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
      && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
    {
      LODWORD(v43) = v20;
      LOBYTE(v17) = 5;
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        v17,
        1,
        22,
        (__int64)WPP_3ddeec0b7fee33ed2b3cc846f6231af9_Traceguids,
        v43);
      v17 = a5;
    }
    if ( !v20 )
    {
      for ( i = *(__int64 **)(v18 + 16); ; i = (__int64 *)*i )
      {
        if ( !i )
        {
          v20 = -1073676261;
          goto LABEL_71;
        }
        v22 = *((_DWORD *)i + 2) == 0;
        v23 = 0;
        v45 = 0;
        if ( v22 )
        {
          v20 = -1073741811;
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            goto LABEL_71;
          LODWORD(v43) = 0;
          LOBYTE(v17) = 2;
          WPP_RECORDER_SF_d(
            WPP_GLOBAL_Control->DeviceExtension,
            v17,
            1,
            19,
            (__int64)WPP_3ddeec0b7fee33ed2b3cc846f6231af9_Traceguids,
            v43);
          v17 = a5;
          v23 = 0;
        }
        else
        {
          v24 = i[2];
          if ( *(_BYTE *)(v24 + 8) || (v24 = *(_QWORD *)(v24 + 48)) != 0 )
          {
            v20 = 0;
            v45 = (void *)v24;
            v23 = (_DWORD *)v24;
          }
          else
          {
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              LODWORD(v43) = 0;
              LOBYTE(v17) = 4;
              WPP_RECORDER_SF_d(
                WPP_GLOBAL_Control->DeviceExtension,
                v17,
                1,
                20,
                (__int64)WPP_3ddeec0b7fee33ed2b3cc846f6231af9_Traceguids,
                v43);
              v17 = a5;
              v23 = 0;
            }
            v20 = -1073741436;
          }
        }
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
          && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
        {
          LODWORD(v43) = v20;
          LOBYTE(v17) = 5;
          WPP_RECORDER_SF_d(
            WPP_GLOBAL_Control->DeviceExtension,
            v17,
            1,
            22,
            (__int64)WPP_3ddeec0b7fee33ed2b3cc846f6231af9_Traceguids,
            v43);
          v23 = v45;
          v17 = a5;
        }
        if ( v20 )
        {
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LODWORD(v43) = v20;
            LOBYTE(v17) = 2;
            WPP_RECORDER_SF_d(
              WPP_GLOBAL_Control->DeviceExtension,
              v17,
              1,
              40,
              (__int64)WPP_3ddeec0b7fee33ed2b3cc846f6231af9_Traceguids,
              v43);
            v17 = a5;
          }
          goto LABEL_71;
        }
        if ( v23[4] == v17 )
          break;
      }
      v25 = operator new(0x10u);
      v27 = v25;
      if ( v25 )
      {
        *v25 = a3;
        v28 = 0;
        v25[1] = i;
        v29 = *(_DWORD *)(a1 + 680);
        *(_DWORD *)(a1 + 788) = 0;
        v30 = v25[1];
        a5 = v29;
        if ( *(_DWORD *)(v30 + 8) <= 4u )
        {
          v32 = -1073741811;
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            goto LABEL_54;
          LODWORD(v43) = 4;
          LOBYTE(v26) = 2;
          WPP_RECORDER_SF_d(
            WPP_GLOBAL_Control->DeviceExtension,
            v26,
            1,
            19,
            (__int64)WPP_3ddeec0b7fee33ed2b3cc846f6231af9_Traceguids,
            v43);
          v29 = a5;
        }
        else
        {
          v31 = *(_QWORD *)(v30 + 16);
          if ( *(_BYTE *)(v31 + 232) )
          {
            v28 = v31 + 224;
LABEL_51:
            v32 = 0;
            goto LABEL_52;
          }
          if ( *(_QWORD *)(v31 + 272) )
          {
            v28 = *(_QWORD *)(v31 + 272);
            goto LABEL_51;
          }
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LODWORD(v43) = 4;
            LOBYTE(v26) = 4;
            WPP_RECORDER_SF_d(
              WPP_GLOBAL_Control->DeviceExtension,
              v26,
              1,
              20,
              (__int64)WPP_3ddeec0b7fee33ed2b3cc846f6231af9_Traceguids,
              v43);
            v29 = a5;
          }
          v32 = -1073741436;
        }
LABEL_52:
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
          && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
        {
          LODWORD(v43) = v32;
          LOBYTE(v26) = 5;
          WPP_RECORDER_SF_d(
            WPP_GLOBAL_Control->DeviceExtension,
            v26,
            1,
            22,
            (__int64)WPP_3ddeec0b7fee33ed2b3cc846f6231af9_Traceguids,
            v43);
          v29 = a5;
        }
        if ( !v32 )
        {
          v39 = *(_QWORD *)(v28 + 24);
          v26 = 0;
          v40 = *(_DWORD *)(v28 + 32) >> 3;
          v41 = -1073676261;
          v12 = v27;
          while ( v26 < v40 )
          {
            if ( *(_DWORD *)(v39 + 8LL * v26) == v29 )
            {
              *(_DWORD *)(a1 + 792) = *(_DWORD *)(v39 + 8LL * v26 + 4);
              if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
                && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
              {
                LOBYTE(v26) = 5;
                WPP_RECORDER_SF_DDDDDD(
                  WPP_GLOBAL_Control->DeviceExtension,
                  v26,
                  v40,
                  85,
                  (__int64)WPP_3599b95ca20c3e0ba686e8b05788690d_Traceguids,
                  *(_DWORD *)(a1 + 780),
                  *(_DWORD *)(a1 + 684),
                  *(_DWORD *)(a1 + 776),
                  *(_DWORD *)(a1 + 680),
                  *(_DWORD *)(a1 + 788),
                  *(_DWORD *)(a1 + 792));
              }
              v33 = *(_DWORD *)(a1 + 680);
              if ( v33 )
              {
                *(_DWORD *)(a1 + 780) = *(_DWORD *)(a1 + 684);
                v34 = 1;
                *(_DWORD *)(a1 + 776) = v33;
              }
              else
              {
                v34 = 0;
              }
              *(_BYTE *)(a1 + 784) = v34;
              goto LABEL_61;
            }
            ++v26;
          }
          goto LABEL_117;
        }
LABEL_54:
        v12 = v27;
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LODWORD(v43) = v32;
          LOBYTE(v26) = 2;
          WPP_RECORDER_SF_d(
            WPP_GLOBAL_Control->DeviceExtension,
            v26,
            1,
            170,
            (__int64)WPP_3ddeec0b7fee33ed2b3cc846f6231af9_Traceguids,
            v43);
        }
        v41 = v32;
LABEL_117:
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_61;
        v42 = 84;
        LODWORD(v43) = v41;
        goto LABEL_127;
      }
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LODWORD(v43) = a5;
        LOBYTE(v26) = 2;
        WPP_RECORDER_SF_d(
          WPP_GLOBAL_Control->DeviceExtension,
          v26,
          1,
          36,
          (__int64)WPP_3ddeec0b7fee33ed2b3cc846f6231af9_Traceguids,
          v43);
      }
      v35 = -1073741670;
LABEL_125:
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_61;
      v42 = 83;
      LODWORD(v43) = v35;
LABEL_127:
      LOBYTE(v26) = 2;
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        v26,
        1,
        v42,
        (__int64)WPP_3599b95ca20c3e0ba686e8b05788690d_Traceguids,
        v43);
LABEL_61:
      if ( v12 )
      {
        if ( g_Feature_56544556_MoveToWDFMemory_IsEnabled )
        {
          if ( (unsigned __int64)v12 < 0x10 )
          {
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              WPP_RECORDER_SF_(
                WPP_GLOBAL_Control->DeviceExtension,
                2,
                1,
                13,
                (__int64)WPP_8af6070512533c37ff8d635f078fb2ba_Traceguids);
          }
          else
          {
            (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01031 + 1664))(
              WdfDriverGlobals,
              *(v12 - 1));
          }
        }
        else
        {
          ExFreePoolWithTag(v12, 0x47696457u);
        }
      }
      return;
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LODWORD(v43) = v20;
      LOBYTE(v17) = 2;
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        v17,
        1,
        39,
        (__int64)WPP_3ddeec0b7fee33ed2b3cc846f6231af9_Traceguids,
        v43);
      v17 = a5;
    }
LABEL_71:
    v35 = v20;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_61;
    v44 = v17;
    LOBYTE(v17) = 2;
    WPP_RECORDER_SF_Ld(
      WPP_GLOBAL_Control->DeviceExtension,
      v17,
      (unsigned int)WPP_3ddeec0b7fee33ed2b3cc846f6231af9_Traceguids,
      35,
      (__int64)WPP_3ddeec0b7fee33ed2b3cc846f6231af9_Traceguids,
      v44,
      v20);
    goto LABEL_125;
  }
LABEL_21:
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      2,
      1,
      81,
      (__int64)WPP_3599b95ca20c3e0ba686e8b05788690d_Traceguids);
}

```

## disassembly

```asm
0x14000e3f0  push    rbx
0x14000e3f2  push    rbp
0x14000e3f3  push    rsi
0x14000e3f4  push    rdi
0x14000e3f5  push    r15
0x14000e3f7  sub     rsp, 60h
0x14000e3fb  mov     r10d, [rcx+308h]
0x14000e402  mov     rbp, r8
0x14000e405  mov     eax, [rsp+88h+arg_20]
0x14000e40c  mov     rbx, rcx
0x14000e40f  mov     [rcx+2A8h], r9d
0x14000e416  mov     [rcx+2ACh], eax
0x14000e41c  cmp     r10d, r9d
0x14000e41f  jnz     short loc_14000E452
0x14000e421  mov     r8d, [rcx+30Ch]
0x14000e428  cmp     r8d, eax
0x14000e42b  jnz     short loc_14000E452
0x14000e42d  test    r10d, r10d
0x14000e430  jnz     short loc_14000E489
0x14000e432  lea     rsi, WPP_RECORDER_INITIALIZED
0x14000e439  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14000e440  jnz     loc_14000E972
0x14000e446  add     rsp, 60h
0x14000e44a  pop     r15
0x14000e44c  pop     rdi
0x14000e44d  pop     rsi
0x14000e44e  pop     rbp
0x14000e44f  pop     rbx
0x14000e450  retn
0x14000e452  cmp     dword ptr [rcx+30Ch], 3
0x14000e459  movzx   r8d, word ptr [rcx+258h]
0x14000e461  mov     [rsp+88h+arg_18], r14
0x14000e469  jz      short loc_14000E4D2
0x14000e46b  movzx   eax, word ptr [rcx+280h]
0x14000e472  test    r8w, r8w
0x14000e476  jnz     short loc_14000E4E5
0x14000e478  test    ax, ax
0x14000e47b  jz      loc_14000E523
0x14000e481  xor     r14d, r14d
0x14000e484  jmp     loc_14000E50F
0x14000e489  mov     edx, [rcx+318h]
0x14000e48f  test    edx, edx
0x14000e491  jz      short loc_14000E432
0x14000e493  lea     rsi, WPP_RECORDER_INITIALIZED
0x14000e49a  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14000e4a1  jz      short loc_14000E4BF
0x14000e4a3  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e4aa  cmp     byte ptr [rcx+29h], 5
0x14000e4ae  jnb     loc_14000E92D
0x14000e4b4  cmp     word ptr [rcx+48h], 0
0x14000e4b9  jnz     loc_14000E92D
0x14000e4bf  mov     byte ptr [rbx+310h], 1
0x14000e4c6  add     rsp, 60h
0x14000e4ca  pop     r15
0x14000e4cc  pop     rdi
0x14000e4cd  pop     rsi
0x14000e4ce  pop     rbp
0x14000e4cf  pop     rbx
0x14000e4d0  retn
0x14000e4d2  movzx   eax, r8w
0x14000e4d6  neg     ax
0x14000e4d9  sbb     r10d, r10d
0x14000e4dc  add     r10d, 2
0x14000e4e0  xor     r14d, r14d
0x14000e4e3  jmp     short loc_14000E506
0x14000e4e5  xor     r14d, r14d
0x14000e4e8  test    ax, ax
0x14000e4eb  jz      loc_14000E688
0x14000e4f1  mov     rax, [rcx+2A0h]
0x14000e4f8  mov     r10d, r14d
0x14000e4fb  cmp     [rcx+278h], rax
0x14000e502  setnbe  r10b
0x14000e506  test    r10d, r10d
0x14000e509  jnz     loc_14000E67E
0x14000e50f  mov     r10, [rcx+288h]
0x14000e516  movzx   r8d, word ptr [rcx+280h]
0x14000e51e  test    r10, r10
0x14000e521  jnz     short loc_14000E56A
0x14000e523  lea     rsi, WPP_RECORDER_INITIALIZED
0x14000e52a  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14000e531  jz      short loc_14000E55D
0x14000e533  lea     r15, WPP_3599b95ca20c3e0ba686e8b05788690d_Traceguids
0x14000e53a  mov     r9d, 51h ; 'Q'
0x14000e540  mov     [rsp+88h+var_68], r15
0x14000e545  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e54c  mov     r8d, 1
0x14000e552  mov     dl, 2
0x14000e554  mov     rcx, [rcx+40h]
0x14000e558  call    WPP_RECORDER_SF_
0x14000e55d  mov     r14, [rsp+88h+arg_18]
0x14000e565  jmp     loc_14000E446
0x14000e56a  test    r8w, r8w
0x14000e56e  jz      short loc_14000E523
0x14000e570  mov     [rsp+88h+arg_8], r12
0x14000e578  lea     rsi, WPP_RECORDER_INITIALIZED
0x14000e57f  lea     r15, WPP_3599b95ca20c3e0ba686e8b05788690d_Traceguids
0x14000e586  test    dl, dl
0x14000e588  jnz     loc_14000E9B9
0x14000e58e  cmp     dword ptr [rbp+8], 2
0x14000e592  lea     r8, WPP_3ddeec0b7fee33ed2b3cc846f6231af9_Traceguids
0x14000e599  mov     edx, [rbx+2ACh]
0x14000e59f  mov     r12, r14
0x14000e5a2  mov     [rsp+88h+arg_20], edx
0x14000e5a9  mov     [rsp+88h+arg_10], r13
0x14000e5b1  jbe     loc_14000EAF7
0x14000e5b7  mov     rax, [rbp+10h]
0x14000e5bb  cmp     byte ptr [rax+78h], 0
0x14000e5bf  jz      loc_14000EA96
0x14000e5c5  lea     r12, [rax+70h]
0x14000e5c9  mov     r13d, r14d
0x14000e5cc  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14000e5d3  jnz     loc_14000E874
0x14000e5d9  test    r13d, r13d
0x14000e5dc  jnz     loc_14000E694
0x14000e5e2  mov     r12, [r12+10h]
0x14000e5e7  test    r12, r12
0x14000e5ea  jz      loc_14000E833
0x14000e5f0  cmp     dword ptr [r12+8], 0
0x14000e5f6  mov     rax, r14
0x14000e5f9  mov     [rsp+88h+arg_0], rax
0x14000e601  jbe     loc_14000EBA2
0x14000e607  mov     rcx, [r12+10h]
0x14000e60c  cmp     byte ptr [rcx+8], 0
0x14000e610  jz      loc_14000EB48
0x14000e616  mov     r13d, r14d
0x14000e619  mov     [rsp+88h+arg_0], rcx
0x14000e621  mov     rax, rcx
0x14000e624  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14000e62b  jnz     loc_14000E7DF
0x14000e631  test    r13d, r13d
0x14000e634  jz      short loc_14000E6AF
0x14000e636  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14000e63d  jz      loc_14000E839
0x14000e643  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e64a  mov     r9d, 28h ; '('
0x14000e650  mov     dword ptr [rsp+88h+var_60], r13d
0x14000e655  mov     dl, 2
0x14000e657  mov     [rsp+88h+var_68], r8
0x14000e65c  mov     r8d, 1
0x14000e662  mov     rcx, [rcx+40h]
0x14000e666  call    WPP_RECORDER_SF_d
0x14000e66b  mov     edx, [rsp+88h+arg_20]
0x14000e672  lea     r8, WPP_3ddeec0b7fee33ed2b3cc846f6231af9_Traceguids
0x14000e679  jmp     loc_14000E839
0x14000e67e  cmp     r10d, 1
0x14000e682  jnz     loc_14000E523
0x14000e688  mov     r10, [rcx+260h]
0x14000e68f  jmp     loc_14000E51E
0x14000e694  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14000e69b  jnz     loc_14000EBF3
0x14000e6a1  mov     r12, r14
0x14000e6a4  test    r13d, r13d
0x14000e6a7  jnz     loc_14000E839
0x14000e6ad  jmp     short loc_14000E6B8
0x14000e6af  cmp     [rax+10h], edx
0x14000e6b2  jnz     loc_14000E7D2
0x14000e6b8  mov     ecx, 10h; unsigned __int64
0x14000e6bd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000e6c2  mov     r13, rax
0x14000e6c5  test    rax, rax
0x14000e6c8  jz      loc_14000EDCE
0x14000e6ce  mov     [rax], rbp
0x14000e6d1  mov     rbp, r14
0x14000e6d4  mov     [rax+8], r12
0x14000e6d8  mov     r10d, [rbx+2A8h]
0x14000e6df  mov     [rbx+314h], r14d
0x14000e6e6  mov     rax, [rax+8]
0x14000e6ea  mov     [rsp+88h+arg_20], r10d
0x14000e6f2  cmp     dword ptr [rax+8], 4
0x14000e6f6  jbe     loc_14000EC90
0x14000e6fc  mov     rax, [rax+10h]
0x14000e700  cmp     byte ptr [rax+0E8h], 0
0x14000e707  jz      loc_14000EC2E
0x14000e70d  lea     rbp, [rax+0E0h]
0x14000e714  mov     r12d, r14d
0x14000e717  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14000e71e  jnz     loc_14000E8C0
0x14000e724  test    r12d, r12d
0x14000e727  jz      loc_14000ECE2
0x14000e72d  mov     r14, r13
0x14000e730  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14000e737  jnz     loc_14000ED0C
0x14000e73d  test    r12d, r12d
0x14000e740  jnz     loc_14000ED40
0x14000e746  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14000e74d  jnz     loc_14000ED5F
0x14000e753  mov     ecx, [rbx+2A8h]
0x14000e759  test    ecx, ecx
0x14000e75b  jz      short loc_14000E7DB
0x14000e75d  mov     eax, [rbx+2ACh]
0x14000e763  mov     [rbx+30Ch], eax
0x14000e769  mov     al, 1
0x14000e76b  mov     [rbx+308h], ecx
0x14000e771  mov     [rbx+310h], al
0x14000e777  mov     r13, [rsp+88h+arg_10]
0x14000e77f  mov     r12, [rsp+88h+arg_8]
0x14000e787  test    r14, r14
0x14000e78a  jz      loc_14000E55D
0x14000e790  cmp     cs:?g_Feature_56544556_MoveToWDFMemory_IsEnabled@@3_NA, 0; bool g_Feature_56544556_MoveToWDFMemory_IsEnabled
0x14000e797  jz      loc_14000EE6E
0x14000e79d  cmp     r14, 10h
0x14000e7a1  jb      loc_14000EE4A
0x14000e7a7  mov     rax, cs:WdfFunctions_01031
0x14000e7ae  mov     rdx, [r14-8]
0x14000e7b2  mov     rcx, cs:WdfDriverGlobals
0x14000e7b9  mov     rax, [rax+680h]
0x14000e7c0  call    _guard_dispatch_icall
0x14000e7c5  mov     r14, [rsp+88h+arg_18]
0x14000e7cd  jmp     loc_14000E446
0x14000e7d2  mov     r12, [r12]
0x14000e7d6  jmp     loc_14000E5E7
0x14000e7db  xor     al, al
0x14000e7dd  jmp     short loc_14000E771
0x14000e7df  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e7e6  cmp     byte ptr [rcx+29h], 5
0x14000e7ea  jnb     short loc_14000E7F7
0x14000e7ec  cmp     word ptr [rcx+48h], 0
0x14000e7f1  jz      loc_14000E631
0x14000e7f7  mov     rcx, [rcx+40h]
0x14000e7fb  mov     r9d, 16h
0x14000e801  mov     dword ptr [rsp+88h+var_60], r13d
0x14000e806  mov     dl, 5
0x14000e808  mov     [rsp+88h+var_68], r8
0x14000e80d  mov     r8d, 1
0x14000e813  call    WPP_RECORDER_SF_d
0x14000e818  mov     rax, [rsp+88h+arg_0]
0x14000e820  lea     r8, WPP_3ddeec0b7fee33ed2b3cc846f6231af9_Traceguids
0x14000e827  mov     edx, [rsp+88h+arg_20]
0x14000e82e  jmp     loc_14000E631
0x14000e833  mov     r13d, 0C001001Bh
0x14000e839  mov     ebx, r13d
0x14000e83c  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14000e843  jz      loc_14000E777
0x14000e849  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e850  mov     r9d, 23h ; '#'
0x14000e856  mov     [rsp+88h+var_58], r13d
0x14000e85b  mov     dword ptr [rsp+88h+var_60], edx
0x14000e85f  mov     dl, 2
0x14000e861  mov     [rsp+88h+var_68], r8
0x14000e866  mov     rcx, [rcx+40h]
0x14000e86a  call    WPP_RECORDER_SF_Ld
0x14000e86f  jmp     loc_14000EE11
0x14000e874  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e87b  cmp     byte ptr [rcx+29h], 5
0x14000e87f  jnb     short loc_14000E88C
0x14000e881  cmp     word ptr [rcx+48h], 0
0x14000e886  jz      loc_14000E5D9
0x14000e88c  mov     rcx, [rcx+40h]
0x14000e890  mov     r9d, 16h
0x14000e896  mov     dword ptr [rsp+88h+var_60], r13d
0x14000e89b  mov     dl, 5
0x14000e89d  mov     [rsp+88h+var_68], r8
0x14000e8a2  mov     r8d, 1
0x14000e8a8  call    WPP_RECORDER_SF_d
0x14000e8ad  mov     edx, [rsp+88h+arg_20]
0x14000e8b4  lea     r8, WPP_3ddeec0b7fee33ed2b3cc846f6231af9_Traceguids
0x14000e8bb  jmp     loc_14000E5D9
0x14000e8c0  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e8c7  cmp     byte ptr [rcx+29h], 5
0x14000e8cb  jnb     short loc_14000E8D8
0x14000e8cd  cmp     word ptr [rcx+48h], 0
0x14000e8d2  jz      loc_14000E724
0x14000e8d8  mov     rcx, [rcx+40h]
0x14000e8dc  lea     rax, WPP_3ddeec0b7fee33ed2b3cc846f6231af9_Traceguids
0x14000e8e3  mov     r9d, 16h
0x14000e8e9  mov     dword ptr [rsp+88h+var_60], r12d
0x14000e8ee  mov     r8d, 1
0x14000e8f4  mov     [rsp+88h+var_68], rax
0x14000e8f9  mov     dl, 5
0x14000e8fb  call    WPP_RECORDER_SF_d
0x14000e900  mov     r10d, [rsp+88h+arg_20]
0x14000e908  jmp     loc_14000E724
0x14000e910  cmp     edx, r8d
0x14000e913  jnb     loc_14000ED43
0x14000e919  mov     eax, edx
0x14000e91b  cmp     [r9+rax*8], r10d
0x14000e91f  lea     rax, [r9+rax*8]
0x14000e923  jz      loc_14000ECFE
0x14000e929  inc     edx
0x14000e92b  jmp     short loc_14000E910
0x14000e92d  movzx   eax, byte ptr [rbx+310h]
0x14000e934  lea     r15, WPP_3599b95ca20c3e0ba686e8b05788690d_Traceguids
0x14000e93b  mov     rcx, [rcx+40h]
0x14000e93f  mov     r9d, 4Fh ; 'O'
0x14000e945  mov     [rsp+88h+var_40], eax
0x14000e949  mov     eax, [rbx+314h]
0x14000e94f  mov     [rsp+88h+var_48], edx
0x14000e953  mov     dl, 5
0x14000e955  mov     [rsp+88h+var_50], eax
0x14000e959  mov     [rsp+88h+var_58], r10d
0x14000e95e  mov     dword ptr [rsp+88h+var_60], r8d
0x14000e963  mov     [rsp+88h+var_68], r15
0x14000e968  call    WPP_RECORDER_SF_ddddd
0x14000e96d  jmp     loc_14000E4BF
0x14000e972  mov     eax, [rcx+318h]
0x14000e978  lea     r15, WPP_3599b95ca20c3e0ba686e8b05788690d_Traceguids
0x14000e97f  mov     [rsp+88h+var_48], eax
0x14000e983  mov     r9d, 50h ; 'P'
0x14000e989  mov     eax, [rcx+314h]
0x14000e98f  mov     dl, 2
  ... truncated ...
```
