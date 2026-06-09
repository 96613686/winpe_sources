# SystemSettings::Speech::DownloadVoicesHelper::GetAlternateNames(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> &)

- ea: `0x1800e1108`
- end: `0x1800e1570`
- name: `?GetAlternateNames@DownloadVoicesHelper@Speech@SystemSettings@@CAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@5@@Z`
- size: `1128`
- prototype: ``
- caller_count: `1`
- callee_count: `23`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800e1970`

## callees

- `0x18000c840`
- `0x18000cd08`
- `0x180010b9c`
- `0x180010c04`
- `0x180011bb0`
- `0x180019a20`
- `0x18001d624`
- `0x18002012c`
- `0x180022e28`
- `0x1800234f8`
- `0x180024410`
- `0x180027dd8`
- `0x180027f98`
- `0x18002b9a8`
- `0x18002bd34`
- `0x18002e0a8`
- `0x1800df188`
- `0x1800e0abc`
- `0x1800e0cc0`
- `0x1800e1108`
- `0x1800e1d2c`
- `0x1800e1d6c`
- `0x180289010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e12fc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e133e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e1388`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e13ca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e13de`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e14c7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e14db`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e12fc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e133e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e1388`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e13ca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e13de`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e14c7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e14db`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e144e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e148b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e144e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e148b`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800e121c`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800e121c`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall SystemSettings::Speech::DownloadVoicesHelper::GetAlternateNames(__int64 a1, __int64 a2)
{
  __int64 v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // rcx
  int ActivationFactory; // eax
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // r9
  unsigned int v11; // ebx
  __int64 v12; // rcx
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, _QWORD, __int64 *); // rbx
  __int64 v16; // rax
  int v17; // eax
  __int64 v18; // rcx
  __int64 v19; // rdi
  __int64 (__fastcall *v20)(__int64, HSTRING *); // rbx
  int v21; // eax
  __int64 v22; // rcx
  __int64 v23; // rdi
  __int64 (__fastcall *v24)(__int64, HSTRING *); // rbx
  int v25; // eax
  __int64 v26; // rcx
  __int64 v27; // rcx
  __int64 v28; // rax
  __int64 v29; // rcx
  __int64 v30; // rax
  __int64 v31; // rcx
  _QWORD *i; // rbx
  __int64 v33; // rdx
  HSTRING_HEADER hstringHeader; // [rsp+20h] [rbp-59h] BYREF
  __int64 v35; // [rsp+38h] [rbp-41h]
  _BYTE v36[32]; // [rsp+40h] [rbp-39h] BYREF
  _BYTE v37[32]; // [rsp+60h] [rbp-19h] BYREF
  __int64 v38; // [rsp+80h] [rbp+7h] BYREF
  HSTRING string; // [rsp+88h] [rbp+Fh] BYREF
  HSTRING v40; // [rsp+90h] [rbp+17h] BYREF
  __int64 v41; // [rsp+98h] [rbp+1Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  if ( dword_1803AF980 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_1803AF980);
    if ( dword_1803AF980 == -1 )
    {
      std::list<std::pair<std::wstring const,std::wstring>>::list<std::pair<std::wstring const,std::wstring>>(&qword_1803AF998);
      std::vector<Microsoft::WRL::ComPtr<Windows::Media::SpeechSynthesis::IVoiceInformation>>::vector<Microsoft::WRL::ComPtr<Windows::Media::SpeechSynthesis::IVoiceInformation>>(&qword_1803AF9A8);
      qword_1803AF9C0 = 7;
      qword_1803AF9C8 = 8;
      dword_1803AF990 = 1065353216;
      std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<SystemSettings::DataModel::CSingletonHelper<SInputMethodNotification &>::CCallback *>>,std::_Iterator_base0>>>::_Assign_grow(
        v4,
        16,
        qword_1803AF998);
      atexit(SystemSettings::Speech::DownloadVoicesHelper::GetAlternateNames_::_2_::_dynamic_atexit_destructor_for__s_languageTag2AlternateNamesMap__);
      Init_thread_footer(&dword_1803AF980);
    }
  }
  std::vector<std::wstring>::clear(a2);
  if ( !std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,1>>::count(
          v5,
          a1) )
  {
    v38 = 0;
    v35 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Globalization.Language",
      0x1Fu,
      0x1Eu);
    ActivationFactory = RoGetActivationFactory(v35, &GUID_9b0252ac_0c27_44f8_b792_9793fb66c63e, &v38);
    v11 = ActivationFactory;
    if ( ActivationFactory < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x67,
        (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\speech\\lib\\downloadvoiceshelper.cpp",
        (const char *)(unsigned int)ActivationFactory,
        (int)hstringHeader.Reserved.Reserved1);
      v12 = v38;
      if ( v38 )
      {
        v38 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
      }
      return v11;
    }
    v41 = 0;
    v14 = v38;
    v15 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v38 + 48LL);
    hstringHeader.Reserved.Reserved1 = (PVOID)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a1, v8, v9, v10);
    v16 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v36, &hstringHeader);
    v17 = v15(v14, *(_QWORD *)(v16 + 24), &v41);
    v11 = v17;
    if ( v17 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6A,
        (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\speech\\lib\\downloadvoiceshelper.cpp",
        (const char *)(unsigned int)v17,
        (int)hstringHeader.Reserved.Reserved1);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v41);
      v18 = v38;
      if ( v38 )
      {
        v38 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
      }
      return v11;
    }
    string = 0;
    v19 = v41;
    v20 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v41 + 56LL);
    WindowsDeleteString(0);
    string = 0;
    v21 = v20(v19, &string);
    v11 = v21;
    if ( v21 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6D,
        (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\speech\\lib\\downloadvoiceshelper.cpp",
        (const char *)(unsigned int)v21,
        (int)hstringHeader.Reserved.Reserved1);
      WindowsDeleteString(string);
      string = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v41);
      v22 = v38;
      if ( v38 )
      {
        v38 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
      }
      return v11;
    }
    v40 = 0;
    v23 = v41;
    v24 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v41 + 64LL);
    WindowsDeleteString(0);
    v40 = 0;
    v25 = v24(v23, &v40);
    v11 = v25;
    if ( v25 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x70,
        (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\speech\\lib\\downloadvoiceshelper.cpp",
        (const char *)(unsigned int)v25,
        (int)hstringHeader.Reserved.Reserved1);
      WindowsDeleteString(v40);
      v40 = 0;
      WindowsDeleteString(string);
      string = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v41);
      v26 = v38;
      if ( v38 )
      {
        v38 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
      }
      return v11;
    }
    std::wstring::wstring(v36, a1);
    std::wstring::wstring(v37, a1);
    std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,1>>::emplace<std::pair<std::wstring,std::wstring>>(
      v27,
      &hstringHeader,
      v36);
    std::pair<std::wstring const,std::wstring>::~pair<std::wstring const,std::wstring>(v36);
    hstringHeader.Reserved.Reserved1 = (PVOID)WindowsGetStringRawBuffer(string, 0);
    v28 = std::pair<std::wstring,std::wstring>::pair<std::wstring,std::wstring>(v36, a1, &hstringHeader);
    std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,1>>::emplace<std::pair<std::wstring,std::wstring>>(
      v29,
      &hstringHeader,
      v28);
    std::pair<std::wstring const,std::wstring>::~pair<std::wstring const,std::wstring>(v36);
    hstringHeader.Reserved.Reserved1 = (PVOID)WindowsGetStringRawBuffer(v40, 0);
    v30 = std::pair<std::wstring,std::wstring>::pair<std::wstring,std::wstring>(v36, a1, &hstringHeader);
    std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,1>>::emplace<std::pair<std::wstring,std::wstring>>(
      v31,
      &hstringHeader,
      v30);
    std::pair<std::wstring const,std::wstring>::~pair<std::wstring const,std::wstring>(v36);
    WindowsDeleteString(v40);
    v40 = 0;
    WindowsDeleteString(string);
    string = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v41);
    v6 = v38;
    if ( v38 )
    {
      v38 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    }
  }
  std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,1>>::equal_range(
    v6,
    &hstringHeader,
    a1);
  for ( i = hstringHeader.Reserved.Reserved1; i != *(_QWORD **)&hstringHeader.Reserved.Reserved2[8]; i = (_QWORD *)*i )
  {
    v33 = *(_QWORD *)(a2 + 8);
    if ( v33 == *(_QWORD *)(a2 + 16) )
      std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(a2, v33, i + 6);
    else
      std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring const &>(a2, i + 6);
  }
  return 0;
}

```

## disassembly

```asm
0x1800e1108  mov     [rsp-8+arg_10], rbx
0x1800e110d  push    rbp
0x1800e110e  push    rsi
0x1800e110f  push    rdi
0x1800e1110  push    r14
0x1800e1112  push    r15
0x1800e1114  lea     rbp, [rsp-37h]
0x1800e1119  sub     rsp, 0B0h
0x1800e1120  mov     rax, cs:__security_cookie
0x1800e1127  xor     rax, rsp
0x1800e112a  mov     [rbp+57h+var_30], rax
0x1800e112e  mov     rsi, rdx
0x1800e1131  mov     r14, rcx
0x1800e1134  mov     ecx, cs:_tls_index
0x1800e113a  mov     rax, gs:58h
0x1800e1143  mov     edx, 4
0x1800e1148  mov     rax, [rax+rcx*8]
0x1800e114c  mov     ecx, [rdx+rax]
0x1800e114f  cmp     cs:dword_1803AF980, ecx
0x1800e1155  jle     short loc_1800E11D1
0x1800e1157  lea     rcx, dword_1803AF980
0x1800e115e  call    _Init_thread_header
0x1800e1163  cmp     cs:dword_1803AF980, 0FFFFFFFFh
0x1800e116a  jnz     short loc_1800E11D1
0x1800e116c  lea     rcx, qword_1803AF998
0x1800e1173  call    ??0?$list@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAA@AEBV?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@1@@Z; std::list<std::pair<std::wstring const,std::wstring>>::list<std::pair<std::wstring const,std::wstring>>(std::allocator<std::pair<std::wstring const,std::wstring>> const &)
0x1800e1178  nop
0x1800e1179  lea     rcx, qword_1803AF9A8; void *
0x1800e1180  call    ??0?$vector@V?$ComPtr@UIVoiceInformation@SpeechSynthesis@Media@Windows@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIVoiceInformation@SpeechSynthesis@Media@Windows@@@WRL@Microsoft@@@std@@@std@@QEAA@XZ; std::vector<Microsoft::WRL::ComPtr<Windows::Media::SpeechSynthesis::IVoiceInformation>>::vector<Microsoft::WRL::ComPtr<Windows::Media::SpeechSynthesis::IVoiceInformation>>(void)
0x1800e1185  nop
0x1800e1186  mov     cs:qword_1803AF9C0, 7
0x1800e1191  mov     cs:qword_1803AF9C8, 8
0x1800e119c  mov     cs:dword_1803AF990, 3F800000h
0x1800e11a6  mov     r8, cs:qword_1803AF998
0x1800e11ad  mov     edx, 10h
0x1800e11b2  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@PEAVCCallback@?$CSingletonHelper@AEAUSInputMethodNotification@@@DataModel@SystemSettings@@@std@@@std@@U_Iterator_base0@2@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@PEAVCCallback@?$CSingletonHelper@AEAUSInputMethodNotification@@@DataModel@SystemSettings@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<SystemSettings::DataModel::CSingletonHelper<SInputMethodNotification &>::CCallback *>>,std::_Iterator_base0>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<SystemSettings::DataModel::CSingletonHelper<SInputMethodNotification &>::CCallback *>>,std::_Iterator_base0>)
0x1800e11b7  nop
0x1800e11b8  lea     rcx, _SystemSettings__Speech__DownloadVoicesHelper__GetAlternateNames____2____dynamic_atexit_destructor_for__s_languageTag2AlternateNamesMap__; void (__cdecl *)()
0x1800e11bf  call    atexit
0x1800e11c4  nop
0x1800e11c5  lea     rcx, dword_1803AF980
0x1800e11cc  call    _Init_thread_footer
0x1800e11d1  mov     rcx, rsi
0x1800e11d4  call    ?clear@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAXXZ; std::vector<std::wstring>::clear(void)
0x1800e11d9  mov     rdx, r14
0x1800e11dc  call    ?count@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$00@std@@@std@@QEBA_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,1>>::count(std::wstring const &)
0x1800e11e1  xor     r15d, r15d
0x1800e11e4  test    rax, rax
0x1800e11e7  jnz     loc_1800E150F
0x1800e11ed  mov     [rbp+57h+var_50], r15
0x1800e11f1  mov     [rbp+57h+var_98], r15
0x1800e11f5  lea     r9d, [r15+1Eh]; unsigned int
0x1800e11f9  lea     r8d, [r15+1Fh]; unsigned int
0x1800e11fd  lea     rdx, ?RuntimeClass_Windows_Globalization_Language@@3QBGB; "Windows.Globalization.Language"
0x1800e1204  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1800e1208  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800e120d  lea     r8, [rbp+57h+var_50]
0x1800e1211  lea     rdx, _GUID_9b0252ac_0c27_44f8_b792_9793fb66c63e
0x1800e1218  mov     rcx, [rbp+57h+var_98]
0x1800e121c  call    cs:__imp_RoGetActivationFactory
0x1800e1223  nop     dword ptr [rax+rax+00h]
0x1800e1228  mov     ebx, eax
0x1800e122a  test    eax, eax
0x1800e122c  jns     short loc_1800E1267
0x1800e122e  mov     rcx, [rbp+5Fh]; this
0x1800e1232  mov     r9d, eax; char *
0x1800e1235  lea     r8, aShellSystemset_11; "shell\\systemsettingsthreshold\\handler"...
0x1800e123c  lea     edx, [r15+67h]; void *
0x1800e1240  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e1245  nop
0x1800e1246  mov     rcx, [rbp+57h+var_50]
0x1800e124a  test    rcx, rcx
0x1800e124d  jz      short loc_1800E1260
0x1800e124f  mov     [rbp+57h+var_50], r15
0x1800e1253  mov     rax, [rcx]
0x1800e1256  mov     rax, [rax+10h]
0x1800e125a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e125f  nop
0x1800e1260  mov     eax, ebx
0x1800e1262  jmp     loc_1800E154C
0x1800e1267  mov     [rbp+57h+var_38], r15
0x1800e126b  mov     rdi, [rbp+57h+var_50]
0x1800e126f  mov     rax, [rdi]
0x1800e1272  mov     rbx, [rax+30h]
0x1800e1276  mov     rcx, r14
0x1800e1279  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800e127e  mov     qword ptr [rbp+57h+hstringHeader.Reserved], rax
0x1800e1282  lea     rdx, [rbp+57h+hstringHeader]
0x1800e1286  lea     rcx, [rbp+57h+var_90]
0x1800e128a  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800e128f  nop
0x1800e1290  lea     r8, [rbp+57h+var_38]
0x1800e1294  mov     rdx, [rax+18h]
0x1800e1298  mov     rcx, rdi
0x1800e129b  mov     rax, rbx
0x1800e129e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e12a3  mov     ebx, eax
0x1800e12a5  test    eax, eax
0x1800e12a7  jns     short loc_1800E12EB
0x1800e12a9  mov     rcx, [rbp+5Fh]; this
0x1800e12ad  mov     r9d, eax; char *
0x1800e12b0  lea     r8, aShellSystemset_11; "shell\\systemsettingsthreshold\\handler"...
0x1800e12b7  mov     edx, 6Ah ; 'j'; void *
0x1800e12bc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e12c1  nop
0x1800e12c2  lea     rcx, [rbp+57h+var_38]
0x1800e12c6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800e12cb  nop
0x1800e12cc  mov     rcx, [rbp+57h+var_50]
0x1800e12d0  test    rcx, rcx
0x1800e12d3  jz      short loc_1800E12E6
0x1800e12d5  mov     [rbp+57h+var_50], r15
0x1800e12d9  mov     rax, [rcx]
0x1800e12dc  mov     rax, [rax+10h]
0x1800e12e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e12e5  nop
0x1800e12e6  jmp     loc_1800E1260
0x1800e12eb  mov     [rbp+57h+string], r15
0x1800e12ef  mov     rdi, [rbp+57h+var_38]
0x1800e12f3  mov     rax, [rdi]
0x1800e12f6  mov     rbx, [rax+38h]
0x1800e12fa  xor     ecx, ecx; string
0x1800e12fc  call    cs:__imp_WindowsDeleteString
0x1800e1303  nop     dword ptr [rax+rax+00h]
0x1800e1308  mov     [rbp+57h+string], r15
0x1800e130c  lea     rdx, [rbp+57h+string]
0x1800e1310  mov     rcx, rdi
0x1800e1313  mov     rax, rbx
0x1800e1316  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e131b  mov     ebx, eax
0x1800e131d  test    eax, eax
0x1800e131f  jns     short loc_1800E1377
0x1800e1321  mov     rcx, [rbp+5Fh]; this
0x1800e1325  mov     r9d, eax; char *
0x1800e1328  lea     r8, aShellSystemset_11; "shell\\systemsettingsthreshold\\handler"...
0x1800e132f  mov     edx, 6Dh ; 'm'; void *
0x1800e1334  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e1339  nop
0x1800e133a  mov     rcx, [rbp+57h+string]; string
0x1800e133e  call    cs:__imp_WindowsDeleteString
0x1800e1345  nop     dword ptr [rax+rax+00h]
0x1800e134a  mov     [rbp+57h+string], r15
0x1800e134e  lea     rcx, [rbp+57h+var_38]
0x1800e1352  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800e1357  nop
0x1800e1358  mov     rcx, [rbp+57h+var_50]
0x1800e135c  test    rcx, rcx
0x1800e135f  jz      short loc_1800E1372
0x1800e1361  mov     [rbp+57h+var_50], r15
0x1800e1365  mov     rax, [rcx]
0x1800e1368  mov     rax, [rax+10h]
0x1800e136c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e1371  nop
0x1800e1372  jmp     loc_1800E1260
0x1800e1377  mov     [rbp+57h+var_40], r15
0x1800e137b  mov     rdi, [rbp+57h+var_38]
0x1800e137f  mov     rax, [rdi]
0x1800e1382  mov     rbx, [rax+40h]
0x1800e1386  xor     ecx, ecx; string
0x1800e1388  call    cs:__imp_WindowsDeleteString
0x1800e138f  nop     dword ptr [rax+rax+00h]
0x1800e1394  mov     [rbp+57h+var_40], r15
0x1800e1398  lea     rdx, [rbp+57h+var_40]
0x1800e139c  mov     rcx, rdi
0x1800e139f  mov     rax, rbx
0x1800e13a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e13a7  mov     ebx, eax
0x1800e13a9  test    eax, eax
0x1800e13ab  jns     short loc_1800E1417
0x1800e13ad  mov     rcx, [rbp+5Fh]; this
0x1800e13b1  mov     r9d, eax; char *
0x1800e13b4  lea     r8, aShellSystemset_11; "shell\\systemsettingsthreshold\\handler"...
0x1800e13bb  mov     edx, 70h ; 'p'; void *
0x1800e13c0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e13c5  nop
0x1800e13c6  mov     rcx, [rbp+57h+var_40]; string
0x1800e13ca  call    cs:__imp_WindowsDeleteString
0x1800e13d1  nop     dword ptr [rax+rax+00h]
0x1800e13d6  mov     [rbp+57h+var_40], r15
0x1800e13da  mov     rcx, [rbp+57h+string]; string
0x1800e13de  call    cs:__imp_WindowsDeleteString
0x1800e13e5  nop     dword ptr [rax+rax+00h]
0x1800e13ea  mov     [rbp+57h+string], r15
0x1800e13ee  lea     rcx, [rbp+57h+var_38]
0x1800e13f2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800e13f7  nop
0x1800e13f8  mov     rcx, [rbp+57h+var_50]
0x1800e13fc  test    rcx, rcx
0x1800e13ff  jz      short loc_1800E1412
0x1800e1401  mov     [rbp+57h+var_50], r15
0x1800e1405  mov     rax, [rcx]
0x1800e1408  mov     rax, [rax+10h]
0x1800e140c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e1411  nop
0x1800e1412  jmp     loc_1800E1260
0x1800e1417  mov     rdx, r14
0x1800e141a  lea     rcx, [rbp+57h+var_90]
0x1800e141e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800e1423  nop
0x1800e1424  mov     rdx, r14
0x1800e1427  lea     rcx, [rbp+57h+var_70]
0x1800e142b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800e1430  nop
0x1800e1431  lea     r8, [rbp+57h+var_90]
0x1800e1435  lea     rdx, [rbp+57h+hstringHeader]
0x1800e1439  call    ??$emplace@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$00@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@@1@$$QEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@1@@Z; std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,1>>::emplace<std::pair<std::wstring,std::wstring>>(std::pair<std::wstring,std::wstring> &&)
0x1800e143e  nop
0x1800e143f  lea     rcx, [rbp+57h+var_90]
0x1800e1443  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@QEAA@XZ; std::pair<std::wstring const,std::wstring>::~pair<std::wstring const,std::wstring>(void)
0x1800e1448  xor     edx, edx; length
0x1800e144a  mov     rcx, [rbp+57h+string]; string
0x1800e144e  call    cs:__imp_WindowsGetStringRawBuffer
0x1800e1455  nop     dword ptr [rax+rax+00h]
0x1800e145a  mov     qword ptr [rbp+57h+hstringHeader.Reserved], rax
0x1800e145e  lea     r8, [rbp+57h+hstringHeader]
0x1800e1462  mov     rdx, r14
0x1800e1465  lea     rcx, [rbp+57h+var_90]
0x1800e1469  call    ??$?0AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG$0A@@?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAPEBG@Z; std::pair<std::wstring,std::wstring>::pair<std::wstring,std::wstring>(std::wstring const &,ushort const * &&)
0x1800e146e  nop
0x1800e146f  mov     r8, rax
0x1800e1472  lea     rdx, [rbp+57h+hstringHeader]
0x1800e1476  call    ??$emplace@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$00@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@@1@$$QEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@1@@Z; std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,1>>::emplace<std::pair<std::wstring,std::wstring>>(std::pair<std::wstring,std::wstring> &&)
0x1800e147b  nop
0x1800e147c  lea     rcx, [rbp+57h+var_90]
0x1800e1480  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@QEAA@XZ; std::pair<std::wstring const,std::wstring>::~pair<std::wstring const,std::wstring>(void)
0x1800e1485  xor     edx, edx; length
0x1800e1487  mov     rcx, [rbp+57h+var_40]; string
0x1800e148b  call    cs:__imp_WindowsGetStringRawBuffer
0x1800e1492  nop     dword ptr [rax+rax+00h]
0x1800e1497  mov     qword ptr [rbp+57h+hstringHeader.Reserved], rax
0x1800e149b  lea     r8, [rbp+57h+hstringHeader]
0x1800e149f  mov     rdx, r14
0x1800e14a2  lea     rcx, [rbp+57h+var_90]
0x1800e14a6  call    ??$?0AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG$0A@@?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAPEBG@Z; std::pair<std::wstring,std::wstring>::pair<std::wstring,std::wstring>(std::wstring const &,ushort const * &&)
0x1800e14ab  nop
0x1800e14ac  mov     r8, rax
0x1800e14af  lea     rdx, [rbp+57h+hstringHeader]
0x1800e14b3  call    ??$emplace@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$00@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@@1@$$QEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@1@@Z; std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,1>>::emplace<std::pair<std::wstring,std::wstring>>(std::pair<std::wstring,std::wstring> &&)
0x1800e14b8  nop
0x1800e14b9  lea     rcx, [rbp+57h+var_90]
0x1800e14bd  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@QEAA@XZ; std::pair<std::wstring const,std::wstring>::~pair<std::wstring const,std::wstring>(void)
0x1800e14c2  nop
0x1800e14c3  mov     rcx, [rbp+57h+var_40]; string
0x1800e14c7  call    cs:__imp_WindowsDeleteString
0x1800e14ce  nop     dword ptr [rax+rax+00h]
0x1800e14d3  mov     [rbp+57h+var_40], r15
0x1800e14d7  mov     rcx, [rbp+57h+string]; string
0x1800e14db  call    cs:__imp_WindowsDeleteString
0x1800e14e2  nop     dword ptr [rax+rax+00h]
0x1800e14e7  mov     [rbp+57h+string], r15
0x1800e14eb  lea     rcx, [rbp+57h+var_38]
0x1800e14ef  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800e14f4  nop
0x1800e14f5  mov     rcx, [rbp+57h+var_50]
0x1800e14f9  test    rcx, rcx
0x1800e14fc  jz      short loc_1800E150F
0x1800e14fe  mov     [rbp+57h+var_50], r15
0x1800e1502  mov     rax, [rcx]
0x1800e1505  mov     rax, [rax+10h]
0x1800e1509  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e150e  nop
0x1800e150f  mov     r8, r14
0x1800e1512  lea     rdx, [rbp+57h+hstringHeader]
0x1800e1516  call    ?equal_range@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$00@std@@@std@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@@std@@V12@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,1>>::equal_range(std::wstring const &)
0x1800e151b  mov     rbx, qword ptr [rbp+57h+hstringHeader.Reserved]
0x1800e151f  cmp     rbx, qword ptr [rbp+57h+hstringHeader.Reserved+8]
0x1800e1523  jz      short loc_1800E154A
0x1800e1525  lea     r8, [rbx+30h]
0x1800e1529  mov     rdx, [rsi+8]
0x1800e152d  mov     rcx, rsi
0x1800e1530  cmp     rdx, [rsi+10h]
0x1800e1534  jz      short loc_1800E1540
0x1800e1536  mov     rdx, r8
0x1800e1539  call    ??$_Emplace_back_with_unused_capacity@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@AEBV21@@Z; std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring const &>(std::wstring const &)
0x1800e153e  jmp     short loc_1800E1545
0x1800e1540  call    ??$_Emplace_reallocate@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@AEBV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(std::wstring * const,std::wstring const &)
0x1800e1545  mov     rbx, [rbx]
0x1800e1548  jmp     short loc_1800E151F
0x1800e154a  xor     eax, eax
0x1800e154c  mov     rcx, [rbp+57h+var_30]
0x1800e1550  xor     rcx, rsp; StackCookie
0x1800e1553  call    __security_check_cookie
0x1800e1558  mov     rbx, [rsp+0D0h+arg_10]
0x1800e1560  add     rsp, 0B0h
0x1800e1567  pop     r15
0x1800e1569  pop     r14
0x1800e156b  pop     rdi
0x1800e156c  pop     rsi
0x1800e156d  pop     rbp
0x1800e156e  retn
```
