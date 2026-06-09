# VsmmVaGpaRangepCreate

- ea: `0x1400f8808`
- end: `0x1400f91a4`
- name: `VsmmVaGpaRangepCreate`
- size: `2460`
- prototype: `__int64 __usercall@<rax>(PVOID P@<rcx>, __int64, int, __int64)`
- caller_count: `2`
- callee_count: `27`
- tags: `broker_com_uri`

## callers

- `0x1400d8770`
- `0x1400f87d4`

## callees

- `0x1400029c0`
- `0x140006b68`
- `0x14000a010`
- `0x140021c60`
- `0x140028b04`
- `0x14002e270`
- `0x14002f724`
- `0x1400305c0`
- `0x140033a60`
- `0x1400347a4`
- `0x140034b64`
- `0x1400386a0`
- `0x14009c5e8`
- `0x1400ac19c`
- `0x1400cd92c`
- `0x1400d40c8`
- `0x1400d9c7c`
- `0x1400f1160`
- `0x1400f1ea0`
- `0x1400f2450`
- `0x1400f5094`
- `0x1400f50dc`
- `0x1400f610c`
- `0x1400f6da8`
- `0x1400f8808`
- `0x1400fb39c`
- `0x1400fe190`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcess` at `0x1400f8c26`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400f8c26`

## string_xrefs

- `0x1400f88cf`: `VsmmVaGpaRangepCreate`
- `0x1400f890f`: `VsmmVaGpaRangepCreate`
- `0x1400f895a`: `VsmmVaGpaRangepCreate`
- `0x1400f8991`: `VsmmVaGpaRangepCreate`
- `0x1400f89bb`: `VsmmVaGpaRangepCreate`
- `0x1400f89e8`: `VsmmVaGpaRangepCreate`
- `0x1400f8a34`: `VsmmVaGpaRangepCreate`
- `0x1400f8acc`: `VsmmVaGpaRangepCreate`
- `0x1400f8b06`: `VsmmVaGpaRangepCreate`
- `0x1400f8b51`: `VsmmVaGpaRangepCreate`
- `0x1400f8bc2`: `VsmmVaGpaRangepCreate`
- `0x1400f8c49`: `VsmmVaGpaRangepCreate`
- `0x1400f8ca9`: `VsmmVaGpaRangepCreate`
- `0x1400f8d29`: `VsmmVaGpaRangepCreate`
- `0x1400f8dbe`: `VsmmVaGpaRangepCreate`
- `0x1400f8e6a`: `VsmmVaGpaRangepCreate`
- `0x1400f8ed4`: `VsmmVaGpaRangepCreate`
- `0x1400f8f03`: `VsmmVaGpaRangepCreate`
- `0x1400f8f43`: `VsmmVaGpaRangepCreate`
- `0x1400f8fad`: `VsmmVaGpaRangepCreate`
- `0x1400f9036`: `VsmmVaGpaRangepCreate`

## pseudocode

```c
__int64 __fastcall VsmmVaGpaRangepCreate(_BYTE *P, __int64 a2, __int64 a3, __int64 a4, __int64 a5, int a6, _QWORD *a7)
{
  char v8; // r13
  __int64 v9; // rsi
  __int64 v10; // rdi
  __int64 v11; // r12
  __int64 v12; // r14
  int Entry; // ebx
  int v14; // eax
  __int64 v15; // r8
  int v16; // ecx
  char v17; // r14
  bool v18; // zf
  __int64 v19; // rbx
  __int64 v20; // rdx
  __int64 v21; // r8
  int v22; // r14d
  __int64 v23; // rdx
  __int64 v24; // rcx
  __int64 v25; // r8
  __int64 v26; // r9
  int v27; // eax
  int v28; // r9d
  int v29; // r8d
  int v31; // [rsp+20h] [rbp-E0h]
  int v32; // [rsp+20h] [rbp-E0h]
  __int64 v33; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v34; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v35; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v36; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v37; // [rsp+68h] [rbp-98h] BYREF
  __int64 v38; // [rsp+70h] [rbp-90h] BYREF
  _QWORD *v39; // [rsp+78h] [rbp-88h] BYREF
  __int64 v40; // [rsp+80h] [rbp-80h] BYREF
  __int64 v41; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v42[32]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v43[16]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v44[16]; // [rsp+C0h] [rbp-40h] BYREF
  __int64 *v45; // [rsp+D0h] [rbp-30h]
  __int64 v46; // [rsp+D8h] [rbp-28h]
  __int64 *v47; // [rsp+E0h] [rbp-20h]
  __int64 v48; // [rsp+E8h] [rbp-18h]
  char v49[32]; // [rsp+F0h] [rbp-10h] BYREF
  char v50[16]; // [rsp+110h] [rbp+10h] BYREF
  char v51[16]; // [rsp+120h] [rbp+20h] BYREF
  __int64 *v52; // [rsp+130h] [rbp+30h]
  __int64 v53; // [rsp+138h] [rbp+38h]
  __int64 *v54; // [rsp+140h] [rbp+40h]
  __int64 v55; // [rsp+148h] [rbp+48h]
  char *v56; // [rsp+150h] [rbp+50h]
  __int64 v57; // [rsp+158h] [rbp+58h]
  _DWORD *v58; // [rsp+160h] [rbp+60h]
  __int64 v59; // [rsp+168h] [rbp+68h]
  __int64 v60; // [rsp+170h] [rbp+70h]
  _DWORD v61[2]; // [rsp+178h] [rbp+78h] BYREF
  _QWORD **v62; // [rsp+180h] [rbp+80h]
  __int64 v63; // [rsp+188h] [rbp+88h]
  __int64 *v64; // [rsp+190h] [rbp+90h]
  __int64 v65; // [rsp+198h] [rbp+98h]
  __int64 *v66; // [rsp+1A0h] [rbp+A0h]
  __int64 v67; // [rsp+1A8h] [rbp+A8h]
  __int64 *v68; // [rsp+1B0h] [rbp+B0h]
  __int64 v69; // [rsp+1B8h] [rbp+B8h]
  __int64 *v70; // [rsp+1C0h] [rbp+C0h]
  __int64 v71; // [rsp+1C8h] [rbp+C8h]

  v8 = 0;
  v38 = a4;
  v9 = 0;
  v34 = a3;
  v10 = 0;
  v33 = a2;
  *a7 = -1;
  v11 = a3;
  v39 = a7;
  v12 = a2;
  v40 = 0;
  v37 = 0;
  v35 = 0;
  v36 = 0;
  VidObjectLockAcquireExclusive(P + 3736);
  if ( (P[40] & 4) != 0 || (*((_DWORD *)P + 8) & 0xB1E0LL) != 0 )
  {
    Entry = -1073741637;
    VidTraceErrorInternal0("VsmmVaGpaRangepCreate", "onecore\\vm\\vid\\sys\\vsmm\\vsmmvagparange.c", 5227);
    goto LABEL_47;
  }
  Entry = VsmmGpaRangeValidatePageRange(P, v12, v11);
  if ( Entry < 0 )
  {
    VidTraceErrorInternal0("VsmmVaGpaRangepCreate", "onecore\\vm\\vid\\sys\\vsmm\\vsmmvagparange.c", 5237);
    goto LABEL_47;
  }
  if ( (unsigned int)VsmmGpaRangeListOverlapCheck((_DWORD)P, v12, v11, 1, 0) )
  {
    Entry = -1070137272;
    VidTraceErrorInternal0("VsmmVaGpaRangepCreate", "onecore\\vm\\vid\\sys\\vsmm\\vsmmvagparange.c", 5252);
    goto LABEL_47;
  }
  Entry = VsmmMemoryBlockLookupByHandle((_DWORD)P, v38, a6, 1, (__int64)&v36);
  if ( Entry < 0 )
  {
    VidTraceErrorInternal0("VsmmVaGpaRangepCreate", "onecore\\vm\\vid\\sys\\vsmm\\vsmmvagparange.c", 5265);
    v10 = v36;
    goto LABEL_47;
  }
  v10 = v36;
  v14 = *(_DWORD *)(v36 + 264);
  if ( (v14 & 8) == 0 )
  {
    Entry = -1070137326;
    VidTraceErrorInternal0("VsmmVaGpaRangepCreate", "onecore\\vm\\vid\\sys\\vsmm\\vsmmvagparange.c", 5275);
    goto LABEL_47;
  }
  if ( (v14 & 0x2F6) != 0 )
  {
    Entry = -1070137326;
    VidTraceErrorInternal0("VsmmVaGpaRangepCreate", "onecore\\vm\\vid\\sys\\vsmm\\vsmmvagparange.c", 5287);
    goto LABEL_47;
  }
  if ( *(_QWORD *)(v36 + 232) == -1 )
  {
    Entry = -1070137322;
    VidTraceErrorInternal0("VsmmVaGpaRangepCreate", "onecore\\vm\\vid\\sys\\vsmm\\vsmmvagparange.c", 5298);
    goto LABEL_47;
  }
  if ( !*(_DWORD *)(v36 + 224) )
  {
    if ( v11 != *(_QWORD *)(v36 + 40) )
    {
      Entry = -1073741811;
      VidTraceErrorInternal0("VsmmVaGpaRangepCreate", "onecore\\vm\\vid\\sys\\vsmm\\vsmmvagparange.c", 5318);
      goto LABEL_47;
    }
    if ( (a5 & 8) != 0 && (*(_DWORD *)(v36 + 264) & 1) == 0 )
    {
      Entry = -1073741811;
      VidTraceErrorInternal0("VsmmVaGpaRangepCreate", "onecore\\vm\\vid\\sys\\vsmm\\vsmmvagparange.c", 5327);
      v8 = 0;
      goto LABEL_47;
    }
    v16 = *(_DWORD *)(v36 + 264);
    v17 = 4;
    if ( (v16 & 1) != 0 )
    {
      v17 = 21;
      if ( *(_QWORD *)&P[8 * *(unsigned __int8 *)(v36 + 16) + 8984] )
      {
        Entry = -1073741811;
        VidTraceErrorInternal0("VsmmVaGpaRangepCreate", "onecore\\vm\\vid\\sys\\vsmm\\vsmmvagparange.c", 5345);
        v8 = 0;
LABEL_46:
        v12 = v33;
        goto LABEL_47;
      }
    }
    if ( (v16 & 0x10000) != 0 && ((*(_DWORD *)(v36 + 976) - 32) & 0xFFFFFFDF) == 0 )
      v17 |= 0x10u;
    Entry = VsmmGpaRangeAlloc(P, v11, (__int64)&v35);
    if ( Entry < 0 )
    {
      VidTraceErrorInternal0("VsmmVaGpaRangepCreate", "onecore\\vm\\vid\\sys\\vsmm\\vsmmvagparange.c", 5376);
      v9 = v35;
      v8 = 0;
      goto LABEL_46;
    }
    v9 = v35;
    VsmmGpaRangeInitializeMbBacked(v35, v10, 0);
    v18 = (v17 & 1) == 0;
    *(_QWORD *)(v9 + 264) = *(_QWORD *)(v10 + 48) + *(_QWORD *)(v9 + 256) - 1LL;
    v12 = v33;
    if ( !v18 )
      *(_QWORD *)(v10 + 944) = v33 & 0x3FFFF;
    v19 = *((_QWORD *)P + 1280);
    if ( PsGetCurrentProcess() != v19 )
    {
      Entry = -1073741811;
      VidTraceErrorInternal0("VsmmVaGpaRangepCreate", "onecore\\vm\\vid\\sys\\vsmm\\vsmmvagparange.c", 5396);
LABEL_36:
      v8 = 0;
      goto LABEL_47;
    }
    VsmmHvMemPreDepositForGpaRange(v9);
    *(_DWORD *)(v9 + 292) |= 0x400u;
    Entry = VsmmHvPrecommitGpas(
              (_DWORD)P,
              0,
              *(_QWORD *)(v9 + 256),
              (unsigned int)*(_QWORD *)(v9 + 272) - (unsigned int)*(_QWORD *)(v9 + 256) + 1,
              (__int64)&v40);
    if ( Entry < 0 )
    {
      VidTraceErrorInternal0("VsmmVaGpaRangepCreate", "onecore\\vm\\vid\\sys\\vsmm\\vsmmvagparange.c", 5424);
      goto LABEL_36;
    }
    v22 = 6;
    if ( (a5 & 8) != 0 && (unsigned int)VsmmVsmAnyDefaultVtlProtectionsRequired(P, v20, v21) )
      v22 = 7;
    Entry = VsmmHvMapGpasFromPfnArray(
              (_DWORD)P,
              *(_QWORD *)(v9 + 256),
              (unsigned int)*(_QWORD *)(v9 + 272) - (unsigned int)*(_QWORD *)(v9 + 256) + 1,
              v22,
              v31,
              (__int64)&v37,
              *(_DWORD *)(v9 + 292),
              4);
    if ( Entry >= 0 )
    {
      v26 = *(_QWORD *)(v9 + 256);
      if ( v37 != *(_QWORD *)(v9 + 272) - v26 + 1 )
      {
        Entry = -1073741670;
        if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
        {
          tlgCreate1Sz_char(v43, "VsmmVaGpaRangepCreate");
          tlgCreate1Sz_char(v44, "onecore\\vm\\vid\\sys\\vsmm\\vsmmvagparange.c");
          LODWORD(v36) = 5470;
          v45 = &v36;
          v35 = v37;
          v46 = 4;
          v47 = &v35;
          v48 = 8;
          tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, &unk_140057900, 0, 0, 6, v42);
        }
        goto LABEL_44;
      }
      if ( v22 != 6 )
      {
        v27 = VsmmVsmApplyDefaultVtlProtectionToGpaRange((_DWORD)P, 1, v9, v26, *(_QWORD *)(v9 + 272) - v26 + 1);
        Entry = v27;
        if ( v27 < 0 )
        {
          VidTraceErrorStatusInternal0(
            "VsmmVaGpaRangepCreate",
            "onecore\\vm\\vid\\sys\\vsmm\\vsmmvagparange.c",
            5497,
            (unsigned int)v27);
          goto LABEL_44;
        }
        VsmmHvMapGpasFromPfnArray(
          (_DWORD)P,
          *(_QWORD *)(v9 + 256),
          *(_QWORD *)(v9 + 272) - *(_QWORD *)(v9 + 256) + 1,
          6,
          v32,
          (__int64)&v37,
          *(_DWORD *)(v9 + 292),
          0);
      }
      Entry = VsmmNtSlatMemoryRangeRegister((int)P);
      if ( Entry >= 0 )
      {
        Entry = VsmmGpaRangeListInsert(P, v9);
        if ( Entry >= 0 )
        {
          v8 = 1;
          Entry = VidHandleTableAllocateEntry(P + 3264, v9, v9 + 248);
          if ( Entry >= 0 )
          {
            if ( (*(_DWORD *)(v10 + 968) & 1) != 0 )
              VsmmGpaRangeReference(v9);
            *v39 = *(_QWORD *)(v9 + 248);
            if ( *(_QWORD *)(v10 + 40) != *(_QWORD *)(v10 + 48) )
              *(_QWORD *)&P[8 * *(unsigned __int8 *)(v10 + 16) + 8984] = *(_QWORD *)(v9 + 264) + 1LL;
          }
          else
          {
            VidTraceErrorInternal0("VsmmVaGpaRangepCreate", "onecore\\vm\\vid\\sys\\vsmm\\vsmmvagparange.c", 5554);
          }
          goto LABEL_45;
        }
        VidTraceErrorInternal0("VsmmVaGpaRangepCreate", "onecore\\vm\\vid\\sys\\vsmm\\vsmmvagparange.c", 5538);
      }
      else
      {
        VidTraceErrorInternal0("VsmmVaGpaRangepCreate", "onecore\\vm\\vid\\sys\\vsmm\\vsmmvagparange.c", 5527);
      }
    }
    else
    {
      VidTraceErrorInternal0("VsmmVaGpaRangepCreate", "onecore\\vm\\vid\\sys\\vsmm\\vsmmvagparange.c", 5463);
    }
LABEL_44:
    v8 = 0;
LABEL_45:
    v11 = v34;
    goto LABEL_46;
  }
  Entry = -1070137326;
  if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
  {
    tlgCreate1Sz_char(v43, "VsmmVaGpaRangepCreate");
    tlgCreate1Sz_char(v44, "onecore\\vm\\vid\\sys\\vsmm\\vsmmvagparange.c");
    LODWORD(v35) = 5308;
    v45 = &v35;
    v46 = 4;
    LODWORD(v36) = *(_DWORD *)(v10 + 224);
    v47 = &v36;
    v48 = 4;
    tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, &unk_1400578AB, v15, 0, 6, v42);
  }
LABEL_47:
  VidObjectLockRelease(P + 3736);
  if ( Entry < 0 )
  {
    if ( v9 )
    {
      if ( v8 )
      {
        LOBYTE(v23) = 1;
        VidOpCtrlBlock(v9 + 8, v23);
      }
      VsmmGpaRangeRelease(v24, v9, 0);
    }
    else if ( v10 )
    {
      VidOpCtrlFinish(v10 + 128);
    }
    if ( Entry == -1070137299 && a6 == 1 )
      Entry = -1073741670;
    if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
    {
      tlgCreate1Sz_char(v50, "VsmmVaGpaRangepCreate");
      tlgCreate1Sz_char(v51, "onecore\\vm\\vid\\sys\\vsmm\\vsmmvagparange.c");
      v61[1] = v28;
      v52 = &v36;
      LODWORD(v33) = v29;
      v54 = &v35;
      LODWORD(v36) = 5655;
      v56 = P + 656;
      v53 = 4;
      v58 = v61;
      v60 = *((_QWORD *)P + 16);
      v61[0] = *((unsigned __int16 *)P + 60);
      v39 = (_QWORD *)*((_QWORD *)P + 81);
      v62 = &v39;
      v64 = &v34;
      v66 = &v41;
      v68 = &v38;
      v70 = &v33;
      LODWORD(v35) = Entry;
      v55 = 4;
      v57 = 16;
      v59 = 2;
      v63 = 8;
      v34 = v12;
      v65 = 8;
      v41 = v11;
      v67 = 8;
      v69 = 8;
      v71 = 4;
      tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, &unk_140057949, 0, 0, 14, v49);
    }
  }
  else if ( (*(_DWORD *)(v10 + 968) & 1) != 0 )
  {
    VsmmVaGpaRangepSpeculativeFaultForRangeCreate(v9, v23, v25, 0);
  }
  return (unsigned int)Entry;
}

```

## disassembly

```asm
0x1400f8808  push    rbp
0x1400f880a  push    rbx
0x1400f880b  push    rsi
0x1400f880c  push    rdi
0x1400f880d  push    r12
0x1400f880f  push    r13
0x1400f8811  push    r14
0x1400f8813  push    r15
0x1400f8815  lea     rbp, [rsp-0E8h]
0x1400f881d  sub     rsp, 1E8h
0x1400f8824  mov     rax, cs:__security_cookie
0x1400f882b  xor     rax, rsp
0x1400f882e  mov     [rbp+120h+var_50], rax
0x1400f8835  mov     rax, [rbp+120h+arg_30]
0x1400f883c  mov     r15, rcx
0x1400f883f  xor     r13b, r13b
0x1400f8842  mov     [rsp+220h+var_1B0], r9
0x1400f8847  xor     esi, esi
0x1400f8849  mov     [rsp+220h+var_1D0], r8
0x1400f884e  xor     edi, edi
0x1400f8850  mov     [rsp+220h+var_1D8], rdx
0x1400f8855  add     rcx, 0E98h
0x1400f885c  mov     qword ptr [rax], 0FFFFFFFFFFFFFFFFh
0x1400f8863  mov     r12, r8
0x1400f8866  mov     [rsp+220h+var_1A8], rax
0x1400f886b  mov     r14, rdx
0x1400f886e  mov     [rbp+120h+var_1A0], 0
0x1400f8876  mov     [rsp+220h+var_1B8], 0
0x1400f887f  mov     [rsp+220h+var_1E0], r13b
0x1400f8884  mov     [rsp+220h+var_1C8], rsi
0x1400f8889  mov     [rsp+220h+var_1C0], rdi
0x1400f888e  call    VidObjectLockAcquireExclusive
0x1400f8893  test    byte ptr [r15+28h], 4
0x1400f8898  jnz     loc_1400F8F9B
0x1400f889e  mov     eax, [r15+20h]
0x1400f88a2  test    rax, 0B1E0h
0x1400f88a8  jnz     loc_1400F8F9B
0x1400f88ae  mov     r8, r12
0x1400f88b1  mov     rdx, r14
0x1400f88b4  mov     rcx, r15
0x1400f88b7  call    VsmmGpaRangeValidatePageRange
0x1400f88bc  mov     ebx, eax
0x1400f88be  test    eax, eax
0x1400f88c0  jns     short loc_1400F88E0
0x1400f88c2  mov     r8d, 1475h
0x1400f88c8  lea     rdx, aOnecoreVmVidSy_57; "onecore\\vm\\vid\\sys\\vsmm\\vsmmvagpar"...
0x1400f88cf  lea     rcx, aVsmmvagparange_9; "VsmmVaGpaRangepCreate"
0x1400f88d6  call    VidTraceErrorInternal0
0x1400f88db  jmp     loc_1400F8D44
0x1400f88e0  mov     r9d, 1
0x1400f88e6  mov     [rsp+220h+var_200], rsi
0x1400f88eb  mov     r8, r12
0x1400f88ee  mov     rdx, r14
0x1400f88f1  mov     rcx, r15
0x1400f88f4  call    VsmmGpaRangeListOverlapCheck
0x1400f88f9  test    eax, eax
0x1400f88fb  jz      short loc_1400F8920
0x1400f88fd  mov     ebx, 0C0370048h
0x1400f8902  mov     r8d, 1484h
0x1400f8908  lea     rdx, aOnecoreVmVidSy_57; "onecore\\vm\\vid\\sys\\vsmm\\vsmmvagpar"...
0x1400f890f  lea     rcx, aVsmmvagparange_9; "VsmmVaGpaRangepCreate"
0x1400f8916  call    VidTraceErrorInternal0
0x1400f891b  jmp     loc_1400F8D44
0x1400f8920  mov     r8d, [rbp+120h+arg_28]
0x1400f8927  lea     rax, [rsp+220h+var_1C0]
0x1400f892c  mov     rdx, [rsp+220h+var_1B0]
0x1400f8931  mov     r9d, 1
0x1400f8937  mov     rcx, r15
0x1400f893a  mov     [rsp+220h+var_200], rax
0x1400f893f  call    VsmmMemoryBlockLookupByHandle
0x1400f8944  xor     r8d, r8d
0x1400f8947  mov     ebx, eax
0x1400f8949  test    eax, eax
0x1400f894b  jns     short loc_1400F8970
0x1400f894d  mov     r8d, 1491h
0x1400f8953  lea     rdx, aOnecoreVmVidSy_57; "onecore\\vm\\vid\\sys\\vsmm\\vsmmvagpar"...
0x1400f895a  lea     rcx, aVsmmvagparange_9; "VsmmVaGpaRangepCreate"
0x1400f8961  call    VidTraceErrorInternal0
0x1400f8966  mov     rdi, [rsp+220h+var_1C0]
0x1400f896b  jmp     loc_1400F8D44
0x1400f8970  mov     rdi, [rsp+220h+var_1C0]
0x1400f8975  mov     eax, [rdi+108h]
0x1400f897b  test    al, 8
0x1400f897d  jnz     short loc_1400F89A2
0x1400f897f  mov     ebx, 0C0370012h
0x1400f8984  mov     r8d, 149Bh
0x1400f898a  lea     rdx, aOnecoreVmVidSy_57; "onecore\\vm\\vid\\sys\\vsmm\\vsmmvagpar"...
0x1400f8991  lea     rcx, aVsmmvagparange_9; "VsmmVaGpaRangepCreate"
0x1400f8998  call    VidTraceErrorInternal0
0x1400f899d  jmp     loc_1400F8D44
0x1400f89a2  test    eax, 2F6h
0x1400f89a7  jz      short loc_1400F89CC
0x1400f89a9  mov     ebx, 0C0370012h
0x1400f89ae  mov     r8d, 14A7h
0x1400f89b4  lea     rdx, aOnecoreVmVidSy_57; "onecore\\vm\\vid\\sys\\vsmm\\vsmmvagpar"...
0x1400f89bb  lea     rcx, aVsmmvagparange_9; "VsmmVaGpaRangepCreate"
0x1400f89c2  call    VidTraceErrorInternal0
0x1400f89c7  jmp     loc_1400F8D44
0x1400f89cc  cmp     qword ptr [rdi+0E8h], 0FFFFFFFFFFFFFFFFh
0x1400f89d4  jnz     short loc_1400F89F9
0x1400f89d6  mov     ebx, 0C0370016h
0x1400f89db  mov     r8d, 14B2h
0x1400f89e1  lea     rdx, aOnecoreVmVidSy_57; "onecore\\vm\\vid\\sys\\vsmm\\vsmmvagpar"...
0x1400f89e8  lea     rcx, aVsmmvagparange_9; "VsmmVaGpaRangepCreate"
0x1400f89ef  call    VidTraceErrorInternal0
0x1400f89f4  jmp     loc_1400F8D44
0x1400f89f9  mov     eax, [rdi+0E0h]
0x1400f89ff  test    eax, eax
0x1400f8a01  jz      loc_1400F8AB4
0x1400f8a07  mov     eax, cs:dword_140065110
0x1400f8a0d  mov     ebx, 0C0370012h
0x1400f8a12  cmp     eax, 2
0x1400f8a15  jbe     loc_1400F8D44
0x1400f8a1b  mov     edx, 100h
0x1400f8a20  lea     rcx, dword_140065110
0x1400f8a27  call    _tlgKeywordOn
0x1400f8a2c  test    al, al
0x1400f8a2e  jz      loc_1400F8D44
0x1400f8a34  lea     rdx, aVsmmvagparange_9; "VsmmVaGpaRangepCreate"
0x1400f8a3b  lea     rcx, [rbp+120h+var_170]
0x1400f8a3f  call    _tlgCreate1Sz_char
0x1400f8a44  lea     rdx, aOnecoreVmVidSy_57; "onecore\\vm\\vid\\sys\\vsmm\\vsmmvagpar"...
0x1400f8a4b  lea     rcx, [rbp+120h+var_160]
0x1400f8a4f  call    _tlgCreate1Sz_char
0x1400f8a54  lea     rax, [rsp+220h+var_1C8]
0x1400f8a59  mov     dword ptr [rsp+220h+var_1C8], 14BCh
0x1400f8a61  mov     [rbp+120h+var_150], rax
0x1400f8a65  lea     rdx, unk_1400578AB
0x1400f8a6c  mov     [rbp+120h+var_148], 4
0x1400f8a74  lea     rcx, dword_140065110
0x1400f8a7b  mov     eax, [rdi+0E0h]
0x1400f8a81  xor     r9d, r9d
0x1400f8a84  mov     dword ptr [rsp+220h+var_1C0], eax
0x1400f8a88  lea     rax, [rsp+220h+var_1C0]
0x1400f8a8d  mov     [rbp+120h+var_140], rax
0x1400f8a91  lea     rax, [rbp+120h+var_190]
0x1400f8a95  mov     [rsp+220h+var_1F8], rax
0x1400f8a9a  mov     dword ptr [rsp+220h+var_200], 6
0x1400f8aa2  mov     [rbp+120h+var_138], 4
0x1400f8aaa  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400f8aaf  jmp     loc_1400F8D44
0x1400f8ab4  cmp     r12, [rdi+28h]
0x1400f8ab8  jz      short loc_1400F8ADD
0x1400f8aba  mov     ebx, 0C000000Dh
0x1400f8abf  mov     r8d, 14C6h
0x1400f8ac5  lea     rdx, aOnecoreVmVidSy_57; "onecore\\vm\\vid\\sys\\vsmm\\vsmmvagpar"...
0x1400f8acc  lea     rcx, aVsmmvagparange_9; "VsmmVaGpaRangepCreate"
0x1400f8ad3  call    VidTraceErrorInternal0
0x1400f8ad8  jmp     loc_1400F8D44
0x1400f8add  mov     r13, [rbp+120h+arg_20]
0x1400f8ae4  and     r13d, 8
0x1400f8ae8  jz      short loc_1400F8B1A
0x1400f8aea  mov     eax, [rdi+108h]
0x1400f8af0  test    al, 1
0x1400f8af2  jnz     short loc_1400F8B1A
0x1400f8af4  mov     ebx, 0C000000Dh
0x1400f8af9  mov     r8d, 14CFh
0x1400f8aff  lea     rdx, aOnecoreVmVidSy_57; "onecore\\vm\\vid\\sys\\vsmm\\vsmmvagpar"...
0x1400f8b06  lea     rcx, aVsmmvagparange_9; "VsmmVaGpaRangepCreate"
0x1400f8b0d  call    VidTraceErrorInternal0
0x1400f8b12  mov     r13b, sil
0x1400f8b15  jmp     loc_1400F8D44
0x1400f8b1a  mov     ecx, [rdi+108h]
0x1400f8b20  mov     r14d, 2004h
0x1400f8b26  test    cl, 1
0x1400f8b29  jz      short loc_1400F8B65
0x1400f8b2b  movzx   eax, byte ptr [rdi+10h]
0x1400f8b2f  mov     r14d, 2015h
0x1400f8b35  cmp     [r15+rax*8+2318h], r8
0x1400f8b3d  jz      short loc_1400F8B65
0x1400f8b3f  mov     ebx, 0C000000Dh
0x1400f8b44  mov     r8d, 14E1h
0x1400f8b4a  lea     rdx, aOnecoreVmVidSy_57; "onecore\\vm\\vid\\sys\\vsmm\\vsmmvagpar"...
0x1400f8b51  lea     rcx, aVsmmvagparange_9; "VsmmVaGpaRangepCreate"
0x1400f8b58  call    VidTraceErrorInternal0
0x1400f8b5d  mov     r13b, sil
0x1400f8b60  jmp     loc_1400F8D3F
0x1400f8b65  bt      ecx, 10h
0x1400f8b69  jnb     short loc_1400F8B8E
0x1400f8b6b  mov     ecx, [rdi+3D0h]
0x1400f8b71  lea     eax, [rcx-20h]
0x1400f8b74  test    eax, 0FFFFFFDFh
0x1400f8b79  jnz     short loc_1400F8B7F
0x1400f8b7b  or      r14d, 10h
0x1400f8b7f  cmp     ecx, 2
0x1400f8b82  jz      short loc_1400F8B89
0x1400f8b84  cmp     ecx, 20h ; ' '
0x1400f8b87  jnz     short loc_1400F8B8E
0x1400f8b89  bts     r14d, 0Eh
0x1400f8b8e  mov     r9, [rsp+220h+var_1D8]
0x1400f8b93  lea     rax, [rsp+220h+var_1C8]
0x1400f8b98  mov     [rsp+220h+var_1F8], rax; __int64
0x1400f8b9d  mov     r8d, r14d
0x1400f8ba0  xor     edx, edx
0x1400f8ba2  mov     [rsp+220h+var_200], r12; __int64
0x1400f8ba7  mov     rcx, r15; P
0x1400f8baa  call    VsmmGpaRangeAlloc
0x1400f8baf  mov     ebx, eax
0x1400f8bb1  test    eax, eax
0x1400f8bb3  jns     short loc_1400F8BDD
0x1400f8bb5  mov     r8d, 1500h
0x1400f8bbb  lea     rdx, aOnecoreVmVidSy_57; "onecore\\vm\\vid\\sys\\vsmm\\vsmmvagpar"...
0x1400f8bc2  lea     rcx, aVsmmvagparange_9; "VsmmVaGpaRangepCreate"
0x1400f8bc9  call    VidTraceErrorInternal0
0x1400f8bce  mov     rsi, [rsp+220h+var_1C8]
0x1400f8bd3  mov     r13b, [rsp+220h+var_1E0]
0x1400f8bd8  jmp     loc_1400F8D3F
0x1400f8bdd  mov     rsi, [rsp+220h+var_1C8]
0x1400f8be2  xor     r8d, r8d
0x1400f8be5  mov     rcx, rsi
0x1400f8be8  mov     rdx, rdi
0x1400f8beb  call    VsmmGpaRangeInitializeMbBacked
0x1400f8bf0  mov     rcx, [rsi+100h]
0x1400f8bf7  dec     rcx
0x1400f8bfa  add     rcx, [rdi+30h]
0x1400f8bfe  test    r14b, 1
0x1400f8c02  mov     [rsi+108h], rcx
0x1400f8c09  mov     r14, [rsp+220h+var_1D8]
0x1400f8c0e  jz      short loc_1400F8C1F
0x1400f8c10  mov     rax, r14
0x1400f8c13  and     eax, 3FFFFh
0x1400f8c18  mov     [rdi+3B0h], rax
0x1400f8c1f  mov     rbx, [r15+2800h]
0x1400f8c26  call    cs:__imp_PsGetCurrentProcess
0x1400f8c2d  nop     dword ptr [rax+rax+00h]
0x1400f8c32  cmp     rax, rbx
0x1400f8c35  jz      short loc_1400F8C5F
0x1400f8c37  mov     ebx, 0C000000Dh
0x1400f8c3c  mov     r8d, 1514h
0x1400f8c42  lea     rdx, aOnecoreVmVidSy_57; "onecore\\vm\\vid\\sys\\vsmm\\vsmmvagpar"...
0x1400f8c49  lea     rcx, aVsmmvagparange_9; "VsmmVaGpaRangepCreate"
0x1400f8c50  call    VidTraceErrorInternal0
0x1400f8c55  mov     r13b, [rsp+220h+var_1E0]
0x1400f8c5a  jmp     loc_1400F8D44
0x1400f8c5f  mov     rcx, rsi
0x1400f8c62  call    VsmmHvMemPreDepositForGpaRange
0x1400f8c67  bts     dword ptr [rsi+124h], 0Ah
0x1400f8c6f  lea     rax, [rbp+120h+var_1A0]
0x1400f8c73  mov     r8, [rsi+100h]
0x1400f8c7a  xor     edx, edx
0x1400f8c7c  mov     r9, [rsi+110h]
0x1400f8c83  mov     rcx, r15
0x1400f8c86  sub     r9, r8
0x1400f8c89  mov     [rsp+220h+var_200], rax
0x1400f8c8e  inc     r9
0x1400f8c91  call    VsmmHvPrecommitGpas
0x1400f8c96  mov     ebx, eax
0x1400f8c98  test    eax, eax
0x1400f8c9a  jns     short loc_1400F8CB7
0x1400f8c9c  mov     r8d, 1530h
0x1400f8ca2  lea     rdx, aOnecoreVmVidSy_57; "onecore\\vm\\vid\\sys\\vsmm\\vsmmvagpar"...
0x1400f8ca9  lea     rcx, aVsmmvagparange_9; "VsmmVaGpaRangepCreate"
0x1400f8cb0  call    VidTraceErrorInternal0
0x1400f8cb5  jmp     short loc_1400F8C55
0x1400f8cb7  mov     r12d, 6
0x1400f8cbd  mov     r14d, r12d
0x1400f8cc0  test    r13, r13
0x1400f8cc3  jz      short loc_1400F8CD8
0x1400f8cc5  mov     rcx, r15
0x1400f8cc8  call    VsmmVsmAnyDefaultVtlProtectionsRequired
0x1400f8ccd  test    eax, eax
0x1400f8ccf  lea     ecx, [r12+1]
0x1400f8cd4  cmovnz  r14d, ecx
0x1400f8cd8  mov     eax, [rsi+124h]
0x1400f8cde  mov     r13d, 4
0x1400f8ce4  mov     rdx, [rsi+100h]
0x1400f8ceb  mov     r9d, r14d
0x1400f8cee  mov     r8, [rsi+110h]
0x1400f8cf5  mov     rcx, r15
0x1400f8cf8  mov     [rsp+220h+var_1E8], r13d
0x1400f8cfd  sub     r8, rdx
0x1400f8d00  mov     [rsp+220h+var_1F0], eax
0x1400f8d04  inc     r8
0x1400f8d07  lea     rax, [rsp+220h+var_1B8]
0x1400f8d0c  mov     [rsp+220h+var_1F8], rax
0x1400f8d11  call    VsmmHvMapGpasFromPfnArray
0x1400f8d16  mov     ebx, eax
0x1400f8d18  test    eax, eax
0x1400f8d1a  jns     short loc_1400F8D76
0x1400f8d1c  mov     r8d, 1557h
0x1400f8d22  lea     rdx, aOnecoreVmVidSy_57; "onecore\\vm\\vid\\sys\\vsmm\\vsmmvagpar"...
0x1400f8d29  lea     rcx, aVsmmvagparange_9; "VsmmVaGpaRangepCreate"
0x1400f8d30  call    VidTraceErrorInternal0
0x1400f8d35  mov     r13b, [rsp+220h+var_1E0]
0x1400f8d3a  mov     r12, [rsp+220h+var_1D0]
0x1400f8d3f  mov     r14, [rsp+220h+var_1D8]
0x1400f8d44  lea     rcx, [r15+0E98h]
0x1400f8d4b  call    VidObjectLockRelease
0x1400f8d50  xor     r9d, r9d
0x1400f8d53  test    ebx, ebx
0x1400f8d55  js      loc_1400F8FBE
0x1400f8d5b  mov     eax, [rdi+3C8h]
0x1400f8d61  test    al, 1
0x1400f8d63  jz      loc_1400F917E
0x1400f8d69  mov     rcx, rsi
0x1400f8d6c  call    VsmmVaGpaRangepSpeculativeFaultForRangeCreate
0x1400f8d71  jmp     loc_1400F917E
0x1400f8d76  mov     r9, [rsi+100h]
0x1400f8d7d  mov     rax, [rsi+110h]
0x1400f8d84  sub     rax, r9
  ... truncated ...
```
