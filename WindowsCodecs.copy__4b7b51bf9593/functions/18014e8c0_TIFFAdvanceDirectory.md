# TIFFAdvanceDirectory

- ea: `0x18014e8c0`
- end: `0x18014edb0`
- name: `TIFFAdvanceDirectory`
- size: `1264`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x18014f270`

## callees

- `0x18014e8c0`
- `0x180153970`
- `0x18015a210`
- `0x18015a320`
- `0x18015b6b0`
- `0x18015b6e0`
- `0x18015b730`
- `0x1801636f0`
- `0x180164390`
- `0x1801ca010`

## string_xrefs

- `0x18014e8f6`: `TIFFAdvanceDirectory`
- `0x18014ea19`: `TIFFAdvanceDirectory`
- `0x18014ea40`: `TIFFAdvanceDirectory`
- `0x18014eae5`: `TIFFAdvanceDirectory`
- `0x18014ec16`: `TIFFAdvanceDirectory`
- `0x18014ed4a`: `TIFFAdvanceDirectory`
- `0x18014ed86`: `TIFFAdvanceDirectory`
- `0x18014e8ec`: `Starting directory %u at offset 0x%llx (%llu) might cause an IFD loop`
- `0x18014ea39`: `%s:%d: %s: Error fetching directory count`
- `0x18014ed7f`: `%s:%d: %s: Error fetching directory count`
- `0x18014ea0f`: `Error fetching directory link`
- `0x18014eadb`: `Sanity check on directory count failed`
- `0x18014ec0f`: `%s: Error fetching directory link`
- `0x18014ed2b`: `the next directory %u at offset 0x%llx (%llu) might be an IFD loop. Treating directory %d as last directory`

## pseudocode

```c
__int64 __fastcall TIFFAdvanceDirectory(const char **a1, unsigned __int64 *a2, __int64 *a3, unsigned int *a4)
{
  __int64 result; // rax
  unsigned __int64 v9; // rdx
  int v10; // ecx
  __int64 v11; // rsi
  __int64 v12; // rcx
  __int64 v13; // rax
  signed __int64 v14; // r12
  __int64 v15; // rcx
  __int64 v16; // rcx
  const char *v17; // rcx
  const char *v18; // rax
  __int64 v19; // rdx
  unsigned __int16 v20; // [rsp+40h] [rbp-28h] BYREF
  unsigned int v21[8]; // [rsp+48h] [rbp-20h] BYREF

  if ( !(unsigned int)TIFFCheckDirNumberAndOffset(a1, *a4, *a2) )
  {
    TIFFErrorExtR(
      a1,
      "TIFFAdvanceDirectory",
      "Starting directory %u at offset 0x%llx (%llu) might cause an IFD loop",
      *a4,
      *a2,
      *a2);
    result = 0;
    *a2 = 0;
    *a4 = 0;
    return result;
  }
  v9 = *a2;
  v10 = (_DWORD)a1[2] & 0x80000;
  if ( ((_DWORD)a1[2] & 0x800) == 0 )
  {
    if ( v10 )
    {
      if ( !(unsigned int)TIFFSeekOK(a1)
        || ((__int64 (__fastcall *)(const char *, unsigned int *, __int64))a1[148])(a1[147], v21, 8) != 8 )
      {
        TIFFErrorExtR(
          a1,
          "TIFFAdvanceDirectory",
          "%s:%d: %s: Error fetching directory count",
          "D:\\os\\obj\\amd64fre\\onecoreuap\\windows\\oss\\libtiff\\vcpkg\\objfre\\amd64\\vcpkg_buildtrees\\tiff\\src\\v"
          "4.7.0-8cbea2c0ad.clean\\libtiff\\tif_dir.c",
          1981,
          *a1);
        return 0;
      }
      if ( *((char *)a1 + 16) < 0 )
        TIFFSwabLong8(v21);
      if ( *(_QWORD *)v21 > 0xFFFFu )
      {
        TIFFErrorExtR(
          a1,
          "TIFFAdvanceDirectory",
          "%s:%d: %s: Error fetching directory count",
          "D:\\os\\obj\\amd64fre\\onecoreuap\\windows\\oss\\libtiff\\vcpkg\\objfre\\amd64\\vcpkg_buildtrees\\tiff\\src\\v"
          "4.7.0-8cbea2c0ad.clean\\libtiff\\tif_dir.c",
          1990,
          *a1);
        return 0;
      }
      v17 = a1[147];
      v18 = a1[150];
      v19 = 20LL * LOWORD(v21[0]);
      if ( a3 )
        *a3 = ((__int64 (__fastcall *)(const char *, __int64, __int64))v18)(v17, v19, 1);
      else
        ((void (__fastcall *)(const char *, __int64, __int64))v18)(v17, v19, 1);
      if ( ((__int64 (__fastcall *)(const char *, unsigned __int64 *, __int64))a1[148])(a1[147], a2, 8) == 8 )
        goto LABEL_57;
    }
    else
    {
      if ( !(unsigned int)TIFFSeekOK(a1)
        || ((__int64 (__fastcall *)(const char *, unsigned __int16 *, __int64))a1[148])(a1[147], &v20, 2) != 2 )
      {
        TIFFErrorExtR(
          a1,
          "TIFFAdvanceDirectory",
          "%s:%d: %s: Error fetching directory count",
          "D:\\os\\obj\\amd64fre\\onecoreuap\\windows\\oss\\libtiff\\vcpkg\\objfre\\amd64\\vcpkg_buildtrees\\tiff\\src\\v"
          "4.7.0-8cbea2c0ad.clean\\libtiff\\tif_dir.c",
          1953,
          *a1);
        return 0;
      }
      if ( *((char *)a1 + 16) < 0 )
        TIFFSwabShort(&v20);
      if ( a3 )
        *a3 = ((__int64 (__fastcall *)(const char *, _QWORD, __int64))a1[150])(a1[147], 12 * (unsigned int)v20, 1);
      else
        ((void (__fastcall *)(const char *, _QWORD, __int64))a1[150])(a1[147], 12 * (unsigned int)v20, 1);
      if ( ((__int64 (__fastcall *)(const char *, unsigned int *, __int64))a1[148])(a1[147], v21, 4) == 4 )
        goto LABEL_18;
    }
    TIFFErrorExtR(a1, "TIFFAdvanceDirectory", "%s: Error fetching directory link", *a1);
    return 0;
  }
  if ( v10 )
  {
    if ( v9 > 0x7FFFFFFFFFFFFFF7LL )
    {
      TIFFErrorExtR(
        a1,
        "TIFFAdvanceDirectory",
        "%s:%d: %s: Error fetching directory count",
        "D:\\os\\obj\\amd64fre\\onecoreuap\\windows\\oss\\libtiff\\vcpkg\\objfre\\amd64\\vcpkg_buildtrees\\tiff\\src\\v4."
        "7.0-8cbea2c0ad.clean\\libtiff\\tif_dir.c",
        1900,
        *a1);
      return 0;
    }
    v14 = v9 + 8;
    if ( (__int64)(v9 + 8) > (__int64)a1[144] )
    {
      TIFFErrorExtR(
        a1,
        "TIFFAdvanceDirectory",
        "%s:%d: %s: Error fetching directory count",
        "D:\\os\\obj\\amd64fre\\onecoreuap\\windows\\oss\\libtiff\\vcpkg\\objfre\\amd64\\vcpkg_buildtrees\\tiff\\src\\v4."
        "7.0-8cbea2c0ad.clean\\libtiff\\tif_dir.c",
        1909,
        *a1);
      return 0;
    }
    TIFFmemcpy(v21, &a1[143][v9], 8u);
    if ( *((char *)a1 + 16) < 0 )
      TIFFSwabLong8(v21);
    if ( *(_QWORD *)v21 > 0xFFFFu )
    {
      TIFFErrorExtR(a1, "TIFFAdvanceDirectory", "Sanity check on directory count failed");
      return 0;
    }
    v15 = 20LL * LOWORD(v21[0]);
    if ( v14 > 0x7FFFFFFFFFFFFFF7LL - v15 || (v16 = v14 + v15, v16 + 8 > (__int64)a1[144]) )
    {
LABEL_21:
      TIFFErrorExtR(a1, "TIFFAdvanceDirectory", "Error fetching directory link");
      return 0;
    }
    if ( a3 )
      *a3 = v16;
    TIFFmemcpy(a2, &a1[143][v16], 8u);
LABEL_57:
    if ( *((char *)a1 + 16) < 0 )
      TIFFSwabLong8(a2);
    goto LABEL_59;
  }
  v11 = v9 + 2;
  if ( (__int64)(v9 + 2) <= (__int64)v9 || v11 < 2 || v11 > (__int64)a1[144] )
  {
    TIFFErrorExtR(
      a1,
      "TIFFAdvanceDirectory",
      "%s:%d: %s: Error fetching directory count",
      "D:\\os\\obj\\amd64fre\\onecoreuap\\windows\\oss\\libtiff\\vcpkg\\objfre\\amd64\\vcpkg_buildtrees\\tiff\\src\\v4.7."
      "0-8cbea2c0ad.clean\\libtiff\\tif_dir.c",
      1869,
      *a1);
    result = 0;
    *a2 = 0;
    return result;
  }
  TIFFmemcpy(&v20, &a1[143][v9], 2u);
  if ( *((char *)a1 + 16) < 0 )
    TIFFSwabShort(&v20);
  v12 = v11 + 12 * (unsigned int)v20;
  if ( __OFSUB__(v12, v11) )
    goto LABEL_21;
  if ( v12 < 12 * (unsigned int)v20 )
    goto LABEL_21;
  v13 = v12 + 4;
  if ( v12 + 4 <= v12 || v13 < 4 || v13 > (__int64)a1[144] )
    goto LABEL_21;
  if ( a3 )
    *a3 = v12;
  TIFFmemcpy(v21, &a1[143][v12], 4u);
LABEL_18:
  if ( *((char *)a1 + 16) < 0 )
    TIFFSwabLong(v21);
  *a2 = v21[0];
LABEL_59:
  if ( *a2 )
  {
    if ( !(unsigned int)TIFFCheckDirNumberAndOffset(a1, ++*a4, *a2) )
    {
      TIFFWarningExtR(
        a1,
        "TIFFAdvanceDirectory",
        "the next directory %u at offset 0x%llx (%llu) might be an IFD loop. Treating directory %d as last directory",
        *a4,
        *a2,
        *a2,
        *a4 - 1);
      *a2 = 0;
      --*a4;
    }
  }
  return 1;
}

```

## disassembly

```asm
0x18014e8c0  mov     [rsp+arg_10], rbx
0x18014e8c5  push    rdi
0x18014e8c6  push    r14
0x18014e8c8  push    r15
0x18014e8ca  sub     rsp, 50h
0x18014e8ce  mov     r14, r8
0x18014e8d1  mov     rdi, rdx
0x18014e8d4  mov     r8, [rdx]
0x18014e8d7  mov     r15, r9
0x18014e8da  mov     edx, [r9]
0x18014e8dd  mov     rbx, rcx
0x18014e8e0  call    _TIFFCheckDirNumberAndOffset
0x18014e8e5  test    eax, eax
0x18014e8e7  jnz     short loc_18014E929
0x18014e8e9  mov     rax, [rdi]
0x18014e8ec  lea     r8, aStartingDirect; "Starting directory %u at offset 0x%llx "...
0x18014e8f3  mov     r9d, [r15]
0x18014e8f6  lea     rdx, aTiffadvancedir; "TIFFAdvanceDirectory"
0x18014e8fd  mov     [rsp+68h+var_40], rax
0x18014e902  mov     rcx, rbx
0x18014e905  mov     [rsp+68h+var_48], rax
0x18014e90a  call    TIFFErrorExtR
0x18014e90f  xor     eax, eax
0x18014e911  mov     [rdi], rax
0x18014e914  mov     [r15], eax
0x18014e917  mov     rbx, [rsp+68h+arg_10]
0x18014e91f  add     rsp, 50h
0x18014e923  pop     r15
0x18014e925  pop     r14
0x18014e927  pop     rdi
0x18014e928  retn
0x18014e929  mov     ecx, [rbx+10h]
0x18014e92c  mov     rdx, [rdi]
0x18014e92f  and     ecx, 80000h
0x18014e935  test    dword ptr [rbx+10h], 800h
0x18014e93c  mov     [rsp+68h+arg_0], rsi
0x18014e941  mov     [rsp+68h+arg_8], r12
0x18014e946  jz      loc_18014EB4A
0x18014e94c  test    ecx, ecx
0x18014e94e  jnz     loc_18014EA61
0x18014e954  lea     rsi, [rdx+2]
0x18014e958  cmp     rsi, rdx
0x18014e95b  jl      loc_18014EA2A
0x18014e961  cmp     rsi, 2
0x18014e965  jl      loc_18014EA2A
0x18014e96b  cmp     rsi, [rbx+480h]
0x18014e972  jg      loc_18014EA2A
0x18014e978  add     rdx, [rbx+478h]; Src
0x18014e97f  lea     rcx, [rsp+68h+var_28]; void *
0x18014e984  mov     r8d, 2; Size
0x18014e98a  call    _TIFFmemcpy
0x18014e98f  test    byte ptr [rbx+10h], 80h
0x18014e993  jz      short loc_18014E99F
0x18014e995  lea     rcx, [rsp+68h+var_28]
0x18014e99a  call    TIFFSwabShort
0x18014e99f  movzx   eax, [rsp+68h+var_28]
0x18014e9a4  lea     ecx, [rax+rax*2]
0x18014e9a7  shl     ecx, 2
0x18014e9aa  mov     eax, ecx
0x18014e9ac  add     rcx, rsi
0x18014e9af  cmp     rcx, rsi
0x18014e9b2  jl      short loc_18014EA0F
0x18014e9b4  cmp     rcx, rax
0x18014e9b7  jl      short loc_18014EA0F
0x18014e9b9  lea     rax, [rcx+4]
0x18014e9bd  cmp     rax, rcx
0x18014e9c0  jl      short loc_18014EA0F
0x18014e9c2  cmp     rax, 4
0x18014e9c6  jl      short loc_18014EA0F
0x18014e9c8  cmp     rax, [rbx+480h]
0x18014e9cf  jg      short loc_18014EA0F
0x18014e9d1  test    r14, r14
0x18014e9d4  jz      short loc_18014E9D9
0x18014e9d6  mov     [r14], rcx
0x18014e9d9  mov     rdx, [rbx+478h]
0x18014e9e0  mov     r8d, 4; Size
0x18014e9e6  add     rdx, rcx; Src
0x18014e9e9  lea     rcx, [rsp+68h+var_20]; void *
0x18014e9ee  call    _TIFFmemcpy
0x18014e9f3  test    byte ptr [rbx+10h], 80h
0x18014e9f7  jz      short loc_18014EA03
0x18014e9f9  lea     rcx, [rsp+68h+var_20]
0x18014e9fe  call    TIFFSwabLong
0x18014ea03  mov     eax, [rsp+68h+var_20]
0x18014ea07  mov     [rdi], rax
0x18014ea0a  jmp     loc_18014ED0D
0x18014ea0f  lea     r8, aErrorFetchingD; "Error fetching directory link"
0x18014ea16  mov     rcx, rbx
0x18014ea19  lea     rdx, aTiffadvancedir; "TIFFAdvanceDirectory"
0x18014ea20  call    TIFFErrorExtR
0x18014ea25  jmp     loc_18014ED92
0x18014ea2a  mov     rax, [rbx]
0x18014ea2d  lea     r9, aDOsObjAmd64fre; "D:\\os\\obj\\amd64fre\\onecoreuap\\wind"...
0x18014ea34  mov     [rsp+68h+var_40], rax
0x18014ea39  lea     r8, aSDSErrorFetchi; "%s:%d: %s: Error fetching directory cou"...
0x18014ea40  lea     rdx, aTiffadvancedir; "TIFFAdvanceDirectory"
0x18014ea47  mov     dword ptr [rsp+68h+var_48], 74Dh
0x18014ea4f  mov     rcx, rbx
0x18014ea52  call    TIFFErrorExtR
0x18014ea57  xor     eax, eax
0x18014ea59  mov     [rdi], rax
0x18014ea5c  jmp     loc_18014ED94
0x18014ea61  mov     rsi, 7FFFFFFFFFFFFFF7h
0x18014ea6b  cmp     rdx, rsi
0x18014ea6e  jbe     short loc_18014EA85
0x18014ea70  mov     rax, [rbx]
0x18014ea73  mov     [rsp+68h+var_40], rax
0x18014ea78  mov     dword ptr [rsp+68h+var_48], 76Ch
0x18014ea80  jmp     loc_18014ED75
0x18014ea85  lea     r12, [rdx+8]
0x18014ea89  cmp     r12, [rbx+480h]
0x18014ea90  jle     short loc_18014EAA7
0x18014ea92  mov     rax, [rbx]
0x18014ea95  mov     [rsp+68h+var_40], rax
0x18014ea9a  mov     dword ptr [rsp+68h+var_48], 775h
0x18014eaa2  jmp     loc_18014ED75
0x18014eaa7  add     rdx, [rbx+478h]; Src
0x18014eaae  lea     rcx, [rsp+68h+var_20]; void *
0x18014eab3  mov     r8d, 8; Size
0x18014eab9  call    _TIFFmemcpy
0x18014eabe  test    byte ptr [rbx+10h], 80h
0x18014eac2  jz      short loc_18014EACE
0x18014eac4  lea     rcx, [rsp+68h+var_20]
0x18014eac9  call    TIFFSwabLong8
0x18014eace  mov     rax, qword ptr [rsp+68h+var_20]
0x18014ead3  cmp     rax, 0FFFFh
0x18014ead9  jbe     short loc_18014EAF6
0x18014eadb  lea     r8, aSanityCheckOnD; "Sanity check on directory count failed"
0x18014eae2  mov     rcx, rbx
0x18014eae5  lea     rdx, aTiffadvancedir; "TIFFAdvanceDirectory"
0x18014eaec  call    TIFFErrorExtR
0x18014eaf1  jmp     loc_18014ED92
0x18014eaf6  movzx   eax, ax
0x18014eaf9  lea     rcx, [rax+rax*4]
0x18014eafd  lea     rcx, ds:0[rcx*4]
0x18014eb05  sub     rsi, rcx
0x18014eb08  cmp     r12, rsi
0x18014eb0b  jg      loc_18014EA0F
0x18014eb11  add     rcx, r12
0x18014eb14  lea     rax, [rcx+8]
0x18014eb18  cmp     rax, [rbx+480h]
0x18014eb1f  jg      loc_18014EA0F
0x18014eb25  test    r14, r14
0x18014eb28  jz      short loc_18014EB2D
0x18014eb2a  mov     [r14], rcx
0x18014eb2d  mov     rdx, [rbx+478h]
0x18014eb34  mov     r8d, 8; Size
0x18014eb3a  add     rdx, rcx; Src
0x18014eb3d  mov     rcx, rdi; void *
0x18014eb40  call    _TIFFmemcpy
0x18014eb45  jmp     loc_18014ECFF
0x18014eb4a  test    ecx, ecx
0x18014eb4c  mov     rcx, rbx
0x18014eb4f  jnz     loc_18014EC3F
0x18014eb55  call    _TIFFSeekOK
0x18014eb5a  test    eax, eax
0x18014eb5c  jz      loc_18014EC2A
0x18014eb62  mov     rcx, [rbx+498h]
0x18014eb69  lea     rdx, [rsp+68h+var_28]
0x18014eb6e  mov     rax, [rbx+4A0h]
0x18014eb75  mov     r8d, 2
0x18014eb7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014eb80  cmp     rax, 2
0x18014eb84  jnz     loc_18014EC2A
0x18014eb8a  test    byte ptr [rbx+10h], 80h
0x18014eb8e  jz      short loc_18014EB9A
0x18014eb90  lea     rcx, [rsp+68h+var_28]
0x18014eb95  call    TIFFSwabShort
0x18014eb9a  mov     r9, [rbx+498h]
0x18014eba1  mov     r8d, 1
0x18014eba7  mov     r10, [rbx+4B0h]
0x18014ebae  test    r14, r14
0x18014ebb1  jz      short loc_18014EBCE
0x18014ebb3  movzx   eax, [rsp+68h+var_28]
0x18014ebb8  mov     rcx, r9
0x18014ebbb  lea     edx, [rax+rax*2]
0x18014ebbe  mov     rax, r10
0x18014ebc1  shl     edx, 2
0x18014ebc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014ebc9  mov     [r14], rax
0x18014ebcc  jmp     short loc_18014EBE4
0x18014ebce  movzx   ecx, [rsp+68h+var_28]
0x18014ebd3  mov     rax, r10
0x18014ebd6  lea     edx, [rcx+rcx*2]
0x18014ebd9  mov     rcx, r9
0x18014ebdc  shl     edx, 2
0x18014ebdf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014ebe4  mov     rcx, [rbx+498h]
0x18014ebeb  lea     rdx, [rsp+68h+var_20]
0x18014ebf0  mov     rax, [rbx+4A0h]
0x18014ebf7  mov     r8d, 4
0x18014ebfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014ec02  cmp     rax, 4
0x18014ec06  jz      loc_18014E9F3
0x18014ec0c  mov     r9, [rbx]
0x18014ec0f  lea     r8, aSErrorFetching; "%s: Error fetching directory link"
0x18014ec16  lea     rdx, aTiffadvancedir; "TIFFAdvanceDirectory"
0x18014ec1d  mov     rcx, rbx
0x18014ec20  call    TIFFErrorExtR
0x18014ec25  jmp     loc_18014ED92
0x18014ec2a  mov     rax, [rbx]
0x18014ec2d  mov     [rsp+68h+var_40], rax
0x18014ec32  mov     dword ptr [rsp+68h+var_48], 7A1h
0x18014ec3a  jmp     loc_18014ED75
0x18014ec3f  call    _TIFFSeekOK
0x18014ec44  test    eax, eax
0x18014ec46  jz      loc_18014ED65
0x18014ec4c  mov     rcx, [rbx+498h]
0x18014ec53  lea     rdx, [rsp+68h+var_20]
0x18014ec58  mov     rax, [rbx+4A0h]
0x18014ec5f  mov     r8d, 8
0x18014ec65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014ec6a  cmp     rax, 8
0x18014ec6e  jnz     loc_18014ED65
0x18014ec74  test    byte ptr [rbx+10h], 80h
0x18014ec78  jz      short loc_18014EC84
0x18014ec7a  lea     rcx, [rsp+68h+var_20]
0x18014ec7f  call    TIFFSwabLong8
0x18014ec84  mov     rax, qword ptr [rsp+68h+var_20]
0x18014ec89  cmp     rax, 0FFFFh
0x18014ec8f  jbe     short loc_18014ECA6
0x18014ec91  mov     rax, [rbx]
0x18014ec94  mov     [rsp+68h+var_40], rax
0x18014ec99  mov     dword ptr [rsp+68h+var_48], 7C6h
0x18014eca1  jmp     loc_18014ED75
0x18014eca6  mov     rcx, [rbx+498h]
0x18014ecad  mov     r8d, 1
0x18014ecb3  movzx   eax, ax
0x18014ecb6  lea     rdx, [rax+rax*4]
0x18014ecba  mov     rax, [rbx+4B0h]
0x18014ecc1  shl     rdx, 2
0x18014ecc5  test    r14, r14
0x18014ecc8  jz      short loc_18014ECD4
0x18014ecca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014eccf  mov     [r14], rax
0x18014ecd2  jmp     short loc_18014ECD9
0x18014ecd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014ecd9  mov     rcx, [rbx+498h]
0x18014ece0  mov     r8d, 8
0x18014ece6  mov     rax, [rbx+4A0h]
0x18014eced  mov     rdx, rdi
0x18014ecf0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014ecf5  cmp     rax, 8
0x18014ecf9  jnz     loc_18014EC0C
0x18014ecff  test    byte ptr [rbx+10h], 80h
0x18014ed03  jz      short loc_18014ED0D
0x18014ed05  mov     rcx, rdi
0x18014ed08  call    TIFFSwabLong8
0x18014ed0d  cmp     qword ptr [rdi], 0
0x18014ed11  jz      short loc_18014ED5E
0x18014ed13  inc     dword ptr [r15]
0x18014ed16  mov     rcx, rbx
0x18014ed19  mov     r8, [rdi]
0x18014ed1c  mov     edx, [r15]
0x18014ed1f  call    _TIFFCheckDirNumberAndOffset
0x18014ed24  test    eax, eax
0x18014ed26  jnz     short loc_18014ED5E
0x18014ed28  mov     rdx, [rdi]
0x18014ed2b  lea     r8, aTheNextDirecto; "the next directory %u at offset 0x%llx "...
0x18014ed32  mov     r9d, [r15]
0x18014ed35  lea     ecx, [r9-1]
0x18014ed39  mov     [rsp+68h+var_38], ecx
0x18014ed3d  mov     rcx, rbx
0x18014ed40  mov     [rsp+68h+var_40], rdx
0x18014ed45  mov     [rsp+68h+var_48], rdx
0x18014ed4a  lea     rdx, aTiffadvancedir; "TIFFAdvanceDirectory"
0x18014ed51  call    TIFFWarningExtR
0x18014ed56  xor     eax, eax
0x18014ed58  mov     [rdi], rax
0x18014ed5b  dec     dword ptr [r15]
0x18014ed5e  mov     eax, 1
0x18014ed63  jmp     short loc_18014ED94
0x18014ed65  mov     rax, [rbx]
0x18014ed68  mov     [rsp+68h+var_40], rax
0x18014ed6d  mov     dword ptr [rsp+68h+var_48], 7BDh
0x18014ed75  lea     r9, aDOsObjAmd64fre; "D:\\os\\obj\\amd64fre\\onecoreuap\\wind"...
0x18014ed7c  mov     rcx, rbx
0x18014ed7f  lea     r8, aSDSErrorFetchi; "%s:%d: %s: Error fetching directory cou"...
0x18014ed86  lea     rdx, aTiffadvancedir; "TIFFAdvanceDirectory"
0x18014ed8d  call    TIFFErrorExtR
0x18014ed92  xor     eax, eax
0x18014ed94  mov     rsi, [rsp+68h+arg_0]
0x18014ed99  mov     r12, [rsp+68h+arg_8]
0x18014ed9e  mov     rbx, [rsp+68h+arg_10]
0x18014eda6  add     rsp, 50h
0x18014edaa  pop     r15
0x18014edac  pop     r14
0x18014edae  pop     rdi
0x18014edaf  retn
```
