# __std_fs_convert_wide_to_narrow_replace_chars(x,x,x,x,x)

- ea: `0x40c4e5`
- end: `0x40c554`
- name: `___std_fs_convert_wide_to_narrow_replace_chars@20`
- size: `111`
- prototype: `int __stdcall(UINT CodePage, LPCWCH lpWideCharStr, int cchWideChar, LPSTR lpMultiByteStr, int cbMultiByte)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x40a1cd`

## callees

- `0x40c4e5`

## import_xrefs

- `KERNEL32!GetLastError` at `0x40c50e`
- `KERNEL32!GetLastError` at `0x40c540`
- `KERNEL32!GetLastError` at `0x40c50e`
- `KERNEL32!GetLastError` at `0x40c540`
- `KERNEL32!WideCharToMultiByte` at `0x40c502`
- `KERNEL32!WideCharToMultiByte` at `0x40c534`
- `KERNEL32!WideCharToMultiByte` at `0x40c502`
- `KERNEL32!WideCharToMultiByte` at `0x40c534`

## pseudocode

```c
int __stdcall __std_fs_convert_wide_to_narrow_replace_chars(
        UINT CodePage,
        LPCWCH lpWideCharStr,
        int cchWideChar,
        LPSTR lpMultiByteStr,
        int cbMultiByte)
{
  int v5; // esi
  DWORD LastError; // edx

  v5 = WideCharToMultiByte(CodePage, 0x400u, lpWideCharStr, cchWideChar, lpMultiByteStr, cbMultiByte, 0, 0);
  if ( v5 )
    LastError = 0;
  else
    LastError = GetLastError();
  if ( LastError == 1004 )
  {
    v5 = WideCharToMultiByte(CodePage, 0, lpWideCharStr, cchWideChar, lpMultiByteStr, cbMultiByte, 0, 0);
    if ( !v5 )
      GetLastError();
  }
  return v5;
}

```

## disassembly

```asm
0x40c4e5  push    ebp
0x40c4e6  mov     ebp, esp
0x40c4e8  push    esi
0x40c4e9  push    edi
0x40c4ea  xor     edi, edi
0x40c4ec  push    edi; lpUsedDefaultChar
0x40c4ed  push    edi; lpDefaultChar
0x40c4ee  push    [ebp+cbMultiByte]; cbMultiByte
0x40c4f1  push    [ebp+lpMultiByteStr]; lpMultiByteStr
0x40c4f4  push    [ebp+cchWideChar]; cchWideChar
0x40c4f7  push    [ebp+lpWideCharStr]; lpWideCharStr
0x40c4fa  push    400h; dwFlags
0x40c4ff  push    [ebp+CodePage]; CodePage
0x40c502  call    ds:WideCharToMultiByte
0x40c508  mov     esi, eax
0x40c50a  test    esi, esi
0x40c50c  jnz     short loc_40C518
0x40c50e  call    ds:GetLastError
0x40c514  mov     edx, eax
0x40c516  jmp     short loc_40C51A
0x40c518  mov     edx, edi
0x40c51a  cmp     edx, 3ECh
0x40c520  jnz     short loc_40C54C
0x40c522  push    edi; lpUsedDefaultChar
0x40c523  push    edi; lpDefaultChar
0x40c524  push    [ebp+cbMultiByte]; cbMultiByte
0x40c527  push    [ebp+lpMultiByteStr]; lpMultiByteStr
0x40c52a  push    [ebp+cchWideChar]; cchWideChar
0x40c52d  push    [ebp+lpWideCharStr]; lpWideCharStr
0x40c530  push    edi; dwFlags
0x40c531  push    [ebp+CodePage]; CodePage
0x40c534  call    ds:WideCharToMultiByte
0x40c53a  mov     esi, eax
0x40c53c  test    esi, esi
0x40c53e  jnz     short loc_40C54A
0x40c540  call    ds:GetLastError
0x40c546  mov     edx, eax
0x40c548  jmp     short loc_40C54C
0x40c54a  mov     edx, edi
0x40c54c  pop     edi
0x40c54d  mov     eax, esi
0x40c54f  pop     esi
0x40c550  pop     ebp
0x40c551  retn    14h
```
