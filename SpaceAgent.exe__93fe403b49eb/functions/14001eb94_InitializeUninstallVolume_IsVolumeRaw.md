# InitializeUninstallVolume_IsVolumeRaw

- ea: `0x14001eb94`
- end: `0x14001ec2d`
- name: `InitializeUninstallVolume_IsVolumeRaw`
- size: `153`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x14001e464`

## callees

- `0x14001eb94`
- `0x14001edc0`

## import_xrefs

- `KERNEL32!GetVolumeInformationW` at `0x14001ebe2`
- `KERNEL32!GetVolumeInformationW` at `0x14001ebe2`
- `KERNEL32!GetLastError` at `0x14001ebee`
- `KERNEL32!GetLastError` at `0x14001ebee`

## pseudocode

```c
__int64 __fastcall InitializeUninstallVolume_IsVolumeRaw(const WCHAR *a1, _DWORD *a2)
{
  unsigned int VolumeInformationW; // ebx
  WCHAR FileSystemNameBuffer[264]; // [rsp+40h] [rbp-228h] BYREF

  VolumeInformationW = GetVolumeInformationW(a1, 0, 0, 0, 0, 0, FileSystemNameBuffer, 0x104u);
  if ( VolumeInformationW )
  {
    *a2 = 0;
  }
  else if ( GetLastError() == 1005 )
  {
    VolumeInformationW = 1;
    *a2 = 1;
  }
  return VolumeInformationW;
}

```

## disassembly

```asm
0x14001eb94  mov     [rsp+arg_10], rbx
0x14001eb99  push    rdi
0x14001eb9a  sub     rsp, 260h
0x14001eba1  mov     rax, cs:__security_cookie
0x14001eba8  xor     rax, rsp
0x14001ebab  mov     [rsp+268h+var_18], rax
0x14001ebb3  mov     [rsp+268h+nFileSystemNameSize], 104h; nFileSystemNameSize
0x14001ebbb  lea     rax, [rsp+268h+FileSystemNameBuffer]
0x14001ebc0  mov     [rsp+268h+lpFileSystemNameBuffer], rax; lpFileSystemNameBuffer
0x14001ebc5  mov     rdi, rdx
0x14001ebc8  mov     [rsp+268h+lpFileSystemFlags], 0; lpFileSystemFlags
0x14001ebd1  xor     r9d, r9d; lpVolumeSerialNumber
0x14001ebd4  xor     r8d, r8d; nVolumeNameSize
0x14001ebd7  mov     [rsp+268h+lpMaximumComponentLength], 0; lpMaximumComponentLength
0x14001ebe0  xor     edx, edx; lpVolumeNameBuffer
0x14001ebe2  call    cs:__imp_GetVolumeInformationW
0x14001ebe8  mov     ebx, eax
0x14001ebea  test    eax, eax
0x14001ebec  jnz     short loc_14001EC04
0x14001ebee  call    cs:__imp_GetLastError
0x14001ebf4  cmp     eax, 3EDh
0x14001ebf9  jnz     short loc_14001EC0A
0x14001ebfb  mov     ebx, 1
0x14001ec00  mov     [rdi], ebx
0x14001ec02  jmp     short loc_14001EC0A
0x14001ec04  mov     dword ptr [rdi], 0
0x14001ec0a  mov     eax, ebx
0x14001ec0c  mov     rcx, [rsp+268h+var_18]
0x14001ec14  xor     rcx, rsp; StackCookie
0x14001ec17  call    __security_check_cookie
0x14001ec1c  mov     rbx, [rsp+268h+arg_10]
0x14001ec24  add     rsp, 260h
0x14001ec2b  pop     rdi
0x14001ec2c  retn
```
