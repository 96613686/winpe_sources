# SystemSettings::DataModel::CQuickMachineRecoveryRetryInterval::SetValue(HSTRING__ *)

- ea: `0x180108630`
- end: `0x180108874`
- name: `?SetValue@CQuickMachineRecoveryRetryInterval@DataModel@SystemSettings@@UEAAJPEAUHSTRING__@@@Z`
- size: `580`
- prototype: `__int64 __fastcall(SystemSettings::DataModel::CQuickMachineRecoveryRetryInterval *__hidden this, HSTRING)`
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
- `0x180108630`
- `0x180109154`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x180108761`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x180108761`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180108685`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801086e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010878d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010882f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180108685`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801086e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010878d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010882f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801086c2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801086fc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801086c2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801086fc`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SystemSettings::DataModel::CQuickMachineRecoveryRetryInterval::SetValue(
        SystemSettings::DataModel::CQuickMachineRecoveryRetryInterval *this,
        SystemSettings::DataModel *a2)
{
  unsigned int i; // edi
  HSTRING *v5; // r8
  int ResourceStringById; // eax
  int v7; // ebx
  HSTRING v8; // rbx
  WCHAR *StringRawBuffer; // rax
  const unsigned __int16 *v10; // r8
  PCWSTR v11; // rax
  __int64 v12; // rax
  int v13; // edi
  int v14; // eax
  const unsigned __int16 *v15; // r8
  int v17; // [rsp+20h] [rbp-E0h]
  int v18; // [rsp+20h] [rbp-E0h]
  int v19; // [rsp+20h] [rbp-E0h]
  HSTRING string; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v21[8]; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v22[3]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v23[40]; // [rsp+58h] [rbp-A8h] BYREF
  struct HWND__ v24; // [rsp+80h] [rbp-80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2C8h] [rbp+1C8h]

  wil::AcquireSRWLockExclusive(v21, (char *)this + 240);
  for ( i = 0; i < 7; ++i )
  {
    WindowsDeleteString(0);
    string = 0;
    ResourceStringById = SystemSettings::DataModel::GetResourceStringById(
                           (SystemSettings::DataModel *)(&off_1802BFE10)[2 * (int)i],
                           &string,
                           v5);
    v7 = ResourceStringById;
    if ( ResourceStringById < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x245,
        (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\restore\\quickmachinerecovery.cpp",
        (const char *)(unsigned int)ResourceStringById,
        v17);
      WindowsDeleteString(string);
      goto LABEL_15;
    }
    v8 = string;
    StringRawBuffer = (WCHAR *)WindowsGetStringRawBuffer(string, 0);
    if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)StringRawBuffer, v10) )
    {
      v13 = *((_DWORD *)&off_1802BFE10 + 4 * (int)i + 2);
      WindowsDeleteString(v8);
      goto LABEL_9;
    }
    WindowsDeleteString(v8);
  }
  v11 = WindowsGetStringRawBuffer((HSTRING)a2, 0);
  std::wstring::wstring(v23, v11);
  SystemSettings::DataModel::splitDelimitedString(v22, v23);
  if ( (unsigned __int64)((__int64)(v22[1] - v22[0]) >> 5) < 2 )
  {
    std::vector<std::wstring>::_Tidy(v22);
    std::wstring::_Tidy_deallocate(v23);
    v7 = -2147024809;
    goto LABEL_15;
  }
  v12 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v22[0]);
  v13 = _o__wtoi(v12);
  std::vector<std::wstring>::_Tidy(v22);
  std::wstring::_Tidy_deallocate(v23);
LABEL_9:
  v18 = v13;
  v14 = StringCchPrintfW((unsigned __int16 *)&v24, 0x104u, L"%s SetRetryInterval %d", L"QuickMachineRecovery", v18);
  v7 = v14;
  if ( v14 >= 0 )
  {
    v7 = SystemSettings::DataModel::ExecuteAdminFlowWait(0, &v24, v15);
    if ( v7 >= 0 )
      *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 11) + 24LL) + 240LL) = v13;
    else
      SystemSettings::DataModel::CSettingBase::OnValueChanged(this, L"Value");
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x262,
      (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\restore\\quickmachinerecovery.cpp",
      (const char *)(unsigned int)v14,
      v19);
  }
LABEL_15:
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(v21);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180108630  mov     [rsp-8+arg_10], rbx
0x180108635  mov     [rsp-8+arg_18], rsi
0x18010863a  push    rbp
0x18010863b  push    rdi
0x18010863c  push    r12
0x18010863e  push    r14
0x180108640  push    r15
0x180108642  lea     rbp, [rsp-1A0h]
0x18010864a  sub     rsp, 2A0h
0x180108651  mov     rax, cs:__security_cookie
0x180108658  xor     rax, rsp
0x18010865b  mov     [rbp+1C0h+var_30], rax
0x180108662  mov     r15, rdx
0x180108665  mov     rsi, rcx
0x180108668  lea     rdx, [rcx+0F0h]
0x18010866f  lea     rcx, [rsp+2C0h+var_288]
0x180108674  call    ?AcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x180108679  nop
0x18010867a  xor     edi, edi
0x18010867c  lea     r12, off_1802BFE10; "SystemSettings_Misc_QuickMachineRecover"...
0x180108683  xor     ecx, ecx; string
0x180108685  call    cs:__imp_WindowsDeleteString
0x18010868c  nop     dword ptr [rax+rax+00h]
0x180108691  mov     [rsp+2C0h+string], 0
0x18010869a  movsxd  r14, edi
0x18010869d  add     r14, r14
0x1801086a0  lea     rdx, [rsp+2C0h+string]; HSTRING *
0x1801086a5  mov     rcx, [r12+r14*8]; this
0x1801086a9  call    ?GetResourceStringById@DataModel@SystemSettings@@YAJPEBGPEAPEAUHSTRING__@@@Z; SystemSettings::DataModel::GetResourceStringById(ushort const *,HSTRING__ * *)
0x1801086ae  mov     ebx, eax
0x1801086b0  test    eax, eax
0x1801086b2  js      loc_18010880E
0x1801086b8  xor     edx, edx; length
0x1801086ba  mov     rbx, [rsp+2C0h+string]
0x1801086bf  mov     rcx, rbx; string
0x1801086c2  call    cs:__imp_WindowsGetStringRawBuffer
0x1801086c9  nop     dword ptr [rax+rax+00h]
0x1801086ce  mov     rdx, rax; HSTRING
0x1801086d1  mov     rcx, r15; this
0x1801086d4  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x1801086d9  test    al, al
0x1801086db  jnz     loc_180108785
0x1801086e1  mov     rcx, rbx; string
0x1801086e4  call    cs:__imp_WindowsDeleteString
0x1801086eb  nop     dword ptr [rax+rax+00h]
0x1801086f0  inc     edi
0x1801086f2  cmp     edi, 7
0x1801086f5  jb      short loc_180108683
0x1801086f7  xor     edx, edx; length
0x1801086f9  mov     rcx, r15; string
0x1801086fc  call    cs:__imp_WindowsGetStringRawBuffer
0x180108703  nop     dword ptr [rax+rax+00h]
0x180108708  mov     rdx, rax
0x18010870b  lea     rcx, [rsp+2C0h+var_268]
0x180108710  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180108715  lea     rdx, [rsp+2C0h+var_268]
0x18010871a  lea     rcx, [rsp+2C0h+var_280]
0x18010871f  call    ?splitDelimitedString@DataModel@SystemSettings@@YA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@4@G@Z; SystemSettings::DataModel::splitDelimitedString(std::wstring const &,ushort)
0x180108724  mov     rax, [rsp+2C0h+var_278]
0x180108729  mov     rcx, [rsp+2C0h+var_280]
0x18010872e  sub     rax, rcx
0x180108731  sar     rax, 5
0x180108735  cmp     rax, 2
0x180108739  jnb     short loc_180108759
0x18010873b  lea     rcx, [rsp+2C0h+var_280]
0x180108740  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180108745  lea     rcx, [rsp+2C0h+var_268]
0x18010874a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010874f  mov     ebx, 80070057h
0x180108754  jmp     loc_18010883C
0x180108759  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18010875e  mov     rcx, rax
0x180108761  call    cs:__imp__o__wtoi
0x180108768  nop     dword ptr [rax+rax+00h]
0x18010876d  mov     edi, eax
0x18010876f  lea     rcx, [rsp+2C0h+var_280]
0x180108774  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180108779  lea     rcx, [rsp+2C0h+var_268]
0x18010877e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180108783  jmp     short loc_180108799
0x180108785  mov     edi, [r12+r14*8+8]
0x18010878a  mov     rcx, rbx; string
0x18010878d  call    cs:__imp_WindowsDeleteString
0x180108794  nop     dword ptr [rax+rax+00h]
0x180108799  mov     [rsp+2C0h+var_2A0], edi; int
0x18010879d  lea     r9, aQuickmachinere; "QuickMachineRecovery"
0x1801087a4  lea     r8, aSSetretryinter; "%s SetRetryInterval %d"
0x1801087ab  mov     edx, 104h; unsigned __int64
0x1801087b0  lea     rcx, [rbp+1C0h+var_240]; unsigned __int16 *
0x1801087b4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1801087b9  mov     ebx, eax
0x1801087bb  test    eax, eax
0x1801087bd  jns     short loc_1801087DC
0x1801087bf  mov     rcx, [rbp+1C8h]; this
0x1801087c6  mov     r9d, eax; char *
0x1801087c9  lea     r8, aShellSystemset_65; "shell\\systemsettingsthreshold\\handler"...
0x1801087d0  mov     edx, 262h; void *
0x1801087d5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801087da  jmp     short loc_18010883C
0x1801087dc  lea     rdx, [rbp+1C0h+var_240]; HWND
0x1801087e0  xor     ecx, ecx; this
0x1801087e2  call    ?ExecuteAdminFlowWait@DataModel@SystemSettings@@YAJPEAUHWND__@@PEBG@Z; SystemSettings::DataModel::ExecuteAdminFlowWait(HWND__ *,ushort const *)
0x1801087e7  mov     ebx, eax
0x1801087e9  test    eax, eax
0x1801087eb  jns     short loc_1801087FE
0x1801087ed  lea     rdx, aValue_0; "Value"
0x1801087f4  mov     rcx, rsi; this
0x1801087f7  call    ?OnValueChanged@CSettingBase@DataModel@SystemSettings@@QEAAXPEBG@Z; SystemSettings::DataModel::CSettingBase::OnValueChanged(ushort const *)
0x1801087fc  jmp     short loc_18010883C
0x1801087fe  mov     rax, [rsi+58h]
0x180108802  mov     rcx, [rax+18h]
0x180108806  mov     [rcx+0F0h], edi
0x18010880c  jmp     short loc_18010883C
0x18010880e  mov     rcx, [rbp+1C8h]; this
0x180108815  mov     r9d, ebx; char *
0x180108818  lea     r8, aShellSystemset_65; "shell\\systemsettingsthreshold\\handler"...
0x18010881f  mov     edx, 245h; void *
0x180108824  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180108829  nop
0x18010882a  mov     rcx, [rsp+2C0h+string]; string
0x18010882f  call    cs:__imp_WindowsDeleteString
0x180108836  nop     dword ptr [rax+rax+00h]
0x18010883b  nop
0x18010883c  lea     rcx, [rsp+2C0h+var_288]
0x180108841  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180108846  mov     eax, ebx
0x180108848  mov     rcx, [rbp+1C0h+var_30]
0x18010884f  xor     rcx, rsp; StackCookie
0x180108852  call    __security_check_cookie
0x180108857  lea     r11, [rsp+2C0h+var_20]
0x18010885f  mov     rbx, [r11+40h]
0x180108863  mov     rsi, [r11+48h]
0x180108867  mov     rsp, r11
0x18010886a  pop     r15
0x18010886c  pop     r14
0x18010886e  pop     r12
0x180108870  pop     rdi
0x180108871  pop     rbp
0x180108872  retn
```
