# RemoteAppUtil::UnsubscribeRemoteWorkspace(void)

- ea: `0x18001a4f8`
- end: `0x18001a7f7`
- name: `?UnsubscribeRemoteWorkspace@RemoteAppUtil@@SAJXZ`
- size: `767`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18000dcb4`

## callees

- `0x1800065f8`
- `0x18000702c`
- `0x18000a290`
- `0x18000a3c0`
- `0x18000a6a4`
- `0x180019a88`
- `0x180019b24`
- `0x18001a3d8`
- `0x18001a4f8`
- `0x18001f420`
- `0x18001f4e0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18001a5d8`
- `ADVAPI32!RegCloseKey` at `0x18001a5d8`
- `ADVAPI32!RegEnumValueW` at `0x18001a731`
- `ADVAPI32!RegEnumValueW` at `0x18001a731`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18001a69d`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18001a69d`
- `ADVAPI32!RegOpenKeyExW` at `0x18001a58f`
- `ADVAPI32!RegOpenKeyExW` at `0x18001a58f`
- `KERNEL32!GetLastError` at `0x18001a62b`
- `KERNEL32!GetLastError` at `0x18001a6da`
- `KERNEL32!GetLastError` at `0x18001a7bd`
- `KERNEL32!GetLastError` at `0x18001a62b`
- `KERNEL32!GetLastError` at `0x18001a6da`
- `KERNEL32!GetLastError` at `0x18001a7bd`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 RemoteAppUtil::UnsubscribeRemoteWorkspace(void)
{
  LSTATUS v0; // eax
  char v1; // di
  unsigned int v2; // ebx
  char LastError; // al
  int v5; // edx
  LSTATUS v6; // eax
  DWORD i; // edi
  LSTATUS v8; // esi
  OLECHAR *v9; // rax
  int v10; // eax
  char v11; // al
  DWORD cValues; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cchValueName; // [rsp+64h] [rbp-9Ch] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v15[40]; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v16[32]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v17[80]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR ValueName[4096]; // [rsp+110h] [rbp+10h] BYREF

  hKey = 0;
  cValues = 0;
  cchValueName = 4095;
  if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_2663f27e31e039d03781a4e1bd1e8da8_Traceguids);
  v0 = RegOpenKeyExW(
         HKEY_CURRENT_USER,
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\MDM\\RemoteAppUserCookie",
         0,
         0x20019u,
         &hKey);
  v1 = v0;
  if ( v0 )
  {
    if ( v0 == 2 )
    {
      if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_2663f27e31e039d03781a4e1bd1e8da8_Traceguids);
      v2 = 0;
      goto LABEL_10;
    }
    if ( v0 > 0 )
      v2 = (unsigned __int16)v0 | 0x80070000;
    else
      v2 = v0;
    if ( WPP_GLOBAL_Control == (LPCWSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 4) == 0 )
      goto LABEL_10;
    LastError = GetLastError();
    v5 = 22;
LABEL_19:
    WPP_SF_SdD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v5,
      (unsigned int)WPP_2663f27e31e039d03781a4e1bd1e8da8_Traceguids,
      (unsigned int)L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\MDM\\RemoteAppUserCookie",
      v1,
      LastError);
    goto LABEL_10;
  }
  v6 = RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, &cValues, 0, 0, 0, 0);
  v1 = v6;
  if ( v6 )
  {
    if ( v6 > 0 )
      v2 = (unsigned __int16)v6 | 0x80070000;
    else
      v2 = v6;
    if ( WPP_GLOBAL_Control == (LPCWSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 4) == 0 )
      goto LABEL_10;
    LastError = GetLastError();
    v5 = 23;
    goto LABEL_19;
  }
  v2 = 0;
  for ( i = 0; i < cValues; ++i )
  {
    cchValueName = 4095;
    ValueName[0] = 0;
    v8 = RegEnumValueW(hKey, i, ValueName, &cchValueName, 0, 0, 0, 0);
    if ( v8 )
    {
      if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
      {
        v11 = GetLastError();
        WPP_SF_SdD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          25,
          (unsigned int)WPP_2663f27e31e039d03781a4e1bd1e8da8_Traceguids,
          (unsigned int)L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\MDM\\RemoteAppUserCookie",
          v8,
          v11);
      }
    }
    else
    {
      RemoteAppDispatchParam::RemoteAppDispatchParam((RemoteAppDispatchParam *)v16);
      std::wstring::assign(v17, ValueName);
      v9 = (OLECHAR *)std::wstring::wstring(v15, v17);
      v10 = RemoteAppUtil::UnsubscribeRemoteWorkspace(v9);
      v2 = v10;
      if ( v10 < 0 && WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          24,
          (unsigned int)WPP_2663f27e31e039d03781a4e1bd1e8da8_Traceguids,
          (unsigned int)ValueName,
          v10);
      RemoteAppDispatchParam::~RemoteAppDispatchParam((RemoteAppDispatchParam *)v16);
    }
  }
LABEL_10:
  if ( hKey )
    RegCloseKey(hKey);
  return v2;
}

```

## disassembly

```asm
0x18001a4f8  push    rbp
0x18001a4fa  push    rbx
0x18001a4fb  push    rsi
0x18001a4fc  push    rdi
0x18001a4fd  push    r12
0x18001a4ff  push    r14
0x18001a501  push    r15
0x18001a503  lea     rbp, [rsp-2020h]
0x18001a50b  mov     eax, 2120h
0x18001a510  call    _alloca_probe
0x18001a515  sub     rsp, rax
0x18001a518  mov     rax, cs:__security_cookie
0x18001a51f  xor     rax, rsp
0x18001a522  mov     [rbp+2050h+var_40], rax
0x18001a529  xor     r14d, r14d
0x18001a52c  mov     [rsp+2150h+hKey], r14
0x18001a531  mov     [rsp+2150h+cValues], r14d
0x18001a536  mov     [rsp+2150h+cchValueName], 0FFFh
0x18001a53e  lea     r15, WPP_GLOBAL_Control
0x18001a545  lea     r12, WPP_2663f27e31e039d03781a4e1bd1e8da8_Traceguids
0x18001a54c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a553  cmp     rcx, r15
0x18001a556  jz      short loc_18001A56E
0x18001a558  test    byte ptr [rcx+1Ch], 1
0x18001a55c  jz      short loc_18001A56E
0x18001a55e  lea     edx, [r14+14h]
0x18001a562  mov     r8, r12
0x18001a565  mov     rcx, [rcx+10h]
0x18001a569  call    WPP_SF_
0x18001a56e  lea     rax, [rsp+2150h+hKey]
0x18001a573  mov     [rsp+2150h+phkResult], rax; phkResult
0x18001a578  mov     r9d, 20019h; samDesired
0x18001a57e  xor     r8d, r8d; ulOptions
0x18001a581  lea     rdx, aSoftwareMicros_3; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18001a588  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18001a58f  call    cs:__imp_RegOpenKeyExW
0x18001a596  nop     dword ptr [rax+rax+00h]
0x18001a59b  mov     edi, eax
0x18001a59d  test    eax, eax
0x18001a59f  jz      loc_18001A663
0x18001a5a5  cmp     eax, 2
0x18001a5a8  jnz     short loc_18001A608
0x18001a5aa  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a5b1  cmp     rcx, r15
0x18001a5b4  jz      short loc_18001A5CB
0x18001a5b6  test    byte ptr [rcx+1Ch], 1
0x18001a5ba  jz      short loc_18001A5CB
0x18001a5bc  lea     edx, [rax+13h]
0x18001a5bf  mov     r8, r12
0x18001a5c2  mov     rcx, [rcx+10h]
0x18001a5c6  call    WPP_SF_
0x18001a5cb  mov     ebx, r14d
0x18001a5ce  mov     rcx, [rsp+2150h+hKey]; hKey
0x18001a5d3  test    rcx, rcx
0x18001a5d6  jz      short loc_18001A5E4
0x18001a5d8  call    cs:__imp_RegCloseKey
0x18001a5df  nop     dword ptr [rax+rax+00h]
0x18001a5e4  mov     eax, ebx
0x18001a5e6  mov     rcx, [rbp+2050h+var_40]
0x18001a5ed  xor     rcx, rsp; StackCookie
0x18001a5f0  call    __security_check_cookie
0x18001a5f5  add     rsp, 2120h
0x18001a5fc  pop     r15
0x18001a5fe  pop     r14
0x18001a600  pop     r12
0x18001a602  pop     rdi
0x18001a603  pop     rsi
0x18001a604  pop     rbx
0x18001a605  pop     rbp
0x18001a606  retn
0x18001a608  test    edi, edi
0x18001a60a  jg      short loc_18001A610
0x18001a60c  mov     ebx, edi
0x18001a60e  jmp     short loc_18001A619
0x18001a610  movzx   ebx, di
0x18001a613  or      ebx, 80070000h
0x18001a619  mov     rax, cs:WPP_GLOBAL_Control
0x18001a620  cmp     rax, r15
0x18001a623  jz      short loc_18001A5CE
0x18001a625  test    byte ptr [rax+1Ch], 4
0x18001a629  jz      short loc_18001A5CE
0x18001a62b  call    cs:__imp_GetLastError
0x18001a632  nop     dword ptr [rax+rax+00h]
0x18001a637  mov     edx, 16h
0x18001a63c  mov     dword ptr [rsp+2150h+lpcbMaxSubKeyLen], eax
0x18001a640  mov     dword ptr [rsp+2150h+phkResult], edi
0x18001a644  lea     r9, aSoftwareMicros_3; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18001a64b  mov     r8, r12
0x18001a64e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a655  mov     rcx, [rcx+10h]
0x18001a659  call    WPP_SF_SdD
0x18001a65e  jmp     loc_18001A5CE
0x18001a663  mov     [rsp+2150h+lpftLastWriteTime], r14; lpftLastWriteTime
0x18001a668  mov     [rsp+2150h+lpcbSecurityDescriptor], r14; lpcbSecurityDescriptor
0x18001a66d  mov     [rsp+2150h+lpcbMaxValueLen], r14; lpcbMaxValueLen
0x18001a672  mov     [rsp+2150h+lpcbMaxValueNameLen], r14; lpcbMaxValueNameLen
0x18001a677  lea     rax, [rsp+2150h+cValues]
0x18001a67c  mov     [rsp+2150h+lpcValues], rax; lpcValues
0x18001a681  mov     [rsp+2150h+lpcbMaxClassLen], r14; lpcbMaxClassLen
0x18001a686  mov     [rsp+2150h+lpcbMaxSubKeyLen], r14; lpcbMaxSubKeyLen
0x18001a68b  mov     [rsp+2150h+phkResult], r14; lpcSubKeys
0x18001a690  xor     r9d, r9d; lpReserved
0x18001a693  xor     r8d, r8d; lpcchClass
0x18001a696  xor     edx, edx; lpClass
0x18001a698  mov     rcx, [rsp+2150h+hKey]; hKey
0x18001a69d  call    cs:__imp_RegQueryInfoKeyW
0x18001a6a4  nop     dword ptr [rax+rax+00h]
0x18001a6a9  mov     edi, eax
0x18001a6ab  test    eax, eax
0x18001a6ad  jz      short loc_18001A6F0
0x18001a6af  test    eax, eax
0x18001a6b1  jg      short loc_18001A6B7
0x18001a6b3  mov     ebx, eax
0x18001a6b5  jmp     short loc_18001A6C0
0x18001a6b7  movzx   ebx, di
0x18001a6ba  or      ebx, 80070000h
0x18001a6c0  mov     rax, cs:WPP_GLOBAL_Control
0x18001a6c7  cmp     rax, r15
0x18001a6ca  jz      loc_18001A5CE
0x18001a6d0  test    byte ptr [rax+1Ch], 4
0x18001a6d4  jz      loc_18001A5CE
0x18001a6da  call    cs:__imp_GetLastError
0x18001a6e1  nop     dword ptr [rax+rax+00h]
0x18001a6e6  mov     edx, 17h
0x18001a6eb  jmp     loc_18001A63C
0x18001a6f0  mov     ebx, r14d
0x18001a6f3  mov     edi, r14d
0x18001a6f6  cmp     edi, [rsp+2150h+cValues]
0x18001a6fa  jnb     loc_18001A5CE
0x18001a700  mov     [rsp+2150h+cchValueName], 0FFFh
0x18001a708  mov     [rbp+2050h+ValueName], r14w
0x18001a70d  mov     [rsp+2150h+lpcValues], r14; lpcbData
0x18001a712  mov     [rsp+2150h+lpcbMaxClassLen], r14; lpData
0x18001a717  mov     [rsp+2150h+lpcbMaxSubKeyLen], r14; lpType
0x18001a71c  mov     [rsp+2150h+phkResult], r14; lpReserved
0x18001a721  lea     r9, [rsp+2150h+cchValueName]; lpcchValueName
0x18001a726  lea     r8, [rbp+2050h+ValueName]; lpValueName
0x18001a72a  mov     edx, edi; dwIndex
0x18001a72c  mov     rcx, [rsp+2150h+hKey]; hKey
0x18001a731  call    cs:__imp_RegEnumValueW
0x18001a738  nop     dword ptr [rax+rax+00h]
0x18001a73d  mov     esi, eax
0x18001a73f  test    eax, eax
0x18001a741  jnz     short loc_18001A7AB
0x18001a743  lea     rcx, [rbp+2050h+var_20B0]; this
0x18001a747  call    ??0RemoteAppDispatchParam@@QEAA@XZ; RemoteAppDispatchParam::RemoteAppDispatchParam(void)
0x18001a74c  nop
0x18001a74d  lea     rdx, [rbp+2050h+ValueName]
0x18001a751  lea     rcx, [rbp+2050h+var_2090]
0x18001a755  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x18001a75a  lea     rdx, [rbp+2050h+var_2090]
0x18001a75e  lea     rcx, [rsp+2150h+var_20D8]
0x18001a763  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001a768  mov     rcx, rax; psz
0x18001a76b  call    ?UnsubscribeRemoteWorkspace@RemoteAppUtil@@CAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; RemoteAppUtil::UnsubscribeRemoteWorkspace(std::wstring)
0x18001a770  mov     ebx, eax
0x18001a772  test    eax, eax
0x18001a774  jns     short loc_18001A7A0
0x18001a776  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a77d  cmp     rcx, r15
0x18001a780  jz      short loc_18001A7A0
0x18001a782  test    byte ptr [rcx+1Ch], 4
0x18001a786  jz      short loc_18001A7A0
0x18001a788  lea     edx, [rsi+18h]
0x18001a78b  mov     dword ptr [rsp+2150h+phkResult], eax
0x18001a78f  lea     r9, [rbp+2050h+ValueName]
0x18001a793  mov     r8, r12
0x18001a796  mov     rcx, [rcx+10h]
0x18001a79a  call    WPP_SF_Sd
0x18001a79f  nop
0x18001a7a0  lea     rcx, [rbp+2050h+var_20B0]; this
0x18001a7a4  call    ??1RemoteAppDispatchParam@@QEAA@XZ; RemoteAppDispatchParam::~RemoteAppDispatchParam(void)
0x18001a7a9  jmp     short loc_18001A7F0
0x18001a7ab  mov     rax, cs:WPP_GLOBAL_Control
0x18001a7b2  cmp     rax, r15
0x18001a7b5  jz      short loc_18001A7F0
0x18001a7b7  test    byte ptr [rax+1Ch], 4
0x18001a7bb  jz      short loc_18001A7F0
0x18001a7bd  call    cs:__imp_GetLastError
0x18001a7c4  nop     dword ptr [rax+rax+00h]
0x18001a7c9  mov     edx, 19h
0x18001a7ce  mov     dword ptr [rsp+2150h+lpcbMaxSubKeyLen], eax
0x18001a7d2  mov     dword ptr [rsp+2150h+phkResult], esi
0x18001a7d6  lea     r9, aSoftwareMicros_3; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18001a7dd  mov     r8, r12
0x18001a7e0  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a7e7  mov     rcx, [rcx+10h]
0x18001a7eb  call    WPP_SF_SdD
0x18001a7f0  inc     edi
0x18001a7f2  jmp     loc_18001A6F6
```
