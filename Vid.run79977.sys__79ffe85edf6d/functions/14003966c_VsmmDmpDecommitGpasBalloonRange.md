# VsmmDmpDecommitGpasBalloonRange

- ea: `0x14003966c`
- end: `0x140039ee2`
- name: `VsmmDmpDecommitGpasBalloonRange`
- size: `2166`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x14002c610`

## callees

- `0x1400029c0`
- `0x140006b68`
- `0x140007b68`
- `0x140007e30`
- `0x14000a010`
- `0x14000f78c`
- `0x140021c60`
- `0x140023224`
- `0x140028b04`
- `0x1400294f0`
- `0x14002c98c`
- `0x14002cdb0`
- `0x14002cf3c`
- `0x14002e180`
- `0x14002f724`
- `0x140030990`
- `0x1400309d0`
- `0x14003966c`
- `0x1400af2e8`
- `0x1400f39c0`
- `0x1400fd578`
- `0x1400ff40c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140039e30`
- `ntoskrnl!ExFreePoolWithTag` at `0x140039e30`
- `ntoskrnl!RtlSetBitsEx` at `0x140039d1c`
- `ntoskrnl!RtlSetBitsEx` at `0x140039d1c`

## string_xrefs

- `0x1400397c2`: `VsmmDmpDecommitGpasBalloonRange`
- `0x140039995`: `VsmmDmpDecommitGpasBalloonRange`
- `0x140039cb6`: `VsmmDmpDecommitGpasBalloonRange`
- `0x140039cd4`: `VsmmDmpDecommitGpasBalloonRange`
- `0x140039cf2`: `VsmmDmpDecommitGpasBalloonRange`

## pseudocode

```c
__int64 __fastcall VsmmDmpDecommitGpasBalloonRange(__int64 a1, __int64 a2, unsigned __int64 a3, _QWORD *a4)
{
  __int64 v6; // r14
  __int64 v7; // r15
  __int64 v8; // r13
  char v9; // al
  __int64 v10; // rdi
  _DWORD *v11; // rsi
  PVOID v12; // rdx
  int v13; // ecx
  __int64 v14; // r8
  __int64 v15; // r9
  int v16; // r10d
  int v17; // r11d
  int v18; // edi
  __int64 v19; // r9
  __int64 v20; // r8
  char *v21; // r11
  int v22; // eax
  unsigned __int64 v23; // rbx
  int IsHmeMemoryBlock; // eax
  int v25; // edx
  char *v26; // rax
  unsigned __int64 v27; // rcx
  unsigned __int64 v28; // rax
  __int64 v29; // rcx
  __int64 v30; // rax
  _QWORD *v31; // rbx
  __int64 v32; // rbx
  _QWORD *v33; // rdi
  __int64 v34; // rcx
  int v35; // r12d
  char v37; // [rsp+50h] [rbp-B0h] BYREF
  char v38; // [rsp+51h] [rbp-AFh]
  char v39; // [rsp+52h] [rbp-AEh] BYREF
  char v40; // [rsp+53h] [rbp-ADh]
  char v41; // [rsp+54h] [rbp-ACh]
  char *v42; // [rsp+58h] [rbp-A8h]
  PVOID P; // [rsp+60h] [rbp-A0h]
  unsigned __int64 v44; // [rsp+68h] [rbp-98h] BYREF
  __int64 v45; // [rsp+70h] [rbp-90h]
  __int64 v46; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int64 v47; // [rsp+80h] [rbp-80h]
  unsigned __int64 v48; // [rsp+88h] [rbp-78h] BYREF
  __int64 v49; // [rsp+90h] [rbp-70h] BYREF
  __int64 v50; // [rsp+98h] [rbp-68h]
  _QWORD *v51; // [rsp+A0h] [rbp-60h]
  int v52[2]; // [rsp+A8h] [rbp-58h] BYREF
  char *v53; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v54; // [rsp+B8h] [rbp-48h] BYREF
  unsigned __int64 v55; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v56; // [rsp+C8h] [rbp-38h]
  __int64 v57; // [rsp+D0h] [rbp-30h]
  __int64 v58; // [rsp+D8h] [rbp-28h]
  __int64 v59; // [rsp+E0h] [rbp-20h] BYREF
  _QWORD v60[3]; // [rsp+E8h] [rbp-18h] BYREF
  char v61[32]; // [rsp+100h] [rbp+0h] BYREF
  char v62[16]; // [rsp+120h] [rbp+20h] BYREF
  char v63[16]; // [rsp+130h] [rbp+30h] BYREF
  __int64 *v64; // [rsp+140h] [rbp+40h]
  __int64 v65; // [rsp+148h] [rbp+48h]
  unsigned __int64 *v66; // [rsp+150h] [rbp+50h]
  __int64 v67; // [rsp+158h] [rbp+58h]
  __int64 v68; // [rsp+160h] [rbp+60h]
  __int64 v69; // [rsp+168h] [rbp+68h]
  _DWORD *v70; // [rsp+170h] [rbp+70h]
  __int64 v71; // [rsp+178h] [rbp+78h]
  __int64 v72; // [rsp+180h] [rbp+80h]
  _DWORD v73[2]; // [rsp+188h] [rbp+88h] BYREF
  __int64 *v74; // [rsp+190h] [rbp+90h]
  __int64 v75; // [rsp+198h] [rbp+98h]
  char **v76; // [rsp+1A0h] [rbp+A0h]
  __int64 v77; // [rsp+1A8h] [rbp+A8h]
  int *v78; // [rsp+1B0h] [rbp+B0h]
  __int64 v79; // [rsp+1B8h] [rbp+B8h]
  __int64 *v80; // [rsp+1C0h] [rbp+C0h]
  __int64 v81; // [rsp+1C8h] [rbp+C8h]
  unsigned __int64 *v82; // [rsp+1D0h] [rbp+D0h]
  __int64 v83; // [rsp+1D8h] [rbp+D8h]
  __int64 *v84; // [rsp+1E0h] [rbp+E0h]
  __int64 v85; // [rsp+1E8h] [rbp+E8h]
  _QWORD *v86; // [rsp+1F0h] [rbp+F0h]
  __int64 v87; // [rsp+1F8h] [rbp+F8h]
  _QWORD v88[32]; // [rsp+200h] [rbp+100h] BYREF

  v60[1] = a1;
  v51 = a4;
  *a4 = 0;
  v58 = 0;
  v6 = *(_QWORD *)(a1 + 240);
  v7 = *(_QWORD *)(a1 + 384);
  v8 = a2 + *(_QWORD *)(a1 + 392) - *(_QWORD *)(a1 + 256);
  v9 = *(_BYTE *)(v6 + 8460);
  v10 = 0;
  v57 = a2;
  v46 = 0;
  v37 = 0;
  v11 = (_DWORD *)(v7 + 264);
  v41 = 0;
  v38 = v9 != 0;
  P = 0;
  v45 = 0;
  v49 = 0;
  v50 = 0;
  v56 = 0;
  v47 = 0;
  v42 = 0;
  v55 = 0;
  v39 = 0;
  v40 = v9;
  if ( (unsigned int)VsmmVsmGetEnabledSecureVtls(v6, 0, 0, 0) )
  {
    if ( (*v11 & 8) != 0 )
    {
      if ( !_bittest64(*(const signed __int64 **)(*((_QWORD *)VidDeviceExtension + 274) + 8LL), 1u) )
      {
        v18 = -1073741637;
        if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
        {
          tlgCreate1Sz_char(v62, "VsmmDmpDecommitGpasBalloonRange");
          tlgCreate1Sz_char(v63, "onecore\\vm\\vid\\sys\\vsmm\\vsmmdm.c");
          v75 = v19;
          v64 = &v46;
          v77 = v19;
          v66 = &v44;
          v69 = 16;
          v68 = v6 + 656;
          v70 = v73;
          v72 = *(_QWORD *)(v6 + 128);
          v73[0] = *(unsigned __int16 *)(v6 + 120);
          v54 = *(_QWORD *)(v6 + 648);
          v74 = &v54;
          v76 = &v53;
          v78 = v52;
          v49 = *(_QWORD *)(a1 + 248);
          v80 = &v49;
          v48 = *(_QWORD *)(a1 + 256);
          v82 = &v48;
          v59 = *(_QWORD *)(a1 + 264);
          v84 = &v59;
          v60[0] = *(int *)(a1 + 292);
          v86 = v60;
          v79 = v19;
          v81 = v19;
          v83 = v19;
          v85 = v19;
          v87 = v19;
          LODWORD(v46) = 3451;
          v65 = 4;
          LODWORD(v44) = -1073741637;
          v67 = 4;
          v71 = 2;
          v73[1] = v20;
          v53 = v21;
          *(_QWORD *)v52 = a3;
          tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, &unk_14005AF18, v20, 0, 16, v61);
        }
        goto LABEL_52;
      }
      VsmmHvMapGpasFromPfnArray(v6, v17, a3, 7);
    }
    else
    {
      VsmmUpdateGpaSpaceForMbpRangeModification(v13, v7, v8, a3, 1, -1, (__int64)v12);
    }
    v41 = 1;
    v22 = VsmmVsmVerifyGpaRangeDefaultVtlPermissions(a1, v57, a3, 0);
    v18 = v22;
    if ( v22 < 0 )
    {
      VidTraceErrorStatusInternal0(
        "VsmmDmpDecommitGpasBalloonRange",
        "onecore\\vm\\vid\\sys\\vsmm\\vsmmdm.c",
        3486,
        (unsigned int)v22);
      goto LABEL_52;
    }
    v10 = (__int64)v42;
    v15 = v49;
    v12 = v42;
    v14 = (__int64)v42;
    v16 = (int)v42;
  }
  v23 = 0;
  v48 = -1;
  v44 = -1;
  v53 = 0;
  v54 = 0;
  if ( !a3 )
  {
LABEL_51:
    v18 = 0;
    goto LABEL_52;
  }
  while ( 1 )
  {
    if ( (*v11 & 8) == 0 )
    {
      if ( v12 && v14 == v15 )
      {
        if ( v10 )
        {
          VsmmUpdateGpaSpaceForMbpRangeModification(v6, v7, v16 + v8, v10, 0, -1, 0);
          v12 = P;
          v10 = 0;
          v14 = v45;
          v42 = 0;
          v47 = v23;
        }
        LOBYTE(v15) = v38;
        VsmmDmpRepurposePfns(v7, v12, v14, v15);
        v45 = 0;
        if ( v40 )
        {
          P = 0;
          v39 = 0;
          v49 = 0;
        }
      }
      if ( v50 == 32 )
      {
        if ( v10 )
        {
          VsmmUpdateGpaSpaceForMbpRangeModification(v6, v7, v8 + v47, v10, 0, -1, 0);
          v47 = v23;
          v42 = 0;
        }
        IsHmeMemoryBlock = VsmmHmeIsHmeMemoryBlock(v7, v12, v14, v15);
        LOBYTE(v25) = *(_BYTE *)(v7 + 16);
        VsmmFreePagesIoSpace(v6, v25, *(_DWORD *)(v7 + 252), 3, (__int64)v88, 32, IsHmeMemoryBlock);
        v50 = 0;
      }
      if ( !P )
      {
        LOBYTE(v14) = v38;
        v26 = (char *)VsmmDmpDecommitGpasMdlGet(v6, (int)a3 - *(_DWORD *)v51, v14, (unsigned int)&v39, (__int64)&v49);
        P = v26;
        if ( !v26 )
        {
          v18 = -1073741670;
          VidTraceErrorStatusInternal0(
            "VsmmDmpDecommitGpasBalloonRange",
            "onecore\\vm\\vid\\sys\\vsmm\\vsmmdm.c",
            3571,
            3221225626LL);
          goto LABEL_52;
        }
        v53 = v26 + 48;
      }
    }
    *(_QWORD *)v52 = v23 + v8;
    v18 = VsmmMbpDmBalloon(v7, (int)v23 + (int)v8, (unsigned int)&v46, (unsigned int)&v55, (__int64)&v37);
    if ( v18 < 0 )
      break;
LABEL_32:
    if ( (*v11 & 8) != 0 )
    {
      v10 = (__int64)v42;
      goto LABEL_46;
    }
    if ( v37 )
    {
      v27 = v44;
      if ( (v46 & 0xFFFFFFFFFFFC0000uLL) != v44 )
      {
        v27 = v46 & 0xFFFFFFFFFFFC0000uLL;
        v44 = v46 & 0xFFFFFFFFFFFC0000uLL;
        v28 = v23 & 0xFFFFFFFFFFFC0000uLL;
        v48 = v23 & 0xFFFFFFFFFFFC0000uLL;
        goto LABEL_41;
      }
    }
    else
    {
      if ( v46 == -1 )
      {
        ++v56;
      }
      else
      {
        v29 = v45;
        *(_QWORD *)&v53[8 * v45] = v46;
        v45 = v29 + 1;
      }
      v27 = v44;
    }
    v28 = v48;
LABEL_41:
    if ( v27 != -1 && v23 == v28 + 0x3FFFF )
    {
      v30 = v50;
      v44 = -1;
      v88[v50] = v27 << 12;
      v50 = v30 + 1;
    }
    v10 = (__int64)++v42;
LABEL_46:
    v54 = ++v23;
    ++*v51;
    if ( v23 >= a3 )
      goto LABEL_51;
    v12 = P;
    v14 = v45;
    v15 = v49;
    v16 = v47;
  }
  while ( v18 == -2147483631 )
  {
    VidLockRelease(v6 + 3744);
    v18 = VsmmDmSlpWaitForTransientMbpOperationComplete(v7, v52[0]);
    VidLockAcquireExclusive(v6 + 3744);
    if ( v18 < 0 )
    {
      VidTraceErrorStatusInternal0(
        "VsmmDmpDecommitGpasBalloonRange",
        "onecore\\vm\\vid\\sys\\vsmm\\vsmmdm.c",
        3607,
        (unsigned int)v18);
      goto LABEL_52;
    }
    v18 = VsmmMbpDmBalloon(v7, v52[0], (unsigned int)&v46, (unsigned int)&v55, (__int64)&v37);
    if ( v18 >= 0 )
    {
      v23 = v54;
      goto LABEL_32;
    }
  }
  VidTraceErrorStatusInternal0(
    "VsmmDmpDecommitGpasBalloonRange",
    "onecore\\vm\\vid\\sys\\vsmm\\vsmmdm.c",
    3593,
    (unsigned int)v18);
LABEL_52:
  v31 = v51;
  if ( *v51 )
  {
    RtlSetBitsEx(v7 + 424, v8);
    VidReaderCounterAdvanceAndWait(v6 + 3928, 1);
    if ( (*v11 & 8) != 0 )
    {
      VsmmMemoryBlockDecommitPrimaryRamRange(v7, v8, *v31, 1);
      v32 = (__int64)v42;
    }
    else
    {
      v32 = (__int64)v42;
      VsmmDmpDecommitGpasFlush(v6, v7, (_DWORD)P, v45, (__int64)v88, v50, v8 + v47, (__int64)v42, v38);
      if ( *(_BYTE *)(v6 + 8460) )
      {
        v33 = v51;
        VsmmDmSlpBitmapRangeClear(v7 + 624, v8, *v51);
        VsmmDmSlpBitmapRangeClear(v7 + 648, v8, *v33);
        if ( v55 )
          _InterlockedAdd64((volatile signed __int64 *)(*(_QWORD *)(v6 + 1528) + 1096LL), v55);
        if ( v56 )
          _InterlockedAdd64((volatile signed __int64 *)(*(_QWORD *)(v6 + 1528) + 1104LL), -v56);
      }
    }
    v18 = 0;
  }
  else
  {
    v32 = (__int64)v42;
  }
  if ( v39 && (!v40 || !v32) )
    ExFreePoolWithTag(P, 0x6D4D6456u);
  if ( v41 )
  {
    v34 = *v51;
    if ( *v51 != a3 )
    {
      v35 = a3 - v34;
      if ( (*v11 & 8) != 0 )
        VsmmHvMapGpasFromPfnArray(v6, v34 + v57, v35, 6);
      else
        VsmmUpdateGpaSpaceForMbpRangeModification(v6, v7, v34 + v8, v35, 0, -1, 0);
    }
  }
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x14003966c  push    rbp
0x14003966e  push    rbx
0x14003966f  push    rsi
0x140039670  push    rdi
0x140039671  push    r12
0x140039673  push    r13
0x140039675  push    r14
0x140039677  push    r15
0x140039679  lea     rbp, [rsp-218h]
0x140039681  sub     rsp, 318h
0x140039688  mov     rax, cs:__security_cookie
0x14003968f  xor     rax, rsp
0x140039692  mov     [rbp+250h+var_50], rax
0x140039699  mov     rbx, rcx
0x14003969c  mov     [rbp+250h+var_260], rcx
0x1400396a0  xor     ecx, ecx
0x1400396a2  mov     [rbp+250h+var_2B0], r9
0x1400396a6  mov     [r9], rcx
0x1400396a9  mov     r11, rdx
0x1400396ac  mov     [rbp+250h+var_278], rcx
0x1400396b0  mov     r12, r8
0x1400396b3  mov     r14, [rbx+0F0h]
0x1400396ba  mov     r8d, ecx
0x1400396bd  mov     r13, [rbx+188h]
0x1400396c4  mov     r9d, ecx
0x1400396c7  sub     r13, [rbx+100h]
0x1400396ce  mov     r10d, ecx
0x1400396d1  mov     r15, [rbx+180h]
0x1400396d8  add     r13, r11
0x1400396db  mov     al, [r14+210Ch]
0x1400396e2  mov     edi, ecx
0x1400396e4  test    al, al
0x1400396e6  mov     [rbp+250h+var_280], rdx
0x1400396ea  mov     [rsp+350h+var_2D8], rcx
0x1400396ef  mov     edx, ecx
0x1400396f1  mov     [rsp+350h+var_300], cl
0x1400396f5  lea     rsi, [r15+108h]
0x1400396fc  mov     [rsp+350h+var_2FC], cl
0x140039700  setnz   [rsp+350h+var_2FF]
0x140039705  mov     [rsp+350h+P], rcx
0x14003970a  mov     [rsp+350h+var_2E0], rcx
0x14003970f  mov     [rbp+250h+var_2C0], rcx
0x140039713  mov     [rbp+250h+var_2B8], rcx
0x140039717  mov     [rbp+250h+var_288], rcx
0x14003971b  mov     [rbp+250h+var_2D0], rcx
0x14003971f  mov     [rsp+350h+var_2F8], rcx
0x140039724  mov     [rbp+250h+var_290], rcx
0x140039728  mov     [rsp+350h+var_2FE], cl
0x14003972c  mov     rcx, r14
0x14003972f  mov     [rsp+350h+var_2FD], al
0x140039733  call    VsmmVsmGetEnabledSecureVtls
0x140039738  test    eax, eax
0x14003973a  jz      loc_1400399B8
0x140039740  mov     eax, [rsi]
0x140039742  lea     r9d, [rdi+8]
0x140039746  test    r9b, al
0x140039749  jnz     short loc_140039773
0x14003974b  mov     [rsp+350h+var_320], rdx
0x140039750  mov     r9, r12
0x140039753  mov     dword ptr [rsp+350h+var_328], 0FFFFFFFFh
0x14003975b  mov     rdx, r15
0x14003975e  mov     r8, r13
0x140039761  mov     dword ptr [rsp+350h+var_330], 1
0x140039769  call    VsmmUpdateGpaSpaceForMbpRangeModification
0x14003976e  jmp     loc_140039968
0x140039773  mov     rax, cs:VidDeviceExtension
0x14003977a  mov     rcx, [rax+890h]
0x140039781  mov     rax, [rcx+8]
0x140039785  bt      qword ptr [rax], 1
0x14003978a  setb    al
0x14003978d  test    al, al
0x14003978f  jnz     loc_14003993C
0x140039795  mov     eax, cs:dword_140065110
0x14003979b  mov     edi, 0C00000BBh
0x1400397a0  cmp     eax, 2
0x1400397a3  jbe     loc_140039D02
0x1400397a9  mov     edx, 100h
0x1400397ae  lea     rcx, dword_140065110
0x1400397b5  call    _tlgKeywordOn
0x1400397ba  test    al, al
0x1400397bc  jz      loc_140039D02
0x1400397c2  lea     rdx, aVsmmdmpdecommi_0; "VsmmDmpDecommitGpasBalloonRange"
0x1400397c9  lea     rcx, [rbp+250h+var_230]
0x1400397cd  call    _tlgCreate1Sz_char
0x1400397d2  lea     rdx, aOnecoreVmVidSy_18; "onecore\\vm\\vid\\sys\\vsmm\\vsmmdm.c"
0x1400397d9  lea     rcx, [rbp+250h+var_220]
0x1400397dd  call    _tlgCreate1Sz_char
0x1400397e2  lea     rax, [rsp+350h+var_2D8]
0x1400397e7  mov     [rbp+250h+var_1B8], r9
0x1400397ee  mov     [rbp+250h+var_210], rax
0x1400397f2  lea     rcx, dword_140065110
0x1400397f9  lea     rax, [rsp+350h+var_2E8]
0x1400397fe  mov     [rbp+250h+var_1A8], r9
0x140039805  mov     [rbp+250h+var_200], rax
0x140039809  mov     edx, 10h
0x14003980e  lea     rax, [r14+290h]
0x140039815  mov     [rbp+250h+var_1E8], rdx
0x140039819  mov     [rbp+250h+var_1F0], rax
0x14003981d  lea     rax, [rbp+250h+var_1C8]
0x140039824  mov     [rbp+250h+var_1E0], rax
0x140039828  mov     rax, [r14+80h]
0x14003982f  mov     [rbp+250h+var_1D0], rax
0x140039836  movzx   eax, word ptr [r14+78h]
0x14003983b  mov     [rbp+250h+var_1C8], eax
0x140039841  mov     rax, [r14+288h]
0x140039848  mov     [rbp+250h+var_298], rax
0x14003984c  lea     rax, [rbp+250h+var_298]
0x140039850  mov     [rbp+250h+var_1C0], rax
0x140039857  lea     rax, [rbp+250h+var_2A0]
0x14003985b  mov     [rbp+250h+var_1B0], rax
0x140039862  lea     rax, [rbp+250h+var_2A8]
0x140039866  mov     [rbp+250h+var_1A0], rax
0x14003986d  mov     rax, [rbx+0F8h]
0x140039874  mov     [rbp+250h+var_2C0], rax
0x140039878  lea     rax, [rbp+250h+var_2C0]
0x14003987c  mov     [rbp+250h+var_190], rax
0x140039883  mov     rax, [rbx+100h]
0x14003988a  mov     [rbp+250h+var_2C8], rax
0x14003988e  lea     rax, [rbp+250h+var_2C8]
0x140039892  mov     [rbp+250h+var_180], rax
0x140039899  mov     rax, [rbx+108h]
0x1400398a0  mov     [rbp+250h+var_270], rax
0x1400398a4  lea     rax, [rbp+250h+var_270]
0x1400398a8  mov     [rbp+250h+var_170], rax
0x1400398af  movsxd  rax, dword ptr [rbx+124h]
0x1400398b6  mov     [rbp+250h+var_268], rax
0x1400398ba  lea     rax, [rbp+250h+var_268]
0x1400398be  mov     [rbp+250h+var_160], rax
0x1400398c5  lea     rax, [rbp+250h+var_250]
0x1400398c9  mov     [rsp+350h+var_328], rax
0x1400398ce  mov     dword ptr [rsp+350h+var_330], edx
0x1400398d2  lea     rdx, unk_14005AF18
0x1400398d9  mov     [rbp+250h+var_198], r9
0x1400398e0  mov     [rbp+250h+var_188], r9
0x1400398e7  mov     [rbp+250h+var_178], r9
0x1400398ee  mov     [rbp+250h+var_168], r9
0x1400398f5  mov     [rbp+250h+var_158], r9
0x1400398fc  xor     r9d, r9d
0x1400398ff  mov     dword ptr [rsp+350h+var_2D8], 0D7Bh
0x140039907  mov     [rbp+250h+var_208], 4
0x14003990f  mov     dword ptr [rsp+350h+var_2E8], edi
0x140039913  mov     [rbp+250h+var_1F8], 4
0x14003991b  mov     [rbp+250h+var_1D8], 2
0x140039923  mov     [rbp+250h+var_1C4], r8d
0x14003992a  mov     [rbp+250h+var_2A0], r11
0x14003992e  mov     qword ptr [rbp+250h+var_2A8], r12
0x140039932  call    _tlgWriteTransfer_EtwWriteTransfer
0x140039937  jmp     loc_140039D02
0x14003993c  mov     eax, [rbx+124h]
0x140039942  mov     r9d, 7
0x140039948  mov     dword ptr [rsp+350h+var_318], r8d
0x14003994d  mov     rdx, r11
0x140039950  mov     dword ptr [rsp+350h+var_320], eax
0x140039954  mov     r8, r12
0x140039957  lea     rax, [rbp+250h+var_278]
0x14003995b  mov     rcx, r14
0x14003995e  mov     [rsp+350h+var_328], rax
0x140039963  call    VsmmHvMapGpasFromPfnArray
0x140039968  mov     rdx, [rbp+250h+var_280]
0x14003996c  xor     r9d, r9d
0x14003996f  mov     r8, r12
0x140039972  mov     [rsp+350h+var_2FC], 1
0x140039977  mov     rcx, rbx
0x14003997a  call    VsmmVsmVerifyGpaRangeDefaultVtlPermissions
0x14003997f  mov     edi, eax
0x140039981  test    eax, eax
0x140039983  jns     short loc_1400399A6
0x140039985  mov     r9d, eax
0x140039988  lea     rdx, aOnecoreVmVidSy_18; "onecore\\vm\\vid\\sys\\vsmm\\vsmmdm.c"
0x14003998f  mov     r8d, 0D9Eh
0x140039995  lea     rcx, aVsmmdmpdecommi_0; "VsmmDmpDecommitGpasBalloonRange"
0x14003999c  call    VidTraceErrorStatusInternal0
0x1400399a1  jmp     loc_140039D02
0x1400399a6  mov     rdi, [rsp+350h+var_2F8]
0x1400399ab  mov     r9, [rbp+250h+var_2C0]
0x1400399af  mov     rdx, rdi
0x1400399b2  mov     r8, rdi
0x1400399b5  mov     r10, rdi
0x1400399b8  xor     ebx, ebx
0x1400399ba  mov     [rbp+250h+var_2C8], 0FFFFFFFFFFFFFFFFh
0x1400399c2  mov     [rsp+350h+var_2E8], 0FFFFFFFFFFFFFFFFh
0x1400399cb  mov     [rbp+250h+var_2A0], 0
0x1400399d3  mov     [rbp+250h+var_298], rbx
0x1400399d7  test    r12, r12
0x1400399da  jz      loc_140039D00
0x1400399e0  mov     eax, [rsi]
0x1400399e2  test    al, 8
0x1400399e4  jnz     loc_140039B3C
0x1400399ea  test    rdx, rdx
0x1400399ed  jz      short loc_140039A6C
0x1400399ef  cmp     r8, r9
0x1400399f2  jnz     short loc_140039A6C
0x1400399f4  test    rdi, rdi
0x1400399f7  jz      short loc_140039A39
0x1400399f9  mov     [rsp+350h+var_320], 0
0x140039a02  lea     r8, [r10+r13]
0x140039a06  mov     dword ptr [rsp+350h+var_328], 0FFFFFFFFh
0x140039a0e  mov     r9, rdi
0x140039a11  mov     rdx, r15
0x140039a14  mov     dword ptr [rsp+350h+var_330], 0
0x140039a1c  mov     rcx, r14
0x140039a1f  call    VsmmUpdateGpaSpaceForMbpRangeModification
0x140039a24  mov     rdx, [rsp+350h+P]
0x140039a29  xor     edi, edi
0x140039a2b  mov     r8, [rsp+350h+var_2E0]
0x140039a30  mov     [rsp+350h+var_2F8], rdi
0x140039a35  mov     [rbp+250h+var_2D0], rbx
0x140039a39  mov     r9b, [rsp+350h+var_2FF]
0x140039a3e  mov     rcx, r15
0x140039a41  call    VsmmDmpRepurposePfns
0x140039a46  cmp     [rsp+350h+var_2FD], 0
0x140039a4b  mov     [rsp+350h+var_2E0], 0
0x140039a54  jz      short loc_140039A6C
0x140039a56  mov     [rsp+350h+P], 0
0x140039a5f  mov     [rsp+350h+var_2FE], 0
0x140039a64  mov     [rbp+250h+var_2C0], 0
0x140039a6c  cmp     [rbp+250h+var_2B8], 20h ; ' '
0x140039a71  jnz     loc_140039AF9
0x140039a77  test    rdi, rdi
0x140039a7a  jz      short loc_140039AB7
0x140039a7c  mov     r8, [rbp+250h+var_2D0]
0x140039a80  mov     r9, rdi
0x140039a83  mov     [rsp+350h+var_320], 0
0x140039a8c  add     r8, r13
0x140039a8f  mov     dword ptr [rsp+350h+var_328], 0FFFFFFFFh
0x140039a97  mov     rdx, r15
0x140039a9a  mov     rcx, r14
0x140039a9d  mov     dword ptr [rsp+350h+var_330], 0
0x140039aa5  call    VsmmUpdateGpaSpaceForMbpRangeModification
0x140039aaa  mov     [rbp+250h+var_2D0], rbx
0x140039aae  mov     [rsp+350h+var_2F8], 0
0x140039ab7  mov     rcx, r15
0x140039aba  call    VsmmHmeIsHmeMemoryBlock
0x140039abf  mov     r8d, [r15+0FCh]
0x140039ac6  mov     r9d, 3
0x140039acc  mov     dl, [r15+10h]
0x140039ad0  mov     rcx, r14
0x140039ad3  mov     dword ptr [rsp+350h+var_320], eax
0x140039ad7  lea     rax, [rbp+250h+var_150]
0x140039ade  mov     [rsp+350h+var_328], 20h ; ' '
0x140039ae7  mov     [rsp+350h+var_330], rax
0x140039aec  call    VsmmFreePagesIoSpace
0x140039af1  mov     [rbp+250h+var_2B8], 0
0x140039af9  cmp     [rsp+350h+P], 0
0x140039aff  jnz     short loc_140039B3C
0x140039b01  mov     rcx, [rbp+250h+var_2B0]
0x140039b05  lea     rax, [rbp+250h+var_2C0]
0x140039b09  mov     r8b, [rsp+350h+var_2FF]
0x140039b0e  lea     r9, [rsp+350h+var_2FE]
0x140039b13  mov     rdx, r12
0x140039b16  mov     [rsp+350h+var_330], rax
0x140039b1b  sub     rdx, [rcx]
0x140039b1e  mov     rcx, r14
0x140039b21  call    VsmmDmpDecommitGpasMdlGet
0x140039b26  mov     [rsp+350h+P], rax
0x140039b2b  test    rax, rax
0x140039b2e  jz      loc_140039CA1
0x140039b34  add     rax, 30h ; '0'
0x140039b38  mov     [rbp+250h+var_2A0], rax
0x140039b3c  lea     rax, [rbx+r13]
0x140039b40  lea     rcx, [rsp+350h+var_300]
0x140039b45  mov     qword ptr [rbp+250h+var_2A8], rax
0x140039b49  mov     [rsp+350h+var_330], rcx
0x140039b4e  lea     r9, [rbp+250h+var_290]
0x140039b52  mov     rcx, r15
0x140039b55  lea     r8, [rsp+350h+var_2D8]
0x140039b5a  mov     rdx, rax
0x140039b5d  call    VsmmMbpDmBalloon
0x140039b62  mov     edi, eax
0x140039b64  test    eax, eax
0x140039b66  jns     short loc_140039BCA
0x140039b68  cmp     edi, 80000011h
0x140039b6e  jnz     loc_140039CE2
0x140039b74  lea     rbx, [r14+0EA0h]
0x140039b7b  mov     rcx, rbx
0x140039b7e  call    VidLockRelease
0x140039b83  mov     rdx, qword ptr [rbp+250h+var_2A8]; int
0x140039b87  mov     rcx, r15; int
0x140039b8a  call    VsmmDmSlpWaitForTransientMbpOperationComplete
0x140039b8f  mov     rcx, rbx
0x140039b92  mov     edi, eax
0x140039b94  call    VidLockAcquireExclusive
0x140039b99  test    edi, edi
0x140039b9b  js      loc_140039CC4
0x140039ba1  mov     rdx, qword ptr [rbp+250h+var_2A8]
0x140039ba5  lea     rax, [rsp+350h+var_300]
0x140039baa  lea     r9, [rbp+250h+var_290]
0x140039bae  mov     [rsp+350h+var_330], rax
0x140039bb3  lea     r8, [rsp+350h+var_2D8]
0x140039bb8  mov     rcx, r15
0x140039bbb  call    VsmmMbpDmBalloon
0x140039bc0  mov     edi, eax
0x140039bc2  test    eax, eax
0x140039bc4  js      short loc_140039B68
0x140039bc6  mov     rbx, [rbp+250h+var_298]
0x140039bca  mov     eax, [rsi]
0x140039bcc  test    al, 8
0x140039bce  jnz     loc_140039C72
0x140039bd4  cmp     [rsp+350h+var_300], 0
0x140039bd9  mov     rax, [rsp+350h+var_2D8]
  ... truncated ...
```
