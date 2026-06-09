# SystemSettings::DataModel::CPITRSnapshotCadence::SetValue(HSTRING__ *)

- ea: `0x180102860`
- end: `0x180102ce8`
- name: `?SetValue@CPITRSnapshotCadence@DataModel@SystemSettings@@UEAAJPEAUHSTRING__@@@Z`
- size: `1160`
- prototype: `__int64 __fastcall(SystemSettings::DataModel::CPITRSnapshotCadence *__hidden this, HSTRING)`
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
- `0x180102860`
- `0x18010b7e0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x180102a57`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x180102a57`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801028aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180102aff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180102ba6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801028aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180102aff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180102ba6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180102934`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801029bd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180102a94`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180102c67`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180102ca3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180102934`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801029bd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180102a94`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180102c67`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180102ca3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18010297c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801029d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18010297c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801029d9`
- `WDSCORE!WdsSetupLogMessageW` at `0x180102924`
- `WDSCORE!WdsSetupLogMessageW` at `0x180102b79`
- `WDSCORE!WdsSetupLogMessageW` at `0x180102c20`
- `WDSCORE!WdsSetupLogMessageW` at `0x180102924`
- `WDSCORE!WdsSetupLogMessageW` at `0x180102b79`
- `WDSCORE!WdsSetupLogMessageW` at `0x180102c20`
- `WDSCORE!CurrentIP` at `0x1801028b8`
- `WDSCORE!CurrentIP` at `0x180102b0d`
- `WDSCORE!CurrentIP` at `0x180102bb4`
- `WDSCORE!CurrentIP` at `0x1801028b8`
- `WDSCORE!CurrentIP` at `0x180102b0d`
- `WDSCORE!CurrentIP` at `0x180102bb4`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall SystemSettings::DataModel::CPITRSnapshotCadence::SetValue(
        SystemSettings::DataModel::CPITRSnapshotCadence *this,
        char *a2)
{
  struct tagLOG_PARTIAL_MSG *v4; // rax
  int v5; // esi
  HSTRING *v6; // r8
  int ResourceStringById; // eax
  unsigned int v8; // ebx
  unsigned int v9; // edi
  HSTRING v10; // rbx
  const unsigned __int16 *StringRawBuffer; // rax
  int v12; // eax
  const unsigned __int16 *v13; // r8
  unsigned int v14; // edi
  PCWSTR v15; // rax
  __int64 v16; // rax
  int v17; // esi
  int v18; // eax
  const unsigned __int16 *v19; // r8
  struct tagLOG_PARTIAL_MSG *v20; // rax
  struct tagLOG_PARTIAL_MSG *v21; // rax
  int v23; // [rsp+20h] [rbp-E0h]
  int v24; // [rsp+20h] [rbp-E0h]
  HSTRING string; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v26[8]; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v27[3]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v28[40]; // [rsp+88h] [rbp-78h] BYREF
  HSTRING__ v29; // [rsp+B0h] [rbp-50h] BYREF
  struct HWND__ v30; // [rsp+2C0h] [rbp+1C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+508h] [rbp+408h]

  wil::AcquireSRWLockExclusive(v26, (char *)this + 240);
  GetLastError();
  CurrentIP();
  v4 = ConstructPartialMsgW(
         0x4000000u,
         "SystemSettings::DataModel::CPITRSnapshotCadence::SetValue: Setting PITR snapshot cadence to %s",
         a2);
  WdsSetupLogMessageW(v4, 0, L"D", 0);
  v5 = 0;
  while ( 1 )
  {
    WindowsDeleteString(0);
    string = 0;
    ResourceStringById = SystemSettings::DataModel::GetResourceStringById(
                           (SystemSettings::DataModel *)L"SystemSettings_Misc_PointInTimeRestore_SnapshotCadence_HourlyValue",
                           &string,
                           v6);
    v8 = ResourceStringById;
    if ( ResourceStringById < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2F1,
        (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\restore\\pointintimerestore.cpp",
        (const char *)(unsigned int)ResourceStringById,
        739);
      WindowsDeleteString(string);
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(v26);
      return v8;
    }
    v9 = dword_180306120[v5];
    v10 = string;
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    v12 = StringCchPrintfW((unsigned __int16 *)&v29, 0x104u, StringRawBuffer, v9);
    v14 = v12;
    if ( v12 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2F5,
        (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\restore\\pointintimerestore.cpp",
        (const char *)(unsigned int)v12,
        739);
      WindowsDeleteString(v10);
      goto LABEL_19;
    }
    if ( SystemSettings::DataModel::IsHstringEqual((SystemSettings::DataModel *)a2, &v29, v13) )
      break;
    WindowsDeleteString(v10);
    if ( (unsigned int)++v5 >= 5 )
    {
      v15 = WindowsGetStringRawBuffer((HSTRING)a2, 0);
      std::wstring::wstring(v28, v15);
      RestoreSplitDelimitedString(v27, v28);
      std::wstring::_Tidy_deallocate(v28);
      if ( v27[1] - v27[0] == 96
        && !(unsigned __int8)std::operator!=<unsigned short>(v27[0], L"Every")
        && !(unsigned __int8)std::operator!=<unsigned short>(v27[0] + 64LL, L"minutes") )
      {
        v16 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v27[0] + 32LL);
        v17 = _o__wtoi(v16);
        std::vector<std::wstring>::_Tidy(v27);
        goto LABEL_12;
      }
      std::vector<std::wstring>::_Tidy(v27);
      v14 = -2147024809;
LABEL_19:
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(v26);
      return v14;
    }
  }
  v17 = 60 * dword_180306120[v5];
  WindowsDeleteString(v10);
LABEL_12:
  v23 = v17;
  v18 = StringCchPrintfW((unsigned __int16 *)&v30, 0x104u, L"%s SetSnapshotInterval %d", L"PointInTimeRestore", v23);
  v14 = v18;
  if ( v18 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x317,
      (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\restore\\pointintimerestore.cpp",
      (const char *)(unsigned int)v18,
      v24);
    goto LABEL_19;
  }
  if ( (int)SystemSettings::DataModel::ExecuteAdminFlowWait(0, &v30, v19) >= 0 )
  {
    GetLastError();
    CurrentIP();
    v21 = ConstructPartialMsgW(
            0x4000000u,
            "SystemSettings::DataModel::CPITRSnapshotCadence::SetValue: Successfully set PITR snapshot cadence to %d minutes",
            v17);
    WdsSetupLogMessageW(v21, 0, L"D", 0);
    *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 11) + 24LL) + 236LL) = v17;
  }
  else
  {
    GetLastError();
    CurrentIP();
    v20 = ConstructPartialMsgW(
            0x2000000u,
            "SystemSettings::DataModel::CPITRSnapshotCadence::SetValue: Failed to set PITR snapshot cadence to %d minutes",
            v17);
    WdsSetupLogMessageW(v20, 0, L"D", 0);
    SystemSettings::DataModel::CPITRSingleton::EvaluateSettingState(*(SystemSettings::DataModel::CPITRSingleton **)(*((_QWORD *)this + 11) + 24LL));
    SystemSettings::DataModel::CSettingBase::OnValueChanged(this, L"Value");
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(v26);
  return 0;
}

```

## disassembly

```asm
0x180102860  mov     [rsp-8+arg_10], rbx
0x180102865  mov     [rsp-8+arg_18], rsi
0x18010286a  push    rbp
0x18010286b  push    rdi
0x18010286c  push    r13
0x18010286e  push    r14
0x180102870  push    r15
0x180102872  lea     rbp, [rsp-3E0h]
0x18010287a  sub     rsp, 4E0h
0x180102881  mov     rax, cs:__security_cookie
0x180102888  xor     rax, rsp
0x18010288b  mov     [rbp+400h+var_30], rax
0x180102892  mov     r15, rdx
0x180102895  mov     r13, rcx
0x180102898  lea     rdx, [rcx+0F0h]
0x18010289f  lea     rcx, [rsp+500h+var_498]
0x1801028a4  call    ?AcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x1801028a9  nop
0x1801028aa  call    cs:__imp_GetLastError
0x1801028b1  nop     dword ptr [rax+rax+00h]
0x1801028b6  mov     edi, eax
0x1801028b8  call    cs:__imp_CurrentIP
0x1801028bf  nop     dword ptr [rax+rax+00h]
0x1801028c4  mov     rbx, rax
0x1801028c7  mov     r8, r15
0x1801028ca  lea     rdx, aSystemsettings_198; "SystemSettings::DataModel::CPITRSnapsho"...
0x1801028d1  mov     ecx, 4000000h; unsigned int
0x1801028d6  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1801028db  mov     [rsp+500h+var_4B0], 0
0x1801028e3  mov     [rsp+500h+var_4B8], 0
0x1801028ec  mov     [rsp+500h+var_4C0], edi
0x1801028f0  mov     [rsp+500h+var_4C8], rbx
0x1801028f5  lea     rcx, aSystemsettings_33; "SystemSettings::DataModel::CPITRSnapsho"...
0x1801028fc  mov     [rsp+500h+var_4D0], rcx
0x180102901  lea     rcx, aShellSystemset_101; "shell\\systemsettingsthreshold\\handler"...
0x180102908  mov     [rsp+500h+var_4D8], rcx
0x18010290d  mov     [rsp+500h+var_4E0], 2E3h; int
0x180102915  xor     r9d, r9d
0x180102918  lea     r8, aD_2; "D"
0x18010291f  xor     edx, edx
0x180102921  mov     rcx, rax
0x180102924  call    cs:__imp_WdsSetupLogMessageW
0x18010292b  nop     dword ptr [rax+rax+00h]
0x180102930  xor     esi, esi
0x180102932  xor     ecx, ecx; string
0x180102934  call    cs:__imp_WindowsDeleteString
0x18010293b  nop     dword ptr [rax+rax+00h]
0x180102940  mov     [rsp+500h+string], 0
0x180102949  lea     rdx, [rsp+500h+string]; HSTRING *
0x18010294e  lea     rcx, aSystemsettings_1072; "SystemSettings_Misc_PointInTimeRestore_"...
0x180102955  call    ?GetResourceStringById@DataModel@SystemSettings@@YAJPEBGPEAPEAUHSTRING__@@@Z; SystemSettings::DataModel::GetResourceStringById(ushort const *,HSTRING__ * *)
0x18010295a  mov     ebx, eax
0x18010295c  test    eax, eax
0x18010295e  js      loc_180102C82
0x180102964  movsxd  r14, esi
0x180102967  lea     rax, dword_180306120
0x18010296e  mov     edi, [rax+r14*4]
0x180102972  xor     edx, edx; length
0x180102974  mov     rbx, [rsp+500h+string]
0x180102979  mov     rcx, rbx; string
0x18010297c  call    cs:__imp_WindowsGetStringRawBuffer
0x180102983  nop     dword ptr [rax+rax+00h]
0x180102988  mov     r9d, edi
0x18010298b  mov     r8, rax; unsigned __int16 *
0x18010298e  mov     edx, 104h; unsigned __int64
0x180102993  lea     rcx, [rbp+400h+var_450]; unsigned __int16 *
0x180102997  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18010299c  mov     edi, eax
0x18010299e  test    eax, eax
0x1801029a0  js      loc_180102C48
0x1801029a6  lea     rdx, [rbp+400h+var_450]; HSTRING
0x1801029aa  mov     rcx, r15; this
0x1801029ad  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x1801029b2  test    al, al
0x1801029b4  jnz     loc_180102A85
0x1801029ba  mov     rcx, rbx; string
0x1801029bd  call    cs:__imp_WindowsDeleteString
0x1801029c4  nop     dword ptr [rax+rax+00h]
0x1801029c9  inc     esi
0x1801029cb  cmp     esi, 5
0x1801029ce  jb      loc_180102932
0x1801029d4  xor     edx, edx; length
0x1801029d6  mov     rcx, r15; string
0x1801029d9  call    cs:__imp_WindowsGetStringRawBuffer
0x1801029e0  nop     dword ptr [rax+rax+00h]
0x1801029e5  mov     rdx, rax
0x1801029e8  lea     rcx, [rbp+400h+var_478]
0x1801029ec  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1801029f1  nop
0x1801029f2  lea     rdx, [rbp+400h+var_478]
0x1801029f6  lea     rcx, [rsp+500h+var_490]
0x1801029fb  call    ?RestoreSplitDelimitedString@@YA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@G@Z; RestoreSplitDelimitedString(std::wstring const &,ushort)
0x180102a00  nop
0x180102a01  lea     rcx, [rbp+400h+var_478]
0x180102a05  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180102a0a  mov     rcx, [rsp+500h+var_490]
0x180102a0f  mov     rax, [rsp+500h+var_488]
0x180102a14  sub     rax, rcx
0x180102a17  cmp     rax, 60h ; '`'
0x180102a1b  jnz     short loc_180102A71
0x180102a1d  lea     rdx, aEvery; "Every"
0x180102a24  call    ??$?9GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEBG@Z; std::operator!=<ushort>(std::wstring const &,ushort const * const)
0x180102a29  test    al, al
0x180102a2b  jnz     short loc_180102A71
0x180102a2d  mov     rcx, [rsp+500h+var_490]
0x180102a32  add     rcx, 40h ; '@'
0x180102a36  lea     rdx, aMinutes; "minutes"
0x180102a3d  call    ??$?9GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEBG@Z; std::operator!=<ushort>(std::wstring const &,ushort const * const)
0x180102a42  test    al, al
0x180102a44  jnz     short loc_180102A71
0x180102a46  mov     rcx, [rsp+500h+var_490]
0x180102a4b  add     rcx, 20h ; ' '
0x180102a4f  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180102a54  mov     rcx, rax
0x180102a57  call    cs:__imp__o__wtoi
0x180102a5e  nop     dword ptr [rax+rax+00h]
0x180102a63  mov     esi, eax
0x180102a65  lea     rcx, [rsp+500h+var_490]
0x180102a6a  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180102a6f  jmp     short loc_180102AA0
0x180102a71  lea     rcx, [rsp+500h+var_490]
0x180102a76  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180102a7b  mov     edi, 80070057h
0x180102a80  jmp     loc_180102C74
0x180102a85  lea     rax, dword_180306120
0x180102a8c  imul    esi, [rax+r14*4], 3Ch ; '<'
0x180102a91  mov     rcx, rbx; string
0x180102a94  call    cs:__imp_WindowsDeleteString
0x180102a9b  nop     dword ptr [rax+rax+00h]
0x180102aa0  mov     [rsp+500h+var_4E0], esi; int
0x180102aa4  lea     r9, aPointintimeres; "PointInTimeRestore"
0x180102aab  lea     r8, aSSetsnapshotin; "%s SetSnapshotInterval %d"
0x180102ab2  mov     edx, 104h; unsigned __int64
0x180102ab7  lea     rcx, [rbp+400h+var_240]; unsigned __int16 *
0x180102abe  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180102ac3  mov     edi, eax
0x180102ac5  test    eax, eax
0x180102ac7  jns     short loc_180102AE9
0x180102ac9  mov     rcx, [rbp+408h]; this
0x180102ad0  mov     r9d, eax; char *
0x180102ad3  lea     r8, aShellSystemset_19; "shell\\systemsettingsthreshold\\handler"...
0x180102ada  mov     edx, 317h; void *
0x180102adf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180102ae4  jmp     loc_180102C74
0x180102ae9  lea     rdx, [rbp+400h+var_240]; HWND
0x180102af0  xor     ecx, ecx; this
0x180102af2  call    ?ExecuteAdminFlowWait@DataModel@SystemSettings@@YAJPEAUHWND__@@PEBG@Z; SystemSettings::DataModel::ExecuteAdminFlowWait(HWND__ *,ushort const *)
0x180102af7  test    eax, eax
0x180102af9  jns     loc_180102BA6
0x180102aff  call    cs:__imp_GetLastError
0x180102b06  nop     dword ptr [rax+rax+00h]
0x180102b0b  mov     edi, eax
0x180102b0d  call    cs:__imp_CurrentIP
0x180102b14  nop     dword ptr [rax+rax+00h]
0x180102b19  mov     rbx, rax
0x180102b1c  mov     r8d, esi
0x180102b1f  lea     rdx, aSystemsettings_695; "SystemSettings::DataModel::CPITRSnapsho"...
0x180102b26  mov     ecx, 2000000h; unsigned int
0x180102b2b  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180102b30  mov     [rsp+500h+var_4B0], 0
0x180102b38  mov     [rsp+500h+var_4B8], 0
0x180102b41  mov     [rsp+500h+var_4C0], edi
0x180102b45  mov     [rsp+500h+var_4C8], rbx
0x180102b4a  lea     rcx, aSystemsettings_33; "SystemSettings::DataModel::CPITRSnapsho"...
0x180102b51  mov     [rsp+500h+var_4D0], rcx
0x180102b56  lea     rcx, aShellSystemset_101; "shell\\systemsettingsthreshold\\handler"...
0x180102b5d  mov     [rsp+500h+var_4D8], rcx
0x180102b62  mov     [rsp+500h+var_4E0], 31Bh
0x180102b6a  xor     r9d, r9d
0x180102b6d  lea     r8, aD_2; "D"
0x180102b74  xor     edx, edx
0x180102b76  mov     rcx, rax
0x180102b79  call    cs:__imp_WdsSetupLogMessageW
0x180102b80  nop     dword ptr [rax+rax+00h]
0x180102b85  mov     rcx, [r13+58h]
0x180102b89  mov     rcx, [rcx+18h]; this
0x180102b8d  call    ?EvaluateSettingState@CPITRSingleton@DataModel@SystemSettings@@QEAAJXZ; SystemSettings::DataModel::CPITRSingleton::EvaluateSettingState(void)
0x180102b92  lea     rdx, aValue_0; "Value"
0x180102b99  mov     rcx, r13; this
0x180102b9c  call    ?OnValueChanged@CSettingBase@DataModel@SystemSettings@@QEAAXPEBG@Z; SystemSettings::DataModel::CSettingBase::OnValueChanged(ushort const *)
0x180102ba1  jmp     loc_180102C3A
0x180102ba6  call    cs:__imp_GetLastError
0x180102bad  nop     dword ptr [rax+rax+00h]
0x180102bb2  mov     edi, eax
0x180102bb4  call    cs:__imp_CurrentIP
0x180102bbb  nop     dword ptr [rax+rax+00h]
0x180102bc0  mov     rbx, rax
0x180102bc3  mov     r8d, esi
0x180102bc6  lea     rdx, aSystemsettings_861; "SystemSettings::DataModel::CPITRSnapsho"...
0x180102bcd  mov     ecx, 4000000h; unsigned int
0x180102bd2  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180102bd7  mov     [rsp+500h+var_4B0], 0
0x180102bdf  mov     [rsp+500h+var_4B8], 0
0x180102be8  mov     [rsp+500h+var_4C0], edi
0x180102bec  mov     [rsp+500h+var_4C8], rbx
0x180102bf1  lea     rcx, aSystemsettings_33; "SystemSettings::DataModel::CPITRSnapsho"...
0x180102bf8  mov     [rsp+500h+var_4D0], rcx
0x180102bfd  lea     rcx, aShellSystemset_101; "shell\\systemsettingsthreshold\\handler"...
0x180102c04  mov     [rsp+500h+var_4D8], rcx
0x180102c09  mov     [rsp+500h+var_4E0], 322h
0x180102c11  xor     r9d, r9d
0x180102c14  lea     r8, aD_2; "D"
0x180102c1b  xor     edx, edx
0x180102c1d  mov     rcx, rax
0x180102c20  call    cs:__imp_WdsSetupLogMessageW
0x180102c27  nop     dword ptr [rax+rax+00h]
0x180102c2c  mov     rax, [r13+58h]
0x180102c30  mov     rcx, [rax+18h]
0x180102c34  mov     [rcx+0ECh], esi
0x180102c3a  lea     rcx, [rsp+500h+var_498]
0x180102c3f  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180102c44  xor     eax, eax
0x180102c46  jmp     short loc_180102CBC
0x180102c48  mov     rcx, [rbp+408h]; this
0x180102c4f  mov     r9d, eax; char *
0x180102c52  lea     r8, aShellSystemset_19; "shell\\systemsettingsthreshold\\handler"...
0x180102c59  mov     edx, 2F5h; void *
0x180102c5e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180102c63  nop
0x180102c64  mov     rcx, rbx; string
0x180102c67  call    cs:__imp_WindowsDeleteString
0x180102c6e  nop     dword ptr [rax+rax+00h]
0x180102c73  nop
0x180102c74  lea     rcx, [rsp+500h+var_498]
0x180102c79  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180102c7e  mov     eax, edi
0x180102c80  jmp     short loc_180102CBC
0x180102c82  mov     rcx, [rbp+408h]; this
0x180102c89  mov     r9d, ebx; char *
0x180102c8c  lea     r8, aShellSystemset_19; "shell\\systemsettingsthreshold\\handler"...
0x180102c93  mov     edx, 2F1h; void *
0x180102c98  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180102c9d  nop
0x180102c9e  mov     rcx, [rsp+500h+string]; string
0x180102ca3  call    cs:__imp_WindowsDeleteString
0x180102caa  nop     dword ptr [rax+rax+00h]
0x180102caf  nop
0x180102cb0  lea     rcx, [rsp+500h+var_498]
0x180102cb5  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180102cba  mov     eax, ebx
0x180102cbc  mov     rcx, [rbp+400h+var_30]
0x180102cc3  xor     rcx, rsp; StackCookie
0x180102cc6  call    __security_check_cookie
0x180102ccb  lea     r11, [rsp+500h+var_20]
0x180102cd3  mov     rbx, [r11+40h]
0x180102cd7  mov     rsi, [r11+48h]
0x180102cdb  mov     rsp, r11
0x180102cde  pop     r15
0x180102ce0  pop     r14
0x180102ce2  pop     r13
0x180102ce4  pop     rdi
0x180102ce5  pop     rbp
0x180102ce6  retn
```
