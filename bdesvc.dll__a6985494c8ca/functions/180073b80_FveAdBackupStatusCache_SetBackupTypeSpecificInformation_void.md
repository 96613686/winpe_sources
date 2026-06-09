# FveAdBackupStatusCache::SetBackupTypeSpecificInformation(void)

- ea: `0x180073b80`
- end: `0x180073cc3`
- name: `?SetBackupTypeSpecificInformation@FveAdBackupStatusCache@@MEBAJXZ`
- size: `323`
- prototype: `__int64 __fastcall(FveAdBackupStatusCache *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180009f60`
- `0x180073b80`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180073bd7`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180073bd7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180073c51`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180073c51`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180073ca4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180073ca4`

## pseudocode

```c
__int64 __fastcall FveAdBackupStatusCache::SetBackupTypeSpecificInformation(const BYTE *this)
{
  LSTATUS v2; // eax
  unsigned int v3; // ebx
  LSTATUS v4; // eax
  HKEY hKey; // [rsp+68h] [rbp+10h] BYREF

  hKey = 0;
  v2 = RegCreateKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\DeviceEncryption\\ADBackup",
         0,
         0,
         0,
         2u,
         0,
         &hKey,
         0);
  v3 = v2;
  if ( v2 > 0 )
    v3 = (unsigned __int16)v2 | 0x80070000;
  if ( !v3 )
    goto LABEL_8;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 138, &WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids, v3);
  if ( (v3 & 0x80000000) == 0 )
  {
LABEL_8:
    v4 = RegSetValueExW(hKey, L"DomainGuid", 0, 3u, this + 8, 0x10u);
    v3 = v4;
    if ( v4 > 0 )
      v3 = (unsigned __int16)v4 | 0x80070000;
    if ( v3 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 139, &WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids, v3);
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v3;
}

```

## disassembly

```asm
0x180073b80  mov     r11, rsp
0x180073b83  mov     [r11+8], rbx
0x180073b87  mov     [r11+18h], rbp
0x180073b8b  push    rdi
0x180073b8c  sub     rsp, 50h
0x180073b90  mov     qword ptr [r11-18h], 0
0x180073b98  lea     rax, [r11+10h]
0x180073b9c  mov     [r11-20h], rax
0x180073ba0  lea     rdx, aSoftwareMicros_7; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180073ba7  mov     qword ptr [r11-28h], 0
0x180073baf  mov     rdi, rcx
0x180073bb2  mov     [rsp+58h+samDesired], 2; samDesired
0x180073bba  xor     r9d, r9d; lpClass
0x180073bbd  xor     r8d, r8d; Reserved
0x180073bc0  mov     [rsp+58h+dwOptions], 0; dwOptions
0x180073bc8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180073bcf  mov     qword ptr [r11+10h], 0
0x180073bd7  call    cs:__imp_RegCreateKeyExW
0x180073bde  nop     dword ptr [rax+rax+00h]
0x180073be3  mov     ebx, eax
0x180073be5  test    eax, eax
0x180073be7  jle     short loc_180073BF2
0x180073be9  movzx   ebx, ax
0x180073bec  or      ebx, 80070000h
0x180073bf2  lea     rbp, WPP_GLOBAL_Control
0x180073bf9  test    ebx, ebx
0x180073bfb  jz      short loc_180073C2B
0x180073bfd  mov     rcx, cs:WPP_GLOBAL_Control
0x180073c04  cmp     rcx, rbp
0x180073c07  jz      short loc_180073C27
0x180073c09  test    byte ptr [rcx+1Ch], 40h
0x180073c0d  jz      short loc_180073C27
0x180073c0f  mov     rcx, [rcx+10h]
0x180073c13  lea     r8, WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids
0x180073c1a  mov     edx, 8Ah
0x180073c1f  mov     r9d, ebx
0x180073c22  call    WPP_SF_d
0x180073c27  test    ebx, ebx
0x180073c29  js      short loc_180073C9A
0x180073c2b  mov     rcx, [rsp+58h+hKey]; hKey
0x180073c30  lea     rax, [rdi+8]
0x180073c34  mov     [rsp+58h+samDesired], 10h; cbData
0x180073c3c  lea     rdx, aDomainguid; "DomainGuid"
0x180073c43  mov     r9d, 3; dwType
0x180073c49  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x180073c4e  xor     r8d, r8d; Reserved
0x180073c51  call    cs:__imp_RegSetValueExW
0x180073c58  nop     dword ptr [rax+rax+00h]
0x180073c5d  mov     ebx, eax
0x180073c5f  test    eax, eax
0x180073c61  jle     short loc_180073C6C
0x180073c63  movzx   ebx, ax
0x180073c66  or      ebx, 80070000h
0x180073c6c  test    ebx, ebx
0x180073c6e  jz      short loc_180073C9A
0x180073c70  mov     rcx, cs:WPP_GLOBAL_Control
0x180073c77  cmp     rcx, rbp
0x180073c7a  jz      short loc_180073C9A
0x180073c7c  test    byte ptr [rcx+1Ch], 40h
0x180073c80  jz      short loc_180073C9A
0x180073c82  mov     rcx, [rcx+10h]
0x180073c86  lea     r8, WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids
0x180073c8d  mov     edx, 8Bh
0x180073c92  mov     r9d, ebx
0x180073c95  call    WPP_SF_d
0x180073c9a  mov     rcx, [rsp+58h+hKey]; hKey
0x180073c9f  test    rcx, rcx
0x180073ca2  jz      short loc_180073CB0
0x180073ca4  call    cs:__imp_RegCloseKey
0x180073cab  nop     dword ptr [rax+rax+00h]
0x180073cb0  mov     rbp, [rsp+58h+arg_10]
0x180073cb5  mov     eax, ebx
0x180073cb7  mov     rbx, [rsp+58h+arg_0]
0x180073cbc  add     rsp, 50h
0x180073cc0  pop     rdi
0x180073cc1  retn
```
