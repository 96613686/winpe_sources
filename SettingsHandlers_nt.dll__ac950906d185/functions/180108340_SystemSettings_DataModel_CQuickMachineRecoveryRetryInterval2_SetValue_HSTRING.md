# SystemSettings::DataModel::CQuickMachineRecoveryRetryInterval2::SetValue(HSTRING__ *)

- ea: `0x180108340`
- end: `0x180108621`
- name: `?SetValue@CQuickMachineRecoveryRetryInterval2@DataModel@SystemSettings@@UEAAJPEAUHSTRING__@@@Z`
- size: `737`
- prototype: `__int64 __fastcall(SystemSettings::DataModel::CQuickMachineRecoveryRetryInterval2 *__hidden this, HSTRING)`
- caller_count: `0`
- callee_count: `17`
- tags: `registry_config, loader_planting`

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
- `0x180044010`
- `0x18004528c`
- `0x18004d1ac`
- `0x1800886b0`
- `0x1800ce7ec`
- `0x180108340`
- `0x180109154`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x1801084d3`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x1801084d3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180108383`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180108568`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801085b6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801085e1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180108383`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180108568`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801085b6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801085e1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801083d6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801083fd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801083d6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801083fd`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SystemSettings::DataModel::CQuickMachineRecoveryRetryInterval2::SetValue(
        SystemSettings::DataModel::CQuickMachineRecoveryRetryInterval2 *this,
        SystemSettings::DataModel *a2)
{
  HSTRING *v4; // r8
  int ResourceStringById; // eax
  unsigned int v6; // edi
  WCHAR *StringRawBuffer; // rax
  const unsigned __int16 *v8; // r8
  int v9; // edi
  PCWSTR v10; // rax
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 v13; // r9
  __int64 v14; // rax
  int v15; // eax
  const unsigned __int16 *v16; // r8
  int v17; // esi
  int v19; // [rsp+20h] [rbp-E0h]
  int v20; // [rsp+20h] [rbp-E0h]
  int v21; // [rsp+20h] [rbp-E0h]
  HSTRING string; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v23[8]; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v24[3]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v25[40]; // [rsp+58h] [rbp-A8h] BYREF
  struct HWND__ v26; // [rsp+80h] [rbp-80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+1B8h]

  wil::AcquireSRWLockExclusive(v23, (char *)this + 240);
  WindowsDeleteString(0);
  string = 0;
  ResourceStringById = SystemSettings::DataModel::GetResourceStringById(
                         (SystemSettings::DataModel *)L"SystemSettings_Misc_QuickMachineRecovery_RetryInterval_Once",
                         &string,
                         v4);
  v6 = ResourceStringById;
  if ( ResourceStringById < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x35A,
      (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\restore\\quickmachinerecovery.cpp",
      (const char *)(unsigned int)ResourceStringById,
      v19);
LABEL_17:
    WindowsDeleteString(string);
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(v23);
    return v6;
  }
  StringRawBuffer = (WCHAR *)WindowsGetStringRawBuffer(string, 0);
  if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)StringRawBuffer, v8) )
  {
    v9 = 0;
  }
  else
  {
    v10 = WindowsGetStringRawBuffer((HSTRING)a2, 0);
    std::wstring::wstring(v25, v10);
    SystemSettings::DataModel::splitDelimitedString(v24, v25);
    std::wstring::_Tidy_deallocate(v25);
    if ( v24[1] - v24[0] != 96
      || (unsigned __int8)std::operator!=<unsigned short>(v24[0], L"Every")
      || (unsigned __int8)std::operator!=<unsigned short>(v24[0] + 64LL, L"minute")
      && (unsigned __int8)std::operator!=<unsigned short>(v24[0] + 64LL, L"minutes")
      && (unsigned __int8)std::operator!=<unsigned short>(v24[0] + 64LL, L"hour")
      && (unsigned __int8)std::operator!=<unsigned short>(v24[0] + 64LL, L"hours") )
    {
      std::vector<std::wstring>::_Tidy(v24);
      WindowsDeleteString(string);
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(v23);
      return 2147942487LL;
    }
    v14 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v24[0] + 32LL, v11, v12, v13);
    v9 = _o__wtoi(v14);
    if ( (unsigned __int8)std::wstring::_Equal(v24[0] + 64LL, L"hour")
      || (unsigned __int8)std::wstring::_Equal(v24[0] + 64LL, L"hours") )
    {
      v9 *= 60;
    }
    std::vector<std::wstring>::_Tidy(v24);
  }
  v20 = v9;
  v15 = StringCchPrintfW((unsigned __int16 *)&v26, 0x104u, L"%s SetRetryInterval %d", L"QuickMachineRecovery", v20);
  v17 = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x37B,
      (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\restore\\quickmachinerecovery.cpp",
      (const char *)(unsigned int)v15,
      v21);
    v6 = v17;
    goto LABEL_17;
  }
  if ( (int)SystemSettings::DataModel::ExecuteAdminFlowWait(0, &v26, v16) >= 0 )
    *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 11) + 24LL) + 240LL) = v9;
  else
    SystemSettings::DataModel::CSettingBase::OnValueChanged(this, L"Value");
  WindowsDeleteString(string);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(v23);
  return 0;
}

```

## disassembly

```asm
0x180108340  mov     [rsp-8+arg_10], rsi
0x180108345  push    rbp
0x180108346  push    rdi
0x180108347  push    r14
0x180108349  lea     rbp, [rsp-1A0h]
0x180108351  sub     rsp, 2A0h
0x180108358  mov     rax, cs:__security_cookie
0x18010835f  xor     rax, rsp
0x180108362  mov     [rbp+1B0h+var_20], rax
0x180108369  mov     rsi, rdx
0x18010836c  mov     r14, rcx
0x18010836f  lea     rdx, [rcx+0F0h]
0x180108376  lea     rcx, [rsp+2B0h+var_278]
0x18010837b  call    ?AcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x180108380  nop
0x180108381  xor     ecx, ecx; string
0x180108383  call    cs:__imp_WindowsDeleteString
0x18010838a  nop     dword ptr [rax+rax+00h]
0x18010838f  mov     [rsp+2B0h+string], 0
0x180108398  lea     rdx, [rsp+2B0h+string]; HSTRING *
0x18010839d  lea     rcx, aSystemsettings_128; "SystemSettings_Misc_QuickMachineRecover"...
0x1801083a4  call    ?GetResourceStringById@DataModel@SystemSettings@@YAJPEBGPEAPEAUHSTRING__@@@Z; SystemSettings::DataModel::GetResourceStringById(ushort const *,HSTRING__ * *)
0x1801083a9  mov     edi, eax
0x1801083ab  test    eax, eax
0x1801083ad  jns     short loc_1801083CF
0x1801083af  mov     rcx, [rbp+1B8h]; this
0x1801083b6  mov     r9d, eax; char *
0x1801083b9  lea     r8, aShellSystemset_65; "shell\\systemsettingsthreshold\\handler"...
0x1801083c0  mov     edx, 35Ah; void *
0x1801083c5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801083ca  jmp     loc_180108563
0x1801083cf  xor     edx, edx; length
0x1801083d1  mov     rcx, [rsp+2B0h+string]; string
0x1801083d6  call    cs:__imp_WindowsGetStringRawBuffer
0x1801083dd  nop     dword ptr [rax+rax+00h]
0x1801083e2  mov     rdx, rax; HSTRING
0x1801083e5  mov     rcx, rsi; this
0x1801083e8  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x1801083ed  test    al, al
0x1801083ef  jz      short loc_1801083F8
0x1801083f1  xor     edi, edi
0x1801083f3  jmp     loc_180108520
0x1801083f8  xor     edx, edx; length
0x1801083fa  mov     rcx, rsi; string
0x1801083fd  call    cs:__imp_WindowsGetStringRawBuffer
0x180108404  nop     dword ptr [rax+rax+00h]
0x180108409  mov     rdx, rax
0x18010840c  lea     rcx, [rsp+2B0h+var_258]
0x180108411  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180108416  lea     rdx, [rsp+2B0h+var_258]
0x18010841b  lea     rcx, [rsp+2B0h+var_270]
0x180108420  call    ?splitDelimitedString@DataModel@SystemSettings@@YA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@4@G@Z; SystemSettings::DataModel::splitDelimitedString(std::wstring const &,ushort)
0x180108425  lea     rcx, [rsp+2B0h+var_258]
0x18010842a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010842f  mov     rcx, [rsp+2B0h+var_270]
0x180108434  mov     rax, [rsp+2B0h+var_268]
0x180108439  sub     rax, rcx
0x18010843c  cmp     rax, 60h ; '`'
0x180108440  jnz     loc_1801085D1
0x180108446  lea     rdx, aEvery; "Every"
0x18010844d  call    ??$?9GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEBG@Z; std::operator!=<ushort>(std::wstring const &,ushort const * const)
0x180108452  test    al, al
0x180108454  jnz     loc_1801085D1
0x18010845a  mov     rcx, [rsp+2B0h+var_270]
0x18010845f  add     rcx, 40h ; '@'
0x180108463  lea     rdx, aMinute; "minute"
0x18010846a  call    ??$?9GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEBG@Z; std::operator!=<ushort>(std::wstring const &,ushort const * const)
0x18010846f  test    al, al
0x180108471  jz      short loc_1801084C2
0x180108473  mov     rcx, [rsp+2B0h+var_270]
0x180108478  add     rcx, 40h ; '@'
0x18010847c  lea     rdx, aMinutes; "minutes"
0x180108483  call    ??$?9GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEBG@Z; std::operator!=<ushort>(std::wstring const &,ushort const * const)
0x180108488  test    al, al
0x18010848a  jz      short loc_1801084C2
0x18010848c  mov     rcx, [rsp+2B0h+var_270]
0x180108491  add     rcx, 40h ; '@'
0x180108495  lea     rdx, aHour; "hour"
0x18010849c  call    ??$?9GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEBG@Z; std::operator!=<ushort>(std::wstring const &,ushort const * const)
0x1801084a1  test    al, al
0x1801084a3  jz      short loc_1801084C2
0x1801084a5  mov     rcx, [rsp+2B0h+var_270]
0x1801084aa  add     rcx, 40h ; '@'
0x1801084ae  lea     rdx, aHours; "hours"
0x1801084b5  call    ??$?9GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEBG@Z; std::operator!=<ushort>(std::wstring const &,ushort const * const)
0x1801084ba  test    al, al
0x1801084bc  jnz     loc_1801085D1
0x1801084c2  mov     rcx, [rsp+2B0h+var_270]
0x1801084c7  add     rcx, 20h ; ' '
0x1801084cb  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1801084d0  mov     rcx, rax
0x1801084d3  call    cs:__imp__o__wtoi
0x1801084da  nop     dword ptr [rax+rax+00h]
0x1801084df  mov     edi, eax
0x1801084e1  mov     rcx, [rsp+2B0h+var_270]
0x1801084e6  add     rcx, 40h ; '@'
0x1801084ea  lea     rdx, aHour; "hour"
0x1801084f1  call    ?_Equal@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_NQEBG@Z; std::wstring::_Equal(ushort const * const)
0x1801084f6  test    al, al
0x1801084f8  jnz     short loc_180108513
0x1801084fa  mov     rcx, [rsp+2B0h+var_270]
0x1801084ff  add     rcx, 40h ; '@'
0x180108503  lea     rdx, aHours; "hours"
0x18010850a  call    ?_Equal@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_NQEBG@Z; std::wstring::_Equal(ushort const * const)
0x18010850f  test    al, al
0x180108511  jz      short loc_180108516
0x180108513  imul    edi, 3Ch ; '<'
0x180108516  lea     rcx, [rsp+2B0h+var_270]
0x18010851b  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180108520  mov     [rsp+2B0h+var_290], edi; int
0x180108524  lea     r9, aQuickmachinere; "QuickMachineRecovery"
0x18010852b  lea     r8, aSSetretryinter; "%s SetRetryInterval %d"
0x180108532  mov     edx, 104h; unsigned __int64
0x180108537  lea     rcx, [rbp+1B0h+var_230]; unsigned __int16 *
0x18010853b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180108540  mov     esi, eax
0x180108542  test    eax, eax
0x180108544  jns     short loc_180108583
0x180108546  mov     rcx, [rbp+1B8h]; this
0x18010854d  mov     r9d, eax; char *
0x180108550  lea     r8, aShellSystemset_65; "shell\\systemsettingsthreshold\\handler"...
0x180108557  mov     edx, 37Bh; void *
0x18010855c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180108561  mov     edi, esi
0x180108563  mov     rcx, [rsp+2B0h+string]; string
0x180108568  call    cs:__imp_WindowsDeleteString
0x18010856f  nop     dword ptr [rax+rax+00h]
0x180108574  nop
0x180108575  lea     rcx, [rsp+2B0h+var_278]
0x18010857a  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18010857f  mov     eax, edi
0x180108581  jmp     short loc_1801085FD
0x180108583  lea     rdx, [rbp+1B0h+var_230]; HWND
0x180108587  xor     ecx, ecx; this
0x180108589  call    ?ExecuteAdminFlowWait@DataModel@SystemSettings@@YAJPEAUHWND__@@PEBG@Z; SystemSettings::DataModel::ExecuteAdminFlowWait(HWND__ *,ushort const *)
0x18010858e  test    eax, eax
0x180108590  jns     short loc_1801085A3
0x180108592  lea     rdx, aValue_0; "Value"
0x180108599  mov     rcx, r14; this
0x18010859c  call    ?OnValueChanged@CSettingBase@DataModel@SystemSettings@@QEAAXPEBG@Z; SystemSettings::DataModel::CSettingBase::OnValueChanged(ushort const *)
0x1801085a1  jmp     short loc_1801085B1
0x1801085a3  mov     rax, [r14+58h]
0x1801085a7  mov     rcx, [rax+18h]
0x1801085ab  mov     [rcx+0F0h], edi
0x1801085b1  mov     rcx, [rsp+2B0h+string]; string
0x1801085b6  call    cs:__imp_WindowsDeleteString
0x1801085bd  nop     dword ptr [rax+rax+00h]
0x1801085c2  nop
0x1801085c3  lea     rcx, [rsp+2B0h+var_278]
0x1801085c8  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1801085cd  xor     eax, eax
0x1801085cf  jmp     short loc_1801085FD
0x1801085d1  lea     rcx, [rsp+2B0h+var_270]
0x1801085d6  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1801085db  nop
0x1801085dc  mov     rcx, [rsp+2B0h+string]; string
0x1801085e1  call    cs:__imp_WindowsDeleteString
0x1801085e8  nop     dword ptr [rax+rax+00h]
0x1801085ed  nop
0x1801085ee  lea     rcx, [rsp+2B0h+var_278]
0x1801085f3  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1801085f8  mov     eax, 80070057h
0x1801085fd  mov     rcx, [rbp+1B0h+var_20]
0x180108604  xor     rcx, rsp; StackCookie
0x180108607  call    __security_check_cookie
0x18010860c  mov     rsi, [rsp+2B0h+arg_10]
0x180108614  add     rsp, 2A0h
0x18010861b  pop     r14
0x18010861d  pop     rdi
0x18010861e  pop     rbp
0x18010861f  retn
```
