# NgcUtils::ExistsSecureFpRegKey(void)

- ea: `0x18008915c`
- end: `0x1800894b2`
- name: `?ExistsSecureFpRegKey@NgcUtils@@YA_NXZ`
- size: `854`
- prototype: `bool __fastcall(NgcUtils *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800894b8`

## callees

- `0x18000e570`
- `0x18000e960`
- `0x1800138c0`
- `0x180023190`
- `0x180034cf8`
- `0x1800533a4`
- `0x18005cee0`
- `0x18008915c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800892ff`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800892ff`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180089367`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180089367`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180089382`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008938b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800893c8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800893d1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180089382`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008938b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800893c8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800893d1`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x1800891f6`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x1800891f6`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x180089455`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x180089490`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x180089455`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x180089490`
- `DEVOBJ!DevObjGetClassDevs` at `0x180089231`
- `DEVOBJ!DevObjGetClassDevs` at `0x180089231`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x1800893ab`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x1800893ab`
- `DEVOBJ!DevObjEnumDeviceInfo` at `0x180089272`
- `DEVOBJ!DevObjEnumDeviceInfo` at `0x180089272`
- `DEVOBJ!DevObjOpenDevRegKey` at `0x1800892c4`
- `DEVOBJ!DevObjOpenDevRegKey` at `0x1800892c4`

## string_xrefs

- `0x180089281`: `onecore\ds\security\ngc\utils\bio\lib\securebioutils.cpp`
- `0x180089313`: `onecore\ds\security\ngc\utils\bio\lib\securebioutils.cpp`
- `0x180089465`: `onecore\ds\security\ngc\utils\bio\lib\securebioutils.cpp`
- `0x1800891d2`: `Configurations`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall NgcUtils::ExistsSecureFpRegKey(NgcUtils *this)
{
  __int64 DeviceInfoList; // rcx
  const char *v2; // r9
  __int64 v3; // rdx
  char v4; // di
  unsigned int v5; // esi
  __int64 i; // r9
  __int64 v7; // rdx
  const char *v8; // r9
  __int64 v9; // rdx
  HKEY v10; // rcx
  HKEY v11; // rbx
  const WCHAR *v12; // rdx
  unsigned int phkResult; // [rsp+20h] [rbp-E0h]
  char v15; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v16; // [rsp+48h] [rbp-B8h] BYREF
  int pvData; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hkey; // [rsp+58h] [rbp-A8h] BYREF
  char v19; // [rsp+60h] [rbp-A0h]
  DWORD pcbData; // [rsp+68h] [rbp-98h] BYREF
  LPCWSTR lpSubKey[4]; // [rsp+70h] [rbp-90h] BYREF
  _OWORD v22[2]; // [rsp+90h] [rbp-70h] BYREF
  _OWORD v23[3]; // [rsp+B0h] [rbp-50h] BYREF
  char *v24; // [rsp+100h] [rbp+0h]
  __int64 v25; // [rsp+108h] [rbp+8h]
  HKEY *p_hkey; // [rsp+110h] [rbp+10h]
  __int64 v27; // [rsp+118h] [rbp+18h]
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+58h]

  v16 = -1;
  hkey = (HKEY)&v16;
  v19 = 1;
  memset(v22, 0, sizeof(v22));
  memset(v23, 0, sizeof(v23));
  std::wstring::wstring((char **)lpSubKey, L"WinBio");
  std::wstring::append(lpSubKey, (void *)L"\\");
  std::wstring::append(lpSubKey, L"Configurations");
  DeviceInfoList = DevObjCreateDeviceInfoList(0, 0, 0, 0, 0);
  v16 = DeviceInfoList;
  if ( (unsigned __int64)(DeviceInfoList - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    v3 = 748;
    goto LABEL_33;
  }
  if ( !(unsigned int)DevObjGetClassDevs(DeviceInfoList, &GUID_DEVINTERFACE_BIOMETRIC_READER, 0, 16, 0, 0) )
  {
    v3 = 764;
LABEL_33:
    wil::details::in1diag3::Log_GetLastError(
      retaddr,
      (void *)v3,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\bio\\lib\\securebioutils.cpp",
      v2);
    std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(lpSubKey);
    if ( (unsigned __int64)(v16 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      ((void (*)(void))DevObjDestroyDeviceInfoList)();
    return 0;
  }
  v4 = 0;
  v5 = 0;
  LODWORD(v22[0]) = 32;
  for ( i = 0; (unsigned int)DevObjEnumDeviceInterfaces(v16, 0, &GUID_DEVINTERFACE_BIOMETRIC_READER, i, v22); i = v5 )
  {
    v7 = v5++;
    hkey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
    LODWORD(v23[0]) = 48;
    if ( !(unsigned int)DevObjEnumDeviceInfo(v16, v7, v23) )
    {
      v9 = 800;
      goto LABEL_7;
    }
    v11 = (HKEY)DevObjOpenDevRegKey(v16, v23, 1);
    if ( v11 == HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
    {
      v9 = 813;
LABEL_7:
      wil::details::in1diag3::Log_GetLastError(
        retaddr,
        (void *)v9,
        (unsigned int)"onecore\\ds\\security\\ngc\\utils\\bio\\lib\\securebioutils.cpp",
        v8);
      v10 = hkey;
      if ( hkey == HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
        continue;
      goto LABEL_20;
    }
    v12 = (const WCHAR *)lpSubKey;
    if ( lpSubKey[3] > (LPCWSTR)7 )
      v12 = lpSubKey[0];
    if ( RegOpenKeyExW(v11, v12, 0, 0x20019u, &hkey) )
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
        v4 = 1;
        if ( hkey != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
          RegCloseKey(hkey);
        RegCloseKey(v11);
        break;
      }
    }
    if ( hkey != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
      RegCloseKey(hkey);
    v10 = v11;
LABEL_20:
    RegCloseKey(v10);
  }
  if ( (unsigned int)dword_180122070 > 4 )
  {
    hkey = (HKEY)v5;
    v15 = v4;
    p_hkey = &hkey;
    v27 = 8;
    v24 = &v15;
    v25 = 1;
    tlgWriteTransfer_EventWriteTransfer(&dword_180122070, &dword_180106ADC, 0);
  }
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(lpSubKey);
  if ( (unsigned __int64)(v16 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    DevObjDestroyDeviceInfoList(v16);
  return v4;
}

```

## disassembly

```asm
0x18008915c  push    rbp
0x18008915e  push    rbx
0x18008915f  push    rsi
0x180089160  push    rdi
0x180089161  push    r15
0x180089163  lea     rbp, [rsp-30h]
0x180089168  sub     rsp, 130h
0x18008916f  mov     rax, cs:__security_cookie
0x180089176  xor     rax, rsp
0x180089179  mov     [rbp+50h+var_30], rax
0x18008917d  or      r15, 0FFFFFFFFFFFFFFFFh
0x180089181  mov     [rsp+150h+var_108], r15
0x180089186  lea     rax, [rsp+150h+var_108]
0x18008918b  mov     [rsp+150h+hkey], rax
0x180089190  mov     [rsp+150h+var_F0], 1
0x180089195  xorps   xmm0, xmm0
0x180089198  movups  [rbp+50h+var_C0], xmm0
0x18008919c  movups  [rbp+50h+var_B0], xmm0
0x1800891a0  xorps   xmm1, xmm1
0x1800891a3  movups  [rbp+50h+var_A0], xmm1
0x1800891a7  movups  [rbp+50h+var_90], xmm1
0x1800891ab  movups  [rbp+50h+var_80], xmm1
0x1800891af  lea     rdx, aWinbio; "WinBio"
0x1800891b6  lea     rcx, [rsp+150h+lpSubKey]
0x1800891bb  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800891c0  nop
0x1800891c1  lea     rdx, asc_1800DB4FC; "\\"
0x1800891c8  lea     rcx, [rsp+150h+lpSubKey]; Src
0x1800891cd  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800891d2  lea     rdx, aConfigurations; "Configurations"
0x1800891d9  lea     rcx, [rsp+150h+lpSubKey]; Src
0x1800891de  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800891e3  mov     [rsp+150h+phkResult], 0
0x1800891ec  xor     r9d, r9d
0x1800891ef  xor     r8d, r8d
0x1800891f2  xor     edx, edx
0x1800891f4  xor     ecx, ecx
0x1800891f6  call    cs:__imp_DevObjCreateDeviceInfoList
0x1800891fc  mov     rcx, rax
0x1800891ff  mov     [rsp+150h+var_108], rax
0x180089204  dec     rax
0x180089207  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18008920b  ja      loc_180089460
0x180089211  mov     [rsp+150h+pvData], 0
0x18008921a  mov     [rsp+150h+phkResult], 0
0x180089223  lea     r9d, [r15+11h]
0x180089227  xor     r8d, r8d
0x18008922a  lea     rdx, GUID_DEVINTERFACE_BIOMETRIC_READER
0x180089231  call    cs:__imp_DevObjGetClassDevs
0x180089237  test    eax, eax
0x180089239  jnz     short loc_180089245
0x18008923b  mov     edx, 2FCh
0x180089240  jmp     loc_180089465
0x180089245  xor     dil, dil
0x180089248  xor     esi, esi
0x18008924a  mov     dword ptr [rbp+50h+var_C0], 20h ; ' '
0x180089251  xor     r9d, r9d
0x180089254  jmp     loc_180089394
0x180089259  mov     edx, esi
0x18008925b  inc     esi
0x18008925d  mov     [rsp+150h+hkey], r15
0x180089262  mov     dword ptr [rbp+50h+var_A0], 30h ; '0'
0x180089269  lea     r8, [rbp+50h+var_A0]
0x18008926d  mov     rcx, [rsp+150h+var_108]
0x180089272  call    cs:__imp_DevObjEnumDeviceInfo
0x180089278  test    eax, eax
0x18008927a  jnz     short loc_1800892A4
0x18008927c  mov     edx, 320h; void *
0x180089281  lea     r8, aOnecoreDsSecur_40; "onecore\\ds\\security\\ngc\\utils\\bio"...
0x180089288  mov     rcx, [rbp+58h]; this
0x18008928c  call    ?Log_GetLastError@in1diag3@details@wil@@YAKPEAXIPEBD@Z; wil::details::in1diag3::Log_GetLastError(void *,uint,char const *)
0x180089291  mov     rcx, [rsp+150h+hkey]
0x180089296  cmp     rcx, r15
0x180089299  jz      loc_180089391
0x18008929f  jmp     loc_18008938B
0x1800892a4  mov     dword ptr [rsp+150h+pvData], 20019h
0x1800892ac  mov     dword ptr [rsp+150h+phkResult], 1
0x1800892b4  xor     r9d, r9d
0x1800892b7  lea     r8d, [r9+1]
0x1800892bb  lea     rdx, [rbp+50h+var_A0]
0x1800892bf  mov     rcx, [rsp+150h+var_108]
0x1800892c4  call    cs:__imp_DevObjOpenDevRegKey
0x1800892ca  mov     rbx, rax
0x1800892cd  cmp     rax, r15
0x1800892d0  jnz     short loc_1800892D9
0x1800892d2  mov     edx, 32Dh
0x1800892d7  jmp     short loc_180089281
0x1800892d9  lea     rdx, [rsp+150h+lpSubKey]
0x1800892de  cmp     [rbp+50h+var_C8], 7
0x1800892e3  cmova   rdx, [rsp+150h+lpSubKey]; lpSubKey
0x1800892e9  lea     rax, [rsp+150h+hkey]
0x1800892ee  mov     [rsp+150h+phkResult], rax; unsigned int
0x1800892f3  mov     r9d, 20019h; samDesired
0x1800892f9  xor     r8d, r8d; ulOptions
0x1800892fc  mov     rcx, rbx; hKey
0x1800892ff  call    cs:__imp_RegOpenKeyExW
0x180089305  test    eax, eax
0x180089307  jz      short loc_180089326
0x180089309  mov     rcx, [rbp+58h]; this
0x18008930d  mov     r9d, 3F3h; char *
0x180089313  lea     r8, aOnecoreDsSecur_40; "onecore\\ds\\security\\ngc\\utils\\bio"...
0x18008931a  mov     edx, 338h; void *
0x18008931f  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x180089324  jmp     short loc_180089378
0x180089326  mov     [rsp+150h+var_100], 0
0x18008932e  mov     [rsp+150h+var_E8], 4
0x180089336  lea     rax, [rsp+150h+var_E8]
0x18008933b  mov     [rsp+150h+pcbData], rax; pcbData
0x180089340  lea     rax, [rsp+150h+var_100]
0x180089345  mov     [rsp+150h+pvData], rax; pvData
0x18008934a  mov     [rsp+150h+phkResult], 0; pdwType
0x180089353  mov     r9d, 18h; dwFlags
0x180089359  lea     r8, aSecurefingerpr; "SecureFingerprint"
0x180089360  xor     edx, edx; lpSubKey
0x180089362  mov     rcx, [rsp+150h+hkey]; hkey
0x180089367  call    cs:__imp_RegGetValueW
0x18008936d  test    eax, eax
0x18008936f  jnz     short loc_180089378
0x180089371  cmp     [rsp+150h+var_100], 1
0x180089376  jz      short loc_1800893BB
0x180089378  mov     rcx, [rsp+150h+hkey]; hKey
0x18008937d  cmp     rcx, r15
0x180089380  jz      short loc_180089388
0x180089382  call    cs:__imp_RegCloseKey
0x180089388  mov     rcx, rbx; hKey
0x18008938b  call    cs:__imp_RegCloseKey
0x180089391  mov     r9d, esi
0x180089394  lea     rax, [rbp+50h+var_C0]
0x180089398  mov     [rsp+150h+phkResult], rax
0x18008939d  lea     r8, GUID_DEVINTERFACE_BIOMETRIC_READER
0x1800893a4  xor     edx, edx
0x1800893a6  mov     rcx, [rsp+150h+var_108]
0x1800893ab  call    cs:__imp_DevObjEnumDeviceInterfaces
0x1800893b1  test    eax, eax
0x1800893b3  jnz     loc_180089259
0x1800893b9  jmp     short loc_1800893D7
0x1800893bb  mov     dil, 1
0x1800893be  mov     rcx, [rsp+150h+hkey]; hKey
0x1800893c3  cmp     rcx, r15
0x1800893c6  jz      short loc_1800893CE
0x1800893c8  call    cs:__imp_RegCloseKey
0x1800893ce  mov     rcx, rbx; hKey
0x1800893d1  call    cs:__imp_RegCloseKey
0x1800893d7  mov     eax, cs:dword_180122070
0x1800893dd  cmp     eax, 4
0x1800893e0  jbe     short loc_18008943B
0x1800893e2  mov     eax, esi
0x1800893e4  mov     [rsp+150h+hkey], rax
0x1800893e9  mov     [rsp+150h+var_110], dil
0x1800893ee  lea     rax, [rsp+150h+hkey]
0x1800893f3  mov     [rbp+50h+var_40], rax
0x1800893f7  mov     [rbp+50h+var_38], 8
0x1800893ff  lea     rax, [rsp+150h+var_110]
0x180089404  mov     [rbp+50h+var_50], rax
0x180089408  mov     [rbp+50h+var_48], 1
0x180089410  lea     rax, [rbp+50h+var_70]
0x180089414  mov     [rsp+150h+pvData], rax
0x180089419  mov     dword ptr [rsp+150h+phkResult], 4
0x180089421  xor     r9d, r9d
0x180089424  xor     r8d, r8d
0x180089427  lea     rdx, dword_180106ADC
0x18008942e  lea     rcx, dword_180122070
0x180089435  call    _tlgWriteTransfer_EventWriteTransfer
0x18008943a  nop
0x18008943b  lea     rcx, [rsp+150h+lpSubKey]
0x180089440  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x180089445  nop
0x180089446  mov     rcx, [rsp+150h+var_108]
0x18008944b  lea     rdx, [rcx-1]
0x18008944f  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180089453  ja      short loc_18008945B
0x180089455  call    cs:__imp_DevObjDestroyDeviceInfoList
0x18008945b  mov     al, dil
0x18008945e  jmp     short loc_180089498
0x180089460  mov     edx, 2ECh; void *
0x180089465  lea     r8, aOnecoreDsSecur_40; "onecore\\ds\\security\\ngc\\utils\\bio"...
0x18008946c  mov     rcx, [rbp+58h]; this
0x180089470  call    ?Log_GetLastError@in1diag3@details@wil@@YAKPEAXIPEBD@Z; wil::details::in1diag3::Log_GetLastError(void *,uint,char const *)
0x180089475  nop
0x180089476  lea     rcx, [rsp+150h+lpSubKey]
0x18008947b  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x180089480  nop
0x180089481  mov     rcx, [rsp+150h+var_108]
0x180089486  lea     rax, [rcx-1]
0x18008948a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18008948e  ja      short loc_180089496
0x180089490  call    cs:__imp_DevObjDestroyDeviceInfoList
0x180089496  xor     al, al
0x180089498  mov     rcx, [rbp+50h+var_30]
0x18008949c  xor     rcx, rsp; StackCookie
0x18008949f  call    __security_check_cookie
0x1800894a4  add     rsp, 130h
0x1800894ab  pop     r15
0x1800894ad  pop     rdi
0x1800894ae  pop     rsi
0x1800894af  pop     rbx
0x1800894b0  pop     rbp
0x1800894b1  retn
```
