# IsPathOnNTFS(ushort const *,bool *)

- ea: `0x180008d68`
- end: `0x180008f60`
- name: `?IsPathOnNTFS@@YAKPEBGPEA_N@Z`
- size: `504`
- prototype: `unsigned int __fastcall(LPCWSTR lpszFileName, bool *)`
- caller_count: `4`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18003b700`
- `0x18003edb0`
- `0x180054250`
- `0x180115608`

## callees

- `0x180008d68`
- `0x18000cf48`
- `0x18000cfc0`
- `0x180144882`
- `0x1801448c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008ded`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008eb8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008ded`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008eb8`
- `KERNEL32!GetVolumePathNameW` at `0x180008de3`
- `KERNEL32!GetVolumePathNameW` at `0x180008de3`
- `KERNEL32!GetVolumeInformationW` at `0x180008eae`
- `KERNEL32!GetVolumeInformationW` at `0x180008eae`
- `KERNEL32!CompareStringW` at `0x180008f22`
- `KERNEL32!CompareStringW` at `0x180008f22`

## pseudocode

```c
__int64 __fastcall IsPathOnNTFS(LPCWSTR lpszFileName, bool *a2)
{
  DWORD LastError; // ebx
  WCHAR szVolumePathName; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v7[526]; // [rsp+42h] [rbp-BEh] BYREF
  WCHAR FileSystemNameBuffer; // [rsp+250h] [rbp+150h] BYREF
  _BYTE v9[526]; // [rsp+252h] [rbp+152h] BYREF
  WCHAR VolumeNameBuffer; // [rsp+460h] [rbp+360h] BYREF
  _BYTE v11[526]; // [rsp+462h] [rbp+362h] BYREF

  LastError = 0;
  szVolumePathName = 0;
  memset_0(v7, 0, 0x208u);
  if ( !lpszFileName || !*lpszFileName || !a2 )
    return 87;
  *a2 = 0;
  if ( GetVolumePathNameW(lpszFileName, &szVolumePathName, 0x105u) )
  {
    VolumeNameBuffer = 0;
    memset_0(v11, 0, 0x208u);
    FileSystemNameBuffer = 0;
    memset_0(v9, 0, 0x208u);
    if ( GetVolumeInformationW(&szVolumePathName, &VolumeNameBuffer, 0x105u, 0, 0, 0, &FileSystemNameBuffer, 0x105u) )
    {
      if ( CompareStringW(0x7Fu, 1u, &FileSystemNameBuffer, -1, L"NTFS", -1) == 2 )
        *a2 = 1;
    }
    else
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 12),
          43,
          (unsigned int)WPP_2c6ea872a9483291c23b89912c4e9397_Traceguids,
          (unsigned int)&szVolumePathName,
          LastError);
      }
    }
  }
  else
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0 )
    {
      if ( *((_BYTE *)WPP_GLOBAL_Control + 105) )
        WPP_SF_SSD(
          *((_QWORD *)WPP_GLOBAL_Control + 12),
          42,
          (unsigned int)WPP_2c6ea872a9483291c23b89912c4e9397_Traceguids,
          (_DWORD)lpszFileName,
          (__int64)&szVolumePathName,
          LastError);
    }
  }
  return LastError;
}

```

## disassembly

```asm
0x180008d68  mov     [rsp-8+arg_10], rbx
0x180008d6d  mov     [rsp-8+arg_18], rsi
0x180008d72  push    rbp
0x180008d73  push    rdi
0x180008d74  push    r15
0x180008d76  lea     rbp, [rsp-580h]
0x180008d7e  sub     rsp, 680h
0x180008d85  mov     rax, cs:__security_cookie
0x180008d8c  xor     rax, rsp
0x180008d8f  mov     [rbp+590h+var_20], rax
0x180008d96  mov     rsi, rdx
0x180008d99  mov     rdi, rcx
0x180008d9c  mov     r15d, 208h
0x180008da2  lea     rcx, [rsp+690h+var_64E]; void *
0x180008da7  xor     ebx, ebx
0x180008da9  mov     r8d, r15d; Size
0x180008dac  xor     edx, edx; Val
0x180008dae  mov     [rsp+690h+szVolumePathName], bx
0x180008db3  call    memset_0
0x180008db8  test    rdi, rdi
0x180008dbb  jz      loc_180008F34
0x180008dc1  cmp     bx, [rdi]
0x180008dc4  jz      loc_180008F34
0x180008dca  test    rsi, rsi
0x180008dcd  jz      loc_180008F34
0x180008dd3  mov     r8d, 105h; cchBufferLength
0x180008dd9  mov     [rsi], bl
0x180008ddb  lea     rdx, [rsp+690h+szVolumePathName]; lpszVolumePathName
0x180008de0  mov     rcx, rdi; lpszFileName
0x180008de3  call    cs:__imp_GetVolumePathNameW
0x180008de9  test    eax, eax
0x180008deb  jnz     short loc_180008E4B
0x180008ded  call    cs:__imp_GetLastError
0x180008df3  mov     ebx, eax
0x180008df5  mov     rcx, cs:WPP_GLOBAL_Control
0x180008dfc  lea     rax, WPP_GLOBAL_Control
0x180008e03  cmp     rcx, rax
0x180008e06  jz      loc_180008F30
0x180008e0c  test    byte ptr [rcx+6Ch], 4
0x180008e10  jz      loc_180008F30
0x180008e16  cmp     byte ptr [rcx+69h], 1
0x180008e1a  jb      loc_180008F30
0x180008e20  mov     rcx, [rcx+60h]
0x180008e24  lea     rax, [rsp+690h+szVolumePathName]
0x180008e29  mov     edx, 2Ah ; '*'
0x180008e2e  mov     dword ptr [rsp+690h+lpFileSystemFlags], ebx
0x180008e32  mov     r9, rdi
0x180008e35  mov     [rsp+690h+lpMaximumComponentLength], rax
0x180008e3a  lea     r8, WPP_2c6ea872a9483291c23b89912c4e9397_Traceguids
0x180008e41  call    WPP_SF_SSD
0x180008e46  jmp     loc_180008F30
0x180008e4b  mov     r8, r15; Size
0x180008e4e  mov     [rbp+590h+VolumeNameBuffer], bx
0x180008e55  xor     edx, edx; Val
0x180008e57  lea     rcx, [rbp+590h+var_22E]; void *
0x180008e5e  call    memset_0
0x180008e63  mov     r8, r15; Size
0x180008e66  mov     [rbp+590h+FileSystemNameBuffer], bx
0x180008e6d  xor     edx, edx; Val
0x180008e6f  lea     rcx, [rbp+590h+var_43E]; void *
0x180008e76  call    memset_0
0x180008e7b  mov     [rsp+690h+nFileSystemNameSize], 105h; nFileSystemNameSize
0x180008e83  lea     rax, [rbp+590h+FileSystemNameBuffer]
0x180008e8a  mov     [rsp+690h+lpFileSystemNameBuffer], rax; lpFileSystemNameBuffer
0x180008e8f  lea     rdx, [rbp+590h+VolumeNameBuffer]; lpVolumeNameBuffer
0x180008e96  mov     [rsp+690h+lpFileSystemFlags], rbx; lpFileSystemFlags
0x180008e9b  lea     rcx, [rsp+690h+szVolumePathName]; lpRootPathName
0x180008ea0  xor     r9d, r9d; lpVolumeSerialNumber
0x180008ea3  mov     [rsp+690h+lpMaximumComponentLength], rbx; lpMaximumComponentLength
0x180008ea8  mov     r8d, 105h; nVolumeNameSize
0x180008eae  call    cs:__imp_GetVolumeInformationW
0x180008eb4  test    eax, eax
0x180008eb6  jnz     short loc_180008EFF
0x180008eb8  call    cs:__imp_GetLastError
0x180008ebe  mov     ebx, eax
0x180008ec0  mov     rcx, cs:WPP_GLOBAL_Control
0x180008ec7  lea     rax, WPP_GLOBAL_Control
0x180008ece  cmp     rcx, rax
0x180008ed1  jz      short loc_180008F30
0x180008ed3  test    byte ptr [rcx+6Ch], 4
0x180008ed7  jz      short loc_180008F30
0x180008ed9  cmp     byte ptr [rcx+69h], 1
0x180008edd  jb      short loc_180008F30
0x180008edf  mov     rcx, [rcx+60h]
0x180008ee3  lea     r9, [rsp+690h+szVolumePathName]
0x180008ee8  mov     edx, 2Bh ; '+'
0x180008eed  mov     dword ptr [rsp+690h+lpMaximumComponentLength], ebx
0x180008ef1  lea     r8, WPP_2c6ea872a9483291c23b89912c4e9397_Traceguids
0x180008ef8  call    WPP_SF_Sd
0x180008efd  jmp     short loc_180008F30
0x180008eff  or      r9d, 0FFFFFFFFh; cchCount1
0x180008f03  lea     rax, String2; "NTFS"
0x180008f0a  mov     dword ptr [rsp+690h+lpFileSystemFlags], r9d; cchCount2
0x180008f0f  lea     r8, [rbp+590h+FileSystemNameBuffer]; lpString1
0x180008f16  mov     [rsp+690h+lpMaximumComponentLength], rax; lpString2
0x180008f1b  lea     edx, [r9+2]; dwCmpFlags
0x180008f1f  lea     ecx, [rdx+7Eh]; Locale
0x180008f22  call    cs:__imp_CompareStringW
0x180008f28  cmp     eax, 2
0x180008f2b  jnz     short loc_180008F30
0x180008f2d  mov     byte ptr [rsi], 1
0x180008f30  mov     eax, ebx
0x180008f32  jmp     short loc_180008F39
0x180008f34  mov     eax, 57h ; 'W'
0x180008f39  mov     rcx, [rbp+590h+var_20]
0x180008f40  xor     rcx, rsp; StackCookie
0x180008f43  call    __security_check_cookie
0x180008f48  lea     r11, [rsp+690h+var_10]
0x180008f50  mov     rbx, [r11+30h]
0x180008f54  mov     rsi, [r11+38h]
0x180008f58  mov     rsp, r11
0x180008f5b  pop     r15
0x180008f5d  pop     rdi
0x180008f5e  pop     rbp
0x180008f5f  retn
```
