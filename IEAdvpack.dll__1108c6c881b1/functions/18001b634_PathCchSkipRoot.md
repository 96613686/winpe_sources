# PathCchSkipRoot

- ea: `0x18001b634`
- end: `0x18001b77b`
- name: `PathCchSkipRoot`
- size: `327`
- prototype: `HRESULT __stdcall(PCWSTR pszPath, PCWSTR *ppszRootEnd)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path`

## callers

- `0x18001b784`

## callees

- `0x1800198d0`
- `0x18001a688`
- `0x18001a720`
- `0x18001b634`

## import_xrefs

- `msvcrt!iswalpha` at `0x18001b73f`
- `msvcrt!iswalpha` at `0x18001b73f`
- `msvcrt!wcschr` at `0x18001b691`
- `msvcrt!wcschr` at `0x18001b6a8`
- `msvcrt!wcschr` at `0x18001b691`
- `msvcrt!wcschr` at `0x18001b6a8`

## pseudocode

```c
HRESULT __stdcall PathCchSkipRoot(PCWSTR pszPath, PCWSTR *ppszRootEnd)
{
  wchar_t *v4; // rax
  wchar_t *v5; // rbx
  wchar_t *v6; // rsi
  wchar_t *v7; // rax
  const WCHAR *v8; // rbx
  __int64 v9; // rax
  __int64 v10; // rax
  WCHAR v11; // bp
  __int64 v12; // rax
  bool v13; // al
  PCWSTR v14; // rsi
  __int64 v15; // rbx

  if ( pszPath && *pszPath && ppszRootEnd )
  {
    *ppszRootEnd = 0;
    if ( (unsigned int)PathIsUnc2((unsigned __int16 *)pszPath) )
    {
      v4 = wcschr(0, 0x5Cu);
      v5 = v4;
      if ( v4 )
      {
        v6 = v4 + 1;
        v7 = wcschr(v4 + 1, 0x5Cu);
        if ( v7 )
        {
          v8 = v7 + 1;
          if ( v7 == v6 )
            v8 = v7;
        }
        else
        {
          v9 = -1;
          do
            ++v9;
          while ( v5[v9] );
          v8 = &v5[v9];
        }
      }
      else
      {
        v10 = -1;
        do
          ++v10;
        while ( *(_WORD *)(2 * v10) );
        v8 = (const WCHAR *)(2 * v10);
      }
      goto LABEL_32;
    }
    v11 = *pszPath;
    if ( *pszPath == 92 && pszPath[1] != 92 )
    {
      v8 = pszPath + 1;
LABEL_32:
      *ppszRootEnd = v8;
      return 0;
    }
    if ( PathIsVolumeGUIDWorker(pszPath) )
    {
      v12 = 49;
      if ( pszPath[48] != 92 )
        v12 = 48;
      v8 = &pszPath[v12];
      goto LABEL_32;
    }
    v13 = IsExtendedLengthDosDevicePath(pszPath);
    if ( v13 )
      v11 = pszPath[4];
    v14 = pszPath + 4;
    if ( !v13 )
      v14 = pszPath;
    if ( iswalpha(v11) && v14[1] == 58 )
    {
      v15 = 3;
      if ( v14[2] != 92 )
        v15 = 2;
      v8 = &v14[v15];
      goto LABEL_32;
    }
  }
  return -2147024809;
}

```

## disassembly

```asm
0x18001b634  push    rbx
0x18001b636  push    rbp
0x18001b637  push    rsi
0x18001b638  push    rdi
0x18001b639  push    r14
0x18001b63b  push    r15
0x18001b63d  sub     rsp, 28h
0x18001b641  xor     r15d, r15d
0x18001b644  mov     r14, rdx
0x18001b647  mov     [rsp+58h+Str], r15
0x18001b64c  mov     rbx, rcx
0x18001b64f  test    rcx, rcx
0x18001b652  jz      loc_18001B769
0x18001b658  cmp     [rcx], r15w
0x18001b65c  jz      loc_18001B769
0x18001b662  test    rdx, rdx
0x18001b665  jz      loc_18001B769
0x18001b66b  mov     [rdx], r15
0x18001b66e  lea     r8, IsBackslash
0x18001b675  lea     rdx, [rsp+58h+Str]
0x18001b67a  call    PathIsUnc2
0x18001b67f  lea     edi, [r15+5Ch]
0x18001b683  test    eax, eax
0x18001b685  jz      short loc_18001B6EE
0x18001b687  mov     rsi, [rsp+58h+Str]
0x18001b68c  mov     edx, edi; Ch
0x18001b68e  mov     rcx, rsi; Str
0x18001b691  call    cs:__imp_wcschr
0x18001b697  mov     rbx, rax
0x18001b69a  test    rax, rax
0x18001b69d  jz      short loc_18001B6DA
0x18001b69f  lea     rsi, [rax+2]
0x18001b6a3  mov     edx, edi; Ch
0x18001b6a5  mov     rcx, rsi; Str
0x18001b6a8  call    cs:__imp_wcschr
0x18001b6ae  test    rax, rax
0x18001b6b1  jz      short loc_18001B6C3
0x18001b6b3  cmp     rax, rsi
0x18001b6b6  lea     rbx, [rax+2]
0x18001b6ba  cmovz   rbx, rax
0x18001b6be  jmp     loc_18001B762
0x18001b6c3  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001b6c7  inc     rax
0x18001b6ca  cmp     [rbx+rax*2], r15w
0x18001b6cf  jnz     short loc_18001B6C7
0x18001b6d1  lea     rbx, [rbx+rax*2]
0x18001b6d5  jmp     loc_18001B762
0x18001b6da  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001b6de  inc     rax
0x18001b6e1  cmp     [rsi+rax*2], r15w
0x18001b6e6  jnz     short loc_18001B6DE
0x18001b6e8  lea     rbx, [rsi+rax*2]
0x18001b6ec  jmp     short loc_18001B762
0x18001b6ee  movzx   ebp, word ptr [rbx]
0x18001b6f1  cmp     bp, di
0x18001b6f4  jnz     short loc_18001B702
0x18001b6f6  cmp     [rbx+2], di
0x18001b6fa  jz      short loc_18001B702
0x18001b6fc  add     rbx, 2
0x18001b700  jmp     short loc_18001B762
0x18001b702  mov     rcx, rbx; unsigned __int16 *
0x18001b705  call    ?PathIsVolumeGUIDWorker@@YA_NPEBG@Z; PathIsVolumeGUIDWorker(ushort const *)
0x18001b70a  test    al, al
0x18001b70c  jz      short loc_18001B722
0x18001b70e  cmp     [rbx+60h], di
0x18001b712  mov     eax, 62h ; 'b'
0x18001b717  lea     ecx, [rax-2]
0x18001b71a  cmovnz  eax, ecx
0x18001b71d  add     rbx, rax
0x18001b720  jmp     short loc_18001B762
0x18001b722  mov     rcx, rbx; unsigned __int16 *
0x18001b725  call    ?IsExtendedLengthDosDevicePath@@YA_NPEBG@Z; IsExtendedLengthDosDevicePath(ushort const *)
0x18001b72a  test    al, al
0x18001b72c  jz      short loc_18001B732
0x18001b72e  movzx   ebp, word ptr [rbx+8]
0x18001b732  test    al, al
0x18001b734  lea     rsi, [rbx+8]
0x18001b738  movzx   ecx, bp; C
0x18001b73b  cmovz   rsi, rbx
0x18001b73f  call    cs:__imp_iswalpha
0x18001b745  test    eax, eax
0x18001b747  jz      short loc_18001B769
0x18001b749  cmp     word ptr [rsi+2], 3Ah ; ':'
0x18001b74e  jnz     short loc_18001B769
0x18001b750  cmp     [rsi+4], di
0x18001b754  mov     ebx, 6
0x18001b759  lea     eax, [rbx-2]
0x18001b75c  cmovnz  ebx, eax
0x18001b75f  add     rbx, rsi
0x18001b762  mov     [r14], rbx
0x18001b765  xor     eax, eax
0x18001b767  jmp     short loc_18001B76E
0x18001b769  mov     eax, 80070057h
0x18001b76e  add     rsp, 28h
0x18001b772  pop     r15
0x18001b774  pop     r14
0x18001b776  pop     rdi
0x18001b777  pop     rsi
0x18001b778  pop     rbp
0x18001b779  pop     rbx
0x18001b77a  retn
```
