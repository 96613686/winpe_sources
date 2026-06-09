# FBuildTempPathW

- ea: `0x18000af00`
- end: `0x18000b1c9`
- name: `FBuildTempPathW`
- size: `713`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 *, unsigned __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x18000ae20`

## callees

- `0x180004640`
- `0x18000470c`
- `0x1800095a8`
- `0x18000a038`
- `0x18000af00`
- `0x180011930`
- `0x180012f8e`
- `0x180012fc0`
- `0x180014010`

## import_xrefs

- `SHLWAPI!PathFindExtensionW` at `0x18000b01f`
- `SHLWAPI!PathFindExtensionW` at `0x18000b01f`
- `SHLWAPI!PathFindFileNameW` at `0x18000b013`
- `SHLWAPI!PathFindFileNameW` at `0x18000b013`
- `SHLWAPI!PathFileExistsW` at `0x18000b119`
- `SHLWAPI!PathFileExistsW` at `0x18000b179`
- `SHLWAPI!PathFileExistsW` at `0x18000b119`
- `SHLWAPI!PathFileExistsW` at `0x18000b179`

## pseudocode

```c
__int64 __fastcall FBuildTempPathW(unsigned __int16 *a1, unsigned __int16 *a2, unsigned int a3, int a4)
{
  unsigned __int64 v4; // r15
  __int64 v8; // rcx
  __int64 v9; // rbx
  __int64 v10; // rdi
  __int64 v11; // rax
  unsigned int v12; // r14d
  unsigned __int64 v13; // rdx
  const WCHAR *v14; // r14
  const unsigned __int16 *FileNameW; // rsi
  LPWSTR ExtensionW; // rax
  __int64 v17; // rdx
  __int64 v18; // rcx
  unsigned __int64 v19; // rdx
  unsigned __int64 v20; // rcx
  unsigned __int16 *v21; // r11
  const unsigned __int16 *v22; // rdi
  int i; // ebx
  __int64 v25; // [rsp+28h] [rbp-D8h]
  LPCWSTR pszPath; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 v27[264]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 v28[264]; // [rsp+260h] [rbp+160h] BYREF

  v4 = a3;
  pszPath = 0;
  memset_0(v28, 0, 0x208u);
  memset_0(v27, 0, 0x208u);
  if ( !(unsigned int)AthGetTempUniquePathW(v8, v27) )
    v27[0] = 0;
  v9 = -1;
  v10 = -1;
  do
    ++v10;
  while ( v27[v10] );
  if ( (int)v10 >= (int)v4 - 15 )
  {
    StringCchCopyW(v27, 0x104u, L"\\");
    v10 = -1;
    do
      ++v10;
    while ( v27[v10] );
  }
  if ( a1 )
  {
    v11 = -1;
    do
      ++v11;
    while ( a1[v11] );
  }
  else
  {
    LODWORD(v11) = 0;
  }
  v12 = v11 + 1;
  if ( (unsigned int)MemAlloc((void **)&pszPath, 2 * ((int)v11 + 1)) )
  {
    if ( a1 )
    {
      v13 = v12;
      v14 = pszPath;
      StringCchCopyW((unsigned __int16 *)pszPath, v13, a1);
      FileNameW = PathFindFileNameW(v14);
      ExtensionW = PathFindExtensionW(v14);
      if ( ExtensionW )
      {
        if ( FileNameW )
        {
          v17 = -1;
          do
            ++v17;
          while ( FileNameW[v17] );
        }
        else
        {
          LODWORD(v17) = 0;
        }
        v18 = -1;
        do
          ++v18;
        while ( ExtensionW[v18] );
        if ( (int)v10 + (int)v17 + (int)v18 > (int)v4 - 10 )
        {
          if ( (int)v18 + (int)v10 > (int)v4 - 10 )
            *ExtensionW = 0;
          if ( FileNameW )
          {
            v19 = -1;
            do
              ++v19;
            while ( FileNameW[v19] );
          }
          else
          {
            v19 = 0;
          }
          do
            ++v9;
          while ( ExtensionW[v9] );
          v20 = (int)v4 - (__int64)(int)v10 - v9 - 11;
          if ( v19 >= v20 )
            FileNameW[v20] = 0;
        }
        if ( *ExtensionW )
        {
          *ExtensionW = 0;
          StringCchCopyW(v28, 0x104u, FileNameW);
          *v21 = 46;
        }
        else
        {
          StringCchCopyW(v28, 0x104u, FileNameW);
        }
        v22 = L".lnk";
        if ( !a4 )
          v22 = v21;
        StringCchCopyW(a2, v4, v27);
        StringCchCatW(a2, v4, v28);
        StringCchCatW(a2, v4, v22);
        if ( !PathFileExistsW(a2) )
        {
LABEL_40:
          ((void (__fastcall *)(LPMALLOC, const WCHAR *))g_pMalloc->lpVtbl->Free)(g_pMalloc, v14);
          return 1;
        }
        for ( i = 1; i < 100; ++i )
        {
          LODWORD(v25) = i;
          StringCchPrintfW(a2, v4, L"%s%s (%d)%s", v27, v28, v25, v22);
          if ( !PathFileExistsW(a2) )
            goto LABEL_40;
        }
        ((void (__fastcall *)(LPMALLOC, const WCHAR *))g_pMalloc->lpVtbl->Free)(g_pMalloc, v14);
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000af00  mov     [rsp-8+arg_18], rbx
0x18000af05  push    rbp
0x18000af06  push    rsi
0x18000af07  push    rdi
0x18000af08  push    r12
0x18000af0a  push    r13
0x18000af0c  push    r14
0x18000af0e  push    r15
0x18000af10  lea     rbp, [rsp-380h]
0x18000af18  sub     rsp, 480h
0x18000af1f  mov     rax, cs:__security_cookie
0x18000af26  xor     rax, rsp
0x18000af29  mov     [rbp+3B0h+var_40], rax
0x18000af30  mov     r15d, r8d
0x18000af33  mov     r12, rdx
0x18000af36  mov     rsi, rcx
0x18000af39  mov     ebx, 208h
0x18000af3e  xor     r14d, r14d
0x18000af41  lea     rcx, [rbp+3B0h+var_250]; void *
0x18000af48  mov     r8d, ebx; Size
0x18000af4b  mov     [rsp+4B0h+pszPath], r14
0x18000af50  xor     edx, edx; Val
0x18000af52  mov     r13d, r9d
0x18000af55  call    memset_0
0x18000af5a  mov     r8d, ebx; Size
0x18000af5d  lea     rcx, [rsp+4B0h+var_460]; void *
0x18000af62  xor     edx, edx; Val
0x18000af64  call    memset_0
0x18000af69  lea     rdx, [rsp+4B0h+var_460]; unsigned __int16 *
0x18000af6e  call    ?AthGetTempUniquePathW@@YAKKPEAG@Z; AthGetTempUniquePathW(ulong,ushort *)
0x18000af73  test    eax, eax
0x18000af75  jnz     short loc_18000AF7D
0x18000af77  mov     [rsp+4B0h+var_460], r14w
0x18000af7d  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000af81  lea     rax, [rsp+4B0h+var_460]
0x18000af86  mov     rdi, rbx
0x18000af89  inc     rdi
0x18000af8c  cmp     [rax+rdi*2], r14w
0x18000af91  jnz     short loc_18000AF89
0x18000af93  lea     eax, [r15-0Fh]
0x18000af97  cmp     edi, eax
0x18000af99  jl      short loc_18000AFC3
0x18000af9b  lea     r8, asc_180016C34; "\\"
0x18000afa2  mov     edx, 104h; unsigned __int64
0x18000afa7  lea     rcx, [rsp+4B0h+var_460]; unsigned __int16 *
0x18000afac  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000afb1  lea     r11, [rsp+4B0h+var_460]
0x18000afb6  mov     rdi, rbx
0x18000afb9  inc     rdi
0x18000afbc  cmp     [r11+rdi*2], r14w
0x18000afc1  jnz     short loc_18000AFB9
0x18000afc3  test    rsi, rsi
0x18000afc6  jz      short loc_18000AFD7
0x18000afc8  mov     rax, rbx
0x18000afcb  inc     rax
0x18000afce  cmp     [rsi+rax*2], r14w
0x18000afd3  jnz     short loc_18000AFCB
0x18000afd5  jmp     short loc_18000AFDA
0x18000afd7  mov     rax, r14
0x18000afda  lea     r14d, [rax+1]
0x18000afde  lea     edx, [r14+r14]; unsigned int
0x18000afe2  lea     rcx, [rsp+4B0h+pszPath]; void **
0x18000afe7  call    ?MemAlloc@@YAHPEAPEAXK@Z; MemAlloc(void * *,ulong)
0x18000afec  test    eax, eax
0x18000afee  jz      loc_18000B19D
0x18000aff4  test    rsi, rsi
0x18000aff7  jz      loc_18000B19D
0x18000affd  mov     edx, r14d; unsigned __int64
0x18000b000  mov     r8, rsi; unsigned __int16 *
0x18000b003  mov     r14, [rsp+4B0h+pszPath]
0x18000b008  mov     rcx, r14; unsigned __int16 *
0x18000b00b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000b010  mov     rcx, r14; pszPath
0x18000b013  call    cs:__imp_PathFindFileNameW
0x18000b019  mov     rcx, r14; pszPath
0x18000b01c  mov     rsi, rax
0x18000b01f  call    cs:__imp_PathFindExtensionW
0x18000b025  xor     r9d, r9d
0x18000b028  mov     r11, rax
0x18000b02b  test    rax, rax
0x18000b02e  jz      loc_18000B19D
0x18000b034  test    rsi, rsi
0x18000b037  jz      short loc_18000B048
0x18000b039  mov     rdx, rbx
0x18000b03c  inc     rdx
0x18000b03f  cmp     [rsi+rdx*2], r9w
0x18000b044  jnz     short loc_18000B03C
0x18000b046  jmp     short loc_18000B04B
0x18000b048  mov     rdx, r9
0x18000b04b  mov     rcx, rbx
0x18000b04e  inc     rcx
0x18000b051  cmp     [rax+rcx*2], r9w
0x18000b056  jnz     short loc_18000B04E
0x18000b058  lea     eax, [rdx+rcx]
0x18000b05b  add     eax, edi
0x18000b05d  lea     r8d, [r15-0Ah]
0x18000b061  cmp     eax, r8d
0x18000b064  jle     short loc_18000B0AD
0x18000b066  lea     eax, [rcx+rdi]
0x18000b069  cmp     eax, r8d
0x18000b06c  jle     short loc_18000B072
0x18000b06e  mov     [r11], r9w
0x18000b072  test    rsi, rsi
0x18000b075  jz      short loc_18000B086
0x18000b077  mov     rdx, rbx
0x18000b07a  inc     rdx
0x18000b07d  cmp     [rsi+rdx*2], r9w
0x18000b082  jnz     short loc_18000B07A
0x18000b084  jmp     short loc_18000B089
0x18000b086  mov     rdx, r9
0x18000b089  inc     rbx
0x18000b08c  cmp     [r11+rbx*2], r9w
0x18000b091  jnz     short loc_18000B089
0x18000b093  movsxd  rcx, r15d
0x18000b096  movsxd  rax, edi
0x18000b099  sub     rcx, rax
0x18000b09c  sub     rcx, rbx
0x18000b09f  add     rcx, 0FFFFFFFFFFFFFFF5h
0x18000b0a3  cmp     rdx, rcx
0x18000b0a6  jb      short loc_18000B0AD
0x18000b0a8  mov     [rsi+rcx*2], r9w
0x18000b0ad  lea     rcx, [rbp+3B0h+var_250]; unsigned __int16 *
0x18000b0b4  mov     r8, rsi; unsigned __int16 *
0x18000b0b7  mov     edx, 104h; unsigned __int64
0x18000b0bc  cmp     [r11], r9w
0x18000b0c0  jz      short loc_18000B0D3
0x18000b0c2  mov     [r11], r9w
0x18000b0c6  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000b0cb  mov     word ptr [r11], 2Eh ; '.'
0x18000b0d1  jmp     short loc_18000B0D8
0x18000b0d3  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000b0d8  test    r13d, r13d
0x18000b0db  lea     rdi, c_szLnkExt; ".lnk"
0x18000b0e2  lea     r8, [rsp+4B0h+var_460]; unsigned __int16 *
0x18000b0e7  mov     rdx, r15; unsigned __int64
0x18000b0ea  mov     rcx, r12; unsigned __int16 *
0x18000b0ed  cmovz   rdi, r11
0x18000b0f1  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000b0f6  lea     r8, [rbp+3B0h+var_250]; unsigned __int16 *
0x18000b0fd  mov     rdx, r15; unsigned __int64
0x18000b100  mov     rcx, r12; unsigned __int16 *
0x18000b103  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000b108  mov     r8, rdi; unsigned __int16 *
0x18000b10b  mov     rdx, r15; unsigned __int64
0x18000b10e  mov     rcx, r12; unsigned __int16 *
0x18000b111  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000b116  mov     rcx, r12; pszPath
0x18000b119  call    cs:__imp_PathFileExistsW
0x18000b11f  test    eax, eax
0x18000b121  jnz     short loc_18000B140
0x18000b123  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x18000b12a  mov     rdx, r14
0x18000b12d  mov     rax, [rcx]
0x18000b130  mov     rax, [rax+28h]
0x18000b134  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b139  mov     eax, 1
0x18000b13e  jmp     short loc_18000B19F
0x18000b140  mov     ebx, 1
0x18000b145  cmp     ebx, 64h ; 'd'
0x18000b148  jge     short loc_18000B187
0x18000b14a  mov     [rsp+4B0h+var_480], rdi
0x18000b14f  lea     rax, [rbp+3B0h+var_250]
0x18000b156  mov     dword ptr [rsp+4B0h+var_488], ebx
0x18000b15a  lea     r9, [rsp+4B0h+var_460]
0x18000b15f  lea     r8, aSSDS; "%s%s (%d)%s"
0x18000b166  mov     [rsp+4B0h+var_490], rax
0x18000b16b  mov     rdx, r15; unsigned __int64
0x18000b16e  mov     rcx, r12; unsigned __int16 *
0x18000b171  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000b176  mov     rcx, r12; pszPath
0x18000b179  call    cs:__imp_PathFileExistsW
0x18000b17f  test    eax, eax
0x18000b181  jz      short loc_18000B123
0x18000b183  inc     ebx
0x18000b185  jmp     short loc_18000B145
0x18000b187  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x18000b18e  mov     rdx, r14
0x18000b191  mov     rax, [rcx]
0x18000b194  mov     rax, [rax+28h]
0x18000b198  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b19d  xor     eax, eax
0x18000b19f  mov     rcx, [rbp+3B0h+var_40]
0x18000b1a6  xor     rcx, rsp; StackCookie
0x18000b1a9  call    __security_check_cookie
0x18000b1ae  mov     rbx, [rsp+4B0h+arg_18]
0x18000b1b6  add     rsp, 480h
0x18000b1bd  pop     r15
0x18000b1bf  pop     r14
0x18000b1c1  pop     r13
0x18000b1c3  pop     r12
0x18000b1c5  pop     rdi
0x18000b1c6  pop     rsi
0x18000b1c7  pop     rbp
0x18000b1c8  retn
```
