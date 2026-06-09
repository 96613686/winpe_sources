# UpdateReserveManager::CalculateTotalPendingScratchIncrease(unsigned __int64 *)

- ea: `0x1800127c8`
- end: `0x180012be7`
- name: `?CalculateTotalPendingScratchIncrease@UpdateReserveManager@@AEAAJPEA_K@Z`
- size: `1055`
- prototype: `__int64 __fastcall(HKEY *this, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800166a8`

## callees

- `0x180003870`
- `0x18000fafc`
- `0x180011cf8`
- `0x18001224c`
- `0x1800127c8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012864`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800128e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012ad4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012b38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012bd9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012864`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800128e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012ad4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012b38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012bd9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180012823`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180012823`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18001293f`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18001293f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012856`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800128dd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012aca`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012b2e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012bcb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012856`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800128dd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012aca`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012b2e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012bcb`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180012a67`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180012a67`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180012a0e`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180012a0e`

## string_xrefs

- `0x18001287a`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x18001294b`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x180012b5c`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x180012885`: `UpdateReserveManager::CalculateTotalPendingScratchIncrease`
- `0x180012956`: `UpdateReserveManager::CalculateTotalPendingScratchIncrease`
- `0x180012b67`: `UpdateReserveManager::CalculateTotalPendingScratchIncrease`

## pseudocode

```c
__int64 __fastcall UpdateReserveManager::CalculateTotalPendingScratchIncrease(HKEY *this, unsigned __int64 *a2)
{
  int ValueW; // esi
  bool v4; // cc
  const char *v5; // rax
  unsigned __int64 v7; // r14
  __int64 v8; // rax
  LPWSTR *v9; // rdi
  unsigned __int64 i; // rcx
  DWORD v11; // edi
  WCHAR *v12; // r8
  LSTATUS v13; // eax
  const WCHAR *v14; // rdx
  const char *v15; // [rsp+68h] [rbp-39h] BYREF
  const char *v16; // [rsp+70h] [rbp-31h]
  __int64 v17; // [rsp+78h] [rbp-29h]
  const char *v18; // [rsp+80h] [rbp-21h]
  __int64 v19; // [rsp+88h] [rbp-19h]
  HKEY hKey; // [rsp+90h] [rbp-11h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+98h] [rbp-9h] BYREF
  DWORD cSubKeys; // [rsp+9Ch] [rbp-5h] BYREF
  LPWSTR lpName[2]; // [rsp+A0h] [rbp-1h] BYREF
  __int64 v24; // [rsp+B0h] [rbp+Fh]
  unsigned __int64 v25; // [rsp+B8h] [rbp+17h]
  DWORD cchName; // [rsp+C0h] [rbp+1Fh] BYREF
  DWORD pcbData; // [rsp+C4h] [rbp+23h] BYREF
  __int64 pvData; // [rsp+C8h] [rbp+27h] BYREF

  v19 = -2;
  hKey = 0;
  ValueW = RegOpenKeyExW(
             this[13],
             L"Microsoft\\Windows\\CurrentVersion\\ReserveManager\\PendingAdjustments",
             0,
             0x2011Fu,
             &hKey);
  if ( ValueW == 2 )
  {
    *a2 = 0;
    if ( hKey && ((unsigned __int64)hKey & 0xFFFFFFFF80000000uLL) != 0xFFFFFFFF80000000uLL && RegCloseKey(hKey) )
      goto LABEL_41;
    return 0;
  }
  v4 = ValueW <= 0;
  if ( ValueW )
  {
    v15 = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
    v16 = "UpdateReserveManager::CalculateTotalPendingScratchIncrease";
    v17 = 2449;
    v5 = "RetValue";
    goto LABEL_8;
  }
  cSubKeys = 0;
  cbMaxSubKeyLen = 0;
  ValueW = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
  if ( ValueW )
  {
    v15 = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
    v16 = "UpdateReserveManager::CalculateTotalPendingScratchIncrease";
    v17 = 2466;
    v5 = "RegQueryInfoKeyW(PendingAdjustmentsKey, nullptr, nullptr, nullptr, &NumSubKeys, &MaxSubKeyLength, nullptr, null"
         "ptr, nullptr, nullptr, nullptr, nullptr)";
    v4 = ValueW <= 0;
LABEL_8:
    v18 = v5;
    if ( !v4 )
      ValueW = (unsigned __int16)ValueW | 0x80070000;
    RtlReportErrorOrigination(&v15, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, (unsigned int)ValueW);
    if ( hKey && ((unsigned __int64)hKey & 0xFFFFFFFF80000000uLL) != 0xFFFFFFFF80000000uLL && RegCloseKey(hKey) )
      goto LABEL_13;
    return (unsigned int)ValueW;
  }
  v7 = 0;
  v8 = cbMaxSubKeyLen + 1;
  cbMaxSubKeyLen = v8;
  *(_OWORD *)lpName = 0;
  v24 = 0;
  v25 = 7;
  LOWORD(lpName[0]) = 0;
  if ( (unsigned int)v8 > 7uLL )
  {
    ____Reallocate_for_V_lambda_1___1__assign___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__QEAAAEAV34__K_W_Z__W___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAAAEAV01__KV_lambda_1___1__assign_01_QEAAAEAV01_0_W_Z__W_Z(lpName);
  }
  else
  {
    v24 = (unsigned int)v8;
    v9 = lpName;
    if ( (_DWORD)v8 )
    {
      for ( i = (unsigned __int64)(2 * v8) >> 1; i; --i )
      {
        *(_WORD *)v9 = 0;
        v9 = (LPWSTR *)((char *)v9 + 2);
      }
    }
    *((_WORD *)lpName + v8) = 0;
  }
  v11 = 0;
  if ( !cSubKeys )
  {
LABEL_38:
    *a2 = v7;
    std::wstring::~wstring((char **)lpName);
    if ( hKey && ((unsigned __int64)hKey & 0xFFFFFFFF80000000uLL) != 0xFFFFFFFF80000000uLL && RegCloseKey(hKey) )
    {
LABEL_41:
      GetLastError();
      __fastfail(7u);
    }
    return 0;
  }
  while ( 1 )
  {
    cchName = cbMaxSubKeyLen;
    v12 = (WCHAR *)lpName;
    if ( v25 > 7 )
      v12 = lpName[0];
    v13 = RegEnumKeyExW(hKey, v11, v12, &cchName, 0, 0, 0, 0);
    ValueW = v13;
    if ( v13 == 259 )
      goto LABEL_38;
    if ( v13 )
    {
      v17 = 2492;
LABEL_50:
      v15 = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
      v16 = "UpdateReserveManager::CalculateTotalPendingScratchIncrease";
      v18 = "RetValue";
      if ( ValueW > 0 )
        ValueW = (unsigned __int16)ValueW | 0x80070000;
      RtlReportErrorOrigination(&v15, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, (unsigned int)ValueW);
      std::wstring::~wstring((char **)lpName);
      if ( hKey && ((unsigned __int64)hKey & 0xFFFFFFFF80000000uLL) != 0xFFFFFFFF80000000uLL && RegCloseKey(hKey) )
      {
LABEL_13:
        GetLastError();
        __fastfail(7u);
      }
      return (unsigned int)ValueW;
    }
    pvData = 0;
    pcbData = 8;
    v14 = (const WCHAR *)lpName;
    if ( v25 > 7 )
      v14 = lpName[0];
    ValueW = RegGetValueW(hKey, v14, L"IncreasedScratch", v13 + 64, 0, &pvData, &pcbData);
    if ( ValueW != 2 )
      break;
    pvData = 0;
LABEL_37:
    if ( ++v11 >= cSubKeys )
      goto LABEL_38;
  }
  if ( ValueW )
  {
    v17 = 2511;
    goto LABEL_50;
  }
  if ( !pvData )
    goto LABEL_37;
  if ( pvData + v7 >= v7 )
  {
    v7 += pvData;
    goto LABEL_37;
  }
  std::wstring::~wstring((char **)lpName);
  if ( hKey && ((unsigned __int64)hKey & 0xFFFFFFFF80000000uLL) != 0xFFFFFFFF80000000uLL && RegCloseKey(hKey) )
  {
    GetLastError();
    __fastfail(7u);
  }
  return 2147942934LL;
}

```

## disassembly

```asm
0x1800127c8  mov     rax, rsp
0x1800127cb  push    rbp
0x1800127cc  push    rdi
0x1800127cd  push    r12
0x1800127cf  push    r14
0x1800127d1  push    r15
0x1800127d3  lea     rbp, [rax-5Fh]
0x1800127d7  sub     rsp, 0D0h
0x1800127de  mov     [rbp+57h+var_70], 0FFFFFFFFFFFFFFFEh
0x1800127e6  mov     [rax+18h], rbx
0x1800127ea  mov     [rax+20h], rsi
0x1800127ee  mov     rax, cs:__security_cookie
0x1800127f5  xor     rax, rsp
0x1800127f8  mov     [rbp+57h+var_28], rax
0x1800127fc  mov     r15, rdx
0x1800127ff  xor     r12d, r12d
0x180012802  mov     [rbp+57h+hKey], r12
0x180012806  lea     rax, [rbp+57h+hKey]
0x18001280a  mov     [rsp+0F0h+phkResult], rax; phkResult
0x18001280f  mov     r9d, 2011Fh; samDesired
0x180012815  xor     r8d, r8d; ulOptions
0x180012818  lea     rdx, SubKey; "Microsoft\\Windows\\CurrentVersion\\Res"...
0x18001281f  mov     rcx, [rcx+68h]; hKey
0x180012823  call    cs:__imp_RegOpenKeyExW
0x180012829  mov     esi, eax
0x18001282b  cmp     eax, 2
0x18001282e  jnz     short loc_180012872
0x180012830  mov     [r15], r12
0x180012833  mov     rcx, [rbp+57h+hKey]; hKey
0x180012837  test    rcx, rcx
0x18001283a  jz      loc_180012ADF
0x180012840  mov     rax, rcx
0x180012843  mov     rdi, 0FFFFFFFF80000000h
0x18001284a  and     rax, rdi
0x18001284d  cmp     rax, rdi
0x180012850  jz      loc_180012ADF
0x180012856  call    cs:__imp_RegCloseKey
0x18001285c  test    eax, eax
0x18001285e  jz      loc_180012ADF
0x180012864  call    cs:__imp_GetLastError
0x18001286a  lea     ecx, [rsi+5]
0x18001286d  jmp     loc_180012ADD
0x180012872  test    esi, esi
0x180012874  jz      loc_1800128FB
0x18001287a  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x180012881  mov     [rbp+57h+var_90], rax
0x180012885  lea     rax, aUpdatereservem_41; "UpdateReserveManager::CalculateTotalPen"...
0x18001288c  mov     [rbp+57h+var_88], rax
0x180012890  mov     [rbp+57h+var_80], 991h
0x180012898  lea     rax, aRetvalue; "RetValue"
0x18001289f  mov     [rbp+57h+var_78], rax
0x1800128a3  jle     short loc_1800128AE
0x1800128a5  movzx   esi, si
0x1800128a8  or      esi, 80070000h
0x1800128ae  mov     r8d, esi
0x1800128b1  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x1800128b8  lea     rcx, [rbp+57h+var_90]
0x1800128bc  call    RtlReportErrorOrigination
0x1800128c1  nop
0x1800128c2  mov     rcx, [rbp+57h+hKey]; hKey
0x1800128c6  test    rcx, rcx
0x1800128c9  jz      short loc_1800128F4
0x1800128cb  mov     rax, rcx
0x1800128ce  mov     rdi, 0FFFFFFFF80000000h
0x1800128d5  and     rax, rdi
0x1800128d8  cmp     rax, rdi
0x1800128db  jz      short loc_1800128F4
0x1800128dd  call    cs:__imp_RegCloseKey
0x1800128e3  test    eax, eax
0x1800128e5  jz      short loc_1800128F4
0x1800128e7  call    cs:__imp_GetLastError
0x1800128ed  mov     ecx, 7
0x1800128f2  int     29h; Win8: RtlFailFast(ecx)
0x1800128f4  mov     eax, esi
0x1800128f6  jmp     loc_180012AE1
0x1800128fb  mov     [rbp+57h+cSubKeys], r12d
0x1800128ff  mov     [rbp+57h+cbMaxSubKeyLen], r12d
0x180012903  mov     [rsp+0F0h+lpftLastWriteTime], r12; lpftLastWriteTime
0x180012908  mov     [rsp+0F0h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x18001290d  mov     [rsp+0F0h+lpcbMaxValueLen], r12; lpcbMaxValueLen
0x180012912  mov     [rsp+0F0h+lpcbMaxValueNameLen], r12; lpcbMaxValueNameLen
0x180012917  mov     [rsp+0F0h+lpcValues], r12; lpcValues
0x18001291c  mov     [rsp+0F0h+lpcbMaxClassLen], r12; lpcbMaxClassLen
0x180012921  lea     rax, [rbp+57h+cbMaxSubKeyLen]
0x180012925  mov     [rsp+0F0h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x18001292a  lea     rax, [rbp+57h+cSubKeys]
0x18001292e  mov     [rsp+0F0h+phkResult], rax; lpcSubKeys
0x180012933  xor     r9d, r9d; lpReserved
0x180012936  xor     r8d, r8d; lpcchClass
0x180012939  xor     edx, edx; lpClass
0x18001293b  mov     rcx, [rbp+57h+hKey]; hKey
0x18001293f  call    cs:__imp_RegQueryInfoKeyW
0x180012945  mov     esi, eax
0x180012947  test    eax, eax
0x180012949  jz      short loc_180012977
0x18001294b  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x180012952  mov     [rbp+57h+var_90], rax
0x180012956  lea     rax, aUpdatereservem_41; "UpdateReserveManager::CalculateTotalPen"...
0x18001295d  mov     [rbp+57h+var_88], rax
0x180012961  mov     [rbp+57h+var_80], 9A2h
0x180012969  lea     rax, aRegqueryinfoke; "RegQueryInfoKeyW(PendingAdjustmentsKey,"...
0x180012970  test    esi, esi
0x180012972  jmp     loc_18001289F
0x180012977  mov     r14, r12
0x18001297a  mov     eax, [rbp+57h+cbMaxSubKeyLen]
0x18001297d  inc     eax
0x18001297f  mov     [rbp+57h+cbMaxSubKeyLen], eax
0x180012982  mov     edx, eax
0x180012984  xorps   xmm0, xmm0
0x180012987  movups  xmmword ptr [rbp+57h+lpName], xmm0
0x18001298b  mov     [rbp+57h+var_48], r12
0x18001298f  mov     ebx, 7
0x180012994  mov     [rbp+57h+var_40], rbx
0x180012998  mov     word ptr [rbp+57h+lpName], r12w
0x18001299d  cmp     rdx, rbx
0x1800129a0  ja      short loc_1800129C7
0x1800129a2  mov     [rbp+57h+var_48], rdx
0x1800129a6  lea     rdi, [rbp+57h+lpName]
0x1800129aa  lea     r8, [rax+rax]
0x1800129ae  test    eax, eax
0x1800129b0  jz      short loc_1800129BF
0x1800129b2  mov     rcx, r8
0x1800129b5  shr     rcx, 1
0x1800129b8  movzx   eax, r12w
0x1800129bc  rep stosw
0x1800129bf  mov     word ptr [rbp+r8+57h+lpName], r12w
0x1800129c5  jmp     short loc_1800129D0
0x1800129c7  lea     rcx, [rbp+57h+lpName]
0x1800129cb  call    ??$_Reallocate_for@V_lambda_1_@?1??assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV34@_K_W@Z@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??assign@01@QEAAAEAV01@0_W@Z@_W@Z; std::wstring::_Reallocate_for<`std::wstring::assign(unsigned __int64,wchar_t)'::`2'::_lambda_1_,wchar_t>(unsigned __int64,`std::wstring::assign(unsigned __int64,wchar_t)'::`2'::_lambda_1_,wchar_t)
0x1800129d0  mov     edi, r12d
0x1800129d3  cmp     [rbp+57h+cSubKeys], r12d
0x1800129d7  jbe     loc_180012AA2
0x1800129dd  mov     eax, [rbp+57h+cbMaxSubKeyLen]
0x1800129e0  mov     [rbp+57h+cchName], eax
0x1800129e3  lea     r8, [rbp+57h+lpName]
0x1800129e7  cmp     [rbp+57h+var_40], rbx
0x1800129eb  cmova   r8, [rbp+57h+lpName]; lpName
0x1800129f0  mov     [rsp+0F0h+lpcValues], r12; lpftLastWriteTime
0x1800129f5  mov     [rsp+0F0h+lpcbMaxClassLen], r12; lpcchClass
0x1800129fa  mov     [rsp+0F0h+lpcbMaxSubKeyLen], r12; lpClass
0x1800129ff  mov     [rsp+0F0h+phkResult], r12; lpReserved
0x180012a04  lea     r9, [rbp+57h+cchName]; lpcchName
0x180012a08  mov     edx, edi; dwIndex
0x180012a0a  mov     rcx, [rbp+57h+hKey]; hKey
0x180012a0e  call    cs:__imp_RegEnumKeyExW
0x180012a14  mov     esi, eax
0x180012a16  cmp     eax, 103h
0x180012a1b  jz      loc_180012AA2
0x180012a21  test    eax, eax
0x180012a23  jnz     loc_180012B54
0x180012a29  mov     [rbp+57h+pvData], r12
0x180012a2d  mov     [rbp+57h+pcbData], 8
0x180012a34  lea     rdx, [rbp+57h+lpName]
0x180012a38  cmp     [rbp+57h+var_40], rbx
0x180012a3c  cmova   rdx, [rbp+57h+lpName]; lpSubKey
0x180012a41  lea     rax, [rbp+57h+pcbData]
0x180012a45  mov     [rsp+0F0h+lpcbMaxClassLen], rax; pcbData
0x180012a4a  lea     rax, [rbp+57h+pvData]
0x180012a4e  mov     [rsp+0F0h+lpcbMaxSubKeyLen], rax; pvData
0x180012a53  mov     [rsp+0F0h+phkResult], r12; pdwType
0x180012a58  lea     r9d, [rsi+40h]; dwFlags
0x180012a5c  lea     r8, Value; "IncreasedScratch"
0x180012a63  mov     rcx, [rbp+57h+hKey]; hkey
0x180012a67  call    cs:__imp_RegGetValueW
0x180012a6d  mov     esi, eax
0x180012a6f  cmp     eax, 2
0x180012a72  jnz     short loc_180012A7A
0x180012a74  mov     [rbp+57h+pvData], r12
0x180012a78  jmp     short loc_180012A97
0x180012a7a  test    esi, esi
0x180012a7c  jnz     loc_180012B4A
0x180012a82  mov     rax, [rbp+57h+pvData]
0x180012a86  test    rax, rax
0x180012a89  jz      short loc_180012A97
0x180012a8b  lea     rcx, [rax+r14]
0x180012a8f  cmp     rcx, r14
0x180012a92  jb      short loc_180012B09
0x180012a94  mov     r14, rcx
0x180012a97  inc     edi
0x180012a99  cmp     edi, [rbp+57h+cSubKeys]
0x180012a9c  jb      loc_1800129DD
0x180012aa2  mov     [r15], r14
0x180012aa5  lea     rcx, [rbp+57h+lpName]
0x180012aa9  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180012aae  nop
0x180012aaf  mov     rcx, [rbp+57h+hKey]; hKey
0x180012ab3  test    rcx, rcx
0x180012ab6  jz      short loc_180012ADF
0x180012ab8  mov     rax, rcx
0x180012abb  mov     rdi, 0FFFFFFFF80000000h
0x180012ac2  and     rax, rdi
0x180012ac5  cmp     rax, rdi
0x180012ac8  jz      short loc_180012ADF
0x180012aca  call    cs:__imp_RegCloseKey
0x180012ad0  test    eax, eax
0x180012ad2  jz      short loc_180012ADF
0x180012ad4  call    cs:__imp_GetLastError
0x180012ada  mov     rcx, rbx
0x180012add  int     29h; Win8: RtlFailFast(ecx)
0x180012adf  xor     eax, eax
0x180012ae1  mov     rcx, [rbp+57h+var_28]
0x180012ae5  xor     rcx, rsp; StackCookie
0x180012ae8  call    __security_check_cookie
0x180012aed  lea     r11, [rsp+0F0h+var_20]
0x180012af5  mov     rbx, [r11+40h]
0x180012af9  mov     rsi, [r11+48h]
0x180012afd  mov     rsp, r11
0x180012b00  pop     r15
0x180012b02  pop     r14
0x180012b04  pop     r12
0x180012b06  pop     rdi
0x180012b07  pop     rbp
0x180012b08  retn
0x180012b09  lea     rcx, [rbp+57h+lpName]
0x180012b0d  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180012b12  nop
0x180012b13  mov     rcx, [rbp+57h+hKey]; hKey
0x180012b17  test    rcx, rcx
0x180012b1a  jz      short loc_180012B43
0x180012b1c  mov     rax, rcx
0x180012b1f  mov     rdi, 0FFFFFFFF80000000h
0x180012b26  and     rax, rdi
0x180012b29  cmp     rax, rdi
0x180012b2c  jz      short loc_180012B43
0x180012b2e  call    cs:__imp_RegCloseKey
0x180012b34  test    eax, eax
0x180012b36  jz      short loc_180012B43
0x180012b38  call    cs:__imp_GetLastError
0x180012b3e  mov     rcx, rbx
0x180012b41  int     29h; Win8: RtlFailFast(ecx)
0x180012b43  mov     eax, 80070216h
0x180012b48  jmp     short loc_180012AE1
0x180012b4a  mov     [rbp+57h+var_80], 9CFh
0x180012b52  jmp     short loc_180012B5C
0x180012b54  mov     [rbp+57h+var_80], 9BCh
0x180012b5c  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x180012b63  mov     [rbp+57h+var_90], rax
0x180012b67  lea     rax, aUpdatereservem_41; "UpdateReserveManager::CalculateTotalPen"...
0x180012b6e  mov     [rbp+57h+var_88], rax
0x180012b72  lea     rax, aRetvalue; "RetValue"
0x180012b79  test    esi, esi
0x180012b7b  mov     [rbp+57h+var_78], rax
0x180012b7f  jle     short loc_180012B8A
0x180012b81  movzx   esi, si
0x180012b84  or      esi, 80070000h
0x180012b8a  mov     r8d, esi
0x180012b8d  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x180012b94  lea     rcx, [rbp+57h+var_90]
0x180012b98  call    RtlReportErrorOrigination
0x180012b9d  nop
0x180012b9e  lea     rcx, [rbp+57h+lpName]
0x180012ba2  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180012ba7  nop
0x180012ba8  mov     rcx, [rbp+57h+hKey]; hKey
0x180012bac  test    rcx, rcx
0x180012baf  jz      loc_1800128F4
0x180012bb5  mov     rdx, rcx
0x180012bb8  mov     rdi, 0FFFFFFFF80000000h
0x180012bbf  and     rdx, rdi
0x180012bc2  cmp     rdx, rdi
0x180012bc5  jz      loc_1800128F4
0x180012bcb  call    cs:__imp_RegCloseKey
0x180012bd1  test    eax, eax
0x180012bd3  jz      loc_1800128F4
0x180012bd9  call    cs:__imp_GetLastError
0x180012bdf  mov     rcx, rbx
0x180012be2  jmp     loc_1800128F2
```
