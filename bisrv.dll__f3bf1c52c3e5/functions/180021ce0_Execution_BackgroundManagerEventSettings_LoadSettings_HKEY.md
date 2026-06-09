# Execution::BackgroundManagerEventSettings::LoadSettings(HKEY__ *)

- ea: `0x180021ce0`
- end: `0x180022249`
- name: `?LoadSettings@BackgroundManagerEventSettings@Execution@@UEAAJPEAUHKEY__@@@Z`
- size: `1385`
- prototype: `int(Execution::BackgroundManagerEventSettings *__hidden this, HKEY)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x18001ef7c`
- `0x180021ce0`
- `0x180022250`
- `0x18009467a`
- `0x1800946a0`
- `0x180095010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180021ef2`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180021ef2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180021dd1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180021e8f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180021f45`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180021f98`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180021ff0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180022048`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180022098`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800220e8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180022139`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180021dd1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180021e8f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180021f45`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180021f98`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180021ff0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180022048`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180022098`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800220e8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180022139`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180021eb2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180021eb2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180021d8d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180021d8d`
- `ResourcePolicyClient!CreateResourcePolicyStoreClient` at `0x180021dfd`
- `ResourcePolicyClient!CreateResourcePolicyStoreClient` at `0x180021dfd`

## string_xrefs

- `0x180021e84`: `CLSID`

## pseudocode

```c
__int64 __fastcall Execution::BackgroundManagerEventSettings::LoadSettings(
        Execution::BackgroundManagerEventSettings *this,
        HKEY a2)
{
  __int64 v4; // r9
  int v5; // ebx
  LSTATUS v6; // eax
  bool v7; // cc
  __int64 v8; // rcx
  LSTATUS v10; // eax
  LSTATUS v11; // eax
  LSTATUS v12; // eax
  LSTATUS v13; // eax
  LSTATUS v14; // eax
  LSTATUS v15; // eax
  LSTATUS v16; // eax
  BYTE v17[4]; // [rsp+30h] [rbp-D0h] BYREF
  DWORD lpcbData; // [rsp+34h] [rbp-CCh] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  DWORD cbData; // [rsp+40h] [rbp-C0h] BYREF
  DWORD Type; // [rsp+44h] [rbp-BCh] BYREF
  GUID pclsid; // [rsp+48h] [rbp-B8h] BYREF
  OLECHAR Data[264]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR SubKey[264]; // [rsp+270h] [rbp+170h] BYREF

  hKey = 0;
  memset_0(SubKey, 0, 0x208u);
  memset_0(Data, 0, 0x208u);
  v4 = *((unsigned int *)this + 6);
  Type = 0;
  cbData = 0;
  v5 = StringCchPrintfW(SubKey, 0x104u, L"%d", v4);
  if ( v5 < 0 )
    goto LABEL_14;
  v6 = RegOpenKeyExW(a2, SubKey, 0, 0x20019u, &hKey);
  v5 = v6;
  v7 = v6 <= 0;
  if ( v6 )
    goto LABEL_12;
  cbData = 520;
  Type = 1;
  v6 = RegQueryValueExW(hKey, L"ResourceSetType", 0, &Type, (LPBYTE)Data, &cbData);
  v5 = v6;
  if ( v6 )
  {
    if ( v6 != 2 )
      goto LABEL_11;
  }
  else
  {
    *(_DWORD *)v17 = 57;
    *(_QWORD *)&pclsid.Data1 = 0;
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&pclsid);
    v5 = CreateResourcePolicyStoreClient(&pclsid);
    if ( v5 < 0
      || (v5 = (*(__int64 (__fastcall **)(_QWORD, OLECHAR *, _QWORD, BYTE *))(**(_QWORD **)&pclsid.Data1 + 24LL))(
                 *(_QWORD *)&pclsid.Data1,
                 Data,
                 0,
                 v17),
          v5 < 0) )
    {
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&pclsid);
      goto LABEL_14;
    }
    v8 = *(_QWORD *)&pclsid.Data1;
    *((_DWORD *)this + 7) = *(_DWORD *)v17;
    if ( v8 )
    {
      *(_QWORD *)&pclsid.Data1 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    }
  }
  cbData = 520;
  Type = 1;
  v6 = RegQueryValueExW(hKey, L"CLSID", 0, &Type, (LPBYTE)Data, &cbData);
  v5 = v6;
  if ( v6 )
  {
    if ( v6 != 2 )
    {
LABEL_11:
      v7 = v6 <= 0;
LABEL_12:
      if ( !v7 )
        v5 = (unsigned __int16)v6 | 0x80070000;
      goto LABEL_14;
    }
  }
  else
  {
    pclsid = 0;
    v5 = CLSIDFromString(Data, &pclsid);
    if ( v5 < 0 )
      goto LABEL_14;
    *(GUID *)((char *)this + 36) = pclsid;
  }
  *(_DWORD *)v17 = 0;
  lpcbData = 4;
  pclsid.Data1 = 4;
  v10 = RegQueryValueExW(hKey, L"RescheduleOnCancel", 0, &pclsid.Data1, v17, &lpcbData);
  v5 = v10;
  if ( v10 )
  {
    if ( v10 != 2 )
    {
      if ( v10 > 0 )
        v5 = (unsigned __int16)v10 | 0x80070000;
      if ( v5 < 0 )
        goto LABEL_14;
    }
  }
  else
  {
    *((_DWORD *)this + 8) = *(_DWORD *)v17;
  }
  pclsid.Data1 = 4;
  lpcbData = 4;
  *(_DWORD *)v17 = 0;
  v11 = RegQueryValueExW(hKey, L"RescheduleOnAbort", 0, &lpcbData, v17, &pclsid.Data1);
  v5 = v11;
  if ( v11 )
  {
    if ( v11 != 2 )
    {
      if ( v11 > 0 )
        v5 = (unsigned __int16)v11 | 0x80070000;
      if ( v5 < 0 )
        goto LABEL_14;
    }
  }
  else
  {
    *((_DWORD *)this + 13) = *(_DWORD *)v17;
  }
  pclsid.Data1 = 4;
  lpcbData = 4;
  *(_DWORD *)v17 = 0;
  v12 = RegQueryValueExW(hKey, L"BatterySaverOverride", 0, &lpcbData, v17, &pclsid.Data1);
  v5 = v12;
  if ( !v12 )
  {
    *((_DWORD *)this + 14) = *(_DWORD *)v17;
    goto LABEL_27;
  }
  if ( v12 == 2 )
    goto LABEL_27;
  if ( v12 > 0 )
    v5 = (unsigned __int16)v12 | 0x80070000;
  if ( v5 >= 0 )
  {
LABEL_27:
    pclsid.Data1 = 4;
    lpcbData = 4;
    *(_DWORD *)v17 = 0;
    v13 = RegQueryValueExW(hKey, L"WallClockLimitMs", 0, &lpcbData, v17, &pclsid.Data1);
    v5 = v13;
    if ( v13 )
    {
      if ( v13 != 2 )
      {
        if ( v13 > 0 )
          v5 = (unsigned __int16)v13 | 0x80070000;
        if ( v5 < 0 )
          goto LABEL_14;
      }
    }
    else
    {
      *((_DWORD *)this + 15) = *(_DWORD *)v17;
    }
    pclsid.Data1 = 4;
    lpcbData = 4;
    *(_DWORD *)v17 = 0;
    v14 = RegQueryValueExW(hKey, L"PolicyFlags", 0, &lpcbData, v17, &pclsid.Data1);
    v5 = v14;
    if ( v14 )
    {
      if ( v14 != 2 )
      {
        if ( v14 > 0 )
          v5 = (unsigned __int16)v14 | 0x80070000;
        if ( v5 < 0 )
          goto LABEL_14;
      }
    }
    else
    {
      *((_DWORD *)this + 16) = *(_DWORD *)v17;
    }
    pclsid.Data1 = 4;
    lpcbData = 4;
    *(_DWORD *)v17 = 0;
    v15 = RegQueryValueExW(hKey, L"ExecutionDisabledOverride", 0, &lpcbData, v17, &pclsid.Data1);
    v5 = v15;
    if ( v15 )
    {
      if ( v15 != 2 )
      {
        if ( v15 > 0 )
          v5 = (unsigned __int16)v15 | 0x80070000;
        if ( v5 < 0 )
          goto LABEL_14;
      }
    }
    else
    {
      *((_DWORD *)this + 17) = *(_DWORD *)v17;
    }
    pclsid.Data1 = 4;
    lpcbData = 4;
    v5 = 0;
    *(_DWORD *)v17 = 0;
    v16 = RegQueryValueExW(hKey, L"TimeCritical", 0, &lpcbData, v17, &pclsid.Data1);
    if ( v16 )
    {
      if ( v16 != 2 )
      {
        if ( v16 > 0 )
          v5 = (unsigned __int16)v16 | 0x80070000;
        else
          v5 = v16;
      }
    }
    else
    {
      *((_DWORD *)this + 18) = *(_DWORD *)v17;
    }
  }
LABEL_14:
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180021ce0  mov     [rsp-8+arg_10], rbx
0x180021ce5  push    rbp
0x180021ce6  push    rsi
0x180021ce7  push    rdi
0x180021ce8  push    r12
0x180021cea  push    r14
0x180021cec  lea     rbp, [rsp-390h]
0x180021cf4  sub     rsp, 490h
0x180021cfb  mov     rax, cs:__security_cookie
0x180021d02  xor     rax, rsp
0x180021d05  mov     [rbp+3B0h+var_30], rax
0x180021d0c  mov     rdi, rdx
0x180021d0f  mov     rsi, rcx
0x180021d12  mov     r12d, 208h
0x180021d18  lea     rcx, [rbp+3B0h+SubKey]; void *
0x180021d1f  xor     r14d, r14d
0x180021d22  mov     r8d, r12d; Size
0x180021d25  xor     edx, edx; Val
0x180021d27  mov     [rsp+4B0h+hKey], r14
0x180021d2c  call    memset_0
0x180021d31  mov     r8d, r12d; Size
0x180021d34  lea     rcx, [rsp+4B0h+Data]; void *
0x180021d39  xor     edx, edx; Val
0x180021d3b  call    memset_0
0x180021d40  mov     r9d, [rsi+18h]
0x180021d44  lea     r8, aD; "%d"
0x180021d4b  mov     edx, 104h; unsigned __int64
0x180021d50  mov     [rsp+4B0h+Type], r14d
0x180021d55  lea     rcx, [rbp+3B0h+SubKey]; unsigned __int16 *
0x180021d5c  mov     [rsp+4B0h+cbData], r14d
0x180021d61  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180021d66  mov     ebx, eax
0x180021d68  test    eax, eax
0x180021d6a  js      loc_180021EA8
0x180021d70  lea     rax, [rsp+4B0h+hKey]
0x180021d75  mov     r9d, 20019h; samDesired
0x180021d7b  xor     r8d, r8d; ulOptions
0x180021d7e  mov     [rsp+4B0h+phkResult], rax; phkResult
0x180021d83  lea     rdx, [rbp+3B0h+SubKey]; lpSubKey
0x180021d8a  mov     rcx, rdi; hKey
0x180021d8d  call    cs:__imp_RegOpenKeyExW
0x180021d93  mov     ebx, eax
0x180021d95  test    eax, eax
0x180021d97  jnz     loc_180021EA2
0x180021d9d  mov     rcx, [rsp+4B0h+hKey]; hKey
0x180021da2  lea     edi, [rax+1]
0x180021da5  lea     rax, [rsp+4B0h+cbData]
0x180021daa  mov     [rsp+4B0h+cbData], r12d
0x180021daf  mov     [rsp+4B0h+lpcbData], rax; lpcbData
0x180021db4  lea     r9, [rsp+4B0h+Type]; lpType
0x180021db9  lea     rax, [rsp+4B0h+Data]
0x180021dbe  mov     [rsp+4B0h+Type], edi
0x180021dc2  xor     r8d, r8d; lpReserved
0x180021dc5  mov     [rsp+4B0h+phkResult], rax; lpData
0x180021dca  lea     rdx, ValueName; "ResourceSetType"
0x180021dd1  call    cs:__imp_RegQueryValueExW
0x180021dd7  mov     ebx, eax
0x180021dd9  test    eax, eax
0x180021ddb  jnz     loc_180022153
0x180021de1  lea     rcx, [rsp+4B0h+pclsid]
0x180021de6  mov     dword ptr [rsp+4B0h+var_480], 39h ; '9'
0x180021dee  mov     qword ptr [rsp+4B0h+pclsid.Data1], r14
0x180021df3  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180021df8  lea     rcx, [rsp+4B0h+pclsid]
0x180021dfd  call    cs:__imp_CreateResourcePolicyStoreClient
0x180021e03  mov     ebx, eax
0x180021e05  test    eax, eax
0x180021e07  jns     short loc_180021E18
0x180021e09  lea     rcx, [rsp+4B0h+pclsid]
0x180021e0e  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180021e13  jmp     loc_180021EA8
0x180021e18  mov     rcx, qword ptr [rsp+4B0h+pclsid.Data1]
0x180021e1d  lea     r9, [rsp+4B0h+var_480]
0x180021e22  xor     r8d, r8d
0x180021e25  lea     rdx, [rsp+4B0h+Data]
0x180021e2a  mov     rax, [rcx]
0x180021e2d  mov     rax, [rax+18h]
0x180021e31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021e36  mov     ebx, eax
0x180021e38  test    eax, eax
0x180021e3a  js      short loc_180021E09
0x180021e3c  mov     rcx, qword ptr [rsp+4B0h+pclsid.Data1]
0x180021e41  mov     eax, dword ptr [rsp+4B0h+var_480]
0x180021e45  mov     [rsi+1Ch], eax
0x180021e48  test    rcx, rcx
0x180021e4b  jz      short loc_180021E5E
0x180021e4d  mov     qword ptr [rsp+4B0h+pclsid.Data1], r14
0x180021e52  mov     rax, [rcx]
0x180021e55  mov     rax, [rax+10h]
0x180021e59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021e5e  mov     rcx, [rsp+4B0h+hKey]; hKey
0x180021e63  lea     rax, [rsp+4B0h+cbData]
0x180021e68  mov     [rsp+4B0h+lpcbData], rax; lpcbData
0x180021e6d  lea     r9, [rsp+4B0h+Type]; lpType
0x180021e72  lea     rax, [rsp+4B0h+Data]
0x180021e77  mov     [rsp+4B0h+cbData], r12d
0x180021e7c  xor     r8d, r8d; lpReserved
0x180021e7f  mov     [rsp+4B0h+phkResult], rax; lpData
0x180021e84  lea     rdx, aClsid; "CLSID"
0x180021e8b  mov     [rsp+4B0h+Type], edi
0x180021e8f  call    cs:__imp_RegQueryValueExW
0x180021e95  mov     ebx, eax
0x180021e97  test    eax, eax
0x180021e99  jz      short loc_180021EE0
0x180021e9b  cmp     eax, 2
0x180021e9e  jz      short loc_180021F08
0x180021ea0  test    eax, eax
0x180021ea2  jg      loc_180022179
0x180021ea8  mov     rcx, [rsp+4B0h+hKey]; hKey
0x180021ead  test    rcx, rcx
0x180021eb0  jz      short loc_180021EB8
0x180021eb2  call    cs:__imp_RegCloseKey
0x180021eb8  mov     eax, ebx
0x180021eba  mov     rcx, [rbp+3B0h+var_30]
0x180021ec1  xor     rcx, rsp; StackCookie
0x180021ec4  call    __security_check_cookie
0x180021ec9  mov     rbx, [rsp+4B0h+arg_10]
0x180021ed1  add     rsp, 490h
0x180021ed8  pop     r14
0x180021eda  pop     r12
0x180021edc  pop     rdi
0x180021edd  pop     rsi
0x180021ede  pop     rbp
0x180021edf  retn
0x180021ee0  xorps   xmm0, xmm0
0x180021ee3  lea     rdx, [rsp+4B0h+pclsid]; pclsid
0x180021ee8  lea     rcx, [rsp+4B0h+Data]; lpsz
0x180021eed  movups  xmmword ptr [rsp+4B0h+pclsid.Data1], xmm0
0x180021ef2  call    cs:__imp_CLSIDFromString
0x180021ef8  mov     ebx, eax
0x180021efa  test    eax, eax
0x180021efc  js      short loc_180021EA8
0x180021efe  movups  xmm0, xmmword ptr [rsp+4B0h+pclsid.Data1]
0x180021f03  movdqu  xmmword ptr [rsi+24h], xmm0
0x180021f08  mov     rcx, [rsp+4B0h+hKey]; hKey
0x180021f0d  lea     rax, [rsp+4B0h+var_47C]
0x180021f12  mov     [rsp+4B0h+lpcbData], rax; lpcbData
0x180021f17  lea     r9, [rsp+4B0h+pclsid]; lpType
0x180021f1c  lea     rax, [rsp+4B0h+var_480]
0x180021f21  mov     dword ptr [rsp+4B0h+var_480], r14d
0x180021f26  mov     r12d, 4
0x180021f2c  mov     [rsp+4B0h+phkResult], rax; lpData
0x180021f31  xor     r8d, r8d; lpReserved
0x180021f34  mov     [rsp+4B0h+var_47C], r12d
0x180021f39  lea     rdx, aRescheduleonca; "RescheduleOnCancel"
0x180021f40  mov     [rsp+4B0h+pclsid.Data1], r12d
0x180021f45  call    cs:__imp_RegQueryValueExW
0x180021f4b  mov     ebx, eax
0x180021f4d  mov     edi, 80070000h
0x180021f52  test    eax, eax
0x180021f54  jnz     loc_180022187
0x180021f5a  mov     eax, dword ptr [rsp+4B0h+var_480]
0x180021f5e  mov     [rsi+20h], eax
0x180021f61  mov     rcx, [rsp+4B0h+hKey]; hKey
0x180021f66  lea     rax, [rsp+4B0h+pclsid]
0x180021f6b  mov     [rsp+4B0h+lpcbData], rax; lpcbData
0x180021f70  lea     r9, [rsp+4B0h+var_47C]; lpType
0x180021f75  lea     rax, [rsp+4B0h+var_480]
0x180021f7a  mov     [rsp+4B0h+pclsid.Data1], r12d
0x180021f7f  xor     r8d, r8d; lpReserved
0x180021f82  mov     [rsp+4B0h+phkResult], rax; lpData
0x180021f87  lea     rdx, aRescheduleonab; "RescheduleOnAbort"
0x180021f8e  mov     [rsp+4B0h+var_47C], r12d
0x180021f93  mov     dword ptr [rsp+4B0h+var_480], r14d
0x180021f98  call    cs:__imp_RegQueryValueExW
0x180021f9e  mov     ebx, eax
0x180021fa0  test    eax, eax
0x180021fa2  jnz     loc_1800221A6
0x180021fa8  mov     eax, dword ptr [rsp+4B0h+var_480]
0x180021fac  mov     [rsi+34h], eax
0x180021faf  jmp     short loc_180021FB9
0x180021fb1  test    ebx, ebx
0x180021fb3  js      loc_180021EA8
0x180021fb9  mov     rcx, [rsp+4B0h+hKey]; hKey
0x180021fbe  lea     rax, [rsp+4B0h+pclsid]
0x180021fc3  mov     [rsp+4B0h+lpcbData], rax; lpcbData
0x180021fc8  lea     r9, [rsp+4B0h+var_47C]; lpType
0x180021fcd  lea     rax, [rsp+4B0h+var_480]
0x180021fd2  mov     [rsp+4B0h+pclsid.Data1], r12d
0x180021fd7  xor     r8d, r8d; lpReserved
0x180021fda  mov     [rsp+4B0h+phkResult], rax; lpData
0x180021fdf  lea     rdx, aBatterysaverov; "BatterySaverOverride"
0x180021fe6  mov     [rsp+4B0h+var_47C], r12d
0x180021feb  mov     dword ptr [rsp+4B0h+var_480], r14d
0x180021ff0  call    cs:__imp_RegQueryValueExW
0x180021ff6  mov     ebx, eax
0x180021ff8  test    eax, eax
0x180021ffa  jnz     loc_1800221C1
0x180022000  mov     eax, dword ptr [rsp+4B0h+var_480]
0x180022004  mov     [rsi+38h], eax
0x180022007  jmp     short loc_180022011
0x180022009  test    ebx, ebx
0x18002200b  js      loc_180021EA8
0x180022011  mov     rcx, [rsp+4B0h+hKey]; hKey
0x180022016  lea     rax, [rsp+4B0h+pclsid]
0x18002201b  mov     [rsp+4B0h+lpcbData], rax; lpcbData
0x180022020  lea     r9, [rsp+4B0h+var_47C]; lpType
0x180022025  lea     rax, [rsp+4B0h+var_480]
0x18002202a  mov     [rsp+4B0h+pclsid.Data1], r12d
0x18002202f  xor     r8d, r8d; lpReserved
0x180022032  mov     [rsp+4B0h+phkResult], rax; lpData
0x180022037  lea     rdx, aWallclocklimit; "WallClockLimitMs"
0x18002203e  mov     [rsp+4B0h+var_47C], r12d
0x180022043  mov     dword ptr [rsp+4B0h+var_480], r14d
0x180022048  call    cs:__imp_RegQueryValueExW
0x18002204e  mov     ebx, eax
0x180022050  test    eax, eax
0x180022052  jz      loc_180022161
0x180022058  cmp     eax, 2
0x18002205b  jnz     loc_180022229
0x180022061  mov     rcx, [rsp+4B0h+hKey]; hKey
0x180022066  lea     rax, [rsp+4B0h+pclsid]
0x18002206b  mov     [rsp+4B0h+lpcbData], rax; lpcbData
0x180022070  lea     r9, [rsp+4B0h+var_47C]; lpType
0x180022075  lea     rax, [rsp+4B0h+var_480]
0x18002207a  mov     [rsp+4B0h+pclsid.Data1], r12d
0x18002207f  xor     r8d, r8d; lpReserved
0x180022082  mov     [rsp+4B0h+phkResult], rax; lpData
0x180022087  lea     rdx, aPolicyflags; "PolicyFlags"
0x18002208e  mov     [rsp+4B0h+var_47C], r12d
0x180022093  mov     dword ptr [rsp+4B0h+var_480], r14d
0x180022098  call    cs:__imp_RegQueryValueExW
0x18002209e  mov     ebx, eax
0x1800220a0  test    eax, eax
0x1800220a2  jz      loc_18002216D
0x1800220a8  cmp     eax, 2
0x1800220ab  jnz     loc_180022234
0x1800220b1  mov     rcx, [rsp+4B0h+hKey]; hKey
0x1800220b6  lea     rax, [rsp+4B0h+pclsid]
0x1800220bb  mov     [rsp+4B0h+lpcbData], rax; lpcbData
0x1800220c0  lea     r9, [rsp+4B0h+var_47C]; lpType
0x1800220c5  lea     rax, [rsp+4B0h+var_480]
0x1800220ca  mov     [rsp+4B0h+pclsid.Data1], r12d
0x1800220cf  xor     r8d, r8d; lpReserved
0x1800220d2  mov     [rsp+4B0h+phkResult], rax; lpData
0x1800220d7  lea     rdx, aExecutiondisab; "ExecutionDisabledOverride"
0x1800220de  mov     [rsp+4B0h+var_47C], r12d
0x1800220e3  mov     dword ptr [rsp+4B0h+var_480], r14d
0x1800220e8  call    cs:__imp_RegQueryValueExW
0x1800220ee  mov     ebx, eax
0x1800220f0  test    eax, eax
0x1800220f2  jnz     loc_1800221DC
0x1800220f8  mov     eax, dword ptr [rsp+4B0h+var_480]
0x1800220fc  mov     [rsi+44h], eax
0x1800220ff  mov     rcx, [rsp+4B0h+hKey]; hKey
0x180022104  lea     rax, [rsp+4B0h+pclsid]
0x180022109  mov     [rsp+4B0h+lpcbData], rax; lpcbData
0x18002210e  lea     r9, [rsp+4B0h+var_47C]; lpType
0x180022113  lea     rax, [rsp+4B0h+var_480]
0x180022118  mov     [rsp+4B0h+pclsid.Data1], r12d
0x18002211d  xor     r8d, r8d; lpReserved
0x180022120  mov     [rsp+4B0h+phkResult], rax; lpData
0x180022125  lea     rdx, aTimecritical; "TimeCritical"
0x18002212c  mov     [rsp+4B0h+var_47C], r12d
0x180022131  mov     ebx, r14d
0x180022134  mov     dword ptr [rsp+4B0h+var_480], r14d
0x180022139  call    cs:__imp_RegQueryValueExW
0x18002213f  test    eax, eax
0x180022141  jnz     loc_1800221FB
0x180022147  mov     eax, dword ptr [rsp+4B0h+var_480]
0x18002214b  mov     [rsi+48h], eax
0x18002214e  jmp     loc_180021EA8
0x180022153  cmp     eax, 2
0x180022156  jz      loc_180021E5E
0x18002215c  jmp     loc_180021EA0
0x180022161  mov     eax, dword ptr [rsp+4B0h+var_480]
0x180022165  mov     [rsi+3Ch], eax
0x180022168  jmp     loc_180022061
0x18002216d  mov     eax, dword ptr [rsp+4B0h+var_480]
0x180022171  mov     [rsi+40h], eax
0x180022174  jmp     loc_1800220B1
0x180022179  movzx   ebx, ax
0x18002217c  or      ebx, 80070000h
0x180022182  jmp     loc_180021EA8
0x180022187  cmp     eax, 2
0x18002218a  jz      loc_180021F61
0x180022190  test    eax, eax
0x180022192  jle     short loc_180022199
0x180022194  movzx   ebx, ax
0x180022197  or      ebx, edi
0x180022199  test    ebx, ebx
0x18002219b  jns     loc_180021F61
0x1800221a1  jmp     loc_180021EA8
0x1800221a6  cmp     eax, 2
0x1800221a9  jz      loc_180021FB9
0x1800221af  test    eax, eax
0x1800221b1  jle     loc_180021FB1
0x1800221b7  movzx   ebx, ax
0x1800221ba  or      ebx, edi
0x1800221bc  jmp     loc_180021FB1
0x1800221c1  cmp     eax, 2
0x1800221c4  jz      loc_180022011
0x1800221ca  test    eax, eax
0x1800221cc  jle     loc_180022009
0x1800221d2  movzx   ebx, ax
0x1800221d5  or      ebx, edi
0x1800221d7  jmp     loc_180022009
0x1800221dc  cmp     eax, 2
0x1800221df  jz      loc_1800220FF
0x1800221e5  test    eax, eax
  ... truncated ...
```
