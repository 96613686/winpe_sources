# SystemSettings::DataModel::CPITRSnapshotRetention::SetValue(HSTRING__ *)

- ea: `0x180103070`
- end: `0x18010355f`
- name: `?SetValue@CPITRSnapshotRetention@DataModel@SystemSettings@@UEAAJPEAUHSTRING__@@@Z`
- size: `1263`
- prototype: `__int64 __fastcall(SystemSettings::DataModel::CPITRSnapshotRetention *__hidden this, HSTRING)`
- caller_count: `0`
- callee_count: `18`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x18000c840`
- `0x180013170`
- `0x180013d14`
- `0x180019a20`
- `0x18001a64c`
- `0x18001ecfc`
- `0x180021398`
- `0x180021640`
- `0x1800234f8`
- `0x18002373c`
- `0x18004528c`
- `0x18004d1ac`
- `0x1800886b0`
- `0x1800ce7ec`
- `0x1800ff9dc`
- `0x1800ffb04`
- `0x180103070`
- `0x18010b7e0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x18010324d`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x18010324d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801030ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801032f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010339c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180103431`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801030ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801032f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010339c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180103431`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180103144`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801031cd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010328a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801034de`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010351a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180103144`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801031cd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010328a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801034de`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010351a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18010318c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801031e9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18010318c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801031e9`
- `WDSCORE!WdsSetupLogMessageW` at `0x180103134`
- `WDSCORE!WdsSetupLogMessageW` at `0x18010336f`
- `WDSCORE!WdsSetupLogMessageW` at `0x180103416`
- `WDSCORE!WdsSetupLogMessageW` at `0x1801034a4`
- `WDSCORE!WdsSetupLogMessageW` at `0x180103134`
- `WDSCORE!WdsSetupLogMessageW` at `0x18010336f`
- `WDSCORE!WdsSetupLogMessageW` at `0x180103416`
- `WDSCORE!WdsSetupLogMessageW` at `0x1801034a4`
- `WDSCORE!CurrentIP` at `0x1801030c8`
- `WDSCORE!CurrentIP` at `0x180103303`
- `WDSCORE!CurrentIP` at `0x1801033aa`
- `WDSCORE!CurrentIP` at `0x18010343f`
- `WDSCORE!CurrentIP` at `0x1801030c8`
- `WDSCORE!CurrentIP` at `0x180103303`
- `WDSCORE!CurrentIP` at `0x1801033aa`
- `WDSCORE!CurrentIP` at `0x18010343f`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall SystemSettings::DataModel::CPITRSnapshotRetention::SetValue(
        SystemSettings::DataModel::CPITRSnapshotRetention *this,
        char *a2)
{
  DWORD LastError; // edi
  __int64 v5; // rbx
  struct tagLOG_PARTIAL_MSG *v6; // rax
  int v7; // esi
  HSTRING *v8; // r8
  int ResourceStringById; // eax
  unsigned int v10; // ebx
  unsigned int v11; // edi
  HSTRING v12; // rbx
  const unsigned __int16 *StringRawBuffer; // rax
  int v14; // eax
  const unsigned __int16 *v15; // r8
  unsigned int v16; // edi
  PCWSTR v17; // rax
  __int64 v18; // rax
  int v19; // esi
  int v20; // eax
  const unsigned __int16 *v21; // r8
  struct tagLOG_PARTIAL_MSG *v22; // rax
  struct tagLOG_PARTIAL_MSG *v23; // rax
  __int64 v24; // rdx
  __int64 v25; // rcx
  __int64 v26; // r8
  __int64 v27; // r9
  struct tagLOG_PARTIAL_MSG *v28; // rax
  int v30; // [rsp+20h] [rbp-E0h]
  int v31; // [rsp+20h] [rbp-E0h]
  int v32; // [rsp+20h] [rbp-E0h]
  __int64 v33; // [rsp+38h] [rbp-C8h]
  DWORD v34; // [rsp+40h] [rbp-C0h]
  int v35; // [rsp+50h] [rbp-B0h]
  HSTRING string; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v37[8]; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v38[3]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v39[40]; // [rsp+88h] [rbp-78h] BYREF
  HSTRING__ v40; // [rsp+B0h] [rbp-50h] BYREF
  struct HWND__ v41; // [rsp+2C0h] [rbp+1C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+508h] [rbp+408h]

  wil::AcquireSRWLockExclusive(v37, (char *)this + 240);
  LastError = GetLastError();
  v5 = ((__int64 (*)(void))CurrentIP)();
  v6 = ConstructPartialMsgW(
         0x4000000u,
         "SystemSettings::DataModel::CPITRSnapshotRetention::SetValue: Setting PITR snapshot retention to %s",
         a2);
  v35 = 0;
  v34 = LastError;
  v33 = v5;
  WdsSetupLogMessageW(v6, 0, L"D", 0);
  v7 = 0;
  while ( 1 )
  {
    WindowsDeleteString(0);
    string = 0;
    ResourceStringById = SystemSettings::DataModel::GetResourceStringById(
                           (SystemSettings::DataModel *)L"SystemSettings_Misc_PointInTimeRestore_SnapshotRetention_HourlyValue",
                           &string,
                           v8);
    v10 = ResourceStringById;
    if ( ResourceStringById < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3F8,
        (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\restore\\pointintimerestore.cpp",
        (const char *)(unsigned int)ResourceStringById,
        1002);
      WindowsDeleteString(string);
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(v37);
      return v10;
    }
    v11 = dword_180306138[v7];
    v12 = string;
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    v14 = StringCchPrintfW((unsigned __int16 *)&v40, 0x104u, StringRawBuffer, v11);
    v16 = v14;
    if ( v14 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3FC,
        (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\restore\\pointintimerestore.cpp",
        (const char *)(unsigned int)v14,
        1002);
      WindowsDeleteString(v12);
      goto LABEL_18;
    }
    if ( SystemSettings::DataModel::IsHstringEqual((SystemSettings::DataModel *)a2, &v40, v15) )
      break;
    WindowsDeleteString(v12);
    if ( (unsigned int)++v7 >= 5 )
    {
      v17 = WindowsGetStringRawBuffer((HSTRING)a2, 0);
      std::wstring::wstring(v39, v17);
      RestoreSplitDelimitedString(v38, v39);
      std::wstring::_Tidy_deallocate(v39);
      if ( v38[1] - v38[0] == 64 && !(unsigned __int8)std::operator!=<unsigned short>(v38[0] + 64LL, L"minutes") )
      {
        v18 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v38[0]);
        v19 = _o__wtoi(v18);
        std::vector<std::wstring>::_Tidy(v38);
        goto LABEL_11;
      }
      std::vector<std::wstring>::_Tidy(v38);
      v16 = -2147024809;
LABEL_18:
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(v37);
      return v16;
    }
  }
  v19 = 60 * dword_180306138[v7];
  WindowsDeleteString(v12);
LABEL_11:
  v30 = v19;
  v20 = StringCchPrintfW(
          (unsigned __int16 *)&v41,
          0x104u,
          L"%s SetSnapshotRetention %d",
          L"PointInTimeRestore",
          v30,
          L"shell\\systemsettingsthreshold\\handlers\\internal\\restore\\pointintimerestore.cpp",
          L"SystemSettings::DataModel::CPITRSnapshotRetention::SetValue",
          v33,
          v34,
          0,
          v35);
  v16 = v20;
  if ( v20 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x41B,
      (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\restore\\pointintimerestore.cpp",
      (const char *)(unsigned int)v20,
      v31);
    goto LABEL_18;
  }
  if ( (int)SystemSettings::DataModel::ExecuteAdminFlowWait(0, &v41, v21) >= 0 )
  {
    GetLastError();
    ((void (*)(void))CurrentIP)();
    v23 = ConstructPartialMsgW(
            0x4000000u,
            "SystemSettings::DataModel::CPITRSnapshotRetention::SetValue: Successfully set PITR snapshot retention to %d minutes",
            v19);
    v32 = 1062;
    WdsSetupLogMessageW(v23, 0, L"D", 0);
    *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 11) + 24LL) + 244LL) = v19;
  }
  else
  {
    GetLastError();
    ((void (*)(void))CurrentIP)();
    v22 = ConstructPartialMsgW(
            0x2000000u,
            "SystemSettings::DataModel::CPITRSnapshotRetention::SetValue: Failed to set PITR snapshot retention to %d minutes",
            v19);
    v32 = 1055;
    WdsSetupLogMessageW(v22, 0, L"D", 0);
    SystemSettings::DataModel::CPITRSingleton::EvaluateSettingState(*(SystemSettings::DataModel::CPITRSingleton **)(*((_QWORD *)this + 11) + 24LL));
    SystemSettings::DataModel::CSettingBase::OnValueChanged(this, L"Value");
  }
  GetLastError();
  CurrentIP(
    v25,
    v24,
    v26,
    v27,
    v32,
    L"shell\\systemsettingsthreshold\\handlers\\internal\\restore\\pointintimerestore.cpp",
    L"SystemSettings::DataModel::CPITRSnapshotRetention::SetValue");
  v28 = ConstructPartialMsgW(
          0x4000000u,
          "SystemSettings::DataModel::CPITRSnapshotRetention::SetValue: Setting PITR snapshot retention to %s",
          a2);
  WdsSetupLogMessageW(v28, 0, L"D", 0);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(v37);
  return 0;
}

```

## disassembly

```asm
0x180103070  mov     [rsp-8+arg_10], rbx
0x180103075  mov     [rsp-8+arg_18], rsi
0x18010307a  push    rbp
0x18010307b  push    rdi
0x18010307c  push    r13
0x18010307e  push    r14
0x180103080  push    r15
0x180103082  lea     rbp, [rsp-3E0h]
0x18010308a  sub     rsp, 4E0h
0x180103091  mov     rax, cs:__security_cookie
0x180103098  xor     rax, rsp
0x18010309b  mov     [rbp+400h+var_30], rax
0x1801030a2  mov     r15, rdx
0x1801030a5  mov     r13, rcx
0x1801030a8  lea     rdx, [rcx+0F0h]
0x1801030af  lea     rcx, [rsp+500h+var_498]
0x1801030b4  call    ?AcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x1801030b9  nop
0x1801030ba  call    cs:__imp_GetLastError
0x1801030c1  nop     dword ptr [rax+rax+00h]
0x1801030c6  mov     edi, eax
0x1801030c8  call    cs:__imp_CurrentIP
0x1801030cf  nop     dword ptr [rax+rax+00h]
0x1801030d4  mov     rbx, rax
0x1801030d7  mov     r8, r15
0x1801030da  lea     rdx, aSystemsettings_774; "SystemSettings::DataModel::CPITRSnapsho"...
0x1801030e1  mov     ecx, 4000000h; unsigned int
0x1801030e6  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1801030eb  mov     [rsp+500h+var_4B0], 0
0x1801030f3  mov     [rsp+500h+var_4B8], 0
0x1801030fc  mov     [rsp+500h+var_4C0], edi
0x180103100  mov     [rsp+500h+var_4C8], rbx
0x180103105  lea     rcx, aSystemsettings_1271; "SystemSettings::DataModel::CPITRSnapsho"...
0x18010310c  mov     [rsp+500h+var_4D0], rcx
0x180103111  lea     rcx, aShellSystemset_101; "shell\\systemsettingsthreshold\\handler"...
0x180103118  mov     [rsp+500h+var_4D8], rcx
0x18010311d  mov     [rsp+500h+var_4E0], 3EAh; int
0x180103125  xor     r9d, r9d
0x180103128  lea     r8, aD_2; "D"
0x18010312f  xor     edx, edx
0x180103131  mov     rcx, rax
0x180103134  call    cs:__imp_WdsSetupLogMessageW
0x18010313b  nop     dword ptr [rax+rax+00h]
0x180103140  xor     esi, esi
0x180103142  xor     ecx, ecx; string
0x180103144  call    cs:__imp_WindowsDeleteString
0x18010314b  nop     dword ptr [rax+rax+00h]
0x180103150  mov     [rsp+500h+string], 0
0x180103159  lea     rdx, [rsp+500h+string]; HSTRING *
0x18010315e  lea     rcx, aSystemsettings_1241; "SystemSettings_Misc_PointInTimeRestore_"...
0x180103165  call    ?GetResourceStringById@DataModel@SystemSettings@@YAJPEBGPEAPEAUHSTRING__@@@Z; SystemSettings::DataModel::GetResourceStringById(ushort const *,HSTRING__ * *)
0x18010316a  mov     ebx, eax
0x18010316c  test    eax, eax
0x18010316e  js      loc_1801034F9
0x180103174  movsxd  r14, esi
0x180103177  lea     rax, dword_180306138
0x18010317e  mov     edi, [rax+r14*4]
0x180103182  xor     edx, edx; length
0x180103184  mov     rbx, [rsp+500h+string]
0x180103189  mov     rcx, rbx; string
0x18010318c  call    cs:__imp_WindowsGetStringRawBuffer
0x180103193  nop     dword ptr [rax+rax+00h]
0x180103198  mov     r9d, edi
0x18010319b  mov     r8, rax; unsigned __int16 *
0x18010319e  mov     edx, 104h; unsigned __int64
0x1801031a3  lea     rcx, [rbp+400h+var_450]; unsigned __int16 *
0x1801031a7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1801031ac  mov     edi, eax
0x1801031ae  test    eax, eax
0x1801031b0  js      loc_1801034BF
0x1801031b6  lea     rdx, [rbp+400h+var_450]; HSTRING
0x1801031ba  mov     rcx, r15; this
0x1801031bd  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x1801031c2  test    al, al
0x1801031c4  jnz     loc_18010327B
0x1801031ca  mov     rcx, rbx; string
0x1801031cd  call    cs:__imp_WindowsDeleteString
0x1801031d4  nop     dword ptr [rax+rax+00h]
0x1801031d9  inc     esi
0x1801031db  cmp     esi, 5
0x1801031de  jb      loc_180103142
0x1801031e4  xor     edx, edx; length
0x1801031e6  mov     rcx, r15; string
0x1801031e9  call    cs:__imp_WindowsGetStringRawBuffer
0x1801031f0  nop     dword ptr [rax+rax+00h]
0x1801031f5  mov     rdx, rax
0x1801031f8  lea     rcx, [rbp+400h+var_478]
0x1801031fc  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180103201  nop
0x180103202  lea     rdx, [rbp+400h+var_478]
0x180103206  lea     rcx, [rsp+500h+var_490]
0x18010320b  call    ?RestoreSplitDelimitedString@@YA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@G@Z; RestoreSplitDelimitedString(std::wstring const &,ushort)
0x180103210  nop
0x180103211  lea     rcx, [rbp+400h+var_478]
0x180103215  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010321a  mov     rcx, [rsp+500h+var_490]
0x18010321f  mov     rax, [rsp+500h+var_488]
0x180103224  sub     rax, rcx
0x180103227  cmp     rax, 40h ; '@'
0x18010322b  jnz     short loc_180103267
0x18010322d  add     rcx, rax
0x180103230  lea     rdx, aMinutes; "minutes"
0x180103237  call    ??$?9GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEBG@Z; std::operator!=<ushort>(std::wstring const &,ushort const * const)
0x18010323c  test    al, al
0x18010323e  jnz     short loc_180103267
0x180103240  mov     rcx, [rsp+500h+var_490]
0x180103245  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18010324a  mov     rcx, rax
0x18010324d  call    cs:__imp__o__wtoi
0x180103254  nop     dword ptr [rax+rax+00h]
0x180103259  mov     esi, eax
0x18010325b  lea     rcx, [rsp+500h+var_490]
0x180103260  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180103265  jmp     short loc_180103296
0x180103267  lea     rcx, [rsp+500h+var_490]
0x18010326c  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180103271  mov     edi, 80070057h
0x180103276  jmp     loc_1801034EB
0x18010327b  lea     rax, dword_180306138
0x180103282  imul    esi, [rax+r14*4], 3Ch ; '<'
0x180103287  mov     rcx, rbx; string
0x18010328a  call    cs:__imp_WindowsDeleteString
0x180103291  nop     dword ptr [rax+rax+00h]
0x180103296  mov     [rsp+500h+var_4E0], esi; int
0x18010329a  lea     r9, aPointintimeres; "PointInTimeRestore"
0x1801032a1  lea     r8, aSSetsnapshotre; "%s SetSnapshotRetention %d"
0x1801032a8  mov     edx, 104h; unsigned __int64
0x1801032ad  lea     rcx, [rbp+400h+var_240]; unsigned __int16 *
0x1801032b4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1801032b9  mov     edi, eax
0x1801032bb  test    eax, eax
0x1801032bd  jns     short loc_1801032DF
0x1801032bf  mov     rcx, [rbp+408h]; this
0x1801032c6  mov     r9d, eax; char *
0x1801032c9  lea     r8, aShellSystemset_19; "shell\\systemsettingsthreshold\\handler"...
0x1801032d0  mov     edx, 41Bh; void *
0x1801032d5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801032da  jmp     loc_1801034EB
0x1801032df  lea     rdx, [rbp+400h+var_240]; HWND
0x1801032e6  xor     ecx, ecx; this
0x1801032e8  call    ?ExecuteAdminFlowWait@DataModel@SystemSettings@@YAJPEAUHWND__@@PEBG@Z; SystemSettings::DataModel::ExecuteAdminFlowWait(HWND__ *,ushort const *)
0x1801032ed  test    eax, eax
0x1801032ef  jns     loc_18010339C
0x1801032f5  call    cs:__imp_GetLastError
0x1801032fc  nop     dword ptr [rax+rax+00h]
0x180103301  mov     edi, eax
0x180103303  call    cs:__imp_CurrentIP
0x18010330a  nop     dword ptr [rax+rax+00h]
0x18010330f  mov     rbx, rax
0x180103312  mov     r8d, esi
0x180103315  lea     rdx, aSystemsettings_386; "SystemSettings::DataModel::CPITRSnapsho"...
0x18010331c  mov     ecx, 2000000h; unsigned int
0x180103321  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180103326  mov     [rsp+500h+var_4B0], 0
0x18010332e  mov     [rsp+500h+var_4B8], 0
0x180103337  mov     [rsp+500h+var_4C0], edi
0x18010333b  mov     [rsp+500h+var_4C8], rbx
0x180103340  lea     r14, aSystemsettings_1271; "SystemSettings::DataModel::CPITRSnapsho"...
0x180103347  mov     [rsp+500h+var_4D0], r14
0x18010334c  lea     rcx, aShellSystemset_101; "shell\\systemsettingsthreshold\\handler"...
0x180103353  mov     [rsp+500h+var_4D8], rcx
0x180103358  mov     [rsp+500h+var_4E0], 41Fh
0x180103360  xor     r9d, r9d
0x180103363  lea     r8, aD_2; "D"
0x18010336a  xor     edx, edx
0x18010336c  mov     rcx, rax
0x18010336f  call    cs:__imp_WdsSetupLogMessageW
0x180103376  nop     dword ptr [rax+rax+00h]
0x18010337b  mov     rcx, [r13+58h]
0x18010337f  mov     rcx, [rcx+18h]; this
0x180103383  call    ?EvaluateSettingState@CPITRSingleton@DataModel@SystemSettings@@QEAAJXZ; SystemSettings::DataModel::CPITRSingleton::EvaluateSettingState(void)
0x180103388  lea     rdx, aValue_0; "Value"
0x18010338f  mov     rcx, r13; this
0x180103392  call    ?OnValueChanged@CSettingBase@DataModel@SystemSettings@@QEAAXPEBG@Z; SystemSettings::DataModel::CSettingBase::OnValueChanged(ushort const *)
0x180103397  jmp     loc_180103431
0x18010339c  call    cs:__imp_GetLastError
0x1801033a3  nop     dword ptr [rax+rax+00h]
0x1801033a8  mov     edi, eax
0x1801033aa  call    cs:__imp_CurrentIP
0x1801033b1  nop     dword ptr [rax+rax+00h]
0x1801033b6  mov     rbx, rax
0x1801033b9  mov     r8d, esi
0x1801033bc  lea     rdx, aSystemsettings_177; "SystemSettings::DataModel::CPITRSnapsho"...
0x1801033c3  mov     ecx, 4000000h; unsigned int
0x1801033c8  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1801033cd  mov     [rsp+500h+var_4B0], 0
0x1801033d5  mov     [rsp+500h+var_4B8], 0
0x1801033de  mov     [rsp+500h+var_4C0], edi
0x1801033e2  mov     [rsp+500h+var_4C8], rbx
0x1801033e7  lea     r14, aSystemsettings_1271; "SystemSettings::DataModel::CPITRSnapsho"...
0x1801033ee  mov     [rsp+500h+var_4D0], r14
0x1801033f3  lea     rcx, aShellSystemset_101; "shell\\systemsettingsthreshold\\handler"...
0x1801033fa  mov     [rsp+500h+var_4D8], rcx
0x1801033ff  mov     [rsp+500h+var_4E0], 426h
0x180103407  xor     r9d, r9d
0x18010340a  lea     r8, aD_2; "D"
0x180103411  xor     edx, edx
0x180103413  mov     rcx, rax
0x180103416  call    cs:__imp_WdsSetupLogMessageW
0x18010341d  nop     dword ptr [rax+rax+00h]
0x180103422  mov     rax, [r13+58h]
0x180103426  mov     r9, [rax+18h]
0x18010342a  mov     [r9+0F4h], esi
0x180103431  call    cs:__imp_GetLastError
0x180103438  nop     dword ptr [rax+rax+00h]
0x18010343d  mov     edi, eax
0x18010343f  call    cs:__imp_CurrentIP
0x180103446  nop     dword ptr [rax+rax+00h]
0x18010344b  mov     rbx, rax
0x18010344e  mov     r8, r15
0x180103451  lea     rdx, aSystemsettings_774; "SystemSettings::DataModel::CPITRSnapsho"...
0x180103458  mov     ecx, 4000000h; unsigned int
0x18010345d  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180103462  mov     [rsp+500h+var_4B0], 0
0x18010346a  mov     [rsp+500h+var_4B8], 0
0x180103473  mov     [rsp+500h+var_4C0], edi
0x180103477  mov     [rsp+500h+var_4C8], rbx
0x18010347c  mov     [rsp+500h+var_4D0], r14
0x180103481  lea     rcx, aShellSystemset_101; "shell\\systemsettingsthreshold\\handler"...
0x180103488  mov     [rsp+500h+var_4D8], rcx
0x18010348d  mov     [rsp+500h+var_4E0], 42Bh
0x180103495  xor     r9d, r9d
0x180103498  lea     r8, aD_2; "D"
0x18010349f  xor     edx, edx
0x1801034a1  mov     rcx, rax
0x1801034a4  call    cs:__imp_WdsSetupLogMessageW
0x1801034ab  nop     dword ptr [rax+rax+00h]
0x1801034b0  nop
0x1801034b1  lea     rcx, [rsp+500h+var_498]
0x1801034b6  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1801034bb  xor     eax, eax
0x1801034bd  jmp     short loc_180103533
0x1801034bf  mov     rcx, [rbp+408h]; this
0x1801034c6  mov     r9d, eax; char *
0x1801034c9  lea     r8, aShellSystemset_19; "shell\\systemsettingsthreshold\\handler"...
0x1801034d0  mov     edx, 3FCh; void *
0x1801034d5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801034da  nop
0x1801034db  mov     rcx, rbx; string
0x1801034de  call    cs:__imp_WindowsDeleteString
0x1801034e5  nop     dword ptr [rax+rax+00h]
0x1801034ea  nop
0x1801034eb  lea     rcx, [rsp+500h+var_498]
0x1801034f0  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1801034f5  mov     eax, edi
0x1801034f7  jmp     short loc_180103533
0x1801034f9  mov     rcx, [rbp+408h]; this
0x180103500  mov     r9d, ebx; char *
0x180103503  lea     r8, aShellSystemset_19; "shell\\systemsettingsthreshold\\handler"...
0x18010350a  mov     edx, 3F8h; void *
0x18010350f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180103514  nop
0x180103515  mov     rcx, [rsp+500h+string]; string
0x18010351a  call    cs:__imp_WindowsDeleteString
0x180103521  nop     dword ptr [rax+rax+00h]
0x180103526  nop
0x180103527  lea     rcx, [rsp+500h+var_498]
0x18010352c  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180103531  mov     eax, ebx
0x180103533  mov     rcx, [rbp+400h+var_30]
0x18010353a  xor     rcx, rsp; StackCookie
0x18010353d  call    __security_check_cookie
0x180103542  lea     r11, [rsp+500h+var_20]
0x18010354a  mov     rbx, [r11+40h]
0x18010354e  mov     rsi, [r11+48h]
0x180103552  mov     rsp, r11
0x180103555  pop     r15
0x180103557  pop     r14
0x180103559  pop     r13
0x18010355b  pop     rdi
0x18010355c  pop     rbp
0x18010355d  retn
```
