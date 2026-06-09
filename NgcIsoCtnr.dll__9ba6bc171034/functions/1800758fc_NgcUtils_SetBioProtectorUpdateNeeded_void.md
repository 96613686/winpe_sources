# NgcUtils::SetBioProtectorUpdateNeeded(void)

- ea: `0x1800758fc`
- end: `0x180075b68`
- name: `?SetBioProtectorUpdateNeeded@NgcUtils@@YAJXZ`
- size: `620`
- prototype: `__int64 __fastcall(NgcUtils *__hidden this)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, installer_update`

## callers

- `0x180030bdc`
- `0x1800454b0`

## callees

- `0x180002654`
- `0x180007670`
- `0x180011c9c`
- `0x18001cbe8`
- `0x18006fa04`
- `0x18006fa64`
- `0x18006ff8c`
- `0x18006ffd4`
- `0x180075244`
- `0x1800756dc`
- `0x1800758fc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180075aaf`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180075aaf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180075980`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180075980`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180075a8c`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180075a8c`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180075a15`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180075a15`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall NgcUtils::SetBioProtectorUpdateNeeded(NgcUtils *this)
{
  int RedirectedWinBioAccontInfoRegPath; // ebx
  const WCHAR *v2; // rax
  LSTATUS v3; // eax
  int v4; // r8d
  int v5; // r9d
  signed int v6; // edi
  int v7; // ecx
  __int16 *v8; // rdx
  DWORD v9; // esi
  int v10; // r8d
  int v11; // r9d
  DWORD cchName; // [rsp+60h] [rbp-29h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-21h] BYREF
  DWORD cSubKeys; // [rsp+70h] [rbp-19h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+74h] [rbp-15h] BYREF
  signed int v17; // [rsp+78h] [rbp-11h] BYREF
  LPWSTR lpName[3]; // [rsp+80h] [rbp-9h] BYREF
  _OWORD v19[2]; // [rsp+98h] [rbp+Fh] BYREF

  v19[0] = 0;
  v19[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v19[0]) = 0;
  RedirectedWinBioAccontInfoRegPath = anonymous_namespace_::GetRedirectedWinBioAccontInfoRegPath(v19);
  if ( RedirectedWinBioAccontInfoRegPath < 0 )
    goto LABEL_25;
  hKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  v2 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v19);
  v3 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v2, 0, 0x20019u, &hKey);
  v6 = v3;
  if ( v3 != 2 )
  {
    if ( v3 )
    {
      v7 = g_logProvider;
      if ( *(_DWORD *)g_logProvider <= 2u )
        goto LABEL_7;
      v8 = &word_1800B3EEE;
      goto LABEL_6;
    }
    cSubKeys = 0;
    cbMaxSubKeyLen = 0;
    v6 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
    if ( v6 )
    {
      v7 = g_logProvider;
      if ( *(_DWORD *)g_logProvider <= 2u )
      {
LABEL_7:
        if ( v6 > 0 )
          v6 = (unsigned __int16)v6 | 0x80070000;
        goto LABEL_24;
      }
      v8 = (__int16 *)&byte_1800B3E97;
LABEL_6:
      cchName = v6;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        v7,
        (_DWORD)v8,
        v4,
        v5,
        (__int64)&cchName);
      goto LABEL_7;
    }
    if ( cSubKeys )
    {
      std::vector<unsigned short>::vector<unsigned short>(lpName, cbMaxSubKeyLen + 1);
      v9 = 0;
      if ( !cSubKeys )
      {
LABEL_18:
        std::vector<unsigned short>::_Tidy(lpName);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
LABEL_25:
        std::wstring::_Tidy_deallocate(v19);
        return (unsigned int)RedirectedWinBioAccontInfoRegPath;
      }
      while ( 1 )
      {
        cchName = lpName[1] - lpName[0];
        v6 = RegEnumKeyExW(hKey, v9, lpName[0], &cchName, 0, 0, 0, 0);
        if ( v6 )
          break;
        lpName[0][cchName] = 0;
        if ( !(unsigned int)_o__wcsicmp(L".DEFAULT", lpName[0])
          || (RedirectedWinBioAccontInfoRegPath = NgcUtils::SetBioProtectorRegKey((__int64)lpName[0]),
              RedirectedWinBioAccontInfoRegPath >= 0) )
        {
          if ( ++v9 < cSubKeys )
            continue;
        }
        goto LABEL_18;
      }
      if ( *(_DWORD *)g_logProvider > 2u )
      {
        v17 = v6;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          g_logProvider,
          (unsigned int)&dword_1800B3EC4,
          v10,
          v11,
          (__int64)&v17);
      }
      if ( v6 > 0 )
        v6 = (unsigned __int16)v6 | 0x80070000;
      std::vector<unsigned short>::_Tidy(lpName);
LABEL_24:
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      RedirectedWinBioAccontInfoRegPath = v6;
      goto LABEL_25;
    }
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  std::wstring::_Tidy_deallocate(v19);
  return 0;
}

```

## disassembly

```asm
0x1800758fc  push    rbp
0x1800758fe  push    rbx
0x1800758ff  push    rsi
0x180075900  push    rdi
0x180075901  push    r14
0x180075903  lea     rbp, [rsp-37h]
0x180075908  sub     rsp, 0C0h
0x18007590f  mov     rax, cs:__security_cookie
0x180075916  xor     rax, rsp
0x180075919  mov     [rbp+57h+var_28], rax
0x18007591d  xorps   xmm0, xmm0
0x180075920  movups  [rbp+57h+var_48], xmm0
0x180075924  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18007592c  movdqu  [rbp+57h+var_38], xmm1
0x180075931  xor     r14d, r14d
0x180075934  mov     word ptr [rbp+57h+var_48], r14w
0x180075939  lea     rcx, [rbp+57h+var_48]
0x18007593d  call    _anonymous_namespace___GetRedirectedWinBioAccontInfoRegPath
0x180075942  mov     ebx, eax
0x180075944  test    eax, eax
0x180075946  js      loc_180075B2C
0x18007594c  mov     [rbp+57h+hKey], r14
0x180075950  xor     edx, edx
0x180075952  lea     rcx, [rbp+57h+hKey]
0x180075956  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18007595b  lea     rcx, [rbp+57h+var_48]
0x18007595f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180075964  mov     rdx, rax; lpSubKey
0x180075967  lea     rax, [rbp+57h+hKey]
0x18007596b  mov     [rsp+0E0h+phkResult], rax; phkResult
0x180075970  mov     r9d, 20019h; samDesired
0x180075976  xor     r8d, r8d; ulOptions
0x180075979  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180075980  call    cs:__imp_RegOpenKeyExW
0x180075986  mov     edi, eax
0x180075988  cmp     eax, 2
0x18007598b  jz      loc_180075B39
0x180075991  test    eax, eax
0x180075993  jz      short loc_1800759D1
0x180075995  mov     rcx, cs:g_logProvider
0x18007599c  mov     edx, [rcx]
0x18007599e  cmp     edx, 2
0x1800759a1  jbe     short loc_1800759BB
0x1800759a3  lea     rdx, word_1800B3EEE
0x1800759aa  lea     rax, [rbp+57h+cchName]
0x1800759ae  mov     [rsp+0E0h+phkResult], rax
0x1800759b3  mov     [rbp+57h+cchName], edi
0x1800759b6  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800759bb  test    edi, edi
0x1800759bd  jle     loc_180075B21
0x1800759c3  movzx   edi, di
0x1800759c6  or      edi, 80070000h
0x1800759cc  jmp     loc_180075B21
0x1800759d1  mov     [rbp+57h+cSubKeys], r14d
0x1800759d5  mov     [rbp+57h+cbMaxSubKeyLen], r14d
0x1800759d9  mov     [rsp+0E0h+lpftLastWriteTime], r14; lpftLastWriteTime
0x1800759de  mov     [rsp+0E0h+lpcbSecurityDescriptor], r14; lpcbSecurityDescriptor
0x1800759e3  mov     [rsp+0E0h+lpcbMaxValueLen], r14; lpcbMaxValueLen
0x1800759e8  mov     [rsp+0E0h+lpcbMaxValueNameLen], r14; lpcbMaxValueNameLen
0x1800759ed  mov     [rsp+0E0h+lpcValues], r14; lpcValues
0x1800759f2  mov     [rsp+0E0h+lpcbMaxClassLen], r14; lpcbMaxClassLen
0x1800759f7  lea     rax, [rbp+57h+cbMaxSubKeyLen]
0x1800759fb  mov     [rsp+0E0h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x180075a00  lea     rax, [rbp+57h+cSubKeys]
0x180075a04  mov     [rsp+0E0h+phkResult], rax; lpcSubKeys
0x180075a09  xor     r9d, r9d; lpReserved
0x180075a0c  xor     r8d, r8d; lpcchClass
0x180075a0f  xor     edx, edx; lpClass
0x180075a11  mov     rcx, [rbp+57h+hKey]; hKey
0x180075a15  call    cs:__imp_RegQueryInfoKeyW
0x180075a1b  mov     edi, eax
0x180075a1d  test    eax, eax
0x180075a1f  jz      short loc_180075A3B
0x180075a21  mov     rcx, cs:g_logProvider
0x180075a28  mov     edx, [rcx]
0x180075a2a  cmp     edx, 2
0x180075a2d  jbe     short loc_1800759BB
0x180075a2f  lea     rdx, byte_1800B3E97
0x180075a36  jmp     loc_1800759AA
0x180075a3b  cmp     [rbp+57h+cSubKeys], r14d
0x180075a3f  jz      loc_180075B39
0x180075a45  mov     edx, [rbp+57h+cbMaxSubKeyLen]
0x180075a48  inc     edx
0x180075a4a  lea     rcx, [rbp+57h+lpName]
0x180075a4e  call    ??0?$vector@GV?$allocator@G@std@@@std@@QEAA@_KAEBV?$allocator@G@1@@Z; std::vector<ushort>::vector<ushort>(unsigned __int64,std::allocator<ushort> const &)
0x180075a53  nop
0x180075a54  mov     esi, r14d
0x180075a57  cmp     [rbp+57h+cSubKeys], r14d
0x180075a5b  jbe     short loc_180075ACF
0x180075a5d  mov     r8, [rbp+57h+lpName]; lpName
0x180075a61  mov     rax, [rbp+57h+var_58]
0x180075a65  sub     rax, r8
0x180075a68  sar     rax, 1
0x180075a6b  mov     [rbp+57h+cchName], eax
0x180075a6e  mov     [rsp+0E0h+lpcValues], r14; lpftLastWriteTime
0x180075a73  mov     [rsp+0E0h+lpcbMaxClassLen], r14; lpcchClass
0x180075a78  mov     [rsp+0E0h+lpcbMaxSubKeyLen], r14; lpClass
0x180075a7d  mov     [rsp+0E0h+phkResult], r14; lpReserved
0x180075a82  lea     r9, [rbp+57h+cchName]; lpcchName
0x180075a86  mov     edx, esi; dwIndex
0x180075a88  mov     rcx, [rbp+57h+hKey]; hKey
0x180075a8c  call    cs:__imp_RegEnumKeyExW
0x180075a92  mov     edi, eax
0x180075a94  test    eax, eax
0x180075a96  jnz     short loc_180075AE4
0x180075a98  mov     edx, [rbp+57h+cchName]
0x180075a9b  mov     rax, [rbp+57h+lpName]
0x180075a9f  mov     [rax+rdx*2], r14w
0x180075aa4  mov     rdx, [rbp+57h+lpName]
0x180075aa8  lea     rcx, aDefault; ".DEFAULT"
0x180075aaf  call    cs:__imp__o__wcsicmp
0x180075ab5  test    eax, eax
0x180075ab7  jz      short loc_180075AC8
0x180075ab9  mov     rcx, [rbp+57h+lpName]
0x180075abd  call    NgcUtils__SetBioProtectorRegKey
0x180075ac2  mov     ebx, eax
0x180075ac4  test    eax, eax
0x180075ac6  js      short loc_180075ACF
0x180075ac8  inc     esi
0x180075aca  cmp     esi, [rbp+57h+cSubKeys]
0x180075acd  jb      short loc_180075A5D
0x180075acf  lea     rcx, [rbp+57h+lpName]
0x180075ad3  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x180075ad8  nop
0x180075ad9  lea     rcx, [rbp+57h+hKey]
0x180075add  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180075ae2  jmp     short loc_180075B2C
0x180075ae4  mov     rcx, cs:g_logProvider
0x180075aeb  mov     eax, [rcx]
0x180075aed  cmp     eax, 2
0x180075af0  jbe     short loc_180075B0A
0x180075af2  mov     [rbp+57h+var_68], edi
0x180075af5  lea     rax, [rbp+57h+var_68]
0x180075af9  mov     [rsp+0E0h+phkResult], rax
0x180075afe  lea     rdx, dword_1800B3EC4
0x180075b05  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180075b0a  test    edi, edi
0x180075b0c  jle     short loc_180075B17
0x180075b0e  movzx   edi, di
0x180075b11  or      edi, 80070000h
0x180075b17  lea     rcx, [rbp+57h+lpName]
0x180075b1b  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x180075b20  nop
0x180075b21  lea     rcx, [rbp+57h+hKey]
0x180075b25  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180075b2a  mov     ebx, edi
0x180075b2c  lea     rcx, [rbp+57h+var_48]
0x180075b30  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180075b35  mov     eax, ebx
0x180075b37  jmp     short loc_180075B4E
0x180075b39  lea     rcx, [rbp+57h+hKey]
0x180075b3d  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180075b42  nop
0x180075b43  lea     rcx, [rbp+57h+var_48]
0x180075b47  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180075b4c  xor     eax, eax
0x180075b4e  mov     rcx, [rbp+57h+var_28]
0x180075b52  xor     rcx, rsp; StackCookie
0x180075b55  call    __security_check_cookie
0x180075b5a  add     rsp, 0C0h
0x180075b61  pop     r14
0x180075b63  pop     rdi
0x180075b64  pop     rsi
0x180075b65  pop     rbx
0x180075b66  pop     rbp
0x180075b67  retn
```
