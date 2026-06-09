# Isoch_Stage_CompleteTD

- ea: `0x140014d70`
- end: `0x14001566d`
- name: `Isoch_Stage_CompleteTD`
- size: `2301`
- prototype: ``
- caller_count: `3`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x140015810`
- `0x140015bf0`
- `0x140016218`

## callees

- `0x14000d26c`
- `0x14000d2e4`
- `0x14000d6a0`
- `0x140014270`
- `0x140014d70`
- `0x140015680`
- `0x140029410`
- `0x1400599b0`
- `0x140059d80`

## import_xrefs

- `ntoskrnl!KfRaiseIrql` at `0x140014ea2`
- `ntoskrnl!KfRaiseIrql` at `0x1400150fc`
- `ntoskrnl!KfRaiseIrql` at `0x140014ea2`
- `ntoskrnl!KfRaiseIrql` at `0x1400150fc`
- `ntoskrnl!KeLowerIrql` at `0x140014ed4`
- `ntoskrnl!KeLowerIrql` at `0x140015131`
- `ntoskrnl!KeLowerIrql` at `0x140014ed4`
- `ntoskrnl!KeLowerIrql` at `0x140015131`
- `ntoskrnl!IoFreeMdl` at `0x1400150e2`
- `ntoskrnl!IoFreeMdl` at `0x1400155e6`
- `ntoskrnl!IoFreeMdl` at `0x1400150e2`
- `ntoskrnl!IoFreeMdl` at `0x1400155e6`
- `ntoskrnl!KeReleaseSpinLock` at `0x140014ff7`
- `ntoskrnl!KeReleaseSpinLock` at `0x140015172`
- `ntoskrnl!KeReleaseSpinLock` at `0x140014ff7`
- `ntoskrnl!KeReleaseSpinLock` at `0x140015172`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140014eec`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140015141`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140014eec`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140015141`

## pseudocode

```c
__int64 __fastcall Isoch_Stage_CompleteTD(unsigned __int8 *a1, int a2, int a3, char a4, _BYTE *a5, _DWORD *a6)
{
  __int64 *v6; // rbx
  int v7; // r15d
  int v8; // edi
  int v11; // ebp
  __int64 result; // rax
  __int64 v13; // r13
  __int64 v14; // r12
  unsigned int v15; // edi
  __int64 v16; // rdx
  __int64 v17; // rdx
  int v18; // r8d
  __int64 v19; // rdi
  __int64 v20; // rsi
  KIRQL v21; // al
  __int64 v22; // r8
  KIRQL v23; // bp
  unsigned __int8 *v24; // rbp
  __int64 *v25; // rdi
  __int64 *v26; // rsi
  __int64 *v27; // rdx
  __int64 *v28; // rdi
  __int64 *v29; // rsi
  int v30; // ecx
  int v31; // edx
  unsigned int v32; // r8d
  __int64 *v33; // rcx
  __int64 **v34; // rax
  int v35; // eax
  __int64 v36; // r9
  __int64 v37; // rcx
  int v38; // r8d
  __int64 v39; // rdx
  unsigned int v40; // eax
  int v41; // eax
  int v42; // eax
  struct _MDL *v43; // rcx
  __int64 v44; // r8
  KIRQL v45; // di
  KIRQL v46; // dl
  int v47; // edx
  __int64 **v48; // rcx
  int v49; // edx
  __int64 v50; // rax
  bool v51; // zf
  int v52; // edx
  __int64 v53; // rdx
  int v54; // r8d
  int v55; // [rsp+20h] [rbp-98h]
  __int64 v56; // [rsp+70h] [rbp-48h]
  unsigned int v57; // [rsp+C0h] [rbp+8h]
  char v59; // [rsp+D8h] [rbp+20h]

  v59 = a4;
  v6 = *(__int64 **)a1;
  v7 = a3;
  v8 = *((_DWORD *)a1 + 12);
  v11 = -1073545216;
  *a6 = 0;
  result = (__int64)a5;
  v13 = v6[7];
  v14 = v6[6] + 140;
  *a5 = 0;
  v15 = v8 - 1;
  if ( v15 )
  {
    v16 = v15 - 1;
    v57 = v15 - 1;
    if ( *(_DWORD *)(v14 + 12 * v16 + 8) == -1 && (int)v16 >= 0 )
    {
      do
      {
        v50 = v16 + 2 * (v16 + 1);
        v51 = *(_DWORD *)(v14 + 4 * v50) == -1;
        result = v14 + 4 * v50;
        v56 = result;
        if ( !v51 )
          break;
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          v52 = *(unsigned __int8 *)(*(_QWORD *)(v13 + 48) + 143LL);
          LOBYTE(v52) = 2;
          WPP_RECORDER_SF_DDqq(
            *(_QWORD *)(*(_QWORD *)(v13 + 56) + 80LL),
            v52,
            a3,
            24,
            (__int64)WPP_3bb012812b813cd0ec02732545724755_Traceguids,
            *(_BYTE *)(*(_QWORD *)(v13 + 48) + 143LL),
            *(_DWORD *)(*(_QWORD *)(v13 + 56) + 152LL),
            v6[3],
            (char)a1);
          LODWORD(v16) = v57;
          result = v56;
        }
        v16 = (unsigned int)(v16 - 1);
        *(_DWORD *)result = -1073545216;
        v57 = v16;
      }
      while ( (int)v16 >= 0 );
      v7 = a3;
      a4 = v59;
    }
  }
  v17 = v14 + 12LL * v15;
  if ( *(_DWORD *)(v17 + 8) == -1 )
  {
    result = (unsigned int)(a2 - 26);
    if ( (unsigned int)result > 2 )
      goto LABEL_58;
    if ( !v7 )
      goto LABEL_10;
    if ( a2 == 28 )
    {
LABEL_7:
      v11 = 0;
    }
    else
    {
LABEL_58:
      switch ( a2 )
      {
        case 0:
          v11 = -1;
          break;
        case 1:
        case 13:
        case 26:
          goto LABEL_7;
        case 2:
          v11 = -1073741805;
          break;
        case 3:
        case 31:
          v11 = -1073741806;
          break;
        case 6:
          v11 = -1073741820;
          break;
        case 10:
          v11 = -1073741803;
          break;
        case 20:
          v11 = -1073741804;
          break;
        case 23:
          break;
        case 27:
          v11 = -1073610752;
          break;
        case 34:
          v11 = -1073741802;
          break;
        case 199:
          v11 = -1073741807;
          if ( _bittest64((const signed __int64 *)(*(_QWORD *)(v13 + 40) + 736LL), 0x3Eu) )
            v11 = -1073709056;
          break;
        default:
          v11 = -1073741807;
          break;
      }
    }
    *(_DWORD *)(v17 + 8) = v11;
    *((_DWORD *)v6 + 21) += v7;
    result = *(_QWORD *)(v13 + 56);
    if ( *(_DWORD *)(result + 128) == 5 )
      *(_DWORD *)(v17 + 4) = v7;
  }
LABEL_10:
  v18 = *((_DWORD *)a1 + 11);
  if ( v15 != v18 )
    return result;
  if ( a4 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v47 = *(unsigned __int8 *)(*(_QWORD *)(v13 + 48) + 143LL);
      LOBYTE(v47) = 4;
      WPP_RECORDER_SF_DDqqD(
        *(_QWORD *)(*(_QWORD *)(v13 + 56) + 80LL),
        v47,
        v18 - *((_DWORD *)a1 + 10) + 1,
        25,
        v55,
        *(_BYTE *)(*(_QWORD *)(v13 + 48) + 143LL),
        *(_DWORD *)(*(_QWORD *)(v13 + 56) + 152LL),
        v6[3],
        (char)a1,
        v18 - a1[40] + 1);
    }
    if ( *(_BYTE *)(v13 + 288) )
    {
      if ( *((_DWORD *)a1 + 40) )
      {
        TR_SendCompleteStageRequest(v13);
        SecureDmaEnabler_ReleaseResourcesAfterDma(*(_QWORD *)(*(_QWORD *)(v13 + 40) + 104LL), (__int64)(a1 + 128));
      }
    }
    else if ( *((_QWORD *)a1 + 9) )
    {
      v19 = *(_QWORD *)(*(_QWORD *)a1 + 48LL);
      v20 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v13 + 40) + 96LL) + 24LL);
      v21 = KfRaiseIrql(2u);
      v22 = *(unsigned int *)(v19 + 32);
      v23 = v21;
      LOBYTE(v22) = (v22 & 1) == 0;
      (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)(v20 + 8) + 96LL))(v20, *((_QWORD *)a1 + 9), v22);
      KeLowerIrql(v23);
      *((_QWORD *)a1 + 9) = 0;
    }
    *(_BYTE *)(v13 + 104) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v13 + 96));
    v24 = *(unsigned __int8 **)a1;
    if ( a1[56] )
    {
      IoFreeMdl(*((PMDL *)a1 + 8));
      *((_QWORD *)a1 + 8) = 0;
      a1[56] = 0;
    }
    v25 = (__int64 *)*((_QWORD *)a1 + 1);
    v26 = (__int64 *)(a1 + 8);
    if ( v25 == (__int64 *)(a1 + 8) )
    {
      v27 = (__int64 *)(v13 + 208);
    }
    else
    {
      if ( (*(_QWORD *)(*(_QWORD *)(v13 + 40) + 736LL) & 0x4000000000000LL) != 0 )
      {
        do
        {
          memset((void *)v25[2], 0, *((unsigned int *)v25 + 11));
          v25 = (__int64 *)*v25;
        }
        while ( v26 != v25 );
      }
      v27 = (__int64 *)(v13 + 208);
      if ( (__int64 *)*v26 != v26 )
      {
        **((_QWORD **)a1 + 2) = *v27;
        *(_QWORD *)(*v27 + 8) = *((_QWORD *)a1 + 2);
        *v27 = *v26;
        *(_QWORD *)(*v26 + 8) = v27;
        *((_QWORD *)a1 + 2) = a1 + 8;
        *v26 = (__int64)v26;
      }
    }
    v28 = (__int64 *)*((_QWORD *)a1 + 3);
    v29 = (__int64 *)(a1 + 24);
    if ( v28 != (__int64 *)(a1 + 24) )
    {
      if ( (*(_QWORD *)(*(_QWORD *)(v13 + 40) + 736LL) & 0x4000000000000LL) != 0 )
      {
        do
        {
          memset((void *)v28[2], 0, *((unsigned int *)v28 + 11));
          v28 = (__int64 *)*v28;
        }
        while ( v29 != v28 );
        v27 = (__int64 *)(v13 + 208);
      }
      if ( (__int64 *)*v29 != v29 )
      {
        *(_QWORD *)v27[1] = *v29;
        *(_QWORD *)(*v29 + 8) = v27[1];
        **((_QWORD **)a1 + 4) = v27;
        v27[1] = *((_QWORD *)a1 + 4);
        *((_QWORD *)a1 + 4) = a1 + 24;
        *v29 = (__int64)v29;
      }
    }
    v30 = v24[128];
    v31 = v24[132];
    --v24[130];
    v32 = v24[129];
    if ( a1 == &v24[v31 * v30 + 144] )
      v24[132] = (v31 + 1) % v32;
    else
      v24[131] = (int)(v32 + v24[131] - 1) % (int)v32;
    ++*((_DWORD *)v6 + 28);
    if ( *((_DWORD *)v6 + 25) != *((_DWORD *)v6 + 24) )
      goto LABEL_49;
    if ( *((_DWORD *)v6 + 16) == 1 )
    {
      v33 = (__int64 *)*v6;
      if ( *(__int64 **)(*v6 + 8) == v6 )
      {
        v34 = (__int64 **)v6[1];
        if ( *v34 == v6 )
        {
          *v34 = v33;
          v33[1] = (__int64)v34;
          v35 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01033 + 2048))(
                  WdfDriverGlobals,
                  v6[3]);
          if ( v35 >= 0 )
          {
            *((_DWORD *)v6 + 16) = 0;
LABEL_31:
            KeReleaseSpinLock((PKSPIN_LOCK)(v13 + 96), *(_BYTE *)(v13 + 104));
            v36 = v6[6];
            if ( *(_WORD *)(v36 + 2) == 56 )
            {
LABEL_32:
              v37 = 36;
            }
            else
            {
              switch ( *(_WORD *)(v36 + 2) )
              {
                case '9':
                case ':':
                  v37 = 52;
                  break;
                default:
                  goto LABEL_32;
              }
            }
            v38 = 0;
            *(_DWORD *)(v37 + v36) = *((_DWORD *)v6 + 21);
            v39 = 0;
            v40 = *((_DWORD *)v6 + 24);
            if ( v40 )
            {
              while ( 1 )
              {
                v41 = *(_DWORD *)(v36 + 12 * v39 + 148);
                if ( v41 == -1 )
                  break;
                if ( v41 )
                  goto LABEL_57;
                ++v38;
LABEL_37:
                ++*(_DWORD *)(v13 + 264);
                v39 = (unsigned int)(v39 + 1);
                v40 = *((_DWORD *)v6 + 24);
                if ( (unsigned int)v39 >= v40 )
                  goto LABEL_38;
              }
              *(_DWORD *)(v36 + 12 * v39 + 148) = -1073610752;
LABEL_57:
              ++*(_DWORD *)(v36 + 136);
              ++*(_DWORD *)(v13 + 268);
              goto LABEL_37;
            }
LABEL_38:
            if ( *(_DWORD *)(v36 + 136) == v40 )
            {
              *(_DWORD *)(v36 + 4) = -1073739008;
              v42 = -1073741823;
            }
            else
            {
              *(_DWORD *)(v36 + 4) = 0;
              v42 = 0;
            }
            *((_DWORD *)v6 + 17) = v42;
            ++*(_DWORD *)(v13 + 248);
            *(_QWORD *)(v13 + 256) += *((unsigned int *)v6 + 21);
            if ( *((int *)v6 + 17) < 0 )
              ++*(_DWORD *)(v13 + 252);
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              WPP_RECORDER_SF_DDqdDDDD(
                *(_QWORD *)(*(_QWORD *)(v13 + 56) + 80LL),
                *(unsigned __int8 *)(*(_QWORD *)(v13 + 48) + 143LL),
                v38,
                v36,
                v55,
                *(_BYTE *)(*(_QWORD *)(v13 + 48) + 143LL),
                *(_DWORD *)(*(_QWORD *)(v13 + 56) + 152LL),
                v6[3],
                *((_DWORD *)v6 + 17),
                *(_DWORD *)(v36 + 128),
                v38,
                *((_DWORD *)v6 + 24),
                *((_DWORD *)v6 + 21));
            v43 = (struct _MDL *)v6[9];
            if ( v43 )
            {
              v44 = v6[6];
              if ( *(_WORD *)(v44 + 2) != 56 )
              {
                switch ( *(_WORD *)(v44 + 2) )
                {
                  case '9':
                  case ':':
                    goto LABEL_47;
                  default:
                    break;
                }
              }
              if ( v43 != *(struct _MDL **)(v44 + 48) )
              {
LABEL_47:
                IoFreeMdl(v43);
                v6[9] = 0;
              }
            }
            *((_BYTE *)v6 + 16) = 0;
            v45 = KfRaiseIrql(2u);
            (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD))(WdfFunctions_01033 + 2104))(
              WdfDriverGlobals,
              v6[3],
              *((unsigned int *)v6 + 17));
            KeLowerIrql(v45);
            *(_BYTE *)(v13 + 104) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v13 + 96));
LABEL_49:
            --*(_DWORD *)(v13 + 384);
            v46 = *(_BYTE *)(v13 + 104);
            *a6 = *(_DWORD *)(v13 + 384);
            KeReleaseSpinLock((PKSPIN_LOCK)(v13 + 96), v46);
            result = (__int64)a5;
            *a5 = 1;
            return result;
          }
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            v53 = *(_QWORD *)(v13 + 48);
            v54 = *(unsigned __int8 *)(v53 + 143);
            LOBYTE(v53) = 4;
            WPP_RECORDER_SF_DDqd(
              *(_QWORD *)(*(_QWORD *)(v13 + 56) + 80LL),
              v53,
              v54,
              17,
              (__int64)WPP_3bb012812b813cd0ec02732545724755_Traceguids,
              v54,
              *(_DWORD *)(*(_QWORD *)(v13 + 56) + 152LL),
              v6[3],
              v35);
          }
          *((_DWORD *)v6 + 16) = 2;
          v48 = *(__int64 ***)(v13 + 416);
          if ( *v48 == (__int64 *)(v13 + 408) )
          {
            *v6 = v13 + 408;
            v6[1] = (__int64)v48;
            *v48 = v6;
            *(_QWORD *)(v13 + 416) = v6;
            goto LABEL_49;
          }
        }
      }
      __fastfail(3u);
    }
    if ( *((_DWORD *)v6 + 16) == 3 )
      goto LABEL_49;
    goto LABEL_31;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    result = (__int64)WPP_GLOBAL_Control;
    if ( LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      v49 = *(unsigned __int8 *)(*(_QWORD *)(v13 + 48) + 143LL);
      LOBYTE(v49) = 5;
      return WPP_RECORDER_SF_DDqqD(
               *(_QWORD *)(*(_QWORD *)(v13 + 56) + 80LL),
               v49,
               v18 - *((_DWORD *)a1 + 10) + 1,
               26,
               v55,
               *(_BYTE *)(*(_QWORD *)(v13 + 48) + 143LL),
               *(_DWORD *)(*(_QWORD *)(v13 + 56) + 152LL),
               v6[3],
               (char)a1,
               (unsigned __int8)v18 - a1[40] + 1);
    }
  }
  return result;
}

```

## disassembly

```asm
0x140014d70  mov     [rsp+arg_8], rbx
0x140014d75  mov     [rsp+arg_18], r9b
0x140014d7a  mov     [rsp+arg_10], r8d
0x140014d7f  push    rbp
0x140014d80  push    rsi
0x140014d81  push    rdi
0x140014d82  push    r12
0x140014d84  push    r13
0x140014d86  push    r14
0x140014d88  push    r15
0x140014d8a  sub     rsp, 80h
0x140014d91  mov     rax, [rsp+0B8h+arg_28]
0x140014d99  lea     r10, WPP_RECORDER_INITIALIZED
0x140014da0  mov     rbx, [rcx]
0x140014da3  mov     r15d, r8d
0x140014da6  mov     edi, [rcx+30h]
0x140014da9  mov     r14, rcx
0x140014dac  mov     esi, edx
0x140014dae  mov     ebp, 0C0030000h
0x140014db3  mov     dword ptr [rax], 0
0x140014db9  mov     rax, [rsp+0B8h+arg_20]
0x140014dc1  mov     r12, [rbx+30h]
0x140014dc5  mov     r13, [rbx+38h]
0x140014dc9  add     r12, 8Ch
0x140014dd0  mov     byte ptr [rax], 0
0x140014dd3  sub     edi, 1
0x140014dd6  jz      short loc_140014DF2
0x140014dd8  lea     edx, [rdi-1]
0x140014ddb  lea     rcx, [rdx+rdx*2]
0x140014ddf  mov     [rsp+0B8h+arg_0], edx
0x140014de6  cmp     dword ptr [r12+rcx*4+8], 0FFFFFFFFh
0x140014dec  jz      loc_1400154E5
0x140014df2  lea     rcx, [rdi+rdi*2]
0x140014df6  cmp     dword ptr [r12+rcx*4+8], 0FFFFFFFFh
0x140014dfc  lea     rdx, [r12+rcx*4]
0x140014e00  lea     r8, cs:140000000h
0x140014e07  jnz     short loc_140014E3D
0x140014e09  lea     eax, [rsi-1Ah]
0x140014e0c  cmp     eax, 2
0x140014e0f  ja      loc_140015293
0x140014e15  test    r15d, r15d
0x140014e18  jz      short loc_140014E3D
0x140014e1a  cmp     esi, 1Ch
0x140014e1d  jnz     loc_140015293
0x140014e23  xor     ebp, ebp; jumptable 00000001400152B3 cases 1,13,26
0x140014e25  mov     [rdx+8], ebp; jumptable 00000001400152B3 case 23
0x140014e28  add     [rbx+54h], r15d
0x140014e2c  mov     rax, [r13+38h]
0x140014e30  cmp     dword ptr [rax+80h], 5
0x140014e37  jnz     short loc_140014E3D
0x140014e39  mov     [rdx+4], r15d
0x140014e3d  mov     r8d, [r14+2Ch]
0x140014e41  cmp     edi, r8d
0x140014e44  jz      short loc_140014E62
0x140014e46  mov     rbx, [rsp+0B8h+arg_8]
0x140014e4e  add     rsp, 80h
0x140014e55  pop     r15
0x140014e57  pop     r14
0x140014e59  pop     r13
0x140014e5b  pop     r12
0x140014e5d  pop     rdi
0x140014e5e  pop     rsi
0x140014e5f  pop     rbp
0x140014e60  retn
0x140014e62  test    r9b, r9b
0x140014e65  jz      loc_1400153BF
0x140014e6b  cmp     cs:WPP_RECORDER_INITIALIZED, r10; __annotation("TMF:",
0x140014e72  jnz     loc_140015227
0x140014e78  cmp     byte ptr [r13+120h], 0
0x140014e80  jnz     loc_14001538F
0x140014e86  cmp     qword ptr [r14+48h], 0
0x140014e8b  jz      short loc_140014EE8
0x140014e8d  mov     rax, [r14]
0x140014e90  mov     rdi, [rax+30h]
0x140014e94  mov     rax, [r13+28h]
0x140014e98  mov     rcx, [rax+60h]
0x140014e9c  mov     rsi, [rcx+18h]
0x140014ea0  mov     cl, 2; NewIrql
0x140014ea2  call    cs:__imp_KfRaiseIrql
0x140014ea9  nop     dword ptr [rax+rax+00h]
0x140014eae  mov     rdx, [rsi+8]
0x140014eb2  mov     rcx, rsi
0x140014eb5  mov     r8d, [rdi+20h]
0x140014eb9  movzx   ebp, al
0x140014ebc  not     r8b
0x140014ebf  and     r8b, 1
0x140014ec3  mov     rax, [rdx+60h]
0x140014ec7  mov     rdx, [r14+48h]
0x140014ecb  call    _guard_dispatch_icall
0x140014ed0  movzx   ecx, bpl; NewIrql
0x140014ed4  call    cs:__imp_KeLowerIrql
0x140014edb  nop     dword ptr [rax+rax+00h]
0x140014ee0  mov     qword ptr [r14+48h], 0
0x140014ee8  lea     rcx, [r13+60h]; SpinLock
0x140014eec  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140014ef3  nop     dword ptr [rax+rax+00h]
0x140014ef8  mov     [r13+68h], al
0x140014efc  cmp     byte ptr [r14+38h], 0
0x140014f01  mov     rbp, [r14]
0x140014f04  jnz     loc_1400155E2
0x140014f0a  mov     rdi, [r14+8]
0x140014f0e  lea     rsi, [r14+8]
0x140014f12  mov     r8, 4000000000000h
0x140014f1c  mov     r15, r13
0x140014f1f  cmp     rdi, rsi
0x140014f22  jnz     loc_14001518E
0x140014f28  lea     rdx, [r13+0D0h]
0x140014f2f  mov     eax, 28h ; '('
0x140014f34  mov     rdi, [r14+18h]
0x140014f38  lea     rsi, [r14+18h]
0x140014f3c  cmp     rdi, rsi
0x140014f3f  jnz     loc_1400151DD
0x140014f45  movzx   ecx, byte ptr [rbp+80h]
0x140014f4c  movzx   edx, byte ptr [rbp+84h]
0x140014f53  dec     byte ptr [rbp+82h]
0x140014f59  movzx   r8d, byte ptr [rbp+81h]
0x140014f61  imul    ecx, edx
0x140014f64  add     rcx, 90h
0x140014f6b  add     rcx, rbp
0x140014f6e  cmp     r14, rcx
0x140014f71  jnz     loc_140015604
0x140014f77  lea     eax, [rdx+1]
0x140014f7a  xor     edx, edx
0x140014f7c  div     r8d
0x140014f7f  mov     [rbp+84h], dl
0x140014f85  inc     dword ptr [rbx+70h]
0x140014f88  mov     eax, [rbx+60h]
0x140014f8b  cmp     [rbx+64h], eax
0x140014f8e  jnz     loc_140015151
0x140014f94  mov     ecx, [rbx+40h]
0x140014f97  sub     ecx, 1
0x140014f9a  jnz     loc_1400152F5
0x140014fa0  mov     rcx, [rbx]
0x140014fa3  cmp     [rcx+8], rbx
0x140014fa7  jnz     loc_1400152EE
0x140014fad  mov     rax, [rbx+8]
0x140014fb1  cmp     [rax], rbx
0x140014fb4  jnz     loc_1400152EE
0x140014fba  mov     [rax], rcx
0x140014fbd  mov     [rcx+8], rax
0x140014fc1  mov     rax, cs:WdfFunctions_01033
0x140014fc8  mov     rdx, [rbx+18h]
0x140014fcc  mov     rcx, cs:WdfDriverGlobals
0x140014fd3  mov     rax, [rax+800h]
0x140014fda  call    _guard_dispatch_icall
0x140014fdf  test    eax, eax
0x140014fe1  js      loc_1400152C3
0x140014fe7  mov     dword ptr [rbx+40h], 0
0x140014fee  movzx   edx, byte ptr [r13+68h]; NewIrql
0x140014ff3  lea     rcx, [r13+60h]; SpinLock
0x140014ff7  call    cs:__imp_KeReleaseSpinLock
0x140014ffe  nop     dword ptr [rax+rax+00h]
0x140015003  mov     r9, [rbx+30h]
0x140015007  lea     rdi, cs:140000000h
0x14001500e  movzx   eax, word ptr [r9+2]
0x140015013  cmp     eax, 38h ; '8'
0x140015016  jz      short def_140015449; jumptable 0000000140015449 default case, cases 8-56
0x140015018  add     eax, 0FFFFFFF8h; switch 51 cases
0x14001501b  cmp     eax, 32h
0x14001501e  jbe     loc_140015435
0x140015024  mov     ecx, 24h ; '$'; jumptable 0000000140015449 default case, cases 8-56
0x140015029  mov     eax, [rbx+54h]
0x14001502c  xor     r8d, r8d
0x14001502f  mov     [rcx+r9], eax
0x140015033  xor     edx, edx
0x140015035  mov     eax, [rbx+60h]
0x140015038  test    eax, eax
0x14001503a  jz      short loc_140015070
0x14001503c  nop     dword ptr [rax+00h]
0x140015040  lea     rcx, [rdx+rdx*2]
0x140015044  mov     eax, [r9+rcx*4+94h]
0x14001504c  cmp     eax, 0FFFFFFFFh
0x14001504f  jz      loc_140015274
0x140015055  test    eax, eax
0x140015057  jnz     loc_140015280
0x14001505d  inc     r8d
0x140015060  inc     dword ptr [r13+108h]
0x140015067  inc     edx
0x140015069  mov     eax, [rbx+60h]
0x14001506c  cmp     edx, eax
0x14001506e  jb      short loc_140015040
0x140015070  cmp     [r9+88h], eax
0x140015077  jz      loc_1400154D3
0x14001507d  mov     dword ptr [r9+4], 0
0x140015085  xor     eax, eax
0x140015087  mov     [rbx+44h], eax
0x14001508a  inc     dword ptr [r13+0F8h]
0x140015091  mov     eax, [rbx+54h]
0x140015094  add     [r13+100h], rax
0x14001509b  cmp     dword ptr [rbx+44h], 0
0x14001509f  jl      loc_140015379
0x1400150a5  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400150ac  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x1400150b3  jnz     loc_140015320
0x1400150b9  mov     rcx, [rbx+48h]; Mdl
0x1400150bd  test    rcx, rcx
0x1400150c0  jz      short loc_1400150F6
0x1400150c2  mov     r8, [rbx+30h]
0x1400150c6  movzx   eax, word ptr [r8+2]
0x1400150cb  cmp     eax, 38h ; '8'
0x1400150ce  jz      short def_14001546D; jumptable 000000014001546D default case, cases 8-56
0x1400150d0  add     eax, 0FFFFFFF8h; switch 51 cases
0x1400150d3  cmp     eax, 32h
0x1400150d6  jbe     loc_140015459
0x1400150dc  cmp     rcx, [r8+30h]; jumptable 000000014001546D default case, cases 8-56
0x1400150e0  jz      short loc_1400150F6
0x1400150e2  call    cs:__imp_IoFreeMdl; jumptable 000000014001546D cases 57,58
0x1400150e9  nop     dword ptr [rax+rax+00h]
0x1400150ee  mov     qword ptr [rbx+48h], 0
0x1400150f6  mov     cl, 2; NewIrql
0x1400150f8  mov     byte ptr [rbx+10h], 0
0x1400150fc  call    cs:__imp_KfRaiseIrql
0x140015103  nop     dword ptr [rax+rax+00h]
0x140015108  mov     rcx, cs:WdfFunctions_01033
0x14001510f  movzx   edi, al
0x140015112  mov     r8d, [rbx+44h]
0x140015116  mov     rdx, [rbx+18h]
0x14001511a  mov     rax, [rcx+838h]
0x140015121  mov     rcx, cs:WdfDriverGlobals
0x140015128  call    _guard_dispatch_icall
0x14001512d  movzx   ecx, dil; NewIrql
0x140015131  call    cs:__imp_KeLowerIrql
0x140015138  nop     dword ptr [rax+rax+00h]
0x14001513d  lea     rcx, [r13+60h]; SpinLock
0x140015141  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140015148  nop     dword ptr [rax+rax+00h]
0x14001514d  mov     [r13+68h], al
0x140015151  mov     rcx, [rsp+0B8h+arg_28]
0x140015159  dec     dword ptr [r13+180h]
0x140015160  mov     eax, [r13+180h]
0x140015167  movzx   edx, byte ptr [r13+68h]; NewIrql
0x14001516c  mov     [rcx], eax
0x14001516e  lea     rcx, [r13+60h]; SpinLock
0x140015172  call    cs:__imp_KeReleaseSpinLock
0x140015179  nop     dword ptr [rax+rax+00h]
0x14001517e  mov     rax, [rsp+0B8h+arg_20]
0x140015186  mov     byte ptr [rax], 1
0x140015189  jmp     loc_140014E46
0x14001518e  mov     rax, [r13+28h]
0x140015192  test    [rax+2E0h], r8
0x140015199  jnz     loc_140015480
0x14001519f  lea     rdx, [r13+0D0h]
0x1400151a6  cmp     [rsi], rsi
0x1400151a9  jz      loc_140014F2F
0x1400151af  mov     rax, [rdx]
0x1400151b2  mov     rcx, [rsi+8]
0x1400151b6  mov     [rcx], rax
0x1400151b9  mov     rcx, [rdx]
0x1400151bc  mov     rax, [rsi+8]
0x1400151c0  mov     [rcx+8], rax
0x1400151c4  mov     rax, [rsi]
0x1400151c7  mov     [rdx], rax
0x1400151ca  mov     rax, [rsi]
0x1400151cd  mov     [rax+8], rdx
0x1400151d1  mov     [rsi+8], rsi
0x1400151d5  mov     [rsi], rsi
0x1400151d8  jmp     loc_140014F2F
0x1400151dd  mov     rax, [rax+r15]
0x1400151e1  test    [rax+2E0h], r8
0x1400151e8  jnz     loc_1400154B0
0x1400151ee  mov     rcx, [rsi]
0x1400151f1  cmp     rcx, rsi
0x1400151f4  jz      loc_140014F45
0x1400151fa  mov     rax, [rdx+8]
0x1400151fe  mov     [rax], rcx
0x140015201  mov     rax, [rdx+8]
0x140015205  mov     rcx, [rsi]
0x140015208  mov     [rcx+8], rax
0x14001520c  mov     rax, [rsi+8]
0x140015210  mov     [rax], rdx
0x140015213  mov     rax, [rsi+8]
0x140015217  mov     [rdx+8], rax
0x14001521b  mov     [rsi+8], rsi
0x14001521f  mov     [rsi], rsi
0x140015222  jmp     loc_140014F45
0x140015227  mov     rax, [r13+30h]
0x14001522b  mov     r9d, 19h
0x140015231  mov     rcx, [r13+38h]
0x140015235  sub     r8d, [r14+28h]
0x140015239  inc     r8d
0x14001523c  movzx   edx, byte ptr [rax+8Fh]
0x140015243  mov     rax, [rbx+18h]
0x140015247  mov     [rsp+0B8h+var_70], r8d
0x14001524c  mov     [rsp+0B8h+var_78], r14
0x140015251  mov     [rsp+0B8h+var_80], rax
0x140015256  mov     eax, [rcx+98h]
0x14001525c  mov     rcx, [rcx+50h]
0x140015260  mov     [rsp+0B8h+var_88], eax
0x140015264  mov     [rsp+0B8h+var_90], edx
0x140015268  mov     dl, 4
0x14001526a  call    WPP_RECORDER_SF_DDqqD
0x14001526f  jmp     loc_140014E78
0x140015274  mov     dword ptr [r9+rcx*4+94h], 0C0020000h
0x140015280  inc     dword ptr [r9+88h]
0x140015287  inc     dword ptr [r13+10Ch]
0x14001528e  jmp     loc_140015060
0x140015293  cmp     esi, 0C7h; switch 200 cases
0x140015299  ja      def_1400152B3; jumptable 00000001400152B3 default case, cases 4,5,7-9,11,12,14-19,21,22,24,25,28-30,32,33,35-198
0x14001529f  movzx   eax, ds:(byte_140064981 - 140000000h)[r8+rsi]
0x1400152a8  mov     ecx, ds:(jpt_1400152B3 - 140000000h)[r8+rax*4]
  ... truncated ...
```
