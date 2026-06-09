# _AuthHostAppContainerProfileExist(ushort *)

- ea: `0x18000fbd0`
- end: `0x18000fcf4`
- name: `?_AuthHostAppContainerProfileExist@@YAEPEAG@Z`
- size: `292`
- prototype: `char __fastcall(wchar_t *lpwszMoniker)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000fcfc`

## callees

- `0x18000fbd0`
- `0x180011bb8`
- `0x180011cb0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000fcd1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000fce1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000fcd1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000fce1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000fc10`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000fc71`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000fc10`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000fc71`

## pseudocode

```c
char __fastcall _AuthHostAppContainerProfileExist(wchar_t *lpwszMoniker)
{
  char v2; // bl
  LSTATUS TraceGuid; // edx
  const _GUID *v4; // r8
  const wchar_t *v5; // r9
  LSTATUS _a3; // r8d
  HKEY__ *hKey; // [rsp+48h] [rbp+10h] BYREF
  HKEY__ *hAuthHostKey; // [rsp+50h] [rbp+18h] BYREF

  hKey = 0;
  hAuthHostKey = 0;
  v2 = 0;
  TraceGuid = RegOpenKeyExW(
                HKEY_CURRENT_USER,
                L"Software\\Classes\\Local Settings\\Software\\Microsoft\\Windows\\CurrentVersion\\AppContainer\\Storage",
                0,
                0x20019u,
                &hKey);
  if ( TraceGuid )
  {
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control[1].ReserveSpace[28] & 0x10) != 0
      && WPP_GLOBAL_Control[1].Control.Level >= 5u )
    {
      WPP_SF_SD(WPP_GLOBAL_Control[1].Control.Logger, TraceGuid, v4, v5, TraceGuid);
    }
  }
  else
  {
    _a3 = RegOpenKeyExW(hKey, lpwszMoniker, 0, 0x20019u, &hAuthHostKey);
    if ( _a3 )
    {
      if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control[1].ReserveSpace[28] & 0x10) != 0
        && WPP_GLOBAL_Control[1].Control.Level >= 5u )
      {
        WPP_SF_SSD(
          WPP_GLOBAL_Control[1].Control.Logger,
          0x3Eu,
          WPP_2e67a773e415305932e36b9aa11a69b0_Traceguids,
          L"Software\\Classes\\Local Settings\\Software\\Microsoft\\Windows\\CurrentVersion\\AppContainer\\Storage",
          lpwszMoniker,
          _a3);
      }
    }
    else
    {
      v2 = 1;
    }
  }
  if ( hAuthHostKey )
    RegCloseKey(hAuthHostKey);
  if ( hKey )
    RegCloseKey(hKey);
  return v2;
}

```

## disassembly

```asm
0x18000fbd0  mov     r11, rsp
0x18000fbd3  mov     [r11+8], rbx
0x18000fbd7  push    rdi
0x18000fbd8  sub     rsp, 30h
0x18000fbdc  mov     rdi, lpwszMoniker
0x18000fbdf  mov     qword ptr [r11+10h], 0
0x18000fbe7  lea     rax, [r11+10h]
0x18000fbeb  mov     qword ptr [r11+18h], 0
0x18000fbf3  mov     lpwszMoniker, 0FFFFFFFF80000001h; hKey
0x18000fbfa  mov     [r11-18h], rax
0x18000fbfe  mov     r9d, 20019h; samDesired
0x18000fc04  lea     rdx, aSoftwareClasse; "Software\\Classes\\Local Settings\\Soft"...
0x18000fc0b  xor     r8d, r8d; ulOptions
0x18000fc0e  xor     bl, bl
0x18000fc10  call    cs:__imp_RegOpenKeyExW
0x18000fc16  mov     edx, eax; _a2
0x18000fc18  test    eax, eax
0x18000fc1a  jz      short loc_18000FC56
0x18000fc1c  mov     lpwszMoniker, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18000fc23  lea     rax, WPP_GLOBAL_Control
0x18000fc2a  cmp     lpwszMoniker, rax
0x18000fc2d  jz      $Cleanup
0x18000fc33  test    byte ptr [lpwszMoniker+44h], 10h
0x18000fc37  jz      $Cleanup
0x18000fc3d  cmp     byte ptr [lpwszMoniker+41h], 5
0x18000fc41  jb      $Cleanup
0x18000fc47  mov     lpwszMoniker, [lpwszMoniker+38h]; Logger
0x18000fc4b  mov     [rsp+38h+TraceGuid], edx; TraceGuid
0x18000fc4f  call    WPP_SF_SD
0x18000fc54  jmp     short $Cleanup
0x18000fc56  mov     lpwszMoniker, [rsp+38h+hKey]; hKey
0x18000fc5b  lea     rax, [rsp+38h+hAuthHostKey]
0x18000fc60  mov     r9d, 20019h; samDesired
0x18000fc66  mov     qword ptr [rsp+38h+TraceGuid], rax; phkResult
0x18000fc6b  xor     r8d, r8d; ulOptions
0x18000fc6e  mov     rdx, rdi; lpSubKey
0x18000fc71  call    cs:__imp_RegOpenKeyExW
0x18000fc77  mov     r8d, eax
0x18000fc7a  test    eax, eax
0x18000fc7c  jz      short loc_18000FCC5
0x18000fc7e  mov     lpwszMoniker, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18000fc85  lea     rax, WPP_GLOBAL_Control
0x18000fc8c  cmp     lpwszMoniker, rax
0x18000fc8f  jz      short $Cleanup
0x18000fc91  test    byte ptr [lpwszMoniker+44h], 10h
0x18000fc95  jz      short $Cleanup
0x18000fc97  cmp     byte ptr [lpwszMoniker+41h], 5
0x18000fc9b  jb      short $Cleanup
0x18000fc9d  mov     lpwszMoniker, [lpwszMoniker+38h]; Logger
0x18000fca1  lea     r9, aSoftwareClasse; "Software\\Classes\\Local Settings\\Soft"...
0x18000fca8  mov     [rsp+38h+_a3], r8d; _a3
0x18000fcad  mov     edx, 3Eh ; '>'; id
0x18000fcb2  lea     r8, WPP_2e67a773e415305932e36b9aa11a69b0_Traceguids; TraceGuid
0x18000fcb9  mov     qword ptr [rsp+38h+TraceGuid], rdi; _a2
0x18000fcbe  call    WPP_SF_SSD
0x18000fcc3  jmp     short $Cleanup
0x18000fcc5  mov     bl, 1
0x18000fcc7  mov     lpwszMoniker, [rsp+38h+hAuthHostKey]; hKey
0x18000fccc  test    lpwszMoniker, lpwszMoniker
0x18000fccf  jz      short loc_18000FCD7
0x18000fcd1  call    cs:__imp_RegCloseKey
0x18000fcd7  mov     lpwszMoniker, [rsp+38h+hKey]; hKey
0x18000fcdc  test    lpwszMoniker, lpwszMoniker
0x18000fcdf  jz      short loc_18000FCE7
0x18000fce1  call    cs:__imp_RegCloseKey
0x18000fce7  mov     al, bl
0x18000fce9  mov     rbx, [rsp+38h+arg_0]
0x18000fcee  add     rsp, 30h
0x18000fcf2  pop     rdi
0x18000fcf3  retn
```
