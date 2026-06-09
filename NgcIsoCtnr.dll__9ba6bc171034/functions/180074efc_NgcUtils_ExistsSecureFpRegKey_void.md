# NgcUtils::ExistsSecureFpRegKey(void)

- ea: `0x180074efc`
- end: `0x18007523d`
- name: `?ExistsSecureFpRegKey@NgcUtils@@YA_NXZ`
- size: `833`
- prototype: `bool __fastcall(NgcUtils *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800753fc`

## callees

- `0x1800019e8`
- `0x180007670`
- `0x180011c9c`
- `0x180017d70`
- `0x18001cbe8`
- `0x18001cee4`
- `0x180070708`
- `0x180074efc`
- `0x180075600`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180075095`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180075095`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180075118`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180075121`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007515e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180075167`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180075118`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180075121`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007515e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180075167`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800750fd`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800750fd`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x1800751e7`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x18007521b`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x1800751e7`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x18007521b`
- `DEVOBJ!DevObjGetClassDevs` at `0x180074fd1`
- `DEVOBJ!DevObjGetClassDevs` at `0x180074fd1`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x180075141`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x180075141`
- `DEVOBJ!DevObjEnumDeviceInfo` at `0x180075012`
- `DEVOBJ!DevObjEnumDeviceInfo` at `0x180075012`
- `DEVOBJ!DevObjOpenDevRegKey` at `0x18007505d`
- `DEVOBJ!DevObjOpenDevRegKey` at `0x18007505d`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x180074f96`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x180074f96`

## string_xrefs

- `0x180074f72`: `Configurations`
- `0x1800750a9`: `onecore\ds\security\ngc\utils\bio\lib\securebioutils.cpp`

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
  const WCHAR *v14; // rax
  unsigned int phkResult; // [rsp+20h] [rbp-E0h]
  PHKEY phkResulta; // [rsp+20h] [rbp-E0h]
  char v18; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v19; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hkey; // [rsp+50h] [rbp-B0h] BYREF
  int pvData; // [rsp+58h] [rbp-A8h] BYREF
  DWORD pcbData; // [rsp+5Ch] [rbp-A4h] BYREF
  __int64 *v23; // [rsp+60h] [rbp-A0h] BYREF
  char v24; // [rsp+68h] [rbp-98h]
  _BYTE v25[32]; // [rsp+70h] [rbp-90h] BYREF
  _OWORD v26[2]; // [rsp+90h] [rbp-70h] BYREF
  _OWORD v27[3]; // [rsp+B0h] [rbp-50h] BYREF
  char v28[32]; // [rsp+E0h] [rbp-20h] BYREF
  char *v29; // [rsp+100h] [rbp+0h]
  __int64 v30; // [rsp+108h] [rbp+8h]
  __int64 **v31; // [rsp+110h] [rbp+10h]
  __int64 v32; // [rsp+118h] [rbp+18h]
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+58h]

  v19 = -1;
  v23 = &v19;
  v24 = 1;
  memset(v26, 0, sizeof(v26));
  memset(v27, 0, sizeof(v27));
  std::wstring::wstring(v25, L"WinBio");
  std::wstring::append(v25, L"\\");
  std::wstring::append(v25, L"Configurations");
  DeviceInfoList = DevObjCreateDeviceInfoList(0, 0, 0, 0, 0);
  v19 = DeviceInfoList;
  if ( (unsigned __int64)(DeviceInfoList - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    v4 = 748;
    goto LABEL_31;
  }
  if ( !(unsigned int)DevObjGetClassDevs(DeviceInfoList, &GUID_DEVINTERFACE_BIOMETRIC_READER, 0, 16, 0, 0) )
  {
    v4 = 764;
LABEL_31:
    wil::details::in1diag3::Log_GetLastError(retaddr, (void *)v4, v2, v3);
    std::wstring::_Tidy_deallocate(v25);
    if ( (unsigned __int64)(v19 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      DevObjDestroyDeviceInfoList();
    return 0;
  }
  v5 = 0;
  v6 = 0;
  LODWORD(v26[0]) = 32;
  for ( i = 0; (unsigned int)DevObjEnumDeviceInterfaces(v19, 0, &GUID_DEVINTERFACE_BIOMETRIC_READER, i, v26); i = v6 )
  {
    v8 = v6++;
    hkey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
    LODWORD(v27[0]) = 48;
    if ( !(unsigned int)DevObjEnumDeviceInfo(v19, v8, v27) )
    {
      v11 = 800;
      goto LABEL_7;
    }
    v13 = (HKEY)DevObjOpenDevRegKey(v19, v27, 1);
    if ( v13 == HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
    {
      v11 = 813;
LABEL_7:
      wil::details::in1diag3::Log_GetLastError(retaddr, (void *)v11, v9, v10);
      v12 = hkey;
      if ( hkey == HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
        continue;
      goto LABEL_18;
    }
    v14 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v25);
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
LABEL_18:
    RegCloseKey(v12);
  }
  if ( *(_DWORD *)g_logProvider > 4u )
  {
    v23 = (__int64 *)v6;
    v18 = v5;
    v31 = &v23;
    v32 = 8;
    v29 = &v18;
    v30 = 1;
    LODWORD(phkResulta) = 4;
    tlgWriteTransfer_EventWriteTransfer(g_logProvider, word_1800B3D92, 0, 0, phkResulta, v28);
  }
  std::wstring::_Tidy_deallocate(v25);
  if ( (unsigned __int64)(v19 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    DevObjDestroyDeviceInfoList();
  return v5;
}

```

## disassembly

```asm
0x180074efc  push    rbp
0x180074efe  push    rbx
0x180074eff  push    rsi
0x180074f00  push    rdi
0x180074f01  push    r15
0x180074f03  lea     rbp, [rsp-30h]
0x180074f08  sub     rsp, 130h
0x180074f0f  mov     rax, cs:__security_cookie
0x180074f16  xor     rax, rsp
0x180074f19  mov     [rbp+50h+var_30], rax
0x180074f1d  or      r15, 0FFFFFFFFFFFFFFFFh
0x180074f21  mov     [rsp+150h+var_108], r15
0x180074f26  lea     rax, [rsp+150h+var_108]
0x180074f2b  mov     [rsp+150h+var_F0], rax
0x180074f30  mov     [rsp+150h+var_E8], 1
0x180074f35  xorps   xmm0, xmm0
0x180074f38  movups  [rbp+50h+var_C0], xmm0
0x180074f3c  movups  [rbp+50h+var_B0], xmm0
0x180074f40  xorps   xmm1, xmm1
0x180074f43  movups  [rbp+50h+var_A0], xmm1
0x180074f47  movups  [rbp+50h+var_90], xmm1
0x180074f4b  movups  [rbp+50h+var_80], xmm1
0x180074f4f  lea     rdx, aWinbio; "WinBio"
0x180074f56  lea     rcx, [rsp+150h+var_E0]
0x180074f5b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180074f60  nop
0x180074f61  lea     rdx, asc_180093A68; "\\"
0x180074f68  lea     rcx, [rsp+150h+var_E0]
0x180074f6d  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180074f72  lea     rdx, aConfigurations; "Configurations"
0x180074f79  lea     rcx, [rsp+150h+var_E0]
0x180074f7e  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180074f83  mov     [rsp+150h+phkResult], 0
0x180074f8c  xor     r9d, r9d
0x180074f8f  xor     r8d, r8d
0x180074f92  xor     edx, edx
0x180074f94  xor     ecx, ecx
0x180074f96  call    cs:__imp_DevObjCreateDeviceInfoList
0x180074f9c  mov     rcx, rax
0x180074f9f  mov     [rsp+150h+var_108], rax
0x180074fa4  dec     rax
0x180074fa7  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180074fab  ja      loc_1800751F2
0x180074fb1  mov     [rsp+150h+pvData], 0
0x180074fba  mov     [rsp+150h+phkResult], 0
0x180074fc3  lea     r9d, [r15+11h]
0x180074fc7  xor     r8d, r8d
0x180074fca  lea     rdx, GUID_DEVINTERFACE_BIOMETRIC_READER
0x180074fd1  call    cs:__imp_DevObjGetClassDevs
0x180074fd7  test    eax, eax
0x180074fd9  jnz     short loc_180074FE5
0x180074fdb  mov     edx, 2FCh
0x180074fe0  jmp     loc_1800751F7
0x180074fe5  xor     dil, dil
0x180074fe8  xor     esi, esi
0x180074fea  mov     dword ptr [rbp+50h+var_C0], 20h ; ' '
0x180074ff1  xor     r9d, r9d
0x180074ff4  jmp     loc_18007512A
0x180074ff9  mov     edx, esi
0x180074ffb  inc     esi
0x180074ffd  mov     [rsp+150h+hkey], r15
0x180075002  mov     dword ptr [rbp+50h+var_A0], 30h ; '0'
0x180075009  lea     r8, [rbp+50h+var_A0]
0x18007500d  mov     rcx, [rsp+150h+var_108]
0x180075012  call    cs:__imp_DevObjEnumDeviceInfo
0x180075018  test    eax, eax
0x18007501a  jnz     short loc_18007503D
0x18007501c  mov     edx, 320h; void *
0x180075021  mov     rcx, [rbp+58h]; this
0x180075025  call    ?Log_GetLastError@in1diag3@details@wil@@YAKPEAXIPEBD@Z; wil::details::in1diag3::Log_GetLastError(void *,uint,char const *)
0x18007502a  mov     rcx, [rsp+150h+hkey]
0x18007502f  cmp     rcx, r15
0x180075032  jz      loc_180075127
0x180075038  jmp     loc_180075121
0x18007503d  mov     dword ptr [rsp+150h+pvData], 20019h
0x180075045  mov     dword ptr [rsp+150h+phkResult], 1
0x18007504d  xor     r9d, r9d
0x180075050  lea     r8d, [r9+1]
0x180075054  lea     rdx, [rbp+50h+var_A0]
0x180075058  mov     rcx, [rsp+150h+var_108]
0x18007505d  call    cs:__imp_DevObjOpenDevRegKey
0x180075063  mov     rbx, rax
0x180075066  cmp     rax, r15
0x180075069  jnz     short loc_180075072
0x18007506b  mov     edx, 32Dh
0x180075070  jmp     short loc_180075021
0x180075072  lea     rcx, [rsp+150h+var_E0]
0x180075077  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007507c  mov     rdx, rax; lpSubKey
0x18007507f  lea     rax, [rsp+150h+hkey]
0x180075084  mov     [rsp+150h+phkResult], rax; unsigned int
0x180075089  mov     r9d, 20019h; samDesired
0x18007508f  xor     r8d, r8d; ulOptions
0x180075092  mov     rcx, rbx; hKey
0x180075095  call    cs:__imp_RegOpenKeyExW
0x18007509b  test    eax, eax
0x18007509d  jz      short loc_1800750BC
0x18007509f  mov     rcx, [rbp+58h]; this
0x1800750a3  mov     r9d, 3F3h; char *
0x1800750a9  lea     r8, aOnecoreDsSecur_35; "onecore\\ds\\security\\ngc\\utils\\bio"...
0x1800750b0  mov     edx, 338h; void *
0x1800750b5  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x1800750ba  jmp     short loc_18007510E
0x1800750bc  mov     [rsp+150h+var_F8], 0
0x1800750c4  mov     [rsp+150h+var_F4], 4
0x1800750cc  lea     rax, [rsp+150h+var_F4]
0x1800750d1  mov     [rsp+150h+pcbData], rax; pcbData
0x1800750d6  lea     rax, [rsp+150h+var_F8]
0x1800750db  mov     [rsp+150h+pvData], rax; pvData
0x1800750e0  mov     [rsp+150h+phkResult], 0; pdwType
0x1800750e9  mov     r9d, 18h; dwFlags
0x1800750ef  lea     r8, Value; "SecureFingerprint"
0x1800750f6  xor     edx, edx; lpSubKey
0x1800750f8  mov     rcx, [rsp+150h+hkey]; hkey
0x1800750fd  call    cs:__imp_RegGetValueW
0x180075103  test    eax, eax
0x180075105  jnz     short loc_18007510E
0x180075107  cmp     [rsp+150h+var_F8], 1
0x18007510c  jz      short loc_180075151
0x18007510e  mov     rcx, [rsp+150h+hkey]; hKey
0x180075113  cmp     rcx, r15
0x180075116  jz      short loc_18007511E
0x180075118  call    cs:__imp_RegCloseKey
0x18007511e  mov     rcx, rbx; hKey
0x180075121  call    cs:__imp_RegCloseKey
0x180075127  mov     r9d, esi
0x18007512a  lea     rax, [rbp+50h+var_C0]
0x18007512e  mov     [rsp+150h+phkResult], rax
0x180075133  lea     r8, GUID_DEVINTERFACE_BIOMETRIC_READER
0x18007513a  xor     edx, edx
0x18007513c  mov     rcx, [rsp+150h+var_108]
0x180075141  call    cs:__imp_DevObjEnumDeviceInterfaces
0x180075147  test    eax, eax
0x180075149  jnz     loc_180074FF9
0x18007514f  jmp     short loc_18007516D
0x180075151  mov     dil, 1
0x180075154  mov     rcx, [rsp+150h+hkey]; hKey
0x180075159  cmp     rcx, r15
0x18007515c  jz      short loc_180075164
0x18007515e  call    cs:__imp_RegCloseKey
0x180075164  mov     rcx, rbx; hKey
0x180075167  call    cs:__imp_RegCloseKey
0x18007516d  mov     rcx, cs:g_logProvider
0x180075174  mov     eax, [rcx]
0x180075176  cmp     eax, 4
0x180075179  jbe     short loc_1800751CD
0x18007517b  mov     eax, esi
0x18007517d  mov     [rsp+150h+var_F0], rax
0x180075182  mov     [rsp+150h+var_110], dil
0x180075187  lea     rax, [rsp+150h+var_F0]
0x18007518c  mov     [rbp+50h+var_40], rax
0x180075190  mov     [rbp+50h+var_38], 8
0x180075198  lea     rax, [rsp+150h+var_110]
0x18007519d  mov     [rbp+50h+var_50], rax
0x1800751a1  mov     [rbp+50h+var_48], 1
0x1800751a9  lea     rax, [rbp+50h+var_70]
0x1800751ad  mov     [rsp+150h+pvData], rax
0x1800751b2  mov     dword ptr [rsp+150h+phkResult], 4
0x1800751ba  xor     r9d, r9d
0x1800751bd  xor     r8d, r8d
0x1800751c0  lea     rdx, word_1800B3D92
0x1800751c7  call    _tlgWriteTransfer_EventWriteTransfer
0x1800751cc  nop
0x1800751cd  lea     rcx, [rsp+150h+var_E0]
0x1800751d2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800751d7  nop
0x1800751d8  mov     rcx, [rsp+150h+var_108]
0x1800751dd  lea     rdx, [rcx-1]
0x1800751e1  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1800751e5  ja      short loc_1800751ED
0x1800751e7  call    cs:__imp_DevObjDestroyDeviceInfoList
0x1800751ed  mov     al, dil
0x1800751f0  jmp     short loc_180075223
0x1800751f2  mov     edx, 2ECh; void *
0x1800751f7  mov     rcx, [rbp+58h]; this
0x1800751fb  call    ?Log_GetLastError@in1diag3@details@wil@@YAKPEAXIPEBD@Z; wil::details::in1diag3::Log_GetLastError(void *,uint,char const *)
0x180075200  nop
0x180075201  lea     rcx, [rsp+150h+var_E0]
0x180075206  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007520b  nop
0x18007520c  mov     rcx, [rsp+150h+var_108]
0x180075211  lea     rax, [rcx-1]
0x180075215  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180075219  ja      short loc_180075221
0x18007521b  call    cs:__imp_DevObjDestroyDeviceInfoList
0x180075221  xor     al, al
0x180075223  mov     rcx, [rbp+50h+var_30]
0x180075227  xor     rcx, rsp; StackCookie
0x18007522a  call    __security_check_cookie
0x18007522f  add     rsp, 130h
0x180075236  pop     r15
0x180075238  pop     rdi
0x180075239  pop     rsi
0x18007523a  pop     rbx
0x18007523b  pop     rbp
0x18007523c  retn
```
