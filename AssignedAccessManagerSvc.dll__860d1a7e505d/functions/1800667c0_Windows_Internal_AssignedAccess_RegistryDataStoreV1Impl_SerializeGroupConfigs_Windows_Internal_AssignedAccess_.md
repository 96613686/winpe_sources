# Windows::Internal::AssignedAccess::RegistryDataStoreV1Impl::SerializeGroupConfigs(Windows::Internal::AssignedAccess::RegistryKeyBroker &,std::vector<wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessConfig,wil::err_exception_policy>,std::allocator<wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessConfig,wil::err_exception_policy>>> const &)

- ea: `0x1800667c0`
- end: `0x180066920`
- name: `?SerializeGroupConfigs@RegistryDataStoreV1Impl@AssignedAccess@Internal@Windows@@AEAAXAEAVRegistryKeyBroker@234@AEBV?$vector@V?$com_ptr_t@UIAssignedAccessConfig@AssignedAccess@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UIAssignedAccessConfig@AssignedAccess@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@@Z`
- size: `352`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180065450`

## callees

- `0x180006640`
- `0x180010c98`
- `0x180014a5c`
- `0x18002001c`
- `0x180020050`
- `0x18002b190`
- `0x18003bfac`
- `0x18003d1a8`
- `0x1800575cc`
- `0x18006309c`
- `0x180064314`
- `0x1800667c0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800668a4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800668a4`

## string_xrefs

- `0x1800668da`: `onecoreuap\internal\base\inc\embedded\registrykey.h`
- `0x1800668ef`: `onecoreuap\base\embedded\sys\lockdown\runtime\worker\registrydatastorev1impl.cpp`
- `0x18006680f`: `GroupConfig`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
unsigned __int64 __fastcall Windows::Internal::AssignedAccess::RegistryDataStoreV1Impl::SerializeGroupConfigs(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  unsigned __int64 i; // rbx
  unsigned __int64 result; // rax
  struct Windows::Internal::AssignedAccess::IAssignedAccessConfig *v7; // r8
  int v8; // eax
  const WCHAR *v9; // rax
  unsigned int v10; // eax
  unsigned int lpData; // [rsp+20h] [rbp-49h]
  BYTE Data[8]; // [rsp+30h] [rbp-39h] BYREF
  _BYTE v13[16]; // [rsp+38h] [rbp-31h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-21h]
  __int64 v15; // [rsp+50h] [rbp-19h]
  _BYTE *v16; // [rsp+58h] [rbp-11h]
  char v17; // [rsp+60h] [rbp-9h]
  _BYTE v18[32]; // [rsp+68h] [rbp-1h] BYREF
  _BYTE v19[32]; // [rsp+88h] [rbp+1Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  for ( i = 0; ; ++i )
  {
    result = (__int64)(a3[1] - *a3) >> 3;
    if ( i >= result )
      break;
    std::_Integral_to_string<unsigned short,unsigned __int64>(v18, i);
    std::operator+<unsigned short>(v19, L"GroupConfig", v18);
    std::wstring::_Tidy_deallocate(v18);
    Windows::Internal::AssignedAccess::RegistryKeyBroker::Create(a2, v13, v19);
    v15 = a2;
    v16 = v19;
    v17 = 1;
    v8 = Windows::Internal::AssignedAccess::Details::Serialize(
           (Windows::Internal::AssignedAccess::Details *)v13,
           *(struct Windows::Internal::AssignedAccess::RegistryKeyBroker **)(*a3 + 8 * i),
           v7);
    if ( v8 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x15E,
        (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\registrydatastorev1impl.cpp",
        (const char *)(unsigned int)v8,
        lpData);
    *(_DWORD *)Data = i;
    std::wstring::wstring(v18, L"Index");
    v9 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v18);
    v10 = RegSetValueExW(hKey, v9, 0, 4u, Data, 4u);
    if ( v10 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0xCD,
        (unsigned int)"onecoreuap\\internal\\base\\inc\\embedded\\registrykey.h",
        (const char *)v10,
        lpData);
    std::wstring::_Tidy_deallocate(v18);
    Windows::Internal::AssignedAccess::RegistryKeyBroker::~RegistryKeyBroker((Windows::Internal::AssignedAccess::RegistryKeyBroker *)v13);
    std::wstring::_Tidy_deallocate(v19);
  }
  return result;
}

```

## disassembly

```asm
0x1800667c0  mov     [rsp-8+arg_0], rbx
0x1800667c5  push    rbp
0x1800667c6  push    rsi
0x1800667c7  push    rdi
0x1800667c8  lea     rbp, [rsp-47h]
0x1800667cd  sub     rsp, 0B0h
0x1800667d4  mov     rax, cs:__security_cookie
0x1800667db  xor     rax, rsp
0x1800667de  mov     [rbp+57h+var_18], rax
0x1800667e2  mov     rdi, r8
0x1800667e5  mov     rsi, rdx
0x1800667e8  xor     ebx, ebx
0x1800667ea  mov     rax, [rdi+8]
0x1800667ee  sub     rax, [rdi]
0x1800667f1  sar     rax, 3
0x1800667f5  cmp     rbx, rax
0x1800667f8  jnb     loc_180066901
0x1800667fe  mov     rdx, rbx
0x180066801  lea     rcx, [rbp+57h+var_58]
0x180066805  call    ??$_Integral_to_string@G_K@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@_K@Z; std::_Integral_to_string<ushort,unsigned __int64>(unsigned __int64)
0x18006680a  nop
0x18006680b  lea     r8, [rbp+57h+var_58]
0x18006680f  lea     rdx, aGroupconfig; "GroupConfig"
0x180066816  lea     rcx, [rbp+57h+var_38]
0x18006681a  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEBG$$QEAV10@@Z; std::operator+<ushort>(ushort const * const,std::wstring &&)
0x18006681f  nop
0x180066820  lea     rcx, [rbp+57h+var_58]
0x180066824  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180066829  lea     r8, [rbp+57h+var_38]
0x18006682d  lea     rdx, [rbp+57h+var_88]
0x180066831  mov     rcx, rsi
0x180066834  call    ?Create@RegistryKeyBroker@AssignedAccess@Internal@Windows@@QEAA?AV1234@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KK@Z; Windows::Internal::AssignedAccess::RegistryKeyBroker::Create(std::wstring const &,ulong,ulong)
0x180066839  nop
0x18006683a  mov     [rbp+57h+var_70], rsi
0x18006683e  lea     rax, [rbp+57h+var_38]
0x180066842  mov     [rbp+57h+var_68], rax
0x180066846  mov     [rbp+57h+var_60], 1
0x18006684a  mov     rdx, [rdi]
0x18006684d  mov     rdx, [rdx+rbx*8]; struct Windows::Internal::AssignedAccess::RegistryKeyBroker *
0x180066851  lea     rcx, [rbp+57h+var_88]; this
0x180066855  call    ?Serialize@Details@AssignedAccess@Internal@Windows@@YAJAEAVRegistryKeyBroker@234@PEAUIAssignedAccessConfig@234@@Z; Windows::Internal::AssignedAccess::Details::Serialize(Windows::Internal::AssignedAccess::RegistryKeyBroker &,Windows::Internal::AssignedAccess::IAssignedAccessConfig *)
0x18006685a  mov     rcx, [rbp+5Fh]; this
0x18006685e  test    eax, eax
0x180066860  js      loc_1800668EC
0x180066866  mov     dword ptr [rbp+57h+Data], ebx
0x180066869  lea     rdx, aIndex; "Index"
0x180066870  lea     rcx, [rbp+57h+var_58]
0x180066874  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180066879  nop
0x18006687a  lea     rcx, [rbp+57h+var_58]
0x18006687e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180066883  mov     rdx, rax; lpValueName
0x180066886  mov     [rsp+0C0h+cbData], 4; cbData
0x18006688e  lea     rax, [rbp+57h+Data]
0x180066892  mov     [rsp+0C0h+lpData], rax; unsigned int
0x180066897  mov     r9d, 4; dwType
0x18006689d  xor     r8d, r8d; Reserved
0x1800668a0  mov     rcx, [rbp+57h+hKey]; hKey
0x1800668a4  call    cs:__imp_RegSetValueExW
0x1800668aa  mov     rcx, [rbp+5Fh]; this
0x1800668ae  test    eax, eax
0x1800668b0  jnz     short loc_1800668D7
0x1800668b2  lea     rcx, [rbp+57h+var_58]
0x1800668b6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800668bb  nop
0x1800668bc  lea     rcx, [rbp+57h+var_88]; this
0x1800668c0  call    ??1RegistryKeyBroker@AssignedAccess@Internal@Windows@@QEAA@XZ; Windows::Internal::AssignedAccess::RegistryKeyBroker::~RegistryKeyBroker(void)
0x1800668c5  nop
0x1800668c6  lea     rcx, [rbp+57h+var_38]
0x1800668ca  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800668cf  inc     rbx
0x1800668d2  jmp     loc_1800667EA
0x1800668d7  mov     r9d, eax; char *
0x1800668da  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\base\\inc\\embedd"...
0x1800668e1  mov     edx, 0CDh; void *
0x1800668e6  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x1800668ec  mov     r9d, eax; char *
0x1800668ef  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x1800668f6  mov     edx, 15Eh; void *
0x1800668fb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180066901  mov     rcx, [rbp+57h+var_18]
0x180066905  xor     rcx, rsp; StackCookie
0x180066908  call    __security_check_cookie
0x18006690d  mov     rbx, [rsp+0C0h+arg_0]
0x180066915  add     rsp, 0B0h
0x18006691c  pop     rdi
0x18006691d  pop     rsi
0x18006691e  pop     rbp
0x18006691f  retn
```
