# WUPathCchCanonicalize(wchar_t *,ulong,wchar_t const *)

- ea: `0x18004cb74`
- end: `0x18004cea7`
- name: `?WUPathCchCanonicalize@@YAJPEA_WKPEB_W@Z`
- size: `819`
- prototype: `__int64 __fastcall(wchar_t *, unsigned int, const wchar_t *)`
- caller_count: `1`
- callee_count: `8`
- tags: `reparse_path`

## callers

- `0x18004cf4c`

## callees

- `0x180003180`
- `0x18000970c`
- `0x18000dce4`
- `0x18000dd60`
- `0x18004cb1c`
- `0x18004cb74`
- `0x18004d260`
- `0x180063b78`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCW` at `0x18004cc7c`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCW` at `0x18004cc7c`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRootW` at `0x18004cd24`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRootW` at `0x18004cd64`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRootW` at `0x18004cd24`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRootW` at `0x18004cd64`

## string_xrefs

- `0x18004ce94`: `C:\__w\1\s\src\Client\lib\wusafefn\safepath.cpp`

## pseudocode

```c
__int64 __fastcall WUPathCchCanonicalize(wchar_t *a1, unsigned int a2, const wchar_t *a3)
{
  unsigned __int64 v3; // r13
  wchar_t *v6; // rbx
  __int64 v7; // rdx
  __int64 v8; // rax
  unsigned int v9; // edi
  int v10; // eax
  unsigned __int64 v11; // r9
  const wchar_t *i; // rcx
  wchar_t *v13; // rax
  wchar_t *v14; // r12
  wchar_t *v15; // rsi
  wchar_t *v16; // r15
  unsigned int IsUNCW; // edi
  wchar_t *v18; // rbp
  __int64 v19; // rax
  __int64 v20; // rbp
  wchar_t *v21; // r15
  wchar_t *v22; // rax
  wchar_t *v23; // rcx
  __int64 v24; // rdx
  __int64 v25; // rax
  unsigned __int64 *v27; // [rsp+20h] [rbp-68h]
  unsigned __int64 *v28; // [rsp+28h] [rbp-60h]
  unsigned int v29; // [rsp+30h] [rbp-58h]
  unsigned int v30; // [rsp+40h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  v3 = a2;
  v6 = 0;
  if ( !a1 )
  {
    v7 = 63;
LABEL_11:
    v9 = -2147024809;
    goto LABEL_74;
  }
  if ( !a2 )
  {
    v7 = 64;
    goto LABEL_11;
  }
  if ( !a3 )
  {
    v7 = 65;
    goto LABEL_11;
  }
  v8 = -1;
  do
    ++v8;
  while ( a3[v8] );
  if ( a2 < (int)v8 + 1 )
  {
    v7 = 66;
    goto LABEL_11;
  }
  if ( !*a3 )
  {
    *a1 = 0;
    v9 = 0;
    goto LABEL_76;
  }
  v6 = (wchar_t *)SafeSusAllocArray(a2, 2u);
  v9 = v6 == 0 ? 0x8007000E : 0;
  if ( !v6 )
  {
    v7 = 78;
    goto LABEL_74;
  }
  v10 = StringCchCopyExW(v6, v3, a3, 0, 0, 0x1100u);
  v9 = v10;
  if ( v10 < 0 )
  {
    v11 = (unsigned int)v10;
    v7 = 80;
    goto LABEL_75;
  }
  for ( i = v6; ; i = v13 )
  {
    v13 = wcschr(i, 0x2Fu);
    if ( !v13 )
      break;
    *v13 = 92;
  }
  *a1 = 0;
  v14 = &a1[v3 - 1];
  v15 = v6;
  v16 = a1;
  IsUNCW = PathIsUNCW(a3);
  v30 = IsUNCW;
  if ( !*v6 )
  {
LABEL_65:
    WUNearRootFixupsW(a1, (unsigned int)v3, IsUNCW);
    v9 = 0;
    goto LABEL_66;
  }
  v9 = 0;
  while ( v16 < v14 )
  {
    *v16 = 0;
    v18 = wcschr(v15, 0x5Cu);
    if ( !v18 )
    {
      v19 = -1;
      do
        ++v19;
      while ( v15[v19] );
      v18 = &v15[v19];
    }
    v20 = v18 - v15;
    if ( (_DWORD)v20 )
    {
      switch ( (_DWORD)v20 )
      {
        case 1:
          if ( *v15 == 46 )
          {
            if ( v15[1] )
            {
              v15 += 2;
              goto LABEL_63;
            }
            ++v15;
            if ( v16 <= a1 || PathIsRootW(a1) )
              goto LABEL_63;
            --v16;
            goto LABEL_62;
          }
          break;
        case 2:
          if ( *v15 == 46 && v15[1] == 46 )
          {
            if ( PathIsRootW(a1) )
            {
              if ( v15[2] == 92 )
                ++v15;
              v9 = 0;
            }
            else
            {
              v9 = 0;
              v21 = v16 - 1;
              v22 = 0;
              if ( v21 > a1 )
              {
                v23 = a1;
                if ( !v21 )
                {
                  v24 = -1;
                  do
                    ++v24;
                  while ( a1[v24] );
                  v21 = &a1[v24];
                }
                if ( a1 < v21 )
                {
                  do
                  {
                    if ( *v23 == 92 )
                      v22 = v23;
                    ++v23;
                  }
                  while ( v23 < v21 );
                }
              }
              v16 = a1;
              if ( v22 )
                v16 = v22;
            }
            v15 += 2;
            goto LABEL_62;
          }
          break;
        case 0xFFFFFFFF:
          WUNearRootFixupsW(a1, (unsigned int)v3, v30);
          goto LABEL_76;
      }
    }
    else if ( *v15 == 92 )
    {
      if ( v16 + 1 > v14 )
      {
        v7 = 129;
        goto LABEL_73;
      }
      *v16 = v20 + 92;
      ++v15;
      ++v16;
      goto LABEL_63;
    }
    v9 = StringCchCopyNExW(v16, (unsigned int)(v14 - v16) + 1, v15, (unsigned int)(v20 + 1), (wchar_t **)v27, v28, v29);
    if ( (v9 & 0x80000000) != 0 )
    {
      v7 = 197;
      goto LABEL_74;
    }
    v25 = 2LL * (unsigned int)v20;
    v16 = (wchar_t *)((char *)v16 + v25);
    v15 = (wchar_t *)((char *)v15 + v25);
    v9 = 0;
LABEL_62:
    if ( v16 > v14 )
    {
      v7 = 209;
      goto LABEL_73;
    }
LABEL_63:
    *v16 = 0;
    if ( !*v15 )
    {
      IsUNCW = v30;
      goto LABEL_65;
    }
  }
  v7 = 106;
LABEL_73:
  a1[(unsigned int)(v3 - 1)] = 0;
  v9 = -2147024774;
LABEL_74:
  v11 = v9;
LABEL_75:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v7,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\wusafefn\\safepath.cpp",
    (const char *)v11,
    (int)v27);
LABEL_76:
  if ( v6 )
LABEL_66:
    SusFree(v6);
  return v9;
}

```

## disassembly

```asm
0x18004cb74  mov     [rsp+arg_18], rbx
0x18004cb79  push    rbp
0x18004cb7a  push    rsi
0x18004cb7b  push    rdi
0x18004cb7c  push    r12
0x18004cb7e  push    r13
0x18004cb80  push    r14
0x18004cb82  push    r15
0x18004cb84  sub     rsp, 50h
0x18004cb88  xor     esi, esi
0x18004cb8a  mov     r13d, edx
0x18004cb8d  mov     rbp, r8
0x18004cb90  mov     r14, rcx
0x18004cb93  mov     ebx, esi
0x18004cb95  test    rcx, rcx
0x18004cb98  jnz     short loc_18004CB9F
0x18004cb9a  lea     edx, [rcx+3Fh]
0x18004cb9d  jmp     short loc_18004CBCE
0x18004cb9f  test    edx, edx
0x18004cba1  jnz     short loc_18004CBAA
0x18004cba3  mov     edx, 40h ; '@'
0x18004cba8  jmp     short loc_18004CBCE
0x18004cbaa  test    rbp, rbp
0x18004cbad  jnz     short loc_18004CBB4
0x18004cbaf  lea     edx, [rbp+41h]
0x18004cbb2  jmp     short loc_18004CBCE
0x18004cbb4  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004cbb8  inc     rax
0x18004cbbb  cmp     [r8+rax*2], si
0x18004cbc0  jnz     short loc_18004CBB8
0x18004cbc2  inc     eax
0x18004cbc4  cmp     r13d, eax
0x18004cbc7  jnb     short loc_18004CBD8
0x18004cbc9  mov     edx, 42h ; 'B'
0x18004cbce  mov     edi, 80070057h
0x18004cbd3  jmp     loc_18004CE89
0x18004cbd8  cmp     [r8], si
0x18004cbdc  jnz     short loc_18004CBE8
0x18004cbde  mov     [rcx], si
0x18004cbe1  mov     edi, esi
0x18004cbe3  jmp     loc_18004CEA0
0x18004cbe8  mov     edx, 2; unsigned __int64
0x18004cbed  mov     rcx, r13; unsigned __int64
0x18004cbf0  mov     r12, r13
0x18004cbf3  call    ?SafeSusAllocArray@@YAPEAX_K0@Z; SafeSusAllocArray(unsigned __int64,unsigned __int64)
0x18004cbf8  mov     rbx, rax
0x18004cbfb  neg     rax
0x18004cbfe  sbb     edi, edi
0x18004cc00  not     edi
0x18004cc02  and     edi, 8007000Eh
0x18004cc08  test    rbx, rbx
0x18004cc0b  jnz     short loc_18004CC15
0x18004cc0d  lea     edx, [rbx+4Eh]
0x18004cc10  jmp     loc_18004CE89
0x18004cc15  mov     dword ptr [rsp+88h+var_60], 1100h; unsigned int
0x18004cc1d  xor     r9d, r9d; wchar_t **
0x18004cc20  mov     r8, rbp; wchar_t *
0x18004cc23  mov     [rsp+88h+var_68], rsi; unsigned __int64 *
0x18004cc28  mov     rdx, r13; unsigned __int64
0x18004cc2b  mov     rcx, rbx; pszDest
0x18004cc2e  call    ?StringCchCopyExW@@YAJPEA_W_KPEB_WPEAPEA_WPEA_KK@Z; StringCchCopyExW(wchar_t *,unsigned __int64,wchar_t const *,wchar_t * *,unsigned __int64 *,ulong)
0x18004cc33  mov     edi, eax
0x18004cc35  test    eax, eax
0x18004cc37  jns     short loc_18004CC46
0x18004cc39  mov     r9d, eax
0x18004cc3c  mov     edx, 50h ; 'P'
0x18004cc41  jmp     loc_18004CE8C
0x18004cc46  mov     edi, 2Fh ; '/'
0x18004cc4b  mov     rcx, rbx
0x18004cc4e  jmp     short loc_18004CC58
0x18004cc50  mov     word ptr [rax], 5Ch ; '\'
0x18004cc55  mov     rcx, rax; Str
0x18004cc58  mov     edx, edi; Ch
0x18004cc5a  call    wcschr
0x18004cc5f  test    rax, rax
0x18004cc62  jnz     short loc_18004CC50
0x18004cc64  xor     ecx, ecx
0x18004cc66  lea     r12, [r12-1]
0x18004cc6b  mov     [r14], cx
0x18004cc6f  lea     r12, [r14+r12*2]
0x18004cc73  mov     rcx, rbp; pszPath
0x18004cc76  mov     rsi, rbx
0x18004cc79  mov     r15, r14
0x18004cc7c  call    cs:__imp_PathIsUNCW
0x18004cc82  mov     edi, eax
0x18004cc84  mov     [rsp+88h+var_48], eax
0x18004cc88  xor     eax, eax
0x18004cc8a  cmp     [rbx], ax
0x18004cc8d  jz      loc_18004CE1B
0x18004cc93  xor     edi, edi
0x18004cc95  cmp     r15, r12
0x18004cc98  jnb     loc_18004CE76
0x18004cc9e  mov     edx, 5Ch ; '\'; Ch
0x18004cca3  mov     [r15], di
0x18004cca7  mov     rcx, rsi; Str
0x18004ccaa  call    wcschr
0x18004ccaf  mov     rbp, rax
0x18004ccb2  test    rax, rax
0x18004ccb5  jnz     short loc_18004CCC8
0x18004ccb7  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004ccbb  inc     rax
0x18004ccbe  cmp     [rsi+rax*2], di
0x18004ccc2  jnz     short loc_18004CCBB
0x18004ccc4  lea     rbp, [rsi+rax*2]
0x18004ccc8  sub     rbp, rsi
0x18004cccb  sar     rbp, 1
0x18004ccce  lea     eax, [rbp+1]
0x18004ccd1  cmp     eax, 1
0x18004ccd4  jnz     short loc_18004CCFF
0x18004ccd6  lea     ecx, [rax+5Bh]
0x18004ccd9  cmp     [rsi], cx
0x18004ccdc  jnz     loc_18004CDD9
0x18004cce2  lea     rax, [r15+2]
0x18004cce6  cmp     rax, r12
0x18004cce9  ja      loc_18004CE4F
0x18004ccef  mov     [r15], cx
0x18004ccf3  add     rsi, 2
0x18004ccf7  mov     r15, rax
0x18004ccfa  jmp     loc_18004CE0A
0x18004ccff  cmp     eax, 2
0x18004cd02  jnz     short loc_18004CD44
0x18004cd04  cmp     word ptr [rsi], 2Eh ; '.'
0x18004cd08  jnz     loc_18004CDD9
0x18004cd0e  cmp     [rsi+2], di
0x18004cd12  jnz     short loc_18004CD3B
0x18004cd14  add     rsi, 2
0x18004cd18  cmp     r15, r14
0x18004cd1b  jbe     loc_18004CE0A
0x18004cd21  mov     rcx, r14; pszPath
0x18004cd24  call    cs:__imp_PathIsRootW
0x18004cd2a  test    eax, eax
0x18004cd2c  jnz     loc_18004CE0A
0x18004cd32  sub     r15, 2
0x18004cd36  jmp     loc_18004CE05
0x18004cd3b  add     rsi, 4
0x18004cd3f  jmp     loc_18004CE0A
0x18004cd44  cmp     eax, 3
0x18004cd47  jnz     loc_18004CDD0
0x18004cd4d  cmp     word ptr [rsi], 2Eh ; '.'
0x18004cd51  jnz     loc_18004CDD9
0x18004cd57  lea     rdi, [rsi+2]
0x18004cd5b  cmp     word ptr [rdi], 2Eh ; '.'
0x18004cd5f  jnz     short loc_18004CDD9
0x18004cd61  mov     rcx, r14; pszPath
0x18004cd64  call    cs:__imp_PathIsRootW
0x18004cd6a  test    eax, eax
0x18004cd6c  jnz     short loc_18004CDBB
0x18004cd6e  xor     edi, edi
0x18004cd70  add     r15, 0FFFFFFFFFFFFFFFEh
0x18004cd74  mov     eax, edi
0x18004cd76  cmp     r15, r14
0x18004cd79  jbe     short loc_18004CDAF
0x18004cd7b  mov     rcx, r14
0x18004cd7e  test    r15, r15
0x18004cd81  jnz     short loc_18004CD95
0x18004cd83  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18004cd87  inc     rdx
0x18004cd8a  cmp     [r14+rdx*2], di
0x18004cd8f  jnz     short loc_18004CD87
0x18004cd91  lea     r15, [r14+rdx*2]
0x18004cd95  cmp     r14, r15
0x18004cd98  jnb     short loc_18004CDAF
0x18004cd9a  mov     edx, 5Ch ; '\'
0x18004cd9f  cmp     [rcx], dx
0x18004cda2  cmovz   rax, rcx
0x18004cda6  add     rcx, 2
0x18004cdaa  cmp     rcx, r15
0x18004cdad  jb      short loc_18004CD9F
0x18004cdaf  test    rax, rax
0x18004cdb2  mov     r15, r14
0x18004cdb5  cmovnz  r15, rax
0x18004cdb9  jmp     short loc_18004CDCA
0x18004cdbb  mov     eax, 5Ch ; '\'
0x18004cdc0  cmp     [rsi+4], ax
0x18004cdc4  cmovz   rsi, rdi
0x18004cdc8  xor     edi, edi
0x18004cdca  add     rsi, 4
0x18004cdce  jmp     short loc_18004CE05
0x18004cdd0  cmp     eax, 1
0x18004cdd3  jb      loc_18004CE64
0x18004cdd9  mov     rdx, r12
0x18004cddc  mov     r9d, eax; unsigned __int64
0x18004cddf  sub     rdx, r15
0x18004cde2  mov     r8, rsi; wchar_t *
0x18004cde5  sar     rdx, 1
0x18004cde8  mov     rcx, r15; wchar_t *
0x18004cdeb  inc     edx; unsigned __int64
0x18004cded  call    ?StringCchCopyNExW@@YAJPEA_W_KPEB_W1PEAPEA_WPEA_KK@Z; StringCchCopyNExW(wchar_t *,unsigned __int64,wchar_t const *,unsigned __int64,wchar_t * *,unsigned __int64 *,ulong)
0x18004cdf2  mov     edi, eax
0x18004cdf4  test    eax, eax
0x18004cdf6  js      short loc_18004CE5D
0x18004cdf8  mov     eax, ebp
0x18004cdfa  add     rax, rax
0x18004cdfd  add     r15, rax
0x18004ce00  add     rsi, rax
0x18004ce03  xor     edi, edi
0x18004ce05  cmp     r15, r12
0x18004ce08  ja      short loc_18004CE56
0x18004ce0a  mov     [r15], di
0x18004ce0e  cmp     [rsi], di
0x18004ce11  jnz     loc_18004CC95
0x18004ce17  mov     edi, [rsp+88h+var_48]
0x18004ce1b  mov     r8d, edi
0x18004ce1e  mov     edx, r13d
0x18004ce21  mov     rcx, r14
0x18004ce24  call    WUNearRootFixupsW
0x18004ce29  xor     eax, eax
0x18004ce2b  mov     edi, eax
0x18004ce2d  mov     rcx, rbx; lpMem
0x18004ce30  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18004ce35  mov     rbx, [rsp+88h+arg_18]
0x18004ce3d  mov     eax, edi
0x18004ce3f  add     rsp, 50h
0x18004ce43  pop     r15
0x18004ce45  pop     r14
0x18004ce47  pop     r13
0x18004ce49  pop     r12
0x18004ce4b  pop     rdi
0x18004ce4c  pop     rsi
0x18004ce4d  pop     rbp
0x18004ce4e  retn
0x18004ce4f  mov     edx, 81h
0x18004ce54  jmp     short loc_18004CE7B
0x18004ce56  mov     edx, 0D1h
0x18004ce5b  jmp     short loc_18004CE7B
0x18004ce5d  mov     edx, 0C5h
0x18004ce62  jmp     short loc_18004CE89
0x18004ce64  mov     r8d, [rsp+88h+var_48]
0x18004ce69  mov     edx, r13d
0x18004ce6c  mov     rcx, r14
0x18004ce6f  call    WUNearRootFixupsW
0x18004ce74  jmp     short loc_18004CEA0
0x18004ce76  mov     edx, 6Ah ; 'j'; void *
0x18004ce7b  lea     eax, [r13-1]
0x18004ce7f  mov     [r14+rax*2], di
0x18004ce84  mov     edi, 8007007Ah
0x18004ce89  mov     r9d, edi; char *
0x18004ce8c  mov     rcx, [rsp+88h]; this
0x18004ce94  lea     r8, aCW1SSrcClientL_21; "C:\\__w\\1\\s\\src\\Client\\lib\\wusafe"...
0x18004ce9b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004cea0  test    rbx, rbx
0x18004cea3  jz      short loc_18004CE35
0x18004cea5  jmp     short loc_18004CE2D
```
