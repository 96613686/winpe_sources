# GetWininitSize(void)

- ea: `0x1800078d8`
- end: `0x180007960`
- name: `?GetWininitSize@@YAKXZ`
- size: `136`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x1800080f0`

## callees

- `0x1800078d8`
- `0x180008c88`
- `0x18001a688`
- `0x18001b294`
- `0x18001b980`

## import_xrefs

- `KERNEL32!GetWindowsDirectoryW` at `0x1800078ff`
- `KERNEL32!GetWindowsDirectoryW` at `0x1800078ff`

## pseudocode

```c
__int64 GetWininitSize(void)
{
  unsigned int v0; // ebx
  ULONG v2; // [rsp+20h] [rbp-238h]
  WCHAR Buffer[264]; // [rsp+30h] [rbp-228h] BYREF

  v0 = 0;
  if ( GetWindowsDirectoryW(Buffer, 0x104u) )
  {
    PathIsUnc2(L"wininit.ini");
    PathCchCombineEx(Buffer, 0x104u, Buffer, L"wininit.ini", v2);
    return MyFileSize(Buffer);
  }
  return v0;
}

```

## disassembly

```asm
0x1800078d8  push    rbx
0x1800078da  sub     rsp, 250h
0x1800078e1  mov     rax, cs:__security_cookie
0x1800078e8  xor     rax, rsp
0x1800078eb  mov     [rsp+258h+var_18], rax
0x1800078f3  mov     edx, 104h; uSize
0x1800078f8  lea     rcx, [rsp+258h+Buffer]; lpBuffer
0x1800078fd  xor     ebx, ebx
0x1800078ff  call    cs:__imp_GetWindowsDirectoryW
0x180007905  test    eax, eax
0x180007907  jz      short loc_180007945
0x180007909  lea     r8, IsBackslash
0x180007910  xor     edx, edx
0x180007912  lea     rcx, pszMore; "wininit.ini"
0x180007919  call    PathIsUnc2
0x18000791e  lea     r9, pszMore; "wininit.ini"
0x180007925  mov     edx, 104h; cchPathOut
0x18000792a  lea     r8, [rsp+258h+Buffer]; pszPathIn
0x18000792f  lea     rcx, [rsp+258h+Buffer]; pszPathOut
0x180007934  call    PathCchCombineEx
0x180007939  lea     rcx, [rsp+258h+Buffer]; unsigned __int16 *
0x18000793e  call    ?MyFileSize@@YAKPEBG@Z; MyFileSize(ushort const *)
0x180007943  mov     ebx, eax
0x180007945  mov     eax, ebx
0x180007947  mov     rcx, [rsp+258h+var_18]
0x18000794f  xor     rcx, rsp; StackCookie
0x180007952  call    __security_check_cookie
0x180007957  add     rsp, 250h
0x18000795e  pop     rbx
0x18000795f  retn
```
