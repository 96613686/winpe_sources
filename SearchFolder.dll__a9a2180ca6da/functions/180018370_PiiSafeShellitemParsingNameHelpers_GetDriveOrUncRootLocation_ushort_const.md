# PiiSafeShellitemParsingNameHelpers::GetDriveOrUncRootLocation(ushort const *)

- ea: `0x180018370`
- end: `0x180018420`
- name: `?GetDriveOrUncRootLocation@PiiSafeShellitemParsingNameHelpers@@YA?AW4ShellitemParsingNameRootLoc@@PEBG@Z`
- size: `176`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180014328`

## callees

- `0x180006900`
- `0x1800076dc`
- `0x180018370`
- `0x180018428`

## import_xrefs

- `SHLWAPI!PathGetDriveNumberW` at `0x1800183d1`
- `SHLWAPI!PathGetDriveNumberW` at `0x1800183de`
- `SHLWAPI!PathGetDriveNumberW` at `0x1800183d1`
- `SHLWAPI!PathGetDriveNumberW` at `0x1800183de`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x1800183c4`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x1800183c4`

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
0x180018370  mov     [rsp+arg_8], rbx
0x180018375  push    rdi
0x180018376  sub     rsp, 240h
0x18001837d  mov     rax, cs:__security_cookie
0x180018384  xor     rax, rsp
0x180018387  mov     [rsp+248h+var_18], rax
0x18001838f  xor     edi, edi
0x180018391  mov     rbx, rcx
0x180018394  test    rcx, rcx
0x180018397  jz      short loc_1800183FD
0x180018399  cmp     [rcx], di
0x18001839c  jz      short loc_1800183FD
0x18001839e  call    ?GetDriveTypeFromPath@PiiSafeShellitemParsingNameHelpers@@YAIPEBG@Z; PiiSafeShellitemParsingNameHelpers::GetDriveTypeFromPath(ushort const *)
0x1800183a3  cmp     eax, 3
0x1800183a6  jnz     short loc_1800183ED
0x1800183a8  xor     edx, edx; Val
0x1800183aa  lea     rcx, [rsp+248h+Buffer]; void *
0x1800183af  mov     r8d, 208h; Size
0x1800183b5  call    memset_0
0x1800183ba  mov     edx, 104h; uSize
0x1800183bf  lea     rcx, [rsp+248h+Buffer]; lpBuffer
0x1800183c4  call    cs:__imp_GetWindowsDirectoryW
0x1800183ca  test    eax, eax
0x1800183cc  jz      short loc_1800183FD
0x1800183ce  mov     rcx, rbx; pszPath
0x1800183d1  call    cs:__imp_PathGetDriveNumberW
0x1800183d7  lea     rcx, [rsp+248h+Buffer]; pszPath
0x1800183dc  mov     ebx, eax
0x1800183de  call    cs:__imp_PathGetDriveNumberW
0x1800183e4  cmp     ebx, eax
0x1800183e6  setnz   al
0x1800183e9  add     al, 8Ch
0x1800183eb  jmp     short loc_1800183FF
0x1800183ed  cmp     eax, 2
0x1800183f0  jnz     short loc_1800183F6
0x1800183f2  mov     al, 0FDh
0x1800183f4  jmp     short loc_1800183FF
0x1800183f6  cmp     eax, 4
0x1800183f9  mov     al, 0FEh
0x1800183fb  jz      short loc_1800183FF
0x1800183fd  mov     al, 1
0x1800183ff  mov     rcx, [rsp+248h+var_18]
0x180018407  xor     rcx, rsp; StackCookie
0x18001840a  call    __security_check_cookie
0x18001840f  mov     rbx, [rsp+248h+arg_8]
0x180018417  add     rsp, 240h
0x18001841e  pop     rdi
0x18001841f  retn
```
