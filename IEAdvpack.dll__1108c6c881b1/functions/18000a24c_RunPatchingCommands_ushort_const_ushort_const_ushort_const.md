# RunPatchingCommands(ushort const *,ushort const *,ushort const *)

- ea: `0x18000a24c`
- end: `0x18000a41f`
- name: `?RunPatchingCommands@@YAJPEBG00@Z`
- size: `467`
- prototype: `__int64 __fastcall(const unsigned __int16 *, LPCWSTR lpAppName, LPCWCH lpWideCharStr)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180004880`

## callees

- `0x180006d24`
- `0x180007454`
- `0x18000a24c`
- `0x180015c74`
- `0x180017314`
- `0x18001b980`
- `0x18001c010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000a2fc`
- `KERNEL32!GetLastError` at `0x18000a2fc`
- `KERNEL32!LocalFree` at `0x18000a3df`
- `KERNEL32!LocalFree` at `0x18000a3e8`
- `KERNEL32!LocalFree` at `0x18000a3df`
- `KERNEL32!LocalFree` at `0x18000a3e8`
- `KERNEL32!FreeLibrary` at `0x18000a3f1`
- `KERNEL32!FreeLibrary` at `0x18000a3f1`
- `KERNEL32!GetProcAddress` at `0x18000a35a`
- `KERNEL32!GetProcAddress` at `0x18000a35a`
- `KERNEL32!LoadLibraryW` at `0x18000a2ee`
- `KERNEL32!LoadLibraryW` at `0x18000a2ee`
- `SHLWAPI!__imp_SHUnicodeToAnsi` at `0x18000a34c`
- `SHLWAPI!__imp_SHUnicodeToAnsi` at `0x18000a34c`

## string_xrefs

- `0x18000a2a6`: `LoadAdvpackExtension`

## pseudocode

```c
__int64 __fastcall RunPatchingCommands(const unsigned __int16 *a1, LPCWSTR lpAppName, LPCWCH lpWideCharStr)
{
  unsigned int v6; // ebx
  HMODULE LibraryW; // rsi
  signed int LastError; // eax
  FARPROC ProcAddress; // rbx
  CHAR pszDst[272]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR LibFileName[264]; // [rsp+160h] [rbp+60h] BYREF
  WCHAR pwszSrc[264]; // [rsp+370h] [rbp+270h] BYREF
  unsigned __int16 v14[512]; // [rsp+580h] [rbp+480h] BYREF

  v6 = 0;
  if ( !(unsigned int)GetTranslatedInt(a1, lpAppName, L"Patching", 0)
    || (int)GetTranslatedString(a1, lpAppName, L"LoadAdvpackExtension", v14, 0x200u, 0) < 0
    || !(unsigned int)GetFieldString(v14, 0, LibFileName, 260) )
  {
    return v6;
  }
  LibraryW = LoadLibraryW(LibFileName);
  if ( LibraryW )
  {
    if ( (unsigned int)GetFieldString(v14, 1, pwszSrc, 260) )
    {
      SHUnicodeToAnsi(pwszSrc, pszDst, 260);
      ProcAddress = GetProcAddress(LibraryW, pszDst);
      if ( !ProcAddress )
        goto LABEL_5;
      if ( (int)ThunkToAnsi(lpAppName) < 0 || (int)ThunkToAnsi(lpWideCharStr) < 0 )
        v6 = -2147024882;
      else
        v6 = ((__int64 (__fastcall *)(HINF, HWND, _QWORD, _QWORD, _QWORD, _QWORD))ProcAddress)(
               InfHandle,
               hWnd,
               (unsigned __int16)word_1800257D2,
               0,
               0,
               0);
      LocalFree(0);
      LocalFree(0);
    }
    FreeLibrary(LibraryW);
    return v6;
  }
LABEL_5:
  LastError = GetLastError();
  v6 = LastError;
  if ( LastError > 0 )
    return (unsigned __int16)LastError | 0x80070000;
  return v6;
}

```

## disassembly

```asm
0x18000a24c  mov     [rsp-8+arg_18], rbx
0x18000a251  push    rbp
0x18000a252  push    rsi
0x18000a253  push    rdi
0x18000a254  push    r14
0x18000a256  push    r15
0x18000a258  lea     rbp, [rsp-890h]
0x18000a260  sub     rsp, 990h
0x18000a267  mov     rax, cs:__security_cookie
0x18000a26e  xor     rax, rsp
0x18000a271  mov     [rbp+8B0h+var_30], rax
0x18000a278  mov     r15, r8
0x18000a27b  xor     r9d, r9d; nDefault
0x18000a27e  lea     r8, aPatching; "Patching"
0x18000a285  mov     r14, rdx
0x18000a288  mov     rdi, rcx
0x18000a28b  xor     ebx, ebx
0x18000a28d  call    ?GetTranslatedInt@@YAKPEBG00K@Z; GetTranslatedInt(ushort const *,ushort const *,ushort const *,ulong)
0x18000a292  test    eax, eax
0x18000a294  jz      loc_18000A3F7
0x18000a29a  mov     [rsp+9B0h+var_988], rbx; unsigned int *
0x18000a29f  lea     r9, [rbp+8B0h+var_430]; unsigned __int16 *
0x18000a2a6  lea     r8, aLoadadvpackext; "LoadAdvpackExtension"
0x18000a2ad  mov     [rsp+9B0h+var_990], 200h; unsigned int
0x18000a2b5  mov     rdx, r14; lpAppName
0x18000a2b8  mov     rcx, rdi; unsigned __int16 *
0x18000a2bb  call    ?GetTranslatedString@@YAJPEBG00PEAGKPEAK@Z; GetTranslatedString(ushort const *,ushort const *,ushort const *,ushort *,ulong,ulong *)
0x18000a2c0  test    eax, eax
0x18000a2c2  js      loc_18000A3F7
0x18000a2c8  mov     edi, 104h
0x18000a2cd  lea     r8, [rbp+8B0h+LibFileName]; unsigned __int16 *
0x18000a2d1  mov     r9d, edi; int
0x18000a2d4  lea     rcx, [rbp+8B0h+var_430]; unsigned __int16 *
0x18000a2db  xor     edx, edx; int
0x18000a2dd  call    ?GetFieldString@@YAHPEBGHPEAGH@Z; GetFieldString(ushort const *,int,ushort *,int)
0x18000a2e2  test    eax, eax
0x18000a2e4  jz      loc_18000A3F7
0x18000a2ea  lea     rcx, [rbp+8B0h+LibFileName]; lpLibFileName
0x18000a2ee  call    cs:__imp_LoadLibraryW
0x18000a2f4  mov     rsi, rax
0x18000a2f7  test    rax, rax
0x18000a2fa  jnz     short loc_18000A31A
0x18000a2fc  call    cs:__imp_GetLastError
0x18000a302  mov     ebx, eax
0x18000a304  test    eax, eax
0x18000a306  jle     loc_18000A3F7
0x18000a30c  movzx   ebx, ax
0x18000a30f  or      ebx, 80070000h
0x18000a315  jmp     loc_18000A3F7
0x18000a31a  mov     r9d, edi; int
0x18000a31d  lea     r8, [rbp+8B0h+pwszSrc]; unsigned __int16 *
0x18000a324  mov     edx, 1; int
0x18000a329  lea     rcx, [rbp+8B0h+var_430]; unsigned __int16 *
0x18000a330  call    ?GetFieldString@@YAHPEBGHPEAGH@Z; GetFieldString(ushort const *,int,ushort *,int)
0x18000a335  test    eax, eax
0x18000a337  jz      loc_18000A3EE
0x18000a33d  mov     r8d, edi; cchBuf
0x18000a340  lea     rdx, [rsp+9B0h+pszDst]; pszDst
0x18000a345  lea     rcx, [rbp+8B0h+pwszSrc]; pwszSrc
0x18000a34c  call    cs:__imp_SHUnicodeToAnsi
0x18000a352  lea     rdx, [rsp+9B0h+pszDst]; lpProcName
0x18000a357  mov     rcx, rsi; hModule
0x18000a35a  call    cs:__imp_GetProcAddress
0x18000a360  mov     rbx, rax
0x18000a363  test    rax, rax
0x18000a366  jz      short loc_18000A2FC
0x18000a368  xor     edi, edi
0x18000a36a  mov     [rsp+9B0h+hMem], 0
0x18000a373  lea     rdx, [rsp+9B0h+hMem]
0x18000a378  mov     [rsp+9B0h+var_970], rdi
0x18000a37d  mov     rcx, r14; lpWideCharStr
0x18000a380  call    ThunkToAnsi
0x18000a385  test    eax, eax
0x18000a387  js      short loc_18000A3D5
0x18000a389  lea     rdx, [rsp+9B0h+var_970]
0x18000a38e  mov     rcx, r15; lpWideCharStr
0x18000a391  call    ThunkToAnsi
0x18000a396  test    eax, eax
0x18000a398  js      short loc_18000A3D0
0x18000a39a  movzx   r8d, cs:word_1800257D2
0x18000a3a2  mov     rax, rbx
0x18000a3a5  mov     r9, [rsp+9B0h+hMem]
0x18000a3aa  mov     rdx, cs:hWnd
0x18000a3b1  mov     rcx, cs:InfHandle
0x18000a3b8  mov     [rsp+9B0h+var_988], rdi
0x18000a3bd  mov     rdi, [rsp+9B0h+var_970]
0x18000a3c2  mov     qword ptr [rsp+9B0h+var_990], rdi
0x18000a3c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a3cc  mov     ebx, eax
0x18000a3ce  jmp     short loc_18000A3DA
0x18000a3d0  mov     rdi, [rsp+9B0h+var_970]
0x18000a3d5  mov     ebx, 8007000Eh
0x18000a3da  mov     rcx, [rsp+9B0h+hMem]; hMem
0x18000a3df  call    cs:__imp_LocalFree
0x18000a3e5  mov     rcx, rdi; hMem
0x18000a3e8  call    cs:__imp_LocalFree
0x18000a3ee  mov     rcx, rsi; hLibModule
0x18000a3f1  call    cs:__imp_FreeLibrary
0x18000a3f7  mov     eax, ebx
0x18000a3f9  mov     rcx, [rbp+8B0h+var_30]
0x18000a400  xor     rcx, rsp; StackCookie
0x18000a403  call    __security_check_cookie
0x18000a408  mov     rbx, [rsp+9B0h+arg_18]
0x18000a410  add     rsp, 990h
0x18000a417  pop     r15
0x18000a419  pop     r14
0x18000a41b  pop     rdi
0x18000a41c  pop     rsi
0x18000a41d  pop     rbp
0x18000a41e  retn
```
