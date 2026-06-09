# PathCchRemoveFileSpec(x,x)

- ea: `0x40b958`
- end: `0x40b9df`
- name: `_PathCchRemoveFileSpec@8`
- size: `135`
- prototype: `HRESULT __stdcall(PWSTR pszPath, size_t cchPath)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, reparse_path`

## callers

- `0x408a2f`

## callees

- `0x40b7ce`
- `0x40b825`
- `0x40b958`

## import_xrefs

- `msvcrt!wcschr` at `0x40b9a0`
- `msvcrt!wcschr` at `0x40b9a0`

## pseudocode

```c
HRESULT __stdcall PathCchRemoveFileSpec(PWSTR pszPath, size_t cchPath)
{
  unsigned int v2; // edx
  const wchar_t *v3; // ecx
  const WCHAR *v4; // edi
  const wchar_t *v5; // ebx
  unsigned int v6; // esi
  HRESULT v7; // eax
  const wchar_t *v8; // edi
  wchar_t *i; // eax
  WCHAR *v11; // [esp-8h] [ebp-14h]
  PWSTR *v12; // [esp-4h] [ebp-10h]
  PCWSTR *v13; // [esp+0h] [ebp-Ch]
  size_t *v14; // [esp+0h] [ebp-Ch]
  const wchar_t *v15; // [esp+8h] [ebp-4h]

  v5 = v3;
  v6 = v2;
  if ( !v3 || !v2 || v2 > 0x8000 )
    return -2147024809;
  v7 = PathCchSkipRoot(v4, v13);
  v8 = v15;
  if ( v7 < 0 )
    v8 = v5;
  if ( v8 >= &v5[v6] )
    return -2147024809;
  for ( i = _wcschr(v8, 0x5Cu); i; i = _wcschr(i + 1, 0x5Cu) )
  {
    v8 = i;
    if ( i >= &v5[v6] )
      return -2147024809;
  }
  if ( !*v8 )
    return PathCchRemoveBackslashEx(v11, (size_t)v11, v12, v14);
  *v8 = 0;
  PathCchRemoveBackslashEx(v11, (size_t)v11, v12, v14);
  return 0;
}

```

## disassembly

```asm
0x40b958  mov     edi, edi
0x40b95a  push    ebp
0x40b95b  mov     ebp, esp
0x40b95d  push    ecx
0x40b95e  push    ebx
0x40b95f  mov     ebx, ecx
0x40b961  push    esi; ppszRootEnd
0x40b962  mov     esi, edx
0x40b964  test    ebx, ebx
0x40b966  jz      short loc_40B9D6
0x40b968  test    esi, esi
0x40b96a  jz      short loc_40B9D6
0x40b96c  cmp     esi, 8000h
0x40b972  ja      short loc_40B9D6
0x40b974  push    edi; ppszEnd
0x40b975  lea     edx, [ebp+var_4]
0x40b978  call    _PathCchSkipRoot@8; PathCchSkipRoot(x,x)
0x40b97d  mov     edi, [ebp+var_4]
0x40b980  test    eax, eax
0x40b982  lea     eax, [ebx+esi*2]
0x40b985  cmovs   edi, ebx
0x40b988  cmp     edi, eax
0x40b98a  jnb     short loc_40B9C0
0x40b98c  push    5Ch ; '\'
0x40b98e  push    edi
0x40b98f  jmp     short loc_40B9A0
0x40b991  lea     ecx, [ebx+esi*2]
0x40b994  mov     edi, eax
0x40b996  cmp     eax, ecx
0x40b998  jnb     short loc_40B9C0
0x40b99a  push    5Ch ; '\'; Ch
0x40b99c  add     eax, 2
0x40b99f  push    eax; Str
0x40b9a0  call    ds:__imp__wcschr
0x40b9a6  pop     ecx
0x40b9a7  pop     ecx
0x40b9a8  test    eax, eax
0x40b9aa  jnz     short loc_40B991
0x40b9ac  push    ecx; cchPath
0x40b9ad  xor     eax, eax
0x40b9af  mov     edx, esi
0x40b9b1  push    ecx; pszPath
0x40b9b2  mov     ecx, ebx
0x40b9b4  cmp     [edi], ax
0x40b9b7  jnz     short loc_40B9C7
0x40b9b9  call    _PathCchRemoveBackslashEx@16; PathCchRemoveBackslashEx(x,x,x,x)
0x40b9be  jmp     short loc_40B9D3
0x40b9c0  mov     eax, 80070057h
0x40b9c5  jmp     short loc_40B9D3
0x40b9c7  xor     eax, eax
0x40b9c9  mov     [edi], ax
0x40b9cc  call    _PathCchRemoveBackslashEx@16; PathCchRemoveBackslashEx(x,x,x,x)
0x40b9d1  xor     eax, eax
0x40b9d3  pop     edi
0x40b9d4  jmp     short loc_40B9DB
0x40b9d6  mov     eax, 80070057h
0x40b9db  pop     esi
0x40b9dc  pop     ebx
0x40b9dd  leave
0x40b9de  retn
```
