# SystemSettings::Personalization::BackgroundCycleSlideshow::SetValue(HSTRING__ *)

- ea: `0x180123360`
- end: `0x1801235bb`
- name: `?SetValue@BackgroundCycleSlideshow@Personalization@SystemSettings@@UEAAJPEAUHSTRING__@@@Z`
- size: `603`
- prototype: `int(SystemSettings::Personalization::BackgroundCycleSlideshow *__hidden this, HSTRING)`
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x18000c840`
- `0x180011bb0`
- `0x180019a20`
- `0x18004d1ac`
- `0x180116cd4`
- `0x1801184f0`
- `0x180119a24`
- `0x180123360`
- `0x180124434`
- `0x1801246e8`
- `0x180196dc0`
- `0x180197af4`
- `0x180197d50`
- `0x18019856c`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180123474`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180123474`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180123415`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180123488`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801234e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18012352e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801235ac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180123415`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180123488`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801234e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18012352e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801235ac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18012338e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180123453`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18012338e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180123453`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall SystemSettings::Personalization::BackgroundCycleSlideshow::SetValue(
        SystemSettings::Personalization::BackgroundCycleSlideshow *this,
        HSTRING a2)
{
  const unsigned __int16 *StringRawBuffer; // r14
  int v3; // eax
  unsigned int v4; // ebx
  int i; // edi
  __int64 v6; // rsi
  HSTRING *v7; // r8
  int ResourceStringById; // eax
  HSTRING v9; // rbx
  const WCHAR *v10; // rax
  int SlideshowOptions; // edi
  __int64 v12; // rdx
  WCHAR *v13; // rsi
  BOOL bIgnoreCase; // [rsp+20h] [rbp-E0h]
  unsigned int v16; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID ppv; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v18; // [rsp+40h] [rbp-C0h] BYREF
  HSTRING string; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v20[42]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1E8h] [rbp+E8h]

  StringRawBuffer = WindowsGetStringRawBuffer(a2, 0);
  wil::ActivityBase<PersonalizeSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<PersonalizeSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v20);
  v20[0] = &PersonalizeSettingsTelemetry::BackgroundCycleSlideshowSetValue::`vftable';
  PersonalizeSettingsTelemetry::BackgroundCycleSlideshowSetValue::StartActivity(
    (PersonalizeSettingsTelemetry::BackgroundCycleSlideshowSetValue *)v20,
    StringRawBuffer);
  ppv = 0;
  v3 = SystemSettings::Personalization::DesktopWallpaperHelper::Initialize(&ppv);
  v4 = v3;
  if ( v3 >= 0 )
  {
    for ( i = 0; ; ++i )
    {
      if ( i >= 6 )
        goto LABEL_14;
      WindowsDeleteString(0);
      string = 0;
      v6 = i;
      ResourceStringById = SystemSettings::DataModel::GetResourceStringById(
                             (SystemSettings::DataModel *)off_18038E400[i],
                             &string,
                             v7);
      v4 = ResourceStringById;
      if ( ResourceStringById < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x534,
          (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\lib\\background.cpp",
          (const char *)(unsigned int)ResourceStringById,
          bIgnoreCase);
        WindowsDeleteString(string);
        goto LABEL_15;
      }
      v9 = string;
      v10 = WindowsGetStringRawBuffer(string, 0);
      if ( CompareStringOrdinal(v10, -1, StringRawBuffer, -1, 1) == 2 )
        break;
      WindowsDeleteString(v9);
    }
    v16 = 0;
    v18 = 0;
    SlideshowOptions = SystemSettings::Personalization::DesktopWallpaperHelper::GetSlideshowOptions(
                         (SystemSettings::Personalization::DesktopWallpaperHelper *)&ppv,
                         (enum DESKTOP_SLIDESHOW_OPTIONS *)&v16,
                         &v18);
    if ( SlideshowOptions < 0 )
    {
      v12 = 1339;
LABEL_10:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v12,
        (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\lib\\background.cpp",
        (const char *)(unsigned int)SlideshowOptions,
        bIgnoreCase);
      WindowsDeleteString(v9);
      v4 = SlideshowOptions;
      goto LABEL_15;
    }
    v13 = &_ImageBase + 2 * v6 + 1592460;
    SlideshowOptions = SystemSettings::Personalization::DesktopWallpaperHelper::SetSlideshowOptions(
                         &ppv,
                         v16,
                         *(unsigned int *)v13);
    if ( SlideshowOptions < 0 )
    {
      v12 = 1340;
      goto LABEL_10;
    }
    PersonalizeSettingsTelemetry::BackgroundCycleSlideshowSetValue::TimeMillisecondsEvent<unsigned int const &>(
      v20,
      v13);
    WindowsDeleteString(v9);
LABEL_14:
    SystemSettings::Personalization::CBackgroundSingleton::MarkSettingsUpdated((SystemSettings::Personalization::CBackgroundSingleton *)&SystemSettings::Personalization::g_BackgroundSingleton);
    wil::ActivityBase<PersonalizeSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
      v20,
      0);
    v4 = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x52F,
      (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\lib\\background.cpp",
      (const char *)(unsigned int)v3,
      bIgnoreCase);
  }
LABEL_15:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
  PersonalizeSettingsTelemetry::BackgroundCycleSlideshowSetValue::~BackgroundCycleSlideshowSetValue((PersonalizeSettingsTelemetry::BackgroundCycleSlideshowSetValue *)v20);
  return v4;
}

```

## disassembly

```asm
0x180123360  push    rbp
0x180123362  push    rbx
0x180123363  push    rsi
0x180123364  push    rdi
0x180123365  push    r12
0x180123367  push    r14
0x180123369  lea     rbp, [rsp-0B8h]
0x180123371  sub     rsp, 1B8h
0x180123378  mov     rax, cs:__security_cookie
0x18012337f  xor     rax, rsp
0x180123382  mov     [rbp+0E0h+var_40], rax
0x180123389  mov     rcx, rdx; string
0x18012338c  xor     edx, edx; length
0x18012338e  call    cs:__imp_WindowsGetStringRawBuffer
0x180123395  nop     dword ptr [rax+rax+00h]
0x18012339a  mov     r14, rax
0x18012339d  lea     rdx, aBackgroundcycl_0; "BackgroundCycleSlideshowSetValue"
0x1801233a4  lea     rcx, [rsp+1E0h+var_190]; struct wil::details::IFailureCallback *
0x1801233a9  call    ??0?$ActivityBase@VPersonalizeSettingsLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<PersonalizeSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<PersonalizeSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1801233ae  lea     rax, ??_7BackgroundCycleSlideshowSetValue@PersonalizeSettingsTelemetry@@6B@; const PersonalizeSettingsTelemetry::BackgroundCycleSlideshowSetValue::`vftable'
0x1801233b5  mov     [rsp+1E0h+var_190], rax
0x1801233ba  mov     rdx, r14; unsigned __int16 *
0x1801233bd  lea     rcx, [rsp+1E0h+var_190]; this
0x1801233c2  call    ?StartActivity@BackgroundCycleSlideshowSetValue@PersonalizeSettingsTelemetry@@QEAAXPEBG@Z; PersonalizeSettingsTelemetry::BackgroundCycleSlideshowSetValue::StartActivity(ushort const *)
0x1801233c7  nop
0x1801233c8  mov     [rsp+1E0h+ppv], 0
0x1801233d1  lea     rcx, [rsp+1E0h+ppv]; ppv
0x1801233d6  call    ?Initialize@DesktopWallpaperHelper@Personalization@SystemSettings@@QEAAJXZ; SystemSettings::Personalization::DesktopWallpaperHelper::Initialize(void)
0x1801233db  mov     ebx, eax
0x1801233dd  test    eax, eax
0x1801233df  jns     short loc_180123401
0x1801233e1  mov     rcx, [rbp+0E8h]; this
0x1801233e8  mov     r9d, eax; char *
0x1801233eb  lea     r8, aShellSystemset_24; "shell\\systemsettingsthreshold\\handler"...
0x1801233f2  mov     edx, 52Fh; void *
0x1801233f7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801233fc  jmp     loc_180123554
0x180123401  xor     edi, edi
0x180123403  lea     r12, __ImageBase
0x18012340a  cmp     edi, 6
0x18012340d  jge     loc_18012353A
0x180123413  xor     ecx, ecx; string
0x180123415  call    cs:__imp_WindowsDeleteString
0x18012341c  nop     dword ptr [rax+rax+00h]
0x180123421  mov     [rsp+1E0h+string], 0
0x18012342a  movsxd  rsi, edi
0x18012342d  lea     rdx, [rsp+1E0h+string]; HSTRING *
0x180123432  mov     rcx, rva off_18038E400[r12+rsi*8]; this
0x18012343a  call    ?GetResourceStringById@DataModel@SystemSettings@@YAJPEBGPEAPEAUHSTRING__@@@Z; SystemSettings::DataModel::GetResourceStringById(ushort const *,HSTRING__ * *)
0x18012343f  mov     ebx, eax
0x180123441  test    eax, eax
0x180123443  js      loc_18012358B
0x180123449  xor     edx, edx; length
0x18012344b  mov     rbx, [rsp+1E0h+string]
0x180123450  mov     rcx, rbx; string
0x180123453  call    cs:__imp_WindowsGetStringRawBuffer
0x18012345a  nop     dword ptr [rax+rax+00h]
0x18012345f  mov     [rsp+1E0h+bIgnoreCase], 1; int
0x180123467  or      r9d, 0FFFFFFFFh; cchCount2
0x18012346b  mov     r8, r14; lpString2
0x18012346e  or      edx, r9d; cchCount1
0x180123471  mov     rcx, rax; lpString1
0x180123474  call    cs:__imp_CompareStringOrdinal
0x18012347b  nop     dword ptr [rax+rax+00h]
0x180123480  cmp     eax, 2
0x180123483  jz      short loc_18012349B
0x180123485  mov     rcx, rbx; string
0x180123488  call    cs:__imp_WindowsDeleteString
0x18012348f  nop     dword ptr [rax+rax+00h]
0x180123494  inc     edi
0x180123496  jmp     loc_18012340A
0x18012349b  mov     [rsp+1E0h+var_1B0], 0
0x1801234a3  mov     [rsp+1E0h+var_1A0], 0
0x1801234ab  lea     r8, [rsp+1E0h+var_1A0]; unsigned int *
0x1801234b0  lea     rdx, [rsp+1E0h+var_1B0]; enum DESKTOP_SLIDESHOW_OPTIONS *
0x1801234b5  lea     rcx, [rsp+1E0h+ppv]; this
0x1801234ba  call    ?GetSlideshowOptions@DesktopWallpaperHelper@Personalization@SystemSettings@@QEAAJPEAW4DESKTOP_SLIDESHOW_OPTIONS@@PEAI@Z; SystemSettings::Personalization::DesktopWallpaperHelper::GetSlideshowOptions(DESKTOP_SLIDESHOW_OPTIONS *,uint *)
0x1801234bf  mov     edi, eax
0x1801234c1  test    eax, eax
0x1801234c3  jns     short loc_1801234F4
0x1801234c5  mov     edx, 53Bh; void *
0x1801234ca  lea     r8, aShellSystemset_24; "shell\\systemsettingsthreshold\\handler"...
0x1801234d1  mov     r9d, edi; char *
0x1801234d4  mov     rcx, [rbp+0E8h]; this
0x1801234db  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801234e0  nop
0x1801234e1  mov     rcx, rbx; string
0x1801234e4  call    cs:__imp_WindowsDeleteString
0x1801234eb  nop     dword ptr [rax+rax+00h]
0x1801234f0  mov     ebx, edi
0x1801234f2  jmp     short loc_180123554
0x1801234f4  lea     rsi, ds:309918h[rsi*4]
0x1801234fc  add     rsi, r12
0x1801234ff  mov     r8d, [rsi]
0x180123502  mov     edx, [rsp+1E0h+var_1B0]
0x180123506  lea     rcx, [rsp+1E0h+ppv]
0x18012350b  call    ?SetSlideshowOptions@DesktopWallpaperHelper@Personalization@SystemSettings@@QEAAJW4DESKTOP_SLIDESHOW_OPTIONS@@I@Z; SystemSettings::Personalization::DesktopWallpaperHelper::SetSlideshowOptions(DESKTOP_SLIDESHOW_OPTIONS,uint)
0x180123510  mov     edi, eax
0x180123512  test    eax, eax
0x180123514  jns     short loc_18012351D
0x180123516  mov     edx, 53Ch
0x18012351b  jmp     short loc_1801234CA
0x18012351d  mov     rdx, rsi
0x180123520  lea     rcx, [rsp+1E0h+var_190]
0x180123525  call    ??$TimeMillisecondsEvent@AEBI@BackgroundCycleSlideshowSetValue@PersonalizeSettingsTelemetry@@QEAAXAEBI@Z; PersonalizeSettingsTelemetry::BackgroundCycleSlideshowSetValue::TimeMillisecondsEvent<uint const &>(uint const &)
0x18012352a  nop
0x18012352b  mov     rcx, rbx; string
0x18012352e  call    cs:__imp_WindowsDeleteString
0x180123535  nop     dword ptr [rax+rax+00h]
0x18012353a  lea     rcx, ?g_BackgroundSingleton@Personalization@SystemSettings@@3VCBackgroundSingleton@12@A; this
0x180123541  call    ?MarkSettingsUpdated@CBackgroundSingleton@Personalization@SystemSettings@@QEAAXXZ; SystemSettings::Personalization::CBackgroundSingleton::MarkSettingsUpdated(void)
0x180123546  xor     edx, edx
0x180123548  lea     rcx, [rsp+1E0h+var_190]
0x18012354d  call    ?Stop@?$ActivityBase@VPersonalizeSettingsLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<PersonalizeSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180123552  xor     ebx, ebx
0x180123554  lea     rcx, [rsp+1E0h+ppv]
0x180123559  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18012355e  nop
0x18012355f  lea     rcx, [rsp+1E0h+var_190]; this
0x180123564  call    ??1BackgroundCycleSlideshowSetValue@PersonalizeSettingsTelemetry@@QEAA@XZ; PersonalizeSettingsTelemetry::BackgroundCycleSlideshowSetValue::~BackgroundCycleSlideshowSetValue(void)
0x180123569  mov     eax, ebx
0x18012356b  mov     rcx, [rbp+0E0h+var_40]
0x180123572  xor     rcx, rsp; StackCookie
0x180123575  call    __security_check_cookie
0x18012357a  add     rsp, 1B8h
0x180123581  pop     r14
0x180123583  pop     r12
0x180123585  pop     rdi
0x180123586  pop     rsi
0x180123587  pop     rbx
0x180123588  pop     rbp
0x180123589  retn
0x18012358b  mov     rcx, [rbp+0E8h]; this
0x180123592  mov     r9d, eax; char *
0x180123595  lea     r8, aShellSystemset_24; "shell\\systemsettingsthreshold\\handler"...
0x18012359c  mov     edx, 534h; void *
0x1801235a1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801235a6  nop
0x1801235a7  mov     rcx, [rsp+1E0h+string]; string
0x1801235ac  call    cs:__imp_WindowsDeleteString
0x1801235b3  nop     dword ptr [rax+rax+00h]
0x1801235b8  jmp     short loc_180123554
```
