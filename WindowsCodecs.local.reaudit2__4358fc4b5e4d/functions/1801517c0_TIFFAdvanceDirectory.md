# TIFFAdvanceDirectory

- ea: `0x1801517c0`
- end: `0x180151cb0`
- name: `TIFFAdvanceDirectory`
- size: `1264`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180152170`

## callees

- `0x1801517c0`
- `0x180156870`
- `0x18015d110`
- `0x18015d220`
- `0x18015e5b0`
- `0x18015e5e0`
- `0x18015e630`
- `0x1801665f0`
- `0x180167290`
- `0x1801ce010`

## string_xrefs

- `0x1801517f6`: `TIFFAdvanceDirectory`
- `0x180151919`: `TIFFAdvanceDirectory`
- `0x180151940`: `TIFFAdvanceDirectory`
- `0x1801519e5`: `TIFFAdvanceDirectory`
- `0x180151b16`: `TIFFAdvanceDirectory`
- `0x180151c4a`: `TIFFAdvanceDirectory`
- `0x180151c86`: `TIFFAdvanceDirectory`
- `0x1801517ec`: `Starting directory %u at offset 0x%llx (%llu) might cause an IFD loop`
- `0x180151939`: `%s:%d: %s: Error fetching directory count`
- `0x180151c7f`: `%s:%d: %s: Error fetching directory count`
- `0x18015190f`: `Error fetching directory link`
- `0x1801519db`: `Sanity check on directory count failed`
- `0x180151b0f`: `%s: Error fetching directory link`
- `0x180151c2b`: `the next directory %u at offset 0x%llx (%llu) might be an IFD loop. Treating directory %d as last directory`

## pseudocode

```c
__int64 __fastcall TIFFAdvanceDirectory(const char **a1, unsigned __int64 *a2, __int64 *a3, unsigned int *a4)
{
  __int64 result; // rax
  unsigned __int64 v9; // rdx
  int v10; // ecx
  __int64 v11; // rsi
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // r9
  __int64 v15; // rcx
  __int64 v16; // rax
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v19; // r9
  signed __int64 v20; // r12
  __int64 v21; // rcx
  __int64 v22; // rcx
  __int64 v23; // rdx
  __int64 v24; // r8
  __int64 v25; // r9
  const char *v26; // rcx
  const char *v27; // rax
  __int64 v28; // rdx
  unsigned __int16 v29; // [rsp+40h] [rbp-28h] BYREF
  unsigned int v30[8]; // [rsp+48h] [rbp-20h] BYREF

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
      if ( !(unsigned int)TIFFSeekOK(a1, v9)
        || ((__int64 (__fastcall *)(const char *, unsigned int *, __int64))a1[148])(a1[147], v30, 8) != 8 )
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
        TIFFSwabLong8(v30);
      if ( *(_QWORD *)v30 > 0xFFFFu )
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
      v26 = a1[147];
      v27 = a1[150];
      v28 = 20LL * LOWORD(v30[0]);
      if ( a3 )
        *a3 = ((__int64 (__fastcall *)(const char *, __int64, __int64))v27)(v26, v28, 1);
      else
        ((void (__fastcall *)(const char *, __int64, __int64))v27)(v26, v28, 1);
      if ( ((__int64 (__fastcall *)(const char *, unsigned __int64 *, __int64))a1[148])(a1[147], a2, 8) == 8 )
        goto LABEL_57;
    }
    else
    {
      if ( !(unsigned int)TIFFSeekOK(a1, v9)
        || ((__int64 (__fastcall *)(const char *, unsigned __int16 *, __int64))a1[148])(a1[147], &v29, 2) != 2 )
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
        TIFFSwabShort(&v29, v23, v24, v25);
      if ( a3 )
        *a3 = ((__int64 (__fastcall *)(const char *, _QWORD, __int64))a1[150])(a1[147], 12 * (unsigned int)v29, 1);
      else
        ((void (__fastcall *)(const char *, _QWORD, __int64))a1[150])(a1[147], 12 * (unsigned int)v29, 1);
      if ( ((__int64 (__fastcall *)(const char *, unsigned int *, __int64))a1[148])(a1[147], v30, 4) == 4 )
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
    v20 = v9 + 8;
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
    TIFFmemcpy(v30, &a1[143][v9], 8u);
    if ( *((char *)a1 + 16) < 0 )
      TIFFSwabLong8(v30);
    if ( *(_QWORD *)v30 > 0xFFFFu )
    {
      TIFFErrorExtR(a1, "TIFFAdvanceDirectory", "Sanity check on directory count failed");
      return 0;
    }
    v21 = 20LL * LOWORD(v30[0]);
    if ( v20 > 0x7FFFFFFFFFFFFFF7LL - v21 || (v22 = v20 + v21, v22 + 8 > (__int64)a1[144]) )
    {
LABEL_21:
      TIFFErrorExtR(a1, "TIFFAdvanceDirectory", "Error fetching directory link");
      return 0;
    }
    if ( a3 )
      *a3 = v22;
    TIFFmemcpy(a2, &a1[143][v22], 8u);
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
  TIFFmemcpy(&v29, &a1[143][v9], 2u);
  if ( *((char *)a1 + 16) < 0 )
    TIFFSwabShort(&v29, v12, v13, v14);
  v15 = v11 + 12 * (unsigned int)v29;
  if ( __OFSUB__(v15, v11) )
    goto LABEL_21;
  if ( v15 < 12 * (unsigned int)v29 )
    goto LABEL_21;
  v16 = v15 + 4;
  if ( v15 + 4 <= v15 || v16 < 4 || v16 > (__int64)a1[144] )
    goto LABEL_21;
  if ( a3 )
    *a3 = v15;
  TIFFmemcpy(v30, &a1[143][v15], 4u);
LABEL_18:
  if ( *((char *)a1 + 16) < 0 )
    TIFFSwabLong(v30, v17, v18, v19);
  *a2 = v30[0];
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
0x1801517c0  mov     [rsp+arg_10], rbx
0x1801517c5  push    rdi
0x1801517c6  push    r14
0x1801517c8  push    r15
0x1801517ca  sub     rsp, 50h
0x1801517ce  mov     r14, r8
0x1801517d1  mov     rdi, rdx
0x1801517d4  mov     r8, [rdx]
0x1801517d7  mov     r15, r9
0x1801517da  mov     edx, [r9]
0x1801517dd  mov     rbx, rcx
0x1801517e0  call    _TIFFCheckDirNumberAndOffset
0x1801517e5  test    eax, eax
0x1801517e7  jnz     short loc_180151829
0x1801517e9  mov     rax, [rdi]
0x1801517ec  lea     r8, aStartingDirect; "Starting directory %u at offset 0x%llx "...
0x1801517f3  mov     r9d, [r15]
0x1801517f6  lea     rdx, aTiffadvancedir; "TIFFAdvanceDirectory"
0x1801517fd  mov     [rsp+68h+var_40], rax
0x180151802  mov     rcx, rbx
0x180151805  mov     [rsp+68h+var_48], rax
0x18015180a  call    TIFFErrorExtR
0x18015180f  xor     eax, eax
0x180151811  mov     [rdi], rax
0x180151814  mov     [r15], eax
0x180151817  mov     rbx, [rsp+68h+arg_10]
0x18015181f  add     rsp, 50h
0x180151823  pop     r15
0x180151825  pop     r14
0x180151827  pop     rdi
0x180151828  retn
0x180151829  mov     ecx, [rbx+10h]
0x18015182c  mov     rdx, [rdi]
0x18015182f  and     ecx, 80000h
0x180151835  test    dword ptr [rbx+10h], 800h
0x18015183c  mov     [rsp+68h+arg_0], rsi
0x180151841  mov     [rsp+68h+arg_8], r12
0x180151846  jz      loc_180151A4A
0x18015184c  test    ecx, ecx
0x18015184e  jnz     loc_180151961
0x180151854  lea     rsi, [rdx+2]
0x180151858  cmp     rsi, rdx
0x18015185b  jl      loc_18015192A
0x180151861  cmp     rsi, 2
0x180151865  jl      loc_18015192A
0x18015186b  cmp     rsi, [rbx+480h]
0x180151872  jg      loc_18015192A
0x180151878  add     rdx, [rbx+478h]; Src
0x18015187f  lea     rcx, [rsp+68h+var_28]; void *
0x180151884  mov     r8d, 2; Size
0x18015188a  call    _TIFFmemcpy
0x18015188f  test    byte ptr [rbx+10h], 80h
0x180151893  jz      short loc_18015189F
0x180151895  lea     rcx, [rsp+68h+var_28]
0x18015189a  call    TIFFSwabShort
0x18015189f  movzx   eax, [rsp+68h+var_28]
0x1801518a4  lea     ecx, [rax+rax*2]
0x1801518a7  shl     ecx, 2
0x1801518aa  mov     eax, ecx
0x1801518ac  add     rcx, rsi
0x1801518af  cmp     rcx, rsi
0x1801518b2  jl      short loc_18015190F
0x1801518b4  cmp     rcx, rax
0x1801518b7  jl      short loc_18015190F
0x1801518b9  lea     rax, [rcx+4]
0x1801518bd  cmp     rax, rcx
0x1801518c0  jl      short loc_18015190F
0x1801518c2  cmp     rax, 4
0x1801518c6  jl      short loc_18015190F
0x1801518c8  cmp     rax, [rbx+480h]
0x1801518cf  jg      short loc_18015190F
0x1801518d1  test    r14, r14
0x1801518d4  jz      short loc_1801518D9
0x1801518d6  mov     [r14], rcx
0x1801518d9  mov     rdx, [rbx+478h]
0x1801518e0  mov     r8d, 4; Size
0x1801518e6  add     rdx, rcx; Src
0x1801518e9  lea     rcx, [rsp+68h+var_20]; void *
0x1801518ee  call    _TIFFmemcpy
0x1801518f3  test    byte ptr [rbx+10h], 80h
0x1801518f7  jz      short loc_180151903
0x1801518f9  lea     rcx, [rsp+68h+var_20]
0x1801518fe  call    TIFFSwabLong
0x180151903  mov     eax, [rsp+68h+var_20]
0x180151907  mov     [rdi], rax
0x18015190a  jmp     loc_180151C0D
0x18015190f  lea     r8, aErrorFetchingD; "Error fetching directory link"
0x180151916  mov     rcx, rbx
0x180151919  lea     rdx, aTiffadvancedir; "TIFFAdvanceDirectory"
0x180151920  call    TIFFErrorExtR
0x180151925  jmp     loc_180151C92
0x18015192a  mov     rax, [rbx]
0x18015192d  lea     r9, aDOsObjAmd64fre; "D:\\os\\obj\\amd64fre\\onecoreuap\\wind"...
0x180151934  mov     [rsp+68h+var_40], rax
0x180151939  lea     r8, aSDSErrorFetchi; "%s:%d: %s: Error fetching directory cou"...
0x180151940  lea     rdx, aTiffadvancedir; "TIFFAdvanceDirectory"
0x180151947  mov     dword ptr [rsp+68h+var_48], 74Dh
0x18015194f  mov     rcx, rbx
0x180151952  call    TIFFErrorExtR
0x180151957  xor     eax, eax
0x180151959  mov     [rdi], rax
0x18015195c  jmp     loc_180151C94
0x180151961  mov     rsi, 7FFFFFFFFFFFFFF7h
0x18015196b  cmp     rdx, rsi
0x18015196e  jbe     short loc_180151985
0x180151970  mov     rax, [rbx]
0x180151973  mov     [rsp+68h+var_40], rax
0x180151978  mov     dword ptr [rsp+68h+var_48], 76Ch
0x180151980  jmp     loc_180151C75
0x180151985  lea     r12, [rdx+8]
0x180151989  cmp     r12, [rbx+480h]
0x180151990  jle     short loc_1801519A7
0x180151992  mov     rax, [rbx]
0x180151995  mov     [rsp+68h+var_40], rax
0x18015199a  mov     dword ptr [rsp+68h+var_48], 775h
0x1801519a2  jmp     loc_180151C75
0x1801519a7  add     rdx, [rbx+478h]; Src
0x1801519ae  lea     rcx, [rsp+68h+var_20]; void *
0x1801519b3  mov     r8d, 8; Size
0x1801519b9  call    _TIFFmemcpy
0x1801519be  test    byte ptr [rbx+10h], 80h
0x1801519c2  jz      short loc_1801519CE
0x1801519c4  lea     rcx, [rsp+68h+var_20]
0x1801519c9  call    TIFFSwabLong8
0x1801519ce  mov     rax, qword ptr [rsp+68h+var_20]
0x1801519d3  cmp     rax, 0FFFFh
0x1801519d9  jbe     short loc_1801519F6
0x1801519db  lea     r8, aSanityCheckOnD; "Sanity check on directory count failed"
0x1801519e2  mov     rcx, rbx
0x1801519e5  lea     rdx, aTiffadvancedir; "TIFFAdvanceDirectory"
0x1801519ec  call    TIFFErrorExtR
0x1801519f1  jmp     loc_180151C92
0x1801519f6  movzx   eax, ax
0x1801519f9  lea     rcx, [rax+rax*4]
0x1801519fd  lea     rcx, ds:0[rcx*4]
0x180151a05  sub     rsi, rcx
0x180151a08  cmp     r12, rsi
0x180151a0b  jg      loc_18015190F
0x180151a11  add     rcx, r12
0x180151a14  lea     rax, [rcx+8]
0x180151a18  cmp     rax, [rbx+480h]
0x180151a1f  jg      loc_18015190F
0x180151a25  test    r14, r14
0x180151a28  jz      short loc_180151A2D
0x180151a2a  mov     [r14], rcx
0x180151a2d  mov     rdx, [rbx+478h]
0x180151a34  mov     r8d, 8; Size
0x180151a3a  add     rdx, rcx; Src
0x180151a3d  mov     rcx, rdi; void *
0x180151a40  call    _TIFFmemcpy
0x180151a45  jmp     loc_180151BFF
0x180151a4a  test    ecx, ecx
0x180151a4c  mov     rcx, rbx
0x180151a4f  jnz     loc_180151B3F
0x180151a55  call    _TIFFSeekOK
0x180151a5a  test    eax, eax
0x180151a5c  jz      loc_180151B2A
0x180151a62  mov     rcx, [rbx+498h]
0x180151a69  lea     rdx, [rsp+68h+var_28]
0x180151a6e  mov     rax, [rbx+4A0h]
0x180151a75  mov     r8d, 2
0x180151a7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180151a80  cmp     rax, 2
0x180151a84  jnz     loc_180151B2A
0x180151a8a  test    byte ptr [rbx+10h], 80h
0x180151a8e  jz      short loc_180151A9A
0x180151a90  lea     rcx, [rsp+68h+var_28]
0x180151a95  call    TIFFSwabShort
0x180151a9a  mov     r9, [rbx+498h]
0x180151aa1  mov     r8d, 1
0x180151aa7  mov     r10, [rbx+4B0h]
0x180151aae  test    r14, r14
0x180151ab1  jz      short loc_180151ACE
0x180151ab3  movzx   eax, [rsp+68h+var_28]
0x180151ab8  mov     rcx, r9
0x180151abb  lea     edx, [rax+rax*2]
0x180151abe  mov     rax, r10
0x180151ac1  shl     edx, 2
0x180151ac4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180151ac9  mov     [r14], rax
0x180151acc  jmp     short loc_180151AE4
0x180151ace  movzx   ecx, [rsp+68h+var_28]
0x180151ad3  mov     rax, r10
0x180151ad6  lea     edx, [rcx+rcx*2]
0x180151ad9  mov     rcx, r9
0x180151adc  shl     edx, 2
0x180151adf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180151ae4  mov     rcx, [rbx+498h]
0x180151aeb  lea     rdx, [rsp+68h+var_20]
0x180151af0  mov     rax, [rbx+4A0h]
0x180151af7  mov     r8d, 4
0x180151afd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180151b02  cmp     rax, 4
0x180151b06  jz      loc_1801518F3
0x180151b0c  mov     r9, [rbx]
0x180151b0f  lea     r8, aSErrorFetching; "%s: Error fetching directory link"
0x180151b16  lea     rdx, aTiffadvancedir; "TIFFAdvanceDirectory"
0x180151b1d  mov     rcx, rbx
0x180151b20  call    TIFFErrorExtR
0x180151b25  jmp     loc_180151C92
0x180151b2a  mov     rax, [rbx]
0x180151b2d  mov     [rsp+68h+var_40], rax
0x180151b32  mov     dword ptr [rsp+68h+var_48], 7A1h
0x180151b3a  jmp     loc_180151C75
0x180151b3f  call    _TIFFSeekOK
0x180151b44  test    eax, eax
0x180151b46  jz      loc_180151C65
0x180151b4c  mov     rcx, [rbx+498h]
0x180151b53  lea     rdx, [rsp+68h+var_20]
0x180151b58  mov     rax, [rbx+4A0h]
0x180151b5f  mov     r8d, 8
0x180151b65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180151b6a  cmp     rax, 8
0x180151b6e  jnz     loc_180151C65
0x180151b74  test    byte ptr [rbx+10h], 80h
0x180151b78  jz      short loc_180151B84
0x180151b7a  lea     rcx, [rsp+68h+var_20]
0x180151b7f  call    TIFFSwabLong8
0x180151b84  mov     rax, qword ptr [rsp+68h+var_20]
0x180151b89  cmp     rax, 0FFFFh
0x180151b8f  jbe     short loc_180151BA6
0x180151b91  mov     rax, [rbx]
0x180151b94  mov     [rsp+68h+var_40], rax
0x180151b99  mov     dword ptr [rsp+68h+var_48], 7C6h
0x180151ba1  jmp     loc_180151C75
0x180151ba6  mov     rcx, [rbx+498h]
0x180151bad  mov     r8d, 1
0x180151bb3  movzx   eax, ax
0x180151bb6  lea     rdx, [rax+rax*4]
0x180151bba  mov     rax, [rbx+4B0h]
0x180151bc1  shl     rdx, 2
0x180151bc5  test    r14, r14
0x180151bc8  jz      short loc_180151BD4
0x180151bca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180151bcf  mov     [r14], rax
0x180151bd2  jmp     short loc_180151BD9
0x180151bd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180151bd9  mov     rcx, [rbx+498h]
0x180151be0  mov     r8d, 8
0x180151be6  mov     rax, [rbx+4A0h]
0x180151bed  mov     rdx, rdi
0x180151bf0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180151bf5  cmp     rax, 8
0x180151bf9  jnz     loc_180151B0C
0x180151bff  test    byte ptr [rbx+10h], 80h
0x180151c03  jz      short loc_180151C0D
0x180151c05  mov     rcx, rdi
0x180151c08  call    TIFFSwabLong8
0x180151c0d  cmp     qword ptr [rdi], 0
0x180151c11  jz      short loc_180151C5E
0x180151c13  inc     dword ptr [r15]
0x180151c16  mov     rcx, rbx
0x180151c19  mov     r8, [rdi]
0x180151c1c  mov     edx, [r15]
0x180151c1f  call    _TIFFCheckDirNumberAndOffset
0x180151c24  test    eax, eax
0x180151c26  jnz     short loc_180151C5E
0x180151c28  mov     rdx, [rdi]
0x180151c2b  lea     r8, aTheNextDirecto; "the next directory %u at offset 0x%llx "...
0x180151c32  mov     r9d, [r15]
0x180151c35  lea     ecx, [r9-1]
0x180151c39  mov     [rsp+68h+var_38], ecx
0x180151c3d  mov     rcx, rbx
0x180151c40  mov     [rsp+68h+var_40], rdx
0x180151c45  mov     [rsp+68h+var_48], rdx
0x180151c4a  lea     rdx, aTiffadvancedir; "TIFFAdvanceDirectory"
0x180151c51  call    TIFFWarningExtR
0x180151c56  xor     eax, eax
0x180151c58  mov     [rdi], rax
0x180151c5b  dec     dword ptr [r15]
0x180151c5e  mov     eax, 1
0x180151c63  jmp     short loc_180151C94
0x180151c65  mov     rax, [rbx]
0x180151c68  mov     [rsp+68h+var_40], rax
0x180151c6d  mov     dword ptr [rsp+68h+var_48], 7BDh
0x180151c75  lea     r9, aDOsObjAmd64fre; "D:\\os\\obj\\amd64fre\\onecoreuap\\wind"...
0x180151c7c  mov     rcx, rbx
0x180151c7f  lea     r8, aSDSErrorFetchi; "%s:%d: %s: Error fetching directory cou"...
0x180151c86  lea     rdx, aTiffadvancedir; "TIFFAdvanceDirectory"
0x180151c8d  call    TIFFErrorExtR
0x180151c92  xor     eax, eax
0x180151c94  mov     rsi, [rsp+68h+arg_0]
0x180151c99  mov     r12, [rsp+68h+arg_8]
0x180151c9e  mov     rbx, [rsp+68h+arg_10]
0x180151ca6  add     rsp, 50h
0x180151caa  pop     r15
0x180151cac  pop     r14
0x180151cae  pop     rdi
0x180151caf  retn
```
