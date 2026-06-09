# SupportedFileTypes::IsSystemFolderOrParent(ushort const *)

- ea: `0x180072420`
- end: `0x1800724fe`
- name: `?IsSystemFolderOrParent@SupportedFileTypes@@SA_NPEBG@Z`
- size: `222`
- prototype: `bool __fastcall(LPCWCH lpString2)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18002ed38`

## callees

- `0x18003f800`
- `0x180072420`

## import_xrefs

- `KERNEL32!lstrlenW` at `0x180072453`
- `KERNEL32!lstrlenW` at `0x180072484`
- `KERNEL32!lstrlenW` at `0x180072453`
- `KERNEL32!lstrlenW` at `0x180072484`
- `KERNEL32!CompareStringOrdinal` at `0x18007249f`
- `KERNEL32!CompareStringOrdinal` at `0x1800724c9`
- `KERNEL32!CompareStringOrdinal` at `0x18007249f`
- `KERNEL32!CompareStringOrdinal` at `0x1800724c9`
- `KERNEL32!GetSystemDirectoryW` at `0x180072465`
- `KERNEL32!GetSystemDirectoryW` at `0x180072465`
- `SHLWAPI!PathIsRootW` at `0x180072475`
- `SHLWAPI!PathIsRootW` at `0x180072475`
- `SHLWAPI!PathRemoveFileSpecW` at `0x1800724af`
- `SHLWAPI!PathRemoveFileSpecW` at `0x1800724af`

## pseudocode

```c
char __fastcall SupportedFileTypes::IsSystemFolderOrParent(LPCWCH lpString2)
{
  int v3; // esi
  char v4; // di
  int v5; // eax
  WCHAR Buffer[264]; // [rsp+30h] [rbp-228h] BYREF

  if ( !lpString2 )
    return 0;
  v3 = lstrlenW(lpString2);
  GetSystemDirectoryW(Buffer, 0x104u);
  v4 = 1;
  while ( !PathIsRootW(Buffer) )
  {
    v5 = lstrlenW(Buffer);
    if ( v5 < v3 )
      break;
    if ( CompareStringOrdinal(Buffer, v5, lpString2, v5, 1) == 2 )
      return v4;
    PathRemoveFileSpecW(Buffer);
  }
  return CompareStringOrdinal(Buffer, -1, lpString2, -1, 1) == 2;
}

```

## disassembly

```asm
0x180072420  mov     [rsp+arg_8], rbx
0x180072425  mov     [rsp+arg_10], rsi
0x18007242a  push    rdi
0x18007242b  sub     rsp, 250h
0x180072432  mov     rax, cs:__security_cookie
0x180072439  xor     rax, rsp
0x18007243c  mov     [rsp+258h+var_18], rax
0x180072444  mov     rbx, rcx
0x180072447  test    rcx, rcx
0x18007244a  jnz     short loc_180072453
0x18007244c  xor     al, al
0x18007244e  jmp     loc_1800724D9
0x180072453  call    cs:__imp_lstrlenW
0x180072459  mov     edx, 104h; uSize
0x18007245e  lea     rcx, [rsp+258h+Buffer]; lpBuffer
0x180072463  mov     esi, eax
0x180072465  call    cs:__imp_GetSystemDirectoryW
0x18007246b  mov     edi, 1
0x180072470  lea     rcx, [rsp+258h+Buffer]; pszPath
0x180072475  call    cs:__imp_PathIsRootW
0x18007247b  test    eax, eax
0x18007247d  jnz     short loc_1800724B7
0x18007247f  lea     rcx, [rsp+258h+Buffer]; lpString
0x180072484  call    cs:__imp_lstrlenW
0x18007248a  cmp     eax, esi
0x18007248c  jl      short loc_1800724B7
0x18007248e  mov     r9d, eax; cchCount2
0x180072491  mov     [rsp+258h+bIgnoreCase], edi; bIgnoreCase
0x180072495  mov     r8, rbx; lpString2
0x180072498  lea     rcx, [rsp+258h+Buffer]; lpString1
0x18007249d  mov     edx, eax; cchCount1
0x18007249f  call    cs:__imp_CompareStringOrdinal
0x1800724a5  cmp     eax, 2
0x1800724a8  jz      short loc_1800724D6
0x1800724aa  lea     rcx, [rsp+258h+Buffer]; pszPath
0x1800724af  call    cs:__imp_PathRemoveFileSpecW
0x1800724b5  jmp     short loc_180072470
0x1800724b7  or      edx, 0FFFFFFFFh; cchCount1
0x1800724ba  mov     [rsp+258h+bIgnoreCase], edi; bIgnoreCase
0x1800724be  mov     r9d, edx; cchCount2
0x1800724c1  lea     rcx, [rsp+258h+Buffer]; lpString1
0x1800724c6  mov     r8, rbx; lpString2
0x1800724c9  call    cs:__imp_CompareStringOrdinal
0x1800724cf  cmp     eax, 2
0x1800724d2  setz    dil
0x1800724d6  mov     al, dil
0x1800724d9  mov     rcx, [rsp+258h+var_18]
0x1800724e1  xor     rcx, rsp; StackCookie
0x1800724e4  call    __security_check_cookie
0x1800724e9  lea     r11, [rsp+258h+var_8]
0x1800724f1  mov     rbx, [r11+18h]
0x1800724f5  mov     rsi, [r11+20h]
0x1800724f9  mov     rsp, r11
0x1800724fc  pop     rdi
0x1800724fd  retn
```
