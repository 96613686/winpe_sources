# UpdateAndSaveCultureSettings(wil::cloud_store &,wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings> &)

- ea: `0x18001b6e0`
- end: `0x18001b8d3`
- name: `?UpdateAndSaveCultureSettings@@YAJAEAVcloud_store@wil@@AEAV?$cloud_store_data@UCultureSettings@Culture@Globalization@Data@Windows@@@2@@Z`
- size: `499`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config, installer_update`

## callers

- `0x1800126c4`
- `0x1800203b0`

## callees

- `0x180002380`
- `0x1800032dc`
- `0x18000c494`
- `0x18000ed48`
- `0x18000f35c`
- `0x180011c64`
- `0x18001617c`
- `0x180019dfc`
- `0x180019f30`
- `0x18001b6e0`
- `0x18001d38c`
- `0x18001d3ac`
- `0x18001e868`

## import_xrefs

- `KERNELBASE!GetUserDefaultLocaleName` at `0x18001b74f`
- `KERNELBASE!GetUserDefaultLocaleName` at `0x18001b74f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001b7e9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001b890`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001b7e9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001b890`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x18001b826`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x18001b826`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001b838`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001b838`
- `api-ms-win-core-localization-l1-2-3!GetUserDefaultGeoName` at `0x18001b79d`
- `api-ms-win-core-localization-l1-2-3!GetUserDefaultGeoName` at `0x18001b79d`
- `Bcp47Langs!GetUserLanguages` at `0x18001b802`
- `Bcp47Langs!GetUserLanguages` at `0x18001b802`

## string_xrefs

- `0x18001b705`: `UpdateCultureSettingsActivity`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall UpdateAndSaveCultureSettings(__int64 a1, __int64 a2)
{
  int UserDefaultLocaleName; // eax
  unsigned int v5; // r8d
  const char *v6; // r9
  __int64 v7; // r8
  int UserDefaultGeoName; // eax
  unsigned int v9; // r8d
  const char *v10; // r9
  __int64 v11; // rax
  int UserLanguages; // eax
  __int64 v13; // r8
  unsigned int v14; // r8d
  PCWSTR StringRawBuffer; // rax
  __int64 v16; // rax
  __int64 v17; // rcx
  int v19; // [rsp+20h] [rbp-248h]
  HSTRING string; // [rsp+30h] [rbp-238h] BYREF
  _BYTE v21[24]; // [rsp+38h] [rbp-230h] BYREF
  _QWORD v22[42]; // [rsp+50h] [rbp-218h] BYREF
  WCHAR LocaleName[88]; // [rsp+1A0h] [rbp-C8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+0h]

  wil::ActivityBase<CoreGlobConfigTraceLogging,1,35184372088832,5,16779264,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CoreGlobConfigTraceLogging,1,35184372088832,5,16779264,_TlgReflectorTag_Param0IsProviderType>(
    (__int64)v22,
    (__int64)"UpdateCultureSettingsActivity");
  v22[0] = &CoreGlobConfigTraceLogging::UpdateCultureSettingsActivity::`vftable';
  CoreGlobConfigTraceLogging::UpdateCultureSettingsActivity::StartActivity((CoreGlobConfigTraceLogging::UpdateCultureSettingsActivity *)v22);
  memset_0(LocaleName, 0, 0xAAu);
  UserDefaultLocaleName = GetUserDefaultLocaleName(LocaleName, 85);
  if ( UserDefaultLocaleName )
  {
    if ( UserDefaultLocaleName > 0 )
    {
      v7 = std::_WChar_traits<unsigned short>::length(LocaleName);
      std::wstring::_Assign<unsigned short>(a2 + 64, LocaleName, v7);
    }
  }
  else
  {
    wil::details::in1diag3::_Log_GetLastError(retaddr, (void *)0x4C0, v5, v6);
  }
  UserDefaultGeoName = GetUserDefaultGeoName(LocaleName, 85);
  if ( UserDefaultGeoName )
  {
    if ( UserDefaultGeoName > 0 )
    {
      v11 = std::_WChar_traits<unsigned short>::length(LocaleName);
      std::wstring::_Assign<unsigned short>(a2 + 32, LocaleName, v11);
    }
  }
  else
  {
    wil::details::in1diag3::_Log_GetLastError(retaddr, (void *)0x4C7, v9, v10);
  }
  WindowsDeleteString(0);
  string = 0;
  UserLanguages = GetUserLanguages(59, &string);
  if ( UserLanguages < 0 )
    wil::details::in1diag3::_Log_Hr(retaddr, (void *)0x4CE, v13, (const char *)(unsigned int)UserLanguages);
  if ( WindowsGetStringLen(string) < 2 )
  {
    wil::details::in1diag3::Log_Hr(retaddr, (void *)0x4D8, v14, (const char *)0x8000FFFFLL, v19);
  }
  else
  {
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    v16 = std::_WChar_traits<unsigned short>::length(StringRawBuffer);
    std::wstring::_Assign<unsigned short>(a2, v17, v16);
  }
  wil::cloud_store::save<Windows::Data::Globalization::Culture::CultureSettings>(a1, v21, a2);
  wil::ActivityBase<CoreGlobConfigTraceLogging,1,35184372088832,5,16779264,_TlgReflectorTag_Param0IsProviderType>::Stop(
    v22,
    0);
  WindowsDeleteString(string);
  string = 0;
  CoreGlobConfigTraceLogging::UpdateCultureSettingsActivity::~UpdateCultureSettingsActivity((CoreGlobConfigTraceLogging::UpdateCultureSettingsActivity *)v22);
  return 0;
}

```

## disassembly

```asm
0x18001b6e0  mov     [rsp+arg_10], rbx
0x18001b6e5  push    rdi
0x18001b6e6  sub     rsp, 260h
0x18001b6ed  mov     rax, cs:__security_cookie
0x18001b6f4  xor     rax, rsp
0x18001b6f7  mov     [rsp+268h+var_18], rax
0x18001b6ff  mov     rbx, rdx
0x18001b702  mov     rdi, rcx
0x18001b705  lea     rdx, aUpdatecultures; "UpdateCultureSettingsActivity"
0x18001b70c  lea     rcx, [rsp+268h+var_218]
0x18001b711  call    ??0?$ActivityBase@VCoreGlobConfigTraceLogging@@$00$0CAAAAAAAAAAA@$04$0BAAAIAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<CoreGlobConfigTraceLogging,1,35184372088832,5,16779264,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CoreGlobConfigTraceLogging,1,35184372088832,5,16779264,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18001b716  lea     rax, ??_7UpdateCultureSettingsActivity@CoreGlobConfigTraceLogging@@6B@; const CoreGlobConfigTraceLogging::UpdateCultureSettingsActivity::`vftable'
0x18001b71d  mov     [rsp+268h+var_218], rax
0x18001b722  lea     rcx, [rsp+268h+var_218]; this
0x18001b727  call    ?StartActivity@UpdateCultureSettingsActivity@CoreGlobConfigTraceLogging@@QEAAXXZ; CoreGlobConfigTraceLogging::UpdateCultureSettingsActivity::StartActivity(void)
0x18001b72c  nop
0x18001b72d  xor     edx, edx; Val
0x18001b72f  mov     r8d, 0AAh; Size
0x18001b735  lea     rcx, [rsp+268h+LocaleName]; void *
0x18001b73d  call    memset_0
0x18001b742  mov     edx, 55h ; 'U'; cchLocaleName
0x18001b747  lea     rcx, [rsp+268h+LocaleName]; lpLocaleName
0x18001b74f  call    cs:__imp_GetUserDefaultLocaleName
0x18001b755  mov     rcx, [rsp+268h]; this
0x18001b75d  test    eax, eax
0x18001b75f  jnz     short loc_18001B76D
0x18001b761  mov     edx, 4C0h; void *
0x18001b766  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x18001b76b  jmp     short loc_18001B790
0x18001b76d  jle     short loc_18001B790
0x18001b76f  lea     rcx, [rsp+268h+LocaleName]
0x18001b777  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18001b77c  mov     r8, rax
0x18001b77f  lea     rcx, [rbx+40h]
0x18001b783  lea     rdx, [rsp+268h+LocaleName]
0x18001b78b  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18001b790  mov     edx, 55h ; 'U'; geoNameCount
0x18001b795  lea     rcx, [rsp+268h+LocaleName]; geoName
0x18001b79d  call    cs:__imp_GetUserDefaultGeoName
0x18001b7a3  mov     rcx, [rsp+268h]; this
0x18001b7ab  test    eax, eax
0x18001b7ad  jnz     short loc_18001B7BB
0x18001b7af  mov     edx, 4C7h; void *
0x18001b7b4  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x18001b7b9  jmp     short loc_18001B7DE
0x18001b7bb  jle     short loc_18001B7DE
0x18001b7bd  lea     rcx, [rsp+268h+LocaleName]
0x18001b7c5  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18001b7ca  mov     r8, rax
0x18001b7cd  lea     rcx, [rbx+20h]
0x18001b7d1  lea     rdx, [rsp+268h+LocaleName]
0x18001b7d9  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18001b7de  mov     [rsp+268h+string], 0
0x18001b7e7  xor     ecx, ecx; string
0x18001b7e9  call    cs:__imp_WindowsDeleteString
0x18001b7ef  mov     [rsp+268h+string], 0
0x18001b7f8  mov     ecx, 3Bh ; ';'
0x18001b7fd  lea     rdx, [rsp+268h+string]
0x18001b802  call    cs:__imp_GetUserLanguages
0x18001b808  mov     rcx, [rsp+268h]; this
0x18001b810  test    eax, eax
0x18001b812  jns     short loc_18001B821
0x18001b814  mov     r9d, eax; char *
0x18001b817  mov     edx, 4CEh; void *
0x18001b81c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001b821  mov     rcx, [rsp+268h+string]; string
0x18001b826  call    cs:__imp_WindowsGetStringLen
0x18001b82c  cmp     eax, 2
0x18001b82f  jb      short loc_18001B856
0x18001b831  xor     edx, edx; length
0x18001b833  mov     rcx, [rsp+268h+string]; string
0x18001b838  call    cs:__imp_WindowsGetStringRawBuffer
0x18001b83e  mov     rcx, rax
0x18001b841  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18001b846  mov     r8, rax
0x18001b849  mov     rdx, rcx
0x18001b84c  mov     rcx, rbx
0x18001b84f  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18001b854  jmp     short loc_18001B86E
0x18001b856  mov     rcx, [rsp+268h]; this
0x18001b85e  mov     edx, 4D8h; void *
0x18001b863  mov     r9d, 8000FFFFh; char *
0x18001b869  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18001b86e  mov     r8, rbx
0x18001b871  lea     rdx, [rsp+268h+var_230]
0x18001b876  mov     rcx, rdi
0x18001b879  call    ??$save@UCultureSettings@Culture@Globalization@Data@Windows@@@cloud_store@wil@@QEAA?AVcloud_store_save_result@1@AEBV?$cloud_store_data@UCultureSettings@Culture@Globalization@Data@Windows@@@1@W4cloud_store_save_options@1@_KPEBD@Z; wil::cloud_store::save<Windows::Data::Globalization::Culture::CultureSettings>(wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings> const &,wil::cloud_store_save_options,unsigned __int64,char const *)
0x18001b87e  xor     edx, edx
0x18001b880  lea     rcx, [rsp+268h+var_218]
0x18001b885  call    ?Stop@?$ActivityBase@VCoreGlobConfigTraceLogging@@$00$0CAAAAAAAAAAA@$04$0BAAAIAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<CoreGlobConfigTraceLogging,1,35184372088832,5,16779264,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18001b88a  nop
0x18001b88b  mov     rcx, [rsp+268h+string]; string
0x18001b890  call    cs:__imp_WindowsDeleteString
0x18001b896  mov     [rsp+268h+string], 0
0x18001b89f  lea     rcx, [rsp+268h+var_218]; this
0x18001b8a4  call    ??1UpdateCultureSettingsActivity@CoreGlobConfigTraceLogging@@QEAA@XZ; CoreGlobConfigTraceLogging::UpdateCultureSettingsActivity::~UpdateCultureSettingsActivity(void)
0x18001b8a9  xor     eax, eax
0x18001b8ab  jmp     short loc_18001B8B1
0x18001b8ad  mov     eax, dword ptr [rsp+268h+string]
0x18001b8b1  mov     rcx, [rsp+268h+var_18]
0x18001b8b9  xor     rcx, rsp; StackCookie
0x18001b8bc  call    __security_check_cookie
0x18001b8c1  mov     rbx, [rsp+268h+arg_10]
0x18001b8c9  add     rsp, 260h
0x18001b8d0  pop     rdi
0x18001b8d1  retn
```
