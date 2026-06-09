# SyncLanguageDataFromCloud

- ea: `0x180020010`
- end: `0x1800202e8`
- name: `SyncLanguageDataFromCloud`
- size: `728`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, installer_update`

## callers

- `0x180021bd0`

## callees

- `0x180002380`
- `0x1800036f8`
- `0x18000e794`
- `0x18000f35c`
- `0x1800105ac`
- `0x180011044`
- `0x180011b4c`
- `0x180011ffc`
- `0x1800161bc`
- `0x180016208`
- `0x180016250`
- `0x180018bac`
- `0x180019bbc`
- `0x180019f30`
- `0x18001d3ac`
- `0x18001d564`
- `0x180020010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18002013b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18002013b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180020122`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800201c2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180020122`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800201c2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x18002015f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x18002015f`
- `api-ms-win-core-localization-private-l1-1-0!NlsUpdateLocale` at `0x18002023e`
- `api-ms-win-core-localization-private-l1-1-0!NlsUpdateLocale` at `0x18002023e`
- `api-ms-win-core-localization-l1-2-3!SetUserGeoName` at `0x1800201ef`
- `api-ms-win-core-localization-l1-2-3!SetUserGeoName` at `0x1800201ef`
- `WinLangdb!SetUserLanguagesCore` at `0x180020181`
- `WinLangdb!SetUserLanguagesCore` at `0x180020181`
- `ext-ms-win-ntuser-message-l1-1-1!SendNotifyMessageW` at `0x180020286`
- `ext-ms-win-ntuser-message-l1-1-1!SendNotifyMessageW` at `0x180020286`

## string_xrefs

- `0x1800200c5`: `onecoreuap\base\globalization\coreglobconfig\src\coreglobconfig.cpp`
- `0x1800201a3`: `onecoreuap\base\globalization\coreglobconfig\src\coreglobconfig.cpp`
- `0x18002020a`: `onecoreuap\base\globalization\coreglobconfig\src\coreglobconfig.cpp`
- `0x180020259`: `onecoreuap\base\globalization\coreglobconfig\src\coreglobconfig.cpp`

## pseudocode

```c
__int64 SyncLanguageDataFromCloud()
{
  UINT32 v0; // edi
  const WCHAR *v2; // rbx
  HRESULT v3; // eax
  unsigned int v4; // r8d
  const char *v5; // rbx
  unsigned int v6; // eax
  const char *v7; // rbx
  unsigned int v8; // eax
  const char *v9; // rbx
  unsigned int updated; // eax
  HSTRING string; // [rsp+40h] [rbp-218h] BYREF
  _BYTE v12[40]; // [rsp+48h] [rbp-210h] BYREF
  _BYTE v13[16]; // [rsp+70h] [rbp-1E8h] BYREF
  UINT32 length[2]; // [rsp+80h] [rbp-1D8h]
  _BYTE v15[16]; // [rsp+90h] [rbp-1C8h] BYREF
  unsigned __int64 v16; // [rsp+A0h] [rbp-1B8h]
  _BYTE v17[16]; // [rsp+B0h] [rbp-1A8h] BYREF
  unsigned __int64 v18; // [rsp+C0h] [rbp-198h]
  char v19; // [rsp+E0h] [rbp-178h]
  _QWORD v20[42]; // [rsp+F0h] [rbp-168h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+258h] [rbp+0h]

  wil::ActivityBase<CoreGlobConfigTraceLogging,1,35184372088832,5,16779264,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CoreGlobConfigTraceLogging,1,35184372088832,5,16779264,_TlgReflectorTag_Param0IsProviderType>(
    v20,
    "SyncLanguageDataFromCloudActivity");
  v20[0] = &CoreGlobConfigTraceLogging::SyncLanguageDataFromCloudActivity::`vftable';
  CoreGlobConfigTraceLogging::SyncLanguageDataFromCloudActivity::StartActivity((CoreGlobConfigTraceLogging::SyncLanguageDataFromCloudActivity *)v20);
  wil::cloud_store::cloud_store(v12);
  wil::cloud_store::load<Windows::Data::Globalization::Culture::CultureSettings>(v12, v13, 0);
  if ( !v19 )
  {
    v0 = length[0];
    if ( *(_QWORD *)length > 0xAA0u )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x593,
        (unsigned int)"onecoreuap\\base\\globalization\\coreglobconfig\\src\\coreglobconfig.cpp",
        (const char *)0x80070057LL,
        (int)"len: %zu",
        *(const char **)length);
      wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>::~cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>((wil::cloud_store::validated_data_reference *)v13);
      wil::cloud_store::~cloud_store((wil::cloud_store *)v12);
      CoreGlobConfigTraceLogging::SyncLanguageDataFromCloudActivity::~SyncLanguageDataFromCloudActivity((CoreGlobConfigTraceLogging::SyncLanguageDataFromCloudActivity *)v20);
      return 2147942487LL;
    }
    if ( *(_QWORD *)length > 1u )
    {
      v2 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v13);
      WindowsDeleteString(0);
      string = 0;
      v3 = WindowsCreateString(v2, v0, &string);
      if ( v3 < 0 )
        wil::details::in1diag3::_Log_Hr(retaddr, (void *)0x59C, v4, (const char *)(unsigned int)v3, 0);
      if ( WindowsGetStringLen(string) > 1 )
      {
        v5 = (const char *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v13);
        v6 = SetUserLanguagesCore(59, string);
        wil::details::in1diag3::Log_IfFailedMsg(
          retaddr,
          (void *)0x5A1,
          (unsigned int)"onecoreuap\\base\\globalization\\coreglobconfig\\src\\coreglobconfig.cpp",
          (const char *)v6,
          (int)"%ls",
          v5);
      }
      WindowsDeleteString(string);
    }
    if ( v16 > 1 )
    {
      v7 = (const char *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v15);
      v8 = SetUserGeoName(v7);
      wil::details::in1diag3::Log_IfWin32BoolFalseMsg(
        retaddr,
        (void *)0x5AA,
        (unsigned int)"onecoreuap\\base\\globalization\\coreglobconfig\\src\\coreglobconfig.cpp",
        (const char *)v8,
        (int)"%ls",
        v7);
    }
    if ( v18 > 1 )
    {
      v9 = (const char *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v17);
      updated = NlsUpdateLocale(v9, 1);
      wil::details::in1diag3::Log_IfWin32ErrorMsg(
        retaddr,
        (void *)0x5B4,
        (unsigned int)"onecoreuap\\base\\globalization\\coreglobconfig\\src\\coreglobconfig.cpp",
        (const char *)updated,
        (unsigned int)"%ls",
        v9);
    }
    if ( (unsigned __int8)IsSendNotifyMessageWPresent() )
      SendNotifyMessageW(HWND_BROADCAST, 0x1Au, 0, (LPARAM)L"intl");
  }
  wil::ActivityBase<CoreGlobConfigTraceLogging,1,35184372088832,5,16779264,_TlgReflectorTag_Param0IsProviderType>::Stop(
    v20,
    0);
  wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>::~cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>((wil::cloud_store::validated_data_reference *)v13);
  wil::cloud_store::~cloud_store((wil::cloud_store *)v12);
  CoreGlobConfigTraceLogging::SyncLanguageDataFromCloudActivity::~SyncLanguageDataFromCloudActivity((CoreGlobConfigTraceLogging::SyncLanguageDataFromCloudActivity *)v20);
  return 0;
}

```

## disassembly

```asm
0x180020010  mov     [rsp+arg_0], rbx
0x180020015  push    rdi
0x180020016  sub     rsp, 250h
0x18002001d  mov     rax, cs:__security_cookie
0x180020024  xor     rax, rsp
0x180020027  mov     [rsp+258h+var_18], rax
0x18002002f  lea     rdx, aSynclanguageda_5; "SyncLanguageDataFromCloudActivity"
0x180020036  lea     rcx, [rsp+258h+var_168]
0x18002003e  call    ??0?$ActivityBase@VCoreGlobConfigTraceLogging@@$00$0CAAAAAAAAAAA@$04$0BAAAIAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<CoreGlobConfigTraceLogging,1,35184372088832,5,16779264,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CoreGlobConfigTraceLogging,1,35184372088832,5,16779264,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180020043  lea     rax, ??_7SyncLanguageDataFromCloudActivity@CoreGlobConfigTraceLogging@@6B@; const CoreGlobConfigTraceLogging::SyncLanguageDataFromCloudActivity::`vftable'
0x18002004a  mov     [rsp+258h+var_168], rax
0x180020052  lea     rcx, [rsp+258h+var_168]; this
0x18002005a  call    ?StartActivity@SyncLanguageDataFromCloudActivity@CoreGlobConfigTraceLogging@@QEAAXXZ; CoreGlobConfigTraceLogging::SyncLanguageDataFromCloudActivity::StartActivity(void)
0x18002005f  nop
0x180020060  mov     [rsp+258h+var_238], 0; int
0x180020068  lea     rcx, [rsp+258h+var_210]
0x18002006d  call    ??0cloud_store@wil@@QEAA@W4PartitionKind@Cloud@Storage@Internal@Windows@@PEBG1W4CloudStoreOptions@3456@II@Z; wil::cloud_store::cloud_store(Windows::Internal::Storage::Cloud::PartitionKind,ushort const *,ushort const *,Windows::Internal::Storage::Cloud::CloudStoreOptions,uint,uint)
0x180020072  nop
0x180020073  xor     r8d, r8d
0x180020076  lea     rdx, [rsp+258h+var_1E8]
0x18002007b  lea     rcx, [rsp+258h+var_210]
0x180020080  call    ??$load@UCultureSettings@Culture@Globalization@Data@Windows@@@cloud_store@wil@@QEAA?AV?$cloud_store_data@UCultureSettings@Culture@Globalization@Data@Windows@@@1@W4cloud_store_load_options@1@PEBD@Z; wil::cloud_store::load<Windows::Data::Globalization::Culture::CultureSettings>(wil::cloud_store_load_options,char const *)
0x180020085  cmp     [rsp+258h+var_178], 0
0x18002008d  jnz     loc_18002028C
0x180020093  mov     rdi, qword ptr [rsp+258h+length]
0x18002009b  cmp     rdi, 0AA0h
0x1800200a2  jbe     short loc_180020100
0x1800200a4  mov     rcx, [rsp+258h]; this
0x1800200ac  mov     [rsp+258h+var_230], rdi; char *
0x1800200b1  lea     rax, aLenZu; "len: %zu"
0x1800200b8  mov     qword ptr [rsp+258h+var_238], rax; int
0x1800200bd  mov     ebx, 80070057h
0x1800200c2  mov     r9d, ebx; char *
0x1800200c5  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\globalization\\coregl"...
0x1800200cc  mov     edx, 593h; void *
0x1800200d1  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800200d6  lea     rcx, [rsp+258h+var_1E8]; this
0x1800200db  call    ??1?$cloud_store_data@UCultureSettings@Culture@Globalization@Data@Windows@@@wil@@QEAA@XZ; wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>::~cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>(void)
0x1800200e0  nop
0x1800200e1  lea     rcx, [rsp+258h+var_210]; this
0x1800200e6  call    ??1cloud_store@wil@@QEAA@XZ; wil::cloud_store::~cloud_store(void)
0x1800200eb  nop
0x1800200ec  lea     rcx, [rsp+258h+var_168]; this
0x1800200f4  call    ??1SyncLanguageDataFromCloudActivity@CoreGlobConfigTraceLogging@@QEAA@XZ; CoreGlobConfigTraceLogging::SyncLanguageDataFromCloudActivity::~SyncLanguageDataFromCloudActivity(void)
0x1800200f9  mov     eax, ebx
0x1800200fb  jmp     loc_1800202C6
0x180020100  cmp     rdi, 1
0x180020104  jbe     loc_1800201CA
0x18002010a  mov     [rsp+258h+string], 0
0x180020113  lea     rcx, [rsp+258h+var_1E8]
0x180020118  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002011d  mov     rbx, rax
0x180020120  xor     ecx, ecx; string
0x180020122  call    cs:__imp_WindowsDeleteString
0x180020128  mov     [rsp+258h+string], 0
0x180020131  lea     r8, [rsp+258h+string]; string
0x180020136  mov     edx, edi; length
0x180020138  mov     rcx, rbx; sourceString
0x18002013b  call    cs:__imp_WindowsCreateString
0x180020141  mov     rcx, [rsp+258h]; this
0x180020149  test    eax, eax
0x18002014b  jns     short loc_18002015A
0x18002014d  mov     r9d, eax; char *
0x180020150  mov     edx, 59Ch; void *
0x180020155  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002015a  mov     rcx, [rsp+258h+string]; string
0x18002015f  call    cs:__imp_WindowsGetStringLen
0x180020165  cmp     eax, 1
0x180020168  jbe     short loc_1800201B6
0x18002016a  lea     rcx, [rsp+258h+var_1E8]
0x18002016f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180020174  mov     rbx, rax
0x180020177  mov     ecx, 3Bh ; ';'
0x18002017c  mov     rdx, [rsp+258h+string]
0x180020181  call    cs:__imp_SetUserLanguagesCore
0x180020187  mov     rcx, [rsp+258h]; this
0x18002018f  mov     [rsp+258h+var_230], rbx; char *
0x180020194  lea     rdi, aLs; "%ls"
0x18002019b  mov     qword ptr [rsp+258h+var_238], rdi; int
0x1800201a0  mov     r9d, eax; char *
0x1800201a3  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\globalization\\coregl"...
0x1800201aa  mov     edx, 5A1h; void *
0x1800201af  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800201b4  jmp     short loc_1800201BD
0x1800201b6  lea     rdi, aLs; "%ls"
0x1800201bd  mov     rcx, [rsp+258h+string]; string
0x1800201c2  call    cs:__imp_WindowsDeleteString
0x1800201c8  jmp     short loc_1800201D1
0x1800201ca  lea     rdi, aLs; "%ls"
0x1800201d1  cmp     [rsp+258h+var_1B8], 1
0x1800201da  jbe     short loc_18002021B
0x1800201dc  lea     rcx, [rsp+258h+var_1C8]
0x1800201e4  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800201e9  mov     rbx, rax
0x1800201ec  mov     rcx, rax
0x1800201ef  call    cs:__imp_SetUserGeoName
0x1800201f5  mov     rcx, [rsp+258h]; this
0x1800201fd  mov     [rsp+258h+var_230], rbx; char *
0x180020202  mov     qword ptr [rsp+258h+var_238], rdi; int
0x180020207  mov     r9d, eax; char *
0x18002020a  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\globalization\\coregl"...
0x180020211  mov     edx, 5AAh; void *
0x180020216  call    ?Log_IfWin32BoolFalseMsg@in1diag3@details@wil@@YAHPEAXIPEBDH1ZZ; wil::details::in1diag3::Log_IfWin32BoolFalseMsg(void *,uint,char const *,int,char const *,...)
0x18002021b  cmp     [rsp+258h+var_198], 1
0x180020224  jbe     short loc_18002026A
0x180020226  lea     rcx, [rsp+258h+var_1A8]
0x18002022e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180020233  mov     rbx, rax
0x180020236  mov     edx, 1
0x18002023b  mov     rcx, rax
0x18002023e  call    cs:__imp_NlsUpdateLocale
0x180020244  mov     rcx, [rsp+258h]; this
0x18002024c  mov     [rsp+258h+var_230], rbx; char *
0x180020251  mov     qword ptr [rsp+258h+var_238], rdi; unsigned int
0x180020256  mov     r9d, eax; char *
0x180020259  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\globalization\\coregl"...
0x180020260  mov     edx, 5B4h; void *
0x180020265  call    ?Log_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Log_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x18002026a  call    IsSendNotifyMessageWPresent
0x18002026f  test    al, al
0x180020271  jz      short loc_18002028C
0x180020273  lea     r9, lParam; "intl"
0x18002027a  xor     r8d, r8d; wParam
0x18002027d  lea     edx, [r8+1Ah]; Msg
0x180020281  mov     ecx, 0FFFFh; hWnd
0x180020286  call    cs:__imp_SendNotifyMessageW
0x18002028c  xor     edx, edx
0x18002028e  lea     rcx, [rsp+258h+var_168]
0x180020296  call    ?Stop@?$ActivityBase@VCoreGlobConfigTraceLogging@@$00$0CAAAAAAAAAAA@$04$0BAAAIAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<CoreGlobConfigTraceLogging,1,35184372088832,5,16779264,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18002029b  lea     rcx, [rsp+258h+var_1E8]; this
0x1800202a0  call    ??1?$cloud_store_data@UCultureSettings@Culture@Globalization@Data@Windows@@@wil@@QEAA@XZ; wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>::~cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>(void)
0x1800202a5  nop
0x1800202a6  lea     rcx, [rsp+258h+var_210]; this
0x1800202ab  call    ??1cloud_store@wil@@QEAA@XZ; wil::cloud_store::~cloud_store(void)
0x1800202b0  nop
0x1800202b1  lea     rcx, [rsp+258h+var_168]; this
0x1800202b9  call    ??1SyncLanguageDataFromCloudActivity@CoreGlobConfigTraceLogging@@QEAA@XZ; CoreGlobConfigTraceLogging::SyncLanguageDataFromCloudActivity::~SyncLanguageDataFromCloudActivity(void)
0x1800202be  xor     eax, eax
0x1800202c0  jmp     short loc_1800202C6
0x1800202c2  mov     eax, dword ptr [rsp+258h+string]
0x1800202c6  mov     rcx, [rsp+258h+var_18]
0x1800202ce  xor     rcx, rsp; StackCookie
0x1800202d1  call    __security_check_cookie
0x1800202d6  mov     rbx, [rsp+258h+arg_0]
0x1800202de  add     rsp, 250h
0x1800202e5  pop     rdi
0x1800202e6  retn
```
