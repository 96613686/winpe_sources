# CtapPluginInternal::GetPluginAuthenticatorLocationListFromRegistryForRp(void * const,HKEY__ *,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,_WEBAUTHN_COSE_CREDENTIAL_PARAMETERS *,std::map<FidoCredProvHelper::Locations::PluginAuthenticator,PluginAuthenticatorState,std::less<FidoCredProvHelper::Locations::PluginAuthenticator>,std::allocator<std::pair<FidoCredProvHelper::Locations::PluginAuthenticator const,PluginAuthenticatorState>>> &)

- ea: `0x18004273c`
- end: `0x180042def`
- name: `?GetPluginAuthenticatorLocationListFromRegistryForRp@CtapPluginInternal@@YAJQEAXPEAUHKEY__@@AEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@4@PEAU_WEBAUTHN_COSE_CREDENTIAL_PARAMETERS@@AEAV?$map@UPluginAuthenticator@Locations@FidoCredProvHelper@@UPluginAuthenticatorState@@U?$less@UPluginAuthenticator@Locations@FidoCredProvHelper@@@std@@V?$allocator@U?$pair@$$CBUPluginAuthenticator@Locations@FidoCredProvHelper@@UPluginAuthenticatorState@@@std@@@6@@4@@Z`
- size: `1715`
- prototype: ``
- caller_count: `1`
- callee_count: `27`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18010d4f0`

## callees

- `0x18001687c`
- `0x18001d5e4`
- `0x1800205e4`
- `0x180021878`
- `0x1800328b8`
- `0x180036da4`
- `0x180037f6c`
- `0x180041a14`
- `0x180042154`
- `0x18004273c`
- `0x180042df8`
- `0x180042e40`
- `0x180042e60`
- `0x180043f2c`
- `0x180043f54`
- `0x180099b38`
- `0x18009c824`
- `0x1800ae768`
- `0x18010b550`
- `0x18010bfa8`
- `0x18010dc7c`
- `0x18010de04`
- `0x18010de38`
- `0x18010e5cc`
- `0x18010ee78`
- `0x18010eef8`
- `0x18013c090`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180042af1`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180042af1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180042a36`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180042b18`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180042c5d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180042a36`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180042b18`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180042c5d`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800427db`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800427db`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004288b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004288b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800428d4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004292e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800428d4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004292e`
- `api-ms-win-core-registry-l2-1-0!RegEnumKeyW` at `0x18004284b`
- `api-ms-win-core-registry-l2-1-0!RegEnumKeyW` at `0x18004284b`

## string_xrefs

- `0x1800427f0`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x180042a11`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x180042c9d`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=12 #try_helpers=1
__int64 __fastcall CtapPluginInternal::GetPluginAuthenticatorLocationListFromRegistryForRp(
        CtapPluginInternal *a1,
        HKEY a2,
        __int64 *a3,
        __int64 a4,
        __int64 a5,
        __int64 a6)
{
  __int64 *v6; // r14
  HKEY v7; // rbx
  unsigned int v8; // eax
  DWORD i; // r12d
  HKEY *v11; // rax
  __int128 v12; // rdi
  HKEY v13; // rcx
  HKEY v14; // rcx
  __int64 v15; // rbx
  int CtapCborAuthenticatorInfoFromRegistry; // ebx
  HLOCAL v17; // rcx
  HLOCAL v18; // rcx
  __int64 v19; // rbx
  __int64 v20; // r14
  __int64 j; // rdi
  __int64 v22; // r8
  __int64 v23; // rdx
  __int64 v24; // rsi
  unsigned int v25; // edi
  struct PluginAuthenticatorState *v26; // r9
  __int64 k; // rbx
  __int64 v28; // rbx
  __int64 v29; // rdi
  _QWORD *v30; // rax
  HLOCAL v31; // rcx
  int AuthenticatorState; // eax
  int v33; // ebx
  void *v34; // rcx
  __int64 v35; // rcx
  unsigned int lpcSubKeys; // [rsp+20h] [rbp-1F8h]
  int lpcSubKeysa; // [rsp+20h] [rbp-1F8h]
  unsigned __int16 v38[2]; // [rsp+60h] [rbp-1B8h] BYREF
  HLOCAL hMem; // [rsp+68h] [rbp-1B0h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+70h] [rbp-1A8h] BYREF
  DWORD cSubKeys; // [rsp+74h] [rbp-1A4h] BYREF
  HKEY v42; // [rsp+78h] [rbp-1A0h]
  DWORD cbData; // [rsp+80h] [rbp-198h] BYREF
  __int128 v44; // [rsp+88h] [rbp-190h] BYREF
  void *v45; // [rsp+98h] [rbp-180h] BYREF
  __int64 v46; // [rsp+A0h] [rbp-178h]
  __int128 v47; // [rsp+A8h] [rbp-170h] BYREF
  __int64 *v48; // [rsp+B8h] [rbp-160h]
  LPWSTR lpName[3]; // [rsp+C0h] [rbp-158h] BYREF
  __int64 v50; // [rsp+D8h] [rbp-140h]
  CtapPluginInternal *v51; // [rsp+E0h] [rbp-138h]
  int v52; // [rsp+F0h] [rbp-128h] BYREF
  _QWORD v53[2]; // [rsp+F8h] [rbp-120h] BYREF
  _BYTE v54[24]; // [rsp+108h] [rbp-110h] BYREF
  __int64 v55; // [rsp+120h] [rbp-F8h]
  __int64 v56; // [rsp+128h] [rbp-F0h]
  LPBYTE lpData[3]; // [rsp+130h] [rbp-E8h] BYREF
  _BYTE v58[8]; // [rsp+148h] [rbp-D0h] BYREF
  _BYTE v59[16]; // [rsp+150h] [rbp-C8h] BYREF
  _BYTE v60[16]; // [rsp+160h] [rbp-B8h] BYREF
  HLOCAL *p_hMem; // [rsp+170h] [rbp-A8h] BYREF
  __int64 v62; // [rsp+178h] [rbp-A0h] BYREF
  char v63; // [rsp+180h] [rbp-98h]
  _BYTE v64[32]; // [rsp+190h] [rbp-88h] BYREF
  _BYTE v65[32]; // [rsp+1B0h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+218h] [rbp+0h]

  v50 = a4;
  v6 = a3;
  v48 = a3;
  v7 = a2;
  v42 = a2;
  v51 = a1;
  cSubKeys = 0;
  cbMaxSubKeyLen = 0;
  v8 = RegQueryInfoKeyW(a2, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
  if ( v8 )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0xDEE,
             (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
             (const char *)v8,
             lpcSubKeys);
  ++cbMaxSubKeyLen;
  std::map<FidoCredProvHelper::Locations::PluginAuthenticator,PluginAuthenticatorState>::map<FidoCredProvHelper::Locations::PluginAuthenticator,PluginAuthenticatorState>(&v45);
  for ( i = 0; i < cSubKeys; ++i )
  {
    std::vector<unsigned short>::vector<unsigned short>(lpName, cbMaxSubKeyLen);
    if ( RegEnumKeyW(v7, i, lpName[0], cbMaxSubKeyLen) )
      goto LABEL_60;
    v47 = 0;
    v11 = (HKEY *)wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>>::put(&v47);
    if ( !RegOpenKeyExW(v7, lpName[0], 0, 0x20019u, v11) )
    {
      cbData = 0;
      *(_QWORD *)&v12 = v47;
      v13 = (_QWORD)v47 ? *(HKEY *)v47 : 0LL;
      if ( !RegQueryValueExW(v13, L"Name", 0, 0, 0, &cbData) )
      {
        std::vector<unsigned short>::vector<unsigned short>(lpData, (unsigned __int64)cbData >> 1);
        if ( (_QWORD)v12 )
          v14 = *(HKEY *)v12;
        else
          v14 = 0;
        if ( RegQueryValueExW(v14, L"Name", 0, 0, lpData[0], &cbData) )
          goto LABEL_58;
        v44 = 0;
        *((_QWORD *)&v12 + 1) = *((_QWORD *)&v47 + 1);
        if ( *((_QWORD *)&v47 + 1) )
        {
          v15 = *((_QWORD *)&v47 + 1) + 8LL;
          _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)&v47 + 1) + 8LL));
        }
        else
        {
          v15 = 8;
        }
        v44 = v12;
        if ( !(unsigned __int8)CtapPluginInternal::IsRpSupportedByPluginAuthenticator(&v44, v50) )
          goto LABEL_57;
        hMem = 0;
        p_hMem = &hMem;
        v62 = 0;
        v63 = 1;
        v44 = 0;
        if ( *((_QWORD *)&v12 + 1) )
          _InterlockedIncrement((volatile signed __int32 *)v15);
        v44 = v12;
        CtapCborAuthenticatorInfoFromRegistry = GetCtapCborAuthenticatorInfoFromRegistry(&v44, &v62);
        wil::details::out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&p_hMem);
        if ( CtapCborAuthenticatorInfoFromRegistry < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xE18,
            (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
            (const char *)(unsigned int)CtapCborAuthenticatorInfoFromRegistry,
            lpcSubKeysa);
          v17 = hMem;
          hMem = 0;
          if ( v17 )
            LocalFree(v17);
          std::vector<unsigned short>::_Tidy(lpData);
          std::shared_ptr<CredentialInfo>::~shared_ptr<CredentialInfo>(&v47);
          std::vector<unsigned short>::_Tidy(lpName);
          std::_Tree_val<std::_Tree_simple_types<std::pair<FidoCredProvHelper::Locations::PluginAuthenticator const,PluginAuthenticatorState>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<FidoCredProvHelper::Locations::PluginAuthenticator const,PluginAuthenticatorState>,void *>>>(
            &v45,
            (__int64)&v45);
          return (unsigned int)CtapCborAuthenticatorInfoFromRegistry;
        }
        wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::reset(
          &v47,
          0);
        if ( a5 && *(_DWORD *)a5 )
        {
          v18 = hMem;
          if ( *((_DWORD *)hMem + 28) )
          {
            v19 = 0;
            while ( 2 )
            {
              v20 = *(_QWORD *)(a5 + 8);
              for ( j = 0; (unsigned int)j < *((_DWORD *)v18 + 28); j = (unsigned int)(j + 1) )
              {
                v22 = *((_QWORD *)v18 + 15);
                if ( *(_DWORD *)(v20 + 24 * v19 + 16) == *(_DWORD *)(v22 + 24 * j + 16) )
                {
                  if ( *(_QWORD *)(v20 + 24 * v19 + 8) )
                  {
                    v23 = *(_QWORD *)(v22 + 24 * j + 8);
                    if ( v23 )
                    {
                      if ( !(unsigned int)_o__wcsicmp(*(_QWORD *)(v20 + 24 * v19 + 8), v23) )
                      {
                        v6 = v48;
                        goto LABEL_42;
                      }
                      v18 = hMem;
                    }
                  }
                }
              }
              v19 = (unsigned int)(v19 + 1);
              if ( (unsigned int)v19 < *(_DWORD *)a5 )
                continue;
              break;
            }
            hMem = 0;
            if ( v18 )
              LocalFree(v18);
            v6 = v48;
LABEL_57:
            v7 = v42;
LABEL_58:
            std::vector<unsigned short>::_Tidy(lpData);
            goto LABEL_59;
          }
        }
        else
        {
LABEL_42:
          v18 = hMem;
        }
        v24 = *((_QWORD *)v18 + 3);
        v25 = *((_DWORD *)v18 + 4);
        v52 = 0;
        v53[0] = 0;
        v53[1] = 0;
        std::list<std::string>::_Alloc_sentinel_and_proxy(v53);
        std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(v54);
        v55 = 7;
        v56 = 8;
        v52 = 1065353216;
        std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::string>>,std::_Iterator_base0>>>::_Assign_grow(
          v54,
          16,
          v53[0]);
        for ( k = 0; (unsigned int)k < v25; k = (unsigned int)(k + 1) )
        {
          std::wstring::wstring(&p_hMem, *(_QWORD *)(v24 + 8 * k));
          std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::emplace<std::wstring>(
            (float *)&v52,
            (__int64)v59,
            (unsigned __int8 *)&p_hMem);
          std::wstring::_Tidy_deallocate(&p_hMem);
        }
        v28 = *v6;
        v29 = v6[1];
        while ( v28 != v29 )
        {
          v30 = (_QWORD *)std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::find(
                            &v52,
                            v58,
                            v28);
          if ( *v30 == v53[0] )
            goto LABEL_50;
          v28 += 32;
        }
        v38[0] = 0;
        HIBYTE(v38[1]) = 0;
        AuthenticatorState = CtapPluginInternal::CtapPluginGetAuthenticatorState(v51, lpName[0], v38, v26);
        if ( AuthenticatorState >= 0 )
        {
          if ( LOBYTE(v38[0]) || !HIBYTE(v38[0]) )
          {
            std::wstring::wstring(v64, lpData[0]);
            std::wstring::wstring(v65, lpName[0]);
            v33 = *(_DWORD *)v38;
            *(_DWORD *)(*(_QWORD *)std::map<FidoCredProvHelper::Locations::PluginAuthenticator,PluginAuthenticatorState>::_Try_emplace<FidoCredProvHelper::Locations::PluginAuthenticator const &,>(
                                     (__int64 *)&v45,
                                     (__int64)v60,
                                     (const struct FidoCredProvHelper::Locations::PluginAuthenticator *)v64)
                      + 96LL) = v33;
            FidoCredProvHelper::CreatedPasskeyInfo::~CreatedPasskeyInfo((FidoCredProvHelper::CreatedPasskeyInfo *)v64);
          }
        }
        else
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0xE58,
            (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
            (const char *)(unsigned int)AuthenticatorState,
            lpcSubKeysa);
        }
LABEL_50:
        std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::~_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>(&v52);
        v31 = hMem;
        hMem = 0;
        if ( v31 )
          LocalFree(v31);
        goto LABEL_57;
      }
    }
LABEL_59:
    std::shared_ptr<CredentialInfo>::~shared_ptr<CredentialInfo>(&v47);
LABEL_60:
    std::vector<unsigned short>::_Tidy(lpName);
  }
  if ( (void **)a6 != &v45 )
  {
    std::_Tree<std::_Tmap_traits<FidoCredProvHelper::Locations::PluginAuthenticator,PluginAuthenticatorState,std::less<FidoCredProvHelper::Locations::PluginAuthenticator>,std::allocator<std::pair<FidoCredProvHelper::Locations::PluginAuthenticator const,PluginAuthenticatorState>>,0>>::clear(a6);
    v34 = *(void **)a6;
    *(_QWORD *)a6 = v45;
    v45 = v34;
    v35 = *(_QWORD *)(a6 + 8);
    *(_QWORD *)(a6 + 8) = v46;
    v46 = v35;
  }
  std::_Tree_val<std::_Tree_simple_types<std::pair<FidoCredProvHelper::Locations::PluginAuthenticator const,PluginAuthenticatorState>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<FidoCredProvHelper::Locations::PluginAuthenticator const,PluginAuthenticatorState>,void *>>>(
    &v45,
    (__int64)&v45);
  return 0;
}

```

## disassembly

```asm
0x18004273c  push    rbx
0x18004273e  push    rsi
0x18004273f  push    rdi
0x180042740  push    r12
0x180042742  push    r13
0x180042744  push    r14
0x180042746  push    r15
0x180042748  sub     rsp, 1E0h
0x18004274f  mov     rax, cs:__security_cookie
0x180042756  xor     rax, rsp
0x180042759  mov     [rsp+218h+var_48], rax
0x180042761  mov     [rsp+218h+var_140], r9
0x180042769  mov     r14, r8
0x18004276c  mov     [rsp+218h+var_160], r8
0x180042774  mov     rbx, rdx
0x180042777  mov     [rsp+218h+var_1A0], rdx
0x18004277c  mov     [rsp+218h+var_138], rcx
0x180042784  mov     r13, [rsp+218h+arg_20]
0x18004278c  mov     r15, [rsp+218h+arg_28]
0x180042794  xor     esi, esi
0x180042796  mov     [rsp+218h+cSubKeys], esi
0x18004279a  mov     [rsp+218h+cbMaxSubKeyLen], esi
0x18004279e  mov     [rsp+218h+lpftLastWriteTime], rsi; lpftLastWriteTime
0x1800427a3  mov     [rsp+218h+lpcbSecurityDescriptor], rsi; lpcbSecurityDescriptor
0x1800427a8  mov     [rsp+218h+lpcbMaxValueLen], rsi; lpcbMaxValueLen
0x1800427ad  mov     [rsp+218h+lpcbMaxValueNameLen], rsi; lpcbMaxValueNameLen
0x1800427b2  mov     [rsp+218h+lpcValues], rsi; lpcValues
0x1800427b7  mov     [rsp+218h+lpcbMaxClassLen], rsi; lpcbMaxClassLen
0x1800427bc  lea     rax, [rsp+218h+cbMaxSubKeyLen]
0x1800427c1  mov     [rsp+218h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x1800427c6  lea     rax, [rsp+218h+cSubKeys]
0x1800427cb  mov     [rsp+218h+lpcSubKeys], rax; unsigned int
0x1800427d0  xor     r9d, r9d; lpReserved
0x1800427d3  xor     r8d, r8d; lpcchClass
0x1800427d6  xor     edx, edx; lpClass
0x1800427d8  mov     rcx, rbx; hKey
0x1800427db  call    cs:__imp_RegQueryInfoKeyW
0x1800427e1  test    eax, eax
0x1800427e3  jz      short loc_180042806
0x1800427e5  mov     rcx, [rsp+218h]; this
0x1800427ed  mov     r9d, eax; char *
0x1800427f0  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x1800427f7  mov     edx, 0DEEh; void *
0x1800427fc  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180042801  jmp     loc_180042DCB
0x180042806  inc     [rsp+218h+cbMaxSubKeyLen]
0x18004280a  lea     rcx, [rsp+218h+var_180]
0x180042812  call    ??0?$map@UPluginAuthenticator@Locations@FidoCredProvHelper@@UPluginAuthenticatorState@@U?$less@UPluginAuthenticator@Locations@FidoCredProvHelper@@@std@@V?$allocator@U?$pair@$$CBUPluginAuthenticator@Locations@FidoCredProvHelper@@UPluginAuthenticatorState@@@std@@@6@@std@@QEAA@XZ; std::map<FidoCredProvHelper::Locations::PluginAuthenticator,PluginAuthenticatorState>::map<FidoCredProvHelper::Locations::PluginAuthenticator,PluginAuthenticatorState>(void)
0x180042817  nop
0x180042818  mov     r12d, esi
0x18004281b  cmp     r12d, [rsp+218h+cSubKeys]
0x180042820  jnb     loc_180042D6B
0x180042826  mov     edx, [rsp+218h+cbMaxSubKeyLen]
0x18004282a  lea     rcx, [rsp+218h+lpName]
0x180042832  call    ??0?$vector@GV?$allocator@G@std@@@std@@QEAA@_KAEBV?$allocator@G@1@@Z; std::vector<ushort>::vector<ushort>(unsigned __int64,std::allocator<ushort> const &)
0x180042837  nop
0x180042838  mov     r9d, [rsp+218h+cbMaxSubKeyLen]; cchName
0x18004283d  mov     r8, [rsp+218h+lpName]; lpName
0x180042845  mov     edx, r12d; dwIndex
0x180042848  mov     rcx, rbx; hKey
0x18004284b  call    cs:__imp_RegEnumKeyW
0x180042851  test    eax, eax
0x180042853  jnz     loc_180042D56
0x180042859  xorps   xmm1, xmm1
0x18004285c  movdqu  [rsp+218h+var_170], xmm1
0x180042865  lea     rcx, [rsp+218h+var_170]
0x18004286d  call    ?put@?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>>::put(void)
0x180042872  mov     [rsp+218h+lpcSubKeys], rax; phkResult
0x180042877  mov     r9d, 20019h; samDesired
0x18004287d  xor     r8d, r8d; ulOptions
0x180042880  mov     rdx, [rsp+218h+lpName]; lpSubKey
0x180042888  mov     rcx, rbx; hKey
0x18004288b  call    cs:__imp_RegOpenKeyExW
0x180042891  test    eax, eax
0x180042893  jnz     loc_180042D48
0x180042899  mov     [rsp+218h+cbData], esi
0x1800428a0  mov     rdi, qword ptr [rsp+218h+var_170]
0x1800428a8  test    rdi, rdi
0x1800428ab  jz      short loc_1800428B2
0x1800428ad  mov     rcx, [rdi]
0x1800428b0  jmp     short loc_1800428B5
0x1800428b2  mov     rcx, rsi; hKey
0x1800428b5  lea     rax, [rsp+218h+cbData]
0x1800428bd  mov     [rsp+218h+lpcbMaxSubKeyLen], rax; lpcbData
0x1800428c2  mov     [rsp+218h+lpcSubKeys], rsi; lpData
0x1800428c7  xor     r9d, r9d; lpType
0x1800428ca  xor     r8d, r8d; lpReserved
0x1800428cd  lea     rdx, aName; "Name"
0x1800428d4  call    cs:__imp_RegQueryValueExW
0x1800428da  test    eax, eax
0x1800428dc  jnz     loc_180042D48
0x1800428e2  mov     edx, [rsp+218h+cbData]
0x1800428e9  shr     rdx, 1
0x1800428ec  lea     rcx, [rsp+218h+lpData]
0x1800428f4  call    ??0?$vector@GV?$allocator@G@std@@@std@@QEAA@_KAEBV?$allocator@G@1@@Z; std::vector<ushort>::vector<ushort>(unsigned __int64,std::allocator<ushort> const &)
0x1800428f9  nop
0x1800428fa  mov     rax, [rsp+218h+lpData]
0x180042902  test    rdi, rdi
0x180042905  jz      short loc_18004290C
0x180042907  mov     rcx, [rdi]
0x18004290a  jmp     short loc_18004290F
0x18004290c  mov     rcx, rsi; hKey
0x18004290f  lea     rdx, [rsp+218h+cbData]
0x180042917  mov     [rsp+218h+lpcbMaxSubKeyLen], rdx; lpcbData
0x18004291c  mov     [rsp+218h+lpcSubKeys], rax; int
0x180042921  xor     r9d, r9d; lpType
0x180042924  xor     r8d, r8d; lpReserved
0x180042927  lea     rdx, aName; "Name"
0x18004292e  call    cs:__imp_RegQueryValueExW
0x180042934  test    eax, eax
0x180042936  jnz     loc_180042D3A
0x18004293c  xorps   xmm0, xmm0
0x18004293f  movdqu  [rsp+218h+var_190], xmm0
0x180042948  mov     rsi, qword ptr [rsp+218h+var_170+8]
0x180042950  test    rsi, rsi
0x180042953  jz      short loc_18004295E
0x180042955  lea     rbx, [rsi+8]
0x180042959  lock inc dword ptr [rbx]
0x18004295c  jmp     short loc_180042963
0x18004295e  mov     ebx, 8
0x180042963  mov     qword ptr [rsp+218h+var_190], rdi
0x18004296b  mov     qword ptr [rsp+218h+var_190+8], rsi
0x180042973  mov     rdx, [rsp+218h+var_140]
0x18004297b  lea     rcx, [rsp+218h+var_190]
0x180042983  call    ?IsRpSupportedByPluginAuthenticator@CtapPluginInternal@@YA_NV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CtapPluginInternal::IsRpSupportedByPluginAuthenticator(wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>>,std::wstring const &)
0x180042988  test    al, al
0x18004298a  jz      loc_180042D33
0x180042990  mov     [rsp+218h+hMem], 0
0x180042999  lea     rax, [rsp+218h+hMem]
0x18004299e  mov     [rsp+218h+var_A8], rax
0x1800429a6  mov     [rsp+218h+var_A0], 0
0x1800429b2  mov     [rsp+218h+var_98], 1
0x1800429ba  xorps   xmm0, xmm0
0x1800429bd  movdqu  [rsp+218h+var_190], xmm0
0x1800429c6  test    rsi, rsi
0x1800429c9  jz      short loc_1800429CE
0x1800429cb  lock inc dword ptr [rbx]
0x1800429ce  mov     qword ptr [rsp+218h+var_190], rdi
0x1800429d6  mov     qword ptr [rsp+218h+var_190+8], rsi
0x1800429de  lea     rdx, [rsp+218h+var_A0]
0x1800429e6  lea     rcx, [rsp+218h+var_190]
0x1800429ee  call    ?GetCtapCborAuthenticatorInfoFromRegistry@@YAJV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@PEAPEAU_CTAPCBOR_AUTHENTICATOR_INFO@@@Z; GetCtapCborAuthenticatorInfoFromRegistry(wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>>,_CTAPCBOR_AUTHENTICATOR_INFO * *)
0x1800429f3  mov     ebx, eax
0x1800429f5  lea     rcx, [rsp+218h+var_A8]
0x1800429fd  call    ??1?$out_param_t@V?$unique_ptr@U_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x180042a02  test    ebx, ebx
0x180042a04  jns     short loc_180042A83
0x180042a06  mov     rcx, [rsp+218h]; this
0x180042a0e  mov     r9d, ebx; char *
0x180042a11  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x180042a18  mov     edx, 0E18h; void *
0x180042a1d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180042a22  nop
0x180042a23  mov     rcx, [rsp+218h+hMem]; hMem
0x180042a28  mov     [rsp+218h+hMem], 0
0x180042a31  test    rcx, rcx
0x180042a34  jz      short loc_180042A3D
0x180042a36  call    cs:__imp_LocalFree
0x180042a3c  nop
0x180042a3d  lea     rcx, [rsp+218h+lpData]
0x180042a45  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x180042a4a  nop
0x180042a4b  lea     rcx, [rsp+218h+var_170]
0x180042a53  call    ??1?$shared_ptr@UCredentialInfo@@@std@@QEAA@XZ; std::shared_ptr<CredentialInfo>::~shared_ptr<CredentialInfo>(void)
0x180042a58  nop
0x180042a59  lea     rcx, [rsp+218h+lpName]
0x180042a61  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x180042a66  nop
0x180042a67  lea     rdx, [rsp+218h+var_180]
0x180042a6f  lea     rcx, [rsp+218h+var_180]
0x180042a77  call    ??$_Erase_head@V?$allocator@U?$_Tree_node@U?$pair@$$CBUPluginAuthenticator@Locations@FidoCredProvHelper@@UPluginAuthenticatorState@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBUPluginAuthenticator@Locations@FidoCredProvHelper@@UPluginAuthenticatorState@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBUPluginAuthenticator@Locations@FidoCredProvHelper@@UPluginAuthenticatorState@@@std@@PEAX@std@@@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<FidoCredProvHelper::Locations::PluginAuthenticator const,PluginAuthenticatorState>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<FidoCredProvHelper::Locations::PluginAuthenticator const,PluginAuthenticatorState>,void *>>>(std::allocator<std::_Tree_node<std::pair<FidoCredProvHelper::Locations::PluginAuthenticator const,PluginAuthenticatorState>,void *>> &)
0x180042a7c  mov     eax, ebx
0x180042a7e  jmp     loc_180042DCB
0x180042a83  xor     edx, edx
0x180042a85  lea     rcx, [rsp+218h+var_170]
0x180042a8d  call    ?reset@?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::reset(HKEY__ *)
0x180042a92  test    r13, r13
0x180042a95  jz      loc_180042B33
0x180042a9b  cmp     dword ptr [r13+0], 0
0x180042aa0  jbe     loc_180042B33
0x180042aa6  mov     rcx, [rsp+218h+hMem]; hMem
0x180042aab  cmp     dword ptr [rcx+70h], 0
0x180042aaf  jbe     loc_180042B38
0x180042ab5  xor     ebx, ebx
0x180042ab7  lea     rsi, [rbx+rbx*2]
0x180042abb  mov     r14, [r13+8]
0x180042abf  xor     edi, edi
0x180042ac1  cmp     edi, [rcx+70h]
0x180042ac4  jnb     short loc_180042B04
0x180042ac6  lea     rdx, [rdi+rdi*2]
0x180042aca  mov     r8, [rcx+78h]
0x180042ace  mov     eax, [r8+rdx*8+10h]
0x180042ad3  cmp     [r14+rsi*8+10h], eax
0x180042ad8  jnz     short loc_180042B00
0x180042ada  mov     rax, [r14+rsi*8+8]
0x180042adf  test    rax, rax
0x180042ae2  jz      short loc_180042B00
0x180042ae4  mov     rdx, [r8+rdx*8+8]
0x180042ae9  test    rdx, rdx
0x180042aec  jz      short loc_180042B00
0x180042aee  mov     rcx, rax
0x180042af1  call    cs:__imp__o__wcsicmp
0x180042af7  test    eax, eax
0x180042af9  jz      short loc_180042B2B
0x180042afb  mov     rcx, [rsp+218h+hMem]
0x180042b00  inc     edi
0x180042b02  jmp     short loc_180042AC1
0x180042b04  inc     ebx
0x180042b06  cmp     ebx, [r13+0]
0x180042b0a  jb      short loc_180042AB7
0x180042b0c  xor     esi, esi
0x180042b0e  mov     [rsp+218h+hMem], rsi
0x180042b13  test    rcx, rcx
0x180042b16  jz      short loc_180042B1E
0x180042b18  call    cs:__imp_LocalFree
0x180042b1e  mov     r14, [rsp+218h+var_160]
0x180042b26  jmp     loc_180042D35
0x180042b2b  mov     r14, [rsp+218h+var_160]
0x180042b33  mov     rcx, [rsp+218h+hMem]
0x180042b38  mov     rsi, [rcx+18h]
0x180042b3c  mov     edi, [rcx+10h]
0x180042b3f  mov     [rsp+218h+var_128], 0
0x180042b4a  mov     [rsp+218h+var_120], 0
0x180042b56  mov     [rsp+218h+var_118], 0
0x180042b62  lea     rcx, [rsp+218h+var_120]
0x180042b6a  call    ?_Alloc_sentinel_and_proxy@?$list@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@std@@AEAAXXZ; std::list<std::string>::_Alloc_sentinel_and_proxy(void)
0x180042b6f  nop
0x180042b70  lea     rcx, [rsp+218h+var_110]
0x180042b78  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@XZ; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(void)
0x180042b7d  nop
0x180042b7e  mov     [rsp+218h+var_F8], 7
0x180042b8a  mov     [rsp+218h+var_F0], 8
0x180042b96  mov     [rsp+218h+var_128], 3F800000h
0x180042ba1  mov     r8, [rsp+218h+var_120]
0x180042ba9  mov     edx, 10h
0x180042bae  lea     rcx, [rsp+218h+var_110]
0x180042bb6  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::string>>,std::_Iterator_base0>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::string>>,std::_Iterator_base0>)
0x180042bbb  nop
0x180042bbc  xor     ebx, ebx
0x180042bbe  cmp     ebx, edi
0x180042bc0  jnb     short loc_180042C03
0x180042bc2  mov     rdx, [rsi+rbx*8]
0x180042bc6  lea     rcx, [rsp+218h+var_A8]
0x180042bce  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180042bd3  nop
0x180042bd4  lea     r8, [rsp+218h+var_A8]
0x180042bdc  lea     rdx, [rsp+218h+var_C8]
0x180042be4  lea     rcx, [rsp+218h+var_128]
0x180042bec  call    ??$emplace@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@_N@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::emplace<std::wstring>(std::wstring &&)
0x180042bf1  nop
0x180042bf2  lea     rcx, [rsp+218h+var_A8]
0x180042bfa  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180042bff  inc     ebx
0x180042c01  jmp     short loc_180042BBE
0x180042c03  mov     rbx, [r14]
0x180042c06  mov     rdi, [r14+8]
0x180042c0a  cmp     rbx, rdi
0x180042c0d  jz      short loc_180042C68
0x180042c0f  mov     r8, rbx
0x180042c12  lea     rdx, [rsp+218h+var_D0]
0x180042c1a  lea     rcx, [rsp+218h+var_128]
0x180042c22  call    ?find@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::find(std::wstring const &)
0x180042c27  mov     rcx, [rsp+218h+var_120]
0x180042c2f  cmp     [rax], rcx
0x180042c32  jz      short loc_180042C3A
0x180042c34  add     rbx, 20h ; ' '
0x180042c38  jmp     short loc_180042C0A
0x180042c3a  lea     rcx, [rsp+218h+var_128]
0x180042c42  call    ??1?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::~_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>(void)
0x180042c47  nop
0x180042c48  xor     esi, esi
0x180042c4a  mov     rcx, [rsp+218h+hMem]; hMem
0x180042c4f  mov     [rsp+218h+hMem], rsi
0x180042c54  test    rcx, rcx
0x180042c57  jz      loc_180042D35
0x180042c5d  call    cs:__imp_LocalFree
0x180042c63  jmp     loc_180042D35
0x180042c68  xor     esi, esi
0x180042c6a  mov     [rsp+218h+var_1B8], si
0x180042c6f  mov     byte ptr [rsp+218h+var_1B8+3], sil
0x180042c74  lea     r8, [rsp+218h+var_1B8]; unsigned __int16 *
0x180042c79  mov     rdx, [rsp+218h+lpName]; lpSubKey
0x180042c81  mov     rcx, [rsp+218h+var_138]; this
0x180042c89  call    ?CtapPluginGetAuthenticatorState@CtapPluginInternal@@YAJQEAXPEBGAEAUPluginAuthenticatorState@@@Z; CtapPluginInternal::CtapPluginGetAuthenticatorState(void * const,ushort const *,PluginAuthenticatorState &)
0x180042c8e  mov     rcx, [rsp+218h]; this
0x180042c96  test    eax, eax
0x180042c98  jns     short loc_180042CB0
0x180042c9a  mov     r9d, eax; char *
0x180042c9d  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x180042ca4  mov     edx, 0E58h; void *
0x180042ca9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180042cae  jmp     short loc_180042CBE
0x180042cb0  cmp     byte ptr [rsp+218h+var_1B8], sil
0x180042cb5  jnz     short loc_180042CD1
0x180042cb7  cmp     byte ptr [rsp+218h+var_1B8+1], sil
0x180042cbc  jz      short loc_180042CD1
0x180042cbe  lea     rcx, [rsp+218h+var_128]
0x180042cc6  call    ??1?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::~_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>(void)
0x180042ccb  nop
0x180042ccc  jmp     loc_180042C4A
  ... truncated ...
```
