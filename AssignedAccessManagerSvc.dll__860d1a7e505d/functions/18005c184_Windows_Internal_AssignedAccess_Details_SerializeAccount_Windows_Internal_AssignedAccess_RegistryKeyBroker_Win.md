# Windows::Internal::AssignedAccess::Details::SerializeAccount<Windows::Internal::AssignedAccess::RegistryKeyBroker>(Windows::Internal::AssignedAccess::RegistryKeyBroker &,Windows::Internal::AssignedAccess::IAssignedAccessAccount *)

- ea: `0x18005c184`
- end: `0x18005c435`
- name: `??$SerializeAccount@VRegistryKeyBroker@AssignedAccess@Internal@Windows@@@Details@AssignedAccess@Internal@Windows@@YAJAEAVRegistryKeyBroker@123@PEAUIAssignedAccessAccount@123@@Z`
- size: `689`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180063058`

## callees

- `0x180006640`
- `0x18000b6b4`
- `0x180010c98`
- `0x180014a5c`
- `0x18002001c`
- `0x1800271e4`
- `0x18002901c`
- `0x18002b190`
- `0x18005c184`
- `0x180063b68`
- `0x180096010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005c214`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005c2d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005c214`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005c2d4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005c3c0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005c3c0`

## string_xrefs

- `0x18005c3d5`: `onecoreuap\internal\base\inc\embedded\registrykey.h`
- `0x18005c1ea`: `onecoreuap\base\embedded\sys\lockdown\runtime\worker\registryserializer.cpp`
- `0x18005c29f`: `onecoreuap\base\embedded\sys\lockdown\runtime\worker\registryserializer.cpp`
- `0x18005c34f`: `onecoreuap\base\embedded\sys\lockdown\runtime\worker\registryserializer.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7 #try_helpers=1
__int64 __fastcall Windows::Internal::AssignedAccess::Details::SerializeAccount<Windows::Internal::AssignedAccess::RegistryKeyBroker>(
        __int64 a1,
        __int64 a2)
{
  __int64 (__fastcall *v4)(__int64, HSTRING *); // rbx
  int v5; // eax
  unsigned int v6; // ebx
  PCWSTR StringRawBuffer; // rax
  __int64 (__fastcall *v9)(__int64, HSTRING *); // rbx
  int v10; // eax
  unsigned int v11; // ebx
  PCWSTR v12; // rax
  int v13; // eax
  unsigned int v14; // ebx
  const WCHAR *v15; // rax
  unsigned int v16; // eax
  int lpData; // [rsp+20h] [rbp-88h]
  unsigned int lpDataa; // [rsp+20h] [rbp-88h]
  BYTE Data[8]; // [rsp+30h] [rbp-78h] BYREF
  HSTRING string; // [rsp+38h] [rbp-70h] BYREF
  HSTRING v21; // [rsp+40h] [rbp-68h] BYREF
  int v22; // [rsp+48h] [rbp-60h] BYREF
  _BYTE v23[32]; // [rsp+50h] [rbp-58h] BYREF
  _BYTE v24[32]; // [rsp+70h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  string = 0;
  v4 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)a2 + 48LL);
  wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
    &string,
    0);
  v5 = v4(a2, &string);
  v6 = v5;
  if ( v5 >= 0 )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    std::wstring::wstring(v23, StringRawBuffer);
    std::wstring::wstring(v24, L"Id");
    Windows::Internal::AssignedAccess::RegistryKeyBroker::SetString(a1, v24, v23);
    std::wstring::_Tidy_deallocate(v24);
    std::wstring::_Tidy_deallocate(v23);
    v21 = 0;
    v9 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)a2 + 64LL);
    wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
      &v21,
      0);
    v10 = v9(a2, &v21);
    v11 = v10;
    if ( v10 >= 0 )
    {
      v12 = WindowsGetStringRawBuffer(v21, 0);
      std::wstring::wstring(v24, v12);
      std::wstring::wstring(v23, L"Name");
      Windows::Internal::AssignedAccess::RegistryKeyBroker::SetString(a1, v23, v24);
      std::wstring::_Tidy_deallocate(v23);
      std::wstring::_Tidy_deallocate(v24);
      v22 = 0;
      v13 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)a2 + 80LL))(a2, &v22);
      v14 = v13;
      if ( v13 >= 0 )
      {
        *(_DWORD *)Data = v22;
        std::wstring::wstring(v23, L"Type");
        v15 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v23);
        v16 = RegSetValueExW(*(HKEY *)(a1 + 16), v15, 0, 4u, Data, 4u);
        if ( v16 )
          wil::details::in1diag3::_Throw_Win32(
            retaddr,
            (void *)0xCD,
            (unsigned int)"onecoreuap\\internal\\base\\inc\\embedded\\registrykey.h",
            (const char *)v16,
            lpDataa);
        std::wstring::_Tidy_deallocate(v23);
        wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v21);
        wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&string);
        return 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x15B,
          (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\registryserializer.cpp",
          (const char *)(unsigned int)v13,
          lpData);
        wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v21);
        wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&string);
        return v14;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x157,
        (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\registryserializer.cpp",
        (const char *)(unsigned int)v10,
        lpData);
      wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v21);
      wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&string);
      return v11;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x153,
      (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\registryserializer.cpp",
      (const char *)(unsigned int)v5,
      lpData);
    wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&string);
    return v6;
  }
}

```

## disassembly

```asm
0x18005c184  mov     r11, rsp
0x18005c187  mov     [r11+18h], rbx
0x18005c18b  mov     [r11+20h], rsi
0x18005c18f  push    rdi
0x18005c190  sub     rsp, 0A0h
0x18005c197  mov     rax, cs:__security_cookie
0x18005c19e  xor     rax, rsp
0x18005c1a1  mov     [rsp+0A8h+var_18], rax
0x18005c1a9  mov     rdi, rdx
0x18005c1ac  mov     rsi, rcx
0x18005c1af  mov     qword ptr [r11-70h], 0
0x18005c1b7  mov     rax, [rdx]
0x18005c1ba  mov     rbx, [rax+30h]
0x18005c1be  xor     edx, edx
0x18005c1c0  lea     rcx, [r11-70h]
0x18005c1c4  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x18005c1c9  lea     rdx, [rsp+0A8h+string]
0x18005c1ce  mov     rcx, rdi
0x18005c1d1  mov     rax, rbx
0x18005c1d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c1d9  mov     ebx, eax
0x18005c1db  test    eax, eax
0x18005c1dd  jns     short loc_18005C20D
0x18005c1df  mov     rcx, [rsp+0A8h]; this
0x18005c1e7  mov     r9d, eax; char *
0x18005c1ea  lea     r8, aOnecoreuapBase_40; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x18005c1f1  mov     edx, 153h; void *
0x18005c1f6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005c1fb  nop
0x18005c1fc  lea     rcx, [rsp+0A8h+string]
0x18005c201  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x18005c206  mov     eax, ebx
0x18005c208  jmp     loc_18005C40F
0x18005c20d  xor     edx, edx; length
0x18005c20f  mov     rcx, [rsp+0A8h+string]; string
0x18005c214  call    cs:__imp_WindowsGetStringRawBuffer
0x18005c21a  mov     rdx, rax
0x18005c21d  lea     rcx, [rsp+0A8h+var_58]
0x18005c222  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18005c227  nop
0x18005c228  lea     rdx, aId; "Id"
0x18005c22f  lea     rcx, [rsp+0A8h+var_38]
0x18005c234  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18005c239  nop
0x18005c23a  lea     r8, [rsp+0A8h+var_58]
0x18005c23f  lea     rdx, [rsp+0A8h+var_38]
0x18005c244  mov     rcx, rsi
0x18005c247  call    ?SetString@RegistryKeyBroker@AssignedAccess@Internal@Windows@@QEBAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; Windows::Internal::AssignedAccess::RegistryKeyBroker::SetString(std::wstring const &,std::wstring const &)
0x18005c24c  nop
0x18005c24d  lea     rcx, [rsp+0A8h+var_38]
0x18005c252  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005c257  nop
0x18005c258  lea     rcx, [rsp+0A8h+var_58]
0x18005c25d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005c262  mov     [rsp+0A8h+var_68], 0
0x18005c26b  mov     rax, [rdi]
0x18005c26e  mov     rbx, [rax+40h]
0x18005c272  xor     edx, edx
0x18005c274  lea     rcx, [rsp+0A8h+var_68]
0x18005c279  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x18005c27e  lea     rdx, [rsp+0A8h+var_68]
0x18005c283  mov     rcx, rdi
0x18005c286  mov     rax, rbx
0x18005c289  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c28e  mov     ebx, eax
0x18005c290  test    eax, eax
0x18005c292  jns     short loc_18005C2CD
0x18005c294  mov     rcx, [rsp+0A8h]; this
0x18005c29c  mov     r9d, eax; char *
0x18005c29f  lea     r8, aOnecoreuapBase_40; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x18005c2a6  mov     edx, 157h; void *
0x18005c2ab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005c2b0  nop
0x18005c2b1  lea     rcx, [rsp+0A8h+var_68]
0x18005c2b6  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x18005c2bb  nop
0x18005c2bc  lea     rcx, [rsp+0A8h+string]
0x18005c2c1  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x18005c2c6  mov     eax, ebx
0x18005c2c8  jmp     loc_18005C40F
0x18005c2cd  xor     edx, edx; length
0x18005c2cf  mov     rcx, [rsp+0A8h+var_68]; string
0x18005c2d4  call    cs:__imp_WindowsGetStringRawBuffer
0x18005c2da  mov     rdx, rax
0x18005c2dd  lea     rcx, [rsp+0A8h+var_38]
0x18005c2e2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18005c2e7  nop
0x18005c2e8  lea     rdx, aName; "Name"
0x18005c2ef  lea     rcx, [rsp+0A8h+var_58]
0x18005c2f4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18005c2f9  nop
0x18005c2fa  lea     r8, [rsp+0A8h+var_38]
0x18005c2ff  lea     rdx, [rsp+0A8h+var_58]
0x18005c304  mov     rcx, rsi
0x18005c307  call    ?SetString@RegistryKeyBroker@AssignedAccess@Internal@Windows@@QEBAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; Windows::Internal::AssignedAccess::RegistryKeyBroker::SetString(std::wstring const &,std::wstring const &)
0x18005c30c  nop
0x18005c30d  lea     rcx, [rsp+0A8h+var_58]
0x18005c312  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005c317  nop
0x18005c318  lea     rcx, [rsp+0A8h+var_38]
0x18005c31d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005c322  mov     [rsp+0A8h+var_60], 0
0x18005c32a  mov     rax, [rdi]
0x18005c32d  lea     rdx, [rsp+0A8h+var_60]
0x18005c332  mov     rcx, rdi
0x18005c335  mov     rax, [rax+50h]
0x18005c339  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c33e  mov     ebx, eax
0x18005c340  test    eax, eax
0x18005c342  jns     short loc_18005C37D
0x18005c344  mov     rcx, [rsp+0A8h]; this
0x18005c34c  mov     r9d, eax; char *
0x18005c34f  lea     r8, aOnecoreuapBase_40; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x18005c356  mov     edx, 15Bh; void *
0x18005c35b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005c360  nop
0x18005c361  lea     rcx, [rsp+0A8h+var_68]
0x18005c366  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x18005c36b  nop
0x18005c36c  lea     rcx, [rsp+0A8h+string]
0x18005c371  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x18005c376  mov     eax, ebx
0x18005c378  jmp     loc_18005C40F
0x18005c37d  mov     eax, [rsp+0A8h+var_60]
0x18005c381  mov     dword ptr [rsp+0A8h+Data], eax
0x18005c385  lea     rdx, aType; "Type"
0x18005c38c  lea     rcx, [rsp+0A8h+var_58]
0x18005c391  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18005c396  nop
0x18005c397  lea     rcx, [rsp+0A8h+var_58]
0x18005c39c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18005c3a1  mov     rdx, rax; lpValueName
0x18005c3a4  mov     r9d, 4; dwType
0x18005c3aa  mov     [rsp+0A8h+cbData], r9d; cbData
0x18005c3af  lea     rax, [rsp+0A8h+Data]
0x18005c3b4  mov     [rsp+0A8h+lpData], rax; unsigned int
0x18005c3b9  xor     r8d, r8d; Reserved
0x18005c3bc  mov     rcx, [rsi+10h]; hKey
0x18005c3c0  call    cs:__imp_RegSetValueExW
0x18005c3c6  mov     rcx, [rsp+0A8h]; this
0x18005c3ce  test    eax, eax
0x18005c3d0  jz      short loc_18005C3E7
0x18005c3d2  mov     r9d, eax; char *
0x18005c3d5  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\base\\inc\\embedd"...
0x18005c3dc  mov     edx, 0CDh; void *
0x18005c3e1  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18005c3e7  lea     rcx, [rsp+0A8h+var_58]
0x18005c3ec  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005c3f1  nop
0x18005c3f2  lea     rcx, [rsp+0A8h+var_68]
0x18005c3f7  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x18005c3fc  nop
0x18005c3fd  lea     rcx, [rsp+0A8h+string]
0x18005c402  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x18005c407  xor     eax, eax
0x18005c409  jmp     short loc_18005C40F
0x18005c40b  mov     eax, dword ptr [rsp+0A8h+Data]
0x18005c40f  mov     rcx, [rsp+0A8h+var_18]
0x18005c417  xor     rcx, rsp; StackCookie
0x18005c41a  call    __security_check_cookie
0x18005c41f  lea     r11, [rsp+0A8h+var_8]
0x18005c427  mov     rbx, [r11+20h]
0x18005c42b  mov     rsi, [r11+28h]
0x18005c42f  mov     rsp, r11
0x18005c432  pop     rdi
0x18005c433  retn
```
