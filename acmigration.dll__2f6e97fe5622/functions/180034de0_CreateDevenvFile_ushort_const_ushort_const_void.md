# CreateDevenvFile(ushort const *,ushort const *,void *)

- ea: `0x180034de0`
- end: `0x180034f3e`
- name: `?CreateDevenvFile@@YAJPEBG0PEAX@Z`
- size: `350`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, void *)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, reparse_path, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180001cf0`
- `0x180002874`
- `0x180034de0`
- `0x18004fec8`
- `0x1800543c0`

## import_xrefs

- `KERNEL32!DeleteFileW` at `0x180034e8b`
- `KERNEL32!DeleteFileW` at `0x180034e8b`
- `KERNEL32!CreateFileW` at `0x180034ebb`
- `KERNEL32!CreateFileW` at `0x180034ebb`
- `KERNEL32!GetFileAttributesW` at `0x180034e46`
- `KERNEL32!GetFileAttributesW` at `0x180034e46`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180034e1c`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180034e1c`
- `KERNEL32!CloseHandle` at `0x180034ef4`
- `KERNEL32!CloseHandle` at `0x180034ef4`
- `KERNEL32!GetLastError` at `0x180034e26`
- `KERNEL32!GetLastError` at `0x180034ec7`
- `KERNEL32!GetLastError` at `0x180034e26`
- `KERNEL32!GetLastError` at `0x180034ec7`

## string_xrefs

- `0x180034e6d`: `extensions.configurationchanged`
- `0x180034eda`: `CDevenvDotnetCacheRebuildShim::CreateCacheRebuildSentinelFile`

## pseudocode

```c
__int64 __fastcall CreateDevenvFile(const unsigned __int16 *a1, const unsigned __int16 *a2, void *a3)
{
  int v3; // edi
  __int64 i; // rbx
  DWORD LastError; // eax
  const char *v6; // r9
  __int64 v7; // r8
  size_t v8; // rdx
  HANDLE v9; // rax
  __int64 result; // rax
  __int64 dwCreationDisposition; // [rsp+20h] [rbp-458h]
  WCHAR pszPathOut; // [rsp+40h] [rbp-438h] BYREF
  _BYTE v13[526]; // [rsp+42h] [rbp-436h] BYREF
  WCHAR Dst[264]; // [rsp+250h] [rbp-228h] BYREF

  v3 = 0;
  for ( i = 0; i != 3; ++i )
  {
    if ( !ExpandEnvironmentStringsW(off_18006BD90[i], Dst, 0x103u) )
    {
      LastError = GetLastError();
      v6 = "Error expanding visual studio directoy. [%d]";
      v7 = 160;
LABEL_7:
      LODWORD(dwCreationDisposition) = LastError;
      AslLogCallPrintf(
        1,
        "CDevenvDotnetCacheRebuildShim::CreateCacheRebuildSentinelFile",
        v7,
        v6,
        dwCreationDisposition);
      continue;
    }
    if ( (GetFileAttributesW(Dst) & 0x10) == 0 )
      continue;
    pszPathOut = 0;
    memset_0(v13, 0, 0x206u);
    PathCchCombineEx(&pszPathOut, v8, Dst, L"extensions.configurationchanged", dwCreationDisposition);
    DeleteFileW(&pszPathOut);
    v9 = CreateFileW(&pszPathOut, 0x40000000u, 2u, 0, 2u, 0x200A0u, 0);
    if ( v9 == (HANDLE)-1LL )
    {
      LastError = GetLastError();
      v6 = "Error creating devenv sentinel file. Result [%d]";
      v7 = 187;
      goto LABEL_7;
    }
    CloseHandle(v9);
    ++v3;
  }
  result = v3 == 0;
  if ( !v3 )
    return (v3 == 0) | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180034de0  mov     [rsp+arg_0], rbx
0x180034de5  push    rdi
0x180034de6  sub     rsp, 470h
0x180034ded  mov     rax, cs:__security_cookie
0x180034df4  xor     rax, rsp
0x180034df7  mov     [rsp+478h+var_18], rax
0x180034dff  xor     edi, edi
0x180034e01  xor     ebx, ebx
0x180034e03  lea     rcx, off_18006BD90; "%programfiles(x86)%\\Microsoft Visual S"...
0x180034e0a  mov     r8d, 103h; nSize
0x180034e10  mov     rcx, [rcx+rbx*8]; lpSrc
0x180034e14  lea     rdx, [rsp+478h+Dst]; lpDst
0x180034e1c  call    cs:__imp_ExpandEnvironmentStringsW
0x180034e22  test    eax, eax
0x180034e24  jnz     short loc_180034E3E
0x180034e26  call    cs:__imp_GetLastError
0x180034e2c  lea     r9, aErrorExpanding_0; "Error expanding visual studio directoy."...
0x180034e33  mov     r8d, 0A0h
0x180034e39  jmp     loc_180034EDA
0x180034e3e  lea     rcx, [rsp+478h+Dst]; lpFileName
0x180034e46  call    cs:__imp_GetFileAttributesW
0x180034e4c  test    al, 10h
0x180034e4e  jz      loc_180034EFC
0x180034e54  xor     eax, eax
0x180034e56  lea     rcx, [rsp+478h+var_436]; void *
0x180034e5b  xor     edx, edx; Val
0x180034e5d  mov     [rsp+478h+pszPathOut], ax
0x180034e62  mov     r8d, 206h; Size
0x180034e68  call    memset_0
0x180034e6d  lea     r9, pszMore; "extensions.configurationchanged"
0x180034e74  lea     r8, [rsp+478h+Dst]; pszPathIn
0x180034e7c  lea     rcx, [rsp+478h+pszPathOut]; pszPathOut
0x180034e81  call    PathCchCombineEx
0x180034e86  lea     rcx, [rsp+478h+pszPathOut]; lpFileName
0x180034e8b  call    cs:__imp_DeleteFileW
0x180034e91  xor     r9d, r9d; lpSecurityAttributes
0x180034e94  mov     [rsp+478h+hTemplateFile], 0; hTemplateFile
0x180034e9d  mov     [rsp+478h+dwFlagsAndAttributes], 200A0h; dwFlagsAndAttributes
0x180034ea5  lea     rcx, [rsp+478h+pszPathOut]; lpFileName
0x180034eaa  mov     edx, 40000000h; dwDesiredAccess
0x180034eaf  mov     dword ptr [rsp+478h+dwCreationDisposition], 2; dwCreationDisposition
0x180034eb7  lea     r8d, [r9+2]; dwShareMode
0x180034ebb  call    cs:__imp_CreateFileW
0x180034ec1  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180034ec5  jnz     short loc_180034EF1
0x180034ec7  call    cs:__imp_GetLastError
0x180034ecd  lea     r9, aErrorCreatingD; "Error creating devenv sentinel file. Re"...
0x180034ed4  mov     r8d, 0BBh
0x180034eda  lea     rdx, aCdevenvdotnetc; "CDevenvDotnetCacheRebuildShim::CreateCa"...
0x180034ee1  mov     dword ptr [rsp+478h+dwCreationDisposition], eax
0x180034ee5  mov     ecx, 1
0x180034eea  call    AslLogCallPrintf
0x180034eef  jmp     short loc_180034EFC
0x180034ef1  mov     rcx, rax; hObject
0x180034ef4  call    cs:__imp_CloseHandle
0x180034efa  inc     edi
0x180034efc  inc     rbx
0x180034eff  cmp     rbx, 3
0x180034f03  jnz     loc_180034E03
0x180034f09  xor     eax, eax
0x180034f0b  test    edi, edi
0x180034f0d  setz    al
0x180034f10  mov     ecx, eax
0x180034f12  or      ecx, 80070000h
0x180034f18  test    edi, edi
0x180034f1a  cmovz   eax, ecx
0x180034f1d  mov     rcx, [rsp+478h+var_18]
0x180034f25  xor     rcx, rsp; StackCookie
0x180034f28  call    __security_check_cookie
0x180034f2d  mov     rbx, [rsp+478h+arg_0]
0x180034f35  add     rsp, 470h
0x180034f3c  pop     rdi
0x180034f3d  retn
```
