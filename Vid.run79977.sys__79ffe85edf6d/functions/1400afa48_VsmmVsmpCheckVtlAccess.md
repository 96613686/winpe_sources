# VsmmVsmpCheckVtlAccess

- ea: `0x1400afa48`
- end: `0x1400afed4`
- name: `VsmmVsmpCheckVtlAccess`
- size: `1164`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x1400ac440`
- `0x1400fe358`

## callees

- `0x1400029c0`
- `0x140006b68`
- `0x14000a010`
- `0x140021c60`
- `0x1400347a4`
- `0x1400347d4`
- `0x1400afa48`
- `0x1400fa594`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400afe89`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400afea2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400afe89`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400afea2`
- `ntoskrnl!ExAllocatePool2` at `0x1400afc9e`
- `ntoskrnl!ExAllocatePool2` at `0x1400afcc4`
- `ntoskrnl!ExAllocatePool2` at `0x1400afc9e`
- `ntoskrnl!ExAllocatePool2` at `0x1400afcc4`
- `winhvr!WinHvCheckSparseGpaPageVtlAccess` at `0x1400afd61`
- `winhvr!WinHvCheckSparseGpaPageVtlAccess` at `0x1400afd61`

## string_xrefs

- `0x1400afb2b`: `VsmmVsmpCheckVtlAccess`

## pseudocode

```c
__int64 __fastcall VsmmVsmpCheckVtlAccess(
        __int64 a1,
        unsigned __int64 a2,
        unsigned __int64 a3,
        char a4,
        unsigned int a5,
        _QWORD *a6,
        __int64 *a7)
{
  __int64 v7; // r12
  void *v9; // rdi
  __int64 v10; // rbx
  void *v13; // r13
  char v14; // r11
  int v15; // eax
  int v16; // esi
  __int64 v17; // r8
  char v18; // r11
  __int64 v19; // rdx
  unsigned __int64 v20; // r12
  _BYTE *v21; // rdx
  _BYTE *v22; // r8
  __int64 v23; // rsi
  __int64 v24; // rax
  unsigned __int64 v25; // r15
  unsigned __int64 v26; // rdi
  unsigned __int64 i; // rcx
  __int64 v28; // rcx
  int DefaultVtlPermissionSet; // r11d
  int v30; // r10d
  bool v31; // zf
  int v32; // edx
  char v33; // cl
  int v34; // edx
  int v35; // eax
  _BYTE *v37; // [rsp+20h] [rbp-E0h]
  _BYTE v38[8]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE *v39; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v40; // [rsp+50h] [rbp-B0h] BYREF
  __int64 Pool2; // [rsp+58h] [rbp-A8h]
  __int64 v42; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE *v43; // [rsp+68h] [rbp-98h] BYREF
  __int64 v44; // [rsp+70h] [rbp-90h]
  unsigned __int64 v45; // [rsp+78h] [rbp-88h] BYREF
  _QWORD *v46; // [rsp+80h] [rbp-80h]
  __int64 *v47; // [rsp+88h] [rbp-78h]
  __int64 v48; // [rsp+90h] [rbp-70h]
  char v49[32]; // [rsp+A0h] [rbp-60h] BYREF
  char v50[16]; // [rsp+C0h] [rbp-40h] BYREF
  char v51[16]; // [rsp+D0h] [rbp-30h] BYREF
  _QWORD *v52; // [rsp+E0h] [rbp-20h]
  __int64 v53; // [rsp+E8h] [rbp-18h]
  __int64 *v54; // [rsp+F0h] [rbp-10h]
  __int64 v55; // [rsp+F8h] [rbp-8h]
  __int64 v56; // [rsp+100h] [rbp+0h]
  __int64 v57; // [rsp+108h] [rbp+8h]
  _DWORD *v58; // [rsp+110h] [rbp+10h]
  __int64 v59; // [rsp+118h] [rbp+18h]
  __int64 v60; // [rsp+120h] [rbp+20h]
  _DWORD v61[2]; // [rsp+128h] [rbp+28h] BYREF
  _QWORD *v62; // [rsp+130h] [rbp+30h]
  __int64 v63; // [rsp+138h] [rbp+38h]
  __int64 *v64; // [rsp+140h] [rbp+40h]
  __int64 v65; // [rsp+148h] [rbp+48h]
  _BYTE *v66; // [rsp+150h] [rbp+50h]
  __int64 v67; // [rsp+158h] [rbp+58h]
  _BYTE v68[64]; // [rsp+160h] [rbp+60h] BYREF
  _BYTE v69[64]; // [rsp+1A0h] [rbp+A0h] BYREF

  v7 = *(_QWORD *)(a1 + 240);
  v9 = 0;
  v46 = a6;
  v10 = 0;
  v47 = a7;
  v38[0] = a4;
  v45 = 0;
  LODWORD(v39) = 0;
  v13 = 0;
  Pool2 = 0;
  v44 = v7;
  v42 = 0;
  v48 = v7 + 3736;
  VidObjectLockAcquireShared(v7 + 3736);
  v14 = v38[0];
  v15 = *(_DWORD *)(v7 + 8776);
  if ( ((1 << v38[0]) & v15) == 0 )
  {
    v16 = -1073741811;
    if ( (unsigned int)dword_140065110 > 2 )
    {
      if ( (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
      {
        tlgCreate1Sz_char(v50, "VsmmVsmpCheckVtlAccess");
        tlgCreate1Sz_char(v51, "onecore\\vm\\vid\\sys\\vsmm\\vsmmvsm.c");
        LODWORD(v39) = 3428;
        v52 = &v39;
        v53 = 4;
        v54 = &v42;
        LODWORD(v42) = -1073741811;
        v56 = v7 + 656;
        v55 = 4;
        v58 = v61;
        v60 = *(_QWORD *)(v7 + 128);
        v61[0] = *(unsigned __int16 *)(v7 + 120);
        v43 = *(_BYTE **)(v7 + 648);
        v62 = &v43;
        LODWORD(v40) = *(_DWORD *)(v7 + 8776);
        v64 = &v40;
        v66 = v38;
        v57 = 16;
        v59 = 2;
        v61[1] = v17;
        v63 = 8;
        v65 = 4;
        v38[0] = v18;
        v67 = 1;
        tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, &unk_14004DC6B, v17, 0, 12, v49);
      }
      v9 = 0;
    }
    goto LABEL_39;
  }
  v19 = -1;
  v40 = -1;
  if ( (v15 & 0xFFFFFFFE) != 0 )
  {
    if ( (*(_DWORD *)(a1 + 292) & 1) != 0 )
    {
      v20 = 8;
      v21 = v69;
      v43 = v69;
      v22 = v68;
      v39 = v68;
      if ( a3 <= 8 )
        goto LABEL_16;
      v23 = a3;
      if ( a3 >= 0x1FE )
        v23 = 510;
      Pool2 = ExAllocatePool2(256, 8 * v23, 1833788502);
      if ( Pool2 )
      {
        v24 = ExAllocatePool2(256, 8 * v23, 1833788502);
        v14 = v38[0];
        v13 = (void *)v24;
        if ( v24 )
        {
          v21 = (_BYTE *)Pool2;
          v20 = v23;
          v43 = (_BYTE *)Pool2;
          v22 = (_BYTE *)v24;
          v39 = (_BYTE *)v24;
          goto LABEL_16;
        }
      }
      else
      {
        v14 = v38[0];
      }
      v21 = v69;
      v22 = v68;
LABEL_16:
      v25 = a2 + a3;
      if ( a2 < v25 )
      {
        while ( 1 )
        {
          v26 = v25 - a2;
          if ( v25 - a2 >= v20 )
            v26 = v20;
          for ( i = 0; i < v26; ++i )
            *(_QWORD *)&v21[8 * i] = i + a2;
          v37 = v21;
          LOBYTE(v21) = v14;
          v16 = WinHvCheckSparseGpaPageVtlAccess(*(_QWORD *)(v44 + 648), v21, a5, v26, v37, v22, &v45);
          if ( v16 < 0 )
            goto LABEL_38;
          v28 = 0;
          v22 = v39;
          if ( v45 )
          {
            while ( !v39[8 * v28] )
            {
              if ( ++v28 >= v45 )
                goto LABEL_25;
            }
            v10 = *(_QWORD *)&v39[8 * v28];
            v19 = v28 + a2;
            v42 = v10;
            v40 = v28 + a2;
          }
          else
          {
LABEL_25:
            v19 = v40;
          }
          if ( (_BYTE)v42 )
            goto LABEL_34;
          v21 = v43;
          a2 += v26;
          v14 = v38[0];
          if ( a2 >= v25 )
          {
            v19 = v40;
            goto LABEL_34;
          }
        }
      }
      goto LABEL_33;
    }
    DefaultVtlPermissionSet = VsmmVsmGetDefaultVtlPermissionSet(v7, &v39);
    v31 = !_BitScanForward((unsigned int *)&v32, DefaultVtlPermissionSet & ~(v30 | (v30 - 1)));
    if ( v31 )
    {
LABEL_33:
      v19 = -1;
      goto LABEL_34;
    }
    while ( 1 )
    {
      v33 = v32;
      v34 = a5 & ~*(unsigned __int16 *)&v38[2 * (unsigned __int8)v32 + 6];
      if ( v34 )
        break;
      v31 = !_BitScanForward((unsigned int *)&v32, DefaultVtlPermissionSet & ~((1 << v33) | ((1 << v33) - 1)));
      if ( v31 )
        goto LABEL_33;
    }
    v35 = (unsigned __int8)v34;
    v19 = a2;
    LODWORD(v42) = ((v35 | ((v33 & 0xF) << 8)) << 8) | 1;
    v10 = v42;
  }
LABEL_34:
  v16 = 0;
  *v46 = v10;
  if ( !(_BYTE)v42 )
  {
LABEL_38:
    v9 = (void *)Pool2;
    goto LABEL_39;
  }
  v9 = (void *)Pool2;
  if ( v47 )
    *v47 = v19;
LABEL_39:
  VidObjectLockRelease(v48);
  if ( v13 )
    ExFreePoolWithTag(v13, 0x6D4D6456u);
  if ( v9 )
    ExFreePoolWithTag(v9, 0x6D4D6456u);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x1400afa48  push    rbp
0x1400afa4a  push    rbx
0x1400afa4b  push    rsi
0x1400afa4c  push    rdi
0x1400afa4d  push    r12
0x1400afa4f  push    r13
0x1400afa51  push    r14
0x1400afa53  push    r15
0x1400afa55  lea     rbp, [rsp-0F8h]
0x1400afa5d  sub     rsp, 1F8h
0x1400afa64  mov     rax, cs:__security_cookie
0x1400afa6b  xor     rax, rsp
0x1400afa6e  mov     [rbp+130h+var_50], rax
0x1400afa75  mov     r12, [rcx+0F0h]
0x1400afa7c  mov     rsi, rcx
0x1400afa7f  mov     rax, [rbp+130h+arg_28]
0x1400afa86  xor     edi, edi
0x1400afa88  mov     [rbp+130h+var_1B0], rax
0x1400afa8c  xor     ebx, ebx
0x1400afa8e  mov     rax, [rbp+130h+arg_30]
0x1400afa95  mov     r15, r8
0x1400afa98  mov     [rbp+130h+var_1A8], rax
0x1400afa9c  mov     r14, rdx
0x1400afa9f  lea     rax, [r12+0E98h]
0x1400afaa7  mov     [rsp+230h+var_1F0], r9b
0x1400afaac  mov     rcx, rax
0x1400afaaf  mov     [rsp+230h+var_1B8], 0
0x1400afab8  mov     dword ptr [rsp+230h+var_1E8], 0
0x1400afac0  xor     r13d, r13d
0x1400afac3  mov     [rsp+230h+var_1D8], rdi
0x1400afac8  mov     [rsp+230h+var_1C0], r12
0x1400afacd  mov     [rsp+230h+var_1D0], rbx
0x1400afad2  mov     [rbp+130h+var_1A0], rax
0x1400afad6  call    VidObjectLockAcquireShared
0x1400afadb  mov     r11b, [rsp+230h+var_1F0]
0x1400afae0  lea     r10d, [rdi+1]
0x1400afae4  mov     eax, [r12+2248h]
0x1400afaec  mov     cl, r11b
0x1400afaef  shl     r10d, cl
0x1400afaf2  test    eax, r10d
0x1400afaf5  jnz     loc_1400AFC36
0x1400afafb  mov     eax, cs:dword_140065110
0x1400afb01  mov     esi, 0C000000Dh
0x1400afb06  cmp     eax, 2
0x1400afb09  jbe     loc_1400AFE73
0x1400afb0f  mov     edx, 100h
0x1400afb14  lea     rcx, dword_140065110
0x1400afb1b  call    _tlgKeywordOn
0x1400afb20  xor     r8d, r8d
0x1400afb23  test    al, al
0x1400afb25  jz      loc_1400AFC2E
0x1400afb2b  lea     rdx, aVsmmvsmpcheckv; "VsmmVsmpCheckVtlAccess"
0x1400afb32  lea     rcx, [rbp+130h+var_170]
0x1400afb36  call    _tlgCreate1Sz_char
0x1400afb3b  lea     rdx, aOnecoreVmVidSy_63; "onecore\\vm\\vid\\sys\\vsmm\\vsmmvsm.c"
0x1400afb42  lea     rcx, [rbp+130h+var_160]
0x1400afb46  call    _tlgCreate1Sz_char
0x1400afb4b  lea     rax, [rsp+230h+var_1E8]
0x1400afb50  mov     dword ptr [rsp+230h+var_1E8], 0D64h
0x1400afb58  mov     [rbp+130h+var_150], rax
0x1400afb5c  lea     rdx, unk_14004DC6B
0x1400afb63  lea     rax, [rsp+230h+var_1D0]
0x1400afb68  mov     [rbp+130h+var_148], 4
0x1400afb70  mov     [rbp+130h+var_140], rax
0x1400afb74  lea     rcx, dword_140065110
0x1400afb7b  lea     rax, [r12+290h]
0x1400afb83  mov     dword ptr [rsp+230h+var_1D0], esi
0x1400afb87  mov     [rbp+130h+var_130], rax
0x1400afb8b  xor     r9d, r9d
0x1400afb8e  lea     rax, [rbp+130h+var_108]
0x1400afb92  mov     [rbp+130h+var_138], 4
0x1400afb9a  mov     [rbp+130h+var_120], rax
0x1400afb9e  mov     rax, [r12+80h]
0x1400afba6  mov     [rbp+130h+var_110], rax
0x1400afbaa  movzx   eax, word ptr [r12+78h]
0x1400afbb0  mov     [rbp+130h+var_108], eax
0x1400afbb3  mov     rax, [r12+288h]
0x1400afbbb  mov     [rsp+230h+var_1C8], rax
0x1400afbc0  lea     rax, [rsp+230h+var_1C8]
0x1400afbc5  mov     [rbp+130h+var_100], rax
0x1400afbc9  mov     eax, [r12+2248h]
0x1400afbd1  mov     dword ptr [rsp+230h+var_1E0], eax
0x1400afbd5  lea     rax, [rsp+230h+var_1E0]
0x1400afbda  mov     [rbp+130h+var_F0], rax
0x1400afbde  lea     rax, [rsp+230h+var_1F0]
0x1400afbe3  mov     [rbp+130h+var_E0], rax
0x1400afbe7  lea     rax, [rbp+130h+var_190]
0x1400afbeb  mov     [rsp+230h+var_208], rax
0x1400afbf0  mov     dword ptr [rsp+230h+var_210], 0Ch
0x1400afbf8  mov     [rbp+130h+var_128], 10h
0x1400afc00  mov     [rbp+130h+var_118], 2
0x1400afc08  mov     [rbp+130h+var_104], r8d
0x1400afc0c  mov     [rbp+130h+var_F8], 8
0x1400afc14  mov     [rbp+130h+var_E8], 4
0x1400afc1c  mov     [rsp+230h+var_1F0], r11b
0x1400afc21  mov     [rbp+130h+var_D8], 1
0x1400afc29  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400afc2e  mov     rdi, rbx
0x1400afc31  jmp     loc_1400AFE73
0x1400afc36  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1400afc3a  mov     [rsp+230h+var_1E0], rdx
0x1400afc3f  test    eax, 0FFFFFFFEh
0x1400afc44  jz      loc_1400AFE2C
0x1400afc4a  mov     eax, [rsi+124h]
0x1400afc50  test    al, 1
0x1400afc52  jz      loc_1400AFDD8
0x1400afc58  lea     r12d, [rdx+9]
0x1400afc5c  lea     rdx, [rbp+130h+var_90]
0x1400afc63  mov     [rsp+230h+var_1C8], rdx
0x1400afc68  lea     r8, [rbp+130h+var_D0]
0x1400afc6c  mov     [rsp+230h+var_1E8], r8
0x1400afc71  cmp     r15, r12
0x1400afc74  jbe     loc_1400AFD04
0x1400afc7a  mov     eax, 1FEh
0x1400afc7f  mov     rsi, r15
0x1400afc82  cmp     r15, rax
0x1400afc85  mov     edi, 100h
0x1400afc8a  mov     r8d, 6D4D6456h
0x1400afc90  mov     ecx, edi
0x1400afc92  cmovnb  rsi, rax
0x1400afc96  lea     rdx, ds:0[rsi*8]
0x1400afc9e  call    cs:__imp_ExAllocatePool2
0x1400afca5  nop     dword ptr [rax+rax+00h]
0x1400afcaa  mov     [rsp+230h+var_1D8], rax
0x1400afcaf  test    rax, rax
0x1400afcb2  jz      short loc_1400AFCF4
0x1400afcb4  mov     r8d, 6D4D6456h
0x1400afcba  lea     rdx, ds:0[rsi*8]
0x1400afcc2  mov     ecx, edi
0x1400afcc4  call    cs:__imp_ExAllocatePool2
0x1400afccb  nop     dword ptr [rax+rax+00h]
0x1400afcd0  mov     r11b, [rsp+230h+var_1F0]
0x1400afcd5  mov     r13, rax
0x1400afcd8  test    rax, rax
0x1400afcdb  jz      short loc_1400AFCF9
0x1400afcdd  mov     rdx, [rsp+230h+var_1D8]
0x1400afce2  mov     r12, rsi
0x1400afce5  mov     [rsp+230h+var_1C8], rdx
0x1400afcea  mov     r8, rax
0x1400afced  mov     [rsp+230h+var_1E8], rax
0x1400afcf2  jmp     short loc_1400AFD04
0x1400afcf4  mov     r11b, [rsp+230h+var_1F0]
0x1400afcf9  lea     rdx, [rbp+130h+var_90]
0x1400afd00  lea     r8, [rbp+130h+var_D0]
0x1400afd04  add     r15, r14
0x1400afd07  cmp     r14, r15
0x1400afd0a  jnb     loc_1400AFE28
0x1400afd10  mov     rdi, r15
0x1400afd13  sub     rdi, r14
0x1400afd16  cmp     rdi, r12
0x1400afd19  cmovnb  rdi, r12
0x1400afd1d  xor     ecx, ecx
0x1400afd1f  test    rdi, rdi
0x1400afd22  jz      short loc_1400AFD34
0x1400afd24  lea     rax, [rcx+r14]
0x1400afd28  mov     [rdx+rcx*8], rax
0x1400afd2c  inc     rcx
0x1400afd2f  cmp     rcx, rdi
0x1400afd32  jb      short loc_1400AFD24
0x1400afd34  lea     rax, [rsp+230h+var_1B8]
0x1400afd39  mov     r9, rdi
0x1400afd3c  mov     [rsp+230h+var_200], rax
0x1400afd41  mov     rax, [rsp+230h+var_1C0]
0x1400afd46  mov     [rsp+230h+var_208], r8
0x1400afd4b  mov     r8d, [rbp+130h+arg_20]
0x1400afd52  mov     [rsp+230h+var_210], rdx
0x1400afd57  mov     dl, r11b
0x1400afd5a  mov     rcx, [rax+288h]
0x1400afd61  call    cs:__imp_WinHvCheckSparseGpaPageVtlAccess
0x1400afd68  nop     dword ptr [rax+rax+00h]
0x1400afd6d  mov     esi, eax
0x1400afd6f  test    eax, eax
0x1400afd71  js      loc_1400AFE6E
0x1400afd77  mov     rdx, [rsp+230h+var_1B8]
0x1400afd7c  xor     ecx, ecx
0x1400afd7e  mov     r8, [rsp+230h+var_1E8]
0x1400afd83  test    rdx, rdx
0x1400afd86  jz      short loc_1400AFD97
0x1400afd88  cmp     byte ptr [r8+rcx*8], 0
0x1400afd8d  jnz     short loc_1400AFDC4
0x1400afd8f  inc     rcx
0x1400afd92  cmp     rcx, rdx
0x1400afd95  jb      short loc_1400AFD88
0x1400afd97  mov     rdx, [rsp+230h+var_1E0]
0x1400afd9c  cmp     byte ptr [rsp+230h+var_1D0], 0
0x1400afda1  jnz     loc_1400AFE2C
0x1400afda7  mov     rdx, [rsp+230h+var_1C8]
0x1400afdac  add     r14, rdi
0x1400afdaf  mov     r11b, [rsp+230h+var_1F0]
0x1400afdb4  cmp     r14, r15
0x1400afdb7  jb      loc_1400AFD10
0x1400afdbd  mov     rdx, [rsp+230h+var_1E0]
0x1400afdc2  jmp     short loc_1400AFE2C
0x1400afdc4  mov     rbx, [r8+rcx*8]
0x1400afdc8  lea     rdx, [rcx+r14]
0x1400afdcc  mov     [rsp+230h+var_1D0], rbx
0x1400afdd1  mov     [rsp+230h+var_1E0], rdx
0x1400afdd6  jmp     short loc_1400AFD9C
0x1400afdd8  lea     rdx, [rsp+230h+var_1E8]
0x1400afddd  mov     rcx, r12
0x1400afde0  call    VsmmVsmGetDefaultVtlPermissionSet
0x1400afde5  lea     ecx, [r10-1]
0x1400afde9  mov     r11d, eax
0x1400afdec  or      ecx, r10d
0x1400afdef  not     ecx
0x1400afdf1  and     ecx, eax
0x1400afdf3  bsf     edx, ecx
0x1400afdf6  setnz   cl
0x1400afdf9  test    cl, cl
0x1400afdfb  jz      short loc_1400AFE28
0x1400afdfd  movzx   ecx, dl
0x1400afe00  movzx   edx, [rsp+rcx*2+230h+var_1EA]
0x1400afe05  not     edx
0x1400afe07  and     edx, [rbp+130h+arg_20]
0x1400afe0d  jnz     short loc_1400AFE4F
0x1400afe0f  lea     eax, [rdx+1]
0x1400afe12  shl     eax, cl
0x1400afe14  lea     ecx, [rax-1]
0x1400afe17  or      ecx, eax
0x1400afe19  not     ecx
0x1400afe1b  and     ecx, r11d
0x1400afe1e  bsf     edx, ecx
0x1400afe21  setnz   al
0x1400afe24  test    al, al
0x1400afe26  jnz     short loc_1400AFDFD
0x1400afe28  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1400afe2c  mov     rax, [rbp+130h+var_1B0]
0x1400afe30  xor     esi, esi
0x1400afe32  mov     [rax], rbx
0x1400afe35  cmp     byte ptr [rsp+230h+var_1D0], sil
0x1400afe3a  jz      short loc_1400AFE6E
0x1400afe3c  mov     rax, [rbp+130h+var_1A8]
0x1400afe40  mov     rdi, [rsp+230h+var_1D8]
0x1400afe45  test    rax, rax
0x1400afe48  jz      short loc_1400AFE73
0x1400afe4a  mov     [rax], rdx
0x1400afe4d  jmp     short loc_1400AFE73
0x1400afe4f  and     ecx, 0Fh
0x1400afe52  movzx   eax, dl
0x1400afe55  shl     ecx, 8
0x1400afe58  mov     rdx, r14
0x1400afe5b  or      ecx, eax
0x1400afe5d  shl     ecx, 8
0x1400afe60  or      ecx, 1
0x1400afe63  mov     dword ptr [rsp+230h+var_1D0], ecx
0x1400afe67  mov     rbx, [rsp+230h+var_1D0]
0x1400afe6c  jmp     short loc_1400AFE2C
0x1400afe6e  mov     rdi, [rsp+230h+var_1D8]
0x1400afe73  mov     rcx, [rbp+130h+var_1A0]
0x1400afe77  call    VidObjectLockRelease
0x1400afe7c  test    r13, r13
0x1400afe7f  jz      short loc_1400AFE95
0x1400afe81  mov     edx, 6D4D6456h; Tag
0x1400afe86  mov     rcx, r13; P
0x1400afe89  call    cs:__imp_ExFreePoolWithTag
0x1400afe90  nop     dword ptr [rax+rax+00h]
0x1400afe95  test    rdi, rdi
0x1400afe98  jz      short loc_1400AFEAE
0x1400afe9a  mov     edx, 6D4D6456h; Tag
0x1400afe9f  mov     rcx, rdi; P
0x1400afea2  call    cs:__imp_ExFreePoolWithTag
0x1400afea9  nop     dword ptr [rax+rax+00h]
0x1400afeae  mov     eax, esi
0x1400afeb0  mov     rcx, [rbp+130h+var_50]
0x1400afeb7  xor     rcx, rsp; StackCookie
0x1400afeba  call    __security_check_cookie
0x1400afebf  add     rsp, 1F8h
0x1400afec6  pop     r15
0x1400afec8  pop     r14
0x1400afeca  pop     r13
0x1400afecc  pop     r12
0x1400afece  pop     rdi
0x1400afecf  pop     rsi
0x1400afed0  pop     rbx
0x1400afed1  pop     rbp
0x1400afed2  retn
```
