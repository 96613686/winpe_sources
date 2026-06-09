# SystemSettings::DataModel::CQuickMachineRecoveryTimeToReboot::SetValue(HSTRING__ *)

- ea: `0x180108880`
- end: `0x180108ace`
- name: `?SetValue@CQuickMachineRecoveryTimeToReboot@DataModel@SystemSettings@@UEAAJPEAUHSTRING__@@@Z`
- size: `590`
- prototype: `__int64 __fastcall(SystemSettings::DataModel::CQuickMachineRecoveryTimeToReboot *__hidden this, HSTRING)`
- caller_count: `0`
- callee_count: `15`
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
- `0x18004528c`
- `0x18004d1ac`
- `0x1800886b0`
- `0x180108880`
- `0x180109154`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x1801089b1`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x1801089b1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801088d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180108934`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801089dd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180108a89`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801088d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180108934`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801089dd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180108a89`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180108912`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18010894c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180108912`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18010894c`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SystemSettings::DataModel::CQuickMachineRecoveryTimeToReboot::SetValue(
        SystemSettings::DataModel::CQuickMachineRecoveryTimeToReboot *this,
        SystemSettings::DataModel *a2)
{
  unsigned int i; // edi
  HSTRING *v5; // r8
  int ResourceStringById; // eax
  unsigned int v7; // ebx
  HSTRING v8; // rbx
  WCHAR *StringRawBuffer; // rax
  const unsigned __int16 *v10; // r8
  PCWSTR v11; // rax
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // r9
  __int64 v15; // rax
  int v16; // edi
  int v17; // eax
  const unsigned __int16 *v18; // r8
  int v20; // [rsp+20h] [rbp-E0h]
  int v21; // [rsp+20h] [rbp-E0h]
  int v22; // [rsp+20h] [rbp-E0h]
  HSTRING string; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v24[8]; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v25[3]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v26[40]; // [rsp+58h] [rbp-A8h] BYREF
  struct HWND__ v27; // [rsp+80h] [rbp-80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2C8h] [rbp+1C8h]

  wil::AcquireSRWLockExclusive(v24, (char *)this + 240);
  for ( i = 0; i < 6; ++i )
  {
    WindowsDeleteString(0);
    string = 0;
    ResourceStringById = SystemSettings::DataModel::GetResourceStringById(
                           (SystemSettings::DataModel *)(&off_1802BFDB0)[2 * (int)i],
                           &string,
                           v5);
    v7 = ResourceStringById;
    if ( ResourceStringById < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4A4,
        (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\restore\\quickmachinerecovery.cpp",
        (const char *)(unsigned int)ResourceStringById,
        v20);
      WindowsDeleteString(string);
      goto LABEL_16;
    }
    v8 = string;
    StringRawBuffer = (WCHAR *)WindowsGetStringRawBuffer(string, 0);
    if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)StringRawBuffer, v10) )
    {
      v16 = *((_DWORD *)&off_1802BFDB0 + 4 * (int)i + 2);
      WindowsDeleteString(v8);
      goto LABEL_9;
    }
    WindowsDeleteString(v8);
  }
  v11 = WindowsGetStringRawBuffer((HSTRING)a2, 0);
  std::wstring::wstring(v26, v11);
  SystemSettings::DataModel::splitDelimitedString(v25, v26);
  if ( (unsigned __int64)((__int64)(v25[1] - v25[0]) >> 5) < 2 )
  {
    std::vector<std::wstring>::_Tidy(v25);
    std::wstring::_Tidy_deallocate(v26);
    v7 = -2147024809;
LABEL_16:
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(v24);
    return v7;
  }
  v15 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v25[0], v12, v13, v14);
  v16 = _o__wtoi(v15);
  std::vector<std::wstring>::_Tidy(v25);
  std::wstring::_Tidy_deallocate(v26);
LABEL_9:
  v21 = v16;
  v17 = StringCchPrintfW((unsigned __int16 *)&v27, 0x104u, L"%s SetTimeToReboot %d", L"QuickMachineRecovery", v21);
  v7 = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4BE,
      (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\restore\\quickmachinerecovery.cpp",
      (const char *)(unsigned int)v17,
      v22);
    goto LABEL_16;
  }
  if ( (int)SystemSettings::DataModel::ExecuteAdminFlowWait(0, &v27, v18) >= 0 )
    *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 11) + 24LL) + 244LL) = v16;
  else
    SystemSettings::DataModel::CSettingBase::OnValueChanged(this, L"Value");
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(v24);
  return 0;
}

```

## disassembly

```asm
0x180108880  mov     [rsp-8+arg_10], rbx
0x180108885  mov     [rsp-8+arg_18], rsi
0x18010888a  push    rbp
0x18010888b  push    rdi
0x18010888c  push    r12
0x18010888e  push    r14
0x180108890  push    r15
0x180108892  lea     rbp, [rsp-1A0h]
0x18010889a  sub     rsp, 2A0h
0x1801088a1  mov     rax, cs:__security_cookie
0x1801088a8  xor     rax, rsp
0x1801088ab  mov     [rbp+1C0h+var_30], rax
0x1801088b2  mov     r15, rdx
0x1801088b5  mov     rsi, rcx
0x1801088b8  lea     rdx, [rcx+0F0h]
0x1801088bf  lea     rcx, [rsp+2C0h+var_288]
0x1801088c4  call    ?AcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x1801088c9  nop
0x1801088ca  xor     edi, edi
0x1801088cc  lea     r12, off_1802BFDB0; "SystemSettings_Misc_QuickMachineRecover"...
0x1801088d3  xor     ecx, ecx; string
0x1801088d5  call    cs:__imp_WindowsDeleteString
0x1801088dc  nop     dword ptr [rax+rax+00h]
0x1801088e1  mov     [rsp+2C0h+string], 0
0x1801088ea  movsxd  r14, edi
0x1801088ed  add     r14, r14
0x1801088f0  lea     rdx, [rsp+2C0h+string]; HSTRING *
0x1801088f5  mov     rcx, [r12+r14*8]; this
0x1801088f9  call    ?GetResourceStringById@DataModel@SystemSettings@@YAJPEBGPEAPEAUHSTRING__@@@Z; SystemSettings::DataModel::GetResourceStringById(ushort const *,HSTRING__ * *)
0x1801088fe  mov     ebx, eax
0x180108900  test    eax, eax
0x180108902  js      loc_180108A68
0x180108908  xor     edx, edx; length
0x18010890a  mov     rbx, [rsp+2C0h+string]
0x18010890f  mov     rcx, rbx; string
0x180108912  call    cs:__imp_WindowsGetStringRawBuffer
0x180108919  nop     dword ptr [rax+rax+00h]
0x18010891e  mov     rdx, rax; HSTRING
0x180108921  mov     rcx, r15; this
0x180108924  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x180108929  test    al, al
0x18010892b  jnz     loc_1801089D5
0x180108931  mov     rcx, rbx; string
0x180108934  call    cs:__imp_WindowsDeleteString
0x18010893b  nop     dword ptr [rax+rax+00h]
0x180108940  inc     edi
0x180108942  cmp     edi, 6
0x180108945  jb      short loc_1801088D3
0x180108947  xor     edx, edx; length
0x180108949  mov     rcx, r15; string
0x18010894c  call    cs:__imp_WindowsGetStringRawBuffer
0x180108953  nop     dword ptr [rax+rax+00h]
0x180108958  mov     rdx, rax
0x18010895b  lea     rcx, [rsp+2C0h+var_268]
0x180108960  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180108965  lea     rdx, [rsp+2C0h+var_268]
0x18010896a  lea     rcx, [rsp+2C0h+var_280]
0x18010896f  call    ?splitDelimitedString@DataModel@SystemSettings@@YA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@4@G@Z; SystemSettings::DataModel::splitDelimitedString(std::wstring const &,ushort)
0x180108974  mov     rax, [rsp+2C0h+var_278]
0x180108979  mov     rcx, [rsp+2C0h+var_280]
0x18010897e  sub     rax, rcx
0x180108981  sar     rax, 5
0x180108985  cmp     rax, 2
0x180108989  jnb     short loc_1801089A9
0x18010898b  lea     rcx, [rsp+2C0h+var_280]
0x180108990  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180108995  lea     rcx, [rsp+2C0h+var_268]
0x18010899a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010899f  mov     ebx, 80070057h
0x1801089a4  jmp     loc_180108A96
0x1801089a9  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1801089ae  mov     rcx, rax
0x1801089b1  call    cs:__imp__o__wtoi
0x1801089b8  nop     dword ptr [rax+rax+00h]
0x1801089bd  mov     edi, eax
0x1801089bf  lea     rcx, [rsp+2C0h+var_280]
0x1801089c4  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1801089c9  lea     rcx, [rsp+2C0h+var_268]
0x1801089ce  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801089d3  jmp     short loc_1801089E9
0x1801089d5  mov     edi, [r12+r14*8+8]
0x1801089da  mov     rcx, rbx; string
0x1801089dd  call    cs:__imp_WindowsDeleteString
0x1801089e4  nop     dword ptr [rax+rax+00h]
0x1801089e9  mov     [rsp+2C0h+var_2A0], edi; int
0x1801089ed  lea     r9, aQuickmachinere; "QuickMachineRecovery"
0x1801089f4  lea     r8, aSSettimetorebo; "%s SetTimeToReboot %d"
0x1801089fb  mov     edx, 104h; unsigned __int64
0x180108a00  lea     rcx, [rbp+1C0h+var_240]; unsigned __int16 *
0x180108a04  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180108a09  mov     ebx, eax
0x180108a0b  test    eax, eax
0x180108a0d  jns     short loc_180108A2C
0x180108a0f  mov     rcx, [rbp+1C8h]; this
0x180108a16  mov     r9d, eax; char *
0x180108a19  lea     r8, aShellSystemset_65; "shell\\systemsettingsthreshold\\handler"...
0x180108a20  mov     edx, 4BEh; void *
0x180108a25  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180108a2a  jmp     short loc_180108A96
0x180108a2c  lea     rdx, [rbp+1C0h+var_240]; HWND
0x180108a30  xor     ecx, ecx; this
0x180108a32  call    ?ExecuteAdminFlowWait@DataModel@SystemSettings@@YAJPEAUHWND__@@PEBG@Z; SystemSettings::DataModel::ExecuteAdminFlowWait(HWND__ *,ushort const *)
0x180108a37  test    eax, eax
0x180108a39  jns     short loc_180108A4C
0x180108a3b  lea     rdx, aValue_0; "Value"
0x180108a42  mov     rcx, rsi; this
0x180108a45  call    ?OnValueChanged@CSettingBase@DataModel@SystemSettings@@QEAAXPEBG@Z; SystemSettings::DataModel::CSettingBase::OnValueChanged(ushort const *)
0x180108a4a  jmp     short loc_180108A5A
0x180108a4c  mov     rax, [rsi+58h]
0x180108a50  mov     rcx, [rax+18h]
0x180108a54  mov     [rcx+0F4h], edi
0x180108a5a  lea     rcx, [rsp+2C0h+var_288]
0x180108a5f  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180108a64  xor     eax, eax
0x180108a66  jmp     short loc_180108AA2
0x180108a68  mov     rcx, [rbp+1C8h]; this
0x180108a6f  mov     r9d, ebx; char *
0x180108a72  lea     r8, aShellSystemset_65; "shell\\systemsettingsthreshold\\handler"...
0x180108a79  mov     edx, 4A4h; void *
0x180108a7e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180108a83  nop
0x180108a84  mov     rcx, [rsp+2C0h+string]; string
0x180108a89  call    cs:__imp_WindowsDeleteString
0x180108a90  nop     dword ptr [rax+rax+00h]
0x180108a95  nop
0x180108a96  lea     rcx, [rsp+2C0h+var_288]
0x180108a9b  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180108aa0  mov     eax, ebx
0x180108aa2  mov     rcx, [rbp+1C0h+var_30]
0x180108aa9  xor     rcx, rsp; StackCookie
0x180108aac  call    __security_check_cookie
0x180108ab1  lea     r11, [rsp+2C0h+var_20]
0x180108ab9  mov     rbx, [r11+40h]
0x180108abd  mov     rsi, [r11+48h]
0x180108ac1  mov     rsp, r11
0x180108ac4  pop     r15
0x180108ac6  pop     r14
0x180108ac8  pop     r12
0x180108aca  pop     rdi
0x180108acb  pop     rbp
0x180108acc  retn
```
