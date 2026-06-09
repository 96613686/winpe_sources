# ShellUtil_GetSpecialFolderPath

- ea: `0x18000cb90`
- end: `0x18000cbec`
- name: `ShellUtil_GetSpecialFolderPath`
- size: `92`
- prototype: `__int64 __fastcall(int csidl, LPSTR pszPath)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x18000cb90`

## import_xrefs

- `SHELL32!SHGetPathFromIDListA` at `0x18000cbc6`
- `SHELL32!SHGetPathFromIDListA` at `0x18000cbc6`
- `SHELL32!SHGetSpecialFolderLocation` at `0x18000cbb4`
- `SHELL32!SHGetSpecialFolderLocation` at `0x18000cbb4`
- `SHELL32!__imp_SHFree` at `0x18000cbd9`
- `SHELL32!__imp_SHFree` at `0x18000cbd9`

## pseudocode

```c
__int64 __fastcall ShellUtil_GetSpecialFolderPath(int csidl, LPSTR pszPath)
{
  unsigned int v3; // ebx
  LPITEMIDLIST ppidl; // [rsp+40h] [rbp+18h] BYREF

  ppidl = 0;
  v3 = -2147467259;
  if ( !SHGetSpecialFolderLocation(0, csidl, &ppidl) )
  {
    v3 = !SHGetPathFromIDListA(ppidl, pszPath) ? 0x80004005 : 0;
    SHFree(ppidl);
  }
  return v3;
}

```

## disassembly

```asm
0x18000cb90  mov     [rsp+arg_0], rbx
0x18000cb95  push    rdi
0x18000cb96  sub     rsp, 20h
0x18000cb9a  mov     rdi, rdx
0x18000cb9d  mov     [rsp+28h+ppidl], 0
0x18000cba6  mov     edx, ecx; csidl
0x18000cba8  lea     r8, [rsp+28h+ppidl]; ppidl
0x18000cbad  xor     ecx, ecx; hwnd
0x18000cbaf  mov     ebx, 80004005h
0x18000cbb4  call    cs:__imp_SHGetSpecialFolderLocation
0x18000cbba  test    eax, eax
0x18000cbbc  jnz     short loc_18000CBDF
0x18000cbbe  mov     rcx, [rsp+28h+ppidl]; pidl
0x18000cbc3  mov     rdx, rdi; pszPath
0x18000cbc6  call    cs:__imp_SHGetPathFromIDListA
0x18000cbcc  neg     eax
0x18000cbce  sbb     ecx, ecx
0x18000cbd0  not     ecx
0x18000cbd2  and     ebx, ecx
0x18000cbd4  mov     rcx, [rsp+28h+ppidl]; pv
0x18000cbd9  call    cs:__imp_SHFree
0x18000cbdf  mov     eax, ebx
0x18000cbe1  mov     rbx, [rsp+28h+arg_0]
0x18000cbe6  add     rsp, 20h
0x18000cbea  pop     rdi
0x18000cbeb  retn
```
