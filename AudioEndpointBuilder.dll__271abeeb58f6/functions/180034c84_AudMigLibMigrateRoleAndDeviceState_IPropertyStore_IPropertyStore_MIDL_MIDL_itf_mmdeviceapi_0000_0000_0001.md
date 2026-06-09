# AudMigLibMigrateRoleAndDeviceState(IPropertyStore *,IPropertyStore *,__MIDL___MIDL_itf_mmdeviceapi_0000_0000_0001)

- ea: `0x180034c84`
- end: `0x180034ef5`
- name: `?AudMigLibMigrateRoleAndDeviceState@@YAJPEAUIPropertyStore@@0W4__MIDL___MIDL_itf_mmdeviceapi_0000_0000_0001@@@Z`
- size: `625`
- prototype: `__int64 __fastcall(struct IPropertyStore *, struct IPropertyStore *, enum __MIDL___MIDL_itf_mmdeviceapi_0000_0000_0001)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x18004f474`

## callees

- `0x180012e80`
- `0x180034c84`
- `0x180034efc`
- `0x18003e920`
- `0x18005a928`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180034e50`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180034e60`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180034e50`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180034e60`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180034eda`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180034eda`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180034d65`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180034da5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180034d65`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180034da5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180034dda`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180034e21`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180034dda`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180034e21`

## string_xrefs

- `0x180034d07`: `Failed to GetRegPathForEndpoint with Hresult 0x%lx\n`
- `0x180034d7c`: `RegOpenKeyEx failed with hresult code 0x%lx\n`
- `0x180034e9f`: `Failed to copy role and device state settings 0x%lx\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall AudMigLibMigrateRoleAndDeviceState(
        struct IPropertyStore *a1,
        struct IPropertyStore *a2,
        enum __MIDL___MIDL_itf_mmdeviceapi_0000_0000_0001 a3)
{
  int RegPathForEndpoint; // eax
  unsigned __int64 v6; // r8
  unsigned int v7; // ebx
  LSTATUS v8; // eax
  bool v9; // cc
  const unsigned __int16 *v10; // rcx
  LSTATUS v11; // eax
  LSTATUS v12; // eax
  int v14; // eax
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  BYTE Data[4]; // [rsp+34h] [rbp-CCh] BYREF
  BYTE v17[8]; // [rsp+38h] [rbp-C8h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  HKEY phkResult; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR SubKey[264]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR v21[264]; // [rsp+260h] [rbp+160h] BYREF

  phkResult = 0;
  hKey = 0;
  *(_DWORD *)v17 = 0;
  *(_DWORD *)Data = 0;
  SubKey[0] = 0;
  cbData = 4;
  v21[0] = 0;
  RegPathForEndpoint = GetRegPathForEndpoint(a2, SubKey, (unsigned __int64)a2, a3);
  v7 = RegPathForEndpoint;
  if ( RegPathForEndpoint < 0
    || (RegPathForEndpoint = GetRegPathForEndpoint(a1, v21, v6, a3), v7 = RegPathForEndpoint, RegPathForEndpoint < 0) )
  {
    AudMigLibSetupLog(L"Failed to GetRegPathForEndpoint with Hresult 0x%lx\r\n", (unsigned int)RegPathForEndpoint);
    goto LABEL_18;
  }
  AudMigLibSetupLog(L"Migrating role and device state from %s to %s\r\n", SubKey, v21);
  v8 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &phkResult);
  v7 = v8;
  v9 = v8 <= 0;
  if ( v8 || (v8 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v21, 0, 0x2001Fu, &hKey), v7 = v8, v9 = v8 <= 0, v8) )
  {
    if ( !v9 )
      v7 = (unsigned __int16)v8 | 0x80070000;
    v10 = L"RegOpenKeyEx failed with hresult code 0x%lx\r\n";
    goto LABEL_17;
  }
  v11 = RegQueryValueExW(hKey, L"DeviceState", 0, 0, Data, &cbData);
  v7 = v11;
  if ( v11 )
  {
    if ( v11 > 0 )
      v7 = (unsigned __int16)v11 | 0x80070000;
    v10 = L"Retrieving destination state failed with hresult code 0x%lx\r\n";
    goto LABEL_17;
  }
  cbData = 4;
  v12 = RegQueryValueExW(phkResult, L"DeviceState", 0, 0, v17, &cbData);
  v7 = v12;
  if ( v12 )
  {
    if ( v12 <= 0 )
    {
LABEL_16:
      v10 = L"Retrieving source state failed with hresult code 0x%lx\r\n";
LABEL_17:
      AudMigLibSetupLog(v10, v7);
      goto LABEL_18;
    }
LABEL_15:
    v7 = (unsigned __int16)v12 | 0x80070000;
    goto LABEL_16;
  }
  v14 = AudMigLibCopyRegistrySettings(phkResult, hKey, 0);
  v7 = v14;
  if ( v14 < 0 )
    AudMigLibSetupLog(L"Failed to copy role and device state settings 0x%lx\r\n", (unsigned int)v14);
  *(_DWORD *)Data |= *(_DWORD *)v17 & 0x10000000;
  cbData = 4;
  v12 = RegSetValueExW(hKey, L"DeviceState", 0, 4u, Data, 4u);
  if ( v12 )
  {
    if ( v12 <= 0 )
    {
      v7 = v12;
      goto LABEL_16;
    }
    goto LABEL_15;
  }
LABEL_18:
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( hKey )
    RegCloseKey(hKey);
  return v7;
}

```

## disassembly

```asm
0x180034c84  push    rbp
0x180034c86  push    rbx
0x180034c87  push    rsi
0x180034c88  push    rdi
0x180034c89  push    r15
0x180034c8b  lea     rbp, [rsp-380h]
0x180034c93  sub     rsp, 480h
0x180034c9a  mov     rax, cs:__security_cookie
0x180034ca1  xor     rax, rsp
0x180034ca4  mov     [rbp+3A0h+var_30], rax
0x180034cab  mov     edi, r8d
0x180034cae  mov     [rsp+4A0h+var_458], 0
0x180034cb7  mov     r8, rdx; unsigned __int64
0x180034cba  mov     [rsp+4A0h+hKey], 0
0x180034cc3  xor     eax, eax
0x180034cc5  mov     dword ptr [rsp+4A0h+var_468], 0
0x180034ccd  mov     rsi, rcx
0x180034cd0  mov     dword ptr [rsp+4A0h+Data], 0
0x180034cd8  mov     r15d, 4
0x180034cde  mov     [rsp+4A0h+SubKey], ax
0x180034ce3  mov     rcx, r8; struct IPropertyStore *
0x180034ce6  mov     [rsp+4A0h+cbData], r15d
0x180034ceb  mov     r9d, edi; enum __MIDL___MIDL_itf_mmdeviceapi_0000_0000_0001
0x180034cee  mov     [rbp+3A0h+var_240], ax
0x180034cf5  lea     rdx, [rsp+4A0h+SubKey]; unsigned __int16 *
0x180034cfa  call    ?GetRegPathForEndpoint@@YAJPEAUIPropertyStore@@PEAG_KW4__MIDL___MIDL_itf_mmdeviceapi_0000_0000_0001@@@Z; GetRegPathForEndpoint(IPropertyStore *,ushort *,unsigned __int64,__MIDL___MIDL_itf_mmdeviceapi_0000_0000_0001)
0x180034cff  mov     ebx, eax
0x180034d01  test    eax, eax
0x180034d03  jns     short loc_180034D13
0x180034d05  mov     edx, eax
0x180034d07  lea     rcx, aFailedToGetreg; "Failed to GetRegPathForEndpoint with Hr"...
0x180034d0e  jmp     loc_180034E41
0x180034d13  mov     r9d, edi; enum __MIDL___MIDL_itf_mmdeviceapi_0000_0000_0001
0x180034d16  lea     rdx, [rbp+3A0h+var_240]; unsigned __int16 *
0x180034d1d  mov     rcx, rsi; struct IPropertyStore *
0x180034d20  call    ?GetRegPathForEndpoint@@YAJPEAUIPropertyStore@@PEAG_KW4__MIDL___MIDL_itf_mmdeviceapi_0000_0000_0001@@@Z; GetRegPathForEndpoint(IPropertyStore *,ushort *,unsigned __int64,__MIDL___MIDL_itf_mmdeviceapi_0000_0000_0001)
0x180034d25  mov     ebx, eax
0x180034d27  test    eax, eax
0x180034d29  js      short loc_180034D05
0x180034d2b  lea     r8, [rbp+3A0h+var_240]
0x180034d32  lea     rdx, [rsp+4A0h+SubKey]
0x180034d37  lea     rcx, aMigratingRoleA; "Migrating role and device state from %s"...
0x180034d3e  call    ?AudMigLibSetupLog@@YAXPEBGZZ; AudMigLibSetupLog(ushort const *,...)
0x180034d43  lea     rax, [rsp+4A0h+var_458]
0x180034d48  mov     rdi, 0FFFFFFFF80000002h
0x180034d4f  mov     rcx, rdi; hKey
0x180034d52  mov     [rsp+4A0h+phkResult], rax; phkResult
0x180034d57  mov     r9d, 20019h; samDesired
0x180034d5d  lea     rdx, [rsp+4A0h+SubKey]; lpSubKey
0x180034d62  xor     r8d, r8d; ulOptions
0x180034d65  call    cs:__imp_RegOpenKeyExW
0x180034d6b  mov     ebx, eax
0x180034d6d  test    eax, eax
0x180034d6f  jz      short loc_180034D88
0x180034d71  jle     short loc_180034D7C
0x180034d73  movzx   ebx, ax
0x180034d76  or      ebx, 80070000h
0x180034d7c  lea     rcx, aRegopenkeyexFa; "RegOpenKeyEx failed with hresult code 0"...
0x180034d83  jmp     loc_180034E3F
0x180034d88  lea     rax, [rsp+4A0h+hKey]
0x180034d8d  mov     r9d, 2001Fh; samDesired
0x180034d93  xor     r8d, r8d; ulOptions
0x180034d96  mov     [rsp+4A0h+phkResult], rax; phkResult
0x180034d9b  lea     rdx, [rbp+3A0h+var_240]; lpSubKey
0x180034da2  mov     rcx, rdi; hKey
0x180034da5  call    cs:__imp_RegOpenKeyExW
0x180034dab  mov     ebx, eax
0x180034dad  test    eax, eax
0x180034daf  jnz     short loc_180034D71
0x180034db1  mov     rcx, [rsp+4A0h+hKey]; hKey
0x180034db6  lea     rax, [rsp+4A0h+cbData]
0x180034dbb  mov     [rsp+4A0h+lpcbData], rax; lpcbData
0x180034dc0  lea     rdi, aDevicestate; "DeviceState"
0x180034dc7  lea     rax, [rsp+4A0h+Data]
0x180034dcc  xor     r9d, r9d; lpType
0x180034dcf  xor     r8d, r8d; lpReserved
0x180034dd2  mov     [rsp+4A0h+phkResult], rax; lpData
0x180034dd7  mov     rdx, rdi; lpValueName
0x180034dda  call    cs:__imp_RegQueryValueExW
0x180034de0  mov     ebx, eax
0x180034de2  test    eax, eax
0x180034de4  jz      short loc_180034DFA
0x180034de6  jle     short loc_180034DF1
0x180034de8  movzx   ebx, ax
0x180034deb  or      ebx, 80070000h
0x180034df1  lea     rcx, aRetrievingDest; "Retrieving destination state failed wit"...
0x180034df8  jmp     short loc_180034E3F
0x180034dfa  mov     rcx, [rsp+4A0h+var_458]; hKey
0x180034dff  lea     rax, [rsp+4A0h+cbData]
0x180034e04  mov     [rsp+4A0h+lpcbData], rax; lpcbData
0x180034e09  xor     r9d, r9d; lpType
0x180034e0c  lea     rax, [rsp+4A0h+var_468]
0x180034e11  mov     [rsp+4A0h+cbData], r15d
0x180034e16  xor     r8d, r8d; lpReserved
0x180034e19  mov     [rsp+4A0h+phkResult], rax; lpData
0x180034e1e  mov     rdx, rdi; lpValueName
0x180034e21  call    cs:__imp_RegQueryValueExW
0x180034e27  mov     ebx, eax
0x180034e29  test    eax, eax
0x180034e2b  jz      short loc_180034E85
0x180034e2d  jle     short loc_180034E38
0x180034e2f  movzx   ebx, ax
0x180034e32  or      ebx, 80070000h
0x180034e38  lea     rcx, aRetrievingSour; "Retrieving source state failed with hre"...
0x180034e3f  mov     edx, ebx
0x180034e41  call    ?AudMigLibSetupLog@@YAXPEBGZZ; AudMigLibSetupLog(ushort const *,...)
0x180034e46  mov     rcx, [rsp+4A0h+var_458]; hKey
0x180034e4b  test    rcx, rcx
0x180034e4e  jz      short loc_180034E56
0x180034e50  call    cs:__imp_RegCloseKey
0x180034e56  mov     rcx, [rsp+4A0h+hKey]; hKey
0x180034e5b  test    rcx, rcx
0x180034e5e  jz      short loc_180034E66
0x180034e60  call    cs:__imp_RegCloseKey
0x180034e66  mov     eax, ebx
0x180034e68  mov     rcx, [rbp+3A0h+var_30]
0x180034e6f  xor     rcx, rsp; StackCookie
0x180034e72  call    __security_check_cookie
0x180034e77  add     rsp, 480h
0x180034e7e  pop     r15
0x180034e80  pop     rdi
0x180034e81  pop     rsi
0x180034e82  pop     rbx
0x180034e83  pop     rbp
0x180034e84  retn
0x180034e85  mov     rdx, [rsp+4A0h+hKey]; HKEY
0x180034e8a  xor     r8d, r8d; int
0x180034e8d  mov     rcx, [rsp+4A0h+var_458]; HKEY
0x180034e92  call    ?AudMigLibCopyRegistrySettings@@YAJPEAUHKEY__@@0H@Z; AudMigLibCopyRegistrySettings(HKEY__ *,HKEY__ *,int)
0x180034e97  mov     ebx, eax
0x180034e99  test    eax, eax
0x180034e9b  jns     short loc_180034EAB
0x180034e9d  mov     edx, eax
0x180034e9f  lea     rcx, aFailedToCopyRo; "Failed to copy role and device state se"...
0x180034ea6  call    ?AudMigLibSetupLog@@YAXPEBGZZ; AudMigLibSetupLog(ushort const *,...)
0x180034eab  mov     eax, dword ptr [rsp+4A0h+var_468]
0x180034eaf  mov     r9d, r15d; dwType
0x180034eb2  mov     rcx, [rsp+4A0h+hKey]; hKey
0x180034eb7  and     eax, 10000000h
0x180034ebc  or      dword ptr [rsp+4A0h+Data], eax
0x180034ec0  xor     r8d, r8d; Reserved
0x180034ec3  lea     rax, [rsp+4A0h+Data]
0x180034ec8  mov     dword ptr [rsp+4A0h+lpcbData], r15d; cbData
0x180034ecd  mov     rdx, rdi; lpValueName
0x180034ed0  mov     [rsp+4A0h+phkResult], rax; lpData
0x180034ed5  mov     [rsp+4A0h+cbData], r15d
0x180034eda  call    cs:__imp_RegSetValueExW
0x180034ee0  test    eax, eax
0x180034ee2  jz      loc_180034E46
0x180034ee8  jg      loc_180034E2F
0x180034eee  mov     ebx, eax
0x180034ef0  jmp     loc_180034E38
```
