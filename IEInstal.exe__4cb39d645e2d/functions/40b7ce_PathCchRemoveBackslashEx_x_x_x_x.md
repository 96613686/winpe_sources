# PathCchRemoveBackslashEx(x,x,x,x)

- ea: `0x40b7ce`
- end: `0x40b81f`
- name: `_PathCchRemoveBackslashEx@16`
- size: `81`
- prototype: `HRESULT __stdcall(PWSTR pszPath, size_t cchPath, PWSTR *ppszEnd, size_t *pcchRemaining)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path`

## callers

- `0x40b958`

## callees

- `0x40b6d3`
- `0x40b7ce`

## pseudocode

```c
HRESULT __stdcall PathCchRemoveBackslashEx(PWSTR pszPath, size_t cchPath, PWSTR *ppszEnd, size_t *pcchRemaining)
{
  unsigned int v4; // edx
  _WORD *v5; // ecx
  _WORD *v6; // edi
  _WORD *v7; // esi
  _WORD *v8; // ecx
  unsigned int v10; // esi
  HRESULT v12; // ebx
  const WCHAR *v13; // [esp+0h] [ebp-Ch]

  v6 = v5;
  v7 = v5;
  v8 = v5 + 1;
  while ( *v7++ )
    ;
  v10 = v7 - v8;
  if ( v10 >= v4 )
    return -2147024809;
  v12 = 1;
  if ( v10 && v6[v10 - 1] == 92 && !PathCchIsRoot(v13) )
  {
    v6[v10 - 1] = 0;
    return 0;
  }
  return v12;
}

```

## disassembly

```asm
0x40b7ce  mov     edi, edi
0x40b7d0  push    ebx
0x40b7d1  push    esi
0x40b7d2  push    edi; pszPath
0x40b7d3  mov     edi, ecx
0x40b7d5  xor     ebx, ebx
0x40b7d7  mov     esi, edi
0x40b7d9  lea     ecx, [esi+2]
0x40b7dc  mov     ax, [esi]
0x40b7df  add     esi, 2
0x40b7e2  cmp     ax, bx
0x40b7e5  jnz     short loc_40B7DC
0x40b7e7  sub     esi, ecx
0x40b7e9  sar     esi, 1
0x40b7eb  cmp     esi, edx
0x40b7ed  jb      short loc_40B7F6
0x40b7ef  mov     eax, 80070057h
0x40b7f4  jmp     short loc_40B819
0x40b7f6  xor     ebx, ebx
0x40b7f8  inc     ebx
0x40b7f9  test    esi, esi
0x40b7fb  jz      short loc_40B817
0x40b7fd  cmp     word ptr [edi+esi*2-2], 5Ch ; '\'
0x40b803  jnz     short loc_40B817
0x40b805  mov     ecx, edi
0x40b807  call    _PathCchIsRoot@4; PathCchIsRoot(x)
0x40b80c  test    eax, eax
0x40b80e  jnz     short loc_40B817
0x40b810  mov     [edi+esi*2-2], ax
0x40b815  xor     ebx, ebx
0x40b817  mov     eax, ebx
0x40b819  pop     edi
0x40b81a  pop     esi
0x40b81b  pop     ebx
0x40b81c  retn    8
```
