# TIFFFetchDirectory

- ea: `0x18015ebf0`
- end: `0x18015f1c6`
- name: `TIFFFetchDirectory`
- size: `1494`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x180164d70`

## callees

- `0x180150e00`
- `0x1801565f0`
- `0x180156870`
- `0x18015d110`
- `0x18015d220`
- `0x18015e5b0`
- `0x18015e5e0`
- `0x18015e630`
- `0x18015ebf0`
- `0x180167290`
- `0x1801ce010`

## string_xrefs

- `0x18015ec4c`: `%s: Seek error accessing TIFF directory`
- `0x18015ec96`: `%s: Can not read TIFF directory count`
- `0x18015ec53`: `TIFFFetchDirectory`
- `0x18015ec9d`: `TIFFFetchDirectory`
- `0x18015ed71`: `TIFFFetchDirectory`
- `0x18015ef65`: `TIFFFetchDirectory`
- `0x18015f176`: `TIFFFetchDirectory`
- `0x18015f196`: `TIFFFetchDirectory`
- `0x18015ed08`: `Sanity check on directory count failed, this is probably not a valid IFD offset`
- `0x18015ed21`: `to read TIFF directory`
- `0x18015ee05`: `to read TIFF directory`
- `0x18015ef76`: `to read TIFF directory`
- `0x18015ed6a`: `%.100s: Can not read TIFF directory`
- `0x18015f18f`: `Can not read TIFF directory count`
- `0x18015ef24`: `Sanity check on directory count failed, zero tag directories not supported`
- `0x18015ef59`: `Requested memory size for TIFF directory of %llu is greater than filesize %llu. Memory not allocated, TIFF directory not read`
- `0x18015f16c`: `Can not read TIFF directory`

## pseudocode

```c
__int64 __fastcall TIFFFetchDirectory(_QWORD *a1, __int64 a2, __int64 *a3, unsigned __int64 *a4)
{
  int v7; // eax
  signed __int64 v8; // rcx
  __int64 v9; // rcx
  __int64 (__fastcall *v10)(__int64, unsigned __int64 *, __int64); // rax
  unsigned __int16 v11; // cx
  unsigned int v12; // r14d
  const char *v13; // r8
  __int64 v14; // rax
  char *v15; // r15
  __int64 v16; // rbx
  __int64 v17; // rcx
  __int64 (__fastcall *v18)(__int64, unsigned __int64 *, __int64); // rax
  __int64 v19; // r12
  __int64 result; // rax
  __int64 v21; // rbx
  __int16 v22; // cx
  unsigned int v23; // r14d
  unsigned __int64 v24; // rax
  unsigned __int64 v25; // r9
  __int64 v26; // r9
  signed __int64 v27; // r8
  signed __int64 v28; // rax
  __int64 v29; // rcx
  __int64 v30; // rax
  __int64 v31; // rax
  unsigned __int16 v32; // r14
  char *v33; // rbx
  __int64 i; // rsi
  int v35; // ecx
  __int64 v36; // rax
  __int64 v37; // rax
  unsigned __int16 v38; // [rsp+70h] [rbp+30h] BYREF
  unsigned __int64 v39; // [rsp+78h] [rbp+38h] BYREF
  unsigned __int64 v40; // [rsp+88h] [rbp+48h] BYREF

  a1[3] = a2;
  if ( a4 )
    *a4 = 0;
  v7 = *((_DWORD *)a1 + 4);
  v8 = a1[3];
  if ( (v7 & 0x800) == 0 )
  {
    if ( !(unsigned int)TIFFSeekOK(a1, v8) )
    {
      TIFFErrorExtR(a1, "TIFFFetchDirectory", "%s: Seek error accessing TIFF directory", *a1);
      return 0;
    }
    v9 = a1[147];
    v10 = (__int64 (__fastcall *)(__int64, unsigned __int64 *, __int64))a1[148];
    if ( (a1[2] & 0x80000) != 0 )
    {
      if ( v10(v9, &v39, 8) != 8 )
        goto LABEL_8;
      if ( *((char *)a1 + 16) < 0 )
        TIFFSwabLong8(&v39);
      v11 = v39;
      if ( v39 <= 0x1000 )
      {
        v38 = v39;
        v12 = 20;
LABEL_19:
        v14 = TIFFCheckMalloc(a1, v11, v12, "to read TIFF directory");
        v15 = (char *)v14;
        if ( !v14 )
          return 0;
        v16 = v12 * v38;
        if ( ((__int64 (__fastcall *)(_QWORD, __int64, __int64))a1[148])(a1[147], v14, v16) != v16 )
        {
          TIFFErrorExtR(a1, "TIFFFetchDirectory", "%.100s: Can not read TIFF directory", *a1);
          TIFFfreeExt(a1, v15);
          return 0;
        }
        if ( a4 )
        {
          v17 = a1[147];
          v18 = (__int64 (__fastcall *)(__int64, unsigned __int64 *, __int64))a1[148];
          if ( (a1[2] & 0x80000) == 0 )
          {
            if ( v18(v17, &v39, 4) == 4 )
            {
LABEL_26:
              if ( *((char *)a1 + 16) < 0 )
                TIFFSwabLong(&v39);
              *a4 = (unsigned int)v39;
              goto LABEL_33;
            }
LABEL_25:
            LODWORD(v39) = 0;
            goto LABEL_26;
          }
          if ( v18(v17, a4, 8) != 8 )
LABEL_30:
            *a4 = 0;
LABEL_31:
          if ( *((char *)a1 + 16) < 0 )
            TIFFSwabLong8(a4);
          goto LABEL_33;
        }
        goto LABEL_33;
      }
    }
    else
    {
      if ( v10(v9, (unsigned __int64 *)&v38, 2) != 2 )
      {
LABEL_8:
        TIFFErrorExtR(a1, "TIFFFetchDirectory", "%s: Can not read TIFF directory count", *a1);
        return 0;
      }
      if ( *((char *)a1 + 16) < 0 )
        TIFFSwabShort(&v38);
      v11 = v38;
      if ( v38 <= 0x1000u )
      {
        v12 = 12;
        goto LABEL_19;
      }
    }
    goto LABEL_17;
  }
  if ( (unsigned __int64)v8 > 0x7FFFFFFFFFFFFFFFLL )
    goto LABEL_84;
  if ( (v7 & 0x80000) == 0 )
  {
    v21 = v8 + 2;
    if ( v8 + 2 > v8 && v21 >= 2 && v21 <= a1[144] )
    {
      TIFFmemcpy(&v38, (const void *)(v8 + a1[143]), 2u);
      if ( *((char *)a1 + 16) < 0 )
        TIFFSwabShort(&v38);
      v22 = v38;
      if ( v38 <= 0x1000u )
      {
        v23 = 12;
        goto LABEL_51;
      }
LABEL_17:
      v13 = "Sanity check on directory count failed, this is probably not a valid IFD offset";
LABEL_85:
      TIFFErrorExtR(a1, "TIFFFetchDirectory", v13, a4);
      return 0;
    }
LABEL_84:
    v13 = "Can not read TIFF directory count";
    goto LABEL_85;
  }
  v21 = v8 + 8;
  if ( v8 + 8 <= v8 || v21 < 8 || v21 > a1[144] )
    goto LABEL_84;
  TIFFmemcpy(&v40, (const void *)(v8 + a1[143]), 8u);
  if ( *((char *)a1 + 16) < 0 )
    TIFFSwabLong8(&v40);
  v22 = v40;
  if ( v40 > 0x1000 )
    goto LABEL_17;
  v38 = v40;
  v23 = 20;
LABEL_51:
  if ( !v22 )
  {
    v13 = "Sanity check on directory count failed, zero tag directories not supported";
    goto LABEL_85;
  }
  v24 = ((__int64 (__fastcall *)(_QWORD))a1[152])(a1[147]);
  v25 = v23 * (unsigned __int64)v38;
  if ( v25 > v24 )
  {
    TIFFWarningExtR(
      a1,
      "TIFFFetchDirectory",
      "Requested memory size for TIFF directory of %llu is greater than filesize %llu. Memory not allocated, TIFF directory not read",
      v25,
      v24);
    return 0;
  }
  v15 = (char *)TIFFCheckMalloc(a1, v38, v23, "to read TIFF directory");
  if ( !v15 )
    return 0;
  v27 = v23 * v38;
  v28 = v21 + v27;
  if ( __OFSUB__(v21 + v27, v21) || v28 < v27 || v28 > a1[144] )
  {
    TIFFErrorExtR(a1, "TIFFFetchDirectory", "Can not read TIFF directory", v26);
    TIFFfreeExt(a1, v15);
    return 0;
  }
  TIFFmemcpy(v15, (const void *)(v21 + a1[143]), v27);
  if ( a4 )
  {
    v29 = v21 + v23 * v38;
    if ( (a1[2] & 0x80000) == 0 )
    {
      v30 = v29 + 4;
      if ( v29 + 4 > v29 && v30 >= 4 && v30 <= a1[144] )
      {
        TIFFmemcpy(&v39, (const void *)(v29 + a1[143]), 4u);
        goto LABEL_26;
      }
      goto LABEL_25;
    }
    v31 = v29 + 8;
    if ( v29 + 8 <= v29 || v31 < 8 || v31 > a1[144] )
      goto LABEL_30;
    TIFFmemcpy(a4, (const void *)(v29 + a1[143]), 8u);
    goto LABEL_31;
  }
LABEL_33:
  v19 = TIFFCheckMalloc(a1, v38, 32, "to read TIFF directory");
  if ( v19 )
  {
    v32 = 0;
    v33 = v15;
    for ( i = v19; v32 < v38; ++v32 )
    {
      *(_BYTE *)(i + 24) = 0;
      if ( *((char *)a1 + 16) < 0 )
        TIFFSwabShort(v33);
      *(_WORD *)i = *(_WORD *)v33;
      if ( *((char *)a1 + 16) < 0 )
        TIFFSwabShort(v33 + 2);
      *(_WORD *)(i + 2) = *((_WORD *)v33 + 1);
      v35 = a1[2] & 0x80;
      if ( (a1[2] & 0x80000) != 0 )
      {
        if ( v35 )
          TIFFSwabLong8(v33 + 4);
        v39 = *(_QWORD *)(v33 + 4);
        *(_QWORD *)(i + 8) = v39;
        v37 = *(_QWORD *)(v33 + 12);
        v33 += 20;
        *(_QWORD *)(i + 16) = v37;
      }
      else
      {
        if ( v35 )
          TIFFSwabLong(v33 + 4);
        v36 = *((unsigned int *)v33 + 1);
        *(_QWORD *)(i + 16) = 0;
        *(_QWORD *)(i + 8) = v36;
        LODWORD(v36) = *((_DWORD *)v33 + 2);
        v33 += 12;
        *(_DWORD *)(i + 16) = v36;
      }
      i += 32;
    }
    TIFFfreeExt(a1, v15);
    result = v38;
    *a3 = v19;
  }
  else
  {
    TIFFfreeExt(a1, v15);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18015ebf0  push    rbp
0x18015ebf2  push    rsi
0x18015ebf3  push    rdi
0x18015ebf4  push    r12
0x18015ebf6  push    r13
0x18015ebf8  mov     rbp, rsp
0x18015ebfb  sub     rsp, 40h
0x18015ebff  xor     r12d, r12d
0x18015ec02  mov     [rcx+18h], rdx
0x18015ec06  mov     rsi, r9
0x18015ec09  mov     r13, r8
0x18015ec0c  mov     rdi, rcx
0x18015ec0f  test    r9, r9
0x18015ec12  jz      short loc_18015EC17
0x18015ec14  mov     [r9], r12
0x18015ec17  mov     eax, [rcx+10h]
0x18015ec1a  mov     rcx, [rcx+18h]
0x18015ec1e  mov     [rsp+40h+arg_10], rbx
0x18015ec26  mov     [rsp+40h+var_8], r14
0x18015ec2b  mov     [rsp+40h+var_10], r15
0x18015ec30  bt      eax, 0Bh
0x18015ec34  jb      loc_18015EE38
0x18015ec3a  mov     rdx, rcx
0x18015ec3d  mov     rcx, rdi
0x18015ec40  call    _TIFFSeekOK
0x18015ec45  test    eax, eax
0x18015ec47  jnz     short loc_18015EC67
0x18015ec49  mov     r9, [rdi]
0x18015ec4c  lea     r8, aSSeekErrorAcce; "%s: Seek error accessing TIFF directory"
0x18015ec53  lea     rdx, aTifffetchdirec; "TIFFFetchDirectory"
0x18015ec5a  mov     rcx, rdi
0x18015ec5d  call    TIFFErrorExtR
0x18015ec62  jmp     loc_18015F1A5
0x18015ec67  test    dword ptr [rdi+10h], 80000h
0x18015ec6e  mov     rcx, [rdi+498h]
0x18015ec75  mov     rax, [rdi+4A0h]
0x18015ec7c  jnz     short loc_18015ECD6
0x18015ec7e  mov     r8d, 2
0x18015ec84  lea     rdx, [rbp+arg_0]
0x18015ec88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015ec8d  cmp     rax, 2
0x18015ec91  jz      short loc_18015ECB1
0x18015ec93  mov     r9, [rdi]
0x18015ec96  lea     r8, aSCanNotReadTif; "%s: Can not read TIFF directory count"
0x18015ec9d  lea     rdx, aTifffetchdirec; "TIFFFetchDirectory"
0x18015eca4  mov     rcx, rdi
0x18015eca7  call    TIFFErrorExtR
0x18015ecac  jmp     loc_18015F1A5
0x18015ecb1  test    byte ptr [rdi+10h], 80h
0x18015ecb5  jz      short loc_18015ECC0
0x18015ecb7  lea     rcx, [rbp+arg_0]
0x18015ecbb  call    TIFFSwabShort
0x18015ecc0  movzx   ecx, [rbp+arg_0]
0x18015ecc4  mov     eax, 1000h
0x18015ecc9  cmp     cx, ax
0x18015eccc  ja      short loc_18015ED08
0x18015ecce  mov     r14d, 0Ch
0x18015ecd4  jmp     short loc_18015ED1E
0x18015ecd6  mov     r8d, 8
0x18015ecdc  lea     rdx, [rbp+arg_8]
0x18015ece0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015ece5  cmp     rax, 8
0x18015ece9  jnz     short loc_18015EC93
0x18015eceb  test    byte ptr [rdi+10h], 80h
0x18015ecef  jz      short loc_18015ECFA
0x18015ecf1  lea     rcx, [rbp+arg_8]
0x18015ecf5  call    TIFFSwabLong8
0x18015ecfa  mov     rcx, [rbp+arg_8]
0x18015ecfe  mov     eax, 1000h
0x18015ed03  cmp     rcx, rax
0x18015ed06  jbe     short loc_18015ED14
0x18015ed08  lea     r8, aSanityCheckOnD_1; "Sanity check on directory count failed,"...
0x18015ed0f  jmp     loc_18015F196
0x18015ed14  mov     [rbp+arg_0], cx
0x18015ed18  mov     r14d, 14h
0x18015ed1e  movzx   edx, cx
0x18015ed21  lea     r9, aToReadTiffDire; "to read TIFF directory"
0x18015ed28  mov     rcx, rdi
0x18015ed2b  mov     r8d, r14d
0x18015ed2e  call    _TIFFCheckMalloc
0x18015ed33  mov     r15, rax
0x18015ed36  test    rax, rax
0x18015ed39  jz      loc_18015F1A5
0x18015ed3f  movzx   ecx, [rbp+arg_0]
0x18015ed43  mov     rdx, rax
0x18015ed46  mov     rax, [rdi+4A0h]
0x18015ed4d  imul    ecx, r14d
0x18015ed51  mov     ebx, ecx
0x18015ed53  mov     r8d, ecx
0x18015ed56  mov     rcx, [rdi+498h]
0x18015ed5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015ed62  cmp     rax, rbx
0x18015ed65  jz      short loc_18015ED90
0x18015ed67  mov     r9, [rdi]
0x18015ed6a  lea     r8, a100sCanNotRead; "%.100s: Can not read TIFF directory"
0x18015ed71  lea     rdx, aTifffetchdirec; "TIFFFetchDirectory"
0x18015ed78  mov     rcx, rdi
0x18015ed7b  call    TIFFErrorExtR
0x18015ed80  mov     rdx, r15
0x18015ed83  mov     rcx, rdi
0x18015ed86  call    _TIFFfreeExt
0x18015ed8b  jmp     loc_18015F1A5
0x18015ed90  test    rsi, rsi
0x18015ed93  jz      short loc_18015EE01
0x18015ed95  test    dword ptr [rdi+10h], 80000h
0x18015ed9c  mov     rcx, [rdi+498h]
0x18015eda3  mov     rax, [rdi+4A0h]
0x18015edaa  jnz     short loc_18015EDDC
0x18015edac  mov     r8d, 4
0x18015edb2  lea     rdx, [rbp+arg_8]
0x18015edb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015edbb  cmp     rax, 4
0x18015edbf  jz      short loc_18015EDC5
0x18015edc1  mov     dword ptr [rbp+arg_8], r12d
0x18015edc5  test    byte ptr [rdi+10h], 80h
0x18015edc9  jz      short loc_18015EDD4
0x18015edcb  lea     rcx, [rbp+arg_8]
0x18015edcf  call    TIFFSwabLong
0x18015edd4  mov     eax, dword ptr [rbp+arg_8]
0x18015edd7  mov     [rsi], rax
0x18015edda  jmp     short loc_18015EE01
0x18015eddc  mov     r8d, 8
0x18015ede2  mov     rdx, rsi
0x18015ede5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015edea  cmp     rax, 8
0x18015edee  jz      short loc_18015EDF3
0x18015edf0  mov     [rsi], r12
0x18015edf3  test    byte ptr [rdi+10h], 80h
0x18015edf7  jz      short loc_18015EE01
0x18015edf9  mov     rcx, rsi
0x18015edfc  call    TIFFSwabLong8
0x18015ee01  movzx   edx, [rbp+arg_0]
0x18015ee05  lea     r9, aToReadTiffDire; "to read TIFF directory"
0x18015ee0c  mov     r8d, 20h ; ' '
0x18015ee12  mov     rcx, rdi
0x18015ee15  call    _TIFFCheckMalloc
0x18015ee1a  mov     r12, rax
0x18015ee1d  test    rax, rax
0x18015ee20  jnz     loc_18015F06D
0x18015ee26  mov     rdx, r15
0x18015ee29  mov     rcx, rdi
0x18015ee2c  call    _TIFFfreeExt
0x18015ee31  xor     eax, eax
0x18015ee33  jmp     loc_18015F1A8
0x18015ee38  mov     rdx, 7FFFFFFFFFFFFFFFh
0x18015ee42  cmp     rcx, rdx
0x18015ee45  ja      loc_18015F18F
0x18015ee4b  bt      eax, 13h
0x18015ee4f  jb      short loc_18015EEB7
0x18015ee51  lea     rbx, [rcx+2]
0x18015ee55  cmp     rbx, rcx
0x18015ee58  jl      loc_18015F18F
0x18015ee5e  cmp     rbx, 2
0x18015ee62  jl      loc_18015F18F
0x18015ee68  cmp     rbx, [rdi+480h]
0x18015ee6f  jg      loc_18015F18F
0x18015ee75  mov     rdx, [rdi+478h]
0x18015ee7c  mov     r8d, 2; Size
0x18015ee82  add     rdx, rcx; Src
0x18015ee85  lea     rcx, [rbp+arg_0]; void *
0x18015ee89  call    _TIFFmemcpy
0x18015ee8e  test    byte ptr [rdi+10h], 80h
0x18015ee92  jz      short loc_18015EE9D
0x18015ee94  lea     rcx, [rbp+arg_0]
0x18015ee98  call    TIFFSwabShort
0x18015ee9d  movzx   ecx, [rbp+arg_0]
0x18015eea1  mov     eax, 1000h
0x18015eea6  cmp     cx, ax
0x18015eea9  ja      loc_18015ED08
0x18015eeaf  mov     r14d, 0Ch
0x18015eeb5  jmp     short loc_18015EF1F
0x18015eeb7  lea     rbx, [rcx+8]
0x18015eebb  cmp     rbx, rcx
0x18015eebe  jl      loc_18015F18F
0x18015eec4  cmp     rbx, 8
0x18015eec8  jl      loc_18015F18F
0x18015eece  cmp     rbx, [rdi+480h]
0x18015eed5  jg      loc_18015F18F
0x18015eedb  mov     rdx, [rdi+478h]
0x18015eee2  mov     r8d, 8; Size
0x18015eee8  add     rdx, rcx; Src
0x18015eeeb  lea     rcx, [rbp+arg_18]; void *
0x18015eeef  call    _TIFFmemcpy
0x18015eef4  test    byte ptr [rdi+10h], 80h
0x18015eef8  jz      short loc_18015EF03
0x18015eefa  lea     rcx, [rbp+arg_18]
0x18015eefe  call    TIFFSwabLong8
0x18015ef03  mov     rcx, [rbp+arg_18]
0x18015ef07  mov     eax, 1000h
0x18015ef0c  cmp     rcx, rax
0x18015ef0f  ja      loc_18015ED08
0x18015ef15  mov     [rbp+arg_0], cx
0x18015ef19  mov     r14d, 14h
0x18015ef1f  test    cx, cx
0x18015ef22  jnz     short loc_18015EF30
0x18015ef24  lea     r8, aSanityCheckOnD_0; "Sanity check on directory count failed,"...
0x18015ef2b  jmp     loc_18015F196
0x18015ef30  mov     rcx, [rdi+498h]
0x18015ef37  mov     rax, [rdi+4C0h]
0x18015ef3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015ef43  movzx   edx, [rbp+arg_0]
0x18015ef47  mov     rcx, rdi
0x18015ef4a  mov     r9d, edx
0x18015ef4d  mov     r8d, r14d
0x18015ef50  imul    r9, r8
0x18015ef54  cmp     r9, rax
0x18015ef57  jbe     short loc_18015EF76
0x18015ef59  lea     r8, aRequestedMemor_1; "Requested memory size for TIFF director"...
0x18015ef60  mov     [rsp+40h+var_20], rax
0x18015ef65  lea     rdx, aTifffetchdirec; "TIFFFetchDirectory"
0x18015ef6c  call    TIFFWarningExtR
0x18015ef71  jmp     loc_18015F1A5
0x18015ef76  lea     r9, aToReadTiffDire; "to read TIFF directory"
0x18015ef7d  call    _TIFFCheckMalloc
0x18015ef82  mov     r15, rax
0x18015ef85  test    rax, rax
0x18015ef88  jz      loc_18015F1A5
0x18015ef8e  movzx   eax, [rbp+arg_0]
0x18015ef92  imul    eax, r14d
0x18015ef96  mov     r8d, eax; Size
0x18015ef99  add     rax, rbx
0x18015ef9c  cmp     rax, rbx
0x18015ef9f  jl      loc_18015F16C
0x18015efa5  cmp     rax, r8
0x18015efa8  jl      loc_18015F16C
0x18015efae  cmp     rax, [rdi+480h]
0x18015efb5  jg      loc_18015F16C
0x18015efbb  mov     rdx, [rdi+478h]
0x18015efc2  mov     rcx, r15; void *
0x18015efc5  add     rdx, rbx; Src
0x18015efc8  call    _TIFFmemcpy
0x18015efcd  test    rsi, rsi
0x18015efd0  jz      loc_18015EE01
0x18015efd6  movzx   ecx, [rbp+arg_0]
0x18015efda  imul    ecx, r14d
0x18015efde  add     rcx, rbx
0x18015efe1  test    dword ptr [rdi+10h], 80000h
0x18015efe8  jnz     short loc_18015F02C
0x18015efea  lea     rax, [rcx+4]
0x18015efee  cmp     rax, rcx
0x18015eff1  jl      loc_18015EDC1
0x18015eff7  cmp     rax, 4
0x18015effb  jl      loc_18015EDC1
0x18015f001  cmp     rax, [rdi+480h]
0x18015f008  jg      loc_18015EDC1
0x18015f00e  mov     rdx, [rdi+478h]
0x18015f015  mov     r8d, 4; Size
0x18015f01b  add     rdx, rcx; Src
0x18015f01e  lea     rcx, [rbp+arg_8]; void *
0x18015f022  call    _TIFFmemcpy
0x18015f027  jmp     loc_18015EDC5
0x18015f02c  lea     rax, [rcx+8]
0x18015f030  cmp     rax, rcx
0x18015f033  jl      loc_18015EDF0
0x18015f039  cmp     rax, 8
0x18015f03d  jl      loc_18015EDF0
0x18015f043  cmp     rax, [rdi+480h]
0x18015f04a  jg      loc_18015EDF0
0x18015f050  mov     rdx, [rdi+478h]
0x18015f057  mov     r8d, 8; Size
0x18015f05d  add     rdx, rcx; Src
0x18015f060  mov     rcx, rsi; void *
0x18015f063  call    _TIFFmemcpy
0x18015f068  jmp     loc_18015EDF3
0x18015f06d  xor     r14d, r14d
0x18015f070  xor     eax, eax
0x18015f072  mov     rbx, r15
0x18015f075  mov     rsi, r12
0x18015f078  cmp     ax, [rbp+arg_0]
0x18015f07c  jnb     loc_18015F157
0x18015f082  mov     byte ptr [rsi+18h], 0
0x18015f086  test    byte ptr [rdi+10h], 80h
0x18015f08a  jz      short loc_18015F094
0x18015f08c  mov     rcx, rbx
0x18015f08f  call    TIFFSwabShort
0x18015f094  movzx   eax, word ptr [rbx]
0x18015f097  mov     [rsi], ax
0x18015f09a  test    byte ptr [rdi+10h], 80h
0x18015f09e  jz      short loc_18015F0A9
0x18015f0a0  lea     rcx, [rbx+2]
0x18015f0a4  call    TIFFSwabShort
0x18015f0a9  movzx   eax, word ptr [rbx+2]
0x18015f0ad  mov     [rsi+2], ax
0x18015f0b1  mov     ecx, [rdi+10h]
0x18015f0b4  and     ecx, 80h
0x18015f0ba  test    dword ptr [rdi+10h], 80000h
0x18015f0c1  jnz     short loc_18015F0EB
0x18015f0c3  test    ecx, ecx
0x18015f0c5  jz      short loc_18015F0D0
0x18015f0c7  lea     rcx, [rbx+4]
0x18015f0cb  call    TIFFSwabLong
0x18015f0d0  mov     eax, [rbx+4]
0x18015f0d3  mov     qword ptr [rsi+10h], 0
0x18015f0db  mov     [rsi+8], rax
0x18015f0df  mov     eax, [rbx+8]
0x18015f0e2  add     rbx, 0Ch
0x18015f0e6  mov     [rsi+10h], eax
0x18015f0e9  jmp     short loc_18015F144
0x18015f0eb  test    ecx, ecx
0x18015f0ed  jz      short loc_18015F0F8
  ... truncated ...
```
