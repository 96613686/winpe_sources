# CRDPENCONResolver::IsTSListenerPort(ushort,int *)

- ea: `0x1800e6ebc`
- end: `0x1800e7395`
- name: `?IsTSListenerPort@CRDPENCONResolver@@CAJGPEAH@Z`
- size: `1241`
- prototype: `__int64 __fastcall(unsigned __int16, int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x1800e6a90`

## callees

- `0x1800018a4`
- `0x180004970`
- `0x180046a84`
- `0x18006e7d4`
- `0x1800e6ebc`
- `0x1800e7cac`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800e721d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800e721d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800e7178`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800e734d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800e7360`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800e7178`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800e734d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800e7360`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800e6f27`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800e719b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800e6f27`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800e719b`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800e6ffe`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800e6ffe`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800e7107`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800e7107`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800e70b2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800e70b2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800e7372`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800e7372`

## string_xrefs

- `0x1800e6f49`: `RegOpenKeyEx failed: 0x%x`

## pseudocode

```c
__int64 __fastcall CRDPENCONResolver::IsTSListenerPort(__int16 a1, int *a2)
{
  WCHAR *v4; // rdi
  int v5; // ecx
  int v6; // r8d
  int v7; // r9d
  unsigned int v8; // ebx
  __int64 *v9; // rdx
  const char **v10; // rax
  unsigned __int64 v11; // rax
  DWORD v12; // ebx
  LSTATUS v13; // esi
  unsigned int CurrentThreadActivityIdPrefix; // eax
  LSTATUS v15; // eax
  char v16; // si
  unsigned int v17; // eax
  int v18; // r8d
  int v19; // edx
  LSTATUS v20; // eax
  int *lpcbMaxSubKeyLen; // [rsp+28h] [rbp-51h]
  const char **lpcbMaxValueNameLen; // [rsp+40h] [rbp-39h]
  int *lpcbMaxValueLen; // [rsp+48h] [rbp-31h]
  int v25; // [rsp+60h] [rbp-19h] BYREF
  int v26; // [rsp+64h] [rbp-15h] BYREF
  int v27; // [rsp+68h] [rbp-11h] BYREF
  const char *v28; // [rsp+70h] [rbp-9h] BYREF
  const char *v29; // [rsp+78h] [rbp-1h] BYREF
  const char *v30; // [rsp+80h] [rbp+7h] BYREF
  HKEY phkResult; // [rsp+88h] [rbp+Fh] BYREF
  HKEY hKey; // [rsp+90h] [rbp+17h] BYREF
  DWORD cbData; // [rsp+98h] [rbp+1Fh] BYREF
  BYTE Data[52]; // [rsp+9Ch] [rbp+23h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+E8h] [rbp+6Fh] BYREF
  DWORD cSubKeys; // [rsp+F0h] [rbp+77h] BYREF
  DWORD cchName; // [rsp+F8h] [rbp+7Fh] BYREF

  cbData = 4;
  *a2 = 0;
  cSubKeys = 0;
  cbMaxSubKeyLen = 0;
  cchName = 0;
  *(_DWORD *)Data = 0;
  hKey = 0;
  phkResult = 0;
  v4 = 0;
  if ( RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SYSTEM\\CurrentControlSet\\Control\\Terminal Server\\WinStations",
         0,
         0x20019u,
         &hKey) )
  {
    v8 = -2147467259;
    if ( (unsigned int)CallbackContext <= 2 )
      goto LABEL_39;
    v27 = -2147467259;
    v30 = "RegOpenKeyEx failed: 0x%x";
    v28 = "IsTSListenerPort";
    lpcbMaxValueLen = &v27;
    v9 = qword_1801BE610;
    v25 = 753;
    lpcbMaxValueNameLen = &v28;
    lpcbMaxSubKeyLen = &v26;
    v10 = &v30;
    v26 = -2147467259;
    goto LABEL_4;
  }
  v8 = -2147467259;
  if ( RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0) )
  {
    if ( (unsigned int)CallbackContext <= 2 )
      goto LABEL_39;
    v26 = -2147467259;
    v28 = "RegQueryInfoKey failed: 0x%x";
    v30 = "IsTSListenerPort";
    lpcbMaxValueLen = &v26;
    v9 = (__int64 *)&byte_1801BE5C7;
    v25 = 766;
    lpcbMaxValueNameLen = &v30;
    lpcbMaxSubKeyLen = &v27;
    v10 = &v28;
    v27 = -2147467259;
LABEL_4:
    v29 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\rdpenconresolver.cpp";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v5,
      (_DWORD)v9,
      v6,
      v7,
      (__int64)v10,
      (__int64)lpcbMaxSubKeyLen,
      (__int64)&v29,
      (__int64)&v25,
      (__int64)lpcbMaxValueNameLen,
      (__int64)lpcbMaxValueLen);
    goto LABEL_39;
  }
  if ( cbMaxSubKeyLen == -1 || (v11 = 2LL * (cbMaxSubKeyLen + 1), v5 = -1, v11 > 0xFFFFFFFF) )
  {
    if ( (unsigned int)CallbackContext > 2 )
    {
      v30 = "IsTSListenerPort";
      v28 = "Subkey length too long";
      v26 = 777;
      v29 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\rdpenconresolver.cpp";
      v25 = -2147467259;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v5,
        (unsigned int)word_1801BE582,
        v6,
        v7,
        (__int64)&v28,
        (__int64)&v25,
        (__int64)&v29,
        (__int64)&v26,
        (__int64)&v30);
    }
  }
  else
  {
    v4 = (WCHAR *)LocalAlloc(0x40u, (unsigned int)v11);
    if ( v4 )
    {
      v12 = 0;
      if ( !cSubKeys )
      {
LABEL_32:
        *a2 = 0;
        v8 = 1;
        goto LABEL_39;
      }
      while ( 1 )
      {
        cchName = cbMaxSubKeyLen + 1;
        cbData = 4;
        v13 = RegEnumKeyExW(hKey, v12, v4, &cchName, 0, 0, 0, 0);
        if ( v13 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
          {
            CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_DLD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              30,
              &WPP_aabd390f80d63268e0df741d2a119417_Traceguids,
              CurrentThreadActivityIdPrefix,
              v13,
              v12);
          }
          goto LABEL_31;
        }
        if ( phkResult )
        {
          RegCloseKey(phkResult);
          phkResult = 0;
        }
        v15 = RegOpenKeyExW(hKey, v4, 0, 0x20019u, &phkResult);
        v16 = v15;
        if ( v15 )
          break;
        v20 = RegQueryValueExW(phkResult, L"PortNumber", 0, 0, Data, &cbData);
        v16 = v20;
        if ( v20 )
        {
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u )
          {
            goto LABEL_31;
          }
          v17 = RdpWppGetCurrentThreadActivityIdPrefix();
          v19 = 32;
LABEL_24:
          WPP_SF_DDS(*((_QWORD *)WPP_GLOBAL_Control + 2), v19, v18, v17, v16, (__int64)v4);
          goto LABEL_31;
        }
        if ( a1 == *(_WORD *)Data )
        {
          v8 = 0;
          *a2 = 1;
          goto LABEL_39;
        }
LABEL_31:
        if ( ++v12 >= cSubKeys )
          goto LABEL_32;
      }
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u )
      {
        goto LABEL_31;
      }
      v17 = RdpWppGetCurrentThreadActivityIdPrefix();
      v19 = 31;
      goto LABEL_24;
    }
  }
  if ( (unsigned int)CallbackContext > 2 )
  {
    v30 = "IsTSListenerPort";
    v28 = "Failed to allocate variable pszSubKeyName";
    v26 = 780;
    v29 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\rdpenconresolver.cpp";
    v25 = -2147467259;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      v5,
      (unsigned int)byte_1801BE53D,
      v6,
      v7,
      (__int64)&v28,
      (__int64)&v25,
      (__int64)&v29,
      (__int64)&v26,
      (__int64)&v30);
  }
  v8 = -2147024882;
LABEL_39:
  if ( phkResult )
  {
    RegCloseKey(phkResult);
    phkResult = 0;
  }
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( v4 )
    LocalFree(v4);
  return v8;
}

```

## disassembly

```asm
0x1800e6ebc  mov     [rsp-8+arg_0], rbx
0x1800e6ec1  push    rbp
0x1800e6ec2  push    rsi
0x1800e6ec3  push    rdi
0x1800e6ec4  push    r12
0x1800e6ec6  push    r13
0x1800e6ec8  push    r14
0x1800e6eca  push    r15
0x1800e6ecc  lea     rbp, [rsp-27h]
0x1800e6ed1  sub     rsp, 0A0h
0x1800e6ed8  xor     r13d, r13d
0x1800e6edb  mov     [rbp+57h+cbData], 4
0x1800e6ee2  mov     [rdx], r13d
0x1800e6ee5  lea     rax, [rbp+57h+hKey]
0x1800e6ee9  mov     r15, rdx
0x1800e6eec  mov     [rbp+57h+cSubKeys], r13d
0x1800e6ef0  movzx   r12d, cx
0x1800e6ef4  mov     [rbp+57h+cbMaxSubKeyLen], r13d
0x1800e6ef8  lea     rdx, aSystemCurrentc_4; "SYSTEM\\CurrentControlSet\\Control\\Ter"...
0x1800e6eff  mov     [rbp+57h+cchName], r13d
0x1800e6f03  mov     r9d, 20019h; samDesired
0x1800e6f09  mov     dword ptr [rbp+57h+Data], r13d
0x1800e6f0d  xor     r8d, r8d; ulOptions
0x1800e6f10  mov     [rbp+57h+hKey], r13
0x1800e6f14  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800e6f1b  mov     [rbp+57h+var_48], r13
0x1800e6f1f  mov     edi, r13d
0x1800e6f22  mov     [rsp+0D0h+phkResult], rax; phkResult
0x1800e6f27  call    cs:__imp_RegOpenKeyExW
0x1800e6f2d  test    eax, eax
0x1800e6f2f  jz      loc_1800E6FC2
0x1800e6f35  mov     eax, cs:CallbackContext
0x1800e6f3b  mov     ebx, 80004005h
0x1800e6f40  cmp     eax, 2
0x1800e6f43  jbe     loc_1800E7344
0x1800e6f49  lea     rax, aRegopenkeyexFa; "RegOpenKeyEx failed: 0x%x"
0x1800e6f50  mov     [rbp+57h+var_68], 80004005h
0x1800e6f57  mov     [rbp+57h+var_50], rax
0x1800e6f5b  lea     rsi, aIstslistenerpo; "IsTSListenerPort"
0x1800e6f62  lea     rax, [rbp+57h+var_68]
0x1800e6f66  mov     [rbp+57h+var_60], rsi
0x1800e6f6a  mov     [rsp+0D0h+lpcbMaxValueLen], rax
0x1800e6f6f  lea     rdx, qword_1801BE610
0x1800e6f76  lea     rax, [rbp+57h+var_60]
0x1800e6f7a  mov     [rbp+57h+var_70], 2F1h
0x1800e6f81  mov     [rsp+0D0h+lpcbMaxValueNameLen], rax
0x1800e6f86  lea     rax, [rbp+57h+var_70]
0x1800e6f8a  mov     [rsp+0D0h+lpcValues], rax
0x1800e6f8f  lea     rax, [rbp+57h+var_58]
0x1800e6f93  mov     [rsp+0D0h+lpcbMaxClassLen], rax
0x1800e6f98  lea     rax, [rbp+57h+var_6C]
0x1800e6f9c  mov     [rsp+0D0h+lpcbMaxSubKeyLen], rax
0x1800e6fa1  lea     rax, [rbp+57h+var_50]
0x1800e6fa5  mov     [rbp+57h+var_6C], ebx
0x1800e6fa8  lea     r14, aOnecoreTermsrv_39; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1800e6faf  mov     [rsp+0D0h+phkResult], rax
0x1800e6fb4  mov     [rbp+57h+var_58], r14
0x1800e6fb8  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800e6fbd  jmp     loc_1800E7344
0x1800e6fc2  mov     rcx, [rbp+57h+hKey]; hKey
0x1800e6fc6  lea     rax, [rbp+57h+cbMaxSubKeyLen]
0x1800e6fca  mov     [rsp+0D0h+lpftLastWriteTime], r13; lpftLastWriteTime
0x1800e6fcf  xor     r9d, r9d; lpReserved
0x1800e6fd2  mov     [rsp+0D0h+lpcbSecurityDescriptor], r13; lpcbSecurityDescriptor
0x1800e6fd7  xor     r8d, r8d; lpcchClass
0x1800e6fda  mov     [rsp+0D0h+lpcbMaxValueLen], r13; lpcbMaxValueLen
0x1800e6fdf  xor     edx, edx; lpClass
0x1800e6fe1  mov     [rsp+0D0h+lpcbMaxValueNameLen], r13; lpcbMaxValueNameLen
0x1800e6fe6  mov     [rsp+0D0h+lpcValues], r13; lpcValues
0x1800e6feb  mov     [rsp+0D0h+lpcbMaxClassLen], r13; lpcbMaxClassLen
0x1800e6ff0  mov     [rsp+0D0h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x1800e6ff5  lea     rax, [rbp+57h+cSubKeys]
0x1800e6ff9  mov     [rsp+0D0h+phkResult], rax; lpcSubKeys
0x1800e6ffe  call    cs:__imp_RegQueryInfoKeyW
0x1800e7004  mov     ebx, 80004005h
0x1800e7009  test    eax, eax
0x1800e700b  jz      short loc_1800E7080
0x1800e700d  mov     eax, cs:CallbackContext
0x1800e7013  cmp     eax, 2
0x1800e7016  jbe     loc_1800E7344
0x1800e701c  lea     rax, aRegqueryinfoke; "RegQueryInfoKey failed: 0x%x"
0x1800e7023  mov     [rbp+57h+var_6C], 80004005h
0x1800e702a  mov     [rbp+57h+var_60], rax
0x1800e702e  lea     rsi, aIstslistenerpo; "IsTSListenerPort"
0x1800e7035  lea     rax, [rbp+57h+var_6C]
0x1800e7039  mov     [rbp+57h+var_50], rsi
0x1800e703d  mov     [rsp+0D0h+lpcbMaxValueLen], rax
0x1800e7042  lea     rdx, byte_1801BE5C7
0x1800e7049  lea     rax, [rbp+57h+var_50]
0x1800e704d  mov     [rbp+57h+var_70], 2FEh
0x1800e7054  mov     [rsp+0D0h+lpcbMaxValueNameLen], rax
0x1800e7059  lea     rax, [rbp+57h+var_70]
0x1800e705d  mov     [rsp+0D0h+lpcValues], rax
0x1800e7062  lea     rax, [rbp+57h+var_58]
0x1800e7066  mov     [rsp+0D0h+lpcbMaxClassLen], rax
0x1800e706b  lea     rax, [rbp+57h+var_68]
0x1800e706f  mov     [rsp+0D0h+lpcbMaxSubKeyLen], rax
0x1800e7074  lea     rax, [rbp+57h+var_60]
0x1800e7078  mov     [rbp+57h+var_68], ebx
0x1800e707b  jmp     loc_1800E6FA8
0x1800e7080  mov     eax, [rbp+57h+cbMaxSubKeyLen]
0x1800e7083  lea     rsi, aIstslistenerpo; "IsTSListenerPort"
0x1800e708a  lea     r14, aOnecoreTermsrv_39; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1800e7091  add     eax, 1
0x1800e7094  jz      loc_1800E727D
0x1800e709a  add     rax, rax
0x1800e709d  mov     ecx, 0FFFFFFFFh
0x1800e70a2  cmp     rax, rcx
0x1800e70a5  ja      loc_1800E727D
0x1800e70ab  mov     edx, eax; uBytes
0x1800e70ad  mov     ecx, 40h ; '@'; uFlags
0x1800e70b2  call    cs:__imp_LocalAlloc
0x1800e70b8  mov     rdi, rax
0x1800e70bb  test    rax, rax
0x1800e70be  jz      loc_1800E72DE
0x1800e70c4  mov     ebx, r13d
0x1800e70c7  mov     r14d, 1
0x1800e70cd  cmp     [rbp+57h+cSubKeys], r13d
0x1800e70d1  jbe     loc_1800E7267
0x1800e70d7  mov     eax, [rbp+57h+cbMaxSubKeyLen]
0x1800e70da  lea     r9, [rbp+57h+cchName]; lpcchName
0x1800e70de  mov     rcx, [rbp+57h+hKey]; hKey
0x1800e70e2  inc     eax
0x1800e70e4  mov     [rsp+0D0h+lpcValues], r13; lpftLastWriteTime
0x1800e70e9  mov     r8, rdi; lpName
0x1800e70ec  mov     [rsp+0D0h+lpcbMaxClassLen], r13; lpcchClass
0x1800e70f1  mov     edx, ebx; dwIndex
0x1800e70f3  mov     [rsp+0D0h+lpcbMaxSubKeyLen], r13; lpClass
0x1800e70f8  mov     [rbp+57h+cchName], eax
0x1800e70fb  mov     [rbp+57h+cbData], 4
0x1800e7102  mov     [rsp+0D0h+phkResult], r13; lpReserved
0x1800e7107  call    cs:__imp_RegEnumKeyExW
0x1800e710d  mov     esi, eax
0x1800e710f  test    eax, eax
0x1800e7111  jz      short loc_1800E716F
0x1800e7113  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e711a  lea     rax, WPP_GLOBAL_Control
0x1800e7121  cmp     rcx, rax
0x1800e7124  jz      loc_1800E725B
0x1800e712a  test    [rcx+1Ch], r14b
0x1800e712e  jz      loc_1800E725B
0x1800e7134  cmp     byte ptr [rcx+19h], 3
0x1800e7138  jb      loc_1800E725B
0x1800e713e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800e7143  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e714a  lea     r8, WPP_aabd390f80d63268e0df741d2a119417_Traceguids
0x1800e7151  mov     edx, 1Eh
0x1800e7156  mov     dword ptr [rsp+0D0h+lpcbMaxSubKeyLen], ebx
0x1800e715a  mov     r9d, eax
0x1800e715d  mov     dword ptr [rsp+0D0h+phkResult], esi
0x1800e7161  mov     rcx, [rcx+10h]
0x1800e7165  call    WPP_SF_DLD
0x1800e716a  jmp     loc_1800E725B
0x1800e716f  mov     rcx, [rbp+57h+var_48]; hKey
0x1800e7173  test    rcx, rcx
0x1800e7176  jz      short loc_1800E7182
0x1800e7178  call    cs:__imp_RegCloseKey
0x1800e717e  mov     [rbp+57h+var_48], r13
0x1800e7182  mov     rcx, [rbp+57h+hKey]; hKey
0x1800e7186  lea     rax, [rbp+57h+var_48]
0x1800e718a  mov     r9d, 20019h; samDesired
0x1800e7190  mov     [rsp+0D0h+phkResult], rax; phkResult
0x1800e7195  xor     r8d, r8d; ulOptions
0x1800e7198  mov     rdx, rdi; lpSubKey
0x1800e719b  call    cs:__imp_RegOpenKeyExW
0x1800e71a1  mov     esi, eax
0x1800e71a3  test    eax, eax
0x1800e71a5  jz      short loc_1800E71FA
0x1800e71a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e71ae  lea     rax, WPP_GLOBAL_Control
0x1800e71b5  cmp     rcx, rax
0x1800e71b8  jz      loc_1800E725B
0x1800e71be  test    [rcx+1Ch], r14b
0x1800e71c2  jz      loc_1800E725B
0x1800e71c8  cmp     byte ptr [rcx+19h], 3
0x1800e71cc  jb      loc_1800E725B
0x1800e71d2  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800e71d7  mov     edx, 1Fh
0x1800e71dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e71e3  mov     r9d, eax
0x1800e71e6  mov     [rsp+0D0h+lpcbMaxSubKeyLen], rdi
0x1800e71eb  mov     dword ptr [rsp+0D0h+phkResult], esi
0x1800e71ef  mov     rcx, [rcx+10h]
0x1800e71f3  call    WPP_SF_DDS
0x1800e71f8  jmp     short loc_1800E725B
0x1800e71fa  mov     rcx, [rbp+57h+var_48]; hKey
0x1800e71fe  lea     rax, [rbp+57h+cbData]
0x1800e7202  mov     [rsp+0D0h+lpcbMaxSubKeyLen], rax; lpcbData
0x1800e7207  lea     rdx, aPortnumber; "PortNumber"
0x1800e720e  lea     rax, [rbp+57h+Data]
0x1800e7212  xor     r9d, r9d; lpType
0x1800e7215  xor     r8d, r8d; lpReserved
0x1800e7218  mov     [rsp+0D0h+phkResult], rax; lpData
0x1800e721d  call    cs:__imp_RegQueryValueExW
0x1800e7223  mov     esi, eax
0x1800e7225  test    eax, eax
0x1800e7227  jz      short loc_1800E7254
0x1800e7229  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e7230  lea     rax, WPP_GLOBAL_Control
0x1800e7237  cmp     rcx, rax
0x1800e723a  jz      short loc_1800E725B
0x1800e723c  test    [rcx+1Ch], r14b
0x1800e7240  jz      short loc_1800E725B
0x1800e7242  cmp     byte ptr [rcx+19h], 3
0x1800e7246  jb      short loc_1800E725B
0x1800e7248  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800e724d  mov     edx, 20h ; ' '
0x1800e7252  jmp     short loc_1800E71DC
0x1800e7254  cmp     r12w, word ptr [rbp+57h+Data]
0x1800e7259  jz      short loc_1800E7272
0x1800e725b  add     ebx, r14d
0x1800e725e  cmp     ebx, [rbp+57h+cSubKeys]
0x1800e7261  jb      loc_1800E70D7
0x1800e7267  mov     [r15], r13d
0x1800e726a  mov     ebx, r14d
0x1800e726d  jmp     loc_1800E7344
0x1800e7272  mov     ebx, r13d
0x1800e7275  mov     [r15], r14d
0x1800e7278  jmp     loc_1800E7344
0x1800e727d  mov     eax, cs:CallbackContext
0x1800e7283  cmp     eax, 2
0x1800e7286  jbe     short loc_1800E72DE
0x1800e7288  lea     rax, aSubkeyLengthTo; "Subkey length too long"
0x1800e728f  mov     [rbp+57h+var_50], rsi
0x1800e7293  mov     [rbp+57h+var_60], rax
0x1800e7297  lea     rdx, word_1801BE582
0x1800e729e  lea     rax, [rbp+57h+var_50]
0x1800e72a2  mov     [rbp+57h+var_6C], 309h
0x1800e72a9  mov     [rsp+0D0h+lpcbMaxValueNameLen], rax
0x1800e72ae  lea     rax, [rbp+57h+var_6C]
0x1800e72b2  mov     [rsp+0D0h+lpcValues], rax
0x1800e72b7  lea     rax, [rbp+57h+var_58]
0x1800e72bb  mov     [rsp+0D0h+lpcbMaxClassLen], rax
0x1800e72c0  lea     rax, [rbp+57h+var_70]
0x1800e72c4  mov     [rsp+0D0h+lpcbMaxSubKeyLen], rax
0x1800e72c9  lea     rax, [rbp+57h+var_60]
0x1800e72cd  mov     [rsp+0D0h+phkResult], rax
0x1800e72d2  mov     [rbp+57h+var_58], r14
0x1800e72d6  mov     [rbp+57h+var_70], ebx
0x1800e72d9  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800e72de  mov     eax, cs:CallbackContext
0x1800e72e4  cmp     eax, 2
0x1800e72e7  jbe     short loc_1800E733F
0x1800e72e9  lea     rax, aFailedToAlloca_4; "Failed to allocate variable pszSubKeyNa"...
0x1800e72f0  mov     [rbp+57h+var_50], rsi
0x1800e72f4  mov     [rbp+57h+var_60], rax
0x1800e72f8  lea     rdx, byte_1801BE53D
0x1800e72ff  lea     rax, [rbp+57h+var_50]
0x1800e7303  mov     [rbp+57h+var_6C], 30Ch
0x1800e730a  mov     [rsp+0D0h+lpcbMaxValueNameLen], rax
0x1800e730f  lea     rax, [rbp+57h+var_6C]
0x1800e7313  mov     [rsp+0D0h+lpcValues], rax
0x1800e7318  lea     rax, [rbp+57h+var_58]
0x1800e731c  mov     [rsp+0D0h+lpcbMaxClassLen], rax
0x1800e7321  lea     rax, [rbp+57h+var_70]
0x1800e7325  mov     [rsp+0D0h+lpcbMaxSubKeyLen], rax
0x1800e732a  lea     rax, [rbp+57h+var_60]
0x1800e732e  mov     [rsp+0D0h+phkResult], rax
0x1800e7333  mov     [rbp+57h+var_58], r14
0x1800e7337  mov     [rbp+57h+var_70], ebx
0x1800e733a  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800e733f  mov     ebx, 8007000Eh
0x1800e7344  mov     rcx, [rbp+57h+var_48]; hKey
0x1800e7348  test    rcx, rcx
0x1800e734b  jz      short loc_1800E7357
0x1800e734d  call    cs:__imp_RegCloseKey
0x1800e7353  mov     [rbp+57h+var_48], r13
0x1800e7357  mov     rcx, [rbp+57h+hKey]; hKey
0x1800e735b  test    rcx, rcx
0x1800e735e  jz      short loc_1800E736A
0x1800e7360  call    cs:__imp_RegCloseKey
0x1800e7366  mov     [rbp+57h+hKey], r13
0x1800e736a  test    rdi, rdi
0x1800e736d  jz      short loc_1800E7378
0x1800e736f  mov     rcx, rdi; hMem
0x1800e7372  call    cs:__imp_LocalFree
0x1800e7378  mov     eax, ebx
0x1800e737a  mov     rbx, [rsp+0D0h+arg_0]
0x1800e7382  add     rsp, 0A0h
0x1800e7389  pop     r15
0x1800e738b  pop     r14
0x1800e738d  pop     r13
0x1800e738f  pop     r12
0x1800e7391  pop     rdi
0x1800e7392  pop     rsi
0x1800e7393  pop     rbp
0x1800e7394  retn
```
