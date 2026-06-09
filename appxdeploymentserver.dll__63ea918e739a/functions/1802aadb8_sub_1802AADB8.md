# sub_1802AADB8

- ea: `0x1802aadb8`
- end: `0x1802ab2c8`
- name: `sub_1802AADB8`
- size: `1296`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180096578`

## callees

- `0x180005eb0`
- `0x18001f1a4`
- `0x180024b6c`
- `0x180039898`
- `0x180059ef8`
- `0x18005a63c`
- `0x18007199c`
- `0x180071bac`
- `0x1800738bc`
- `0x180101840`
- `0x18011edd8`
- `0x18015fad0`
- `0x1801931d8`
- `0x1802aa634`
- `0x1802aab14`
- `0x1802aadb8`
- `0x1803e37d0`

## import_xrefs

- `api-ms-win-appmodel-runtime-internal-l1-1-1!UpdatePackageStatus` at `0x1802aaf4c`
- `api-ms-win-appmodel-runtime-internal-l1-1-1!UpdatePackageStatus` at `0x1802aafef`
- `api-ms-win-appmodel-runtime-internal-l1-1-1!UpdatePackageStatus` at `0x1802ab0ff`
- `api-ms-win-appmodel-runtime-internal-l1-1-1!UpdatePackageStatus` at `0x1802ab1bb`
- `api-ms-win-appmodel-runtime-internal-l1-1-1!UpdatePackageStatus` at `0x1802ab233`
- `api-ms-win-appmodel-runtime-internal-l1-1-1!UpdatePackageStatus` at `0x1802ab25b`
- `api-ms-win-appmodel-runtime-internal-l1-1-1!UpdatePackageStatus` at `0x1802aaf4c`
- `api-ms-win-appmodel-runtime-internal-l1-1-1!UpdatePackageStatus` at `0x1802aafef`
- `api-ms-win-appmodel-runtime-internal-l1-1-1!UpdatePackageStatus` at `0x1802ab0ff`
- `api-ms-win-appmodel-runtime-internal-l1-1-1!UpdatePackageStatus` at `0x1802ab1bb`
- `api-ms-win-appmodel-runtime-internal-l1-1-1!UpdatePackageStatus` at `0x1802ab233`
- `api-ms-win-appmodel-runtime-internal-l1-1-1!UpdatePackageStatus` at `0x1802ab25b`

## string_xrefs

- `0x1802aaee0`: `onecore\admin\appmodel\common\packagestatus.cpp`
- `0x1802aaf12`: `onecore\admin\appmodel\common\packagestatus.cpp`
- `0x1802aaf5d`: `onecore\admin\appmodel\common\packagestatus.cpp`
- `0x1802aaf9a`: `onecore\admin\appmodel\common\packagestatus.cpp`
- `0x1802ab000`: `onecore\admin\appmodel\common\packagestatus.cpp`
- `0x1802ab04d`: `onecore\admin\appmodel\common\packagestatus.cpp`
- `0x1802ab0b4`: `onecore\admin\appmodel\common\packagestatus.cpp`
- `0x1802ab183`: `onecore\admin\appmodel\common\packagestatus.cpp`
- `0x1802ab26a`: `onecore\admin\appmodel\common\packagestatus.cpp`
- `0x1802ab2b2`: `onecore\admin\appmodel\common\packagestatus.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall sub_1802AADB8(__int64 a1, int a2, int a3, unsigned int a4, BOOL a5, int a6, __int64 a7, _BYTE *a8)
{
  unsigned int v12; // edi
  _DWORD *v13; // rax
  int v14; // r8d
  int v15; // r9d
  int v16; // r15d
  __int64 v17; // r12
  int v18; // eax
  int v19; // ebx
  int v20; // eax
  int v21; // r8d
  int v22; // r9d
  unsigned int v23; // r15d
  bool v24; // zf
  unsigned int updated; // eax
  bool v27; // zf
  bool v28; // zf
  __int64 v29; // r13
  char v30; // bl
  _BYTE *v31; // r15
  unsigned int v32; // eax
  int v33; // eax
  int v34; // r8d
  unsigned int v35; // edi
  __int64 v36; // rax
  int v37; // eax
  int v38; // r9d
  int v39; // r15d
  int v40; // ecx
  bool v41; // dl
  _BYTE *v42; // r15
  unsigned int v43; // eax
  __int64 v44; // rdx
  __int64 v45; // rdx
  int v46; // eax
  _BYTE *v47; // r15
  _QWORD v48[2]; // [rsp+60h] [rbp-49h] BYREF
  __int64 v49; // [rsp+70h] [rbp-39h] BYREF
  unsigned int v50; // [rsp+78h] [rbp-31h] BYREF
  int v51; // [rsp+7Ch] [rbp-2Dh] BYREF
  _QWORD v52[2]; // [rsp+80h] [rbp-29h] BYREF
  __int64 v53; // [rsp+90h] [rbp-19h]
  char v54; // [rsp+98h] [rbp-11h]
  __int64 v55; // [rsp+A0h] [rbp-9h] BYREF
  __int64 v56[7]; // [rsp+A8h] [rbp-1h] BYREF
  void *retaddr; // [rsp+E8h] [rbp+3Fh]
  unsigned int v58; // [rsp+F8h] [rbp+4Fh] BYREF
  int v59; // [rsp+100h] [rbp+57h]

  v59 = a3;
  v12 = a5;
  if ( (a5 & 6) != 0
    && (v13 = (_DWORD *)sub_180039898(a1), *v13 > 4u)
    && (unsigned __int8)sub_180101840(v13, 0x200000000000LL) )
  {
    v55 = 0x2000000;
    v16 = a6;
    a5 = a6;
    v58 = v12;
    v50 = a4;
    v51 = a3;
    LODWORD(v49) = a2;
    v56[0] = a1;
    sub_180005EB0(
      v15,
      (unsigned int)&byte_180504F27,
      v14,
      v15,
      (__int64)v56,
      (__int64)&v49,
      (__int64)&v51,
      (__int64)&v50,
      (__int64)&v58,
      (__int64)&a5,
      (__int64)&v55);
  }
  else
  {
    v16 = a6;
  }
  if ( (a2 & 4) != 0 && ((v12 & 4) != 0 || v16 == 2 && (a4 & 4) != 0) )
    return 0;
  v49 = 0;
  a5 = 0;
  v17 = a7;
  v18 = sub_1802AA634(a1, a7, &a5, &v49);
  v19 = v18;
  if ( v18 < 0 )
    sub_18001F1A4(retaddr, 938, "onecore\\admin\\appmodel\\common\\packagestatus.cpp", (unsigned int)v18);
  v48[0] = 0;
  v48[1] = 0;
  v20 = sub_180059EF8(v48, 0);
  v23 = v20;
  if ( v20 < 0 )
  {
    sub_180024B6C(retaddr, 941, "onecore\\admin\\appmodel\\common\\packagestatus.cpp", (unsigned int)v20);
    v24 = LODWORD(v48[0]) == 0;
LABEL_14:
    if ( !v24 )
      sub_18005A63C(v48);
    return v23;
  }
  if ( v19 == -2147009295 )
  {
    updated = UpdatePackageStatus(a1, a4, v12);
    if ( updated )
    {
      v19 = sub_18011EDD8(retaddr, 946, "onecore\\admin\\appmodel\\common\\packagestatus.cpp", updated);
LABEL_20:
      v27 = LODWORD(v48[0]) == 0;
LABEL_21:
      if ( !v27 )
        sub_18005A63C(v48);
      return (unsigned int)v19;
    }
    v28 = LODWORD(v48[0]) == 0;
    goto LABEL_61;
  }
  if ( v19 < 0 )
  {
    sub_180024B6C(retaddr, 951, "onecore\\admin\\appmodel\\common\\packagestatus.cpp", (unsigned int)v19);
    goto LABEL_20;
  }
  v29 = v49;
  v30 = 1;
  if ( ((a5 - 2) & 0xFFFFFFFD) != 0 )
  {
    v52[0] = 0;
    v52[1] = 0;
    v53 = 0;
    v54 = 1;
    v36 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v17 + 8LL))(v17);
    v37 = sub_18015FAD0(v36, v29, v52);
    v39 = v37;
    if ( v37 < 0 )
      sub_18001F1A4(retaddr, 979, "onecore\\admin\\appmodel\\common\\packagestatus.cpp", (unsigned int)v37);
    v40 = v59 & 0x4000307;
    v41 = (v59 & 0x4000307) != 0;
    LOBYTE(a5) = v41;
    if ( v39 >= 0 && v53 )
    {
      if ( v40 )
      {
        v42 = a8;
        if ( !*a8 )
        {
          v43 = UpdatePackageStatus(a1, a4, v12);
          if ( v43 )
          {
            v44 = 1005;
LABEL_70:
            v19 = sub_18011EDD8(retaddr, v44, "onecore\\admin\\appmodel\\common\\packagestatus.cpp", v43);
LABEL_71:
            sub_180071BAC(v52);
            goto LABEL_34;
          }
          *v42 = 1;
          v41 = a5;
        }
        LOBYTE(v38) = v41;
        v19 = sub_1802AAB14(v17, v29, (unsigned int)v52, v38, a6, 0);
        if ( v19 < 0 )
        {
          v45 = 1008;
LABEL_75:
          sub_180024B6C(retaddr, v45, "onecore\\admin\\appmodel\\common\\packagestatus.cpp", (unsigned int)v19);
          goto LABEL_71;
        }
      }
      else
      {
        LOBYTE(a5) = 0;
        LOBYTE(v38) = (v59 & 0x4000307) != 0;
        v46 = sub_1802AAB14(v17, v29, (unsigned int)v52, v38, a6, (__int64)&a5);
        v23 = v46;
        if ( v46 < 0 )
        {
          sub_180024B6C(retaddr, 1016, "onecore\\admin\\appmodel\\common\\packagestatus.cpp", (unsigned int)v46);
          sub_180071BAC(v52);
          v24 = LODWORD(v48[0]) == 0;
          goto LABEL_14;
        }
        if ( a5 )
        {
          v43 = UpdatePackageStatus(a1, a4 | 0x40, v12);
          if ( v43 )
          {
            v44 = 1020;
            goto LABEL_70;
          }
          *a8 = 1;
        }
        else
        {
          v43 = UpdatePackageStatus(a1, a4, v12 | 0x40);
          if ( v43 )
          {
            v44 = 1026;
            goto LABEL_70;
          }
        }
      }
    }
    else if ( v40 )
    {
      v47 = a8;
      if ( !*a8 )
      {
        v43 = UpdatePackageStatus(a1, a4, v12);
        if ( v43 )
        {
          v44 = 989;
          goto LABEL_70;
        }
        *v47 = 1;
      }
    }
    else
    {
      v19 = sub_18007199C(v17, a1, v29);
      if ( v19 < 0 )
      {
        v45 = 995;
        goto LABEL_75;
      }
    }
    v30 = 0;
    sub_180071BAC(v52);
    goto LABEL_58;
  }
  if ( (v59 & 0x4000307) == 0 || (LOBYTE(a5) = 1, (v59 & 0x4000307) == 1) )
    LOBYTE(a5) = 0;
  v31 = a8;
  if ( !*a8 )
  {
    v32 = UpdatePackageStatus(a1, a4, v12);
    if ( v32 )
    {
      v19 = sub_18011EDD8(retaddr, 969, "onecore\\admin\\appmodel\\common\\packagestatus.cpp", v32);
LABEL_34:
      v27 = LODWORD(v48[0]) == 0;
      goto LABEL_21;
    }
    *v31 = 1;
  }
  LOBYTE(v22) = 1;
  LOBYTE(v21) = a5;
  v33 = sub_1800738BC(v17, a1, v21, v22, a6 == 2);
  v35 = v33;
  if ( v33 >= 0 )
  {
LABEL_58:
    if ( (v59 & 4) != 0 )
    {
      LOBYTE(v34) = v30;
      sub_1801931D8(a1, v29, v34, v59, v17);
    }
    v28 = LODWORD(v48[0]) == 0;
LABEL_61:
    if ( !v28 )
      sub_18005A63C(v48);
    return 0;
  }
  sub_180024B6C(retaddr, 973, "onecore\\admin\\appmodel\\common\\packagestatus.cpp", (unsigned int)v33);
  if ( LODWORD(v48[0]) )
    sub_18005A63C(v48);
  return v35;
}

```

## disassembly

```asm
0x1802aadb8  mov     [rsp-8+arg_0], rbx
0x1802aadbd  mov     [rsp-8+arg_10], r8d
0x1802aadc2  push    rbp
0x1802aadc3  push    rsi
0x1802aadc4  push    rdi
0x1802aadc5  push    r12
0x1802aadc7  push    r13
0x1802aadc9  push    r14
0x1802aadcb  push    r15
0x1802aadcd  lea     rbp, [rsp-7]
0x1802aadd2  sub     rsp, 0B0h
0x1802aadd9  mov     r14d, r9d
0x1802aaddc  mov     r12d, r8d
0x1802aaddf  mov     ebx, edx
0x1802aade1  mov     rsi, rcx
0x1802aade4  mov     edi, [rbp+37h+arg_20]
0x1802aade7  xor     r13d, r13d
0x1802aadea  test    dil, 6
0x1802aadee  jz      loc_1802AAE91
0x1802aadf4  call    sub_180039898
0x1802aadf9  mov     r9, rax
0x1802aadfc  mov     r8d, [rax]
0x1802aadff  cmp     r8d, 4
0x1802aae03  jbe     loc_1802AAE91
0x1802aae09  mov     rdx, 200000000000h
0x1802aae13  mov     rcx, rax
0x1802aae16  call    sub_180101840
0x1802aae1b  test    al, al
0x1802aae1d  jz      short loc_1802AAE91
0x1802aae1f  mov     [rbp+37h+var_40], 2000000h
0x1802aae27  mov     r15d, [rbp+37h+arg_28]
0x1802aae2b  mov     [rbp+37h+arg_20], r15d
0x1802aae2f  mov     [rbp+37h+arg_8], edi
0x1802aae32  mov     [rbp+37h+var_68], r14d
0x1802aae36  mov     [rbp+37h+var_64], r12d
0x1802aae3a  mov     dword ptr [rbp+37h+var_70], ebx
0x1802aae3d  mov     [rbp+37h+var_38], rsi
0x1802aae41  lea     rax, [rbp+37h+var_40]
0x1802aae45  mov     [rsp+0E0h+var_90], rax
0x1802aae4a  lea     rax, [rbp+37h+arg_20]
0x1802aae4e  mov     [rsp+0E0h+var_98], rax
0x1802aae53  lea     rax, [rbp+37h+arg_8]
0x1802aae57  mov     [rsp+0E0h+var_A0], rax
0x1802aae5c  lea     rax, [rbp+37h+var_68]
0x1802aae60  mov     [rsp+0E0h+var_A8], rax
0x1802aae65  lea     rax, [rbp+37h+var_64]
0x1802aae69  mov     [rsp+0E0h+var_B0], rax
0x1802aae6e  lea     rax, [rbp+37h+var_70]
0x1802aae72  mov     [rsp+0E0h+var_B8], rax
0x1802aae77  lea     rax, [rbp+37h+var_38]
0x1802aae7b  mov     [rsp+0E0h+var_C0], rax
0x1802aae80  lea     rdx, byte_180504F27
0x1802aae87  mov     rcx, r9
0x1802aae8a  call    sub_180005EB0
0x1802aae8f  jmp     short loc_1802AAE95
0x1802aae91  mov     r15d, [rbp+37h+arg_28]
0x1802aae95  test    bl, 4
0x1802aae98  jz      short loc_1802AAEB4
0x1802aae9a  test    dil, 4
0x1802aae9e  jnz     loc_1802AB20D
0x1802aaea4  cmp     r15d, 2
0x1802aaea8  jnz     short loc_1802AAEB4
0x1802aaeaa  test    r14b, 4
0x1802aaeae  jnz     loc_1802AB20D
0x1802aaeb4  mov     [rbp+37h+var_70], r13
0x1802aaeb8  mov     [rbp+37h+arg_20], r13d
0x1802aaebc  lea     r9, [rbp+37h+var_70]
0x1802aaec0  lea     r8, [rbp+37h+arg_20]
0x1802aaec4  mov     r12, [rbp+37h+arg_30]
0x1802aaec8  mov     rdx, r12
0x1802aaecb  mov     rcx, rsi
0x1802aaece  call    sub_1802AA634
0x1802aaed3  mov     ebx, eax
0x1802aaed5  mov     rcx, [rbp+3Fh]
0x1802aaed9  test    eax, eax
0x1802aaedb  jns     short loc_1802AAEF1
0x1802aaedd  mov     r9d, eax
0x1802aaee0  lea     r8, aOnecoreAdminAp_90; "onecore\\admin\\appmodel\\common\\packa"...
0x1802aaee7  mov     edx, 3AAh
0x1802aaeec  call    sub_18001F1A4
0x1802aaef1  mov     [rbp+37h+var_80], r13
0x1802aaef5  mov     [rbp+37h+var_78], r13
0x1802aaef9  xor     edx, edx
0x1802aaefb  lea     rcx, [rbp+37h+var_80]
0x1802aaeff  call    sub_180059EF8
0x1802aaf04  mov     r15d, eax
0x1802aaf07  test    eax, eax
0x1802aaf09  jns     short loc_1802AAF3B
0x1802aaf0b  mov     rcx, [rbp+3Fh]
0x1802aaf0f  mov     r9d, eax
0x1802aaf12  lea     r8, aOnecoreAdminAp_90; "onecore\\admin\\appmodel\\common\\packa"...
0x1802aaf19  mov     edx, 3ADh
0x1802aaf1e  call    sub_180024B6C
0x1802aaf23  nop
0x1802aaf24  cmp     dword ptr [rbp+37h+var_80], r13d
0x1802aaf28  jz      short loc_1802AAF33
0x1802aaf2a  lea     rcx, [rbp+37h+var_80]
0x1802aaf2e  call    sub_18005A63C
0x1802aaf33  mov     eax, r15d
0x1802aaf36  jmp     loc_1802AB20F
0x1802aaf3b  cmp     ebx, 80073CF1h
0x1802aaf41  jnz     short loc_1802AAF8F
0x1802aaf43  mov     r8d, edi
0x1802aaf46  mov     edx, r14d
0x1802aaf49  mov     rcx, rsi
0x1802aaf4c  call    cs:UpdatePackageStatus
0x1802aaf52  test    eax, eax
0x1802aaf54  jz      short loc_1802AAF86
0x1802aaf56  mov     rcx, [rbp+3Fh]
0x1802aaf5a  mov     r9d, eax
0x1802aaf5d  lea     r8, aOnecoreAdminAp_90; "onecore\\admin\\appmodel\\common\\packa"...
0x1802aaf64  mov     edx, 3B2h
0x1802aaf69  call    sub_18011EDD8
0x1802aaf6e  mov     ebx, eax
0x1802aaf70  cmp     dword ptr [rbp+37h+var_80], r13d
0x1802aaf74  jz      short loc_1802AAF7F
0x1802aaf76  lea     rcx, [rbp+37h+var_80]
0x1802aaf7a  call    sub_18005A63C
0x1802aaf7f  mov     eax, ebx
0x1802aaf81  jmp     loc_1802AB20F
0x1802aaf86  cmp     dword ptr [rbp+37h+var_80], r13d
0x1802aaf8a  jmp     loc_1802AB202
0x1802aaf8f  test    ebx, ebx
0x1802aaf91  jns     short loc_1802AAFAD
0x1802aaf93  mov     rcx, [rbp+3Fh]
0x1802aaf97  mov     r9d, ebx
0x1802aaf9a  lea     r8, aOnecoreAdminAp_90; "onecore\\admin\\appmodel\\common\\packa"...
0x1802aafa1  mov     edx, 3B7h
0x1802aafa6  call    sub_180024B6C
0x1802aafab  jmp     short loc_1802AAF70
0x1802aafad  mov     eax, [rbp+37h+arg_20]
0x1802aafb0  add     eax, 0FFFFFFFEh
0x1802aafb3  mov     r13, [rbp+37h+var_70]
0x1802aafb7  mov     ebx, 1
0x1802aafbc  test    eax, 0FFFFFFFDh
0x1802aafc1  jnz     loc_1802AB075
0x1802aafc7  mov     eax, [rbp+37h+arg_10]
0x1802aafca  and     eax, 4000307h
0x1802aafcf  jz      short loc_1802AAFD8
0x1802aafd1  mov     byte ptr [rbp+37h+arg_20], bl
0x1802aafd4  cmp     eax, ebx
0x1802aafd6  jnz     short loc_1802AAFDC
0x1802aafd8  mov     byte ptr [rbp+37h+arg_20], 0
0x1802aafdc  mov     r15, [rbp+37h+arg_38]
0x1802aafe0  cmp     byte ptr [r15], 0
0x1802aafe4  jnz     short loc_1802AB01F
0x1802aafe6  mov     r8d, edi
0x1802aafe9  mov     edx, r14d
0x1802aafec  mov     rcx, rsi
0x1802aafef  call    cs:UpdatePackageStatus
0x1802aaff5  test    eax, eax
0x1802aaff7  jz      short loc_1802AB01C
0x1802aaff9  mov     rcx, [rbp+3Fh]
0x1802aaffd  mov     r9d, eax
0x1802ab000  lea     r8, aOnecoreAdminAp_90; "onecore\\admin\\appmodel\\common\\packa"...
0x1802ab007  mov     edx, 3C9h
0x1802ab00c  call    sub_18011EDD8
0x1802ab011  mov     ebx, eax
0x1802ab013  cmp     dword ptr [rbp+37h+var_80], 0
0x1802ab017  jmp     loc_1802AAF74
0x1802ab01c  mov     [r15], bl
0x1802ab01f  cmp     [rbp+37h+arg_28], 2
0x1802ab023  setz    al
0x1802ab026  mov     byte ptr [rsp+0E0h+var_C0], al
0x1802ab02a  mov     r9b, bl
0x1802ab02d  mov     r8b, byte ptr [rbp+37h+arg_20]
0x1802ab031  mov     rdx, rsi
0x1802ab034  mov     rcx, r12
0x1802ab037  call    sub_1800738BC
0x1802ab03c  mov     edi, eax
0x1802ab03e  test    eax, eax
0x1802ab040  jns     loc_1802AB1E0
0x1802ab046  mov     rcx, [rbp+3Fh]
0x1802ab04a  mov     r9d, eax
0x1802ab04d  lea     r8, aOnecoreAdminAp_90; "onecore\\admin\\appmodel\\common\\packa"...
0x1802ab054  mov     edx, 3CDh
0x1802ab059  call    sub_180024B6C
0x1802ab05e  nop
0x1802ab05f  cmp     dword ptr [rbp+37h+var_80], 0
0x1802ab063  jz      short loc_1802AB06E
0x1802ab065  lea     rcx, [rbp+37h+var_80]
0x1802ab069  call    sub_18005A63C
0x1802ab06e  mov     eax, edi
0x1802ab070  jmp     loc_1802AB20F
0x1802ab075  xor     eax, eax
0x1802ab077  mov     [rbp+37h+var_60], rax
0x1802ab07b  mov     [rbp+37h+var_58], rax
0x1802ab07f  mov     [rbp+37h+var_50], rax
0x1802ab083  mov     [rbp+37h+var_48], bl
0x1802ab086  mov     rax, [r12]
0x1802ab08a  mov     rcx, r12
0x1802ab08d  mov     rax, [rax+8]
0x1802ab091  call    cs:__guard_dispatch_icall_fptr
0x1802ab097  lea     r8, [rbp+37h+var_60]
0x1802ab09b  mov     rdx, r13
0x1802ab09e  mov     rcx, rax
0x1802ab0a1  call    sub_18015FAD0
0x1802ab0a6  mov     r15d, eax
0x1802ab0a9  mov     rcx, [rbp+3Fh]
0x1802ab0ad  test    eax, eax
0x1802ab0af  jns     short loc_1802AB0C5
0x1802ab0b1  mov     r9d, eax
0x1802ab0b4  lea     r8, aOnecoreAdminAp_90; "onecore\\admin\\appmodel\\common\\packa"...
0x1802ab0bb  mov     edx, 3D3h
0x1802ab0c0  call    sub_18001F1A4
0x1802ab0c5  mov     ecx, [rbp+37h+arg_10]
0x1802ab0c8  and     ecx, 4000307h
0x1802ab0ce  setnz   dl
0x1802ab0d1  mov     byte ptr [rbp+37h+arg_20], dl
0x1802ab0d4  test    r15d, r15d
0x1802ab0d7  js      loc_1802AB244
0x1802ab0dd  cmp     [rbp+37h+var_50], 0
0x1802ab0e2  jz      loc_1802AB244
0x1802ab0e8  test    ecx, ecx
0x1802ab0ea  jz      short loc_1802AB14F
0x1802ab0ec  mov     r15, [rbp+37h+arg_38]
0x1802ab0f0  cmp     byte ptr [r15], 0
0x1802ab0f4  jnz     short loc_1802AB119
0x1802ab0f6  mov     r8d, edi
0x1802ab0f9  mov     edx, r14d
0x1802ab0fc  mov     rcx, rsi
0x1802ab0ff  call    cs:UpdatePackageStatus
0x1802ab105  test    eax, eax
0x1802ab107  jz      short loc_1802AB113
0x1802ab109  mov     edx, 3EDh
0x1802ab10e  jmp     loc_1802AB26A
0x1802ab113  mov     [r15], bl
0x1802ab116  mov     dl, byte ptr [rbp+37h+arg_20]
0x1802ab119  mov     [rsp+0E0h+var_B8], 0
0x1802ab122  mov     eax, [rbp+37h+arg_28]
0x1802ab125  mov     dword ptr [rsp+0E0h+var_C0], eax
0x1802ab129  mov     r9b, dl
0x1802ab12c  lea     r8, [rbp+37h+var_60]
0x1802ab130  mov     rdx, r13
0x1802ab133  mov     rcx, r12
0x1802ab136  call    sub_1802AAB14
0x1802ab13b  mov     ebx, eax
0x1802ab13d  test    eax, eax
0x1802ab13f  jns     loc_1802AB1D5
0x1802ab145  mov     edx, 3F0h
0x1802ab14a  jmp     loc_1802AB2B2
0x1802ab14f  mov     byte ptr [rbp+37h+arg_20], 0
0x1802ab153  lea     rax, [rbp+37h+arg_20]
0x1802ab157  mov     [rsp+0E0h+var_B8], rax
0x1802ab15c  mov     eax, [rbp+37h+arg_28]
0x1802ab15f  mov     dword ptr [rsp+0E0h+var_C0], eax
0x1802ab163  mov     r9b, dl
0x1802ab166  lea     r8, [rbp+37h+var_60]
0x1802ab16a  mov     rdx, r13
0x1802ab16d  mov     rcx, r12
0x1802ab170  call    sub_1802AAB14
0x1802ab175  mov     r15d, eax
0x1802ab178  test    eax, eax
0x1802ab17a  jns     short loc_1802AB1A8
0x1802ab17c  mov     rcx, [rbp+3Fh]
0x1802ab180  mov     r9d, eax
0x1802ab183  lea     r8, aOnecoreAdminAp_90; "onecore\\admin\\appmodel\\common\\packa"...
0x1802ab18a  mov     edx, 3F8h
0x1802ab18f  call    sub_180024B6C
0x1802ab194  nop
0x1802ab195  lea     rcx, [rbp+37h+var_60]
0x1802ab199  call    sub_180071BAC
0x1802ab19e  nop
0x1802ab19f  cmp     dword ptr [rbp+37h+var_80], 0
0x1802ab1a3  jmp     loc_1802AAF28
0x1802ab1a8  mov     rcx, rsi
0x1802ab1ab  cmp     byte ptr [rbp+37h+arg_20], 0
0x1802ab1af  jz      short loc_1802AB22A
0x1802ab1b1  or      r14d, 40h
0x1802ab1b5  mov     r8d, edi
0x1802ab1b8  mov     edx, r14d
0x1802ab1bb  call    cs:UpdatePackageStatus
0x1802ab1c1  test    eax, eax
0x1802ab1c3  jz      short loc_1802AB1CF
0x1802ab1c5  mov     edx, 3FCh
0x1802ab1ca  jmp     loc_1802AB26A
0x1802ab1cf  mov     rax, [rbp+37h+arg_38]
0x1802ab1d3  mov     [rax], bl
0x1802ab1d5  xor     bl, bl
0x1802ab1d7  lea     rcx, [rbp+37h+var_60]
0x1802ab1db  call    sub_180071BAC
0x1802ab1e0  mov     eax, [rbp+37h+arg_10]
0x1802ab1e3  test    al, 4
0x1802ab1e5  jz      short loc_1802AB1FE
0x1802ab1e7  mov     [rsp+0E0h+var_C0], r12
0x1802ab1ec  mov     r9d, eax
0x1802ab1ef  mov     r8b, bl
0x1802ab1f2  mov     rdx, r13
0x1802ab1f5  mov     rcx, rsi
0x1802ab1f8  call    sub_1801931D8
0x1802ab1fd  nop
0x1802ab1fe  cmp     dword ptr [rbp+37h+var_80], 0
0x1802ab202  jz      short loc_1802AB20D
0x1802ab204  lea     rcx, [rbp+37h+var_80]
0x1802ab208  call    sub_18005A63C
0x1802ab20d  xor     eax, eax
0x1802ab20f  mov     rbx, [rsp+0E0h+arg_0]
0x1802ab217  add     rsp, 0B0h
0x1802ab21e  pop     r15
0x1802ab220  pop     r14
  ... truncated ...
```
