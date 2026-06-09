# SystemSettings::PenSettings::DevicesPenSetActionModifierBase::SetValue(Windows::Foundation::IPropertyValue *)

- ea: `0x180030130`
- end: `0x18003066d`
- name: `?SetValue@DevicesPenSetActionModifierBase@PenSettings@SystemSettings@@UEAAJPEAUIPropertyValue@Foundation@Windows@@@Z`
- size: `1341`
- prototype: `__int64 __fastcall(SystemSettings::PenSettings::DevicesPenSetActionModifierBase *__hidden this, struct Windows::Foundation::IPropertyValue *)`
- caller_count: `0`
- callee_count: `28`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x1800030e0`
- `0x180005f0c`
- `0x18000a2bc`
- `0x1800102f4`
- `0x1800115d8`
- `0x180019a40`
- `0x180019b90`
- `0x180019fcc`
- `0x18001a378`
- `0x18001ba80`
- `0x18001cff8`
- `0x18001d854`
- `0x18001eb90`
- `0x180027dcc`
- `0x18002b2b4`
- `0x18002efec`
- `0x18002f030`
- `0x180030130`
- `0x18003114c`
- `0x18004c10c`
- `0x18004c334`
- `0x18004c494`
- `0x18004fe28`
- `0x180052518`
- `0x1800526d8`
- `0x180052e6c`
- `0x180052eec`
- `0x18005d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800305f9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800305f9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180030338`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180030338`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800301a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003027a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800303bf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180030491`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180030519`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180030638`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800301a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003027a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800303bf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180030491`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180030519`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180030638`

## string_xrefs

- `0x1800301cf`: `shellcommon\shell\settingshandlers\pen\lib\penbuttoncustomization.cpp`
- `0x180030255`: `shellcommon\shell\settingshandlers\pen\lib\penbuttoncustomization.cpp`
- `0x180030384`: `shellcommon\shell\settingshandlers\pen\lib\penbuttoncustomization.cpp`
- `0x180030448`: `shellcommon\shell\settingshandlers\pen\lib\penbuttoncustomization.cpp`
- `0x1800304d0`: `shellcommon\shell\settingshandlers\pen\lib\penbuttoncustomization.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5 #try_helpers=1
__int64 __fastcall SystemSettings::PenSettings::DevicesPenSetActionModifierBase::SetValue(
        SystemSettings::PenSettings::DevicesPenSetActionModifierBase *this,
        struct Windows::Foundation::IPropertyValue *a2)
{
  RTL_SRWLOCK *v4; // r15
  __int64 (__fastcall *v5)(struct Windows::Foundation::IPropertyValue *, HSTRING *); // rbx
  int v6; // eax
  const char *v7; // r9
  unsigned int v8; // ebx
  unsigned int v9; // r13d
  int v10; // eax
  unsigned int v11; // eax
  HKEY v12; // rcx
  unsigned int v13; // edi
  int v14; // eax
  int v16; // eax
  PCWSTR StringRawBuffer; // rax
  __int64 v18; // rbx
  struct SystemSettings::PenSettings::EnumerateModernAppsSingleton *Instance; // rax
  int ModernApps; // eax
  unsigned int v21; // edi
  __int64 v22; // rax
  int v23; // eax
  HKEY v24; // rcx
  unsigned int v25; // edi
  unsigned __int16 *v26; // r12
  int v27; // eax
  unsigned int v28; // edi
  int v29; // [rsp+20h] [rbp-D8h]
  HSTRING string; // [rsp+30h] [rbp-C8h] BYREF
  unsigned __int16 *v31; // [rsp+38h] [rbp-C0h] BYREF
  __int64 v32; // [rsp+40h] [rbp-B8h] BYREF
  RTL_SRWLOCK *v33; // [rsp+48h] [rbp-B0h] BYREF
  _QWORD v34[3]; // [rsp+50h] [rbp-A8h] BYREF
  __int128 v35; // [rsp+68h] [rbp-90h] BYREF
  __int64 v36; // [rsp+78h] [rbp-80h]
  unsigned __int16 *v37[4]; // [rsp+80h] [rbp-78h] BYREF
  _OWORD v38[2]; // [rsp+A0h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+0h]

  v31 = 0;
  v4 = (RTL_SRWLOCK *)((char *)this + 272);
  v33 = (RTL_SRWLOCK *)((char *)this + 272);
  SystemSettings::PenSettings::ActionTypeOptionManager::GetPrimitiveSpecificParameters(
    *((_DWORD *)this + 68),
    (unsigned int)&v31,
    0,
    0,
    0,
    0);
  string = 0;
  v5 = *(__int64 (__fastcall **)(struct Windows::Foundation::IPropertyValue *, HSTRING *))(*(_QWORD *)a2 + 152LL);
  WindowsDeleteString(0);
  string = 0;
  v6 = v5(a2, &string);
  v8 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x49A,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\pen\\lib\\penbuttoncustomization.cpp",
      (const char *)(unsigned int)v6,
      v29);
LABEL_7:
    WindowsDeleteString(string);
    return v8;
  }
  v38[0] = 0;
  v38[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v38[0]) = 0;
  v9 = 0;
  v10 = *((_DWORD *)this + 69);
  if ( v10 == 5 )
  {
    v11 = SystemSettings::PenSettings::FindEnumFromStringArray<enum SystemSettings::PenSettings::PenWorkspaceVerb,SystemSettings::PenSettings::PenWorkspaceVerbResourceMapping_>((SystemSettings::DataModel *)string);
    v13 = v11;
    if ( v11 != -1 )
    {
      v14 = SHRegSetDWORD(v12, v31, L"PenWorkspaceVerb", v11);
      v8 = v14;
      if ( v14 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x4A3,
          (unsigned int)"shellcommon\\shell\\settingshandlers\\pen\\lib\\penbuttoncustomization.cpp",
          (const char *)(unsigned int)v14,
          v29);
        std::wstring::_Tidy_deallocate(v38);
        goto LABEL_7;
      }
      v9 = v13;
    }
    SystemSettings::PenSettings::PenSettingsCacheSingleton::UpdateActionValueCachePenWorkspace(LODWORD(v4->Ptr), v13);
  }
  else if ( v10 == 2 )
  {
    memset(v34, 0, sizeof(v34));
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    v18 = -1;
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
      v34,
      StringRawBuffer,
      -1);
    v35 = 0;
    v36 = 0;
    Instance = SystemSettings::PenSettings::EnumerateModernAppsSingleton::GetInstance();
    ModernApps = SystemSettings::PenSettings::EnumerateModernAppsSingleton::GetModernApps(Instance, &v35);
    v21 = ModernApps;
    if ( ModernApps < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4AF,
        (unsigned int)"shellcommon\\shell\\settingshandlers\\pen\\lib\\penbuttoncustomization.cpp",
        (const char *)(unsigned int)ModernApps,
        v29);
      std::vector<SystemSettings::PenSettings::PenLaunchableAppInfo>::_Tidy(&v35);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v34);
      std::wstring::_Tidy_deallocate(v38);
      WindowsDeleteString(string);
      string = 0;
      return v21;
    }
    std::find_if_std::_Vector_iterator_std::_Vector_val_std::_Simple_types_SystemSettings::PenSettings::PenLaunchableAppInfo_______lambda_cca772b1c347ec56ec2000e90a3aec09___(
      &v32,
      v35,
      *((_QWORD *)&v35 + 1),
      v34);
    if ( v32 != *((_QWORD *)&v35 + 1) )
    {
      memset(v37, 0, 24);
      v22 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v32 + 32);
      v23 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
              v37,
              L"%s@%s",
              v22,
              v34[0]);
      v25 = v23;
      if ( v23 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x4BB,
          (unsigned int)"shellcommon\\shell\\settingshandlers\\pen\\lib\\penbuttoncustomization.cpp",
          (const char *)(unsigned int)v23,
          v29);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v37);
        std::vector<SystemSettings::PenSettings::PenLaunchableAppInfo>::_Tidy(&v35);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v34);
        std::wstring::_Tidy_deallocate(v38);
        WindowsDeleteString(string);
        string = 0;
        return v25;
      }
      v26 = v37[0];
      v27 = SHRegSetString(v24, v31, L"CustomAppId", v37[0]);
      v28 = v27;
      if ( v27 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x4BC,
          (unsigned int)"shellcommon\\shell\\settingshandlers\\pen\\lib\\penbuttoncustomization.cpp",
          (const char *)(unsigned int)v27,
          v29);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v37);
        std::vector<SystemSettings::PenSettings::PenLaunchableAppInfo>::_Tidy(&v35);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v34);
        std::wstring::_Tidy_deallocate(v38);
        WindowsDeleteString(string);
        string = 0;
        return v28;
      }
      SystemSettings::PenSettings::PenSettingsCacheSingleton::UpdateActionValueCache(LODWORD(v4->Ptr), v26);
      do
        ++v18;
      while ( v26[v18] );
      std::wstring::_Assign<unsigned short>(v38, v26);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v37);
    }
    std::vector<SystemSettings::PenSettings::PenLaunchableAppInfo>::_Tidy(&v35);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v34);
  }
  try
  {
    if ( *((_DWORD *)this + 69) == 5 )
    {
      std::_Integral_to_string<unsigned short,unsigned long>(v37, v9);
      std::wstring::operator=(v38, v37);
      std::wstring::_Tidy_deallocate(v37);
    }
    v16 = *((_DWORD *)this + 69);
    if ( v16 == 5 || v16 == 2 )
    {
      switch ( LODWORD(v4->Ptr) )
      {
        case 1:
          std::wstring::wstring(v37, v38);
          CloudDataPenSettings::SaveSingleClickShortcutAppAsync((SystemSettings::PenSettings::DevicesPenSetActionModifierBase *)((char *)this + 280));
          break;
        case 2:
          std::wstring::wstring(v37, v38);
          CloudDataPenSettings::SaveDoubleClickShortcutAppAsync((SystemSettings::PenSettings::DevicesPenSetActionModifierBase *)((char *)this + 280));
          break;
        case 3:
          std::wstring::wstring(v37, v38);
          CloudDataPenSettings::SaveLongPressShortcutAppAsync((SystemSettings::PenSettings::DevicesPenSetActionModifierBase *)((char *)this + 280));
          break;
      }
    }
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x4DF,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\pen\\lib\\penbuttoncustomization.cpp",
      v7);
    v4 = v33;
  }
  AcquireSRWLockShared(&SystemSettings::PenSettings::PenSettingsCacheSingleton::m_penSettingsCacheLock);
  v33 = &SystemSettings::PenSettings::PenSettingsCacheSingleton::m_penSettingsCacheLock;
  PenSettingsTelemetry::LogPenSettingsTelemetry(
    L"UserOverrideValue",
    LODWORD(v4->Ptr),
    &SystemSettings::PenSettings::PenSettingsCacheSingleton::m_penSettingsCache);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v33);
  std::wstring::_Tidy_deallocate(v38);
  WindowsDeleteString(string);
  return 0;
}

```

## disassembly

```asm
0x180030130  mov     [rsp+arg_10], rbx
0x180030135  mov     [rsp+arg_18], rsi
0x18003013a  push    rdi
0x18003013b  push    r12
0x18003013d  push    r13
0x18003013f  push    r14
0x180030141  push    r15
0x180030143  sub     rsp, 0D0h
0x18003014a  mov     rax, cs:__security_cookie
0x180030151  xor     rax, rsp
0x180030154  mov     [rsp+0F8h+var_38], rax
0x18003015c  mov     rdi, rdx
0x18003015f  mov     r14, rcx
0x180030162  xor     esi, esi
0x180030164  mov     [rsp+0F8h+var_C0], rsi
0x180030169  lea     r15, [rcx+110h]
0x180030170  mov     [rsp+0F8h+var_B0], r15
0x180030175  mov     [rsp+0F8h+var_D0], rsi
0x18003017a  mov     qword ptr [rsp+0F8h+var_D8], rsi; int
0x18003017f  xor     r9d, r9d
0x180030182  xor     r8d, r8d
0x180030185  lea     rdx, [rsp+0F8h+var_C0]
0x18003018a  mov     ecx, [r15]
0x18003018d  call    ?GetPrimitiveSpecificParameters@ActionTypeOptionManager@PenSettings@SystemSettings@@SAXW4PenClickType@@PEAPEBG1PEAPEAV?$vector@UPenActionTypeResourceMapping_@PenSettings@SystemSettings@@V?$allocator@UPenActionTypeResourceMapping_@PenSettings@SystemSettings@@@std@@@std@@11@Z; SystemSettings::PenSettings::ActionTypeOptionManager::GetPrimitiveSpecificParameters(PenClickType,ushort const * *,ushort const * *,std::vector<SystemSettings::PenSettings::PenActionTypeResourceMapping_> * *,ushort const * *,ushort const * *)
0x180030192  mov     [rsp+0F8h+string], rsi
0x180030197  mov     rax, [rdi]
0x18003019a  mov     rbx, [rax+98h]
0x1800301a1  xor     ecx, ecx; string
0x1800301a3  call    cs:__imp_WindowsDeleteString
0x1800301a9  mov     [rsp+0F8h+string], rsi
0x1800301ae  lea     rdx, [rsp+0F8h+string]
0x1800301b3  mov     rcx, rdi
0x1800301b6  mov     rax, rbx
0x1800301b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800301be  mov     ebx, eax
0x1800301c0  test    eax, eax
0x1800301c2  jns     short loc_1800301E5
0x1800301c4  mov     rcx, [rsp+0F8h]; this
0x1800301cc  mov     r9d, eax; char *
0x1800301cf  lea     r8, aShellcommonShe_7; "shellcommon\\shell\\settingshandlers\\p"...
0x1800301d6  mov     edx, 49Ah; void *
0x1800301db  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800301e0  jmp     loc_180030275
0x1800301e5  xorps   xmm0, xmm0
0x1800301e8  movups  [rsp+0F8h+var_58], xmm0
0x1800301f0  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1800301f8  movdqu  [rsp+0F8h+var_48], xmm1
0x180030201  mov     word ptr [rsp+0F8h+var_58], si
0x180030209  mov     r13d, esi
0x18003020c  mov     eax, [r14+114h]
0x180030213  cmp     eax, 5
0x180030216  jnz     loc_180030319
0x18003021c  mov     rcx, [rsp+0F8h+string]; this
0x180030221  call    ??$FindEnumFromStringArray@W4PenWorkspaceVerb@PenSettings@SystemSettings@@UPenWorkspaceVerbResourceMapping_@23@@PenSettings@SystemSettings@@YA?AW4PenWorkspaceVerb@01@PEAUHSTRING__@@PEBUPenWorkspaceVerbResourceMapping_@01@I@Z; SystemSettings::PenSettings::FindEnumFromStringArray<SystemSettings::PenSettings::PenWorkspaceVerb,SystemSettings::PenSettings::PenWorkspaceVerbResourceMapping_>(HSTRING__ *,SystemSettings::PenSettings::PenWorkspaceVerbResourceMapping_ const *,uint)
0x180030226  mov     edi, eax
0x180030228  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18003022c  cmp     eax, ebx
0x18003022e  jz      short loc_18003028A
0x180030230  mov     r9d, eax; unsigned int
0x180030233  lea     r8, aPenworkspaceve; "PenWorkspaceVerb"
0x18003023a  mov     rdx, [rsp+0F8h+var_C0]; unsigned __int16 *
0x18003023f  call    ?SHRegSetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; SHRegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x180030244  mov     ebx, eax
0x180030246  test    eax, eax
0x180030248  jns     short loc_180030287
0x18003024a  mov     rcx, [rsp+0F8h]; this
0x180030252  mov     r9d, eax; char *
0x180030255  lea     r8, aShellcommonShe_7; "shellcommon\\shell\\settingshandlers\\p"...
0x18003025c  mov     edx, 4A3h; void *
0x180030261  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180030266  nop
0x180030267  lea     rcx, [rsp+0F8h+var_58]
0x18003026f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180030274  nop
0x180030275  mov     rcx, [rsp+0F8h+string]; string
0x18003027a  call    cs:__imp_WindowsDeleteString
0x180030280  mov     eax, ebx
0x180030282  jmp     loc_180030640
0x180030287  mov     r13d, edi
0x18003028a  mov     edx, edi
0x18003028c  mov     ecx, [r15]
0x18003028f  call    ?UpdateActionValueCachePenWorkspace@PenSettingsCacheSingleton@PenSettings@SystemSettings@@SAXW4PenClickType@@K@Z; SystemSettings::PenSettings::PenSettingsCacheSingleton::UpdateActionValueCachePenWorkspace(PenClickType,ulong)
0x180030294  nop
0x180030295  cmp     dword ptr [r14+114h], 5
0x18003029d  jnz     short loc_1800302D1
0x18003029f  mov     edx, r13d
0x1800302a2  lea     rcx, [rsp+0F8h+var_78]
0x1800302aa  call    ??$_Integral_to_string@GK@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@K@Z; std::_Integral_to_string<ushort,ulong>(ulong)
0x1800302af  lea     rdx, [rsp+0F8h+var_78]
0x1800302b7  lea     rcx, [rsp+0F8h+var_58]
0x1800302bf  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800302c4  lea     rcx, [rsp+0F8h+var_78]
0x1800302cc  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800302d1  mov     eax, [r14+114h]
0x1800302d8  cmp     eax, 5
0x1800302db  jz      short loc_1800302E6
0x1800302dd  cmp     eax, 2
0x1800302e0  jnz     loc_1800305E6
0x1800302e6  cmp     dword ptr [r15], 1
0x1800302ea  jnz     loc_18003058F
0x1800302f0  lea     rdx, [rsp+0F8h+var_58]
0x1800302f8  lea     rcx, [rsp+0F8h+var_78]
0x180030300  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180030305  lea     rcx, [r14+118h]; struct wil::cloud_store *
0x18003030c  mov     rdx, rax
0x18003030f  call    ?SaveSingleClickShortcutAppAsync@CloudDataPenSettings@@QEAAXV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CloudDataPenSettings::SaveSingleClickShortcutAppAsync(std::wstring)
0x180030314  jmp     loc_1800305B9
0x180030319  cmp     eax, 2
0x18003031c  jnz     loc_180030295
0x180030322  mov     [rsp+0F8h+var_A8], rsi
0x180030327  mov     [rsp+0F8h+var_A0], rsi
0x18003032c  mov     [rsp+0F8h+var_98], rsi
0x180030331  xor     edx, edx; length
0x180030333  mov     rcx, [rsp+0F8h+string]; string
0x180030338  call    cs:__imp_WindowsGetStringRawBuffer
0x18003033e  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180030342  mov     r8, rbx
0x180030345  mov     rdx, rax
0x180030348  lea     rcx, [rsp+0F8h+var_A8]
0x18003034d  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x180030352  nop
0x180030353  xorps   xmm0, xmm0
0x180030356  movdqu  [rsp+0F8h+var_90], xmm0
0x18003035c  mov     [rsp+0F8h+var_80], rsi
0x180030361  call    ?GetInstance@EnumerateModernAppsSingleton@PenSettings@SystemSettings@@SAAEAV123@XZ; SystemSettings::PenSettings::EnumerateModernAppsSingleton::GetInstance(void)
0x180030366  lea     rdx, [rsp+0F8h+var_90]
0x18003036b  mov     rcx, rax
0x18003036e  call    ?GetModernApps@EnumerateModernAppsSingleton@PenSettings@SystemSettings@@QEAAJPEAV?$vector@UPenLaunchableAppInfo@PenSettings@SystemSettings@@V?$allocator@UPenLaunchableAppInfo@PenSettings@SystemSettings@@@std@@@std@@@Z; SystemSettings::PenSettings::EnumerateModernAppsSingleton::GetModernApps(std::vector<SystemSettings::PenSettings::PenLaunchableAppInfo> *)
0x180030373  mov     edi, eax
0x180030375  test    eax, eax
0x180030377  jns     short loc_1800303D1
0x180030379  mov     rcx, [rsp+0F8h]; this
0x180030381  mov     r9d, eax; char *
0x180030384  lea     r8, aShellcommonShe_7; "shellcommon\\shell\\settingshandlers\\p"...
0x18003038b  mov     edx, 4AFh; void *
0x180030390  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180030395  nop
0x180030396  lea     rcx, [rsp+0F8h+var_90]
0x18003039b  call    ?_Tidy@?$vector@UPenLaunchableAppInfo@PenSettings@SystemSettings@@V?$allocator@UPenLaunchableAppInfo@PenSettings@SystemSettings@@@std@@@std@@AEAAXXZ; std::vector<SystemSettings::PenSettings::PenLaunchableAppInfo>::_Tidy(void)
0x1800303a0  nop
0x1800303a1  lea     rcx, [rsp+0F8h+var_A8]
0x1800303a6  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800303ab  nop
0x1800303ac  lea     rcx, [rsp+0F8h+var_58]
0x1800303b4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800303b9  nop
0x1800303ba  mov     rcx, [rsp+0F8h+string]; string
0x1800303bf  call    cs:__imp_WindowsDeleteString
0x1800303c5  mov     [rsp+0F8h+string], rsi
0x1800303ca  mov     eax, edi
0x1800303cc  jmp     loc_180030640
0x1800303d1  lea     r9, [rsp+0F8h+var_A8]
0x1800303d6  mov     r8, qword ptr [rsp+0F8h+var_90+8]
0x1800303db  mov     rdx, qword ptr [rsp+0F8h+var_90]
0x1800303e0  lea     rcx, [rsp+0F8h+var_B8]
0x1800303e5  call    std__find_if_std___Vector_iterator_std___Vector_val_std___Simple_types_SystemSettings__PenSettings__PenLaunchableAppInfo_______lambda_cca772b1c347ec56ec2000e90a3aec09___
0x1800303ea  mov     rcx, [rsp+0F8h+var_B8]
0x1800303ef  cmp     rcx, qword ptr [rsp+0F8h+var_90+8]
0x1800303f4  jz      loc_180030562
0x1800303fa  mov     [rsp+0F8h+var_78], rsi
0x180030402  mov     [rsp+0F8h+var_70], rsi
0x18003040a  mov     [rsp+0F8h+var_68], rsi
0x180030412  add     rcx, 20h ; ' '
0x180030416  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003041b  mov     r9, [rsp+0F8h+var_A8]
0x180030420  mov     r8, rax
0x180030423  lea     rdx, aSS_0; "%s@%s"
0x18003042a  lea     rcx, [rsp+0F8h+var_78]
0x180030432  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x180030437  mov     edi, eax
0x180030439  test    eax, eax
0x18003043b  jns     short loc_1800304A3
0x18003043d  mov     rcx, [rsp+0F8h]; this
0x180030445  mov     r9d, eax; char *
0x180030448  lea     r8, aShellcommonShe_7; "shellcommon\\shell\\settingshandlers\\p"...
0x18003044f  mov     edx, 4BBh; void *
0x180030454  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180030459  nop
0x18003045a  lea     rcx, [rsp+0F8h+var_78]
0x180030462  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180030467  nop
0x180030468  lea     rcx, [rsp+0F8h+var_90]
0x18003046d  call    ?_Tidy@?$vector@UPenLaunchableAppInfo@PenSettings@SystemSettings@@V?$allocator@UPenLaunchableAppInfo@PenSettings@SystemSettings@@@std@@@std@@AEAAXXZ; std::vector<SystemSettings::PenSettings::PenLaunchableAppInfo>::_Tidy(void)
0x180030472  nop
0x180030473  lea     rcx, [rsp+0F8h+var_A8]
0x180030478  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18003047d  nop
0x18003047e  lea     rcx, [rsp+0F8h+var_58]
0x180030486  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003048b  nop
0x18003048c  mov     rcx, [rsp+0F8h+string]; string
0x180030491  call    cs:__imp_WindowsDeleteString
0x180030497  mov     [rsp+0F8h+string], rsi
0x18003049c  mov     eax, edi
0x18003049e  jmp     loc_180030640
0x1800304a3  mov     r12, [rsp+0F8h+var_78]
0x1800304ab  mov     r9, r12; unsigned __int16 *
0x1800304ae  lea     r8, pszValue; "CustomAppId"
0x1800304b5  mov     rdx, [rsp+0F8h+var_C0]; unsigned __int16 *
0x1800304ba  call    ?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x1800304bf  mov     edi, eax
0x1800304c1  test    eax, eax
0x1800304c3  jns     short loc_18003052B
0x1800304c5  mov     rcx, [rsp+0F8h]; this
0x1800304cd  mov     r9d, eax; char *
0x1800304d0  lea     r8, aShellcommonShe_7; "shellcommon\\shell\\settingshandlers\\p"...
0x1800304d7  mov     edx, 4BCh; void *
0x1800304dc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800304e1  nop
0x1800304e2  lea     rcx, [rsp+0F8h+var_78]
0x1800304ea  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800304ef  nop
0x1800304f0  lea     rcx, [rsp+0F8h+var_90]
0x1800304f5  call    ?_Tidy@?$vector@UPenLaunchableAppInfo@PenSettings@SystemSettings@@V?$allocator@UPenLaunchableAppInfo@PenSettings@SystemSettings@@@std@@@std@@AEAAXXZ; std::vector<SystemSettings::PenSettings::PenLaunchableAppInfo>::_Tidy(void)
0x1800304fa  nop
0x1800304fb  lea     rcx, [rsp+0F8h+var_A8]
0x180030500  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180030505  nop
0x180030506  lea     rcx, [rsp+0F8h+var_58]
0x18003050e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180030513  nop
0x180030514  mov     rcx, [rsp+0F8h+string]; string
0x180030519  call    cs:__imp_WindowsDeleteString
0x18003051f  mov     [rsp+0F8h+string], rsi
0x180030524  mov     eax, edi
0x180030526  jmp     loc_180030640
0x18003052b  mov     rdx, r12
0x18003052e  mov     ecx, [r15]
0x180030531  call    ?UpdateActionValueCache@PenSettingsCacheSingleton@PenSettings@SystemSettings@@SAXW4PenClickType@@PEBG@Z; SystemSettings::PenSettings::PenSettingsCacheSingleton::UpdateActionValueCache(PenClickType,ushort const *)
0x180030536  inc     rbx
0x180030539  cmp     [r12+rbx*2], si
0x18003053e  jnz     short loc_180030536
0x180030540  mov     r8, rbx
0x180030543  mov     rdx, r12
0x180030546  lea     rcx, [rsp+0F8h+var_58]
0x18003054e  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180030553  nop
0x180030554  lea     rcx, [rsp+0F8h+var_78]
0x18003055c  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180030561  nop
0x180030562  lea     rcx, [rsp+0F8h+var_90]
0x180030567  call    ?_Tidy@?$vector@UPenLaunchableAppInfo@PenSettings@SystemSettings@@V?$allocator@UPenLaunchableAppInfo@PenSettings@SystemSettings@@@std@@@std@@AEAAXXZ; std::vector<SystemSettings::PenSettings::PenLaunchableAppInfo>::_Tidy(void)
0x18003056c  nop
0x18003056d  lea     rcx, [rsp+0F8h+var_A8]
0x180030572  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180030577  jmp     loc_180030295
0x18003057c  lea     rcx, [rsp+0F8h+var_A8]
0x180030581  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180030586  mov     esi, dword ptr [rsp+0F8h+var_C0]
0x18003058a  jmp     loc_180030625
0x18003058f  cmp     dword ptr [r15], 2
0x180030593  jnz     short loc_1800305BB
0x180030595  lea     rdx, [rsp+0F8h+var_58]
0x18003059d  lea     rcx, [rsp+0F8h+var_78]
0x1800305a5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800305aa  lea     rcx, [r14+118h]; struct wil::cloud_store *
0x1800305b1  mov     rdx, rax
0x1800305b4  call    ?SaveDoubleClickShortcutAppAsync@CloudDataPenSettings@@QEAAXV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CloudDataPenSettings::SaveDoubleClickShortcutAppAsync(std::wstring)
0x1800305b9  jmp     short loc_1800305E6
0x1800305bb  cmp     dword ptr [r15], 3
0x1800305bf  jnz     short loc_1800305E6
0x1800305c1  lea     rdx, [rsp+0F8h+var_58]
0x1800305c9  lea     rcx, [rsp+0F8h+var_78]
0x1800305d1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800305d6  lea     rcx, [r14+118h]; struct wil::cloud_store *
0x1800305dd  mov     rdx, rax
0x1800305e0  call    ?SaveLongPressShortcutAppAsync@CloudDataPenSettings@@QEAAXV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CloudDataPenSettings::SaveLongPressShortcutAppAsync(std::wstring)
0x1800305e5  nop
0x1800305e6  jmp     short loc_1800305EF
0x1800305e8  xor     esi, esi
0x1800305ea  mov     r15, [rsp+0F8h+var_B0]
0x1800305ef  lea     rbx, ?m_penSettingsCacheLock@PenSettingsCacheSingleton@PenSettings@SystemSettings@@0Vsrwlock@wil@@A; wil::srwlock SystemSettings::PenSettings::PenSettingsCacheSingleton::m_penSettingsCacheLock
0x1800305f6  mov     rcx, rbx; SRWLock
0x1800305f9  call    cs:__imp_AcquireSRWLockShared
0x1800305ff  mov     [rsp+0F8h+var_B0], rbx
0x180030604  lea     r8, ?m_penSettingsCache@PenSettingsCacheSingleton@PenSettings@SystemSettings@@0UPenSettingsCache@23@A; SystemSettings::PenSettings::PenSettingsCache SystemSettings::PenSettings::PenSettingsCacheSingleton::m_penSettingsCache
0x18003060b  mov     edx, [r15]
0x18003060e  lea     rcx, aUseroverrideva; "UserOverrideValue"
0x180030615  call    ?LogPenSettingsTelemetry@PenSettingsTelemetry@@SAXPEBGW4PenClickType@@AEAUPenSettingsCache@PenSettings@SystemSettings@@@Z; PenSettingsTelemetry::LogPenSettingsTelemetry(ushort const *,PenClickType,SystemSettings::PenSettings::PenSettingsCache &)
0x18003061a  lea     rcx, [rsp+0F8h+var_B0]
0x18003061f  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180030624  nop
0x180030625  lea     rcx, [rsp+0F8h+var_58]
0x18003062d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180030632  nop
0x180030633  mov     rcx, [rsp+0F8h+string]; string
0x180030638  call    cs:__imp_WindowsDeleteString
0x18003063e  mov     eax, esi
0x180030640  mov     rcx, [rsp+0F8h+var_38]
0x180030648  xor     rcx, rsp; StackCookie
0x18003064b  call    __security_check_cookie
0x180030650  lea     r11, [rsp+0F8h+var_28]
0x180030658  mov     rbx, [r11+40h]
0x18003065c  mov     rsi, [r11+48h]
0x180030660  mov     rsp, r11
0x180030663  pop     r15
0x180030665  pop     r14
0x180030667  pop     r13
0x180030669  pop     r12
0x18003066b  pop     rdi
  ... truncated ...
```
