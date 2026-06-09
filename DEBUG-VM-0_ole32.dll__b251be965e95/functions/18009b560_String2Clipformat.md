# String2Clipformat

- ea: `0x18009b560`
- end: `0x18009b8a2`
- name: `String2Clipformat`
- size: `834`
- prototype: `unsigned __int16 __fastcall(wchar_t *sz)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18009adc0`

## callees

- `0x180009374`
- `0x18009b560`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18009b5c2`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18009b5f2`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18009b61f`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18009b64d`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18009b67c`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18009b6ab`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18009b6da`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18009b709`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18009b738`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18009b767`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18009b796`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18009b7c5`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18009b7f4`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18009b823`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18009b84f`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18009b87b`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18009b5c2`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18009b5f2`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18009b61f`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18009b64d`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18009b67c`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18009b6ab`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18009b6da`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18009b709`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18009b738`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18009b767`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18009b796`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18009b7c5`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18009b7f4`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18009b823`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18009b84f`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18009b87b`
- `USER32!RegisterClipboardFormatW` at `0x18009b88f`
- `USER32!RegisterClipboardFormatW` at `0x18009b88f`

## pseudocode

```c
UINT __fastcall String2Clipformat(wchar_t *sz)
{
  _DWORD *v2; // rcx
  int v3; // ecx

  if ( safe_lstrlenW(sz) < 3 )
    return RegisterClipboardFormatW(sz);
  v3 = *v2 - 4587587;
  if ( !v3 )
    v3 = sz[2] - 95;
  if ( v3 )
    return RegisterClipboardFormatW(sz);
  if ( CompareStringW(0x7Fu, 1u, sz, -1, L"CF_TEXT", -1) == 2 )
    return 1;
  if ( CompareStringW(0x7Fu, 1u, sz, -1, L"CF_BITMAP", -1) == 2 )
    return 2;
  if ( CompareStringW(0x7Fu, 1u, sz, -1, L"CF_METAFILEPICT", -1) == 2 )
    return 3;
  if ( CompareStringW(0x7Fu, 1u, sz, -1, L"CF_SYLK", -1) == 2 )
    return 4;
  if ( CompareStringW(0x7Fu, 1u, sz, -1, L"CF_DIF", -1) == 2 )
    return 5;
  if ( CompareStringW(0x7Fu, 1u, sz, -1, L"CF_TIFF", -1) == 2 )
    return 6;
  if ( CompareStringW(0x7Fu, 1u, sz, -1, L"CF_OEMTEXT", -1) == 2 )
    return 7;
  if ( CompareStringW(0x7Fu, 1u, sz, -1, L"CF_DIB", -1) == 2 )
    return 8;
  if ( CompareStringW(0x7Fu, 1u, sz, -1, L"CF_PALETTE", -1) == 2 )
    return 9;
  if ( CompareStringW(0x7Fu, 1u, sz, -1, L"CF_PENDATA", -1) == 2 )
    return 10;
  if ( CompareStringW(0x7Fu, 1u, sz, -1, L"CF_RIFF", -1) == 2 )
    return 11;
  if ( CompareStringW(0x7Fu, 1u, sz, -1, L"CF_WAVE", -1) == 2 )
    return 12;
  if ( CompareStringW(0x7Fu, 1u, sz, -1, L"CF_OWNERDISPLAY", -1) == 2 )
    return 128;
  if ( CompareStringW(0x7Fu, 1u, sz, -1, L"CF_DSPTEXT", -1) == 2 )
    return 129;
  if ( CompareStringW(0x7Fu, 1u, sz, -1, L"CF_DSPBITMAP", -1) == 2 )
    return 130;
  if ( CompareStringW(0x7Fu, 1u, sz, -1, L"CF_DSPMETAFILEPICT", -1) != 2 )
    return RegisterClipboardFormatW(sz);
  else
    return 131;
}

```

## disassembly

```asm
0x18009b560  push    rbx
0x18009b562  push    rbp
0x18009b563  push    rsi
0x18009b564  push    rdi
0x18009b565  push    r14
0x18009b567  push    r15
0x18009b569  sub     rsp, 38h
0x18009b56d  mov     rbx, sz
0x18009b570  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x18009b575  mov     r15d, 3
0x18009b57b  cmp     eax, r15d
0x18009b57e  jl      loc_18009B88C
0x18009b584  mov     ecx, [sz]
0x18009b586  sub     ecx, 460043h
0x18009b58c  jnz     short loc_18009B595
0x18009b58e  movzx   ecx, word ptr [rbx+4]
0x18009b592  sub     ecx, 5Fh ; '_'
0x18009b595  test    ecx, ecx
0x18009b597  jnz     loc_18009B88C
0x18009b59d  lea     esi, [sz+1]
0x18009b5a0  or      edi, 0FFFFFFFFh
0x18009b5a3  lea     r14d, [sz+7Fh]
0x18009b5a7  mov     [rsp+68h+cchCount2], edi; cchCount2
0x18009b5ab  lea     rax, aCfText; "CF_TEXT"
0x18009b5b2  mov     r9d, edi; cchCount1
0x18009b5b5  mov     edx, esi; dwCmpFlags
0x18009b5b7  mov     [rsp+68h+lpString2], rax; lpString2
0x18009b5bc  mov     ecx, r14d; Locale
0x18009b5bf  mov     r8, rbx; lpString1
0x18009b5c2  call    cs:__imp_CompareStringW
0x18009b5c8  lea     ebp, [rdi+3]
0x18009b5cb  cmp     eax, ebp
0x18009b5cd  jnz     short loc_18009B5D7
0x18009b5cf  movzx   eax, si
0x18009b5d2  jmp     loc_18009B895
0x18009b5d7  lea     sz, aCfBitmap; "CF_BITMAP"
0x18009b5de  mov     [rsp+68h+cchCount2], edi; cchCount2
0x18009b5e2  mov     [rsp+68h+lpString2], sz; lpString2
0x18009b5e7  mov     r9d, edi; cchCount1
0x18009b5ea  mov     ecx, r14d; Locale
0x18009b5ed  mov     r8, rbx; lpString1
0x18009b5f0  mov     edx, esi; dwCmpFlags
0x18009b5f2  call    cs:__imp_CompareStringW
0x18009b5f8  cmp     eax, ebp
0x18009b5fa  jnz     short loc_18009B604
0x18009b5fc  movzx   eax, bp
0x18009b5ff  jmp     loc_18009B895
0x18009b604  lea     sz, aCfMetafilepict; "CF_METAFILEPICT"
0x18009b60b  mov     [rsp+68h+cchCount2], edi; cchCount2
0x18009b60f  mov     [rsp+68h+lpString2], sz; lpString2
0x18009b614  mov     r9d, edi; cchCount1
0x18009b617  mov     ecx, r14d; Locale
0x18009b61a  mov     r8, rbx; lpString1
0x18009b61d  mov     edx, esi; dwCmpFlags
0x18009b61f  call    cs:__imp_CompareStringW
0x18009b625  cmp     eax, ebp
0x18009b627  jnz     short loc_18009B632
0x18009b629  movzx   eax, r15w
0x18009b62d  jmp     loc_18009B895
0x18009b632  lea     rax, aCfSylk; "CF_SYLK"
0x18009b639  mov     [rsp+68h+cchCount2], edi; cchCount2
0x18009b63d  mov     r9d, edi; cchCount1
0x18009b640  mov     [rsp+68h+lpString2], rax; lpString2
0x18009b645  mov     r8, rbx; lpString1
0x18009b648  mov     edx, esi; dwCmpFlags
0x18009b64a  mov     ecx, r14d; Locale
0x18009b64d  call    cs:__imp_CompareStringW
0x18009b653  cmp     eax, ebp
0x18009b655  jnz     short loc_18009B661
0x18009b657  mov     eax, 4
0x18009b65c  jmp     loc_18009B895
0x18009b661  lea     rax, aCfDif; "CF_DIF"
0x18009b668  mov     [rsp+68h+cchCount2], edi; cchCount2
0x18009b66c  mov     r9d, edi; cchCount1
0x18009b66f  mov     [rsp+68h+lpString2], rax; lpString2
0x18009b674  mov     r8, rbx; lpString1
0x18009b677  mov     edx, esi; dwCmpFlags
0x18009b679  mov     ecx, r14d; Locale
0x18009b67c  call    cs:__imp_CompareStringW
0x18009b682  cmp     eax, ebp
0x18009b684  jnz     short loc_18009B690
0x18009b686  mov     eax, 5
0x18009b68b  jmp     loc_18009B895
0x18009b690  lea     rax, aCfTiff; "CF_TIFF"
0x18009b697  mov     [rsp+68h+cchCount2], edi; cchCount2
0x18009b69b  mov     r9d, edi; cchCount1
0x18009b69e  mov     [rsp+68h+lpString2], rax; lpString2
0x18009b6a3  mov     r8, rbx; lpString1
0x18009b6a6  mov     edx, esi; dwCmpFlags
0x18009b6a8  mov     ecx, r14d; Locale
0x18009b6ab  call    cs:__imp_CompareStringW
0x18009b6b1  cmp     eax, ebp
0x18009b6b3  jnz     short loc_18009B6BF
0x18009b6b5  mov     eax, 6
0x18009b6ba  jmp     loc_18009B895
0x18009b6bf  lea     rax, aCfOemtext; "CF_OEMTEXT"
0x18009b6c6  mov     [rsp+68h+cchCount2], edi; cchCount2
0x18009b6ca  mov     r9d, edi; cchCount1
0x18009b6cd  mov     [rsp+68h+lpString2], rax; lpString2
0x18009b6d2  mov     r8, rbx; lpString1
0x18009b6d5  mov     edx, esi; dwCmpFlags
0x18009b6d7  mov     ecx, r14d; Locale
0x18009b6da  call    cs:__imp_CompareStringW
0x18009b6e0  cmp     eax, ebp
0x18009b6e2  jnz     short loc_18009B6EE
0x18009b6e4  mov     eax, 7
0x18009b6e9  jmp     loc_18009B895
0x18009b6ee  lea     rax, aCfDib; "CF_DIB"
0x18009b6f5  mov     [rsp+68h+cchCount2], edi; cchCount2
0x18009b6f9  mov     r9d, edi; cchCount1
0x18009b6fc  mov     [rsp+68h+lpString2], rax; lpString2
0x18009b701  mov     r8, rbx; lpString1
0x18009b704  mov     edx, esi; dwCmpFlags
0x18009b706  mov     ecx, r14d; Locale
0x18009b709  call    cs:__imp_CompareStringW
0x18009b70f  cmp     eax, ebp
0x18009b711  jnz     short loc_18009B71D
0x18009b713  mov     eax, 8
0x18009b718  jmp     loc_18009B895
0x18009b71d  lea     rax, aCfPalette; "CF_PALETTE"
0x18009b724  mov     [rsp+68h+cchCount2], edi; cchCount2
0x18009b728  mov     r9d, edi; cchCount1
0x18009b72b  mov     [rsp+68h+lpString2], rax; lpString2
0x18009b730  mov     r8, rbx; lpString1
0x18009b733  mov     edx, esi; dwCmpFlags
0x18009b735  mov     ecx, r14d; Locale
0x18009b738  call    cs:__imp_CompareStringW
0x18009b73e  cmp     eax, ebp
0x18009b740  jnz     short loc_18009B74C
0x18009b742  mov     eax, 9
0x18009b747  jmp     loc_18009B895
0x18009b74c  lea     rax, aCfPendata; "CF_PENDATA"
0x18009b753  mov     [rsp+68h+cchCount2], edi; cchCount2
0x18009b757  mov     r9d, edi; cchCount1
0x18009b75a  mov     [rsp+68h+lpString2], rax; lpString2
0x18009b75f  mov     r8, rbx; lpString1
0x18009b762  mov     edx, esi; dwCmpFlags
0x18009b764  mov     ecx, r14d; Locale
0x18009b767  call    cs:__imp_CompareStringW
0x18009b76d  cmp     eax, ebp
0x18009b76f  jnz     short loc_18009B77B
0x18009b771  mov     eax, 0Ah
0x18009b776  jmp     loc_18009B895
0x18009b77b  lea     rax, aCfRiff; "CF_RIFF"
0x18009b782  mov     [rsp+68h+cchCount2], edi; cchCount2
0x18009b786  mov     r9d, edi; cchCount1
0x18009b789  mov     [rsp+68h+lpString2], rax; lpString2
0x18009b78e  mov     r8, rbx; lpString1
0x18009b791  mov     edx, esi; dwCmpFlags
0x18009b793  mov     ecx, r14d; Locale
0x18009b796  call    cs:__imp_CompareStringW
0x18009b79c  cmp     eax, ebp
0x18009b79e  jnz     short loc_18009B7AA
0x18009b7a0  mov     eax, 0Bh
0x18009b7a5  jmp     loc_18009B895
0x18009b7aa  lea     rax, aCfWave; "CF_WAVE"
0x18009b7b1  mov     [rsp+68h+cchCount2], edi; cchCount2
0x18009b7b5  mov     r9d, edi; cchCount1
0x18009b7b8  mov     [rsp+68h+lpString2], rax; lpString2
0x18009b7bd  mov     r8, rbx; lpString1
0x18009b7c0  mov     edx, esi; dwCmpFlags
0x18009b7c2  mov     ecx, r14d; Locale
0x18009b7c5  call    cs:__imp_CompareStringW
0x18009b7cb  cmp     eax, ebp
0x18009b7cd  jnz     short loc_18009B7D9
0x18009b7cf  mov     eax, 0Ch
0x18009b7d4  jmp     loc_18009B895
0x18009b7d9  lea     rax, aCfOwnerdisplay; "CF_OWNERDISPLAY"
0x18009b7e0  mov     [rsp+68h+cchCount2], edi; cchCount2
0x18009b7e4  mov     r9d, edi; cchCount1
0x18009b7e7  mov     [rsp+68h+lpString2], rax; lpString2
0x18009b7ec  mov     r8, rbx; lpString1
0x18009b7ef  mov     edx, esi; dwCmpFlags
0x18009b7f1  mov     ecx, r14d; Locale
0x18009b7f4  call    cs:__imp_CompareStringW
0x18009b7fa  cmp     eax, ebp
0x18009b7fc  jnz     short loc_18009B808
0x18009b7fe  mov     eax, 80h
0x18009b803  jmp     loc_18009B895
0x18009b808  lea     rax, aCfDsptext; "CF_DSPTEXT"
0x18009b80f  mov     [rsp+68h+cchCount2], edi; cchCount2
0x18009b813  mov     r9d, edi; cchCount1
0x18009b816  mov     [rsp+68h+lpString2], rax; lpString2
0x18009b81b  mov     r8, rbx; lpString1
0x18009b81e  mov     edx, esi; dwCmpFlags
0x18009b820  mov     ecx, r14d; Locale
0x18009b823  call    cs:__imp_CompareStringW
0x18009b829  cmp     eax, ebp
0x18009b82b  jnz     short loc_18009B834
0x18009b82d  mov     eax, 81h
0x18009b832  jmp     short loc_18009B895
0x18009b834  lea     rax, aCfDspbitmap; "CF_DSPBITMAP"
0x18009b83b  mov     [rsp+68h+cchCount2], edi; cchCount2
0x18009b83f  mov     r9d, edi; cchCount1
0x18009b842  mov     [rsp+68h+lpString2], rax; lpString2
0x18009b847  mov     r8, rbx; lpString1
0x18009b84a  mov     edx, esi; dwCmpFlags
0x18009b84c  mov     ecx, r14d; Locale
0x18009b84f  call    cs:__imp_CompareStringW
0x18009b855  cmp     eax, ebp
0x18009b857  jnz     short loc_18009B860
0x18009b859  mov     eax, 82h
0x18009b85e  jmp     short loc_18009B895
0x18009b860  lea     rax, aCfDspmetafilep; "CF_DSPMETAFILEPICT"
0x18009b867  mov     [rsp+68h+cchCount2], edi; cchCount2
0x18009b86b  mov     r9d, edi; cchCount1
0x18009b86e  mov     [rsp+68h+lpString2], rax; lpString2
0x18009b873  mov     r8, rbx; lpString1
0x18009b876  mov     edx, esi; dwCmpFlags
0x18009b878  mov     ecx, r14d; Locale
0x18009b87b  call    cs:__imp_CompareStringW
0x18009b881  cmp     eax, ebp
0x18009b883  jnz     short loc_18009B88C
0x18009b885  mov     eax, 83h
0x18009b88a  jmp     short loc_18009B895
0x18009b88c  mov     sz, rbx; lpszFormat
0x18009b88f  call    cs:__imp_RegisterClipboardFormatW
0x18009b895  add     rsp, 38h
0x18009b899  pop     r15
0x18009b89b  pop     r14
0x18009b89d  pop     rdi
0x18009b89e  pop     rsi
0x18009b89f  pop     rbp
0x18009b8a0  pop     rbx
0x18009b8a1  retn
```
