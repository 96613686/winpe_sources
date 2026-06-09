# std::_Partition_by_median_guess_unchecked<Jot::OCRLanguageGalleryItem *,std::less<void>>(Jot::OCRLanguageGalleryItem *,Jot::OCRLanguageGalleryItem *,std::less<void>)

- ea: `0x1400f1a30`
- end: `0x1400f1dfa`
- name: `??$_Partition_by_median_guess_unchecked@PEAUOCRLanguageGalleryItem@Jot@@U?$less@X@std@@@std@@YA?AU?$pair@PEAUOCRLanguageGalleryItem@Jot@@PEAU12@@0@PEAUOCRLanguageGalleryItem@Jot@@0U?$less@X@0@@Z`
- size: `970`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400f2208`

## callees

- `0x1400f155c`
- `0x1400f1a30`
- `0x1400f25a4`

## import_xrefs

- `Mso30Win32Client!__imp_MsoGetInstallLcid` at `0x1400f1abd`
- `Mso30Win32Client!__imp_MsoGetInstallLcid` at `0x1400f1b07`
- `Mso30Win32Client!__imp_MsoGetInstallLcid` at `0x1400f1b67`
- `Mso30Win32Client!__imp_MsoGetInstallLcid` at `0x1400f1ba7`
- `Mso30Win32Client!__imp_MsoGetInstallLcid` at `0x1400f1bff`
- `Mso30Win32Client!__imp_MsoGetInstallLcid` at `0x1400f1c41`
- `Mso30Win32Client!__imp_MsoGetInstallLcid` at `0x1400f1cb9`
- `Mso30Win32Client!__imp_MsoGetInstallLcid` at `0x1400f1cfb`
- `Mso30Win32Client!__imp_MsoGetInstallLcid` at `0x1400f1abd`
- `Mso30Win32Client!__imp_MsoGetInstallLcid` at `0x1400f1b07`
- `Mso30Win32Client!__imp_MsoGetInstallLcid` at `0x1400f1b67`
- `Mso30Win32Client!__imp_MsoGetInstallLcid` at `0x1400f1ba7`
- `Mso30Win32Client!__imp_MsoGetInstallLcid` at `0x1400f1bff`
- `Mso30Win32Client!__imp_MsoGetInstallLcid` at `0x1400f1c41`
- `Mso30Win32Client!__imp_MsoGetInstallLcid` at `0x1400f1cb9`
- `Mso30Win32Client!__imp_MsoGetInstallLcid` at `0x1400f1cfb`
- `Mso30Win32Client!__imp_?MsoCompareStringW@@YAHKKPEB_WH0H@Z` at `0x1400f1ade`
- `Mso30Win32Client!__imp_?MsoCompareStringW@@YAHKKPEB_WH0H@Z` at `0x1400f1b28`
- `Mso30Win32Client!__imp_?MsoCompareStringW@@YAHKKPEB_WH0H@Z` at `0x1400f1b82`
- `Mso30Win32Client!__imp_?MsoCompareStringW@@YAHKKPEB_WH0H@Z` at `0x1400f1bc2`
- `Mso30Win32Client!__imp_?MsoCompareStringW@@YAHKKPEB_WH0H@Z` at `0x1400f1c1c`
- `Mso30Win32Client!__imp_?MsoCompareStringW@@YAHKKPEB_WH0H@Z` at `0x1400f1c5e`
- `Mso30Win32Client!__imp_?MsoCompareStringW@@YAHKKPEB_WH0H@Z` at `0x1400f1cd6`
- `Mso30Win32Client!__imp_?MsoCompareStringW@@YAHKKPEB_WH0H@Z` at `0x1400f1d18`
- `Mso30Win32Client!__imp_?MsoCompareStringW@@YAHKKPEB_WH0H@Z` at `0x1400f1ade`
- `Mso30Win32Client!__imp_?MsoCompareStringW@@YAHKKPEB_WH0H@Z` at `0x1400f1b28`
- `Mso30Win32Client!__imp_?MsoCompareStringW@@YAHKKPEB_WH0H@Z` at `0x1400f1b82`
- `Mso30Win32Client!__imp_?MsoCompareStringW@@YAHKKPEB_WH0H@Z` at `0x1400f1bc2`
- `Mso30Win32Client!__imp_?MsoCompareStringW@@YAHKKPEB_WH0H@Z` at `0x1400f1c1c`
- `Mso30Win32Client!__imp_?MsoCompareStringW@@YAHKKPEB_WH0H@Z` at `0x1400f1c5e`
- `Mso30Win32Client!__imp_?MsoCompareStringW@@YAHKKPEB_WH0H@Z` at `0x1400f1cd6`
- `Mso30Win32Client!__imp_?MsoCompareStringW@@YAHKKPEB_WH0H@Z` at `0x1400f1d18`

## pseudocode

```c
unsigned __int64 *__fastcall std::_Partition_by_median_guess_unchecked<Jot::OCRLanguageGalleryItem *,std::less<void>>(
        unsigned __int64 *a1,
        unsigned __int64 a2,
        unsigned __int64 a3)
{
  unsigned __int64 v3; // r12
  unsigned __int64 v4; // r13
  unsigned __int64 v5; // rbx
  unsigned __int64 v6; // rdi
  unsigned __int64 v7; // rsi
  const wchar_t *v8; // rbp
  const wchar_t *v9; // r14
  unsigned int InstallLcid; // eax
  const wchar_t *v11; // r14
  const wchar_t *v12; // rbp
  unsigned int v13; // eax
  const wchar_t *v14; // rsi
  const wchar_t *v15; // rbp
  unsigned int v16; // eax
  const wchar_t *v17; // rbp
  const wchar_t *v18; // rsi
  unsigned int v19; // eax
  unsigned __int64 v20; // rsi
  unsigned __int64 v21; // rbp
  const wchar_t *v22; // r15
  const wchar_t *v23; // r14
  unsigned int v24; // eax
  const wchar_t *v25; // r15
  const wchar_t *v26; // r14
  unsigned int v27; // eax
  unsigned __int64 v28; // r15
  bool v29; // zf
  unsigned __int64 v30; // r14
  const wchar_t *v31; // r13
  const wchar_t *v32; // r12
  unsigned int v33; // eax
  const wchar_t *v34; // r13
  const wchar_t *v35; // r12
  unsigned int v36; // eax
  unsigned __int64 v37; // rax
  unsigned __int64 *result; // rax

  v3 = a2;
  v4 = a3;
  v5 = a2 + 40 * ((__int64)(0xCCCCCCCCCCCCCCCDuLL * ((__int64)(a3 - a2) >> 3)) >> 1);
  std::_Guess_median_unchecked<Jot::OCRLanguageGalleryItem *,std::less<void>>(a2, v5, a3 - 40);
  v6 = v5 + 40;
  if ( v3 < v5 )
  {
    v7 = v5 - 40;
    do
    {
      v8 = (const wchar_t *)v5;
      if ( *(_QWORD *)(v7 + 64) > 7u )
        v8 = *(const wchar_t **)v5;
      v9 = (const wchar_t *)v7;
      if ( *(_QWORD *)(v7 + 24) > 7u )
        v9 = *(const wchar_t **)v7;
      InstallLcid = MsoGetInstallLcid();
      if ( MsoCompareStringW(InstallLcid, 1u, v9, -1, v8, -1) == 1 )
        break;
      v11 = (const wchar_t *)v7;
      if ( *(_QWORD *)(v7 + 24) > 7u )
        v11 = *(const wchar_t **)v7;
      v12 = (const wchar_t *)v5;
      if ( *(_QWORD *)(v7 + 64) > 7u )
        v12 = *(const wchar_t **)v5;
      v13 = MsoGetInstallLcid();
      if ( MsoCompareStringW(v13, 1u, v12, -1, v11, -1) == 1 )
        break;
      v5 -= 40LL;
      v7 -= 40LL;
    }
    while ( v3 < v5 );
  }
  while ( v6 < v4 )
  {
    v14 = (const wchar_t *)v5;
    if ( *(_QWORD *)(v5 + 24) > 7u )
      v14 = *(const wchar_t **)v5;
    v15 = (const wchar_t *)v6;
    if ( *(_QWORD *)(v6 + 24) > 7u )
      v15 = *(const wchar_t **)v6;
    v16 = MsoGetInstallLcid();
    if ( MsoCompareStringW(v16, 1u, v15, -1, v14, -1) == 1 )
      break;
    v17 = (const wchar_t *)v6;
    if ( *(_QWORD *)(v6 + 24) > 7u )
      v17 = *(const wchar_t **)v6;
    v18 = (const wchar_t *)v5;
    if ( *(_QWORD *)(v5 + 24) > 7u )
      v18 = *(const wchar_t **)v5;
    v19 = MsoGetInstallLcid();
    if ( MsoCompareStringW(v19, 1u, v18, -1, v17, -1) == 1 )
      break;
    v6 += 40LL;
  }
  v20 = v6;
  v21 = v5;
  while ( 2 )
  {
    while ( v20 < v4 )
    {
      v22 = (const wchar_t *)v20;
      if ( *(_QWORD *)(v20 + 24) > 7u )
        v22 = *(const wchar_t **)v20;
      v23 = (const wchar_t *)v5;
      if ( *(_QWORD *)(v5 + 24) > 7u )
        v23 = *(const wchar_t **)v5;
      v24 = MsoGetInstallLcid();
      if ( MsoCompareStringW(v24, 1u, v23, -1, v22, -1) != 1 )
      {
        v25 = (const wchar_t *)v5;
        if ( *(_QWORD *)(v5 + 24) > 7u )
          v25 = *(const wchar_t **)v5;
        v26 = (const wchar_t *)v20;
        if ( *(_QWORD *)(v20 + 24) > 7u )
          v26 = *(const wchar_t **)v20;
        v27 = MsoGetInstallLcid();
        if ( MsoCompareStringW(v27, 1u, v26, -1, v25, -1) == 1 )
          break;
        if ( v6 != v20 )
          std::swap<Jot::OCRLanguageGalleryItem,0>(v6, v20);
        v6 += 40LL;
      }
      v20 += 40LL;
    }
    v28 = v5;
    v29 = v21 == v3;
    if ( v21 <= v3 )
      goto LABEL_61;
    v30 = v21 - 40;
    while ( 1 )
    {
      v31 = (const wchar_t *)v5;
      if ( *(_QWORD *)(v5 + 24) > 7u )
        v31 = *(const wchar_t **)v5;
      v32 = (const wchar_t *)v30;
      if ( *(_QWORD *)(v30 + 24) > 7u )
        v32 = *(const wchar_t **)v30;
      v33 = MsoGetInstallLcid();
      if ( MsoCompareStringW(v33, 1u, v32, -1, v31, -1) == 1 )
        goto LABEL_57;
      v34 = (const wchar_t *)v30;
      if ( *(_QWORD *)(v30 + 24) > 7u )
        v34 = *(const wchar_t **)v30;
      v35 = (const wchar_t *)v5;
      if ( *(_QWORD *)(v5 + 24) > 7u )
        v35 = *(const wchar_t **)v5;
      v36 = MsoGetInstallLcid();
      if ( MsoCompareStringW(v36, 1u, v35, -1, v34, -1) == 1 )
        break;
      v5 -= 40LL;
      if ( v5 != v30 )
        std::swap<Jot::OCRLanguageGalleryItem,0>(v5, v30);
LABEL_57:
      v3 = a2;
      v21 -= 40LL;
      v30 -= 40LL;
      v28 = v5;
      if ( a2 >= v21 )
        goto LABEL_60;
    }
    v3 = a2;
LABEL_60:
    v4 = a3;
    v29 = v21 == v3;
LABEL_61:
    if ( !v29 )
    {
      v21 -= 40LL;
      if ( v20 != v4 )
      {
        v28 = v20;
        v37 = v21;
        goto LABEL_71;
      }
      v5 -= 40LL;
      if ( v21 != v5 )
        std::swap<Jot::OCRLanguageGalleryItem,0>(v21, v5);
      v6 -= 40LL;
      v28 = v5;
      v37 = v6;
LABEL_72:
      std::swap<Jot::OCRLanguageGalleryItem,0>(v28, v37);
      continue;
    }
    break;
  }
  if ( v20 != v4 )
  {
    if ( v6 != v20 )
      std::swap<Jot::OCRLanguageGalleryItem,0>(v5, v6);
    v37 = v20;
    v6 += 40LL;
    v5 += 40LL;
LABEL_71:
    v20 += 40LL;
    goto LABEL_72;
  }
  result = a1;
  *a1 = v5;
  a1[1] = v6;
  return result;
}

```

## disassembly

```asm
0x1400f1a30  mov     rax, rsp
0x1400f1a33  mov     [rax+20h], rbx
0x1400f1a37  mov     [rax+18h], r8
0x1400f1a3b  mov     [rax+10h], rdx
0x1400f1a3f  mov     [rax+8], rcx
0x1400f1a43  push    rbp
0x1400f1a44  push    rsi
0x1400f1a45  push    rdi
0x1400f1a46  push    r12
0x1400f1a48  push    r13
0x1400f1a4a  push    r14
0x1400f1a4c  push    r15
0x1400f1a4e  sub     rsp, 40h
0x1400f1a52  mov     rax, r8
0x1400f1a55  mov     r12, rdx
0x1400f1a58  sub     rax, rdx
0x1400f1a5b  mov     rcx, 0CCCCCCCCCCCCCCCDh
0x1400f1a65  sar     rax, 3
0x1400f1a69  mov     r13, r8
0x1400f1a6c  imul    rax, rcx
0x1400f1a70  add     r8, 0FFFFFFFFFFFFFFD8h
0x1400f1a74  mov     rcx, r12
0x1400f1a77  sar     rax, 1
0x1400f1a7a  lea     rax, [rax+rax*4]
0x1400f1a7e  lea     rbx, [rdx+rax*8]
0x1400f1a82  mov     rdx, rbx
0x1400f1a85  call    ??$_Guess_median_unchecked@PEAUOCRLanguageGalleryItem@Jot@@U?$less@X@std@@@std@@YAXPEAUOCRLanguageGalleryItem@Jot@@00U?$less@X@0@@Z; std::_Guess_median_unchecked<Jot::OCRLanguageGalleryItem *,std::less<void>>(Jot::OCRLanguageGalleryItem *,Jot::OCRLanguageGalleryItem *,Jot::OCRLanguageGalleryItem *,std::less<void>)
0x1400f1a8a  or      r15d, 0FFFFFFFFh
0x1400f1a8e  lea     rdi, [rbx+28h]
0x1400f1a92  lea     r14d, [r15+2]
0x1400f1a96  cmp     r12, rbx
0x1400f1a99  jnb     loc_1400F1BD1
0x1400f1a9f  lea     rsi, [rbx-28h]
0x1400f1aa3  cmp     qword ptr [rsi+40h], 7
0x1400f1aa8  mov     rbp, rbx
0x1400f1aab  jbe     short loc_1400F1AB0
0x1400f1aad  mov     rbp, [rbx]
0x1400f1ab0  cmp     qword ptr [rsi+18h], 7
0x1400f1ab5  mov     r14, rsi
0x1400f1ab8  jbe     short loc_1400F1ABD
0x1400f1aba  mov     r14, [rsi]
0x1400f1abd  call    cs:__imp_MsoGetInstallLcid
0x1400f1ac3  mov     r8, r14
0x1400f1ac6  mov     [rsp+78h+var_50], r15d
0x1400f1acb  mov     r14d, 1
0x1400f1ad1  mov     [rsp+78h+var_58], rbp
0x1400f1ad6  mov     edx, r14d
0x1400f1ad9  mov     r9d, r15d
0x1400f1adc  mov     ecx, eax
0x1400f1ade  call    cs:__imp_?MsoCompareStringW@@YAHKKPEB_WH0H@Z; MsoCompareStringW(ulong,ulong,wchar_t const *,int,wchar_t const *,int)
0x1400f1ae4  cmp     eax, r14d
0x1400f1ae7  jz      loc_1400F1BD1
0x1400f1aed  cmp     qword ptr [rsi+18h], 7
0x1400f1af2  mov     r14, rsi
0x1400f1af5  jbe     short loc_1400F1AFA
0x1400f1af7  mov     r14, [rsi]
0x1400f1afa  cmp     qword ptr [rsi+40h], 7
0x1400f1aff  mov     rbp, rbx
0x1400f1b02  jbe     short loc_1400F1B07
0x1400f1b04  mov     rbp, [rbx]
0x1400f1b07  call    cs:__imp_MsoGetInstallLcid
0x1400f1b0d  mov     [rsp+78h+var_50], r15d
0x1400f1b12  mov     r9d, r15d
0x1400f1b15  mov     [rsp+78h+var_58], r14
0x1400f1b1a  mov     r8, rbp
0x1400f1b1d  mov     r14d, 1
0x1400f1b23  mov     ecx, eax
0x1400f1b25  mov     edx, r14d
0x1400f1b28  call    cs:__imp_?MsoCompareStringW@@YAHKKPEB_WH0H@Z; MsoCompareStringW(ulong,ulong,wchar_t const *,int,wchar_t const *,int)
0x1400f1b2e  cmp     eax, r14d
0x1400f1b31  jz      loc_1400F1BD1
0x1400f1b37  sub     rbx, 28h ; '('
0x1400f1b3b  sub     rsi, 28h ; '('
0x1400f1b3f  cmp     r12, rbx
0x1400f1b42  jb      loc_1400F1AA3
0x1400f1b48  jmp     loc_1400F1BD1
0x1400f1b4d  cmp     qword ptr [rbx+18h], 7
0x1400f1b52  mov     rsi, rbx
0x1400f1b55  jbe     short loc_1400F1B5A
0x1400f1b57  mov     rsi, [rbx]
0x1400f1b5a  cmp     qword ptr [rdi+18h], 7
0x1400f1b5f  mov     rbp, rdi
0x1400f1b62  jbe     short loc_1400F1B67
0x1400f1b64  mov     rbp, [rdi]
0x1400f1b67  call    cs:__imp_MsoGetInstallLcid
0x1400f1b6d  mov     [rsp+78h+var_50], r15d
0x1400f1b72  mov     r9d, r15d
0x1400f1b75  mov     ecx, eax
0x1400f1b77  mov     [rsp+78h+var_58], rsi
0x1400f1b7c  mov     r8, rbp
0x1400f1b7f  mov     edx, r14d
0x1400f1b82  call    cs:__imp_?MsoCompareStringW@@YAHKKPEB_WH0H@Z; MsoCompareStringW(ulong,ulong,wchar_t const *,int,wchar_t const *,int)
0x1400f1b88  cmp     eax, r14d
0x1400f1b8b  jz      short loc_1400F1BDA
0x1400f1b8d  cmp     qword ptr [rdi+18h], 7
0x1400f1b92  mov     rbp, rdi
0x1400f1b95  jbe     short loc_1400F1B9A
0x1400f1b97  mov     rbp, [rdi]
0x1400f1b9a  cmp     qword ptr [rbx+18h], 7
0x1400f1b9f  mov     rsi, rbx
0x1400f1ba2  jbe     short loc_1400F1BA7
0x1400f1ba4  mov     rsi, [rbx]
0x1400f1ba7  call    cs:__imp_MsoGetInstallLcid
0x1400f1bad  mov     [rsp+78h+var_50], r15d
0x1400f1bb2  mov     r9d, r15d
0x1400f1bb5  mov     ecx, eax
0x1400f1bb7  mov     [rsp+78h+var_58], rbp
0x1400f1bbc  mov     r8, rsi
0x1400f1bbf  mov     edx, r14d
0x1400f1bc2  call    cs:__imp_?MsoCompareStringW@@YAHKKPEB_WH0H@Z; MsoCompareStringW(ulong,ulong,wchar_t const *,int,wchar_t const *,int)
0x1400f1bc8  cmp     eax, r14d
0x1400f1bcb  jz      short loc_1400F1BDA
0x1400f1bcd  add     rdi, 28h ; '('
0x1400f1bd1  cmp     rdi, r13
0x1400f1bd4  jb      loc_1400F1B4D
0x1400f1bda  mov     rsi, rdi
0x1400f1bdd  mov     rbp, rbx
0x1400f1be0  jmp     loc_1400F1C81
0x1400f1be5  cmp     qword ptr [rsi+18h], 7
0x1400f1bea  mov     r15, rsi
0x1400f1bed  jbe     short loc_1400F1BF2
0x1400f1bef  mov     r15, [rsi]
0x1400f1bf2  cmp     qword ptr [rbx+18h], 7
0x1400f1bf7  mov     r14, rbx
0x1400f1bfa  jbe     short loc_1400F1BFF
0x1400f1bfc  mov     r14, [rbx]
0x1400f1bff  call    cs:__imp_MsoGetInstallLcid
0x1400f1c05  or      ecx, 0FFFFFFFFh
0x1400f1c08  mov     r8, r14
0x1400f1c0b  mov     [rsp+78h+var_50], ecx
0x1400f1c0f  mov     r9d, ecx
0x1400f1c12  mov     [rsp+78h+var_58], r15
0x1400f1c17  lea     edx, [rcx+2]
0x1400f1c1a  mov     ecx, eax
0x1400f1c1c  call    cs:__imp_?MsoCompareStringW@@YAHKKPEB_WH0H@Z; MsoCompareStringW(ulong,ulong,wchar_t const *,int,wchar_t const *,int)
0x1400f1c22  cmp     eax, 1
0x1400f1c25  jz      short loc_1400F1C7D
0x1400f1c27  cmp     qword ptr [rbx+18h], 7
0x1400f1c2c  mov     r15, rbx
0x1400f1c2f  jbe     short loc_1400F1C34
0x1400f1c31  mov     r15, [rbx]
0x1400f1c34  cmp     qword ptr [rsi+18h], 7
0x1400f1c39  mov     r14, rsi
0x1400f1c3c  jbe     short loc_1400F1C41
0x1400f1c3e  mov     r14, [rsi]
0x1400f1c41  call    cs:__imp_MsoGetInstallLcid
0x1400f1c47  or      ecx, 0FFFFFFFFh
0x1400f1c4a  mov     r8, r14
0x1400f1c4d  mov     [rsp+78h+var_50], ecx
0x1400f1c51  mov     r9d, ecx
0x1400f1c54  mov     [rsp+78h+var_58], r15
0x1400f1c59  lea     edx, [rcx+2]
0x1400f1c5c  mov     ecx, eax
0x1400f1c5e  call    cs:__imp_?MsoCompareStringW@@YAHKKPEB_WH0H@Z; MsoCompareStringW(ulong,ulong,wchar_t const *,int,wchar_t const *,int)
0x1400f1c64  cmp     eax, 1
0x1400f1c67  jz      short loc_1400F1C8F
0x1400f1c69  cmp     rdi, rsi
0x1400f1c6c  jz      short loc_1400F1C79
0x1400f1c6e  mov     rdx, rsi
0x1400f1c71  mov     rcx, rdi
0x1400f1c74  call    ??$swap@UOCRLanguageGalleryItem@Jot@@$0A@@std@@YAXAEAUOCRLanguageGalleryItem@Jot@@0@Z; std::swap<Jot::OCRLanguageGalleryItem,0>(Jot::OCRLanguageGalleryItem &,Jot::OCRLanguageGalleryItem &)
0x1400f1c79  add     rdi, 28h ; '('
0x1400f1c7d  add     rsi, 28h ; '('
0x1400f1c81  mov     [rsp+78h+var_48], rsi
0x1400f1c86  cmp     rsi, r13
0x1400f1c89  jb      loc_1400F1BE5
0x1400f1c8f  mov     r15, rbx
0x1400f1c92  cmp     rbp, r12
0x1400f1c95  jbe     loc_1400F1D68
0x1400f1c9b  lea     r14, [rbp-28h]
0x1400f1c9f  cmp     qword ptr [rbx+18h], 7
0x1400f1ca4  mov     r13, rbx
0x1400f1ca7  jbe     short loc_1400F1CAC
0x1400f1ca9  mov     r13, [rbx]
0x1400f1cac  cmp     qword ptr [r14+18h], 7
0x1400f1cb1  mov     r12, r14
0x1400f1cb4  jbe     short loc_1400F1CB9
0x1400f1cb6  mov     r12, [r14]
0x1400f1cb9  call    cs:__imp_MsoGetInstallLcid
0x1400f1cbf  or      ecx, 0FFFFFFFFh
0x1400f1cc2  mov     r8, r12
0x1400f1cc5  mov     [rsp+78h+var_50], ecx
0x1400f1cc9  mov     r9d, ecx
0x1400f1ccc  mov     [rsp+78h+var_58], r13
0x1400f1cd1  lea     edx, [rcx+2]
0x1400f1cd4  mov     ecx, eax
0x1400f1cd6  call    cs:__imp_?MsoCompareStringW@@YAHKKPEB_WH0H@Z; MsoCompareStringW(ulong,ulong,wchar_t const *,int,wchar_t const *,int)
0x1400f1cdc  cmp     eax, 1
0x1400f1cdf  jz      short loc_1400F1D37
0x1400f1ce1  cmp     qword ptr [r14+18h], 7
0x1400f1ce6  mov     r13, r14
0x1400f1ce9  jbe     short loc_1400F1CEE
0x1400f1ceb  mov     r13, [r14]
0x1400f1cee  cmp     qword ptr [rbx+18h], 7
0x1400f1cf3  mov     r12, rbx
0x1400f1cf6  jbe     short loc_1400F1CFB
0x1400f1cf8  mov     r12, [rbx]
0x1400f1cfb  call    cs:__imp_MsoGetInstallLcid
0x1400f1d01  or      ecx, 0FFFFFFFFh
0x1400f1d04  mov     r8, r12
0x1400f1d07  mov     [rsp+78h+var_50], ecx
0x1400f1d0b  mov     r9d, ecx
0x1400f1d0e  mov     [rsp+78h+var_58], r13
0x1400f1d13  lea     edx, [rcx+2]
0x1400f1d16  mov     ecx, eax
0x1400f1d18  call    cs:__imp_?MsoCompareStringW@@YAHKKPEB_WH0H@Z; MsoCompareStringW(ulong,ulong,wchar_t const *,int,wchar_t const *,int)
0x1400f1d1e  cmp     eax, 1
0x1400f1d21  jz      short loc_1400F1D55
0x1400f1d23  sub     rbx, 28h ; '('
0x1400f1d27  cmp     rbx, r14
0x1400f1d2a  jz      short loc_1400F1D37
0x1400f1d2c  mov     rdx, r14
0x1400f1d2f  mov     rcx, rbx
0x1400f1d32  call    ??$swap@UOCRLanguageGalleryItem@Jot@@$0A@@std@@YAXAEAUOCRLanguageGalleryItem@Jot@@0@Z; std::swap<Jot::OCRLanguageGalleryItem,0>(Jot::OCRLanguageGalleryItem &,Jot::OCRLanguageGalleryItem &)
0x1400f1d37  mov     r12, [rsp+78h+arg_8]
0x1400f1d3f  sub     rbp, 28h ; '('
0x1400f1d43  sub     r14, 28h ; '('
0x1400f1d47  mov     r15, rbx
0x1400f1d4a  cmp     r12, rbp
0x1400f1d4d  jb      loc_1400F1C9F
0x1400f1d53  jmp     short loc_1400F1D5D
0x1400f1d55  mov     r12, [rsp+78h+arg_8]
0x1400f1d5d  mov     r13, [rsp+78h+arg_10]
0x1400f1d65  cmp     rbp, r12
0x1400f1d68  jnz     short loc_1400F1D8E
0x1400f1d6a  cmp     rsi, r13
0x1400f1d6d  jz      short loc_1400F1DD3
0x1400f1d6f  cmp     rdi, rsi
0x1400f1d72  jz      short loc_1400F1D7F
0x1400f1d74  mov     rdx, rdi
0x1400f1d77  mov     rcx, rbx
0x1400f1d7a  call    ??$swap@UOCRLanguageGalleryItem@Jot@@$0A@@std@@YAXAEAUOCRLanguageGalleryItem@Jot@@0@Z; std::swap<Jot::OCRLanguageGalleryItem,0>(Jot::OCRLanguageGalleryItem &,Jot::OCRLanguageGalleryItem &)
0x1400f1d7f  mov     rax, [rsp+78h+var_48]
0x1400f1d84  add     rdi, 28h ; '('
0x1400f1d88  add     rbx, 28h ; '('
0x1400f1d8c  jmp     short loc_1400F1DBF
0x1400f1d8e  add     rbp, 0FFFFFFFFFFFFFFD8h
0x1400f1d92  cmp     rsi, r13
0x1400f1d95  jnz     short loc_1400F1DB7
0x1400f1d97  sub     rbx, 28h ; '('
0x1400f1d9b  cmp     rbp, rbx
0x1400f1d9e  jz      short loc_1400F1DAB
0x1400f1da0  mov     rdx, rbx
0x1400f1da3  mov     rcx, rbp
0x1400f1da6  call    ??$swap@UOCRLanguageGalleryItem@Jot@@$0A@@std@@YAXAEAUOCRLanguageGalleryItem@Jot@@0@Z; std::swap<Jot::OCRLanguageGalleryItem,0>(Jot::OCRLanguageGalleryItem &,Jot::OCRLanguageGalleryItem &)
0x1400f1dab  sub     rdi, 28h ; '('
0x1400f1daf  mov     r15, rbx
0x1400f1db2  mov     rax, rdi
0x1400f1db5  jmp     short loc_1400F1DC3
0x1400f1db7  mov     r15, [rsp+78h+var_48]
0x1400f1dbc  mov     rax, rbp
0x1400f1dbf  add     rsi, 28h ; '('
0x1400f1dc3  mov     rdx, rax
0x1400f1dc6  mov     rcx, r15
0x1400f1dc9  call    ??$swap@UOCRLanguageGalleryItem@Jot@@$0A@@std@@YAXAEAUOCRLanguageGalleryItem@Jot@@0@Z; std::swap<Jot::OCRLanguageGalleryItem,0>(Jot::OCRLanguageGalleryItem &,Jot::OCRLanguageGalleryItem &)
0x1400f1dce  jmp     loc_1400F1C81
0x1400f1dd3  mov     rax, [rsp+78h+arg_0]
0x1400f1ddb  mov     [rax], rbx
0x1400f1dde  mov     rbx, [rsp+78h+arg_18]
0x1400f1de6  mov     [rax+8], rdi
0x1400f1dea  add     rsp, 40h
0x1400f1dee  pop     r15
0x1400f1df0  pop     r14
0x1400f1df2  pop     r13
0x1400f1df4  pop     r12
0x1400f1df6  pop     rdi
0x1400f1df7  pop     rsi
0x1400f1df8  pop     rbp
0x1400f1df9  retn
```
