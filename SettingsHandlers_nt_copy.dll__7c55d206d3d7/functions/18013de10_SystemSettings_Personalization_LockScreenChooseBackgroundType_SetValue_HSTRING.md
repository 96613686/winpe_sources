# SystemSettings::Personalization::LockScreenChooseBackgroundType::SetValue(HSTRING__ *)

- ea: `0x18013de10`
- end: `0x18013dfe6`
- name: `?SetValue@LockScreenChooseBackgroundType@Personalization@SystemSettings@@UEAAJPEAUHSTRING__@@@Z`
- size: `470`
- prototype: `int(SystemSettings::Personalization::LockScreenChooseBackgroundType *__hidden this, HSTRING)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000c840`
- `0x180019a20`
- `0x18004d1ac`
- `0x180068188`
- `0x1801184f0`
- `0x1801246e8`
- `0x18013a890`
- `0x18013b494`
- `0x18013de10`
- `0x18013e340`
- `0x180289010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18013deea`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18013deea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18013de92`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18013df09`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18013df3e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18013de92`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18013df09`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18013df3e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18013de47`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18013dec9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18013de47`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18013dec9`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall SystemSettings::Personalization::LockScreenChooseBackgroundType::SetValue(
        SystemSettings::Personalization::LockScreenChooseBackgroundType *this,
        HSTRING a2)
{
  const unsigned __int16 *StringRawBuffer; // r15
  unsigned __int64 v4; // r14
  unsigned __int64 i; // rsi
  HSTRING *v6; // r8
  int ResourceStringById; // eax
  unsigned int v8; // ebx
  const WCHAR *v9; // rax
  int v10; // eax
  unsigned __int64 v11; // rcx
  BOOL bIgnoreCase; // [rsp+20h] [rbp-E0h]
  char v14; // [rsp+30h] [rbp-D0h] BYREF
  HSTRING string; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v16[42]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1C8h] [rbp+C8h]

  StringRawBuffer = WindowsGetStringRawBuffer(a2, 0);
  wil::ActivityBase<PersonalizeSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<PersonalizeSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v16);
  v16[0] = &PersonalizeSettingsTelemetry::LockScreenChooseBackgroundTypeSetValue::`vftable';
  PersonalizeSettingsTelemetry::LockScreenChooseBackgroundTypeSetValue::StartActivity(
    (PersonalizeSettingsTelemetry::LockScreenChooseBackgroundTypeSetValue *)v16,
    StringRawBuffer);
  v4 = 0;
  for ( i = 0; i < 3; ++i )
  {
    WindowsDeleteString(0);
    string = 0;
    ResourceStringById = SystemSettings::DataModel::GetResourceStringById(
                           (SystemSettings::DataModel *)off_18038E540[i],
                           &string,
                           v6);
    v8 = ResourceStringById;
    if ( ResourceStringById < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xCE,
        (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\lib\\lockscreen.cpp",
        (const char *)(unsigned int)ResourceStringById,
        bIgnoreCase);
      WindowsDeleteString(string);
      goto LABEL_11;
    }
    v9 = WindowsGetStringRawBuffer(string, 0);
    v10 = CompareStringOrdinal(v9, -1, StringRawBuffer, -1, 1);
    v11 = i;
    if ( v10 != 2 )
      v11 = v4;
    v4 = v11;
    WindowsDeleteString(string);
  }
  *((_DWORD *)this + 70) = v4;
  LODWORD(string) = v4;
  PersonalizeSettingsTelemetry::LockScreenChooseBackgroundTypeSetValue::LockScreenBackgroundTypeEvent<unsigned long>(
    v16,
    &string);
  (*(void (__fastcall **)(SystemSettings::Personalization::LockScreenChooseBackgroundType *, SystemSettings::Personalization::LockScreenChooseBackgroundType *))(*(_QWORD *)this + 192LL))(
    this,
    this);
  if ( !*((_DWORD *)this + 70) )
  {
    v14 = 1;
    string = (HSTRING)&v14;
    SystemSettings::DataModel::CSingletonHelper<bool>::_Notify<_lambda_78304fa1fdd572e2ab51f23c1c705858_>(
      &g_LockScreenBackgroundUpdatingSingleton,
      &string);
  }
  wil::ActivityBase<PersonalizeSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v16, 0);
  v8 = 0;
LABEL_11:
  PersonalizeSettingsTelemetry::LockScreenChooseBackgroundTypeSetValue::~LockScreenChooseBackgroundTypeSetValue((PersonalizeSettingsTelemetry::LockScreenChooseBackgroundTypeSetValue *)v16);
  return v8;
}

```

## disassembly

```asm
0x18013de10  mov     [rsp-8+arg_10], rbx
0x18013de15  push    rbp
0x18013de16  push    rsi
0x18013de17  push    rdi
0x18013de18  push    r14
0x18013de1a  push    r15
0x18013de1c  lea     rbp, [rsp-0A0h]
0x18013de24  sub     rsp, 1A0h
0x18013de2b  mov     rax, cs:__security_cookie
0x18013de32  xor     rax, rsp
0x18013de35  mov     [rbp+0C0h+var_30], rax
0x18013de3c  mov     rax, rdx
0x18013de3f  mov     rdi, rcx
0x18013de42  xor     edx, edx; length
0x18013de44  mov     rcx, rax; string
0x18013de47  call    cs:__imp_WindowsGetStringRawBuffer
0x18013de4e  nop     dword ptr [rax+rax+00h]
0x18013de53  mov     r15, rax
0x18013de56  lea     rdx, aLockscreenchoo_0; "LockScreenChooseBackgroundTypeSetValue"
0x18013de5d  lea     rcx, [rsp+1C0h+var_180]; struct wil::details::IFailureCallback *
0x18013de62  call    ??0?$ActivityBase@VPersonalizeSettingsLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<PersonalizeSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<PersonalizeSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18013de67  lea     rax, ??_7LockScreenChooseBackgroundTypeSetValue@PersonalizeSettingsTelemetry@@6B@; const PersonalizeSettingsTelemetry::LockScreenChooseBackgroundTypeSetValue::`vftable'
0x18013de6e  mov     [rsp+1C0h+var_180], rax
0x18013de73  mov     rdx, r15; unsigned __int16 *
0x18013de76  lea     rcx, [rsp+1C0h+var_180]; this
0x18013de7b  call    ?StartActivity@LockScreenChooseBackgroundTypeSetValue@PersonalizeSettingsTelemetry@@QEAAXPEBG@Z; PersonalizeSettingsTelemetry::LockScreenChooseBackgroundTypeSetValue::StartActivity(ushort const *)
0x18013de80  nop
0x18013de81  xor     r14d, r14d
0x18013de84  xor     esi, esi
0x18013de86  cmp     rsi, 3
0x18013de8a  jnb     loc_18013DF4C
0x18013de90  xor     ecx, ecx; string
0x18013de92  call    cs:__imp_WindowsDeleteString
0x18013de99  nop     dword ptr [rax+rax+00h]
0x18013de9e  mov     [rsp+1C0h+string], 0
0x18013dea7  lea     rcx, off_18038E540; "SystemSettings_Personalize_LockScreen_B"...
0x18013deae  lea     rdx, [rsp+1C0h+string]; HSTRING *
0x18013deb3  mov     rcx, [rcx+rsi*8]; this
0x18013deb7  call    ?GetResourceStringById@DataModel@SystemSettings@@YAJPEBGPEAPEAUHSTRING__@@@Z; SystemSettings::DataModel::GetResourceStringById(ushort const *,HSTRING__ * *)
0x18013debc  mov     ebx, eax
0x18013debe  test    eax, eax
0x18013dec0  js      short loc_18013DF1D
0x18013dec2  xor     edx, edx; length
0x18013dec4  mov     rcx, [rsp+1C0h+string]; string
0x18013dec9  call    cs:__imp_WindowsGetStringRawBuffer
0x18013ded0  nop     dword ptr [rax+rax+00h]
0x18013ded5  mov     [rsp+1C0h+bIgnoreCase], 1; bIgnoreCase
0x18013dedd  or      r9d, 0FFFFFFFFh; cchCount2
0x18013dee1  mov     r8, r15; lpString2
0x18013dee4  or      edx, r9d; cchCount1
0x18013dee7  mov     rcx, rax; lpString1
0x18013deea  call    cs:__imp_CompareStringOrdinal
0x18013def1  nop     dword ptr [rax+rax+00h]
0x18013def6  nop
0x18013def7  mov     rcx, rsi
0x18013defa  cmp     eax, 2
0x18013defd  cmovnz  rcx, r14
0x18013df01  mov     r14, rcx
0x18013df04  mov     rcx, [rsp+1C0h+string]; string
0x18013df09  call    cs:__imp_WindowsDeleteString
0x18013df10  nop     dword ptr [rax+rax+00h]
0x18013df15  inc     rsi
0x18013df18  jmp     loc_18013DE86
0x18013df1d  mov     rcx, [rbp+0C8h]; this
0x18013df24  mov     r9d, eax; char *
0x18013df27  lea     r8, aShellSystemset_10; "shell\\systemsettingsthreshold\\handler"...
0x18013df2e  mov     edx, 0CEh; void *
0x18013df33  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013df38  nop
0x18013df39  mov     rcx, [rsp+1C0h+string]; string
0x18013df3e  call    cs:__imp_WindowsDeleteString
0x18013df45  nop     dword ptr [rax+rax+00h]
0x18013df4a  jmp     short loc_18013DFB3
0x18013df4c  mov     [rdi+118h], r14d
0x18013df53  mov     dword ptr [rsp+1C0h+string], r14d
0x18013df58  lea     rdx, [rsp+1C0h+string]
0x18013df5d  lea     rcx, [rsp+1C0h+var_180]
0x18013df62  call    ??$LockScreenBackgroundTypeEvent@K@LockScreenChooseBackgroundTypeSetValue@PersonalizeSettingsTelemetry@@QEAAX$$QEAK@Z; PersonalizeSettingsTelemetry::LockScreenChooseBackgroundTypeSetValue::LockScreenBackgroundTypeEvent<ulong>(ulong &&)
0x18013df67  mov     rax, [rdi]
0x18013df6a  mov     rdx, rdi
0x18013df6d  mov     rcx, rdi
0x18013df70  mov     rax, [rax+0C0h]
0x18013df77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013df7c  cmp     dword ptr [rdi+118h], 0
0x18013df83  jnz     short loc_18013DFA5
0x18013df85  mov     [rsp+1C0h+var_190], 1
0x18013df8a  lea     rax, [rsp+1C0h+var_190]
0x18013df8f  mov     [rsp+1C0h+string], rax
0x18013df94  lea     rdx, [rsp+1C0h+string]
0x18013df99  lea     rcx, ?g_LockScreenBackgroundUpdatingSingleton@@3V?$CSingletonHelper@_N@DataModel@SystemSettings@@A; SystemSettings::DataModel::CSingletonHelper<bool> g_LockScreenBackgroundUpdatingSingleton
0x18013dfa0  call    ??$_Notify@V_lambda_78304fa1fdd572e2ab51f23c1c705858_@@@?$CSingletonHelper@_N@DataModel@SystemSettings@@AEAAXAEBV_lambda_78304fa1fdd572e2ab51f23c1c705858_@@@Z; SystemSettings::DataModel::CSingletonHelper<bool>::_Notify<_lambda_78304fa1fdd572e2ab51f23c1c705858_>(_lambda_78304fa1fdd572e2ab51f23c1c705858_ const &)
0x18013dfa5  xor     edx, edx
0x18013dfa7  lea     rcx, [rsp+1C0h+var_180]
0x18013dfac  call    ?Stop@?$ActivityBase@VPersonalizeSettingsLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<PersonalizeSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18013dfb1  xor     ebx, ebx
0x18013dfb3  lea     rcx, [rsp+1C0h+var_180]; this
0x18013dfb8  call    ??1LockScreenChooseBackgroundTypeSetValue@PersonalizeSettingsTelemetry@@QEAA@XZ; PersonalizeSettingsTelemetry::LockScreenChooseBackgroundTypeSetValue::~LockScreenChooseBackgroundTypeSetValue(void)
0x18013dfbd  mov     eax, ebx
0x18013dfbf  mov     rcx, [rbp+0C0h+var_30]
0x18013dfc6  xor     rcx, rsp; StackCookie
0x18013dfc9  call    __security_check_cookie
0x18013dfce  mov     rbx, [rsp+1C0h+arg_10]
0x18013dfd6  add     rsp, 1A0h
0x18013dfdd  pop     r15
0x18013dfdf  pop     r14
0x18013dfe1  pop     rdi
0x18013dfe2  pop     rsi
0x18013dfe3  pop     rbp
0x18013dfe4  retn
```
