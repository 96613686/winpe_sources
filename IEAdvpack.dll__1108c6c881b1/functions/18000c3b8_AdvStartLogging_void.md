# AdvStartLogging(void)

- ea: `0x18000c3b8`
- end: `0x18000c56c`
- name: `?AdvStartLogging@@YAXXZ`
- size: `436`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, reparse_path, registry_config, installer_update, broker_com_uri`

## callers

- `0x18000b4b8`

## callees

- `0x1800022bc`
- `0x18000c3b8`
- `0x1800198d0`
- `0x18001a688`
- `0x18001b294`
- `0x18001b980`

## import_xrefs

- `KERNEL32!GetWindowsDirectoryW` at `0x18000c481`
- `KERNEL32!GetWindowsDirectoryW` at `0x18000c481`
- `KERNEL32!CreateFileW` at `0x18000c521`
- `KERNEL32!CreateFileW` at `0x18000c521`
- `KERNEL32!SetFilePointer` at `0x18000c542`
- `KERNEL32!SetFilePointer` at `0x18000c542`
- `ADVAPI32!RegQueryValueExW` at `0x18000c448`
- `ADVAPI32!RegQueryValueExW` at `0x18000c448`
- `ADVAPI32!RegCloseKey` at `0x18000c45c`
- `ADVAPI32!RegCloseKey` at `0x18000c45c`
- `ADVAPI32!RegOpenKeyExW` at `0x18000c410`
- `ADVAPI32!RegOpenKeyExW` at `0x18000c410`

## pseudocode

```c
void AdvStartLogging(void)
{
  const WCHAR *v0; // rbx
  HANDLE FileW; // rax
  ULONG phkResult; // [rsp+20h] [rbp-E0h]
  DWORD cbData; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  BYTE Data[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int16 v6; // [rsp+52h] [rbp-AEh]
  WCHAR Buffer[264]; // [rsp+260h] [rbp+160h] BYREF

  hKey = 0;
  *(_WORD *)Data = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Advanced INF Setup", 0, 0x20019u, &hKey) )
  {
    cbData = 520;
    if ( RegQueryValueExW(hKey, L"AdvpackLogFile", 0, 0, Data, &cbData) )
      *(_WORD *)Data = 0;
    RegCloseKey(hKey);
  }
  if ( *(_WORD *)Data )
  {
    if ( v6 == 58 )
    {
      StringCchCopyW(Buffer, 0x104u, (const unsigned __int16 *)Data);
    }
    else
    {
      GetWindowsDirectoryW(Buffer, 0x104u);
      v0 = (const WCHAR *)Data;
      if ( !(unsigned int)PathIsUnc2((unsigned __int16 *)Data)
        && !IsExtendedLengthDosDevicePath((const unsigned __int16 *)Data)
        && *(_WORD *)Data == 92 )
      {
        do
          ++v0;
        while ( *v0 == 92 );
      }
      PathCchCombineEx(Buffer, 0x104u, Buffer, v0, phkResult);
    }
    if ( g_hAdvLogFile == (HANDLE)-1LL )
    {
      FileW = CreateFileW(Buffer, 0x40000000u, 3u, 0, 4u, 0x80u, 0);
      g_hAdvLogFile = FileW;
      if ( FileW != (HANDLE)-1LL )
        SetFilePointer(FileW, 0, 0, 2u);
    }
  }
}

```

## disassembly

```asm
0x18000c3b8  mov     [rsp-8+arg_0], rbx
0x18000c3bd  mov     [rsp-8+arg_8], rdi
0x18000c3c2  push    rbp
0x18000c3c3  lea     rbp, [rsp-380h]
0x18000c3cb  sub     rsp, 480h
0x18000c3d2  mov     rax, cs:__security_cookie
0x18000c3d9  xor     rax, rsp
0x18000c3dc  mov     [rbp+380h+var_10], rax
0x18000c3e3  xor     edi, edi
0x18000c3e5  lea     rax, [rsp+480h+hKey]
0x18000c3ea  mov     r9d, 20019h; samDesired
0x18000c3f0  mov     [rsp+480h+hKey], rdi
0x18000c3f5  xor     r8d, r8d; ulOptions
0x18000c3f8  mov     word ptr [rsp+480h+Data], di
0x18000c3fd  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Advanced INF Setup"
0x18000c404  mov     [rsp+480h+phkResult], rax; phkResult
0x18000c409  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000c410  call    cs:__imp_RegOpenKeyExW
0x18000c416  test    eax, eax
0x18000c418  jnz     short loc_18000C462
0x18000c41a  mov     rcx, [rsp+480h+hKey]; hKey
0x18000c41f  lea     rax, [rsp+480h+cbData]
0x18000c424  mov     [rsp+480h+lpcbData], rax; lpcbData
0x18000c429  lea     rdx, aAdvpacklogfile; "AdvpackLogFile"
0x18000c430  lea     rax, [rsp+480h+Data]
0x18000c435  mov     [rsp+480h+cbData], 208h
0x18000c43d  xor     r9d, r9d; lpType
0x18000c440  mov     [rsp+480h+phkResult], rax; dwFlags
0x18000c445  xor     r8d, r8d; lpReserved
0x18000c448  call    cs:__imp_RegQueryValueExW
0x18000c44e  test    eax, eax
0x18000c450  jz      short loc_18000C457
0x18000c452  mov     word ptr [rsp+480h+Data], di
0x18000c457  mov     rcx, [rsp+480h+hKey]; hKey
0x18000c45c  call    cs:__imp_RegCloseKey
0x18000c462  cmp     word ptr [rsp+480h+Data], di
0x18000c467  jz      loc_18000C548
0x18000c46d  cmp     [rsp+480h+var_42E], 3Ah ; ':'
0x18000c473  lea     rcx, [rbp+380h+Buffer]; unsigned __int16 *
0x18000c47a  jz      short loc_18000C4E0
0x18000c47c  mov     edx, 104h; uSize
0x18000c481  call    cs:__imp_GetWindowsDirectoryW
0x18000c487  lea     r8, IsBackslash
0x18000c48e  xor     edx, edx
0x18000c490  lea     rcx, [rsp+480h+Data]; unsigned __int16 *
0x18000c495  lea     rbx, [rsp+480h+Data]
0x18000c49a  call    PathIsUnc2
0x18000c49f  test    eax, eax
0x18000c4a1  jnz     short loc_18000C4C3
0x18000c4a3  lea     rcx, [rsp+480h+Data]; unsigned __int16 *
0x18000c4a8  call    ?IsExtendedLengthDosDevicePath@@YA_NPEBG@Z; IsExtendedLengthDosDevicePath(ushort const *)
0x18000c4ad  test    al, al
0x18000c4af  jnz     short loc_18000C4C3
0x18000c4b1  cmp     word ptr [rsp+480h+Data], 5Ch ; '\'
0x18000c4b7  jnz     short loc_18000C4C3
0x18000c4b9  add     rbx, 2
0x18000c4bd  cmp     word ptr [rbx], 5Ch ; '\'
0x18000c4c1  jz      short loc_18000C4B9
0x18000c4c3  mov     r9, rbx; pszMore
0x18000c4c6  lea     r8, [rbp+380h+Buffer]; pszPathIn
0x18000c4cd  mov     edx, 104h; cchPathOut
0x18000c4d2  lea     rcx, [rbp+380h+Buffer]; pszPathOut
0x18000c4d9  call    PathCchCombineEx
0x18000c4de  jmp     short loc_18000C4EF
0x18000c4e0  lea     r8, [rsp+480h+Data]; unsigned __int16 *
0x18000c4e5  mov     edx, 104h; unsigned __int64
0x18000c4ea  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000c4ef  cmp     cs:?g_hAdvLogFile@@3PEAXEA, 0FFFFFFFFFFFFFFFFh; void * g_hAdvLogFile
0x18000c4f7  jnz     short loc_18000C548
0x18000c4f9  xor     r9d, r9d; lpSecurityAttributes
0x18000c4fc  mov     [rsp+480h+hTemplateFile], rdi; hTemplateFile
0x18000c501  mov     dword ptr [rsp+480h+lpcbData], 80h; dwFlagsAndAttributes
0x18000c509  lea     rcx, [rbp+380h+Buffer]; lpFileName
0x18000c510  mov     edx, 40000000h; dwDesiredAccess
0x18000c515  mov     dword ptr [rsp+480h+phkResult], 4; dwCreationDisposition
0x18000c51d  lea     r8d, [r9+3]; dwShareMode
0x18000c521  call    cs:__imp_CreateFileW
0x18000c527  mov     cs:?g_hAdvLogFile@@3PEAXEA, rax; void * g_hAdvLogFile
0x18000c52e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000c532  jz      short loc_18000C548
0x18000c534  mov     r9d, 2; dwMoveMethod
0x18000c53a  xor     r8d, r8d; lpDistanceToMoveHigh
0x18000c53d  xor     edx, edx; lDistanceToMove
0x18000c53f  mov     rcx, rax; hFile
0x18000c542  call    cs:__imp_SetFilePointer
0x18000c548  mov     rcx, [rbp+380h+var_10]
0x18000c54f  xor     rcx, rsp; StackCookie
0x18000c552  call    __security_check_cookie
0x18000c557  lea     r11, [rsp+480h+var_s0]
0x18000c55f  mov     rbx, [r11+10h]
0x18000c563  mov     rdi, [r11+18h]
0x18000c567  mov     rsp, r11
0x18000c56a  pop     rbp
0x18000c56b  retn
```
