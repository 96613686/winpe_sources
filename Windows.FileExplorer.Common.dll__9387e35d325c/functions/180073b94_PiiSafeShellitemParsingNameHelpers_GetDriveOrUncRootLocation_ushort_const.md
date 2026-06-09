# PiiSafeShellitemParsingNameHelpers::GetDriveOrUncRootLocation(ushort const *)

- ea: `0x180073b94`
- end: `0x180073c44`
- name: `?GetDriveOrUncRootLocation@PiiSafeShellitemParsingNameHelpers@@YA?AW4ShellitemParsingNameRootLoc@@PEBG@Z`
- size: `176`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180072f50`

## callees

- `0x180037780`
- `0x180038708`
- `0x180073b94`
- `0x180073c4c`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x180073be8`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x180073be8`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x180073bf5`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x180073c02`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x180073bf5`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x180073c02`

## pseudocode

```c
char __fastcall PiiSafeShellitemParsingNameHelpers::GetDriveOrUncRootLocation(
        PiiSafeShellitemParsingNameHelpers *a1,
        const unsigned __int16 *a2)
{
  unsigned int DriveTypeFromPath; // eax
  int DriveNumberW; // ebx
  char result; // al
  bool v6; // zf
  WCHAR Buffer[264]; // [rsp+20h] [rbp-228h] BYREF

  if ( !a1 || !*(_WORD *)a1 )
    return 1;
  DriveTypeFromPath = PiiSafeShellitemParsingNameHelpers::GetDriveTypeFromPath(a1, a2);
  if ( DriveTypeFromPath == 3 )
  {
    memset_0(Buffer, 0, 0x208u);
    if ( GetWindowsDirectoryW(Buffer, 0x104u) )
    {
      DriveNumberW = PathGetDriveNumberW((LPCWSTR)a1);
      return (DriveNumberW != PathGetDriveNumberW(Buffer)) - 116;
    }
    return 1;
  }
  if ( DriveTypeFromPath == 2 )
    return -3;
  v6 = DriveTypeFromPath == 4;
  result = -2;
  if ( !v6 )
    return 1;
  return result;
}

```

## disassembly

```asm
0x180073b94  mov     [rsp+arg_8], rbx
0x180073b99  push    rdi
0x180073b9a  sub     rsp, 240h
0x180073ba1  mov     rax, cs:__security_cookie
0x180073ba8  xor     rax, rsp
0x180073bab  mov     [rsp+248h+var_18], rax
0x180073bb3  xor     edi, edi
0x180073bb5  mov     rbx, rcx
0x180073bb8  test    rcx, rcx
0x180073bbb  jz      short loc_180073C21
0x180073bbd  cmp     [rcx], di
0x180073bc0  jz      short loc_180073C21
0x180073bc2  call    ?GetDriveTypeFromPath@PiiSafeShellitemParsingNameHelpers@@YAIPEBG@Z; PiiSafeShellitemParsingNameHelpers::GetDriveTypeFromPath(ushort const *)
0x180073bc7  cmp     eax, 3
0x180073bca  jnz     short loc_180073C11
0x180073bcc  xor     edx, edx; Val
0x180073bce  lea     rcx, [rsp+248h+Buffer]; void *
0x180073bd3  mov     r8d, 208h; Size
0x180073bd9  call    memset_0
0x180073bde  mov     edx, 104h; uSize
0x180073be3  lea     rcx, [rsp+248h+Buffer]; lpBuffer
0x180073be8  call    cs:__imp_GetWindowsDirectoryW
0x180073bee  test    eax, eax
0x180073bf0  jz      short loc_180073C21
0x180073bf2  mov     rcx, rbx; pszPath
0x180073bf5  call    cs:__imp_PathGetDriveNumberW
0x180073bfb  lea     rcx, [rsp+248h+Buffer]; pszPath
0x180073c00  mov     ebx, eax
0x180073c02  call    cs:__imp_PathGetDriveNumberW
0x180073c08  cmp     ebx, eax
0x180073c0a  setnz   al
0x180073c0d  add     al, 8Ch
0x180073c0f  jmp     short loc_180073C23
0x180073c11  cmp     eax, 2
0x180073c14  jnz     short loc_180073C1A
0x180073c16  mov     al, 0FDh
0x180073c18  jmp     short loc_180073C23
0x180073c1a  cmp     eax, 4
0x180073c1d  mov     al, 0FEh
0x180073c1f  jz      short loc_180073C23
0x180073c21  mov     al, 1
0x180073c23  mov     rcx, [rsp+248h+var_18]
0x180073c2b  xor     rcx, rsp; StackCookie
0x180073c2e  call    __security_check_cookie
0x180073c33  mov     rbx, [rsp+248h+arg_8]
0x180073c3b  add     rsp, 240h
0x180073c42  pop     rdi
0x180073c43  retn
```
