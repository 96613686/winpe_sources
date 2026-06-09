# SystemSettings::DataModel::CMagnifierVoicesSingleton::RetrieveDefaultVoice(ushort * *)

- ea: `0x18007b330`
- end: `0x18007b531`
- name: `?RetrieveDefaultVoice@CMagnifierVoicesSingleton@DataModel@SystemSettings@@AEAAJPEAPEAG@Z`
- size: `513`
- prototype: `__int64 __fastcall(SystemSettings::DataModel::CMagnifierVoicesSingleton *__hidden this, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18007a480`

## callees

- `0x180019a20`
- `0x18007a6e4`
- `0x18007b2a0`
- `0x18007b330`
- `0x18007b538`
- `0x18007d13c`
- `0x180088de4`

## import_xrefs

- `api-ms-win-core-localization-obsolete-l1-2-0!GetUserDefaultUILanguage` at `0x18007b34c`
- `api-ms-win-core-localization-obsolete-l1-2-0!GetUserDefaultUILanguage` at `0x18007b34c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007b36c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007b3b9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007b3d7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007b427`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007b441`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007b4c8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007b4e2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007b4f7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007b511`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007b36c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007b3b9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007b3d7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007b427`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007b441`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007b4c8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007b4e2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007b4f7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007b511`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007b469`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007b469`
- `Bcp47Langs!Bcp47FromLcid` at `0x18007b388`
- `Bcp47Langs!Bcp47FromLcid` at `0x18007b388`
- `Bcp47Langs!Bcp47GetNlsForm` at `0x18007b3f6`
- `Bcp47Langs!Bcp47GetNlsForm` at `0x18007b3f6`

## string_xrefs

- `0x18007b3a2`: `shell\systemsettingsthreshold\handlers\internal\accessibility\lib\magnifier.cpp`
- `0x18007b410`: `shell\systemsettingsthreshold\handlers\internal\accessibility\lib\magnifier.cpp`
- `0x18007b4b1`: `shell\systemsettingsthreshold\handlers\internal\accessibility\lib\magnifier.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall SystemSettings::DataModel::CMagnifierVoicesSingleton::RetrieveDefaultVoice(
        SystemSettings::DataModel::CMagnifierVoicesSingleton *this,
        unsigned __int16 **a2)
{
  unsigned int UserDefaultUILanguage; // ebx
  int v4; // eax
  unsigned int v5; // ebx
  __int64 result; // rax
  int NlsForm; // eax
  unsigned int v8; // ebx
  PCWSTR StringRawBuffer; // rbx
  SystemSettings::DataModel::CMagnifierVoicesSingleton *v10; // rcx
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
  UserDefaultUILanguage = dword_18039B6E0;
  if ( !dword_18039B6E0 )
  {
    UserDefaultUILanguage = GetUserDefaultUILanguage();
    dword_18039B6E0 = UserDefaultUILanguage;
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
        OnecoreVoiceInformation = SystemSettings::DataModel::CMagnifierVoicesSingleton::GetOnecoreVoiceInformation(v10);
        CachedVoices = SystemSettings::DataModel::OnecoreVoiceInformation::GetCachedVoices(OnecoreVoiceInformation, v16);
        DefaultVoiceInternal = SystemSettings::DataModel::CMagnifierVoicesSingleton::RetrieveDefaultVoiceInternal(
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
            (void *)0x33A,
            (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\accessibility\\lib\\magnifier.cpp",
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
                               (void *)0x344,
                               (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\accessibility\\lib\\magnifier.cpp",
                               v15);
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x334,
        (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\accessibility\\lib\\magnifier.cpp",
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
      (void *)0x331,
      (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\accessibility\\lib\\magnifier.cpp",
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
0x18007b330  mov     [rsp+arg_8], rbx
0x18007b335  mov     [rsp+arg_0], rcx
0x18007b33a  push    rdi
0x18007b33b  sub     rsp, 40h
0x18007b33f  mov     rdi, rdx
0x18007b342  mov     ebx, cs:dword_18039B6E0
0x18007b348  test    ebx, ebx
0x18007b34a  jnz     short loc_18007B361
0x18007b34c  call    cs:__imp_GetUserDefaultUILanguage
0x18007b353  nop     dword ptr [rax+rax+00h]
0x18007b358  movzx   ebx, ax
0x18007b35b  mov     cs:dword_18039B6E0, ebx
0x18007b361  mov     [rsp+48h+string], 0
0x18007b36a  xor     ecx, ecx; string
0x18007b36c  call    cs:__imp_WindowsDeleteString
0x18007b373  nop     dword ptr [rax+rax+00h]
0x18007b378  mov     [rsp+48h+string], 0
0x18007b381  lea     rdx, [rsp+48h+string]
0x18007b386  mov     ecx, ebx
0x18007b388  call    cs:__imp_Bcp47FromLcid
0x18007b38f  nop     dword ptr [rax+rax+00h]
0x18007b394  mov     ebx, eax
0x18007b396  test    eax, eax
0x18007b398  jns     short loc_18007B3CC
0x18007b39a  mov     rcx, [rsp+48h]; this
0x18007b39f  mov     r9d, eax; char *
0x18007b3a2  lea     r8, aShellSystemset_79; "shell\\systemsettingsthreshold\\handler"...
0x18007b3a9  mov     edx, 331h; void *
0x18007b3ae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007b3b3  nop
0x18007b3b4  mov     rcx, [rsp+48h+string]; string
0x18007b3b9  call    cs:__imp_WindowsDeleteString
0x18007b3c0  nop     dword ptr [rax+rax+00h]
0x18007b3c5  mov     eax, ebx
0x18007b3c7  jmp     loc_18007B525
0x18007b3cc  mov     [rsp+48h+arg_0], 0
0x18007b3d5  xor     ecx, ecx; string
0x18007b3d7  call    cs:__imp_WindowsDeleteString
0x18007b3de  nop     dword ptr [rax+rax+00h]
0x18007b3e3  mov     [rsp+48h+arg_0], 0
0x18007b3ec  lea     rdx, [rsp+48h+arg_0]
0x18007b3f1  mov     rcx, [rsp+48h+string]
0x18007b3f6  call    cs:__imp_Bcp47GetNlsForm
0x18007b3fd  nop     dword ptr [rax+rax+00h]
0x18007b402  mov     ebx, eax
0x18007b404  test    eax, eax
0x18007b406  jns     short loc_18007B454
0x18007b408  mov     rcx, [rsp+48h]; this
0x18007b40d  mov     r9d, eax; char *
0x18007b410  lea     r8, aShellSystemset_79; "shell\\systemsettingsthreshold\\handler"...
0x18007b417  mov     edx, 334h; void *
0x18007b41c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007b421  nop
0x18007b422  mov     rcx, [rsp+48h+arg_0]; string
0x18007b427  call    cs:__imp_WindowsDeleteString
0x18007b42e  nop     dword ptr [rax+rax+00h]
0x18007b433  mov     [rsp+48h+arg_0], 0
0x18007b43c  mov     rcx, [rsp+48h+string]; string
0x18007b441  call    cs:__imp_WindowsDeleteString
0x18007b448  nop     dword ptr [rax+rax+00h]
0x18007b44d  mov     eax, ebx
0x18007b44f  jmp     loc_18007B525
0x18007b454  mov     dl, 1
0x18007b456  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_NarratorSettingsCrashFix@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_NarratorSettingsCrashFix@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NarratorSettingsCrashFix> `wil::Feature<__WilFeatureTraits_Feature_NarratorSettingsCrashFix>::GetImpl(void)'::`2'::impl
0x18007b45d  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_NarratorSettingsCrashFix@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NarratorSettingsCrashFix>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18007b462  xor     edx, edx; length
0x18007b464  mov     rcx, [rsp+48h+arg_0]; string
0x18007b469  call    cs:__imp_WindowsGetStringRawBuffer
0x18007b470  nop     dword ptr [rax+rax+00h]
0x18007b475  mov     rbx, rax
0x18007b478  call    ?GetOnecoreVoiceInformation@CMagnifierVoicesSingleton@DataModel@SystemSettings@@QEAAPEAVOnecoreVoiceInformation@23@XZ; SystemSettings::DataModel::CMagnifierVoicesSingleton::GetOnecoreVoiceInformation(void)
0x18007b47d  lea     rdx, [rsp+48h+var_28]
0x18007b482  mov     rcx, rax
0x18007b485  call    ?GetCachedVoices@OnecoreVoiceInformation@DataModel@SystemSettings@@QEBA?AV?$vector@V?$ComPtr@UIVoiceInformation@SpeechSynthesis@Media@Windows@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIVoiceInformation@SpeechSynthesis@Media@Windows@@@WRL@Microsoft@@@std@@@std@@XZ; SystemSettings::DataModel::OnecoreVoiceInformation::GetCachedVoices(void)
0x18007b48a  nop
0x18007b48b  mov     r9, rdi
0x18007b48e  mov     r8, rbx
0x18007b491  mov     rdx, rax
0x18007b494  call    ?RetrieveDefaultVoiceInternal@CMagnifierVoicesSingleton@DataModel@SystemSettings@@AEAAJAEBV?$vector@V?$ComPtr@UIVoiceInformation@SpeechSynthesis@Media@Windows@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIVoiceInformation@SpeechSynthesis@Media@Windows@@@WRL@Microsoft@@@std@@@std@@PEBGPEAPEAG@Z; SystemSettings::DataModel::CMagnifierVoicesSingleton::RetrieveDefaultVoiceInternal(std::vector<Microsoft::WRL::ComPtr<Windows::Media::SpeechSynthesis::IVoiceInformation>> const &,ushort const *,ushort * *)
0x18007b499  mov     ebx, eax
0x18007b49b  lea     rcx, [rsp+48h+var_28]
0x18007b4a0  call    ?_Tidy@?$vector@V?$ComPtr@UIVoiceInformation@SpeechSynthesis@Media@Windows@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIVoiceInformation@SpeechSynthesis@Media@Windows@@@WRL@Microsoft@@@std@@@std@@AEAAXXZ; std::vector<Microsoft::WRL::ComPtr<Windows::Media::SpeechSynthesis::IVoiceInformation>>::_Tidy(void)
0x18007b4a5  test    ebx, ebx
0x18007b4a7  jns     short loc_18007B4F2
0x18007b4a9  mov     rcx, [rsp+48h]; this
0x18007b4ae  mov     r9d, ebx; char *
0x18007b4b1  lea     r8, aShellSystemset_79; "shell\\systemsettingsthreshold\\handler"...
0x18007b4b8  mov     edx, 33Ah; void *
0x18007b4bd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007b4c2  nop
0x18007b4c3  mov     rcx, [rsp+48h+arg_0]; string
0x18007b4c8  call    cs:__imp_WindowsDeleteString
0x18007b4cf  nop     dword ptr [rax+rax+00h]
0x18007b4d4  mov     [rsp+48h+arg_0], 0
0x18007b4dd  mov     rcx, [rsp+48h+string]; string
0x18007b4e2  call    cs:__imp_WindowsDeleteString
0x18007b4e9  nop     dword ptr [rax+rax+00h]
0x18007b4ee  mov     eax, ebx
0x18007b4f0  jmp     short loc_18007B525
0x18007b4f2  mov     rcx, [rsp+48h+arg_0]; string
0x18007b4f7  call    cs:__imp_WindowsDeleteString
0x18007b4fe  nop     dword ptr [rax+rax+00h]
0x18007b503  mov     [rsp+48h+arg_0], 0
0x18007b50c  mov     rcx, [rsp+48h+string]; string
0x18007b511  call    cs:__imp_WindowsDeleteString
0x18007b518  nop     dword ptr [rax+rax+00h]
0x18007b51d  xor     eax, eax
0x18007b51f  jmp     short loc_18007B525
0x18007b521  mov     eax, dword ptr [rsp+48h+arg_0]
0x18007b525  mov     rbx, [rsp+48h+arg_8]
0x18007b52a  add     rsp, 40h
0x18007b52e  pop     rdi
0x18007b52f  retn
```
