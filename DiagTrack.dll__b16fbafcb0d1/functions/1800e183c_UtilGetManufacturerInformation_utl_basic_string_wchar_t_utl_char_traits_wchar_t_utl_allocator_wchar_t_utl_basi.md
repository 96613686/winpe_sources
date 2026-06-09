# UtilGetManufacturerInformation(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)

- ea: `0x1800e183c`
- end: `0x1800e1b87`
- name: `?UtilGetManufacturerInformation@@YAJPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@00@Z`
- size: `843`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1800e2aa8`

## callees

- `0x1800e183c`
- `0x1800e3c84`
- `0x1800e6240`
- `0x1801e1ebc`
- `0x1802f1154`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800e1894`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800e18cf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800e1894`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800e18cf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800e18ad`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800e1933`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800e1942`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800e19ea`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800e19f9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800e18ad`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800e1933`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800e1942`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800e19ea`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800e19f9`

## string_xrefs

- `0x1800e19be`: `SystemProductName`

## pseudocode

```c
__int64 __fastcall UtilGetManufacturerInformation(__int64 a1, __int64 a2, __int64 a3)
{
  HKEY v4; // rcx
  LSTATUS v7; // eax
  HKEY v8; // rcx
  signed int v9; // esi
  LSTATUS v10; // eax
  signed int v11; // edi
  HKEY v12; // rcx
  const WCHAR *v13; // r8
  _QWORD *v15; // rcx
  HKEY v16; // rcx
  const WCHAR *v17; // r8
  unsigned int v18; // r14d
  HKEY hKey; // [rsp+80h] [rbp+40h] BYREF
  HKEY phkResult; // [rsp+98h] [rbp+58h] BYREF

  hKey = 0;
  v4 = 0;
  phkResult = 0;
  if ( a1 )
  {
    v7 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\Platform\\DeviceTargetingInfo", 0, 1u, &phkResult);
    v8 = hKey;
    v9 = v7;
    hKey = 0;
    if ( v8 )
      RegCloseKey(v8);
    v10 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Control\\SystemInformation", 0, 1u, &hKey);
    v11 = v10;
    if ( v9 )
    {
      if ( v10 )
      {
        v18 = ERROR_HR_FROM_WIN32(v10);
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          if ( v11 > 0 )
            v11 = (unsigned __int16)v11 | 0x80070000;
          if ( v9 > 0 )
            v9 = (unsigned __int16)v9 | 0x80070000;
          WPP_SF_DD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            24,
            WPP_69e296c8cfbe35481aeff25676a4a37b_Traceguids,
            (unsigned int)v9,
            v11);
        }
        goto LABEL_26;
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_69e296c8cfbe35481aeff25676a4a37b_Traceguids);
      v12 = hKey;
      v13 = L"SystemManufacturer";
    }
    else
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_69e296c8cfbe35481aeff25676a4a37b_Traceguids);
      v12 = phkResult;
      v13 = L"PhoneManufacturer";
    }
    UtilRegGetString(v12, 0, v13, a1, 0, 0);
    if ( a3 )
    {
      if ( v11 )
      {
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
          goto LABEL_20;
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_69e296c8cfbe35481aeff25676a4a37b_Traceguids);
      }
      else
      {
        UtilRegGetString(hKey, 0, L"BIOSVersion", a3, 0, 0);
      }
    }
    v15 = WPP_GLOBAL_Control;
LABEL_20:
    if ( a2 )
    {
      if ( v9 )
      {
        if ( v15 != &WPP_GLOBAL_Control && (*((_BYTE *)v15 + 28) & 4) != 0 )
          WPP_SF_(v15[2], 29, WPP_69e296c8cfbe35481aeff25676a4a37b_Traceguids);
        v16 = hKey;
        v17 = L"SystemProductName";
      }
      else
      {
        if ( v15 != &WPP_GLOBAL_Control && (*((_BYTE *)v15 + 28) & 4) != 0 )
          WPP_SF_(v15[2], 28, WPP_69e296c8cfbe35481aeff25676a4a37b_Traceguids);
        v16 = phkResult;
        v17 = L"PhoneManufacturerModelName";
      }
      UtilRegGetString(v16, 0, v17, a2, 0, 0);
    }
    v18 = 0;
LABEL_26:
    if ( phkResult )
      RegCloseKey(phkResult);
    if ( hKey )
      RegCloseKey(hKey);
    return v18;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_69e296c8cfbe35481aeff25676a4a37b_Traceguids);
    v4 = phkResult;
  }
  if ( v4 )
    RegCloseKey(v4);
  if ( hKey )
    RegCloseKey(hKey);
  return 2147942487LL;
}

```

## disassembly

```asm
0x1800e183c  mov     [rsp-38h+arg_8], rbx
0x1800e1841  push    rbp
0x1800e1842  push    rsi
0x1800e1843  push    rdi
0x1800e1844  push    r12
0x1800e1846  push    r13
0x1800e1848  push    r14
0x1800e184a  push    r15
0x1800e184c  mov     rbp, rsp
0x1800e184f  sub     rsp, 40h
0x1800e1853  mov     r15, rcx
0x1800e1856  mov     [rbp+hKey], 0
0x1800e185e  xor     ecx, ecx; hKey
0x1800e1860  mov     r13, r8
0x1800e1863  mov     [rbp+arg_18], rcx
0x1800e1867  mov     r12, rdx
0x1800e186a  test    r15, r15
0x1800e186d  jz      loc_1800E1917
0x1800e1873  lea     rax, [rbp+arg_18]
0x1800e1877  mov     rbx, 0FFFFFFFF80000002h
0x1800e187e  lea     r9d, [rcx+1]; samDesired
0x1800e1882  mov     [rsp+40h+phkResult], rax; phkResult
0x1800e1887  mov     rcx, rbx; hKey
0x1800e188a  lea     rdx, aSystemPlatform; "SYSTEM\\Platform\\DeviceTargetingInfo"
0x1800e1891  xor     r8d, r8d; ulOptions
0x1800e1894  call    cs:__imp_RegOpenKeyExW
0x1800e189a  mov     rcx, [rbp+hKey]; hKey
0x1800e189e  mov     esi, eax
0x1800e18a0  mov     [rbp+hKey], 0
0x1800e18a8  test    rcx, rcx
0x1800e18ab  jz      short loc_1800E18B3
0x1800e18ad  call    cs:__imp_RegCloseKey
0x1800e18b3  lea     rax, [rbp+hKey]
0x1800e18b7  mov     r9d, 1; samDesired
0x1800e18bd  xor     r8d, r8d; ulOptions
0x1800e18c0  mov     [rsp+40h+phkResult], rax; phkResult
0x1800e18c5  lea     rdx, aSystemCurrentc_8; "SYSTEM\\CurrentControlSet\\Control\\Sys"...
0x1800e18cc  mov     rcx, rbx; hKey
0x1800e18cf  call    cs:__imp_RegOpenKeyExW
0x1800e18d5  mov     edi, eax
0x1800e18d7  test    esi, esi
0x1800e18d9  jnz     short loc_1800E1952
0x1800e18db  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e18e2  lea     rbx, WPP_GLOBAL_Control
0x1800e18e9  mov     r14b, 4
0x1800e18ec  cmp     rcx, rbx
0x1800e18ef  jz      short loc_1800E190A
0x1800e18f1  test    [rcx+1Ch], r14b
0x1800e18f5  jz      short loc_1800E190A
0x1800e18f7  mov     rcx, [rcx+10h]
0x1800e18fb  lea     edx, [rsi+19h]
0x1800e18fe  lea     r8, WPP_69e296c8cfbe35481aeff25676a4a37b_Traceguids
0x1800e1905  call    WPP_SF_
0x1800e190a  mov     rcx, [rbp+arg_18]
0x1800e190e  lea     r8, aPhonemanufactu; "PhoneManufacturer"
0x1800e1915  jmp     short loc_1800E197F
0x1800e1917  mov     rax, cs:WPP_GLOBAL_Control
0x1800e191e  lea     rbx, WPP_GLOBAL_Control
0x1800e1925  cmp     rax, rbx
0x1800e1928  jnz     loc_1800E1A83
0x1800e192e  test    rcx, rcx
0x1800e1931  jz      short loc_1800E1939
0x1800e1933  call    cs:__imp_RegCloseKey
0x1800e1939  mov     rcx, [rbp+hKey]; hKey
0x1800e193d  test    rcx, rcx
0x1800e1940  jz      short loc_1800E1948
0x1800e1942  call    cs:__imp_RegCloseKey
0x1800e1948  mov     eax, 80070057h
0x1800e194d  jmp     loc_1800E1A02
0x1800e1952  test    edi, edi
0x1800e1954  jnz     loc_1800E1AAB
0x1800e195a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e1961  lea     rbx, WPP_GLOBAL_Control
0x1800e1968  mov     r14b, 4
0x1800e196b  cmp     rcx, rbx
0x1800e196e  jnz     loc_1800E1ADB
0x1800e1974  mov     rcx, [rbp+hKey]; hKey
0x1800e1978  lea     r8, aSystemmanufact; "SystemManufacturer"
0x1800e197f  mov     [rsp+40h+var_10], 0; char
0x1800e1984  xor     r9d, r9d
0x1800e1987  mov     [rsp+40h+var_18], 0; char
0x1800e198c  xor     edx, edx; lpSubKey
0x1800e198e  mov     [rsp+40h+phkResult], r15; __int64
0x1800e1993  call    ?UtilRegGetString@@YAJPEAUHKEY__@@PEB_W11PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@_N3@Z; UtilRegGetString(HKEY__ *,wchar_t const *,wchar_t const *,wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,bool,bool)
0x1800e1998  test    r13, r13
0x1800e199b  jnz     short loc_1800E1A1A
0x1800e199d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e19a4  test    r12, r12
0x1800e19a7  jz      short loc_1800E19DE
0x1800e19a9  test    esi, esi
0x1800e19ab  jz      loc_1800E1B33
0x1800e19b1  cmp     rcx, rbx
0x1800e19b4  jnz     loc_1800E1B63
0x1800e19ba  mov     rcx, [rbp+hKey]; hKey
0x1800e19be  lea     r8, aSystemproductn; "SystemProductName"
0x1800e19c5  mov     [rsp+40h+var_10], 0; char
0x1800e19ca  xor     r9d, r9d
0x1800e19cd  mov     [rsp+40h+var_18], 0; char
0x1800e19d2  xor     edx, edx; lpSubKey
0x1800e19d4  mov     [rsp+40h+phkResult], r12; __int64
0x1800e19d9  call    ?UtilRegGetString@@YAJPEAUHKEY__@@PEB_W11PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@_N3@Z; UtilRegGetString(HKEY__ *,wchar_t const *,wchar_t const *,wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,bool,bool)
0x1800e19de  xor     r14d, r14d
0x1800e19e1  mov     rcx, [rbp+arg_18]; hKey
0x1800e19e5  test    rcx, rcx
0x1800e19e8  jz      short loc_1800E19F0
0x1800e19ea  call    cs:__imp_RegCloseKey
0x1800e19f0  mov     rcx, [rbp+hKey]; hKey
0x1800e19f4  test    rcx, rcx
0x1800e19f7  jz      short loc_1800E19FF
0x1800e19f9  call    cs:__imp_RegCloseKey
0x1800e19ff  mov     eax, r14d
0x1800e1a02  mov     rbx, [rsp+40h+arg_8]
0x1800e1a0a  add     rsp, 40h
0x1800e1a0e  pop     r15
0x1800e1a10  pop     r14
0x1800e1a12  pop     r13
0x1800e1a14  pop     r12
0x1800e1a16  pop     rdi
0x1800e1a17  pop     rsi
0x1800e1a18  pop     rbp
0x1800e1a19  retn
0x1800e1a1a  test    edi, edi
0x1800e1a1c  jnz     loc_1800E1AFF
0x1800e1a22  mov     rcx, [rbp+hKey]; hKey
0x1800e1a26  lea     r8, aBiosversion; "BIOSVersion"
0x1800e1a2d  mov     [rsp+40h+var_10], dil; char
0x1800e1a32  xor     r9d, r9d
0x1800e1a35  mov     [rsp+40h+var_18], dil; char
0x1800e1a3a  xor     edx, edx; lpSubKey
0x1800e1a3c  mov     [rsp+40h+phkResult], r13; __int64
0x1800e1a41  call    ?UtilRegGetString@@YAJPEAUHKEY__@@PEB_W11PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@_N3@Z; UtilRegGetString(HKEY__ *,wchar_t const *,wchar_t const *,wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,bool,bool)
0x1800e1a46  jmp     loc_1800E199D
0x1800e1a4b  mov     eax, 80070000h
0x1800e1a50  test    edi, edi
0x1800e1a52  jle     short loc_1800E1A59
0x1800e1a54  movzx   edi, di
0x1800e1a57  or      edi, eax
0x1800e1a59  test    esi, esi
0x1800e1a5b  jle     short loc_1800E1A62
0x1800e1a5d  movzx   esi, si
0x1800e1a60  or      esi, eax
0x1800e1a62  mov     rcx, [rcx+10h]
0x1800e1a66  lea     r8, WPP_69e296c8cfbe35481aeff25676a4a37b_Traceguids
0x1800e1a6d  mov     edx, 18h
0x1800e1a72  mov     dword ptr [rsp+40h+phkResult], edi
0x1800e1a76  mov     r9d, esi
0x1800e1a79  call    WPP_SF_DD
0x1800e1a7e  jmp     loc_1800E19E1
0x1800e1a83  test    byte ptr [rax+1Ch], 1
0x1800e1a87  jz      loc_1800E192E
0x1800e1a8d  mov     rcx, [rax+10h]
0x1800e1a91  lea     r8, WPP_69e296c8cfbe35481aeff25676a4a37b_Traceguids
0x1800e1a98  mov     edx, 17h
0x1800e1a9d  call    WPP_SF_
0x1800e1aa2  mov     rcx, [rbp+arg_18]
0x1800e1aa6  jmp     loc_1800E192E
0x1800e1aab  mov     ecx, edi; unsigned int
0x1800e1aad  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x1800e1ab2  mov     r14d, eax
0x1800e1ab5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e1abc  lea     rbx, WPP_GLOBAL_Control
0x1800e1ac3  cmp     rcx, rbx
0x1800e1ac6  jz      loc_1800E19E1
0x1800e1acc  test    byte ptr [rcx+1Ch], 1
0x1800e1ad0  jz      loc_1800E19E1
0x1800e1ad6  jmp     loc_1800E1A4B
0x1800e1adb  test    [rcx+1Ch], r14b
0x1800e1adf  jz      loc_1800E1974
0x1800e1ae5  mov     rcx, [rcx+10h]
0x1800e1ae9  lea     r8, WPP_69e296c8cfbe35481aeff25676a4a37b_Traceguids
0x1800e1af0  mov     edx, 1Ah
0x1800e1af5  call    WPP_SF_
0x1800e1afa  jmp     loc_1800E1974
0x1800e1aff  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e1b06  cmp     rcx, rbx
0x1800e1b09  jz      loc_1800E19A4
0x1800e1b0f  test    [rcx+1Ch], r14b
0x1800e1b13  jz      loc_1800E19A4
0x1800e1b19  mov     rcx, [rcx+10h]
0x1800e1b1d  lea     r8, WPP_69e296c8cfbe35481aeff25676a4a37b_Traceguids
0x1800e1b24  mov     edx, 1Bh
0x1800e1b29  call    WPP_SF_
0x1800e1b2e  jmp     loc_1800E199D
0x1800e1b33  cmp     rcx, rbx
0x1800e1b36  jz      short loc_1800E1B53
0x1800e1b38  test    [rcx+1Ch], r14b
0x1800e1b3c  jz      short loc_1800E1B53
0x1800e1b3e  mov     rcx, [rcx+10h]
0x1800e1b42  lea     r8, WPP_69e296c8cfbe35481aeff25676a4a37b_Traceguids
0x1800e1b49  mov     edx, 1Ch
0x1800e1b4e  call    WPP_SF_
0x1800e1b53  mov     rcx, [rbp+arg_18]
0x1800e1b57  lea     r8, aPhonemanufactu_0; "PhoneManufacturerModelName"
0x1800e1b5e  jmp     loc_1800E19C5
0x1800e1b63  test    [rcx+1Ch], r14b
0x1800e1b67  jz      loc_1800E19BA
0x1800e1b6d  mov     rcx, [rcx+10h]
0x1800e1b71  lea     r8, WPP_69e296c8cfbe35481aeff25676a4a37b_Traceguids
0x1800e1b78  mov     edx, 1Dh
0x1800e1b7d  call    WPP_SF_
0x1800e1b82  jmp     loc_1800E19BA
```
