# Microsoft::Diagnostics::Utils::FileSystem::ExpandAndCreateDirectory(std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,bool,std::basic_string_view<wchar_t,std::char_traits<wchar_t>>)

- ea: `0x1800c53b4`
- end: `0x1800c5823`
- name: `?ExpandAndCreateDirectory@FileSystem@Utils@Diagnostics@Microsoft@@SAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@_N0@Z`
- size: `1135`
- prototype: `__int64 __fastcall(__int64, char, __int128 *)`
- caller_count: `17`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800c5210`
- `0x180169c48`
- `0x1801ad074`
- `0x1801b15cc`
- `0x1801c5e14`
- `0x1801c6134`
- `0x1801cd01c`
- `0x1802549f8`
- `0x1802812f0`
- `0x180295d80`
- `0x180296ad0`
- `0x18029a310`
- `0x18029f8d8`
- `0x1802a00d4`
- `0x1802cf0c0`
- `0x1802d104c`
- `0x1803163c0`

## callees

- `0x180002a28`
- `0x180004618`
- `0x1800046e0`
- `0x18001eb1c`
- `0x18002110c`
- `0x18002b7c0`
- `0x18002df00`
- `0x180064e6c`
- `0x18009c6bc`
- `0x18009c78c`
- `0x1800c53b4`
- `0x1800f9c3c`
- `0x180142fcc`
- `0x18020aac0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c54cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c54fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c568a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c56b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c54cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c54fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c568a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c56b9`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800c54be`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800c567c`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800c54be`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800c567c`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall Microsoft::Diagnostics::Utils::FileSystem::ExpandAndCreateDirectory(
        __int64 a1,
        char a2,
        __int128 *a3)
{
  __int64 v5; // rbx
  __int64 *v6; // rdi
  const WCHAR *v7; // rcx
  const char *v8; // r9
  LPCWSTR *v9; // rax
  __int64 v10; // rax
  int v11; // r8d
  int v12; // r9d
  unsigned int v13; // ebx
  unsigned __int64 i; // rbx
  LPCWSTR *v16; // r14
  LPCWSTR *v17; // rax
  const WCHAR *v18; // rcx
  const char *v19; // r9
  LPCWSTR *v20; // rax
  __int64 v21; // rax
  int v22; // r8d
  int v23; // r9d
  unsigned int LastError; // ebx
  LPCWSTR *v25; // rax
  __int64 v26; // rax
  int v27; // r8d
  int v28; // r9d
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+40h] [rbp-98h] BYREF
  __int64 v30; // [rsp+48h] [rbp-90h] BYREF
  __int128 v31; // [rsp+50h] [rbp-88h] BYREF
  __int128 v32; // [rsp+60h] [rbp-78h] BYREF
  __int64 v33; // [rsp+70h] [rbp-68h]
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+78h] [rbp-60h] BYREF
  LPCWSTR lpPathName[2]; // [rsp+90h] [rbp-48h] BYREF
  unsigned __int64 v36; // [rsp+A0h] [rbp-38h]
  unsigned __int64 v37; // [rsp+A8h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]

  v5 = 0;
  v30 = 0;
  memset(&SecurityAttributes, 0, sizeof(SecurityAttributes));
  if ( *((_QWORD *)a3 + 1) )
  {
    v31 = *a3;
    v6 = (__int64 *)Microsoft::Diagnostics::Utils::Os::CreateSecurityDecriptorFromSddl(&SecurityDescriptor);
    if ( &v30 != v6 )
    {
      wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::reset(
        &v30,
        *v6);
      *v6 = 0;
      v5 = v30;
    }
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>(&SecurityDescriptor);
    *(_QWORD *)&v32 = 24;
    *((_QWORD *)&v32 + 1) = v5;
    v33 = 0;
    *(_OWORD *)&SecurityAttributes.nLength = v32;
    *(_QWORD *)&SecurityAttributes.bInheritHandle = 0;
  }
  std::wstring::wstring(lpPathName, a1);
  Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString((LPCWSTR)lpPathName);
  v7 = (const WCHAR *)lpPathName;
  if ( a2 )
  {
    if ( v37 > 7 )
      v7 = lpPathName[0];
    if ( v7[v36 - 1] != 92 )
      std::wstring::push_back(lpPathName, 92);
    for ( i = 0; i < v36; ++i )
    {
      v16 = lpPathName;
      if ( v37 > 7 )
        v16 = (LPCWSTR *)lpPathName[0];
      if ( *((_WORD *)v16 + i) == 92 )
      {
        if ( !i )
          goto LABEL_49;
        v17 = lpPathName;
        if ( v37 > 7 )
          v17 = (LPCWSTR *)lpPathName[0];
        if ( *((_WORD *)v17 + i - 1) == 58 )
        {
LABEL_49:
          if ( (unsigned int)dword_1804543B0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1804543B0, 0x20000) )
          {
            *(_QWORD *)&v31 = i;
            v25 = lpPathName;
            if ( v37 > 7 )
              v25 = (LPCWSTR *)lpPathName[0];
            SecurityDescriptor = v25;
            v26 = _tlgWrapBinary<wchar_t,2>(&v32, *(_QWORD *)a1, *(unsigned int *)(a1 + 8));
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperArray<1>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<8>>(
              (unsigned int)&SecurityDescriptor,
              (unsigned int)byte_1803E5C81,
              v27,
              v28,
              v26,
              (__int64)&SecurityDescriptor,
              (__int64)&v31);
          }
        }
        else
        {
          *((_WORD *)v16 + i) = 0;
          v18 = (const WCHAR *)lpPathName;
          if ( v37 > 7 )
            v18 = lpPathName[0];
          if ( !CreateDirectoryW(v18, &SecurityAttributes) && GetLastError() != 183 )
          {
            if ( (unsigned int)dword_1804543B0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1804543B0, 0x20000) )
            {
              LODWORD(SecurityDescriptor) = GetLastError();
              v20 = lpPathName;
              if ( v37 > 7 )
                v20 = (LPCWSTR *)lpPathName[0];
              *(_QWORD *)&v31 = v20;
              v21 = _tlgWrapBinary<wchar_t,2>(&v32, *(_QWORD *)a1, *(unsigned int *)(a1 + 8));
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperArray<1>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(
                (unsigned int)&v31,
                (unsigned int)&word_1803E5C26,
                v22,
                v23,
                v21,
                (__int64)&v31,
                (__int64)&SecurityDescriptor);
            }
            LastError = wil::details::in1diag3::Return_GetLastError(
                          retaddr,
                          (void *)0x5C4,
                          (unsigned int)"onecore\\base\\telemetry\\utc\\include\\FileSystemUtils.h",
                          v19);
            std::wstring::_Tidy_deallocate(lpPathName);
            wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>(&v30);
            return LastError;
          }
          *((_WORD *)v16 + i) = 92;
        }
      }
    }
    goto LABEL_46;
  }
  if ( v37 > 7 )
    v7 = lpPathName[0];
  if ( CreateDirectoryW(v7, &SecurityAttributes) || GetLastError() == 183 )
  {
LABEL_46:
    std::wstring::_Tidy_deallocate(lpPathName);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>(&v30);
    return 0;
  }
  if ( (unsigned int)dword_1804543B0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1804543B0, 0x20000) )
  {
    LODWORD(SecurityDescriptor) = GetLastError();
    v9 = lpPathName;
    if ( v37 > 7 )
      v9 = (LPCWSTR *)lpPathName[0];
    *(_QWORD *)&v31 = v9;
    v10 = _tlgWrapBinary<wchar_t,2>(&v32, *(_QWORD *)a1, *(unsigned int *)(a1 + 8));
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperArray<1>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(
      (unsigned int)&v31,
      (unsigned int)word_1803E5BD2,
      v11,
      v12,
      v10,
      (__int64)&v31,
      (__int64)&SecurityDescriptor);
  }
  v13 = wil::details::in1diag3::Return_GetLastError(
          retaddr,
          (void *)0x59C,
          (unsigned int)"onecore\\base\\telemetry\\utc\\include\\FileSystemUtils.h",
          v8);
  std::wstring::_Tidy_deallocate(lpPathName);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>(&v30);
  return v13;
}

```

## disassembly

```asm
0x1800c53b4  mov     r11, rsp
0x1800c53b7  mov     [r11+10h], rbx
0x1800c53bb  mov     [r11+20h], rsi
0x1800c53bf  push    rdi
0x1800c53c0  push    r12
0x1800c53c2  push    r14
0x1800c53c4  sub     rsp, 0C0h
0x1800c53cb  mov     rax, cs:__security_cookie
0x1800c53d2  xor     rax, rsp
0x1800c53d5  mov     [rsp+0D8h+var_28], rax
0x1800c53dd  mov     r14b, dl
0x1800c53e0  mov     rsi, rcx
0x1800c53e3  xor     ebx, ebx
0x1800c53e5  mov     [rsp+0D8h+var_90], rbx
0x1800c53ea  xorps   xmm0, xmm0
0x1800c53ed  xor     eax, eax
0x1800c53ef  movups  xmmword ptr [rsp+0D8h+SecurityAttributes.nLength], xmm0
0x1800c53f4  mov     [r11-50h], rax
0x1800c53f8  cmp     [r8+8], rax
0x1800c53fc  jz      short loc_1800C5473
0x1800c53fe  movups  xmm0, xmmword ptr [r8]
0x1800c5402  movdqu  [rsp+0D8h+var_88], xmm0
0x1800c5408  lea     rdx, [rsp+0D8h+var_88]
0x1800c540d  lea     rcx, [rsp+0D8h+SecurityDescriptor]; SecurityDescriptor
0x1800c5412  call    ?CreateSecurityDecriptorFromSddl@Os@Utils@Diagnostics@Microsoft@@SA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; Microsoft::Diagnostics::Utils::Os::CreateSecurityDecriptorFromSddl(std::wstring_view)
0x1800c5417  mov     rdi, rax
0x1800c541a  lea     rax, [rsp+0D8h+var_90]
0x1800c541f  cmp     rax, rdi
0x1800c5422  jz      short loc_1800C5439
0x1800c5424  mov     rdx, [rdi]
0x1800c5427  lea     rcx, [rsp+0D8h+var_90]
0x1800c542c  call    ?reset@?$unique_storage@U?$resource_policy@PEA_WP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAAXPEA_W@Z; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::reset(wchar_t *)
0x1800c5431  mov     [rdi], rbx
0x1800c5434  mov     rbx, [rsp+0D8h+var_90]
0x1800c5439  lea     rcx, [rsp+0D8h+SecurityDescriptor]
0x1800c543e  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>(void)
0x1800c5443  mov     qword ptr [rsp+0D8h+var_78], 18h
0x1800c544c  mov     qword ptr [rsp+0D8h+var_78+8], rbx
0x1800c5451  mov     [rsp+0D8h+var_68], 0
0x1800c545a  movups  xmm0, [rsp+0D8h+var_78]
0x1800c545f  movups  xmmword ptr [rsp+0D8h+SecurityAttributes.nLength], xmm0
0x1800c5464  movsd   xmm1, [rsp+0D8h+var_68]
0x1800c546a  movsd   qword ptr [rsp+0D8h+SecurityAttributes.bInheritHandle], xmm1
0x1800c5473  mov     rdx, rsi
0x1800c5476  lea     rcx, [rsp+0D8h+lpPathName]
0x1800c547e  call    ??$?0V?$basic_zstring_view@_W@wil@@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV?$basic_zstring_view@_W@wil@@AEBV?$allocator@_W@1@@Z; std::wstring::wstring(wil::basic_zstring_view<wchar_t> const &,std::allocator<wchar_t> const &)
0x1800c5483  nop
0x1800c5484  xor     r8d, r8d
0x1800c5487  mov     dl, 1
0x1800c5489  lea     rcx, [rsp+0D8h+lpPathName]; lpSrc
0x1800c5491  call    ?ExpandEnvironmentStringsInString@String@Utils@Diagnostics@Microsoft@@SAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_NPEAX@Z; Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString(std::wstring &,bool,void *)
0x1800c5496  lea     rcx, [rsp+0D8h+lpPathName]
0x1800c549e  test    r14b, r14b
0x1800c54a1  jnz     loc_1800C55B5
0x1800c54a7  cmp     [rsp+0D8h+var_30], 7
0x1800c54b0  cmova   rcx, [rsp+0D8h+lpPathName]; lpPathName
0x1800c54b9  lea     rdx, [rsp+0D8h+SecurityAttributes]; lpSecurityAttributes
0x1800c54be  call    cs:__imp_CreateDirectoryW
0x1800c54c4  test    eax, eax
0x1800c54c6  jnz     loc_1800C5596
0x1800c54cc  call    cs:__imp_GetLastError
0x1800c54d2  cmp     eax, 0B7h
0x1800c54d7  jz      loc_1800C5596
0x1800c54dd  mov     eax, cs:dword_1804543B0
0x1800c54e3  cmp     eax, 2
0x1800c54e6  jbe     short loc_1800C555C
0x1800c54e8  mov     edx, 20000h
0x1800c54ed  lea     rcx, dword_1804543B0
0x1800c54f4  call    _tlgKeywordOn
0x1800c54f9  test    al, al
0x1800c54fb  jz      short loc_1800C555C
0x1800c54fd  call    cs:__imp_GetLastError
0x1800c5503  mov     dword ptr [rsp+0D8h+SecurityDescriptor], eax
0x1800c5507  lea     rax, [rsp+0D8h+lpPathName]
0x1800c550f  cmp     [rsp+0D8h+var_30], 7
0x1800c5518  cmova   rax, [rsp+0D8h+lpPathName]
0x1800c5521  mov     qword ptr [rsp+0D8h+var_88], rax
0x1800c5526  mov     r8d, [rsi+8]
0x1800c552a  mov     rdx, [rsi]
0x1800c552d  lea     rcx, [rsp+0D8h+var_78]
0x1800c5532  call    ??$_tlgWrapBinary@_W$01@@YA?AU?$_tlgWrapperArray@$00@@PEB_W_K@Z; _tlgWrapBinary<wchar_t,2>(wchar_t const *,unsigned __int64)
0x1800c5537  lea     rcx, [rsp+0D8h+SecurityDescriptor]
0x1800c553c  mov     [rsp+0D8h+var_A8], rcx
0x1800c5541  lea     rcx, [rsp+0D8h+var_88]
0x1800c5546  mov     [rsp+0D8h+var_B0], rcx
0x1800c554b  mov     [rsp+0D8h+var_B8], rax
0x1800c5550  lea     rdx, word_1803E5BD2
0x1800c5557  call    ??$Write@U?$_tlgWrapperArray@$00@@U?$_tlgWrapSz@_W@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperArray@$00@@AEBU?$_tlgWrapSz@_W@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperArray<1>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperArray<1> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &)
0x1800c555c  mov     rcx, [rsp+0D8h]; this
0x1800c5564  lea     r8, aOnecoreBaseTel_0; "onecore\\base\\telemetry\\utc\\include"...
0x1800c556b  mov     edx, 59Ch; void *
0x1800c5570  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800c5575  mov     ebx, eax
0x1800c5577  lea     rcx, [rsp+0D8h+lpPathName]
0x1800c557f  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800c5584  nop
0x1800c5585  lea     rcx, [rsp+0D8h+var_90]
0x1800c558a  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>(void)
0x1800c558f  mov     eax, ebx
0x1800c5591  jmp     loc_1800C57F9
0x1800c5596  lea     rcx, [rsp+0D8h+lpPathName]
0x1800c559e  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800c55a3  nop
0x1800c55a4  lea     rcx, [rsp+0D8h+var_90]
0x1800c55a9  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>(void)
0x1800c55ae  xor     eax, eax
0x1800c55b0  jmp     loc_1800C57F9
0x1800c55b5  cmp     [rsp+0D8h+var_30], 7
0x1800c55be  cmova   rcx, [rsp+0D8h+lpPathName]
0x1800c55c7  mov     r12d, 5Ch ; '\'
0x1800c55cd  mov     rax, [rsp+0D8h+var_38]
0x1800c55d5  cmp     [rcx+rax*2-2], r12w
0x1800c55db  jz      short loc_1800C55ED
0x1800c55dd  mov     edx, r12d
0x1800c55e0  lea     rcx, [rsp+0D8h+lpPathName]
0x1800c55e8  call    ?push_back@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_W@Z; std::wstring::push_back(wchar_t)
0x1800c55ed  xor     ebx, ebx
0x1800c55ef  mov     edi, 20000h
0x1800c55f4  cmp     rbx, [rsp+0D8h+var_38]
0x1800c55fc  jnb     loc_1800C57D9
0x1800c5602  lea     r14, [rsp+0D8h+lpPathName]
0x1800c560a  cmp     [rsp+0D8h+var_30], 7
0x1800c5613  cmova   r14, [rsp+0D8h+lpPathName]
0x1800c561c  cmp     [r14+rbx*2], r12w
0x1800c5621  jnz     loc_1800C57D1
0x1800c5627  test    rbx, rbx
0x1800c562a  jz      loc_1800C5759
0x1800c5630  lea     rax, [rsp+0D8h+lpPathName]
0x1800c5638  cmp     [rsp+0D8h+var_30], 7
0x1800c5641  cmova   rax, [rsp+0D8h+lpPathName]
0x1800c564a  cmp     word ptr [rax+rbx*2-2], 3Ah ; ':'
0x1800c5650  jz      loc_1800C5759
0x1800c5656  xor     eax, eax
0x1800c5658  mov     [r14+rbx*2], ax
0x1800c565d  lea     rcx, [rsp+0D8h+lpPathName]
0x1800c5665  cmp     [rsp+0D8h+var_30], 7
0x1800c566e  cmova   rcx, [rsp+0D8h+lpPathName]; lpPathName
0x1800c5677  lea     rdx, [rsp+0D8h+SecurityAttributes]; lpSecurityAttributes
0x1800c567c  call    cs:__imp_CreateDirectoryW
0x1800c5682  test    eax, eax
0x1800c5684  jnz     loc_1800C5752
0x1800c568a  call    cs:__imp_GetLastError
0x1800c5690  cmp     eax, 0B7h
0x1800c5695  jz      loc_1800C5752
0x1800c569b  mov     eax, cs:dword_1804543B0
0x1800c56a1  cmp     eax, 2
0x1800c56a4  jbe     short loc_1800C5718
0x1800c56a6  mov     rdx, rdi
0x1800c56a9  lea     rcx, dword_1804543B0
0x1800c56b0  call    _tlgKeywordOn
0x1800c56b5  test    al, al
0x1800c56b7  jz      short loc_1800C5718
0x1800c56b9  call    cs:__imp_GetLastError
0x1800c56bf  mov     dword ptr [rsp+0D8h+SecurityDescriptor], eax
0x1800c56c3  lea     rax, [rsp+0D8h+lpPathName]
0x1800c56cb  cmp     [rsp+0D8h+var_30], 7
0x1800c56d4  cmova   rax, [rsp+0D8h+lpPathName]
0x1800c56dd  mov     qword ptr [rsp+0D8h+var_88], rax
0x1800c56e2  mov     r8d, [rsi+8]
0x1800c56e6  mov     rdx, [rsi]
0x1800c56e9  lea     rcx, [rsp+0D8h+var_78]
0x1800c56ee  call    ??$_tlgWrapBinary@_W$01@@YA?AU?$_tlgWrapperArray@$00@@PEB_W_K@Z; _tlgWrapBinary<wchar_t,2>(wchar_t const *,unsigned __int64)
0x1800c56f3  lea     rcx, [rsp+0D8h+SecurityDescriptor]
0x1800c56f8  mov     [rsp+0D8h+var_A8], rcx
0x1800c56fd  lea     rcx, [rsp+0D8h+var_88]
0x1800c5702  mov     [rsp+0D8h+var_B0], rcx
0x1800c5707  mov     [rsp+0D8h+var_B8], rax
0x1800c570c  lea     rdx, word_1803E5C26
0x1800c5713  call    ??$Write@U?$_tlgWrapperArray@$00@@U?$_tlgWrapSz@_W@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperArray@$00@@AEBU?$_tlgWrapSz@_W@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperArray<1>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperArray<1> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &)
0x1800c5718  mov     rcx, [rsp+0D8h]; this
0x1800c5720  lea     r8, aOnecoreBaseTel_0; "onecore\\base\\telemetry\\utc\\include"...
0x1800c5727  mov     edx, 5C4h; void *
0x1800c572c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800c5731  mov     ebx, eax
0x1800c5733  lea     rcx, [rsp+0D8h+lpPathName]
0x1800c573b  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800c5740  nop
0x1800c5741  lea     rcx, [rsp+0D8h+var_90]
0x1800c5746  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>(void)
0x1800c574b  mov     eax, ebx
0x1800c574d  jmp     loc_1800C57F9
0x1800c5752  mov     [r14+rbx*2], r12w
0x1800c5757  jmp     short loc_1800C57D1
0x1800c5759  mov     eax, cs:dword_1804543B0
0x1800c575f  cmp     eax, 5
0x1800c5762  jbe     short loc_1800C57D1
0x1800c5764  mov     rdx, rdi
0x1800c5767  lea     rcx, dword_1804543B0
0x1800c576e  call    _tlgKeywordOn
0x1800c5773  test    al, al
0x1800c5775  jz      short loc_1800C57D1
0x1800c5777  mov     qword ptr [rsp+0D8h+var_88], rbx
0x1800c577c  lea     rax, [rsp+0D8h+lpPathName]
0x1800c5784  cmp     [rsp+0D8h+var_30], 7
0x1800c578d  cmova   rax, [rsp+0D8h+lpPathName]
0x1800c5796  mov     [rsp+0D8h+SecurityDescriptor], rax
0x1800c579b  mov     r8d, [rsi+8]
0x1800c579f  mov     rdx, [rsi]
0x1800c57a2  lea     rcx, [rsp+0D8h+var_78]
0x1800c57a7  call    ??$_tlgWrapBinary@_W$01@@YA?AU?$_tlgWrapperArray@$00@@PEB_W_K@Z; _tlgWrapBinary<wchar_t,2>(wchar_t const *,unsigned __int64)
0x1800c57ac  lea     rcx, [rsp+0D8h+var_88]
0x1800c57b1  mov     [rsp+0D8h+var_A8], rcx
0x1800c57b6  lea     rcx, [rsp+0D8h+SecurityDescriptor]
0x1800c57bb  mov     [rsp+0D8h+var_B0], rcx
0x1800c57c0  mov     [rsp+0D8h+var_B8], rax
0x1800c57c5  lea     rdx, byte_1803E5C81
0x1800c57cc  call    ??$Write@U?$_tlgWrapperArray@$00@@U?$_tlgWrapSz@_W@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperArray@$00@@AEBU?$_tlgWrapSz@_W@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperArray<1>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperArray<1> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<8> const &)
0x1800c57d1  inc     rbx
0x1800c57d4  jmp     loc_1800C55F4
0x1800c57d9  lea     rcx, [rsp+0D8h+lpPathName]
0x1800c57e1  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800c57e6  nop
0x1800c57e7  lea     rcx, [rsp+0D8h+var_90]
0x1800c57ec  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>(void)
0x1800c57f1  xor     eax, eax
0x1800c57f3  jmp     short loc_1800C57F9
0x1800c57f5  mov     eax, dword ptr [rsp+0D8h+SecurityDescriptor]
0x1800c57f9  mov     rcx, [rsp+0D8h+var_28]
0x1800c5801  xor     rcx, rsp; StackCookie
0x1800c5804  call    __security_check_cookie
0x1800c5809  lea     r11, [rsp+0D8h+var_18]
0x1800c5811  mov     rbx, [r11+28h]
0x1800c5815  mov     rsi, [r11+38h]
0x1800c5819  mov     rsp, r11
0x1800c581c  pop     r14
0x1800c581e  pop     r12
0x1800c5820  pop     rdi
0x1800c5821  retn
```
