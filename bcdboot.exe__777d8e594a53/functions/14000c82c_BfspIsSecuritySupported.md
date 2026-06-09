# BfspIsSecuritySupported

- ea: `0x14000c82c`
- end: `0x14000c8d0`
- name: `BfspIsSecuritySupported`
- size: `164`
- prototype: `__int64 __fastcall(const WCHAR *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000c024`

## callees

- `0x14000c82c`
- `0x140026650`

## import_xrefs

- `KERNEL32!SetLastError` at `0x14000c8af`
- `KERNEL32!SetLastError` at `0x14000c8af`
- `KERNEL32!GetVolumeInformationW` at `0x14000c897`
- `KERNEL32!GetVolumeInformationW` at `0x14000c897`
- `KERNEL32!GetVolumePathNameW` at `0x14000c85a`
- `KERNEL32!GetVolumePathNameW` at `0x14000c85a`

## pseudocode

```c
__int64 __fastcall BfspIsSecuritySupported(const WCHAR *a1)
{
  unsigned int VolumePathNameW; // ebx
  DWORD FileSystemFlags[4]; // [rsp+40h] [rbp-238h] BYREF
  WCHAR szVolumePathName[264]; // [rsp+50h] [rbp-228h] BYREF

  FileSystemFlags[0] = 0;
  VolumePathNameW = GetVolumePathNameW(a1, szVolumePathName, 0x105u);
  if ( VolumePathNameW )
  {
    VolumePathNameW = GetVolumeInformationW(szVolumePathName, 0, 0, 0, 0, FileSystemFlags, 0, 0);
    if ( VolumePathNameW )
    {
      if ( (FileSystemFlags[0] & 8) == 0 )
      {
        VolumePathNameW = 0;
        SetLastError(0x32u);
      }
    }
  }
  return VolumePathNameW;
}

```

## disassembly

```asm
0x14000c82c  push    rbx
0x14000c82e  sub     rsp, 270h
0x14000c835  mov     rax, cs:__security_cookie
0x14000c83c  xor     rax, rsp
0x14000c83f  mov     [rsp+278h+var_18], rax
0x14000c847  mov     r8d, 105h; cchBufferLength
0x14000c84d  mov     [rsp+278h+FileSystemFlags], 0
0x14000c855  lea     rdx, [rsp+278h+szVolumePathName]; lpszVolumePathName
0x14000c85a  call    cs:__imp_GetVolumePathNameW
0x14000c860  mov     ebx, eax
0x14000c862  test    eax, eax
0x14000c864  jz      short loc_14000C8B5
0x14000c866  mov     [rsp+278h+nFileSystemNameSize], 0; nFileSystemNameSize
0x14000c86e  lea     rax, [rsp+278h+FileSystemFlags]
0x14000c873  mov     [rsp+278h+lpFileSystemNameBuffer], 0; lpFileSystemNameBuffer
0x14000c87c  lea     rcx, [rsp+278h+szVolumePathName]; lpRootPathName
0x14000c881  mov     [rsp+278h+lpFileSystemFlags], rax; lpFileSystemFlags
0x14000c886  xor     r9d, r9d; lpVolumeSerialNumber
0x14000c889  xor     r8d, r8d; nVolumeNameSize
0x14000c88c  mov     [rsp+278h+lpMaximumComponentLength], 0; lpMaximumComponentLength
0x14000c895  xor     edx, edx; lpVolumeNameBuffer
0x14000c897  call    cs:__imp_GetVolumeInformationW
0x14000c89d  mov     ebx, eax
0x14000c89f  test    eax, eax
0x14000c8a1  jz      short loc_14000C8B5
0x14000c8a3  test    byte ptr [rsp+278h+FileSystemFlags], 8
0x14000c8a8  jnz     short loc_14000C8B5
0x14000c8aa  xor     ebx, ebx
0x14000c8ac  lea     ecx, [rbx+32h]; dwErrCode
0x14000c8af  call    cs:__imp_SetLastError
0x14000c8b5  mov     eax, ebx
0x14000c8b7  mov     rcx, [rsp+278h+var_18]
0x14000c8bf  xor     rcx, rsp; StackCookie
0x14000c8c2  call    __security_check_cookie
0x14000c8c7  add     rsp, 270h
0x14000c8ce  pop     rbx
0x14000c8cf  retn
```
