# NgcUtils::SetBioProtectorRegKey

- ea: `0x1800756dc`
- end: `0x1800758f6`
- name: `NgcUtils::SetBioProtectorRegKey`
- size: `538`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, installer_update`

## callers

- `0x1800758fc`

## callees

- `0x1800019bc`
- `0x180002654`
- `0x180003e98`
- `0x180007670`
- `0x180011c9c`
- `0x18001cbe8`
- `0x18001cee4`
- `0x180034fd0`
- `0x18006fa64`
- `0x18006ffd4`
- `0x180075244`
- `0x1800756dc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180075776`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180075776`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800757ff`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800757ff`

## string_xrefs

- `0x1800757f4`: `ProtectorUpdateNeeded`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall NgcUtils::SetBioProtectorRegKey(__int64 a1)
{
  int RedirectedWinBioAccontInfoRegPath; // edi
  const WCHAR *v3; // rax
  LSTATUS v4; // eax
  int v5; // r8d
  int v6; // r9d
  int v7; // ebx
  int v8; // ecx
  __int16 *v9; // rdx
  int v10; // r8d
  __int64 v11; // r9
  int *v12; // rax
  void *v13; // rdx
  int v14; // ecx
  int *v16; // [rsp+30h] [rbp-29h]
  int v17; // [rsp+40h] [rbp-19h] BYREF
  BYTE Data[8]; // [rsp+48h] [rbp-11h] BYREF
  int v19; // [rsp+50h] [rbp-9h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-1h] BYREF
  __int64 v21; // [rsp+60h] [rbp+7h] BYREF
  _OWORD v22[2]; // [rsp+68h] [rbp+Fh] BYREF

  *(_DWORD *)Data = 1;
  v22[0] = 0;
  v22[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v22[0]) = 0;
  RedirectedWinBioAccontInfoRegPath = anonymous_namespace_::GetRedirectedWinBioAccontInfoRegPath(v22);
  if ( RedirectedWinBioAccontInfoRegPath < 0 )
    goto LABEL_22;
  std::wstring::append(v22, a1);
  hKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  v3 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v22);
  v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v3, 0, 0x20006u, &hKey);
  v7 = v4;
  if ( v4 )
  {
    if ( v4 == 2 )
    {
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      RedirectedWinBioAccontInfoRegPath = 0;
      goto LABEL_22;
    }
    v8 = g_logProvider;
    if ( *(_DWORD *)g_logProvider <= 2u )
      goto LABEL_8;
    v9 = (__int16 *)&dword_1800B3FDC;
    goto LABEL_7;
  }
  v7 = RegSetValueExW(hKey, L"ProtectorUpdateNeeded", 0, 4u, Data, 4u);
  if ( !v7 )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EssFprPeripherals>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_EssFprPeripherals>::GetImpl'::`2'::impl) )
    {
      if ( *(_DWORD *)g_logProvider <= 5u
        || !(unsigned __int8)tlgKeywordOn(g_logProvider, 0x400000000000LL, g_logProvider, v11) )
      {
        goto LABEL_21;
      }
      v17 = *(_DWORD *)Data;
      v19 = RedirectedWinBioAccontInfoRegPath;
      v16 = &v17;
      v12 = &v19;
      v13 = &unk_1800B3F98;
      v14 = v10;
    }
    else
    {
      v14 = g_logProvider;
      if ( *(_DWORD *)g_logProvider <= 4u )
      {
LABEL_21:
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        goto LABEL_22;
      }
      v19 = *(_DWORD *)Data;
      v17 = RedirectedWinBioAccontInfoRegPath;
      v16 = &v19;
      v12 = &v17;
      v13 = &unk_1800B3F18;
    }
    v21 = a1;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
      v14,
      (_DWORD)v13,
      v10,
      v11,
      (__int64)v12,
      (__int64)&v21,
      (__int64)v16);
    goto LABEL_21;
  }
  v8 = g_logProvider;
  if ( *(_DWORD *)g_logProvider <= 2u )
    goto LABEL_8;
  v9 = word_1800B3F5A;
LABEL_7:
  v17 = v7;
  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
    v8,
    (_DWORD)v9,
    v5,
    v6,
    (__int64)&v17);
LABEL_8:
  if ( v7 > 0 )
    v7 = (unsigned __int16)v7 | 0x80070000;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  RedirectedWinBioAccontInfoRegPath = v7;
LABEL_22:
  std::wstring::_Tidy_deallocate(v22);
  return (unsigned int)RedirectedWinBioAccontInfoRegPath;
}

```

## disassembly

```asm
0x1800756dc  push    rbp
0x1800756de  push    rbx
0x1800756df  push    rsi
0x1800756e0  push    rdi
0x1800756e1  lea     rbp, [rsp-3Fh]
0x1800756e6  sub     rsp, 98h
0x1800756ed  mov     rax, cs:__security_cookie
0x1800756f4  xor     rax, rsp
0x1800756f7  mov     [rbp+57h+var_28], rax
0x1800756fb  mov     rsi, rcx
0x1800756fe  mov     dword ptr [rbp+57h+Data], 1
0x180075705  xorps   xmm0, xmm0
0x180075708  movups  [rbp+57h+var_48], xmm0
0x18007570c  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180075714  movdqu  [rbp+57h+var_38], xmm1
0x180075719  xor     eax, eax
0x18007571b  mov     word ptr [rbp+57h+var_48], ax
0x18007571f  lea     rcx, [rbp+57h+var_48]
0x180075723  call    _anonymous_namespace___GetRedirectedWinBioAccontInfoRegPath
0x180075728  mov     edi, eax
0x18007572a  test    eax, eax
0x18007572c  js      loc_1800758D3
0x180075732  mov     rdx, rsi
0x180075735  lea     rcx, [rbp+57h+var_48]
0x180075739  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18007573e  mov     [rbp+57h+hKey], 0
0x180075746  xor     edx, edx
0x180075748  lea     rcx, [rbp+57h+hKey]
0x18007574c  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180075751  lea     rcx, [rbp+57h+var_48]
0x180075755  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007575a  mov     rdx, rax; lpSubKey
0x18007575d  lea     rax, [rbp+57h+hKey]
0x180075761  mov     [rsp+0B0h+phkResult], rax; phkResult
0x180075766  mov     r9d, 20006h; samDesired
0x18007576c  xor     r8d, r8d; ulOptions
0x18007576f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180075776  call    cs:__imp_RegOpenKeyExW
0x18007577c  mov     ebx, eax
0x18007577e  test    eax, eax
0x180075780  jz      short loc_1800757DA
0x180075782  cmp     eax, 2
0x180075785  jnz     short loc_180075797
0x180075787  lea     rcx, [rbp+57h+hKey]
0x18007578b  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180075790  xor     edi, edi
0x180075792  jmp     loc_1800758D3
0x180075797  mov     rcx, cs:g_logProvider
0x18007579e  mov     eax, [rcx]
0x1800757a0  cmp     eax, 2
0x1800757a3  jbe     short loc_1800757BD
0x1800757a5  lea     rdx, dword_1800B3FDC
0x1800757ac  lea     rax, [rbp+57h+var_70]
0x1800757b0  mov     [rsp+0B0h+phkResult], rax
0x1800757b5  mov     [rbp+57h+var_70], ebx
0x1800757b8  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800757bd  test    ebx, ebx
0x1800757bf  jle     short loc_1800757CA
0x1800757c1  movzx   ebx, bx
0x1800757c4  or      ebx, 80070000h
0x1800757ca  lea     rcx, [rbp+57h+hKey]
0x1800757ce  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800757d3  mov     edi, ebx
0x1800757d5  jmp     loc_1800758D3
0x1800757da  mov     [rsp+0B0h+cbData], 4; cbData
0x1800757e2  lea     rax, [rbp+57h+Data]
0x1800757e6  mov     [rsp+0B0h+phkResult], rax; lpData
0x1800757eb  mov     r9d, 4; dwType
0x1800757f1  xor     r8d, r8d; Reserved
0x1800757f4  lea     rdx, ValueName; "ProtectorUpdateNeeded"
0x1800757fb  mov     rcx, [rbp+57h+hKey]; hKey
0x1800757ff  call    cs:__imp_RegSetValueExW
0x180075805  mov     ebx, eax
0x180075807  test    eax, eax
0x180075809  jz      short loc_180075822
0x18007580b  mov     rcx, cs:g_logProvider
0x180075812  mov     edx, [rcx]
0x180075814  cmp     edx, 2
0x180075817  jbe     short loc_1800757BD
0x180075819  lea     rdx, word_1800B3F5A
0x180075820  jmp     short loc_1800757AC
0x180075822  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EssFprPeripherals@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EssFprPeripherals@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EssFprPeripherals> `wil::Feature<__WilFeatureTraits_Feature_EssFprPeripherals>::GetImpl(void)'::`2'::impl
0x180075829  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_EssFprPeripherals@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EssFprPeripherals>::__private_IsEnabled(void)
0x18007582e  test    al, al
0x180075830  jz      short loc_180075886
0x180075832  mov     r8, cs:g_logProvider
0x180075839  mov     eax, [r8]
0x18007583c  cmp     eax, 5
0x18007583f  jbe     loc_1800758C9
0x180075845  mov     rdx, 400000000000h
0x18007584f  mov     rcx, r8
0x180075852  call    _tlgKeywordOn
0x180075857  test    al, al
0x180075859  jz      short loc_1800758C9
0x18007585b  mov     eax, dword ptr [rbp+57h+Data]
0x18007585e  mov     [rbp+57h+var_70], eax
0x180075861  mov     [rbp+57h+var_60], edi
0x180075864  lea     rax, [rbp+57h+var_70]
0x180075868  mov     [rsp+0B0h+var_80], rax
0x18007586d  lea     rax, [rbp+57h+var_50]
0x180075871  mov     qword ptr [rsp+0B0h+cbData], rax
0x180075876  lea     rax, [rbp+57h+var_60]
0x18007587a  lea     rdx, unk_1800B3F98
0x180075881  mov     rcx, r8
0x180075884  jmp     short loc_1800758BA
0x180075886  mov     rcx, cs:g_logProvider
0x18007588d  mov     eax, [rcx]
0x18007588f  cmp     eax, 4
0x180075892  jbe     short loc_1800758C9
0x180075894  mov     eax, dword ptr [rbp+57h+Data]
0x180075897  mov     [rbp+57h+var_60], eax
0x18007589a  mov     [rbp+57h+var_70], edi
0x18007589d  lea     rax, [rbp+57h+var_60]
0x1800758a1  mov     [rsp+0B0h+var_80], rax
0x1800758a6  lea     rax, [rbp+57h+var_50]
0x1800758aa  mov     qword ptr [rsp+0B0h+cbData], rax
0x1800758af  lea     rax, [rbp+57h+var_70]
0x1800758b3  lea     rdx, unk_1800B3F18
0x1800758ba  mov     [rsp+0B0h+phkResult], rax
0x1800758bf  mov     [rbp+57h+var_50], rsi
0x1800758c3  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x1800758c8  nop
0x1800758c9  lea     rcx, [rbp+57h+hKey]
0x1800758cd  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800758d2  nop
0x1800758d3  lea     rcx, [rbp+57h+var_48]
0x1800758d7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800758dc  mov     eax, edi
0x1800758de  mov     rcx, [rbp+57h+var_28]
0x1800758e2  xor     rcx, rsp; StackCookie
0x1800758e5  call    __security_check_cookie
0x1800758ea  add     rsp, 98h
0x1800758f1  pop     rdi
0x1800758f2  pop     rsi
0x1800758f3  pop     rbx
0x1800758f4  pop     rbp
0x1800758f5  retn
```
