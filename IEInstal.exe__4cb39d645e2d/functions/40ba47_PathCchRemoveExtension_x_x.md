# PathCchRemoveExtension(x,x)

- ea: `0x40ba47`
- end: `0x40ba82`
- name: `_PathCchRemoveExtension@8`
- size: `59`
- prototype: `HRESULT __stdcall(PWSTR pszPath, size_t cchPath)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, loader_planting`

## callers

- `0x407eab`

## callees

- `0x40b9e5`
- `0x40ba47`

## pseudocode

```c
HRESULT __stdcall PathCchRemoveExtension(PWSTR pszPath, size_t cchPath)
{
  int v2; // ecx
  size_t v3; // esi
  HRESULT result; // eax
  WCHAR v5[2]; // [esp+0h] [ebp-4h] BYREF

  if ( !v2 )
    return -2147024809;
  result = PathCchFindExtension(v5, v3, 0);
  if ( result >= 0 )
  {
    if ( **(_WORD **)v5 )
    {
      **(_WORD **)v5 = 0;
      return 0;
    }
    else
    {
      return 1;
    }
  }
  return result;
}

```

## disassembly

```asm
0x40ba47  mov     edi, edi
0x40ba49  push    ebp
0x40ba4a  mov     ebp, esp
0x40ba4c  push    ecx; ppszExt
0x40ba4d  test    ecx, ecx
0x40ba4f  jz      short loc_40BA7B
0x40ba51  push    esi; cchPath
0x40ba52  lea     eax, [ebp+var_4]
0x40ba55  xor     esi, esi
0x40ba57  push    eax; pszPath
0x40ba58  mov     dword ptr [ebp+var_4], esi
0x40ba5b  call    _PathCchFindExtension@12; PathCchFindExtension(x,x,x)
0x40ba60  test    eax, eax
0x40ba62  js      short loc_40BA78
0x40ba64  mov     eax, dword ptr [ebp+var_4]
0x40ba67  cmp     [eax], si
0x40ba6a  jnz     short loc_40BA71
0x40ba6c  xor     eax, eax
0x40ba6e  inc     eax
0x40ba6f  jmp     short loc_40BA78
0x40ba71  xor     ecx, ecx
0x40ba73  mov     [eax], cx
0x40ba76  mov     eax, esi
0x40ba78  pop     esi
0x40ba79  leave
0x40ba7a  retn
0x40ba7b  mov     eax, 80070057h
0x40ba80  leave
0x40ba81  retn
```
