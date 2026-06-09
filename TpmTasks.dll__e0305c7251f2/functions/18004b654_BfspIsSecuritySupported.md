# BfspIsSecuritySupported

- ea: `0x18004b654`
- end: `0x18004b6f8`
- name: `BfspIsSecuritySupported`
- size: `164`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18004aec4`

## callees

- `0x1800078b0`
- `0x18004b654`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetVolumeInformationW` at `0x18004b6bf`
- `api-ms-win-core-file-l1-1-0!GetVolumeInformationW` at `0x18004b6bf`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x18004b682`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x18004b682`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004b6d7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004b6d7`

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
0x18004b654  push    rbx
0x18004b656  sub     rsp, 270h
0x18004b65d  mov     rax, cs:__security_cookie
0x18004b664  xor     rax, rsp
0x18004b667  mov     [rsp+278h+var_18], rax
0x18004b66f  mov     r8d, 105h; cchBufferLength
0x18004b675  mov     [rsp+278h+FileSystemFlags], 0
0x18004b67d  lea     rdx, [rsp+278h+szVolumePathName]; lpszVolumePathName
0x18004b682  call    cs:__imp_GetVolumePathNameW
0x18004b688  mov     ebx, eax
0x18004b68a  test    eax, eax
0x18004b68c  jz      short loc_18004B6DD
0x18004b68e  mov     [rsp+278h+nFileSystemNameSize], 0; nFileSystemNameSize
0x18004b696  lea     rax, [rsp+278h+FileSystemFlags]
0x18004b69b  mov     [rsp+278h+lpFileSystemNameBuffer], 0; lpFileSystemNameBuffer
0x18004b6a4  lea     rcx, [rsp+278h+szVolumePathName]; lpRootPathName
0x18004b6a9  mov     [rsp+278h+lpFileSystemFlags], rax; lpFileSystemFlags
0x18004b6ae  xor     r9d, r9d; lpVolumeSerialNumber
0x18004b6b1  xor     r8d, r8d; nVolumeNameSize
0x18004b6b4  mov     [rsp+278h+lpMaximumComponentLength], 0; lpMaximumComponentLength
0x18004b6bd  xor     edx, edx; lpVolumeNameBuffer
0x18004b6bf  call    cs:__imp_GetVolumeInformationW
0x18004b6c5  mov     ebx, eax
0x18004b6c7  test    eax, eax
0x18004b6c9  jz      short loc_18004B6DD
0x18004b6cb  test    byte ptr [rsp+278h+FileSystemFlags], 8
0x18004b6d0  jnz     short loc_18004B6DD
0x18004b6d2  xor     ebx, ebx
0x18004b6d4  lea     ecx, [rbx+32h]; dwErrCode
0x18004b6d7  call    cs:__imp_SetLastError
0x18004b6dd  mov     eax, ebx
0x18004b6df  mov     rcx, [rsp+278h+var_18]
0x18004b6e7  xor     rcx, rsp; StackCookie
0x18004b6ea  call    __security_check_cookie
0x18004b6ef  add     rsp, 270h
0x18004b6f6  pop     rbx
0x18004b6f7  retn
```
