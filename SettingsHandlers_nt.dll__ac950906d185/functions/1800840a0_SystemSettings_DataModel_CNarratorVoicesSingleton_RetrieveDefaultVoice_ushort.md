# SystemSettings::DataModel::CNarratorVoicesSingleton::RetrieveDefaultVoice(ushort * *)

- ea: `0x1800840a0`
- end: `0x1800842a1`
- name: `?RetrieveDefaultVoice@CNarratorVoicesSingleton@DataModel@SystemSettings@@AEAAJPEAPEAG@Z`
- size: `513`
- prototype: `__int64 __fastcall(SystemSettings::DataModel::CNarratorVoicesSingleton *__hidden this, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180081ed8`

## callees

- `0x180019a20`
- `0x18007b2a0`
- `0x18007d13c`
- `0x1800823b0`
- `0x1800840a0`
- `0x1800842a8`
- `0x180088de4`

## import_xrefs

- `api-ms-win-core-localization-obsolete-l1-2-0!GetUserDefaultUILanguage` at `0x1800840bc`
- `api-ms-win-core-localization-obsolete-l1-2-0!GetUserDefaultUILanguage` at `0x1800840bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800840dc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180084129`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180084147`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180084197`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800841b1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180084238`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180084252`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180084267`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180084281`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800840dc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180084129`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180084147`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180084197`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800841b1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180084238`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180084252`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180084267`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180084281`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800841d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800841d9`
- `Bcp47Langs!Bcp47FromLcid` at `0x1800840f8`
- `Bcp47Langs!Bcp47FromLcid` at `0x1800840f8`
- `Bcp47Langs!Bcp47GetNlsForm` at `0x180084166`
- `Bcp47Langs!Bcp47GetNlsForm` at `0x180084166`

## string_xrefs

- `0x180084112`: `shell\systemsettingsthreshold\handlers\internal\accessibility\lib\narrator.cpp`
- `0x180084180`: `shell\systemsettingsthreshold\handlers\internal\accessibility\lib\narrator.cpp`
- `0x180084221`: `shell\systemsettingsthreshold\handlers\internal\accessibility\lib\narrator.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall SystemSettings::DataModel::CNarratorVoicesSingleton::RetrieveDefaultVoice(
        SystemSettings::DataModel::CNarratorVoicesSingleton *this,
        unsigned __int16 **a2)
{
  unsigned int UserDefaultUILanguage; // ebx
  int v4; // eax
  unsigned int v5; // ebx
  __int64 result; // rax
  int NlsForm; // eax
  unsigned int v8; // ebx
  PCWSTR StringRawBuffer; // rbx
  SystemSettings::DataModel::CNarratorVoicesSingleton *v10; // rcx
  struct SystemSettings::DataModel::OnecoreVoiceInformation *OnecoreVoiceInformation; // rax
  __int64 CachedVoices; // rax
  __int64 v13; // rcx
  int DefaultVoiceInternal; // ebx
  const char *v15; // r9
  int v16[10]; // [rsp+20h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  HSTRING v18; // [rsp+50h] [rbp+8h] BYREF
  HSTRING string; // [rsp+60h] [rbp+18h] BYREF

  v18 = (HSTRING)this;
  UserDefaultUILanguage = dword_18039B718;
  if ( !dword_18039B718 )
  {
    UserDefaultUILanguage = GetUserDefaultUILanguage();
    dword_18039B718 = UserDefaultUILanguage;
  }
  string = 0;
  WindowsDeleteString(0);
  string = 0;
  v4 = Bcp47FromLcid(UserDefaultUILanguage, &string);
  v5 = v4;
  if ( v4 >= 0 )
  {
    v18 = 0;
    WindowsDeleteString(0);
    v18 = 0;
    NlsForm = Bcp47GetNlsForm(string, &v18);
    v8 = NlsForm;
    if ( NlsForm >= 0 )
    {
      try
      {
        wil::details::FeatureImpl<__WilFeatureTraits_Feature_NarratorSettingsCrashFix>::ReportUsage();
        StringRawBuffer = WindowsGetStringRawBuffer(v18, 0);
        OnecoreVoiceInformation = SystemSettings::DataModel::CNarratorVoicesSingleton::GetOnecoreVoiceInformation(v10);
        CachedVoices = SystemSettings::DataModel::OnecoreVoiceInformation::GetCachedVoices(OnecoreVoiceInformation, v16);
        DefaultVoiceInternal = SystemSettings::DataModel::CNarratorVoicesSingleton::RetrieveDefaultVoiceInternal(
                                 v13,
                                 CachedVoices,
                                 StringRawBuffer,
                                 a2);
        std::vector<Microsoft::WRL::ComPtr<Windows::Media::SpeechSynthesis::IVoiceInformation>>::_Tidy(v16);
        if ( DefaultVoiceInternal >= 0 )
        {
          WindowsDeleteString(v18);
          v18 = 0;
          WindowsDeleteString(string);
          result = 0;
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x237,
            (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\accessibility\\lib\\narrator.cpp",
            (const char *)(unsigned int)DefaultVoiceInternal,
            v16[0]);
          WindowsDeleteString(v18);
          v18 = 0;
          WindowsDeleteString(string);
          result = (unsigned int)DefaultVoiceInternal;
        }
      }
      catch ( ... )
      {
        return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                               retaddr,
                               (void *)0x240,
                               (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\accessibility\\lib\\narrator.cpp",
                               v15);
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x232,
        (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\accessibility\\lib\\narrator.cpp",
        (const char *)(unsigned int)NlsForm,
        v16[0]);
      WindowsDeleteString(v18);
      v18 = 0;
      WindowsDeleteString(string);
      return v8;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x22F,
      (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\accessibility\\lib\\narrator.cpp",
      (const char *)(unsigned int)v4,
      v16[0]);
    WindowsDeleteString(string);
    return v5;
  }
  return result;
}

```

## disassembly

```asm
0x1800840a0  mov     [rsp+arg_8], rbx
0x1800840a5  mov     [rsp+arg_0], rcx
0x1800840aa  push    rdi
0x1800840ab  sub     rsp, 40h
0x1800840af  mov     rdi, rdx
0x1800840b2  mov     ebx, cs:dword_18039B718
0x1800840b8  test    ebx, ebx
0x1800840ba  jnz     short loc_1800840D1
0x1800840bc  call    cs:__imp_GetUserDefaultUILanguage
0x1800840c3  nop     dword ptr [rax+rax+00h]
0x1800840c8  movzx   ebx, ax
0x1800840cb  mov     cs:dword_18039B718, ebx
0x1800840d1  mov     [rsp+48h+string], 0
0x1800840da  xor     ecx, ecx; string
0x1800840dc  call    cs:__imp_WindowsDeleteString
0x1800840e3  nop     dword ptr [rax+rax+00h]
0x1800840e8  mov     [rsp+48h+string], 0
0x1800840f1  lea     rdx, [rsp+48h+string]
0x1800840f6  mov     ecx, ebx
0x1800840f8  call    cs:__imp_Bcp47FromLcid
0x1800840ff  nop     dword ptr [rax+rax+00h]
0x180084104  mov     ebx, eax
0x180084106  test    eax, eax
0x180084108  jns     short loc_18008413C
0x18008410a  mov     rcx, [rsp+48h]; this
0x18008410f  mov     r9d, eax; char *
0x180084112  lea     r8, aShellSystemset_68; "shell\\systemsettingsthreshold\\handler"...
0x180084119  mov     edx, 22Fh; void *
0x18008411e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180084123  nop
0x180084124  mov     rcx, [rsp+48h+string]; string
0x180084129  call    cs:__imp_WindowsDeleteString
0x180084130  nop     dword ptr [rax+rax+00h]
0x180084135  mov     eax, ebx
0x180084137  jmp     loc_180084295
0x18008413c  mov     [rsp+48h+arg_0], 0
0x180084145  xor     ecx, ecx; string
0x180084147  call    cs:__imp_WindowsDeleteString
0x18008414e  nop     dword ptr [rax+rax+00h]
0x180084153  mov     [rsp+48h+arg_0], 0
0x18008415c  lea     rdx, [rsp+48h+arg_0]
0x180084161  mov     rcx, [rsp+48h+string]
0x180084166  call    cs:__imp_Bcp47GetNlsForm
0x18008416d  nop     dword ptr [rax+rax+00h]
0x180084172  mov     ebx, eax
0x180084174  test    eax, eax
0x180084176  jns     short loc_1800841C4
0x180084178  mov     rcx, [rsp+48h]; this
0x18008417d  mov     r9d, eax; char *
0x180084180  lea     r8, aShellSystemset_68; "shell\\systemsettingsthreshold\\handler"...
0x180084187  mov     edx, 232h; void *
0x18008418c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180084191  nop
0x180084192  mov     rcx, [rsp+48h+arg_0]; string
0x180084197  call    cs:__imp_WindowsDeleteString
0x18008419e  nop     dword ptr [rax+rax+00h]
0x1800841a3  mov     [rsp+48h+arg_0], 0
0x1800841ac  mov     rcx, [rsp+48h+string]; string
0x1800841b1  call    cs:__imp_WindowsDeleteString
0x1800841b8  nop     dword ptr [rax+rax+00h]
0x1800841bd  mov     eax, ebx
0x1800841bf  jmp     loc_180084295
0x1800841c4  mov     dl, 1
0x1800841c6  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_NarratorSettingsCrashFix@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_NarratorSettingsCrashFix@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NarratorSettingsCrashFix> `wil::Feature<__WilFeatureTraits_Feature_NarratorSettingsCrashFix>::GetImpl(void)'::`2'::impl
0x1800841cd  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_NarratorSettingsCrashFix@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NarratorSettingsCrashFix>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1800841d2  xor     edx, edx; length
0x1800841d4  mov     rcx, [rsp+48h+arg_0]; string
0x1800841d9  call    cs:__imp_WindowsGetStringRawBuffer
0x1800841e0  nop     dword ptr [rax+rax+00h]
0x1800841e5  mov     rbx, rax
0x1800841e8  call    ?GetOnecoreVoiceInformation@CNarratorVoicesSingleton@DataModel@SystemSettings@@QEAAPEAVOnecoreVoiceInformation@23@XZ; SystemSettings::DataModel::CNarratorVoicesSingleton::GetOnecoreVoiceInformation(void)
0x1800841ed  lea     rdx, [rsp+48h+var_28]
0x1800841f2  mov     rcx, rax
0x1800841f5  call    ?GetCachedVoices@OnecoreVoiceInformation@DataModel@SystemSettings@@QEBA?AV?$vector@V?$ComPtr@UIVoiceInformation@SpeechSynthesis@Media@Windows@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIVoiceInformation@SpeechSynthesis@Media@Windows@@@WRL@Microsoft@@@std@@@std@@XZ; SystemSettings::DataModel::OnecoreVoiceInformation::GetCachedVoices(void)
0x1800841fa  nop
0x1800841fb  mov     r9, rdi
0x1800841fe  mov     r8, rbx
0x180084201  mov     rdx, rax
0x180084204  call    ?RetrieveDefaultVoiceInternal@CNarratorVoicesSingleton@DataModel@SystemSettings@@AEAAJAEBV?$vector@V?$ComPtr@UIVoiceInformation@SpeechSynthesis@Media@Windows@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIVoiceInformation@SpeechSynthesis@Media@Windows@@@WRL@Microsoft@@@std@@@std@@PEBGPEAPEAG@Z; SystemSettings::DataModel::CNarratorVoicesSingleton::RetrieveDefaultVoiceInternal(std::vector<Microsoft::WRL::ComPtr<Windows::Media::SpeechSynthesis::IVoiceInformation>> const &,ushort const *,ushort * *)
0x180084209  mov     ebx, eax
0x18008420b  lea     rcx, [rsp+48h+var_28]
0x180084210  call    ?_Tidy@?$vector@V?$ComPtr@UIVoiceInformation@SpeechSynthesis@Media@Windows@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIVoiceInformation@SpeechSynthesis@Media@Windows@@@WRL@Microsoft@@@std@@@std@@AEAAXXZ; std::vector<Microsoft::WRL::ComPtr<Windows::Media::SpeechSynthesis::IVoiceInformation>>::_Tidy(void)
0x180084215  test    ebx, ebx
0x180084217  jns     short loc_180084262
0x180084219  mov     rcx, [rsp+48h]; this
0x18008421e  mov     r9d, ebx; char *
0x180084221  lea     r8, aShellSystemset_68; "shell\\systemsettingsthreshold\\handler"...
0x180084228  mov     edx, 237h; void *
0x18008422d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180084232  nop
0x180084233  mov     rcx, [rsp+48h+arg_0]; string
0x180084238  call    cs:__imp_WindowsDeleteString
0x18008423f  nop     dword ptr [rax+rax+00h]
0x180084244  mov     [rsp+48h+arg_0], 0
0x18008424d  mov     rcx, [rsp+48h+string]; string
0x180084252  call    cs:__imp_WindowsDeleteString
0x180084259  nop     dword ptr [rax+rax+00h]
0x18008425e  mov     eax, ebx
0x180084260  jmp     short loc_180084295
0x180084262  mov     rcx, [rsp+48h+arg_0]; string
0x180084267  call    cs:__imp_WindowsDeleteString
0x18008426e  nop     dword ptr [rax+rax+00h]
0x180084273  mov     [rsp+48h+arg_0], 0
0x18008427c  mov     rcx, [rsp+48h+string]; string
0x180084281  call    cs:__imp_WindowsDeleteString
0x180084288  nop     dword ptr [rax+rax+00h]
0x18008428d  xor     eax, eax
0x18008428f  jmp     short loc_180084295
0x180084291  mov     eax, dword ptr [rsp+48h+arg_0]
0x180084295  mov     rbx, [rsp+48h+arg_8]
0x18008429a  add     rsp, 40h
0x18008429e  pop     rdi
0x18008429f  retn
```
