# __archive_mktempx

- ea: `0x180006f5c`
- end: `0x180007296`
- name: `__archive_mktempx`
- size: `826`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180005574`
- `0x1800f6cd0`
- `0x180100c10`
- `0x180113000`

## callees

- `0x180006f5c`
- `0x1800149c0`
- `0x1800ed6c0`
- `0x1800ef3f8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180006fd1`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180007044`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000706a`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180006fd1`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180007044`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000706a`
- `api-ms-win-crt-private-l1-1-0!_o__open_osfhandle` at `0x180007223`
- `api-ms-win-crt-private-l1-1-0!_o__open_osfhandle` at `0x180007223`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18000728f`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18000728f`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000700d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000718b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000725e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180007275`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000700d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000718b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000725e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180007275`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180006fc3`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180006fc3`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800070c2`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800070c2`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180007102`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180007102`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180007255`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180007255`
- `bcrypt!BCryptGenRandom` at `0x180007133`
- `bcrypt!BCryptGenRandom` at `0x180007133`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180007017`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180007058`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180007017`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180007058`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006fab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007024`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007201`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007231`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006fab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007024`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007201`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007231`
- `api-ms-win-core-file-l1-2-0!CreateFile2` at `0x1800071f2`
- `api-ms-win-core-file-l1-2-0!CreateFile2` at `0x1800071f2`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x180006f9f`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x180006fe7`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x180006f9f`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x180006fe7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007241`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007241`

## pseudocode

```c
__int64 __fastcall _archive_mktempx(__int64 a1, const wchar_t *a2)
{
  const WCHAR *v2; // r15
  unsigned int v3; // r13d
  WCHAR *v4; // r14
  DWORD TempPathW; // eax
  DWORD v6; // edi
  DWORD v7; // eax
  WCHAR *v8; // rax
  WCHAR *v9; // rbx
  __int64 v10; // r8
  DWORD FileAttributesW; // eax
  const WCHAR *v12; // rax
  const WCHAR *v13; // rdi
  UCHAR *v14; // rbx
  wchar_t *v15; // rax
  __int16 i; // ax
  UCHAR *j; // r8
  __int64 v18; // rdx
  int v19; // eax
  int v20; // ecx
  __int64 File2; // rax
  void *v22; // r12
  DWORD LastError; // eax
  LPCWSTR lpFileName; // [rsp+30h] [rbp-48h] BYREF
  __int64 v26; // [rsp+38h] [rbp-40h]
  __int64 v27; // [rsp+40h] [rbp-38h]
  _OWORD v28[3]; // [rsp+48h] [rbp-30h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+C0h] [rbp+48h] BYREF

  phAlgorithm = 0;
  v2 = a2;
  lpFileName = 0;
  v3 = -1;
  v26 = 0;
  v4 = 0;
  v27 = 0;
  if ( a2 )
  {
    v15 = wcschr(a2, 0x58u);
    v14 = (UCHAR *)v15;
    if ( !v15 )
      goto LABEL_39;
    v13 = v15;
    for ( i = *v15; i == 88; i = *v13 )
      ++v13;
    if ( i )
LABEL_39:
      abort();
LABEL_21:
    if ( BCryptOpenAlgorithmProvider(&phAlgorithm, L"RNG", 0, 0) >= 0 )
    {
      while ( 1 )
      {
        memset(v28, 0, 32);
        if ( BCryptGenRandom(phAlgorithm, v14, 2 * (((char *)v13 - (char *)v14) >> 1), 0) < 0 )
          break;
        for ( j = v14; j < (UCHAR *)v13; j += 2 )
        {
          v18 = (*(unsigned __int16 *)j * (unsigned __int128)0x842108421084211uLL) >> 64;
          *(_WORD *)j = a0123456789abcd_1[*(unsigned __int16 *)j
                                        - 62 * ((v18 + (((unsigned __int64)*(unsigned __int16 *)j - v18) >> 1)) >> 5)];
        }
        free(v4);
        v4 = (WCHAR *)_la_win_permissive_name_w(v2);
        if ( !v4 )
          goto LABEL_11;
        if ( v2 == lpFileName )
        {
          v19 = 256;
          v20 = 0x4000000;
        }
        else
        {
          v19 = 128;
          v20 = 0;
        }
        *(_QWORD *)((char *)v28 + 4) = __PAIR64__(v20, v19);
        LODWORD(v28[0]) = 32;
        memset((char *)v28 + 12, 0, 20);
        File2 = CreateFile2(v4, 3221291008LL, 0, 1, v28);
        v22 = (void *)File2;
        if ( File2 != -1 )
        {
          v3 = _o__open_osfhandle(File2, 32770);
          if ( v3 == -1 )
          {
            LastError = GetLastError();
            _la_dosmaperr(LastError);
            CloseHandle(v22);
          }
          goto LABEL_34;
        }
        if ( GetLastError() != 80 )
          goto LABEL_3;
      }
    }
    goto LABEL_3;
  }
  TempPathW = GetTempPathW(0, 0);
  v6 = TempPathW;
  if ( !TempPathW )
  {
LABEL_3:
    v7 = GetLastError();
    _la_dosmaperr(v7);
    goto LABEL_34;
  }
  v8 = (WCHAR *)malloc(2LL * TempPathW);
  v9 = v8;
  if ( !v8 )
  {
    *(_DWORD *)_o__errno() = 12;
    goto LABEL_34;
  }
  GetTempPathW(v6, v8);
  v10 = -1;
  v26 = 0;
  do
    ++v10;
  while ( v9[v10] );
  archive_wstrncat(&lpFileName, v9, v10);
  free(v9);
  FileAttributesW = GetFileAttributesW(lpFileName);
  if ( FileAttributesW == -1 )
  {
    if ( GetLastError() != 2 )
      goto LABEL_3;
    v12 = (const WCHAR *)_la_win_permissive_name_w(lpFileName);
    v4 = (WCHAR *)v12;
    if ( !v12 )
    {
LABEL_11:
      *(_DWORD *)_o__errno() = 22;
      goto LABEL_34;
    }
    FileAttributesW = GetFileAttributesW(v12);
    if ( FileAttributesW == -1 )
      goto LABEL_3;
  }
  if ( (FileAttributesW & 0x10) != 0 )
  {
    archive_wstrncat(&lpFileName, L"libarchive_", 0x1000000);
    archive_wstrncat(&lpFileName, L"XXXXXXXXXX", 0x1000000);
    v2 = lpFileName;
    v13 = &lpFileName[v26];
    v14 = (UCHAR *)(v13 - 10);
    goto LABEL_21;
  }
  *(_DWORD *)_o__errno() = 20;
LABEL_34:
  if ( phAlgorithm )
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  free(v4);
  if ( v2 == lpFileName )
  {
    v26 = 0;
    v27 = 0;
    free((void *)lpFileName);
  }
  return v3;
}

```

## disassembly

```asm
0x180006f5c  mov     [rsp-40h+phAlgorithm], rcx
0x180006f61  push    rbp
0x180006f62  push    rbx
0x180006f63  push    rsi
0x180006f64  push    rdi
0x180006f65  push    r12
0x180006f67  push    r13
0x180006f69  push    r14
0x180006f6b  push    r15
0x180006f6d  mov     rbp, rsp
0x180006f70  sub     rsp, 78h
0x180006f74  xor     r12d, r12d
0x180006f77  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180006f7b  mov     [rbp+phAlgorithm], r12
0x180006f7f  mov     r15, rdx
0x180006f82  mov     [rbp+lpFileName], r12
0x180006f86  mov     r13d, esi
0x180006f89  mov     [rbp+var_40], r12
0x180006f8d  mov     r14d, r12d
0x180006f90  mov     [rbp+var_38], r12
0x180006f94  test    rdx, rdx
0x180006f97  jnz     loc_1800070B8
0x180006f9d  xor     ecx, ecx; nBufferLength
0x180006f9f  call    cs:__imp_GetTempPathW
0x180006fa5  mov     edi, eax
0x180006fa7  test    eax, eax
0x180006fa9  jnz     short loc_180006FBD
0x180006fab  call    cs:__imp_GetLastError
0x180006fb1  mov     ecx, eax
0x180006fb3  call    __la_dosmaperr
0x180006fb8  jmp     loc_18000724A
0x180006fbd  mov     rcx, rdi
0x180006fc0  add     rcx, rcx; Size
0x180006fc3  call    cs:__imp_malloc
0x180006fc9  mov     rbx, rax
0x180006fcc  test    rax, rax
0x180006fcf  jnz     short loc_180006FE2
0x180006fd1  call    cs:__imp__o__errno
0x180006fd7  mov     dword ptr [rax], 0Ch
0x180006fdd  jmp     loc_18000724A
0x180006fe2  mov     rdx, rbx; lpBuffer
0x180006fe5  mov     ecx, edi; nBufferLength
0x180006fe7  call    cs:__imp_GetTempPathW
0x180006fed  mov     r8, rsi
0x180006ff0  mov     [rbp+var_40], r12
0x180006ff4  inc     r8
0x180006ff7  cmp     [rbx+r8*2], r12w
0x180006ffc  jnz     short loc_180006FF4
0x180006ffe  mov     rdx, rbx
0x180007001  lea     rcx, [rbp+lpFileName]
0x180007005  call    archive_wstrncat
0x18000700a  mov     rcx, rbx; Block
0x18000700d  call    cs:__imp_free
0x180007013  mov     rcx, [rbp+lpFileName]; lpFileName
0x180007017  call    cs:__imp_GetFileAttributesW
0x18000701d  or      ebx, 0FFFFFFFFh
0x180007020  cmp     eax, ebx
0x180007022  jnz     short loc_180007066
0x180007024  call    cs:__imp_GetLastError
0x18000702a  cmp     eax, 2
0x18000702d  jnz     loc_180006FAB
0x180007033  mov     rcx, [rbp+lpFileName]; lpFileName
0x180007037  call    __la_win_permissive_name_w
0x18000703c  mov     r14, rax
0x18000703f  test    rax, rax
0x180007042  jnz     short loc_180007055
0x180007044  call    cs:__imp__o__errno
0x18000704a  mov     dword ptr [rax], 16h
0x180007050  jmp     loc_18000724A
0x180007055  mov     rcx, rax; lpFileName
0x180007058  call    cs:__imp_GetFileAttributesW
0x18000705e  cmp     eax, ebx
0x180007060  jz      loc_180006FAB
0x180007066  test    al, 10h
0x180007068  jnz     short loc_18000707B
0x18000706a  call    cs:__imp__o__errno
0x180007070  mov     dword ptr [rax], 14h
0x180007076  jmp     loc_18000724A
0x18000707b  mov     ebx, 1000000h
0x180007080  lea     rdx, aLibarchive_1; "libarchive_"
0x180007087  mov     r8d, ebx
0x18000708a  lea     rcx, [rbp+lpFileName]
0x18000708e  call    archive_wstrncat
0x180007093  mov     r8d, ebx
0x180007096  lea     rdx, aXxxxxxxxxx; "XXXXXXXXXX"
0x18000709d  lea     rcx, [rbp+lpFileName]
0x1800070a1  call    archive_wstrncat
0x1800070a6  mov     rax, [rbp+var_40]
0x1800070aa  mov     r15, [rbp+lpFileName]
0x1800070ae  lea     rdi, [r15+rax*2]
0x1800070b2  lea     rbx, [rdi-14h]
0x1800070b6  jmp     short loc_1800070F1
0x1800070b8  mov     esi, 58h ; 'X'
0x1800070bd  mov     rcx, r15; Str
0x1800070c0  mov     edx, esi; Ch
0x1800070c2  call    cs:__imp_wcschr
0x1800070c8  mov     rbx, rax
0x1800070cb  test    rax, rax
0x1800070ce  jz      loc_18000728F
0x1800070d4  mov     rdi, rax
0x1800070d7  movzx   eax, word ptr [rax]
0x1800070da  jmp     short loc_1800070E3
0x1800070dc  add     rdi, 2
0x1800070e0  movzx   eax, word ptr [rdi]
0x1800070e3  cmp     ax, si
0x1800070e6  jz      short loc_1800070DC
0x1800070e8  test    ax, ax
0x1800070eb  jnz     loc_18000728F
0x1800070f1  xor     r9d, r9d; dwFlags
0x1800070f4  lea     rdx, pszAlgId; "RNG"
0x1800070fb  xor     r8d, r8d; pszImplementation
0x1800070fe  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x180007102  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180007108  test    eax, eax
0x18000710a  js      loc_180006FAB
0x180007110  mov     rsi, rdi
0x180007113  sub     rsi, rbx
0x180007116  sar     rsi, 1
0x180007119  add     esi, esi
0x18000711b  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x18000711f  xorps   xmm0, xmm0
0x180007122  xor     r9d, r9d; dwFlags
0x180007125  mov     r8d, esi; cbBuffer
0x180007128  mov     rdx, rbx; pbBuffer
0x18000712b  movups  [rbp+var_30], xmm0
0x18000712f  movups  [rbp+var_20], xmm0
0x180007133  call    cs:__imp_BCryptGenRandom
0x180007139  test    eax, eax
0x18000713b  js      loc_180006FAB
0x180007141  mov     r8, rbx
0x180007144  cmp     rbx, rdi
0x180007147  jnb     short loc_180007188
0x180007149  movzx   ecx, word ptr [r8]
0x18000714d  mov     rax, 842108421084211h
0x180007157  mul     rcx
0x18000715a  mov     eax, ecx
0x18000715c  sub     rax, rdx
0x18000715f  shr     rax, 1
0x180007162  add     rax, rdx
0x180007165  shr     rax, 5
0x180007169  imul    rax, 3Eh ; '>'
0x18000716d  sub     rcx, rax
0x180007170  lea     rax, a0123456789abcd_1; "0123456789ABCDEFGHIJKLMNOPQRSTUVWXYZabc"...
0x180007177  movzx   eax, word ptr [rax+rcx*2]
0x18000717b  mov     [r8], ax
0x18000717f  add     r8, 2
0x180007183  cmp     r8, rdi
0x180007186  jb      short loc_180007149
0x180007188  mov     rcx, r14; Block
0x18000718b  call    cs:__imp_free
0x180007191  mov     rcx, r15; lpFileName
0x180007194  call    __la_win_permissive_name_w
0x180007199  mov     r14, rax
0x18000719c  test    rax, rax
0x18000719f  jz      loc_180007044
0x1800071a5  cmp     r15, [rbp+lpFileName]
0x1800071a9  jnz     short loc_1800071B7
0x1800071ab  mov     eax, 100h
0x1800071b0  mov     ecx, 4000000h
0x1800071b5  jmp     short loc_1800071BF
0x1800071b7  mov     eax, 80h
0x1800071bc  mov     ecx, r12d
0x1800071bf  mov     dword ptr [rbp+var_30+4], eax
0x1800071c2  xorps   xmm0, xmm0
0x1800071c5  lea     rax, [rbp+var_30]
0x1800071c9  mov     dword ptr [rbp+var_30+8], ecx
0x1800071cc  mov     r9d, 1
0x1800071d2  mov     [rsp+78h+var_58], rax
0x1800071d7  xor     r8d, r8d
0x1800071da  mov     dword ptr [rbp+var_20+0Ch], r12d
0x1800071de  mov     edx, 0C0010000h
0x1800071e3  mov     dword ptr [rbp+var_30], 20h ; ' '
0x1800071ea  mov     rcx, r14
0x1800071ed  movdqu  [rbp+var_30+0Ch], xmm0
0x1800071f2  call    cs:__imp_CreateFile2
0x1800071f8  mov     r12, rax
0x1800071fb  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800071ff  jnz     short loc_18000721B
0x180007201  call    cs:__imp_GetLastError
0x180007207  mov     r12d, 0
0x18000720d  cmp     eax, 50h ; 'P'
0x180007210  jz      loc_18000711B
0x180007216  jmp     loc_180006FAB
0x18000721b  mov     edx, 8002h
0x180007220  mov     rcx, r12
0x180007223  call    cs:__imp__o__open_osfhandle
0x180007229  mov     r13d, eax
0x18000722c  cmp     eax, 0FFFFFFFFh
0x18000722f  jnz     short loc_180007247
0x180007231  call    cs:__imp_GetLastError
0x180007237  mov     ecx, eax
0x180007239  call    __la_dosmaperr
0x18000723e  mov     rcx, r12; hObject
0x180007241  call    cs:__imp_CloseHandle
0x180007247  xor     r12d, r12d
0x18000724a  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x18000724e  test    rcx, rcx
0x180007251  jz      short loc_18000725B
0x180007253  xor     edx, edx; dwFlags
0x180007255  call    cs:__imp_BCryptCloseAlgorithmProvider
0x18000725b  mov     rcx, r14; Block
0x18000725e  call    cs:__imp_free
0x180007264  mov     rcx, [rbp+lpFileName]; Block
0x180007268  cmp     r15, rcx
0x18000726b  jnz     short loc_18000727B
0x18000726d  mov     [rbp+var_40], r12
0x180007271  mov     [rbp+var_38], r12
0x180007275  call    cs:__imp_free
0x18000727b  mov     eax, r13d
0x18000727e  add     rsp, 78h
0x180007282  pop     r15
0x180007284  pop     r14
0x180007286  pop     r13
0x180007288  pop     r12
0x18000728a  pop     rdi
0x18000728b  pop     rsi
0x18000728c  pop     rbx
0x18000728d  pop     rbp
0x18000728e  retn
0x18000728f  call    cs:__imp_abort
```
