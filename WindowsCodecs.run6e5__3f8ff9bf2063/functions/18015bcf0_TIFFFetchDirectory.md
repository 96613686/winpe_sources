# TIFFFetchDirectory

- ea: `0x18015bcf0`
- end: `0x18015c2c6`
- name: `TIFFFetchDirectory`
- size: `1494`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x180161e70`

## callees

- `0x18014df00`
- `0x1801536f0`
- `0x180153970`
- `0x18015a210`
- `0x18015a320`
- `0x18015b6b0`
- `0x18015b6e0`
- `0x18015b730`
- `0x18015bcf0`
- `0x180164390`
- `0x1801ca010`

## string_xrefs

- `0x18015bd4c`: `%s: Seek error accessing TIFF directory`
- `0x18015bd96`: `%s: Can not read TIFF directory count`
- `0x18015bd53`: `TIFFFetchDirectory`
- `0x18015bd9d`: `TIFFFetchDirectory`
- `0x18015be71`: `TIFFFetchDirectory`
- `0x18015c065`: `TIFFFetchDirectory`
- `0x18015c276`: `TIFFFetchDirectory`
- `0x18015c296`: `TIFFFetchDirectory`
- `0x18015be08`: `Sanity check on directory count failed, this is probably not a valid IFD offset`
- `0x18015be21`: `to read TIFF directory`
- `0x18015bf05`: `to read TIFF directory`
- `0x18015c076`: `to read TIFF directory`
- `0x18015be6a`: `%.100s: Can not read TIFF directory`
- `0x18015c28f`: `Can not read TIFF directory count`
- `0x18015c024`: `Sanity check on directory count failed, zero tag directories not supported`
- `0x18015c059`: `Requested memory size for TIFF directory of %llu is greater than filesize %llu. Memory not allocated, TIFF directory not read`
- `0x18015c26c`: `Can not read TIFF directory`

## pseudocode

```c
__int64 __fastcall TIFFFetchDirectory(const char **a1, const char *a2, __int64 *a3, _QWORD *a4)
{
  int v7; // eax
  signed __int64 v8; // rcx
  const char *v9; // rcx
  const char *v10; // rax
  unsigned __int16 v11; // cx
  unsigned int v12; // r14d
  __int64 v13; // rax
  char *v14; // r15
  __int64 v15; // rbx
  const char *v16; // rcx
  const char *v17; // rax
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // r9
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 v23; // r9
  __int64 v24; // r12
  __int64 result; // rax
  __int64 v26; // rbx
  __int16 v27; // cx
  unsigned int v28; // r14d
  unsigned __int64 v29; // rax
  unsigned __int64 v30; // r9
  signed __int64 v31; // r8
  signed __int64 v32; // rax
  __int64 v33; // rcx
  __int64 v34; // rax
  __int64 v35; // rax
  unsigned __int16 v36; // r14
  char *v37; // rbx
  __int64 i; // rsi
  int v39; // ecx
  __int64 v40; // rax
  __int64 v41; // rax
  unsigned __int16 v42; // [rsp+70h] [rbp+30h] BYREF
  unsigned __int64 v43; // [rsp+78h] [rbp+38h] BYREF
  unsigned __int64 v44; // [rsp+88h] [rbp+48h] BYREF

  a1[3] = a2;
  if ( a4 )
    *a4 = 0;
  v7 = *((_DWORD *)a1 + 4);
  v8 = (signed __int64)a1[3];
  if ( (v7 & 0x800) == 0 )
  {
    if ( !(unsigned int)TIFFSeekOK(a1, v8) )
    {
      TIFFErrorExtR(a1, "TIFFFetchDirectory", "%s: Seek error accessing TIFF directory", *a1);
      return 0;
    }
    v9 = a1[147];
    v10 = a1[148];
    if ( ((_DWORD)a1[2] & 0x80000) != 0 )
    {
      if ( ((__int64 (__fastcall *)(const char *, unsigned __int64 *, __int64))v10)(v9, &v43, 8) != 8 )
        goto LABEL_8;
      if ( *((char *)a1 + 16) < 0 )
        TIFFSwabLong8(&v43);
      v11 = v43;
      if ( v43 <= 0x1000 )
      {
        v42 = v43;
        v12 = 20;
LABEL_19:
        v13 = TIFFCheckMalloc(a1, v11, v12, "to read TIFF directory");
        v14 = (char *)v13;
        if ( !v13 )
          return 0;
        v15 = v12 * v42;
        if ( ((__int64 (__fastcall *)(const char *, __int64, __int64))a1[148])(a1[147], v13, v15) != v15 )
        {
          TIFFErrorExtR(a1, "TIFFFetchDirectory", "%.100s: Can not read TIFF directory", *a1);
          TIFFfreeExt(a1);
          return 0;
        }
        if ( a4 )
        {
          v16 = a1[147];
          v17 = a1[148];
          if ( ((_DWORD)a1[2] & 0x80000) == 0 )
          {
            if ( ((__int64 (__fastcall *)(const char *, unsigned __int64 *, __int64))v17)(v16, &v43, 4) == 4 )
            {
LABEL_26:
              if ( *((char *)a1 + 16) < 0 )
                TIFFSwabLong(&v43, v18, v19, v20);
              *a4 = (unsigned int)v43;
              goto LABEL_33;
            }
LABEL_25:
            LODWORD(v43) = 0;
            goto LABEL_26;
          }
          if ( ((__int64 (__fastcall *)(const char *, _QWORD *, __int64))v17)(v16, a4, 8) != 8 )
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
      if ( ((__int64 (__fastcall *)(const char *, unsigned __int16 *, __int64))v10)(v9, &v42, 2) != 2 )
      {
LABEL_8:
        TIFFErrorExtR(a1, "TIFFFetchDirectory", "%s: Can not read TIFF directory count", *a1);
        return 0;
      }
      if ( *((char *)a1 + 16) < 0 )
        TIFFSwabShort(&v42);
      v11 = v42;
      if ( v42 <= 0x1000u )
      {
        v12 = 12;
        goto LABEL_19;
      }
    }
LABEL_17:
    TIFFErrorExtR(
      a1,
      "TIFFFetchDirectory",
      "Sanity check on directory count failed, this is probably not a valid IFD offset");
    return 0;
  }
  if ( (unsigned __int64)v8 > 0x7FFFFFFFFFFFFFFFLL )
    goto LABEL_84;
  if ( (v7 & 0x80000) != 0 )
  {
    v26 = v8 + 8;
    if ( v8 + 8 > v8 && v26 >= 8 && v26 <= (__int64)a1[144] )
    {
      TIFFmemcpy(&v44, &a1[143][v8], 8u);
      if ( *((char *)a1 + 16) < 0 )
        TIFFSwabLong8(&v44);
      v27 = v44;
      if ( v44 > 0x1000 )
        goto LABEL_17;
      v42 = v44;
      v28 = 20;
      goto LABEL_51;
    }
LABEL_84:
    TIFFErrorExtR(a1, "TIFFFetchDirectory", "Can not read TIFF directory count");
    return 0;
  }
  v26 = v8 + 2;
  if ( v8 + 2 <= v8 || v26 < 2 || v26 > (__int64)a1[144] )
    goto LABEL_84;
  TIFFmemcpy(&v42, &a1[143][v8], 2u);
  if ( *((char *)a1 + 16) < 0 )
    TIFFSwabShort(&v42);
  v27 = v42;
  if ( v42 > 0x1000u )
    goto LABEL_17;
  v28 = 12;
LABEL_51:
  if ( !v27 )
  {
    TIFFErrorExtR(
      a1,
      "TIFFFetchDirectory",
      "Sanity check on directory count failed, zero tag directories not supported");
    return 0;
  }
  v29 = ((__int64 (__fastcall *)(const char *))a1[152])(a1[147]);
  v30 = v28 * (unsigned __int64)v42;
  if ( v30 > v29 )
  {
    TIFFWarningExtR(
      a1,
      "TIFFFetchDirectory",
      "Requested memory size for TIFF directory of %llu is greater than filesize %llu. Memory not allocated, TIFF directory not read",
      v30,
      v29);
    return 0;
  }
  v14 = (char *)TIFFCheckMalloc(a1, v42, v28, "to read TIFF directory");
  if ( !v14 )
    return 0;
  v31 = v28 * v42;
  v32 = v26 + v31;
  if ( __OFSUB__(v26 + v31, v26) || v32 < v31 || v32 > (__int64)a1[144] )
  {
    TIFFErrorExtR(a1, "TIFFFetchDirectory", "Can not read TIFF directory");
    TIFFfreeExt(a1);
    return 0;
  }
  TIFFmemcpy(v14, &a1[143][v26], v31);
  if ( a4 )
  {
    v33 = v26 + v28 * v42;
    if ( ((_DWORD)a1[2] & 0x80000) == 0 )
    {
      v34 = v33 + 4;
      if ( v33 + 4 > v33 && v34 >= 4 && v34 <= (__int64)a1[144] )
      {
        TIFFmemcpy(&v43, &a1[143][v33], 4u);
        goto LABEL_26;
      }
      goto LABEL_25;
    }
    v35 = v33 + 8;
    if ( v33 + 8 <= v33 || v35 < 8 || v35 > (__int64)a1[144] )
      goto LABEL_30;
    TIFFmemcpy(a4, &a1[143][v33], 8u);
    goto LABEL_31;
  }
LABEL_33:
  v24 = TIFFCheckMalloc(a1, v42, 32, "to read TIFF directory");
  if ( v24 )
  {
    v36 = 0;
    v37 = v14;
    for ( i = v24; v36 < v42; ++v36 )
    {
      *(_BYTE *)(i + 24) = 0;
      if ( *((char *)a1 + 16) < 0 )
        TIFFSwabShort(v37);
      *(_WORD *)i = *(_WORD *)v37;
      if ( *((char *)a1 + 16) < 0 )
        TIFFSwabShort(v37 + 2);
      *(_WORD *)(i + 2) = *((_WORD *)v37 + 1);
      v39 = (_DWORD)a1[2] & 0x80;
      if ( ((_DWORD)a1[2] & 0x80000) != 0 )
      {
        if ( v39 )
          TIFFSwabLong8(v37 + 4);
        v43 = *(_QWORD *)(v37 + 4);
        *(_QWORD *)(i + 8) = v43;
        v41 = *(_QWORD *)(v37 + 12);
        v37 += 20;
        *(_QWORD *)(i + 16) = v41;
      }
      else
      {
        if ( v39 )
          TIFFSwabLong(v37 + 4, v21, v22, v23);
        v40 = *((unsigned int *)v37 + 1);
        *(_QWORD *)(i + 16) = 0;
        *(_QWORD *)(i + 8) = v40;
        LODWORD(v40) = *((_DWORD *)v37 + 2);
        v37 += 12;
        *(_DWORD *)(i + 16) = v40;
      }
      i += 32;
    }
    TIFFfreeExt(a1);
    result = v42;
    *a3 = v24;
  }
  else
  {
    TIFFfreeExt(a1);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18015bcf0  push    rbp
0x18015bcf2  push    rsi
0x18015bcf3  push    rdi
0x18015bcf4  push    r12
0x18015bcf6  push    r13
0x18015bcf8  mov     rbp, rsp
0x18015bcfb  sub     rsp, 40h
0x18015bcff  xor     r12d, r12d
0x18015bd02  mov     [rcx+18h], rdx
0x18015bd06  mov     rsi, r9
0x18015bd09  mov     r13, r8
0x18015bd0c  mov     rdi, rcx
0x18015bd0f  test    r9, r9
0x18015bd12  jz      short loc_18015BD17
0x18015bd14  mov     [r9], r12
0x18015bd17  mov     eax, [rcx+10h]
0x18015bd1a  mov     rcx, [rcx+18h]
0x18015bd1e  mov     [rsp+40h+arg_10], rbx
0x18015bd26  mov     [rsp+40h+var_8], r14
0x18015bd2b  mov     [rsp+40h+var_10], r15
0x18015bd30  bt      eax, 0Bh
0x18015bd34  jb      loc_18015BF38
0x18015bd3a  mov     rdx, rcx
0x18015bd3d  mov     rcx, rdi
0x18015bd40  call    _TIFFSeekOK
0x18015bd45  test    eax, eax
0x18015bd47  jnz     short loc_18015BD67
0x18015bd49  mov     r9, [rdi]
0x18015bd4c  lea     r8, aSSeekErrorAcce; "%s: Seek error accessing TIFF directory"
0x18015bd53  lea     rdx, aTifffetchdirec; "TIFFFetchDirectory"
0x18015bd5a  mov     rcx, rdi
0x18015bd5d  call    TIFFErrorExtR
0x18015bd62  jmp     loc_18015C2A5
0x18015bd67  test    dword ptr [rdi+10h], 80000h
0x18015bd6e  mov     rcx, [rdi+498h]
0x18015bd75  mov     rax, [rdi+4A0h]
0x18015bd7c  jnz     short loc_18015BDD6
0x18015bd7e  mov     r8d, 2
0x18015bd84  lea     rdx, [rbp+arg_0]
0x18015bd88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015bd8d  cmp     rax, 2
0x18015bd91  jz      short loc_18015BDB1
0x18015bd93  mov     r9, [rdi]
0x18015bd96  lea     r8, aSCanNotReadTif; "%s: Can not read TIFF directory count"
0x18015bd9d  lea     rdx, aTifffetchdirec; "TIFFFetchDirectory"
0x18015bda4  mov     rcx, rdi
0x18015bda7  call    TIFFErrorExtR
0x18015bdac  jmp     loc_18015C2A5
0x18015bdb1  test    byte ptr [rdi+10h], 80h
0x18015bdb5  jz      short loc_18015BDC0
0x18015bdb7  lea     rcx, [rbp+arg_0]
0x18015bdbb  call    TIFFSwabShort
0x18015bdc0  movzx   ecx, [rbp+arg_0]
0x18015bdc4  mov     eax, 1000h
0x18015bdc9  cmp     cx, ax
0x18015bdcc  ja      short loc_18015BE08
0x18015bdce  mov     r14d, 0Ch
0x18015bdd4  jmp     short loc_18015BE1E
0x18015bdd6  mov     r8d, 8
0x18015bddc  lea     rdx, [rbp+arg_8]
0x18015bde0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015bde5  cmp     rax, 8
0x18015bde9  jnz     short loc_18015BD93
0x18015bdeb  test    byte ptr [rdi+10h], 80h
0x18015bdef  jz      short loc_18015BDFA
0x18015bdf1  lea     rcx, [rbp+arg_8]
0x18015bdf5  call    TIFFSwabLong8
0x18015bdfa  mov     rcx, [rbp+arg_8]
0x18015bdfe  mov     eax, 1000h
0x18015be03  cmp     rcx, rax
0x18015be06  jbe     short loc_18015BE14
0x18015be08  lea     r8, aSanityCheckOnD_1; "Sanity check on directory count failed,"...
0x18015be0f  jmp     loc_18015C296
0x18015be14  mov     [rbp+arg_0], cx
0x18015be18  mov     r14d, 14h
0x18015be1e  movzx   edx, cx
0x18015be21  lea     r9, aToReadTiffDire; "to read TIFF directory"
0x18015be28  mov     rcx, rdi
0x18015be2b  mov     r8d, r14d
0x18015be2e  call    _TIFFCheckMalloc
0x18015be33  mov     r15, rax
0x18015be36  test    rax, rax
0x18015be39  jz      loc_18015C2A5
0x18015be3f  movzx   ecx, [rbp+arg_0]
0x18015be43  mov     rdx, rax
0x18015be46  mov     rax, [rdi+4A0h]
0x18015be4d  imul    ecx, r14d
0x18015be51  mov     ebx, ecx
0x18015be53  mov     r8d, ecx
0x18015be56  mov     rcx, [rdi+498h]
0x18015be5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015be62  cmp     rax, rbx
0x18015be65  jz      short loc_18015BE90
0x18015be67  mov     r9, [rdi]
0x18015be6a  lea     r8, a100sCanNotRead; "%.100s: Can not read TIFF directory"
0x18015be71  lea     rdx, aTifffetchdirec; "TIFFFetchDirectory"
0x18015be78  mov     rcx, rdi
0x18015be7b  call    TIFFErrorExtR
0x18015be80  mov     rdx, r15
0x18015be83  mov     rcx, rdi
0x18015be86  call    _TIFFfreeExt
0x18015be8b  jmp     loc_18015C2A5
0x18015be90  test    rsi, rsi
0x18015be93  jz      short loc_18015BF01
0x18015be95  test    dword ptr [rdi+10h], 80000h
0x18015be9c  mov     rcx, [rdi+498h]
0x18015bea3  mov     rax, [rdi+4A0h]
0x18015beaa  jnz     short loc_18015BEDC
0x18015beac  mov     r8d, 4
0x18015beb2  lea     rdx, [rbp+arg_8]
0x18015beb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015bebb  cmp     rax, 4
0x18015bebf  jz      short loc_18015BEC5
0x18015bec1  mov     dword ptr [rbp+arg_8], r12d
0x18015bec5  test    byte ptr [rdi+10h], 80h
0x18015bec9  jz      short loc_18015BED4
0x18015becb  lea     rcx, [rbp+arg_8]
0x18015becf  call    TIFFSwabLong
0x18015bed4  mov     eax, dword ptr [rbp+arg_8]
0x18015bed7  mov     [rsi], rax
0x18015beda  jmp     short loc_18015BF01
0x18015bedc  mov     r8d, 8
0x18015bee2  mov     rdx, rsi
0x18015bee5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015beea  cmp     rax, 8
0x18015beee  jz      short loc_18015BEF3
0x18015bef0  mov     [rsi], r12
0x18015bef3  test    byte ptr [rdi+10h], 80h
0x18015bef7  jz      short loc_18015BF01
0x18015bef9  mov     rcx, rsi
0x18015befc  call    TIFFSwabLong8
0x18015bf01  movzx   edx, [rbp+arg_0]
0x18015bf05  lea     r9, aToReadTiffDire; "to read TIFF directory"
0x18015bf0c  mov     r8d, 20h ; ' '
0x18015bf12  mov     rcx, rdi
0x18015bf15  call    _TIFFCheckMalloc
0x18015bf1a  mov     r12, rax
0x18015bf1d  test    rax, rax
0x18015bf20  jnz     loc_18015C16D
0x18015bf26  mov     rdx, r15
0x18015bf29  mov     rcx, rdi
0x18015bf2c  call    _TIFFfreeExt
0x18015bf31  xor     eax, eax
0x18015bf33  jmp     loc_18015C2A8
0x18015bf38  mov     rdx, 7FFFFFFFFFFFFFFFh
0x18015bf42  cmp     rcx, rdx
0x18015bf45  ja      loc_18015C28F
0x18015bf4b  bt      eax, 13h
0x18015bf4f  jb      short loc_18015BFB7
0x18015bf51  lea     rbx, [rcx+2]
0x18015bf55  cmp     rbx, rcx
0x18015bf58  jl      loc_18015C28F
0x18015bf5e  cmp     rbx, 2
0x18015bf62  jl      loc_18015C28F
0x18015bf68  cmp     rbx, [rdi+480h]
0x18015bf6f  jg      loc_18015C28F
0x18015bf75  mov     rdx, [rdi+478h]
0x18015bf7c  mov     r8d, 2; Size
0x18015bf82  add     rdx, rcx; Src
0x18015bf85  lea     rcx, [rbp+arg_0]; void *
0x18015bf89  call    _TIFFmemcpy
0x18015bf8e  test    byte ptr [rdi+10h], 80h
0x18015bf92  jz      short loc_18015BF9D
0x18015bf94  lea     rcx, [rbp+arg_0]
0x18015bf98  call    TIFFSwabShort
0x18015bf9d  movzx   ecx, [rbp+arg_0]
0x18015bfa1  mov     eax, 1000h
0x18015bfa6  cmp     cx, ax
0x18015bfa9  ja      loc_18015BE08
0x18015bfaf  mov     r14d, 0Ch
0x18015bfb5  jmp     short loc_18015C01F
0x18015bfb7  lea     rbx, [rcx+8]
0x18015bfbb  cmp     rbx, rcx
0x18015bfbe  jl      loc_18015C28F
0x18015bfc4  cmp     rbx, 8
0x18015bfc8  jl      loc_18015C28F
0x18015bfce  cmp     rbx, [rdi+480h]
0x18015bfd5  jg      loc_18015C28F
0x18015bfdb  mov     rdx, [rdi+478h]
0x18015bfe2  mov     r8d, 8; Size
0x18015bfe8  add     rdx, rcx; Src
0x18015bfeb  lea     rcx, [rbp+arg_18]; void *
0x18015bfef  call    _TIFFmemcpy
0x18015bff4  test    byte ptr [rdi+10h], 80h
0x18015bff8  jz      short loc_18015C003
0x18015bffa  lea     rcx, [rbp+arg_18]
0x18015bffe  call    TIFFSwabLong8
0x18015c003  mov     rcx, [rbp+arg_18]
0x18015c007  mov     eax, 1000h
0x18015c00c  cmp     rcx, rax
0x18015c00f  ja      loc_18015BE08
0x18015c015  mov     [rbp+arg_0], cx
0x18015c019  mov     r14d, 14h
0x18015c01f  test    cx, cx
0x18015c022  jnz     short loc_18015C030
0x18015c024  lea     r8, aSanityCheckOnD_0; "Sanity check on directory count failed,"...
0x18015c02b  jmp     loc_18015C296
0x18015c030  mov     rcx, [rdi+498h]
0x18015c037  mov     rax, [rdi+4C0h]
0x18015c03e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015c043  movzx   edx, [rbp+arg_0]
0x18015c047  mov     rcx, rdi
0x18015c04a  mov     r9d, edx
0x18015c04d  mov     r8d, r14d
0x18015c050  imul    r9, r8
0x18015c054  cmp     r9, rax
0x18015c057  jbe     short loc_18015C076
0x18015c059  lea     r8, aRequestedMemor_1; "Requested memory size for TIFF director"...
0x18015c060  mov     [rsp+40h+var_20], rax
0x18015c065  lea     rdx, aTifffetchdirec; "TIFFFetchDirectory"
0x18015c06c  call    TIFFWarningExtR
0x18015c071  jmp     loc_18015C2A5
0x18015c076  lea     r9, aToReadTiffDire; "to read TIFF directory"
0x18015c07d  call    _TIFFCheckMalloc
0x18015c082  mov     r15, rax
0x18015c085  test    rax, rax
0x18015c088  jz      loc_18015C2A5
0x18015c08e  movzx   eax, [rbp+arg_0]
0x18015c092  imul    eax, r14d
0x18015c096  mov     r8d, eax; Size
0x18015c099  add     rax, rbx
0x18015c09c  cmp     rax, rbx
0x18015c09f  jl      loc_18015C26C
0x18015c0a5  cmp     rax, r8
0x18015c0a8  jl      loc_18015C26C
0x18015c0ae  cmp     rax, [rdi+480h]
0x18015c0b5  jg      loc_18015C26C
0x18015c0bb  mov     rdx, [rdi+478h]
0x18015c0c2  mov     rcx, r15; void *
0x18015c0c5  add     rdx, rbx; Src
0x18015c0c8  call    _TIFFmemcpy
0x18015c0cd  test    rsi, rsi
0x18015c0d0  jz      loc_18015BF01
0x18015c0d6  movzx   ecx, [rbp+arg_0]
0x18015c0da  imul    ecx, r14d
0x18015c0de  add     rcx, rbx
0x18015c0e1  test    dword ptr [rdi+10h], 80000h
0x18015c0e8  jnz     short loc_18015C12C
0x18015c0ea  lea     rax, [rcx+4]
0x18015c0ee  cmp     rax, rcx
0x18015c0f1  jl      loc_18015BEC1
0x18015c0f7  cmp     rax, 4
0x18015c0fb  jl      loc_18015BEC1
0x18015c101  cmp     rax, [rdi+480h]
0x18015c108  jg      loc_18015BEC1
0x18015c10e  mov     rdx, [rdi+478h]
0x18015c115  mov     r8d, 4; Size
0x18015c11b  add     rdx, rcx; Src
0x18015c11e  lea     rcx, [rbp+arg_8]; void *
0x18015c122  call    _TIFFmemcpy
0x18015c127  jmp     loc_18015BEC5
0x18015c12c  lea     rax, [rcx+8]
0x18015c130  cmp     rax, rcx
0x18015c133  jl      loc_18015BEF0
0x18015c139  cmp     rax, 8
0x18015c13d  jl      loc_18015BEF0
0x18015c143  cmp     rax, [rdi+480h]
0x18015c14a  jg      loc_18015BEF0
0x18015c150  mov     rdx, [rdi+478h]
0x18015c157  mov     r8d, 8; Size
0x18015c15d  add     rdx, rcx; Src
0x18015c160  mov     rcx, rsi; void *
0x18015c163  call    _TIFFmemcpy
0x18015c168  jmp     loc_18015BEF3
0x18015c16d  xor     r14d, r14d
0x18015c170  xor     eax, eax
0x18015c172  mov     rbx, r15
0x18015c175  mov     rsi, r12
0x18015c178  cmp     ax, [rbp+arg_0]
0x18015c17c  jnb     loc_18015C257
0x18015c182  mov     byte ptr [rsi+18h], 0
0x18015c186  test    byte ptr [rdi+10h], 80h
0x18015c18a  jz      short loc_18015C194
0x18015c18c  mov     rcx, rbx
0x18015c18f  call    TIFFSwabShort
0x18015c194  movzx   eax, word ptr [rbx]
0x18015c197  mov     [rsi], ax
0x18015c19a  test    byte ptr [rdi+10h], 80h
0x18015c19e  jz      short loc_18015C1A9
0x18015c1a0  lea     rcx, [rbx+2]
0x18015c1a4  call    TIFFSwabShort
0x18015c1a9  movzx   eax, word ptr [rbx+2]
0x18015c1ad  mov     [rsi+2], ax
0x18015c1b1  mov     ecx, [rdi+10h]
0x18015c1b4  and     ecx, 80h
0x18015c1ba  test    dword ptr [rdi+10h], 80000h
0x18015c1c1  jnz     short loc_18015C1EB
0x18015c1c3  test    ecx, ecx
0x18015c1c5  jz      short loc_18015C1D0
0x18015c1c7  lea     rcx, [rbx+4]
0x18015c1cb  call    TIFFSwabLong
0x18015c1d0  mov     eax, [rbx+4]
0x18015c1d3  mov     qword ptr [rsi+10h], 0
0x18015c1db  mov     [rsi+8], rax
0x18015c1df  mov     eax, [rbx+8]
0x18015c1e2  add     rbx, 0Ch
0x18015c1e6  mov     [rsi+10h], eax
0x18015c1e9  jmp     short loc_18015C244
0x18015c1eb  test    ecx, ecx
0x18015c1ed  jz      short loc_18015C1F8
  ... truncated ...
```
