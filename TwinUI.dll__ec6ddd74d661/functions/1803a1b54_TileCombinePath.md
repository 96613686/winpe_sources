# TileCombinePath

- ea: `0x1803a1b54`
- end: `0x1803a1cdc`
- name: `TileCombinePath`
- size: `392`
- prototype: `__int64 __fastcall(LPCWSTR pszPrefix, PCWSTR pszMore)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, service_task, broker_com_uri`

## callers

- `0x1802f45b0`

## callees

- `0x1803a1b54`

## import_xrefs

- `api-ms-win-core-path-l1-1-0!PathCchRemoveBackslash` at `0x1803a1c5a`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveBackslash` at `0x1803a1c5a`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x1803a1bfc`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x1803a1bfc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1803a1c2b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1803a1c96`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1803a1cb6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1803a1c2b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1803a1c96`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1803a1cb6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1803a1bc8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1803a1bc8`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x1803a1c3f`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x1803a1c3f`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsPrefixW` at `0x1803a1c77`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsPrefixW` at `0x1803a1c77`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRelativeW` at `0x1803a1b7f`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRelativeW` at `0x1803a1b7f`

## pseudocode

```c
__int64 __fastcall TileCombinePath(LPCWSTR pszPrefix, PCWSTR pszMore, __int64 a3, WCHAR **a4)
{
  WCHAR *v5; // rsi
  HRESULT v8; // ebx
  __int64 v9; // rax
  __int64 v10; // rbp
  size_t v11; // r14
  WCHAR *v12; // rax
  bool v13; // zf
  HRESULT v14; // eax
  BOOL IsPrefixW; // eax
  int v16; // ecx
  LPWSTR ppwsz; // [rsp+68h] [rbp+20h] BYREF

  *a4 = 0;
  v5 = 0;
  if ( !PathIsRelativeW(pszMore) )
    goto LABEL_20;
  if ( !pszPrefix )
  {
    v8 = -2147467261;
    goto LABEL_21;
  }
  v9 = -1;
  v10 = -1;
  do
    ++v10;
  while ( pszPrefix[v10] );
  do
    ++v9;
  while ( pszMore[v9] );
  v11 = v10 + v9 + 2;
  v12 = (WCHAR *)CoTaskMemAlloc(2 * v11);
  v5 = v12;
  if ( !v12 )
  {
    v8 = -2147024882;
    goto LABEL_21;
  }
  if ( !*pszPrefix )
  {
LABEL_20:
    v8 = -2147024809;
    goto LABEL_21;
  }
  v8 = PathCchCombine(v12, v11, pszPrefix, pszMore);
  if ( v8 >= 0 )
  {
    if ( *pszPrefix == 45 )
      goto LABEL_19;
    v13 = pszPrefix[v10 - 1] == 92;
    ppwsz = 0;
    if ( !v13
      || (CoTaskMemFree(0), v8 = SHStrDupW(pszPrefix, &ppwsz), v8 >= 0)
      && (v14 = PathCchRemoveBackslash(ppwsz, v10 + 1), pszPrefix = ppwsz, v8 = v14, v14 >= 0) )
    {
      IsPrefixW = PathIsPrefixW(pszPrefix, v5);
      v16 = v8;
      if ( !IsPrefixW )
        v16 = -2147024809;
      v8 = v16;
    }
    CoTaskMemFree(ppwsz);
    if ( v8 >= 0 )
    {
LABEL_19:
      *a4 = v5;
      v5 = 0;
    }
  }
LABEL_21:
  CoTaskMemFree(v5);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1803a1b54  mov     [rsp+arg_0], rbx
0x1803a1b59  mov     [rsp+arg_8], rbp
0x1803a1b5e  push    rsi
0x1803a1b5f  push    rdi
0x1803a1b60  push    r12
0x1803a1b62  push    r14
0x1803a1b64  push    r15
0x1803a1b66  sub     rsp, 20h
0x1803a1b6a  mov     rdi, rcx
0x1803a1b6d  xor     r12d, r12d
0x1803a1b70  mov     rcx, rdx; pszPath
0x1803a1b73  mov     [r9], r12
0x1803a1b76  mov     esi, r12d
0x1803a1b79  mov     r15, r9
0x1803a1b7c  mov     rbx, rdx
0x1803a1b7f  call    cs:__imp_PathIsRelativeW
0x1803a1b86  nop     dword ptr [rax+rax+00h]
0x1803a1b8b  test    eax, eax
0x1803a1b8d  jz      loc_1803A1CAE
0x1803a1b93  test    rdi, rdi
0x1803a1b96  jnz     short loc_1803A1BA2
0x1803a1b98  mov     ebx, 80004003h
0x1803a1b9d  jmp     loc_1803A1CB3
0x1803a1ba2  or      rax, 0FFFFFFFFFFFFFFFFh
0x1803a1ba6  mov     rbp, rax
0x1803a1ba9  inc     rbp
0x1803a1bac  cmp     [rdi+rbp*2], r12w
0x1803a1bb1  jnz     short loc_1803A1BA9
0x1803a1bb3  inc     rax
0x1803a1bb6  cmp     [rbx+rax*2], r12w
0x1803a1bbb  jnz     short loc_1803A1BB3
0x1803a1bbd  lea     r14, [rax+2]
0x1803a1bc1  add     r14, rbp
0x1803a1bc4  lea     rcx, [r14+r14]; cb
0x1803a1bc8  call    cs:__imp_CoTaskMemAlloc
0x1803a1bcf  nop     dword ptr [rax+rax+00h]
0x1803a1bd4  mov     rsi, rax
0x1803a1bd7  test    rax, rax
0x1803a1bda  jnz     short loc_1803A1BE6
0x1803a1bdc  mov     ebx, 8007000Eh
0x1803a1be1  jmp     loc_1803A1CB3
0x1803a1be6  cmp     [rdi], r12w
0x1803a1bea  jz      loc_1803A1CAE
0x1803a1bf0  mov     r9, rbx; pszMore
0x1803a1bf3  mov     r8, rdi; pszPathIn
0x1803a1bf6  mov     rdx, r14; cchPathOut
0x1803a1bf9  mov     rcx, rsi; pszPathOut
0x1803a1bfc  call    cs:__imp_PathCchCombine
0x1803a1c03  nop     dword ptr [rax+rax+00h]
0x1803a1c08  mov     ebx, eax
0x1803a1c0a  test    eax, eax
0x1803a1c0c  js      loc_1803A1CB3
0x1803a1c12  cmp     word ptr [rdi], 2Dh ; '-'
0x1803a1c16  jz      loc_1803A1CA6
0x1803a1c1c  cmp     word ptr [rdi+rbp*2-2], 5Ch ; '\'
0x1803a1c22  mov     [rsp+48h+ppwsz], r12
0x1803a1c27  jnz     short loc_1803A1C71
0x1803a1c29  xor     ecx, ecx; pv
0x1803a1c2b  call    cs:__imp_CoTaskMemFree
0x1803a1c32  nop     dword ptr [rax+rax+00h]
0x1803a1c37  lea     rdx, [rsp+48h+ppwsz]; ppwsz
0x1803a1c3c  mov     rcx, rdi; psz
0x1803a1c3f  call    cs:__imp_SHStrDupW
0x1803a1c46  nop     dword ptr [rax+rax+00h]
0x1803a1c4b  mov     ebx, eax
0x1803a1c4d  test    eax, eax
0x1803a1c4f  js      short loc_1803A1C91
0x1803a1c51  mov     rcx, [rsp+48h+ppwsz]; pszPath
0x1803a1c56  lea     rdx, [rbp+1]; cchPath
0x1803a1c5a  call    cs:__imp_PathCchRemoveBackslash
0x1803a1c61  nop     dword ptr [rax+rax+00h]
0x1803a1c66  mov     rdi, [rsp+48h+ppwsz]
0x1803a1c6b  mov     ebx, eax
0x1803a1c6d  test    eax, eax
0x1803a1c6f  js      short loc_1803A1C91
0x1803a1c71  mov     rdx, rsi; pszPath
0x1803a1c74  mov     rcx, rdi; pszPrefix
0x1803a1c77  call    cs:__imp_PathIsPrefixW
0x1803a1c7e  nop     dword ptr [rax+rax+00h]
0x1803a1c83  mov     ecx, ebx
0x1803a1c85  mov     ebx, 80070057h
0x1803a1c8a  test    eax, eax
0x1803a1c8c  cmovz   ecx, ebx
0x1803a1c8f  mov     ebx, ecx
0x1803a1c91  mov     rcx, [rsp+48h+ppwsz]; pv
0x1803a1c96  call    cs:__imp_CoTaskMemFree
0x1803a1c9d  nop     dword ptr [rax+rax+00h]
0x1803a1ca2  test    ebx, ebx
0x1803a1ca4  js      short loc_1803A1CB3
0x1803a1ca6  mov     [r15], rsi
0x1803a1ca9  mov     rsi, r12
0x1803a1cac  jmp     short loc_1803A1CB3
0x1803a1cae  mov     ebx, 80070057h
0x1803a1cb3  mov     rcx, rsi; pv
0x1803a1cb6  call    cs:__imp_CoTaskMemFree
0x1803a1cbd  nop     dword ptr [rax+rax+00h]
0x1803a1cc2  mov     rbp, [rsp+48h+arg_8]
0x1803a1cc7  mov     eax, ebx
0x1803a1cc9  mov     rbx, [rsp+48h+arg_0]
0x1803a1cce  add     rsp, 20h
0x1803a1cd2  pop     r15
0x1803a1cd4  pop     r14
0x1803a1cd6  pop     r12
0x1803a1cd8  pop     rdi
0x1803a1cd9  pop     rsi
0x1803a1cda  retn
```
