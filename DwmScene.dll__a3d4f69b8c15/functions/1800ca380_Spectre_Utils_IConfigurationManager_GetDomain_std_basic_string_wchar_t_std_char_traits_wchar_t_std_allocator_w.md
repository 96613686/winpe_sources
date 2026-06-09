# Spectre::Utils::IConfigurationManager::GetDomain(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x1800ca380`
- end: `0x1800ca4a2`
- name: `?GetDomain@IConfigurationManager@Utils@Spectre@@UEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV45@@Z`
- size: `290`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config`

## callees

- `0x18000ca90`
- `0x18000dfa2`
- `0x180011f64`
- `0x180013568`
- `0x18001424c`
- `0x1800142d0`
- `0x18001e21c`
- `0x18001f170`
- `0x18001f8bc`
- `0x1800ca24c`
- `0x1800ca380`

## string_xrefs

- `0x1800ca473`: `IConfigurationManager::GetDomain() -- empty string is not a valid property name`
- `0x1800ca3e4`: `IConfigurationManager::GetDomain() -- property domain must begin and end with a slash, e.g. /CustomDomain/Category.Value`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Spectre::Utils::IConfigurationManager::GetDomain(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v5; // r8
  __int64 v6; // rax
  __int64 v7; // rax
  _BYTE v9[32]; // [rsp+30h] [rbp-9h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+50h] [rbp+17h] BYREF

  if ( !*(_QWORD *)(a3 + 16) )
  {
    std::string::string(v9, "IConfigurationManager::GetDomain() -- empty string is not a valid property name");
    Spectre::Utils::SpectreInvalidArgException::SpectreInvalidArgException(pExceptionObject, v9);
    throw (Spectre::Utils::SpectreInvalidArgException *)pExceptionObject;
  }
  if ( *(_WORD *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a3) == 47 )
  {
    v6 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v5);
    v7 = std::_Traits_find_ch<std::char_traits<wchar_t>>(v6);
    if ( v7 == -1 )
    {
      std::string::string(
        v9,
        "IConfigurationManager::GetDomain() -- property domain must begin and end with a slash, e.g. /CustomDomain/Category.Value");
      Spectre::Utils::SpectreInvalidArgException::SpectreInvalidArgException(pExceptionObject, v9);
      throw (Spectre::Utils::SpectreInvalidArgException *)pExceptionObject;
    }
    std::wstring::substr(a3, v9, 1, v7 - 1);
    std::wstring::wstring(a2, v9);
    std::wstring::_Tidy_deallocate(v9);
  }
  else
  {
    std::wstring::wstring(a2, Spectre::Utils::kConfigurationDomain_Standard);
  }
  return a2;
}

```

## disassembly

```asm
0x1800ca380  mov     [rsp-8+arg_0], rbx
0x1800ca385  mov     [rsp-8+arg_18], rdi
0x1800ca38a  push    rbp
0x1800ca38b  lea     rbp, [rsp-57h]
0x1800ca390  sub     rsp, 90h
0x1800ca397  mov     rax, cs:__security_cookie
0x1800ca39e  xor     rax, rsp
0x1800ca3a1  mov     [rbp+57h+var_8], rax
0x1800ca3a5  mov     rdi, r8
0x1800ca3a8  mov     rbx, rdx
0x1800ca3ab  mov     [rbp+57h+var_68], rdx
0x1800ca3af  mov     rdx, [r8+10h]
0x1800ca3b3  test    rdx, rdx
0x1800ca3b6  jz      loc_1800CA473
0x1800ca3bc  mov     rcx, r8
0x1800ca3bf  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800ca3c4  cmp     word ptr [rax], 2Fh ; '/'
0x1800ca3c8  jnz     loc_1800CA462
0x1800ca3ce  mov     rcx, r8
0x1800ca3d1  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800ca3d6  mov     rcx, rax
0x1800ca3d9  call    ??$_Traits_find_ch@U?$char_traits@_W@std@@@std@@YA_KQEB_W_K1_W@Z; std::_Traits_find_ch<std::char_traits<wchar_t>>(wchar_t const * const,unsigned __int64,unsigned __int64,wchar_t)
0x1800ca3de  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800ca3e2  jnz     short loc_1800CA413
0x1800ca3e4  lea     rdx, aIconfiguration_0; "IConfigurationManager::GetDomain() -- p"...
0x1800ca3eb  lea     rcx, [rbp+57h+var_60]
0x1800ca3ef  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800ca3f4  nop
0x1800ca3f5  lea     rdx, [rbp+57h+var_60]
0x1800ca3f9  lea     rcx, [rbp+57h+pExceptionObject]
0x1800ca3fd  call    ??0SpectreInvalidArgException@Utils@Spectre@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@_N@Z; Spectre::Utils::SpectreInvalidArgException::SpectreInvalidArgException(std::string const &,bool)
0x1800ca402  lea     rdx, _TI4?AUSpectreInvalidArgException@Utils@Spectre@@; pThrowInfo
0x1800ca409  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800ca40d  call    _CxxThrowException_0
0x1800ca413  lea     r9, [rax-1]
0x1800ca417  mov     r8d, 1
0x1800ca41d  lea     rdx, [rbp+57h+var_60]
0x1800ca421  mov     rcx, rdi
0x1800ca424  call    ?substr@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x1800ca429  lea     rdx, [rbp+57h+var_60]
0x1800ca42d  mov     rcx, rbx
0x1800ca430  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x1800ca435  lea     rcx, [rbp+57h+var_60]
0x1800ca439  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800ca43e  mov     rax, rbx
0x1800ca441  mov     rcx, [rbp+57h+var_8]
0x1800ca445  xor     rcx, rsp; StackCookie
0x1800ca448  call    __security_check_cookie
0x1800ca44d  lea     r11, [rsp+90h+var_s0]
0x1800ca455  mov     rbx, [r11+10h]
0x1800ca459  mov     rdi, [r11+28h]
0x1800ca45d  mov     rsp, r11
0x1800ca460  pop     rbp
0x1800ca461  retn
0x1800ca462  lea     rdx, ?kConfigurationDomain_Standard@Utils@Spectre@@3V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const Spectre::Utils::kConfigurationDomain_Standard
0x1800ca469  mov     rcx, rbx
0x1800ca46c  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800ca471  jmp     short loc_1800CA43E
0x1800ca473  lea     rdx, aIconfiguration; "IConfigurationManager::GetDomain() -- e"...
0x1800ca47a  lea     rcx, [rbp+57h+var_60]
0x1800ca47e  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800ca483  nop
0x1800ca484  lea     rdx, [rbp+57h+var_60]
0x1800ca488  lea     rcx, [rbp+57h+pExceptionObject]
0x1800ca48c  call    ??0SpectreInvalidArgException@Utils@Spectre@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@_N@Z; Spectre::Utils::SpectreInvalidArgException::SpectreInvalidArgException(std::string const &,bool)
0x1800ca491  lea     rdx, _TI4?AUSpectreInvalidArgException@Utils@Spectre@@; pThrowInfo
0x1800ca498  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800ca49c  call    _CxxThrowException_0
```
