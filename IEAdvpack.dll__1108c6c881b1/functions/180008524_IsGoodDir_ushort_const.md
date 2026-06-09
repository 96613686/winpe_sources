# IsGoodDir(ushort const *)

- ea: `0x180008524`
- end: `0x180008614`
- name: `?IsGoodDir@@YAHPEBG@Z`
- size: `240`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `4`
- callee_count: `5`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x180002928`
- `0x1800056d0`
- `0x1800063c4`
- `0x180009580`

## callees

- `0x1800022bc`
- `0x180008524`
- `0x18001a688`
- `0x18001b294`
- `0x18001b980`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x1800085c5`
- `KERNEL32!CreateFileW` at `0x1800085c5`
- `KERNEL32!CloseHandle` at `0x1800085d4`
- `KERNEL32!CloseHandle` at `0x1800085d4`
- `KERNEL32!DeleteFileW` at `0x18000859b`
- `KERNEL32!DeleteFileW` at `0x18000859b`
- `KERNEL32!GetFileAttributesW` at `0x1800085dd`
- `KERNEL32!GetFileAttributesW` at `0x1800085dd`

## pseudocode

```c
__int64 __fastcall IsGoodDir(const unsigned __int16 *a1)
{
  unsigned int v2; // ebx
  HANDLE FileW; // rax
  DWORD FileAttributesW; // eax
  ULONG dwCreationDisposition; // [rsp+20h] [rbp-248h]
  WCHAR pszPathOut[264]; // [rsp+40h] [rbp-228h] BYREF

  v2 = 0;
  if ( StringCchCopyW(pszPathOut, 0x104u, a1) >= 0 )
  {
    PathIsUnc2(L"TMP4352$.TMP");
    PathCchCombineEx(pszPathOut, 0x104u, pszPathOut, L"TMP4352$.TMP", dwCreationDisposition);
    DeleteFileW(pszPathOut);
    FileW = CreateFileW(pszPathOut, 0x40000000u, 0, 0, 1u, 0x4000100u, 0);
    if ( FileW != (HANDLE)-1LL )
    {
      CloseHandle(FileW);
      FileAttributesW = GetFileAttributesW(a1);
      if ( FileAttributesW != -1 )
        return (FileAttributesW & 0x10) != 0;
    }
  }
  return v2;
}

```

## disassembly

```asm
0x180008524  mov     [rsp+arg_8], rbx
0x180008529  mov     [rsp+arg_10], rsi
0x18000852e  push    rdi
0x18000852f  sub     rsp, 260h
0x180008536  mov     rax, cs:__security_cookie
0x18000853d  xor     rax, rsp
0x180008540  mov     [rsp+268h+var_18], rax
0x180008548  mov     rdi, rcx
0x18000854b  mov     r8, rcx; unsigned __int16 *
0x18000854e  mov     esi, 104h
0x180008553  lea     rcx, [rsp+268h+pszPathOut]; unsigned __int16 *
0x180008558  mov     edx, esi; unsigned __int64
0x18000855a  xor     ebx, ebx
0x18000855c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180008561  test    eax, eax
0x180008563  js      loc_1800085ED
0x180008569  lea     r8, IsBackslash
0x180008570  xor     edx, edx
0x180008572  lea     rcx, aTmp4352Tmp; "TMP4352$.TMP"
0x180008579  call    PathIsUnc2
0x18000857e  lea     r9, aTmp4352Tmp; "TMP4352$.TMP"
0x180008585  mov     edx, esi; cchPathOut
0x180008587  lea     r8, [rsp+268h+pszPathOut]; pszPathIn
0x18000858c  lea     rcx, [rsp+268h+pszPathOut]; pszPathOut
0x180008591  call    PathCchCombineEx
0x180008596  lea     rcx, [rsp+268h+pszPathOut]; lpFileName
0x18000859b  call    cs:__imp_DeleteFileW
0x1800085a1  mov     [rsp+268h+hTemplateFile], rbx; hTemplateFile
0x1800085a6  lea     esi, [rbx+1]
0x1800085a9  mov     [rsp+268h+dwFlagsAndAttributes], 4000100h; dwFlagsAndAttributes
0x1800085b1  lea     rcx, [rsp+268h+pszPathOut]; lpFileName
0x1800085b6  xor     r9d, r9d; lpSecurityAttributes
0x1800085b9  mov     [rsp+268h+dwCreationDisposition], esi; dwCreationDisposition
0x1800085bd  xor     r8d, r8d; dwShareMode
0x1800085c0  mov     edx, 40000000h; dwDesiredAccess
0x1800085c5  call    cs:__imp_CreateFileW
0x1800085cb  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800085cf  jz      short loc_1800085ED
0x1800085d1  mov     rcx, rax; hObject
0x1800085d4  call    cs:__imp_CloseHandle
0x1800085da  mov     rcx, rdi; lpFileName
0x1800085dd  call    cs:__imp_GetFileAttributesW
0x1800085e3  cmp     eax, 0FFFFFFFFh
0x1800085e6  jz      short loc_1800085ED
0x1800085e8  test    al, 10h
0x1800085ea  cmovnz  ebx, esi
0x1800085ed  mov     eax, ebx
0x1800085ef  mov     rcx, [rsp+268h+var_18]
0x1800085f7  xor     rcx, rsp; StackCookie
0x1800085fa  call    __security_check_cookie
0x1800085ff  lea     r11, [rsp+268h+var_8]
0x180008607  mov     rbx, [r11+18h]
0x18000860b  mov     rsi, [r11+20h]
0x18000860f  mov     rsp, r11
0x180008612  pop     rdi
0x180008613  retn
```
