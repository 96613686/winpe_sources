# TextLogDecayLogFileBackups

- ea: `0x14000ceac`
- end: `0x14000d2e5`
- name: `TextLogDecayLogFileBackups`
- size: `1081`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, installer_update`

## callers

- `0x14000ebf4`

## callees

- `0x1400070bc`
- `0x140009794`
- `0x14000bb4c`
- `0x14000c354`
- `0x14000ceac`
- `0x140045ede`
- `0x140045eea`
- `0x140045f30`

## import_xrefs

- `msvcrt!wcsrchr` at `0x14000cf71`
- `msvcrt!wcsrchr` at `0x14000cf71`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000cfe5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000d143`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000cfe5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000d143`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000d1e9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000d254`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000d26f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000d293`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000d1e9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000d254`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000d26f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000d293`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000d2aa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000d2aa`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x14000d090`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x14000d090`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x14000d2a2`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x14000d2a2`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x14000cfb8`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x14000cfb8`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x14000d1ca`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x14000d1ca`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x14000d1c1`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x14000d1c1`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x14000d1ff`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x14000d1ff`

## pseudocode

```c
__int64 __fastcall TextLogDecayLogFileBackups(size_t *a1)
{
  unsigned int v2; // edi
  DWORD v3; // ebx
  __int64 FirstFileW; // r12
  _QWORD *v5; // r14
  WCHAR *v6; // rsi
  wchar_t *v7; // rax
  _QWORD *v8; // rax
  __int64 v9; // rax
  unsigned int i; // r15d
  bool v11; // cc
  char *v12; // rax
  char *v13; // r9
  int v14; // edx
  int v15; // r8d
  int v16; // r8d
  unsigned __int16 *v17; // rax
  __int64 j; // r15
  void *v19; // r8
  unsigned int v21; // [rsp+34h] [rbp-AF4h]
  unsigned int v22; // [rsp+44h] [rbp-AE4h]
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+60h] [rbp-AC8h] BYREF
  WCHAR SrcStr[264]; // [rsp+2B0h] [rbp-878h] BYREF
  wchar_t Str[264]; // [rsp+4C0h] [rbp-668h] BYREF
  size_t v26[66]; // [rsp+6D0h] [rbp-458h] BYREF
  wchar_t pszDest[264]; // [rsp+8E0h] [rbp-248h] BYREF

  v2 = 0;
  v3 = 0;
  FirstFileW = -1;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v5 = 0;
  v21 = 0;
  v6 = 0;
  if ( (int)StringCchCopyW((unsigned __int16 *)v26, 0x104u, a1) >= 0 && (unsigned int)pSetupTrimFileTitle(v26) )
  {
    if ( (int)StringCchCopyW(Str, 0x104u, a1) >= 0 )
    {
      v7 = wcsrchr(Str, 0x2Eu);
      if ( v7 )
      {
        *v7 = 0;
        if ( StringCchPrintfW(pszDest, 0x104u, L"%s.????????_??????.%s", Str, v7 + 1) >= 0 )
        {
          FirstFileW = (__int64)FindFirstFileW(pszDest, &FindFileData);
          if ( FirstFileW == -1 )
          {
            v3 = 0;
            goto LABEL_43;
          }
          v8 = HeapAlloc(hHeap, 0, 0x40u);
          v5 = v8;
          if ( !v8 )
          {
LABEL_10:
            v3 = 8;
            goto LABEL_43;
          }
          memset_0(v8, 0, 0x40u);
          while ( (int)StringCchCopyW(SrcStr, 0x104u, v26) >= 0
               && (unsigned int)pSetupConcatenatePaths(SrcStr, FindFileData.cFileName, 260) )
          {
            v9 = -1;
            do
              ++v9;
            while ( SrcStr[v9] );
            v22 = v9 + 1;
            LCMapStringW(0x7Fu, 0x100u, SrcStr, v9 + 1, SrcStr, v9 + 1);
            v6 = 0;
            for ( i = 0; ; ++i )
            {
              v11 = i <= v21;
              if ( i >= v21 )
                break;
              v12 = (char *)v5[i];
              v13 = (char *)((char *)SrcStr - v12);
              do
              {
                v14 = *(unsigned __int16 *)&v13[(_QWORD)v12];
                v15 = *(unsigned __int16 *)v12 - v14;
                if ( v15 )
                  break;
                v12 += 2;
              }
              while ( v14 );
              if ( v15 < 0 )
              {
                if ( v21 >= 8 )
                {
                  v6 = (WCHAR *)v5[7];
                  v16 = 7;
                }
                else
                {
                  v16 = v21;
                }
                memmove_0(&v5[i + 1], &v5[i], 8LL * (v16 - i));
                v5[i] = 0;
                v11 = i <= v21;
                break;
              }
            }
            if ( v11 && i < 8 )
            {
              v17 = (unsigned __int16 *)HeapAlloc(hHeap, 0, 2 * v22);
              v5[i] = v17;
              if ( !v17 )
                goto LABEL_10;
              if ( (int)StringCchCopyW(v17, v22, (size_t *)SrcStr) < 0 )
                break;
              if ( v21 < 8 )
                ++v21;
            }
            else
            {
              v6 = SrcStr;
            }
            if ( v6 )
            {
              if ( v6 != SrcStr || (FindFileData.dwFileAttributes & 1) != 0 )
                SetFileAttributesW(v6, 0x80u);
              DeleteFileW(v6);
              if ( v6 != SrcStr )
              {
                HeapFree(hHeap, 0, v6);
                v6 = 0;
              }
            }
            if ( !FindNextFileW((HANDLE)FirstFileW, &FindFileData) )
              goto LABEL_43;
          }
        }
      }
    }
    v3 = 13;
    goto LABEL_43;
  }
  v3 = 87;
LABEL_43:
  if ( v5 )
  {
    for ( j = 0; j != 8; ++j )
    {
      v19 = (void *)v5[j];
      if ( v19 )
        HeapFree(hHeap, 0, v19);
    }
    HeapFree(hHeap, 0, v5);
  }
  if ( v6 && v6 != SrcStr )
    HeapFree(hHeap, 0, v6);
  if ( FirstFileW != -1 )
    FindClose((HANDLE)FirstFileW);
  SetLastError(v3);
  LOBYTE(v2) = v3 == 0;
  return v2;
}

```

## disassembly

```asm
0x14000ceac  mov     [rsp+arg_8], rbx
0x14000ceb1  mov     [rsp+arg_10], rsi
0x14000ceb6  push    rdi
0x14000ceb7  push    r12
0x14000ceb9  push    r13
0x14000cebb  push    r14
0x14000cebd  push    r15
0x14000cebf  sub     rsp, 0B00h
0x14000cec6  mov     rax, cs:__security_cookie
0x14000cecd  xor     rax, rsp
0x14000ced0  mov     [rsp+0B28h+var_38], rax
0x14000ced8  mov     r15, rcx
0x14000cedb  xor     edi, edi
0x14000cedd  mov     ebx, edi
0x14000cedf  or      r12, 0FFFFFFFFFFFFFFFFh
0x14000cee3  mov     qword ptr [rsp+0B28h+var_AE4+4], r12
0x14000cee8  xor     edx, edx; Val
0x14000ceea  mov     r8d, 250h; Size
0x14000cef0  lea     rcx, [rsp+0B28h+FindFileData]; void *
0x14000cef5  call    memset_0
0x14000cefa  mov     r14d, edi
0x14000cefd  mov     [rsp+0B28h+var_AD8], rdi
0x14000cf02  mov     [rsp+0B28h+var_AF4], edi
0x14000cf06  mov     esi, edi
0x14000cf08  mov     [rsp+0B28h+var_AF0], rdi
0x14000cf0d  mov     r8, r15; unsigned __int16 *
0x14000cf10  mov     r13d, 104h
0x14000cf16  mov     edx, r13d; unsigned __int64
0x14000cf19  lea     rcx, [rsp+0B28h+var_458]; unsigned __int16 *
0x14000cf21  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14000cf26  test    eax, eax
0x14000cf28  js      loc_14000D215
0x14000cf2e  lea     rcx, [rsp+0B28h+var_458]
0x14000cf36  call    pSetupTrimFileTitle
0x14000cf3b  test    eax, eax
0x14000cf3d  jz      loc_14000D215
0x14000cf43  mov     r8, r15; unsigned __int16 *
0x14000cf46  mov     edx, r13d; unsigned __int64
0x14000cf49  lea     rcx, [rsp+0B28h+Str]; unsigned __int16 *
0x14000cf51  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14000cf56  test    eax, eax
0x14000cf58  jns     short loc_14000CF64
0x14000cf5a  mov     ebx, 0Dh
0x14000cf5f  jmp     loc_14000D21A
0x14000cf64  mov     edx, 2Eh ; '.'; Ch
0x14000cf69  lea     rcx, [rsp+0B28h+Str]; Str
0x14000cf71  call    cs:__imp_wcsrchr
0x14000cf77  test    rax, rax
0x14000cf7a  jz      short loc_14000CF5A
0x14000cf7c  mov     [rax], di
0x14000cf7f  add     rax, 2
0x14000cf83  mov     [rsp+0B28h+lpDestStr], rax
0x14000cf88  lea     r9, [rsp+0B28h+Str]
0x14000cf90  lea     r8, aSS; "%s.????????_??????.%s"
0x14000cf97  mov     rdx, r13; cchDest
0x14000cf9a  lea     rcx, [rsp+0B28h+pszDest]; pszDest
0x14000cfa2  call    StringCchPrintfW
0x14000cfa7  test    eax, eax
0x14000cfa9  js      short loc_14000CF5A
0x14000cfab  lea     rdx, [rsp+0B28h+FindFileData]; lpFindFileData
0x14000cfb0  lea     rcx, [rsp+0B28h+pszDest]; lpFileName
0x14000cfb8  call    cs:__imp_FindFirstFileW
0x14000cfbe  mov     r12, rax
0x14000cfc1  mov     qword ptr [rsp+0B28h+var_AE4+4], rax
0x14000cfc6  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14000cfca  jnz     short loc_14000CFD3
0x14000cfcc  mov     ebx, edi
0x14000cfce  jmp     loc_14000D21A
0x14000cfd3  mov     r15d, 40h ; '@'
0x14000cfd9  mov     r8d, r15d; dwBytes
0x14000cfdc  xor     edx, edx; dwFlags
0x14000cfde  mov     rcx, cs:hHeap; hHeap
0x14000cfe5  call    cs:__imp_HeapAlloc
0x14000cfeb  mov     r14, rax
0x14000cfee  mov     [rsp+0B28h+var_AD8], rax
0x14000cff3  test    rax, rax
0x14000cff6  jnz     short loc_14000D002
0x14000cff8  mov     ebx, 8
0x14000cffd  jmp     loc_14000D21A
0x14000d002  mov     r8, r15; Size
0x14000d005  xor     edx, edx; Val
0x14000d007  mov     rcx, r14; void *
0x14000d00a  call    memset_0
0x14000d00f  lea     r8, [rsp+0B28h+var_458]; unsigned __int16 *
0x14000d017  mov     rdx, r13; unsigned __int64
0x14000d01a  lea     rcx, [rsp+0B28h+SrcStr]; unsigned __int16 *
0x14000d022  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14000d027  test    eax, eax
0x14000d029  js      loc_14000CF5A
0x14000d02f  mov     r8d, r13d
0x14000d032  lea     rdx, [rsp+0B28h+FindFileData.cFileName]
0x14000d03a  lea     rcx, [rsp+0B28h+SrcStr]
0x14000d042  call    pSetupConcatenatePaths
0x14000d047  test    eax, eax
0x14000d049  jz      loc_14000CF5A
0x14000d04f  lea     rcx, [rsp+0B28h+SrcStr]
0x14000d057  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000d05b  inc     rax
0x14000d05e  cmp     [rcx+rax*2], di
0x14000d062  jnz     short loc_14000D05B
0x14000d064  inc     eax
0x14000d066  mov     [rsp+0B28h+var_AE4], eax
0x14000d06a  mov     [rsp+0B28h+cchDest], eax; cchDest
0x14000d06e  lea     rcx, [rsp+0B28h+SrcStr]
0x14000d076  mov     [rsp+0B28h+lpDestStr], rcx; lpDestStr
0x14000d07b  mov     r9d, eax; cchSrc
0x14000d07e  lea     r8, [rsp+0B28h+SrcStr]; lpSrcStr
0x14000d086  mov     edx, 100h; dwMapFlags
0x14000d08b  mov     ecx, 7Fh; Locale
0x14000d090  call    cs:__imp_LCMapStringW
0x14000d096  mov     rsi, rdi
0x14000d099  mov     [rsp+0B28h+var_AF0], rdi
0x14000d09e  mov     r15d, edi
0x14000d0a1  mov     [rsp+0B28h+var_AE8], edi
0x14000d0a5  mov     ecx, [rsp+0B28h+var_AF4]
0x14000d0a9  mov     eax, r15d
0x14000d0ac  lea     r13, ds:0[rax*8]
0x14000d0b4  cmp     r15d, ecx
0x14000d0b7  jnb     short loc_14000D129
0x14000d0b9  mov     rax, [r14+r13]
0x14000d0bd  lea     r9, [rsp+0B28h+SrcStr]
0x14000d0c5  sub     r9, rax
0x14000d0c8  movzx   r8d, word ptr [rax]
0x14000d0cc  movzx   edx, word ptr [rax+r9]
0x14000d0d1  sub     r8d, edx
0x14000d0d4  jnz     short loc_14000D0DE
0x14000d0d6  add     rax, 2
0x14000d0da  test    edx, edx
0x14000d0dc  jnz     short loc_14000D0C8
0x14000d0de  lea     r9d, [r15+1]
0x14000d0e2  test    r8d, r8d
0x14000d0e5  jns     loc_14000D186
0x14000d0eb  mov     eax, r15d
0x14000d0ee  lea     rdx, [r14+rax*8]; Src
0x14000d0f2  lea     r9, [r14+r9*8]
0x14000d0f6  cmp     ecx, 8
0x14000d0f9  jnb     short loc_14000D100
0x14000d0fb  mov     r8d, ecx
0x14000d0fe  jmp     short loc_14000D10F
0x14000d100  mov     rsi, [r14+38h]
0x14000d104  mov     [rsp+0B28h+var_AF0], rsi
0x14000d109  mov     r8d, 7
0x14000d10f  sub     r8d, r15d
0x14000d112  shl     r8, 3; Size
0x14000d116  mov     rcx, r9; void *
0x14000d119  call    memmove_0
0x14000d11e  mov     [r14+r13], rdi
0x14000d122  mov     ecx, [rsp+0B28h+var_AF4]
0x14000d126  cmp     r15d, ecx
0x14000d129  ja      short loc_14000D193
0x14000d12b  cmp     r15d, 8
0x14000d12f  jnb     short loc_14000D193
0x14000d131  mov     r15d, [rsp+0B28h+var_AE4]
0x14000d136  lea     r8d, [r15+r15]; dwBytes
0x14000d13a  xor     edx, edx; dwFlags
0x14000d13c  mov     rcx, cs:hHeap; hHeap
0x14000d143  call    cs:__imp_HeapAlloc
0x14000d149  mov     [r14+r13], rax
0x14000d14d  test    rax, rax
0x14000d150  jz      loc_14000CFF8
0x14000d156  mov     edx, r15d; unsigned __int64
0x14000d159  lea     r8, [rsp+0B28h+SrcStr]; unsigned __int16 *
0x14000d161  mov     rcx, rax; unsigned __int16 *
0x14000d164  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14000d169  test    eax, eax
0x14000d16b  js      loc_14000CF5A
0x14000d171  mov     ecx, [rsp+0B28h+var_AF4]
0x14000d175  cmp     ecx, 8
0x14000d178  jnb     short loc_14000D1A0
0x14000d17a  inc     ecx
0x14000d17c  mov     [rsp+0B28h+var_AF4], ecx
0x14000d180  mov     [rsp+0B28h+var_AD0], ecx
0x14000d184  jmp     short loc_14000D1A0
0x14000d186  mov     r15d, r9d
0x14000d189  mov     [rsp+0B28h+var_AE8], r9d
0x14000d18e  jmp     loc_14000D0A9
0x14000d193  lea     rsi, [rsp+0B28h+SrcStr]
0x14000d19b  mov     [rsp+0B28h+var_AF0], rsi
0x14000d1a0  test    rsi, rsi
0x14000d1a3  jz      short loc_14000D1F7
0x14000d1a5  lea     rax, [rsp+0B28h+SrcStr]
0x14000d1ad  cmp     rsi, rax
0x14000d1b0  jnz     short loc_14000D1B9
0x14000d1b2  test    byte ptr [rsp+0B28h+FindFileData.dwFileAttributes], 1
0x14000d1b7  jz      short loc_14000D1C7
0x14000d1b9  mov     edx, 80h; dwFileAttributes
0x14000d1be  mov     rcx, rsi; lpFileName
0x14000d1c1  call    cs:__imp_SetFileAttributesW
0x14000d1c7  mov     rcx, rsi; lpFileName
0x14000d1ca  call    cs:__imp_DeleteFileW
0x14000d1d0  lea     rax, [rsp+0B28h+SrcStr]
0x14000d1d8  cmp     rsi, rax
0x14000d1db  jz      short loc_14000D1F7
0x14000d1dd  mov     r8, rsi; lpMem
0x14000d1e0  xor     edx, edx; dwFlags
0x14000d1e2  mov     rcx, cs:hHeap; hHeap
0x14000d1e9  call    cs:__imp_HeapFree
0x14000d1ef  mov     rsi, rdi
0x14000d1f2  mov     [rsp+0B28h+var_AF0], rdi
0x14000d1f7  lea     rdx, [rsp+0B28h+FindFileData]; lpFindFileData
0x14000d1fc  mov     rcx, r12; hFindFile
0x14000d1ff  call    cs:__imp_FindNextFileW
0x14000d205  test    eax, eax
0x14000d207  mov     r13d, 104h
0x14000d20d  jnz     loc_14000D00F
0x14000d213  jmp     short loc_14000D21E
0x14000d215  mov     ebx, 57h ; 'W'
0x14000d21a  mov     [rsp+0B28h+var_AF8], ebx
0x14000d21e  jmp     short loc_14000D23A
0x14000d220  mov     ebx, 54Fh
0x14000d225  mov     [rsp+0B28h+var_AF8], ebx
0x14000d229  xor     edi, edi
0x14000d22b  mov     r12, qword ptr [rsp+0B28h+var_AE4+4]
0x14000d230  mov     r14, [rsp+0B28h+var_AD8]
0x14000d235  mov     rsi, [rsp+0B28h+var_AF0]
0x14000d23a  test    r14, r14
0x14000d23d  jz      short loc_14000D275
0x14000d23f  mov     r15, rdi
0x14000d242  mov     r8, [r14+r15*8]; lpMem
0x14000d246  test    r8, r8
0x14000d249  jz      short loc_14000D25A
0x14000d24b  xor     edx, edx; dwFlags
0x14000d24d  mov     rcx, cs:hHeap; hHeap
0x14000d254  call    cs:__imp_HeapFree
0x14000d25a  inc     r15
0x14000d25d  cmp     r15, 8
0x14000d261  jnz     short loc_14000D242
0x14000d263  mov     r8, r14; lpMem
0x14000d266  xor     edx, edx; dwFlags
0x14000d268  mov     rcx, cs:hHeap; hHeap
0x14000d26f  call    cs:__imp_HeapFree
0x14000d275  test    rsi, rsi
0x14000d278  jz      short loc_14000D299
0x14000d27a  lea     rax, [rsp+0B28h+SrcStr]
0x14000d282  cmp     rsi, rax
0x14000d285  jz      short loc_14000D299
0x14000d287  mov     r8, rsi; lpMem
0x14000d28a  xor     edx, edx; dwFlags
0x14000d28c  mov     rcx, cs:hHeap; hHeap
0x14000d293  call    cs:__imp_HeapFree
0x14000d299  cmp     r12, 0FFFFFFFFFFFFFFFFh
0x14000d29d  jz      short loc_14000D2A8
0x14000d29f  mov     rcx, r12; hFindFile
0x14000d2a2  call    cs:__imp_FindClose
0x14000d2a8  mov     ecx, ebx; dwErrCode
0x14000d2aa  call    cs:__imp_SetLastError
0x14000d2b0  test    ebx, ebx
0x14000d2b2  setz    dil
0x14000d2b6  mov     eax, edi
0x14000d2b8  mov     rcx, [rsp+0B28h+var_38]
0x14000d2c0  xor     rcx, rsp; StackCookie
0x14000d2c3  call    __security_check_cookie
0x14000d2c8  lea     r11, [rsp+0B28h+var_28]
0x14000d2d0  mov     rbx, [r11+38h]
0x14000d2d4  mov     rsi, [r11+40h]
0x14000d2d8  mov     rsp, r11
0x14000d2db  pop     r15
0x14000d2dd  pop     r14
0x14000d2df  pop     r13
0x14000d2e1  pop     r12
0x14000d2e3  pop     rdi
0x14000d2e4  retn
```
