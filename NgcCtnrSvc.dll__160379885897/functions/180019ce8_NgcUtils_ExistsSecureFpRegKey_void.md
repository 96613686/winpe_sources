# NgcUtils::ExistsSecureFpRegKey(void)

- ea: `0x180019ce8`
- end: `0x18001a07f`
- name: `?ExistsSecureFpRegKey@NgcUtils@@YA_NXZ`
- size: `919`
- prototype: `bool __fastcall(NgcUtils *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180055e5c`

## callees

- `0x1800067c0`
- `0x18000a8e0`
- `0x180012300`
- `0x180013c88`
- `0x180019ce8`
- `0x180028f14`
- `0x18002c640`
- `0x18003a404`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180019f0a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180019f0a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180019e9c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180019e9c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019f2b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019f3a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019f83`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019f92`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019f2b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019f3a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019f83`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019f92`
- `DEVOBJ!DevObjGetClassDevs` at `0x180019dc3`
- `DEVOBJ!DevObjGetClassDevs` at `0x180019dc3`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x180019f60`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x180019f60`
- `DEVOBJ!DevObjEnumDeviceInfo` at `0x180019e0a`
- `DEVOBJ!DevObjEnumDeviceInfo` at `0x180019e0a`
- `DEVOBJ!DevObjOpenDevRegKey` at `0x180019e5b`
- `DEVOBJ!DevObjOpenDevRegKey` at `0x180019e5b`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x18001a01c`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x18001a056`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x18001a01c`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x18001a056`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x180019d82`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x180019d82`

## string_xrefs

- `0x180019eb6`: `onecore\ds\security\ngc\utils\bio\lib\securebioutils.cpp`
- `0x180019d5e`: `Configurations`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall NgcUtils::ExistsSecureFpRegKey(NgcUtils *this)
{
  __int64 DeviceInfoList; // rcx
  unsigned int v2; // r8d
  const char *v3; // r9
  __int64 v4; // rdx
  char v5; // di
  unsigned int v6; // esi
  __int64 i; // r9
  __int64 v8; // rdx
  unsigned int v9; // r8d
  const char *v10; // r9
  __int64 v11; // rdx
  HKEY v12; // rcx
  HKEY v13; // rbx
  const WCHAR *v14; // rdx
  unsigned int phkResult; // [rsp+20h] [rbp-E0h]
  char v17; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v18; // [rsp+48h] [rbp-B8h] BYREF
  int pvData; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hkey; // [rsp+58h] [rbp-A8h] BYREF
  char v21; // [rsp+60h] [rbp-A0h]
  DWORD pcbData; // [rsp+68h] [rbp-98h] BYREF
  LPCWSTR lpSubKey[4]; // [rsp+70h] [rbp-90h] BYREF
  _OWORD v24[2]; // [rsp+90h] [rbp-70h] BYREF
  _OWORD v25[3]; // [rsp+B0h] [rbp-50h] BYREF
  char v26[32]; // [rsp+E0h] [rbp-20h] BYREF
  char *v27; // [rsp+100h] [rbp+0h]
  __int64 v28; // [rsp+108h] [rbp+8h]
  HKEY *p_hkey; // [rsp+110h] [rbp+10h]
  __int64 v30; // [rsp+118h] [rbp+18h]
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+58h]

  v18 = -1;
  hkey = (HKEY)&v18;
  v21 = 1;
  memset(v24, 0, sizeof(v24));
  memset(v25, 0, sizeof(v25));
  std::wstring::wstring(lpSubKey, L"WinBio");
  std::wstring::append(lpSubKey, L"\\");
  std::wstring::append(lpSubKey, L"Configurations");
  DeviceInfoList = DevObjCreateDeviceInfoList(0, 0, 0, 0, 0);
  v18 = DeviceInfoList;
  if ( (unsigned __int64)(DeviceInfoList - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    v4 = 748;
    goto LABEL_33;
  }
  if ( !(unsigned int)DevObjGetClassDevs(DeviceInfoList, &GUID_DEVINTERFACE_BIOMETRIC_READER, 0, 16, 0, 0) )
  {
    v4 = 764;
LABEL_33:
    wil::details::in1diag3::Log_GetLastError(retaddr, (void *)v4, v2, v3);
    std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(lpSubKey);
    if ( (unsigned __int64)(v18 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      DevObjDestroyDeviceInfoList();
    return 0;
  }
  v5 = 0;
  v6 = 0;
  LODWORD(v24[0]) = 32;
  for ( i = 0; (unsigned int)DevObjEnumDeviceInterfaces(v18, 0, &GUID_DEVINTERFACE_BIOMETRIC_READER, i, v24); i = v6 )
  {
    v8 = v6++;
    hkey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
    LODWORD(v25[0]) = 48;
    if ( !(unsigned int)DevObjEnumDeviceInfo(v18, v8, v25) )
    {
      v11 = 800;
      goto LABEL_7;
    }
    v13 = (HKEY)DevObjOpenDevRegKey(v18, v25, 1);
    if ( v13 == HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
    {
      v11 = 813;
LABEL_7:
      wil::details::in1diag3::Log_GetLastError(retaddr, (void *)v11, v9, v10);
      v12 = hkey;
      if ( hkey == HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
        continue;
      goto LABEL_20;
    }
    v14 = (const WCHAR *)lpSubKey;
    if ( lpSubKey[3] > (LPCWSTR)7 )
      v14 = lpSubKey[0];
    if ( RegOpenKeyExW(v13, v14, 0, 0x20019u, &hkey) )
    {
      wil::details::in1diag3::Log_Win32(
        retaddr,
        (void *)0x338,
        (unsigned int)"onecore\\ds\\security\\ngc\\utils\\bio\\lib\\securebioutils.cpp",
        (const char *)0x3F3,
        phkResult);
    }
    else
    {
      pvData = 0;
      pcbData = 4;
      if ( !RegGetValueW(hkey, 0, L"SecureFingerprint", 0x18u, 0, &pvData, &pcbData) && pvData == 1 )
      {
        v5 = 1;
        if ( hkey != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
          RegCloseKey(hkey);
        RegCloseKey(v13);
        break;
      }
    }
    if ( hkey != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
      RegCloseKey(hkey);
    v12 = v13;
LABEL_20:
    RegCloseKey(v12);
  }
  if ( (unsigned int)dword_1800BE0B8 > 4 )
  {
    hkey = (HKEY)v6;
    v17 = v5;
    p_hkey = &hkey;
    v30 = 8;
    v27 = &v17;
    v28 = 1;
    tlgWriteTransfer_EventWriteTransfer(&dword_1800BE0B8, word_1800ADC3A, 0, 0, 4, v26);
  }
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(lpSubKey);
  if ( (unsigned __int64)(v18 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    DevObjDestroyDeviceInfoList();
  return v5;
}

```

## disassembly

```asm
0x180019ce8  push    rbp
0x180019cea  push    rbx
0x180019ceb  push    rsi
0x180019cec  push    rdi
0x180019ced  push    r15
0x180019cef  lea     rbp, [rsp-30h]
0x180019cf4  sub     rsp, 130h
0x180019cfb  mov     rax, cs:__security_cookie
0x180019d02  xor     rax, rsp
0x180019d05  mov     [rbp+50h+var_30], rax
0x180019d09  or      r15, 0FFFFFFFFFFFFFFFFh
0x180019d0d  mov     [rsp+150h+var_108], r15
0x180019d12  lea     rax, [rsp+150h+var_108]
0x180019d17  mov     [rsp+150h+hkey], rax
0x180019d1c  mov     [rsp+150h+var_F0], 1
0x180019d21  xorps   xmm0, xmm0
0x180019d24  movups  [rbp+50h+var_C0], xmm0
0x180019d28  movups  [rbp+50h+var_B0], xmm0
0x180019d2c  xorps   xmm1, xmm1
0x180019d2f  movups  [rbp+50h+var_A0], xmm1
0x180019d33  movups  [rbp+50h+var_90], xmm1
0x180019d37  movups  [rbp+50h+var_80], xmm1
0x180019d3b  lea     rdx, aWinbio; "WinBio"
0x180019d42  lea     rcx, [rsp+150h+lpSubKey]
0x180019d47  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180019d4c  nop
0x180019d4d  lea     rdx, asc_18008F0A4; "\\"
0x180019d54  lea     rcx, [rsp+150h+lpSubKey]
0x180019d59  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180019d5e  lea     rdx, aConfigurations; "Configurations"
0x180019d65  lea     rcx, [rsp+150h+lpSubKey]
0x180019d6a  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180019d6f  mov     [rsp+150h+phkResult], 0
0x180019d78  xor     r9d, r9d
0x180019d7b  xor     r8d, r8d
0x180019d7e  xor     edx, edx
0x180019d80  xor     ecx, ecx
0x180019d82  call    cs:__imp_DevObjCreateDeviceInfoList
0x180019d89  nop     dword ptr [rax+rax+00h]
0x180019d8e  mov     rcx, rax
0x180019d91  mov     [rsp+150h+var_108], rax
0x180019d96  dec     rax
0x180019d99  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180019d9d  ja      loc_18001A02D
0x180019da3  mov     [rsp+150h+pvData], 0
0x180019dac  mov     [rsp+150h+phkResult], 0
0x180019db5  lea     r9d, [r15+11h]
0x180019db9  xor     r8d, r8d
0x180019dbc  lea     rdx, GUID_DEVINTERFACE_BIOMETRIC_READER
0x180019dc3  call    cs:__imp_DevObjGetClassDevs
0x180019dca  nop     dword ptr [rax+rax+00h]
0x180019dcf  test    eax, eax
0x180019dd1  jnz     short loc_180019DDD
0x180019dd3  mov     edx, 2FCh
0x180019dd8  jmp     loc_18001A032
0x180019ddd  xor     dil, dil
0x180019de0  xor     esi, esi
0x180019de2  mov     dword ptr [rbp+50h+var_C0], 20h ; ' '
0x180019de9  xor     r9d, r9d
0x180019dec  jmp     loc_180019F49
0x180019df1  mov     edx, esi
0x180019df3  inc     esi
0x180019df5  mov     [rsp+150h+hkey], r15
0x180019dfa  mov     dword ptr [rbp+50h+var_A0], 30h ; '0'
0x180019e01  lea     r8, [rbp+50h+var_A0]
0x180019e05  mov     rcx, [rsp+150h+var_108]
0x180019e0a  call    cs:__imp_DevObjEnumDeviceInfo
0x180019e11  nop     dword ptr [rax+rax+00h]
0x180019e16  test    eax, eax
0x180019e18  jnz     short loc_180019E3B
0x180019e1a  mov     edx, 320h; void *
0x180019e1f  mov     rcx, [rbp+58h]; this
0x180019e23  call    ?Log_GetLastError@in1diag3@details@wil@@YAKPEAXIPEBD@Z; wil::details::in1diag3::Log_GetLastError(void *,uint,char const *)
0x180019e28  mov     rcx, [rsp+150h+hkey]
0x180019e2d  cmp     rcx, r15
0x180019e30  jz      loc_180019F46
0x180019e36  jmp     loc_180019F3A
0x180019e3b  mov     dword ptr [rsp+150h+pvData], 20019h
0x180019e43  mov     dword ptr [rsp+150h+phkResult], 1
0x180019e4b  xor     r9d, r9d
0x180019e4e  lea     r8d, [r9+1]
0x180019e52  lea     rdx, [rbp+50h+var_A0]
0x180019e56  mov     rcx, [rsp+150h+var_108]
0x180019e5b  call    cs:__imp_DevObjOpenDevRegKey
0x180019e62  nop     dword ptr [rax+rax+00h]
0x180019e67  mov     rbx, rax
0x180019e6a  cmp     rax, r15
0x180019e6d  jnz     short loc_180019E76
0x180019e6f  mov     edx, 32Dh
0x180019e74  jmp     short loc_180019E1F
0x180019e76  lea     rdx, [rsp+150h+lpSubKey]
0x180019e7b  cmp     [rbp+50h+var_C8], 7
0x180019e80  cmova   rdx, [rsp+150h+lpSubKey]; lpSubKey
0x180019e86  lea     rax, [rsp+150h+hkey]
0x180019e8b  mov     [rsp+150h+phkResult], rax; unsigned int
0x180019e90  mov     r9d, 20019h; samDesired
0x180019e96  xor     r8d, r8d; ulOptions
0x180019e99  mov     rcx, rbx; hKey
0x180019e9c  call    cs:__imp_RegOpenKeyExW
0x180019ea3  nop     dword ptr [rax+rax+00h]
0x180019ea8  test    eax, eax
0x180019eaa  jz      short loc_180019EC9
0x180019eac  mov     rcx, [rbp+58h]; this
0x180019eb0  mov     r9d, 3F3h; char *
0x180019eb6  lea     r8, aOnecoreDsSecur_33; "onecore\\ds\\security\\ngc\\utils\\bio"...
0x180019ebd  mov     edx, 338h; void *
0x180019ec2  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x180019ec7  jmp     short loc_180019F21
0x180019ec9  mov     [rsp+150h+var_100], 0
0x180019ed1  mov     [rsp+150h+var_E8], 4
0x180019ed9  lea     rax, [rsp+150h+var_E8]
0x180019ede  mov     [rsp+150h+pcbData], rax; pcbData
0x180019ee3  lea     rax, [rsp+150h+var_100]
0x180019ee8  mov     [rsp+150h+pvData], rax; pvData
0x180019eed  mov     [rsp+150h+phkResult], 0; pdwType
0x180019ef6  mov     r9d, 18h; dwFlags
0x180019efc  lea     r8, aSecurefingerpr; "SecureFingerprint"
0x180019f03  xor     edx, edx; lpSubKey
0x180019f05  mov     rcx, [rsp+150h+hkey]; hkey
0x180019f0a  call    cs:__imp_RegGetValueW
0x180019f11  nop     dword ptr [rax+rax+00h]
0x180019f16  test    eax, eax
0x180019f18  jnz     short loc_180019F21
0x180019f1a  cmp     [rsp+150h+var_100], 1
0x180019f1f  jz      short loc_180019F76
0x180019f21  mov     rcx, [rsp+150h+hkey]; hKey
0x180019f26  cmp     rcx, r15
0x180019f29  jz      short loc_180019F37
0x180019f2b  call    cs:__imp_RegCloseKey
0x180019f32  nop     dword ptr [rax+rax+00h]
0x180019f37  mov     rcx, rbx; hKey
0x180019f3a  call    cs:__imp_RegCloseKey
0x180019f41  nop     dword ptr [rax+rax+00h]
0x180019f46  mov     r9d, esi
0x180019f49  lea     rax, [rbp+50h+var_C0]
0x180019f4d  mov     [rsp+150h+phkResult], rax
0x180019f52  lea     r8, GUID_DEVINTERFACE_BIOMETRIC_READER
0x180019f59  xor     edx, edx
0x180019f5b  mov     rcx, [rsp+150h+var_108]
0x180019f60  call    cs:__imp_DevObjEnumDeviceInterfaces
0x180019f67  nop     dword ptr [rax+rax+00h]
0x180019f6c  test    eax, eax
0x180019f6e  jnz     loc_180019DF1
0x180019f74  jmp     short loc_180019F9E
0x180019f76  mov     dil, 1
0x180019f79  mov     rcx, [rsp+150h+hkey]; hKey
0x180019f7e  cmp     rcx, r15
0x180019f81  jz      short loc_180019F8F
0x180019f83  call    cs:__imp_RegCloseKey
0x180019f8a  nop     dword ptr [rax+rax+00h]
0x180019f8f  mov     rcx, rbx; hKey
0x180019f92  call    cs:__imp_RegCloseKey
0x180019f99  nop     dword ptr [rax+rax+00h]
0x180019f9e  mov     eax, cs:dword_1800BE0B8
0x180019fa4  cmp     eax, 4
0x180019fa7  jbe     short loc_18001A002
0x180019fa9  mov     eax, esi
0x180019fab  mov     [rsp+150h+hkey], rax
0x180019fb0  mov     [rsp+150h+var_110], dil
0x180019fb5  lea     rax, [rsp+150h+hkey]
0x180019fba  mov     [rbp+50h+var_40], rax
0x180019fbe  mov     [rbp+50h+var_38], 8
0x180019fc6  lea     rax, [rsp+150h+var_110]
0x180019fcb  mov     [rbp+50h+var_50], rax
0x180019fcf  mov     [rbp+50h+var_48], 1
0x180019fd7  lea     rax, [rbp+50h+var_70]
0x180019fdb  mov     [rsp+150h+pvData], rax
0x180019fe0  mov     dword ptr [rsp+150h+phkResult], 4
0x180019fe8  xor     r9d, r9d
0x180019feb  xor     r8d, r8d
0x180019fee  lea     rdx, word_1800ADC3A
0x180019ff5  lea     rcx, dword_1800BE0B8
0x180019ffc  call    _tlgWriteTransfer_EventWriteTransfer
0x18001a001  nop
0x18001a002  lea     rcx, [rsp+150h+lpSubKey]
0x18001a007  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x18001a00c  nop
0x18001a00d  mov     rcx, [rsp+150h+var_108]
0x18001a012  lea     rdx, [rcx-1]
0x18001a016  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18001a01a  ja      short loc_18001A028
0x18001a01c  call    cs:__imp_DevObjDestroyDeviceInfoList
0x18001a023  nop     dword ptr [rax+rax+00h]
0x18001a028  mov     al, dil
0x18001a02b  jmp     short loc_18001A064
0x18001a02d  mov     edx, 2ECh; void *
0x18001a032  mov     rcx, [rbp+58h]; this
0x18001a036  call    ?Log_GetLastError@in1diag3@details@wil@@YAKPEAXIPEBD@Z; wil::details::in1diag3::Log_GetLastError(void *,uint,char const *)
0x18001a03b  nop
0x18001a03c  lea     rcx, [rsp+150h+lpSubKey]
0x18001a041  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x18001a046  nop
0x18001a047  mov     rcx, [rsp+150h+var_108]
0x18001a04c  lea     rax, [rcx-1]
0x18001a050  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001a054  ja      short loc_18001A062
0x18001a056  call    cs:__imp_DevObjDestroyDeviceInfoList
0x18001a05d  nop     dword ptr [rax+rax+00h]
0x18001a062  xor     al, al
0x18001a064  mov     rcx, [rbp+50h+var_30]
0x18001a068  xor     rcx, rsp; StackCookie
0x18001a06b  call    __security_check_cookie
0x18001a070  add     rsp, 130h
0x18001a077  pop     r15
0x18001a079  pop     rdi
0x18001a07a  pop     rsi
0x18001a07b  pop     rbx
0x18001a07c  pop     rbp
0x18001a07d  retn
```
