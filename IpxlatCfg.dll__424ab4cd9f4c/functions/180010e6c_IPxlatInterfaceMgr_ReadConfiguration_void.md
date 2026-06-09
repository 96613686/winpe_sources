# IPxlatInterfaceMgr::ReadConfiguration(void)

- ea: `0x180010e6c`
- end: `0x180011095`
- name: `?ReadConfiguration@IPxlatInterfaceMgr@@AEAAKXZ`
- size: `553`
- prototype: `__int64 __fastcall(IPxlatInterfaceMgr *this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000ea3c`

## callees

- `0x180001d40`
- `0x18000c224`
- `0x180010e6c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180010f8d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180010f8d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180010f16`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180010f16`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011070`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011070`

## string_xrefs

- `0x180010e9b`: `System\CurrentControlSet\Services\IpxlatCfgSvc`
- `0x180010f3f`: `Failed to read Config registry Key`
- `0x180011029`: `Failed to read registry value`
- `0x180010fe0`: `Invalid Registry Setting. Either GetPrefixInfoFromDns or GetPrefixInfoFromRa should be set`

## pseudocode

```c
__int64 __fastcall IPxlatInterfaceMgr::ReadConfiguration(IPxlatInterfaceMgr *this)
{
  LSTATUS v2; // eax
  __int64 v3; // rcx
  __int64 v4; // r8
  unsigned int v5; // ebx
  BYTE *p_cbData; // rax
  int v7; // esi
  LSTATUS v8; // eax
  int v9; // edx
  BYTE Data[8]; // [rsp+30h] [rbp-69h] BYREF
  DWORD cbData; // [rsp+38h] [rbp-61h] BYREF
  int v13; // [rsp+40h] [rbp-59h] BYREF
  unsigned int v14; // [rsp+44h] [rbp-55h] BYREF
  int v15; // [rsp+48h] [rbp-51h] BYREF
  int v16; // [rsp+4Ch] [rbp-4Dh] BYREF
  HKEY hKey; // [rsp+50h] [rbp-49h] BYREF
  LSTATUS v18; // [rsp+58h] [rbp-41h] BYREF
  LPCWSTR lpValueName[4]; // [rsp+60h] [rbp-39h]
  _QWORD v20[2]; // [rsp+80h] [rbp-19h] BYREF
  const char *v21; // [rsp+90h] [rbp-9h]
  __int64 v22; // [rsp+98h] [rbp-1h]
  BYTE *v23; // [rsp+A0h] [rbp+7h]
  __int64 v24; // [rsp+A8h] [rbp+Fh]

  v20[0] = &v15;
  v15 = 0;
  v20[1] = &v13;
  v13 = 0;
  v21 = (const char *)&v14;
  v14 = 0;
  v22 = (__int64)&v16;
  v16 = 0;
  lpValueName[0] = L"PermitNonCellularCLAT";
  hKey = 0;
  lpValueName[1] = L"GetPrefixInfoFromDNS";
  lpValueName[2] = L"GetPrefixInfoFromRA";
  lpValueName[3] = L"DisableDnsQueryNetworkServers";
  v2 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Services\\IpxlatCfgSvc", 0, 0x20019u, &hKey);
  v5 = v2;
  if ( v2 )
  {
    if ( v2 == 2 )
    {
      v5 = 0;
    }
    else if ( (Microsoft_Windows_IPxlatCfgEnableBits & 1) != 0 )
    {
      *(_DWORD *)Data = v2;
      v21 = "Failed to read Config registry Key";
      p_cbData = Data;
      v22 = 35;
      goto LABEL_20;
    }
    goto LABEL_21;
  }
  v7 = 0;
  while ( 1 )
  {
    *(_DWORD *)Data = 0;
    cbData = 4;
    v8 = RegQueryValueExW(hKey, lpValueName[v7], 0, 0, Data, &cbData);
    v5 = v8;
    if ( v8 )
      break;
    *(_DWORD *)v20[v7] = *(_DWORD *)Data != 0;
LABEL_11:
    if ( (unsigned int)++v7 >= 4 )
    {
      v9 = v15;
      v3 = v14;
      if ( !v15 || v13 || v14 )
      {
        *((_DWORD *)this + 37) = v13;
        *((_DWORD *)this + 39) = v16;
        *((_DWORD *)this + 36) = v9;
        *((_DWORD *)this + 38) = v3;
        goto LABEL_21;
      }
      v5 = 87;
      if ( (Microsoft_Windows_IPxlatCfgEnableBits & 1) == 0 )
        goto LABEL_21;
      cbData = 87;
      v21 = "Invalid Registry Setting. Either GetPrefixInfoFromDns or GetPrefixInfoFromRa should be set";
      p_cbData = (BYTE *)&cbData;
      v22 = 91;
      goto LABEL_20;
    }
  }
  if ( v8 == 2 )
  {
    v5 = 0;
    goto LABEL_11;
  }
  if ( (Microsoft_Windows_IPxlatCfgEnableBits & 1) == 0 )
    goto LABEL_21;
  v18 = v8;
  v21 = "Failed to read registry value";
  p_cbData = (BYTE *)&v18;
  v22 = 30;
LABEL_20:
  v23 = p_cbData;
  v24 = 4;
  McGenEventWrite_EventWriteTransfer(v3, IPXLATCFG_ERROR_EVENT, v4, 3, v20);
LABEL_21:
  if ( hKey )
    RegCloseKey(hKey);
  return v5;
}

```

## disassembly

```asm
0x180010e6c  push    rbp
0x180010e6e  push    rbx
0x180010e6f  push    rsi
0x180010e70  push    r12
0x180010e72  push    r14
0x180010e74  push    r15
0x180010e76  lea     rbp, [rsp-2Fh]
0x180010e7b  sub     rsp, 0C8h
0x180010e82  mov     rax, cs:__security_cookie
0x180010e89  xor     rax, rsp
0x180010e8c  mov     [rbp+57h+var_40], rax
0x180010e90  xor     r12d, r12d
0x180010e93  lea     rax, [rbp+57h+var_A8]
0x180010e97  mov     [rbp+57h+var_70], rax
0x180010e9b  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\Ip"...
0x180010ea2  lea     rax, [rbp+57h+var_B0]
0x180010ea6  mov     [rbp+57h+var_A8], r12d
0x180010eaa  mov     [rbp+57h+var_68], rax
0x180010eae  mov     r14, rcx
0x180010eb1  lea     rax, [rbp+57h+var_AC]
0x180010eb5  mov     [rbp+57h+var_B0], r12d
0x180010eb9  mov     [rbp+57h+var_60], rax
0x180010ebd  mov     r9d, 20019h; samDesired
0x180010ec3  lea     rax, [rbp+57h+var_A4]
0x180010ec7  mov     [rbp+57h+var_AC], r12d
0x180010ecb  mov     [rbp+57h+var_58], rax
0x180010ecf  xor     r8d, r8d; ulOptions
0x180010ed2  lea     rax, aPermitnoncellu; "PermitNonCellularCLAT"
0x180010ed9  mov     [rbp+57h+var_A4], r12d
0x180010edd  mov     [rbp+57h+lpValueName], rax
0x180010ee1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180010ee8  lea     rax, aGetprefixinfof; "GetPrefixInfoFromDNS"
0x180010eef  mov     [rbp+57h+hKey], r12
0x180010ef3  mov     [rbp+57h+var_88], rax
0x180010ef7  lea     rax, aGetprefixinfof_1; "GetPrefixInfoFromRA"
0x180010efe  mov     [rbp+57h+var_80], rax
0x180010f02  lea     rax, aDisablednsquer; "DisableDnsQueryNetworkServers"
0x180010f09  mov     [rbp+57h+var_78], rax
0x180010f0d  lea     rax, [rbp+57h+hKey]
0x180010f11  mov     [rsp+0F0h+phkResult], rax; phkResult
0x180010f16  call    cs:__imp_RegOpenKeyExW
0x180010f1c  mov     ebx, eax
0x180010f1e  test    eax, eax
0x180010f20  jz      short loc_180010F5B
0x180010f22  cmp     eax, 2
0x180010f25  jnz     short loc_180010F2F
0x180010f27  mov     ebx, r12d
0x180010f2a  jmp     loc_180011067
0x180010f2f  test    byte ptr cs:Microsoft_Windows_IPxlatCfgEnableBits, 1
0x180010f36  jz      loc_180011067
0x180010f3c  mov     dword ptr [rbp+57h+Data], eax
0x180010f3f  lea     rax, aFailedToReadCo_0; "Failed to read Config registry Key"
0x180010f46  mov     [rbp+57h+var_60], rax
0x180010f4a  lea     rax, [rbp+57h+Data]
0x180010f4e  mov     [rbp+57h+var_58], 23h ; '#'
0x180010f56  jmp     loc_180011040
0x180010f5b  mov     esi, r12d
0x180010f5e  mov     rcx, [rbp+57h+hKey]; hKey
0x180010f62  lea     rax, [rbp+57h+cbData]
0x180010f66  mov     [rsp+0F0h+lpcbData], rax; lpcbData
0x180010f6b  xor     r9d, r9d; lpType
0x180010f6e  lea     rax, [rbp+57h+Data]
0x180010f72  mov     r15d, esi
0x180010f75  xor     r8d, r8d; lpReserved
0x180010f78  mov     dword ptr [rbp+57h+Data], r12d
0x180010f7c  mov     [rbp+57h+cbData], 4
0x180010f83  mov     [rsp+0F0h+phkResult], rax; lpData
0x180010f88  mov     rdx, [rbp+r15*8+57h+lpValueName]; lpValueName
0x180010f8d  call    cs:__imp_RegQueryValueExW
0x180010f93  mov     ebx, eax
0x180010f95  test    eax, eax
0x180010f97  jnz     short loc_180010FAC
0x180010f99  cmp     dword ptr [rbp+57h+Data], r12d
0x180010f9d  mov     edx, r12d
0x180010fa0  mov     rcx, [rbp+r15*8+57h+var_70]
0x180010fa5  setnbe  dl
0x180010fa8  mov     [rcx], edx
0x180010faa  jmp     short loc_180010FB4
0x180010fac  cmp     eax, 2
0x180010faf  jnz     short loc_18001101D
0x180010fb1  mov     ebx, r12d
0x180010fb4  inc     esi
0x180010fb6  cmp     esi, 4
0x180010fb9  jb      short loc_180010F5E
0x180010fbb  mov     edx, [rbp+57h+var_A8]
0x180010fbe  mov     eax, [rbp+57h+var_B0]
0x180010fc1  mov     ecx, [rbp+57h+var_AC]
0x180010fc4  test    edx, edx
0x180010fc6  jz      short loc_180010FFC
0x180010fc8  test    eax, eax
0x180010fca  jnz     short loc_180010FFC
0x180010fcc  test    ecx, ecx
0x180010fce  jnz     short loc_180010FFC
0x180010fd0  test    byte ptr cs:Microsoft_Windows_IPxlatCfgEnableBits, 1
0x180010fd7  lea     ebx, [rax+57h]
0x180010fda  jz      loc_180011067
0x180010fe0  lea     rax, aInvalidRegistr; "Invalid Registry Setting. Either GetPre"...
0x180010fe7  mov     [rbp+57h+cbData], ebx
0x180010fea  mov     [rbp+57h+var_60], rax
0x180010fee  lea     rax, [rbp+57h+cbData]
0x180010ff2  mov     [rbp+57h+var_58], 5Bh ; '['
0x180010ffa  jmp     short loc_180011040
0x180010ffc  mov     [r14+94h], eax
0x180011003  mov     eax, [rbp+57h+var_A4]
0x180011006  mov     [r14+9Ch], eax
0x18001100d  mov     [r14+90h], edx
0x180011014  mov     [r14+98h], ecx
0x18001101b  jmp     short loc_180011067
0x18001101d  test    byte ptr cs:Microsoft_Windows_IPxlatCfgEnableBits, 1
0x180011024  jz      short loc_180011067
0x180011026  mov     [rbp+57h+var_98], eax
0x180011029  lea     rax, aFailedToReadRe; "Failed to read registry value"
0x180011030  mov     [rbp+57h+var_60], rax
0x180011034  lea     rax, [rbp+57h+var_98]
0x180011038  mov     [rbp+57h+var_58], 1Eh
0x180011040  mov     [rbp+57h+var_50], rax
0x180011044  lea     rdx, IPXLATCFG_ERROR_EVENT
0x18001104b  lea     rax, [rbp+57h+var_70]
0x18001104f  mov     [rbp+57h+var_48], 4
0x180011057  mov     r9d, 3
0x18001105d  mov     [rsp+0F0h+phkResult], rax
0x180011062  call    McGenEventWrite_EventWriteTransfer
0x180011067  mov     rcx, [rbp+57h+hKey]; hKey
0x18001106b  test    rcx, rcx
0x18001106e  jz      short loc_180011076
0x180011070  call    cs:__imp_RegCloseKey
0x180011076  mov     eax, ebx
0x180011078  mov     rcx, [rbp+57h+var_40]
0x18001107c  xor     rcx, rsp; StackCookie
0x18001107f  call    __security_check_cookie
0x180011084  add     rsp, 0C8h
0x18001108b  pop     r15
0x18001108d  pop     r14
0x18001108f  pop     r12
0x180011091  pop     rsi
0x180011092  pop     rbx
0x180011093  pop     rbp
0x180011094  retn
```
