# SystemSettings::StorageSenseHandlers::CMcpServerPackageInfo::GetInstallDrive(int *)

- ea: `0x1800a76d0`
- end: `0x1800a776a`
- name: `?GetInstallDrive@CMcpServerPackageInfo@StorageSenseHandlers@SystemSettings@@UEAAJPEAH@Z`
- size: `154`
- prototype: `__int64 __fastcall(SystemSettings::StorageSenseHandlers::CMcpServerPackageInfo *__hidden this, int *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting, installer_update`

## callees

- `0x180006e50`
- `0x1800a76d0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a7703`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a7703`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x1800a772c`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x1800a772c`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x1800a773b`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x1800a773b`

## pseudocode

```c
__int64 __fastcall SystemSettings::StorageSenseHandlers::CMcpServerPackageInfo::GetInstallDrive(HSTRING *this, int *a2)
{
  __int64 v3; // rbx
  const WCHAR *StringRawBuffer; // rax
  WCHAR szVolumePathName[264]; // [rsp+20h] [rbp-228h] BYREF

  v3 = -1;
  *a2 = -1;
  StringRawBuffer = WindowsGetStringRawBuffer(this[11], 0);
  if ( StringRawBuffer )
  {
    do
      ++v3;
    while ( StringRawBuffer[v3] );
    if ( v3 && GetVolumePathNameW(StringRawBuffer, szVolumePathName, 0x104u) )
      *a2 = PathGetDriveNumberW(szVolumePathName);
  }
  return 0;
}

```

## disassembly

```asm
0x1800a76d0  mov     [rsp+arg_10], rbx
0x1800a76d5  mov     [rsp+arg_18], rsi
0x1800a76da  push    rdi
0x1800a76db  sub     rsp, 240h
0x1800a76e2  mov     rax, cs:__security_cookie
0x1800a76e9  xor     rax, rsp
0x1800a76ec  mov     [rsp+248h+var_18], rax
0x1800a76f4  mov     rdi, rdx
0x1800a76f7  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800a76fb  mov     [rdx], ebx
0x1800a76fd  xor     edx, edx; length
0x1800a76ff  mov     rcx, [rcx+58h]; string
0x1800a7703  call    cs:__imp_WindowsGetStringRawBuffer
0x1800a7709  xor     esi, esi
0x1800a770b  test    rax, rax
0x1800a770e  jz      short loc_1800A7743
0x1800a7710  inc     rbx
0x1800a7713  cmp     [rax+rbx*2], si
0x1800a7717  jnz     short loc_1800A7710
0x1800a7719  test    rbx, rbx
0x1800a771c  jz      short loc_1800A7743
0x1800a771e  mov     r8d, 104h; cchBufferLength
0x1800a7724  lea     rdx, [rsp+248h+szVolumePathName]; lpszVolumePathName
0x1800a7729  mov     rcx, rax; lpszFileName
0x1800a772c  call    cs:__imp_GetVolumePathNameW
0x1800a7732  test    eax, eax
0x1800a7734  jz      short loc_1800A7743
0x1800a7736  lea     rcx, [rsp+248h+szVolumePathName]; pszPath
0x1800a773b  call    cs:__imp_PathGetDriveNumberW
0x1800a7741  mov     [rdi], eax
0x1800a7743  xor     eax, eax
0x1800a7745  mov     rcx, [rsp+248h+var_18]
0x1800a774d  xor     rcx, rsp; StackCookie
0x1800a7750  call    __security_check_cookie
0x1800a7755  lea     r11, [rsp+248h+var_8]
0x1800a775d  mov     rbx, [r11+20h]
0x1800a7761  mov     rsi, [r11+28h]
0x1800a7765  mov     rsp, r11
0x1800a7768  pop     rdi
0x1800a7769  retn
```
