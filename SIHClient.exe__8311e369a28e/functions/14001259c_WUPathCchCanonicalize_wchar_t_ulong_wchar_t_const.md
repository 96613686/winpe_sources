# WUPathCchCanonicalize(wchar_t *,ulong,wchar_t const *)

- ea: `0x14001259c`
- end: `0x140012928`
- name: `?WUPathCchCanonicalize@@YAJPEA_WKPEB_W@Z`
- size: `908`
- prototype: `__int64 __fastcall(wchar_t *, unsigned int, const wchar_t *)`
- caller_count: `1`
- callee_count: `7`
- tags: `reparse_path`

## callers

- `0x1400129cc`

## callees

- `0x140008de4`
- `0x14000ce30`
- `0x14000ce9c`
- `0x14000db18`
- `0x14001259c`
- `0x140012c78`
- `0x140047c20`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCW` at `0x14001269a`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCW` at `0x14001269a`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRootW` at `0x140012748`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRootW` at `0x140012788`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRootW` at `0x140012748`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRootW` at `0x140012788`

## string_xrefs

- `0x1400128c1`: `C:\__w\1\s\src\Client\lib\wusafefn\safepath.cpp`

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
  wchar_t *v15; // r14
  wchar_t *v16; // r15
  BOOL v17; // edi
  wchar_t *v18; // rbp
  __int64 v19; // rax
  __int64 v20; // rbp
  wchar_t *v21; // r15
  wchar_t *v22; // rax
  wchar_t *v23; // rdx
  __int64 v24; // rcx
  int v25; // eax
  __int64 v26; // rax
  unsigned __int64 *v28; // [rsp+20h] [rbp-68h]
  unsigned __int64 *v29; // [rsp+28h] [rbp-60h]
  unsigned int v30; // [rsp+30h] [rbp-58h]
  BOOL IsUNCW; // [rsp+40h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  v3 = a2;
  v6 = 0;
  if ( !a1 )
  {
    v7 = 63;
LABEL_9:
    v9 = -2147024809;
LABEL_78:
    v11 = v9;
    goto LABEL_79;
  }
  if ( !a3 )
  {
    v7 = 65;
    goto LABEL_9;
  }
  v8 = -1;
  do
    ++v8;
  while ( a3[v8] );
  if ( a2 < (int)v8 + 1 )
  {
    v7 = 66;
    goto LABEL_9;
  }
  if ( !*a3 )
  {
    *a1 = 0;
    v9 = 0;
    goto LABEL_80;
  }
  v6 = (wchar_t *)SafeSusAllocArray(a2, 2u);
  v9 = v6 == 0 ? 0x8007000E : 0;
  if ( !v6 )
  {
    v7 = 78;
    goto LABEL_78;
  }
  v10 = StringCchCopyExW(v6, v3, a3, 0, 0, 0x1100u);
  v9 = v10;
  if ( v10 < 0 )
  {
    v11 = (unsigned int)v10;
    v7 = 80;
LABEL_79:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\wusafefn\\safepath.cpp",
      (const char *)v11,
      (int)v28);
    goto LABEL_80;
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
  v17 = IsUNCW;
  if ( !*v6 )
  {
LABEL_61:
    if ( *a1 )
    {
      if ( a1[1] != 58 || a1[2] )
      {
        if ( v17 && *a1 == 92 && !a1[1] )
          *(_DWORD *)(a1 + 1) = 92;
      }
      else
      {
        *((_DWORD *)a1 + 1) = 92;
      }
    }
    else
    {
      *(_DWORD *)a1 = 92;
    }
    v9 = 0;
    goto LABEL_90;
  }
  while ( 1 )
  {
    if ( v16 >= v14 )
    {
      v7 = 106;
      goto LABEL_77;
    }
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
    if ( !(_DWORD)v20 )
    {
      if ( *v15 == 92 )
      {
        if ( v16 + 1 > v14 )
        {
          v7 = 129;
LABEL_77:
          v9 = -2147024774;
          a1[(unsigned int)(v3 - 1)] = 0;
          goto LABEL_78;
        }
        *v16 = 92;
        ++v15;
        ++v16;
        goto LABEL_59;
      }
      goto LABEL_56;
    }
    if ( (_DWORD)v20 == 1 )
    {
      if ( *v15 == 46 )
      {
        if ( v15[1] )
        {
          v15 += 2;
          goto LABEL_59;
        }
        ++v15;
        if ( v16 <= a1 || PathIsRootW(a1) )
          goto LABEL_59;
        --v16;
        goto LABEL_58;
      }
      goto LABEL_56;
    }
    if ( (_DWORD)v20 != 2 )
      break;
    if ( *v15 == 46 && v15[1] == 46 )
    {
      if ( PathIsRootW(a1) )
      {
        if ( v15[2] == 92 )
          ++v15;
      }
      else
      {
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
      goto LABEL_58;
    }
LABEL_56:
    v25 = StringCchCopyNExW(v16, (unsigned int)(v14 - v16) + 1, v15, (unsigned int)(v20 + 1), (wchar_t **)v28, v29, v30);
    v9 = v25;
    if ( v25 < 0 )
    {
      v11 = (unsigned int)v25;
      v7 = 197;
      goto LABEL_79;
    }
    v26 = 2LL * (unsigned int)v20;
    v16 = (wchar_t *)((char *)v16 + v26);
    v15 = (wchar_t *)((char *)v15 + v26);
LABEL_58:
    if ( v16 > v14 )
    {
      v7 = 209;
      goto LABEL_77;
    }
LABEL_59:
    *v16 = 0;
    if ( !*v15 )
    {
      v17 = IsUNCW;
      goto LABEL_61;
    }
  }
  if ( (_DWORD)v20 != -1 )
    goto LABEL_56;
  if ( *a1 )
  {
    if ( a1[1] != 58 || a1[2] )
    {
      if ( IsUNCW && *a1 == 92 && !a1[1] )
        *(_DWORD *)(a1 + 1) = 92;
    }
    else
    {
      *((_DWORD *)a1 + 1) = 92;
    }
  }
  else
  {
    *(_DWORD *)a1 = 92;
  }
  v9 = 0;
LABEL_80:
  if ( v6 )
LABEL_90:
    SusFree(v6);
  return v9;
}

```

## disassembly

```asm
0x14001259c  mov     [rsp+arg_18], rbx
0x1400125a1  push    rbp
0x1400125a2  push    rsi
0x1400125a3  push    rdi
0x1400125a4  push    r12
0x1400125a6  push    r13
0x1400125a8  push    r14
0x1400125aa  push    r15
0x1400125ac  sub     rsp, 50h
0x1400125b0  xor     r14d, r14d
0x1400125b3  mov     r13d, edx
0x1400125b6  mov     rbp, r8
0x1400125b9  mov     rsi, rcx
0x1400125bc  mov     ebx, r14d
0x1400125bf  test    rcx, rcx
0x1400125c2  jnz     short loc_1400125C9
0x1400125c4  lea     edx, [rcx+3Fh]
0x1400125c7  jmp     short loc_1400125ED
0x1400125c9  test    rbp, rbp
0x1400125cc  jnz     short loc_1400125D3
0x1400125ce  lea     edx, [rbp+41h]
0x1400125d1  jmp     short loc_1400125ED
0x1400125d3  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400125d7  inc     rax
0x1400125da  cmp     [r8+rax*2], r14w
0x1400125df  jnz     short loc_1400125D7
0x1400125e1  inc     eax
0x1400125e3  cmp     r13d, eax
0x1400125e6  jnb     short loc_1400125F7
0x1400125e8  mov     edx, 42h ; 'B'
0x1400125ed  mov     edi, 80070057h
0x1400125f2  jmp     loc_1400128B6
0x1400125f7  cmp     [r8], r14w
0x1400125fb  jnz     short loc_140012609
0x1400125fd  mov     [rcx], r14w
0x140012601  mov     edi, r14d
0x140012604  jmp     loc_1400128CD
0x140012609  mov     edx, 2; unsigned __int64
0x14001260e  mov     rcx, r13; unsigned __int64
0x140012611  mov     r12, r13
0x140012614  call    ?SafeSusAllocArray@@YAPEAX_K0@Z; SafeSusAllocArray(unsigned __int64,unsigned __int64)
0x140012619  mov     rbx, rax
0x14001261c  neg     rax
0x14001261f  sbb     edi, edi
0x140012621  not     edi
0x140012623  and     edi, 8007000Eh
0x140012629  test    rbx, rbx
0x14001262c  jnz     short loc_140012636
0x14001262e  lea     edx, [rbx+4Eh]
0x140012631  jmp     loc_1400128B6
0x140012636  mov     dword ptr [rsp+88h+var_60], 1100h; unsigned int
0x14001263e  xor     r9d, r9d; wchar_t **
0x140012641  mov     r8, rbp; wchar_t *
0x140012644  mov     [rsp+88h+var_68], r14; unsigned __int64 *
0x140012649  mov     rdx, r13; unsigned __int64
0x14001264c  mov     rcx, rbx; pszDest
0x14001264f  call    ?StringCchCopyExW@@YAJPEA_W_KPEB_WPEAPEA_WPEA_KK@Z; StringCchCopyExW(wchar_t *,unsigned __int64,wchar_t const *,wchar_t * *,unsigned __int64 *,ulong)
0x140012654  mov     edi, eax
0x140012656  test    eax, eax
0x140012658  jns     short loc_140012667
0x14001265a  mov     r9d, eax
0x14001265d  mov     edx, 50h ; 'P'
0x140012662  jmp     loc_1400128B9
0x140012667  mov     edi, 2Fh ; '/'
0x14001266c  mov     rcx, rbx
0x14001266f  jmp     short loc_140012679
0x140012671  mov     word ptr [rax], 5Ch ; '\'
0x140012676  mov     rcx, rax; Str
0x140012679  mov     edx, edi; Ch
0x14001267b  call    wcschr
0x140012680  test    rax, rax
0x140012683  jnz     short loc_140012671
0x140012685  lea     r12, [r12-1]
0x14001268a  mov     [rsi], ax
0x14001268d  mov     rcx, rbp; pszPath
0x140012690  lea     r12, [rsi+r12*2]
0x140012694  mov     r14, rbx
0x140012697  mov     r15, rsi
0x14001269a  call    cs:__imp_PathIsUNCW
0x1400126a0  xor     r8d, r8d
0x1400126a3  mov     [rsp+88h+var_48], eax
0x1400126a7  mov     edi, eax
0x1400126a9  cmp     [rbx], r8w
0x1400126ad  jz      loc_14001283E
0x1400126b3  cmp     r15, r12
0x1400126b6  jnb     loc_1400128A3
0x1400126bc  mov     edi, 5Ch ; '\'
0x1400126c1  mov     [r15], r8w
0x1400126c5  mov     edx, edi; Ch
0x1400126c7  mov     rcx, r14; Str
0x1400126ca  call    wcschr
0x1400126cf  xor     r8d, r8d
0x1400126d2  mov     rbp, rax
0x1400126d5  test    rax, rax
0x1400126d8  jnz     short loc_1400126EC
0x1400126da  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400126de  inc     rax
0x1400126e1  cmp     [r14+rax*2], r8w
0x1400126e6  jnz     short loc_1400126DE
0x1400126e8  lea     rbp, [r14+rax*2]
0x1400126ec  sub     rbp, r14
0x1400126ef  sar     rbp, 1
0x1400126f2  lea     eax, [rbp+1]
0x1400126f5  cmp     eax, 1
0x1400126f8  jnz     short loc_140012721
0x1400126fa  cmp     [r14], di
0x1400126fe  jnz     loc_1400127FA
0x140012704  lea     rax, [r15+2]
0x140012708  cmp     rax, r12
0x14001270b  ja      loc_140012853
0x140012711  mov     [r15], di
0x140012715  add     r14, 2
0x140012719  mov     r15, rax
0x14001271c  jmp     loc_14001282C
0x140012721  cmp     eax, 2
0x140012724  jnz     short loc_14001276B
0x140012726  cmp     word ptr [r14], 2Eh ; '.'
0x14001272b  jnz     loc_1400127FA
0x140012731  cmp     [r14+2], r8w
0x140012736  jnz     short loc_140012762
0x140012738  add     r14, 2
0x14001273c  cmp     r15, rsi
0x14001273f  jbe     loc_14001282C
0x140012745  mov     rcx, rsi; pszPath
0x140012748  call    cs:__imp_PathIsRootW
0x14001274e  xor     r8d, r8d
0x140012751  test    eax, eax
0x140012753  jnz     loc_14001282C
0x140012759  sub     r15, 2
0x14001275d  jmp     loc_140012827
0x140012762  add     r14, 4
0x140012766  jmp     loc_14001282C
0x14001276b  cmp     eax, 3
0x14001276e  jnz     loc_1400127F5
0x140012774  cmp     word ptr [r14], 2Eh ; '.'
0x140012779  jnz     short loc_1400127FA
0x14001277b  lea     rdi, [r14+2]
0x14001277f  cmp     word ptr [rdi], 2Eh ; '.'
0x140012783  jnz     short loc_1400127FA
0x140012785  mov     rcx, rsi; pszPath
0x140012788  call    cs:__imp_PathIsRootW
0x14001278e  xor     r8d, r8d
0x140012791  test    eax, eax
0x140012793  jnz     short loc_1400127E1
0x140012795  add     r15, 0FFFFFFFFFFFFFFFEh
0x140012799  mov     eax, r8d
0x14001279c  cmp     r15, rsi
0x14001279f  jbe     short loc_1400127D5
0x1400127a1  mov     rdx, rsi
0x1400127a4  test    r15, r15
0x1400127a7  jnz     short loc_1400127BB
0x1400127a9  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1400127ad  inc     rcx
0x1400127b0  cmp     [rsi+rcx*2], r8w
0x1400127b5  jnz     short loc_1400127AD
0x1400127b7  lea     r15, [rsi+rcx*2]
0x1400127bb  cmp     rsi, r15
0x1400127be  jnb     short loc_1400127D5
0x1400127c0  mov     ecx, 5Ch ; '\'
0x1400127c5  cmp     [rdx], cx
0x1400127c8  cmovz   rax, rdx
0x1400127cc  add     rdx, 2
0x1400127d0  cmp     rdx, r15
0x1400127d3  jb      short loc_1400127C5
0x1400127d5  test    rax, rax
0x1400127d8  mov     r15, rsi
0x1400127db  cmovnz  r15, rax
0x1400127df  jmp     short loc_1400127EF
0x1400127e1  mov     ecx, 5Ch ; '\'
0x1400127e6  cmp     [r14+4], cx
0x1400127eb  cmovz   r14, rdi
0x1400127ef  add     r14, 4
0x1400127f3  jmp     short loc_140012827
0x1400127f5  cmp     eax, 1
0x1400127f8  jb      short loc_14001286B
0x1400127fa  mov     rdx, r12
0x1400127fd  mov     r9d, eax; unsigned __int64
0x140012800  sub     rdx, r15
0x140012803  mov     r8, r14; wchar_t *
0x140012806  sar     rdx, 1
0x140012809  mov     rcx, r15; wchar_t *
0x14001280c  inc     edx; unsigned __int64
0x14001280e  call    ?StringCchCopyNExW@@YAJPEA_W_KPEB_W1PEAPEA_WPEA_KK@Z; StringCchCopyNExW(wchar_t *,unsigned __int64,wchar_t const *,unsigned __int64,wchar_t * *,unsigned __int64 *,ulong)
0x140012813  xor     r8d, r8d
0x140012816  mov     edi, eax
0x140012818  test    eax, eax
0x14001281a  js      short loc_140012861
0x14001281c  mov     eax, ebp
0x14001281e  add     rax, rax
0x140012821  add     r15, rax
0x140012824  add     r14, rax
0x140012827  cmp     r15, r12
0x14001282a  ja      short loc_14001285A
0x14001282c  mov     [r15], r8w
0x140012830  cmp     [r14], r8w
0x140012834  jnz     loc_1400126B3
0x14001283a  mov     edi, [rsp+88h+var_48]
0x14001283e  cmp     [rsi], r8w
0x140012842  jnz     loc_1400128D4
0x140012848  mov     dword ptr [rsi], 5Ch ; '\'
0x14001284e  jmp     loc_140012903
0x140012853  mov     edx, 81h
0x140012858  jmp     short loc_1400128A8
0x14001285a  mov     edx, 0D1h
0x14001285f  jmp     short loc_1400128A8
0x140012861  mov     r9d, eax
0x140012864  mov     edx, 0C5h
0x140012869  jmp     short loc_1400128B9
0x14001286b  cmp     [rsi], r8w
0x14001286f  jnz     short loc_140012875
0x140012871  mov     [rsi], edi
0x140012873  jmp     short loc_14001289E
0x140012875  cmp     word ptr [rsi+2], 3Ah ; ':'
0x14001287a  jnz     short loc_140012888
0x14001287c  cmp     [rsi+4], r8w
0x140012881  jnz     short loc_140012888
0x140012883  mov     [rsi+4], edi
0x140012886  jmp     short loc_14001289E
0x140012888  cmp     [rsp+88h+var_48], r8d
0x14001288d  jz      short loc_14001289E
0x14001288f  cmp     [rsi], di
0x140012892  jnz     short loc_14001289E
0x140012894  cmp     [rsi+2], r8w
0x140012899  jnz     short loc_14001289E
0x14001289b  mov     [rsi+2], edi
0x14001289e  mov     edi, r8d
0x1400128a1  jmp     short loc_1400128CD
0x1400128a3  mov     edx, 6Ah ; 'j'; void *
0x1400128a8  lea     eax, [r13-1]
0x1400128ac  mov     edi, 8007007Ah
0x1400128b1  mov     [rsi+rax*2], r8w
0x1400128b6  mov     r9d, edi; char *
0x1400128b9  mov     rcx, [rsp+88h]; this
0x1400128c1  lea     r8, aCW1SSrcClientL_27; "C:\\__w\\1\\s\\src\\Client\\lib\\wusafe"...
0x1400128c8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400128cd  test    rbx, rbx
0x1400128d0  jz      short loc_14001290E
0x1400128d2  jmp     short loc_140012906
0x1400128d4  cmp     word ptr [rsi+2], 3Ah ; ':'
0x1400128d9  jnz     short loc_1400128EB
0x1400128db  cmp     [rsi+4], r8w
0x1400128e0  jnz     short loc_1400128EB
0x1400128e2  mov     dword ptr [rsi+4], 5Ch ; '\'
0x1400128e9  jmp     short loc_140012903
0x1400128eb  test    edi, edi
0x1400128ed  jz      short loc_140012903
0x1400128ef  mov     eax, 5Ch ; '\'
0x1400128f4  cmp     [rsi], ax
0x1400128f7  jnz     short loc_140012903
0x1400128f9  cmp     [rsi+2], r8w
0x1400128fe  jnz     short loc_140012903
0x140012900  mov     [rsi+2], eax
0x140012903  mov     edi, r8d
0x140012906  mov     rcx, rbx; lpMem
0x140012909  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x14001290e  mov     rbx, [rsp+88h+arg_18]
0x140012916  mov     eax, edi
0x140012918  add     rsp, 50h
0x14001291c  pop     r15
0x14001291e  pop     r14
0x140012920  pop     r13
0x140012922  pop     r12
0x140012924  pop     rdi
0x140012925  pop     rsi
0x140012926  pop     rbp
0x140012927  retn
```
