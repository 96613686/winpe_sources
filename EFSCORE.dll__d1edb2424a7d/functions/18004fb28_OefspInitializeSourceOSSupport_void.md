# OefspInitializeSourceOSSupport(void)

- ea: `0x18004fb28`
- end: `0x18004fec1`
- name: `?OefspInitializeSourceOSSupport@@YAJXZ`
- size: `921`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18004e7dc`

## callees

- `0x180007c60`
- `0x18000b12c`
- `0x18000dc8c`
- `0x18000eb4c`
- `0x18000ef44`
- `0x180045f68`
- `0x18004c9f0`
- `0x18004ce0c`
- `0x18004d12c`
- `0x18004d1f0`
- `0x18004d3fc`
- `0x18004fb28`
- `0x180051858`
- `0x1800dddf0`

## import_xrefs

- `msvcrt!_wtoi64` at `0x18004fcf9`
- `msvcrt!_wtoi64` at `0x18004fcf9`
- `msvcrt!_wcsnicmp` at `0x18004fc8a`
- `msvcrt!_wcsnicmp` at `0x18004fc8a`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18004fc63`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18004fc63`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004fccc`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004fccc`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18004fbd2`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18004fbd2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004fb82`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004fb82`

## string_xrefs

- `0x18004fbe5`: `onecoreuap\ds\security\efs\dll\efsonline.cxx`
- `0x18004fcdb`: `onecoreuap\ds\security\efs\dll\efsonline.cxx`
- `0x18004fd17`: `onecoreuap\ds\security\efs\dll\efsonline.cxx`
- `0x18004fe61`: `onecoreuap\ds\security\efs\dll\efsonline.cxx`
- `0x18004fe76`: `onecoreuap\ds\security\efs\dll\efsonline.cxx`
- `0x18004fc83`: `Source OS (Updated on`

## pseudocode

```c
__int64 OefspInitializeSourceOSSupport(void)
{
  unsigned int v0; // eax
  __int64 v1; // rdx
  const char *v2; // r9
  unsigned int v3; // ebx
  DWORD v4; // ecx
  WCHAR *v5; // rbx
  __int64 v6; // rsi
  char v7; // r15
  DWORD v8; // r14d
  char v9; // di
  unsigned int ValueW; // eax
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // rax
  __int64 v14; // rdx
  __int64 v15; // rdx
  char v16; // al
  int v18; // eax
  __int64 v19; // rcx
  unsigned __int64 v20; // r9
  __int64 v21; // rdx
  int wnf_subscription; // eax
  wil::details *v23; // rcx
  struct wil::details::wnf_subscription_state_base *v24; // rdx
  unsigned int phkResult; // [rsp+20h] [rbp-E0h]
  _BYTE v26[4]; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+64h] [rbp-9Ch] BYREF
  DWORD pcbData; // [rsp+68h] [rbp-98h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-90h] BYREF
  LPWSTR lpName; // [rsp+78h] [rbp-88h] BYREF
  int v31; // [rsp+80h] [rbp-80h] BYREF
  wil::details *v32; // [rsp+88h] [rbp-78h] BYREF
  DWORD cchName[4]; // [rsp+90h] [rbp-70h] BYREF
  wchar_t pvData; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD v35[15]; // [rsp+A8h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+68h]

  hKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  v0 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\Setup", 0, 0x20019u, &hKey);
  if ( !v0 )
  {
    cbMaxSubKeyLen = 0;
    v0 = RegQueryInfoKeyW(hKey, 0, 0, 0, 0, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
    if ( v0 )
    {
      v1 = 132;
      goto LABEL_5;
    }
    v4 = cbMaxSubKeyLen + 1;
    if ( cbMaxSubKeyLen + 1 < cbMaxSubKeyLen )
    {
      v3 = -2147024362;
      cbMaxSubKeyLen = -1;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x86,
        (unsigned int)"onecoreuap\\ds\\security\\efs\\dll\\efsonline.cxx",
        (const char *)0x80070216LL,
        phkResult);
      goto LABEL_45;
    }
    ++cbMaxSubKeyLen;
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &lpName,
      0,
      v4,
      v2);
    v5 = lpName;
    if ( lpName )
    {
      v6 = 0;
      v7 = 0;
      v8 = 0;
      v9 = 1;
      while ( 1 )
      {
        cchName[0] = cbMaxSubKeyLen;
        ValueW = RegEnumKeyExW(hKey, v8, v5, cchName, 0, 0, 0, 0);
        if ( ValueW == 259 )
          break;
        if ( ValueW )
        {
          v14 = 147;
          goto LABEL_19;
        }
        if ( !_wcsnicmp(v5, L"Source OS (Updated on", 0x15u) )
        {
          pcbData = 128;
          v7 = 1;
          ValueW = RegGetValueW(hKey, v5, L"CurrentBuildNumber", 2u, 0, &pvData, &pcbData);
          if ( ValueW == 2 )
          {
            wil::details::in1diag3::Log_Win32(
              retaddr,
              (void *)0x9F,
              (unsigned int)"onecoreuap\\ds\\security\\efs\\dll\\efsonline.cxx",
              (const char *)2,
              phkResult);
          }
          else
          {
            if ( ValueW )
            {
              v14 = 162;
LABEL_19:
              v3 = wil::details::in1diag3::Return_Win32(
                     retaddr,
                     (void *)v14,
                     (unsigned int)"onecoreuap\\ds\\security\\efs\\dll\\efsonline.cxx",
                     (const char *)ValueW,
                     phkResult);
              goto LABEL_20;
            }
            v13 = _wtoi64(&pvData);
            if ( v13 > v6 )
              v6 = v13;
          }
        }
        ++v8;
      }
      if ( v6 || v7 )
      {
        v16 = byte_1801173A8;
      }
      else
      {
        v16 = 1;
        byte_1801173A8 = 1;
      }
      if ( v16 )
        goto LABEL_29;
      if ( v6 > 16299 )
      {
        byte_1801173A8 = 1;
LABEL_29:
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(
          &lpName,
          v11);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        return 0;
      }
      v31 = 0;
      pcbData = 0;
      v26[0] = 0;
      v18 = wil::wnf_query_nothrow<unsigned long>(v12, v26, &v31, &pcbData);
      v3 = v18;
      if ( v18 < 0 )
      {
        v20 = (unsigned int)v18;
        v21 = 199;
        goto LABEL_43;
      }
      if ( v26[0] && v31 )
        byte_1801173A8 = 1;
      else
        v9 = byte_1801173A8;
      if ( v9 )
        goto LABEL_29;
      v35[0] = off_1800E1E30;
      v32 = 0;
      v35[13] = v35;
      wnf_subscription = wil::details::make_wnf_subscription_state<unsigned long>(v19, &pvData, pcbData, &v32);
      v23 = 0;
      if ( wnf_subscription >= 0 )
        v23 = v32;
      v32 = v23;
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>>::operator=(
        (wil::details **)&qword_180117048,
        &v32);
      wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>(
        &v32,
        v24);
      wistd::function<void (_EDP_DPL_WNF_KEYS_STATE_DATA const &)>::~function<void (_EDP_DPL_WNF_KEYS_STATE_DATA const &)>(&pvData);
      if ( qword_180117048 )
        goto LABEL_29;
      v3 = -2147418113;
      v21 = 220;
    }
    else
    {
      v3 = -2147024882;
      v21 = 136;
    }
    v20 = v3;
LABEL_43:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v21,
      (unsigned int)"onecoreuap\\ds\\security\\efs\\dll\\efsonline.cxx",
      (const char *)v20,
      phkResult);
LABEL_20:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(
      &lpName,
      v15);
    goto LABEL_45;
  }
  v1 = 129;
LABEL_5:
  v3 = wil::details::in1diag3::Return_Win32(
         retaddr,
         (void *)v1,
         (unsigned int)"onecoreuap\\ds\\security\\efs\\dll\\efsonline.cxx",
         (const char *)v0,
         phkResult);
LABEL_45:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return v3;
}

```

## disassembly

```asm
0x18004fb28  push    rbp
0x18004fb2a  push    rbx
0x18004fb2b  push    rsi
0x18004fb2c  push    rdi
0x18004fb2d  push    r12
0x18004fb2f  push    r14
0x18004fb31  push    r15
0x18004fb33  lea     rbp, [rsp-30h]
0x18004fb38  sub     rsp, 130h
0x18004fb3f  mov     rax, cs:__security_cookie
0x18004fb46  xor     rax, rsp
0x18004fb49  mov     [rbp+60h+var_40], rax
0x18004fb4d  xor     r12d, r12d
0x18004fb50  lea     rcx, [rsp+160h+hKey]
0x18004fb55  xor     edx, edx
0x18004fb57  mov     [rsp+160h+hKey], r12
0x18004fb5c  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18004fb61  lea     rax, [rsp+160h+hKey]
0x18004fb66  mov     r9d, 20019h; samDesired
0x18004fb6c  xor     r8d, r8d; ulOptions
0x18004fb6f  mov     [rsp+160h+phkResult], rax; phkResult
0x18004fb74  lea     rdx, aSystemSetup; "SYSTEM\\Setup"
0x18004fb7b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18004fb82  call    cs:__imp_RegOpenKeyExW
0x18004fb88  test    eax, eax
0x18004fb8a  jz      short loc_18004FB93
0x18004fb8c  mov     edx, 81h
0x18004fb91  jmp     short loc_18004FBE1
0x18004fb93  mov     rcx, [rsp+160h+hKey]; hKey
0x18004fb98  lea     rax, [rsp+160h+cbMaxSubKeyLen]
0x18004fb9d  mov     [rsp+160h+lpftLastWriteTime], r12; lpftLastWriteTime
0x18004fba2  xor     r9d, r9d; lpReserved
0x18004fba5  mov     [rsp+160h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x18004fbaa  xor     r8d, r8d; lpcchClass
0x18004fbad  mov     [rsp+160h+lpcbMaxValueLen], r12; lpcbMaxValueLen
0x18004fbb2  xor     edx, edx; lpClass
0x18004fbb4  mov     [rsp+160h+lpcbMaxValueNameLen], r12; lpcbMaxValueNameLen
0x18004fbb9  mov     [rsp+160h+lpcValues], r12; lpcValues
0x18004fbbe  mov     [rsp+160h+lpcbMaxClassLen], r12; lpcbMaxClassLen
0x18004fbc3  mov     [rsp+160h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x18004fbc8  mov     [rsp+160h+phkResult], r12; int
0x18004fbcd  mov     [rsp+160h+cbMaxSubKeyLen], r12d
0x18004fbd2  call    cs:__imp_RegQueryInfoKeyW
0x18004fbd8  test    eax, eax
0x18004fbda  jz      short loc_18004FBFB
0x18004fbdc  mov     edx, 84h; void *
0x18004fbe1  mov     rcx, [rbp+68h]; this
0x18004fbe5  lea     r8, aOnecoreuapDsSe_10; "onecoreuap\\ds\\security\\efs\\dll\\efs"...
0x18004fbec  mov     r9d, eax; char *
0x18004fbef  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18004fbf4  mov     ebx, eax
0x18004fbf6  jmp     loc_18004FE97
0x18004fbfb  mov     eax, [rsp+160h+cbMaxSubKeyLen]
0x18004fbff  lea     ecx, [rax+1]
0x18004fc02  cmp     ecx, eax
0x18004fc04  jb      loc_18004FE72
0x18004fc0a  mov     [rsp+160h+cbMaxSubKeyLen], ecx
0x18004fc0e  xor     edx, edx
0x18004fc10  mov     r8d, ecx
0x18004fc13  lea     rcx, [rsp+160h+lpName]
0x18004fc18  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18004fc1d  mov     rbx, [rsp+160h+lpName]
0x18004fc22  test    rbx, rbx
0x18004fc25  jz      loc_18004FE50
0x18004fc2b  mov     rsi, r12
0x18004fc2e  mov     r15b, r12b
0x18004fc31  mov     r14d, r12d
0x18004fc34  mov     edi, 1
0x18004fc39  mov     eax, [rsp+160h+cbMaxSubKeyLen]
0x18004fc3d  lea     r9, [rbp+60h+cchName]; lpcchName
0x18004fc41  mov     rcx, [rsp+160h+hKey]; hKey
0x18004fc46  mov     r8, rbx; lpName
0x18004fc49  mov     [rsp+160h+lpcValues], r12; lpftLastWriteTime
0x18004fc4e  mov     edx, r14d; dwIndex
0x18004fc51  mov     [rsp+160h+lpcbMaxClassLen], r12; lpcchClass
0x18004fc56  mov     [rsp+160h+lpcbMaxSubKeyLen], r12; lpClass
0x18004fc5b  mov     [rsp+160h+phkResult], r12; lpReserved
0x18004fc60  mov     [rbp+60h+cchName], eax
0x18004fc63  call    cs:__imp_RegEnumKeyExW
0x18004fc69  cmp     eax, 103h
0x18004fc6e  jz      loc_18004FD3E
0x18004fc74  test    eax, eax
0x18004fc76  jnz     loc_18004FD37
0x18004fc7c  lea     r8d, [rax+15h]; MaxCount
0x18004fc80  mov     rcx, rbx; String1
0x18004fc83  lea     rdx, aSourceOsUpdate; "Source OS (Updated on"
0x18004fc8a  call    cs:__imp__wcsnicmp
0x18004fc90  test    eax, eax
0x18004fc92  jnz     short loc_18004FD06
0x18004fc94  mov     rcx, [rsp+160h+hKey]; hkey
0x18004fc99  lea     rax, [rsp+160h+pcbData]
0x18004fc9e  mov     [rsp+160h+lpcbMaxClassLen], rax; pcbData
0x18004fca3  lea     r8, aCurrentbuildnu; "CurrentBuildNumber"
0x18004fcaa  lea     rax, [rbp+60h+pvData]
0x18004fcae  mov     [rsp+160h+pcbData], 80h
0x18004fcb6  mov     [rsp+160h+lpcbMaxSubKeyLen], rax; pvData
0x18004fcbb  mov     r9d, 2; dwFlags
0x18004fcc1  mov     rdx, rbx; lpSubKey
0x18004fcc4  mov     [rsp+160h+phkResult], r12; unsigned int
0x18004fcc9  mov     r15b, dil
0x18004fccc  call    cs:__imp_RegGetValueW
0x18004fcd2  cmp     eax, 2
0x18004fcd5  jnz     short loc_18004FCF1
0x18004fcd7  mov     rcx, [rbp+68h]; this
0x18004fcdb  lea     r8, aOnecoreuapDsSe_10; "onecoreuap\\ds\\security\\efs\\dll\\efs"...
0x18004fce2  mov     r9d, eax; char *
0x18004fce5  mov     edx, 9Fh; void *
0x18004fcea  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x18004fcef  jmp     short loc_18004FD06
0x18004fcf1  test    eax, eax
0x18004fcf3  jnz     short loc_18004FD0E
0x18004fcf5  lea     rcx, [rbp+60h+pvData]; String
0x18004fcf9  call    cs:__imp__wtoi64
0x18004fcff  cmp     rax, rsi
0x18004fd02  cmovg   rsi, rax
0x18004fd06  add     r14d, edi
0x18004fd09  jmp     loc_18004FC39
0x18004fd0e  mov     edx, 0A2h; void *
0x18004fd13  mov     rcx, [rbp+68h]; this
0x18004fd17  lea     r8, aOnecoreuapDsSe_10; "onecoreuap\\ds\\security\\efs\\dll\\efs"...
0x18004fd1e  mov     r9d, eax; char *
0x18004fd21  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18004fd26  mov     ebx, eax
0x18004fd28  lea     rcx, [rsp+160h+lpName]
0x18004fd2d  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18004fd32  jmp     loc_18004FE97
0x18004fd37  mov     edx, 93h
0x18004fd3c  jmp     short loc_18004FD13
0x18004fd3e  test    rsi, rsi
0x18004fd41  jnz     short loc_18004FD53
0x18004fd43  test    r15b, r15b
0x18004fd46  jnz     short loc_18004FD53
0x18004fd48  mov     al, dil
0x18004fd4b  mov     cs:byte_1801173A8, al
0x18004fd51  jmp     short loc_18004FD59
0x18004fd53  mov     al, cs:byte_1801173A8
0x18004fd59  test    al, al
0x18004fd5b  jnz     short loc_18004FD6D
0x18004fd5d  cmp     rsi, 3FABh
0x18004fd64  jle     short loc_18004FD88
0x18004fd66  mov     cs:byte_1801173A8, dil
0x18004fd6d  lea     rcx, [rsp+160h+lpName]
0x18004fd72  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18004fd77  lea     rcx, [rsp+160h+hKey]
0x18004fd7c  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18004fd81  xor     eax, eax
0x18004fd83  jmp     loc_18004FEA3
0x18004fd88  lea     r9, [rsp+160h+pcbData]
0x18004fd8d  mov     [rbp+60h+var_E0], r12d
0x18004fd91  lea     r8, [rbp+60h+var_E0]
0x18004fd95  mov     [rsp+160h+pcbData], r12d
0x18004fd9a  lea     rdx, [rsp+160h+var_100]
0x18004fd9f  mov     [rsp+160h+var_100], r12b
0x18004fda4  call    ??$wnf_query_nothrow@K@wil@@YAJAEBU_WNF_STATE_NAME@@PEA_NPEAKPEAUWNF_CHANGE_STAMP_STRUCT@0@@Z; wil::wnf_query_nothrow<ulong>(_WNF_STATE_NAME const &,bool *,ulong *,wil::WNF_CHANGE_STAMP_STRUCT *)
0x18004fda9  mov     ebx, eax
0x18004fdab  test    eax, eax
0x18004fdad  jns     short loc_18004FDBC
0x18004fdaf  mov     r9d, eax
0x18004fdb2  mov     edx, 0C7h
0x18004fdb7  jmp     loc_18004FE5D
0x18004fdbc  cmp     [rsp+160h+var_100], r12b
0x18004fdc1  jz      short loc_18004FDD2
0x18004fdc3  cmp     [rbp+60h+var_E0], r12d
0x18004fdc7  jz      short loc_18004FDD2
0x18004fdc9  mov     cs:byte_1801173A8, dil
0x18004fdd0  jmp     short loc_18004FDD9
0x18004fdd2  mov     dil, cs:byte_1801173A8
0x18004fdd9  test    dil, dil
0x18004fddc  jnz     short loc_18004FD6D
0x18004fdde  mov     r8d, [rsp+160h+pcbData]
0x18004fde3  lea     rax, off_1800E1E30
0x18004fdea  mov     [rbp+60h+var_B8], rax
0x18004fdee  lea     r9, [rbp+60h+var_D8]
0x18004fdf2  lea     rax, [rbp+60h+var_B8]
0x18004fdf6  mov     [rbp+60h+var_D8], r12
0x18004fdfa  lea     rdx, [rbp+60h+pvData]
0x18004fdfe  mov     [rbp+60h+var_50], rax
0x18004fe02  call    ??$make_wnf_subscription_state@K@details@wil@@YAJAEBU_WNF_STATE_NAME@@$$QEAV?$function@$$A6AXAEBK@Z@wistd@@KPEAPEAU?$wnf_subscription_state@K@01@@Z; wil::details::make_wnf_subscription_state<ulong>(_WNF_STATE_NAME const &,wistd::function<void (ulong const &)> &&,ulong,wil::details::wnf_subscription_state<ulong> * *)
0x18004fe07  test    eax, eax
0x18004fe09  lea     rdx, [rbp+60h+var_D8]
0x18004fe0d  mov     rcx, r12
0x18004fe10  cmovns  rcx, [rbp+60h+var_D8]
0x18004fe15  mov     [rbp+60h+var_D8], rcx
0x18004fe19  lea     rcx, qword_180117048
0x18004fe20  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>> &&)
0x18004fe25  lea     rcx, [rbp+60h+var_D8]
0x18004fe29  call    ??1?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>(void)
0x18004fe2e  lea     rcx, [rbp+60h+pvData]
0x18004fe32  call    ??1?$function@$$A6AXAEBU_EDP_DPL_WNF_KEYS_STATE_DATA@@@Z@wistd@@QEAA@XZ; wistd::function<void (_EDP_DPL_WNF_KEYS_STATE_DATA const &)>::~function<void (_EDP_DPL_WNF_KEYS_STATE_DATA const &)>(void)
0x18004fe37  cmp     cs:qword_180117048, r12
0x18004fe3e  jnz     loc_18004FD6D
0x18004fe44  mov     ebx, 8000FFFFh
0x18004fe49  mov     edx, 0DCh
0x18004fe4e  jmp     short loc_18004FE5A
0x18004fe50  mov     ebx, 8007000Eh
0x18004fe55  mov     edx, 88h; void *
0x18004fe5a  mov     r9d, ebx; char *
0x18004fe5d  mov     rcx, [rbp+68h]; this
0x18004fe61  lea     r8, aOnecoreuapDsSe_10; "onecoreuap\\ds\\security\\efs\\dll\\efs"...
0x18004fe68  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004fe6d  jmp     loc_18004FD28
0x18004fe72  mov     rcx, [rbp+68h]; this
0x18004fe76  lea     r8, aOnecoreuapDsSe_10; "onecoreuap\\ds\\security\\efs\\dll\\efs"...
0x18004fe7d  mov     ebx, 80070216h
0x18004fe82  mov     [rsp+160h+cbMaxSubKeyLen], 0FFFFFFFFh
0x18004fe8a  mov     r9d, ebx; char *
0x18004fe8d  mov     edx, 86h; void *
0x18004fe92  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004fe97  lea     rcx, [rsp+160h+hKey]
0x18004fe9c  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18004fea1  mov     eax, ebx
0x18004fea3  mov     rcx, [rbp+60h+var_40]
0x18004fea7  xor     rcx, rsp; StackCookie
0x18004feaa  call    __security_check_cookie
0x18004feaf  add     rsp, 130h
0x18004feb6  pop     r15
0x18004feb8  pop     r14
0x18004feba  pop     r12
0x18004febc  pop     rdi
0x18004febd  pop     rsi
0x18004febe  pop     rbx
0x18004febf  pop     rbp
0x18004fec0  retn
```
