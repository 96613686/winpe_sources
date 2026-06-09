# Windows::Internal::AssignedAccess::Details::Serialize<Windows::Internal::AssignedAccess::RegistryKeyBroker>(Windows::Internal::AssignedAccess::RegistryKeyBroker &,Windows::Internal::AssignedAccess::IAssignedAccessApplication *)

- ea: `0x18005bd08`
- end: `0x18005c17c`
- name: `??$Serialize@VRegistryKeyBroker@AssignedAccess@Internal@Windows@@@Details@AssignedAccess@Internal@Windows@@YAJAEAVRegistryKeyBroker@123@PEAUIAssignedAccessApplication@123@@Z`
- size: `1140`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18005d4e8`

## callees

- `0x180006640`
- `0x18000b6b4`
- `0x180010c98`
- `0x180014a5c`
- `0x18002001c`
- `0x1800271e4`
- `0x18002901c`
- `0x18002b190`
- `0x18005bd08`
- `0x180063b68`
- `0x180096010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005bd98`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005be58`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005bf23`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005bd98`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005be58`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005bf23`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005c01d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005c0fc`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005c01d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005c0fc`

## string_xrefs

- `0x18005c032`: `onecoreuap\internal\base\inc\embedded\registrykey.h`
- `0x18005c111`: `onecoreuap\internal\base\inc\embedded\registrykey.h`
- `0x18005bd6e`: `onecoreuap\base\embedded\sys\lockdown\runtime\worker\registryserializer.cpp`
- `0x18005be23`: `onecoreuap\base\embedded\sys\lockdown\runtime\worker\registryserializer.cpp`
- `0x18005bee3`: `onecoreuap\base\embedded\sys\lockdown\runtime\worker\registryserializer.cpp`
- `0x18005bf9e`: `onecoreuap\base\embedded\sys\lockdown\runtime\worker\registryserializer.cpp`
- `0x18005c078`: `onecoreuap\base\embedded\sys\lockdown\runtime\worker\registryserializer.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=10 #try_helpers=1
__int64 __fastcall Windows::Internal::AssignedAccess::Details::Serialize<Windows::Internal::AssignedAccess::RegistryKeyBroker>(
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
  __int64 (__fastcall *v13)(__int64, HSTRING *); // rbx
  int v14; // eax
  unsigned int v15; // ebx
  PCWSTR v16; // rax
  int v17; // eax
  unsigned int v18; // ebx
  const WCHAR *v19; // rax
  unsigned int v20; // eax
  int v21; // eax
  unsigned int v22; // ebx
  const WCHAR *v23; // rax
  unsigned int v24; // eax
  int lpData; // [rsp+20h] [rbp-88h]
  unsigned int lpDataa; // [rsp+20h] [rbp-88h]
  unsigned int lpDatab; // [rsp+20h] [rbp-88h]
  _BYTE v28[4]; // [rsp+30h] [rbp-78h] BYREF
  BYTE Data[4]; // [rsp+34h] [rbp-74h] BYREF
  HSTRING string; // [rsp+38h] [rbp-70h] BYREF
  HSTRING v31; // [rsp+40h] [rbp-68h] BYREF
  HSTRING v32; // [rsp+48h] [rbp-60h] BYREF
  int v33; // [rsp+50h] [rbp-58h] BYREF
  _BYTE v34[32]; // [rsp+58h] [rbp-50h] BYREF
  _BYTE v35[32]; // [rsp+78h] [rbp-30h] BYREF
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
    std::wstring::wstring(v34, StringRawBuffer);
    std::wstring::wstring(v35, L"AppId");
    Windows::Internal::AssignedAccess::RegistryKeyBroker::SetString(a1, v35, v34);
    std::wstring::_Tidy_deallocate(v35);
    std::wstring::_Tidy_deallocate(v34);
    v31 = 0;
    v9 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)a2 + 112LL);
    wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
      &v31,
      0);
    v10 = v9(a2, &v31);
    v11 = v10;
    if ( v10 >= 0 )
    {
      v12 = WindowsGetStringRawBuffer(v31, 0);
      std::wstring::wstring(v35, v12);
      std::wstring::wstring(v34, L"Publisher");
      Windows::Internal::AssignedAccess::RegistryKeyBroker::SetString(a1, v34, v35);
      std::wstring::_Tidy_deallocate(v34);
      std::wstring::_Tidy_deallocate(v35);
      v32 = 0;
      v13 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)a2 + 80LL);
      wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
        &v32,
        0);
      v14 = v13(a2, &v32);
      v15 = v14;
      if ( v14 >= 0 )
      {
        v16 = WindowsGetStringRawBuffer(v32, 0);
        std::wstring::wstring(v35, v16);
        std::wstring::wstring(v34, L"Arguments");
        Windows::Internal::AssignedAccess::RegistryKeyBroker::SetString(a1, v34, v35);
        std::wstring::_Tidy_deallocate(v34);
        std::wstring::_Tidy_deallocate(v35);
        v33 = 0;
        v17 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)a2 + 64LL))(a2, &v33);
        v18 = v17;
        if ( v17 >= 0 )
        {
          *(_DWORD *)Data = v33;
          std::wstring::wstring(v34, L"AppType");
          v19 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v34);
          v20 = RegSetValueExW(*(HKEY *)(a1 + 16), v19, 0, 4u, Data, 4u);
          if ( v20 )
            wil::details::in1diag3::_Throw_Win32(
              retaddr,
              (void *)0xCD,
              (unsigned int)"onecoreuap\\internal\\base\\inc\\embedded\\registrykey.h",
              (const char *)v20,
              lpDataa);
          std::wstring::_Tidy_deallocate(v34);
          v28[0] = 0;
          v21 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)a2 + 96LL))(a2, v28);
          v22 = v21;
          if ( v21 >= 0 )
          {
            *(_DWORD *)Data = v28[0] != 0;
            std::wstring::wstring(v34, L"AutoLaunch");
            v23 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v34);
            v24 = RegSetValueExW(*(HKEY *)(a1 + 16), v23, 0, 4u, Data, 4u);
            if ( v24 )
              wil::details::in1diag3::_Throw_Win32(
                retaddr,
                (void *)0xCD,
                (unsigned int)"onecoreuap\\internal\\base\\inc\\embedded\\registrykey.h",
                (const char *)v24,
                lpDatab);
            std::wstring::_Tidy_deallocate(v34);
            wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v32);
            wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v31);
            wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&string);
            return 0;
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x24C,
              (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\registryserializer.cpp",
              (const char *)(unsigned int)v21,
              lpDataa);
            wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v32);
            wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v31);
            wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&string);
            return v22;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x248,
            (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\registryserializer.cpp",
            (const char *)(unsigned int)v17,
            lpData);
          wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v32);
          wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v31);
          wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&string);
          return v18;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x244,
          (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\registryserializer.cpp",
          (const char *)(unsigned int)v14,
          lpData);
        wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v32);
        wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v31);
        wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&string);
        return v15;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x240,
        (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\registryserializer.cpp",
        (const char *)(unsigned int)v10,
        lpData);
      wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v31);
      wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&string);
      return v11;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x23C,
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
0x18005bd08  mov     r11, rsp
0x18005bd0b  mov     [r11+18h], rbx
0x18005bd0f  mov     [r11+20h], rsi
0x18005bd13  push    rdi
0x18005bd14  sub     rsp, 0A0h
0x18005bd1b  mov     rax, cs:__security_cookie
0x18005bd22  xor     rax, rsp
0x18005bd25  mov     [rsp+0A8h+var_10], rax
0x18005bd2d  mov     rdi, rdx
0x18005bd30  mov     rsi, rcx
0x18005bd33  mov     qword ptr [r11-70h], 0
0x18005bd3b  mov     rax, [rdx]
0x18005bd3e  mov     rbx, [rax+30h]
0x18005bd42  xor     edx, edx
0x18005bd44  lea     rcx, [r11-70h]
0x18005bd48  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x18005bd4d  lea     rdx, [rsp+0A8h+string]
0x18005bd52  mov     rcx, rdi
0x18005bd55  mov     rax, rbx
0x18005bd58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bd5d  mov     ebx, eax
0x18005bd5f  test    eax, eax
0x18005bd61  jns     short loc_18005BD91
0x18005bd63  mov     rcx, [rsp+0A8h]; this
0x18005bd6b  mov     r9d, eax; char *
0x18005bd6e  lea     r8, aOnecoreuapBase_40; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x18005bd75  mov     edx, 23Ch; void *
0x18005bd7a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005bd7f  nop
0x18005bd80  lea     rcx, [rsp+0A8h+string]
0x18005bd85  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x18005bd8a  mov     eax, ebx
0x18005bd8c  jmp     loc_18005C156
0x18005bd91  xor     edx, edx; length
0x18005bd93  mov     rcx, [rsp+0A8h+string]; string
0x18005bd98  call    cs:__imp_WindowsGetStringRawBuffer
0x18005bd9e  mov     rdx, rax
0x18005bda1  lea     rcx, [rsp+0A8h+var_50]
0x18005bda6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18005bdab  nop
0x18005bdac  lea     rdx, aAppid; "AppId"
0x18005bdb3  lea     rcx, [rsp+0A8h+var_30]
0x18005bdb8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18005bdbd  nop
0x18005bdbe  lea     r8, [rsp+0A8h+var_50]
0x18005bdc3  lea     rdx, [rsp+0A8h+var_30]
0x18005bdc8  mov     rcx, rsi
0x18005bdcb  call    ?SetString@RegistryKeyBroker@AssignedAccess@Internal@Windows@@QEBAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; Windows::Internal::AssignedAccess::RegistryKeyBroker::SetString(std::wstring const &,std::wstring const &)
0x18005bdd0  nop
0x18005bdd1  lea     rcx, [rsp+0A8h+var_30]
0x18005bdd6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005bddb  nop
0x18005bddc  lea     rcx, [rsp+0A8h+var_50]
0x18005bde1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005bde6  mov     [rsp+0A8h+var_68], 0
0x18005bdef  mov     rax, [rdi]
0x18005bdf2  mov     rbx, [rax+70h]
0x18005bdf6  xor     edx, edx
0x18005bdf8  lea     rcx, [rsp+0A8h+var_68]
0x18005bdfd  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x18005be02  lea     rdx, [rsp+0A8h+var_68]
0x18005be07  mov     rcx, rdi
0x18005be0a  mov     rax, rbx
0x18005be0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005be12  mov     ebx, eax
0x18005be14  test    eax, eax
0x18005be16  jns     short loc_18005BE51
0x18005be18  mov     rcx, [rsp+0A8h]; this
0x18005be20  mov     r9d, eax; char *
0x18005be23  lea     r8, aOnecoreuapBase_40; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x18005be2a  mov     edx, 240h; void *
0x18005be2f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005be34  nop
0x18005be35  lea     rcx, [rsp+0A8h+var_68]
0x18005be3a  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x18005be3f  nop
0x18005be40  lea     rcx, [rsp+0A8h+string]
0x18005be45  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x18005be4a  mov     eax, ebx
0x18005be4c  jmp     loc_18005C156
0x18005be51  xor     edx, edx; length
0x18005be53  mov     rcx, [rsp+0A8h+var_68]; string
0x18005be58  call    cs:__imp_WindowsGetStringRawBuffer
0x18005be5e  mov     rdx, rax
0x18005be61  lea     rcx, [rsp+0A8h+var_30]
0x18005be66  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18005be6b  nop
0x18005be6c  lea     rdx, aPublisher; "Publisher"
0x18005be73  lea     rcx, [rsp+0A8h+var_50]
0x18005be78  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18005be7d  nop
0x18005be7e  lea     r8, [rsp+0A8h+var_30]
0x18005be83  lea     rdx, [rsp+0A8h+var_50]
0x18005be88  mov     rcx, rsi
0x18005be8b  call    ?SetString@RegistryKeyBroker@AssignedAccess@Internal@Windows@@QEBAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; Windows::Internal::AssignedAccess::RegistryKeyBroker::SetString(std::wstring const &,std::wstring const &)
0x18005be90  nop
0x18005be91  lea     rcx, [rsp+0A8h+var_50]
0x18005be96  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005be9b  nop
0x18005be9c  lea     rcx, [rsp+0A8h+var_30]
0x18005bea1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005bea6  mov     [rsp+0A8h+var_60], 0
0x18005beaf  mov     rax, [rdi]
0x18005beb2  mov     rbx, [rax+50h]
0x18005beb6  xor     edx, edx
0x18005beb8  lea     rcx, [rsp+0A8h+var_60]
0x18005bebd  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x18005bec2  lea     rdx, [rsp+0A8h+var_60]
0x18005bec7  mov     rcx, rdi
0x18005beca  mov     rax, rbx
0x18005becd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bed2  mov     ebx, eax
0x18005bed4  test    eax, eax
0x18005bed6  jns     short loc_18005BF1C
0x18005bed8  mov     rcx, [rsp+0A8h]; this
0x18005bee0  mov     r9d, eax; char *
0x18005bee3  lea     r8, aOnecoreuapBase_40; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x18005beea  mov     edx, 244h; void *
0x18005beef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005bef4  nop
0x18005bef5  lea     rcx, [rsp+0A8h+var_60]
0x18005befa  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x18005beff  nop
0x18005bf00  lea     rcx, [rsp+0A8h+var_68]
0x18005bf05  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x18005bf0a  nop
0x18005bf0b  lea     rcx, [rsp+0A8h+string]
0x18005bf10  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x18005bf15  mov     eax, ebx
0x18005bf17  jmp     loc_18005C156
0x18005bf1c  xor     edx, edx; length
0x18005bf1e  mov     rcx, [rsp+0A8h+var_60]; string
0x18005bf23  call    cs:__imp_WindowsGetStringRawBuffer
0x18005bf29  mov     rdx, rax
0x18005bf2c  lea     rcx, [rsp+0A8h+var_30]
0x18005bf31  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18005bf36  nop
0x18005bf37  lea     rdx, aArguments; "Arguments"
0x18005bf3e  lea     rcx, [rsp+0A8h+var_50]
0x18005bf43  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18005bf48  nop
0x18005bf49  lea     r8, [rsp+0A8h+var_30]
0x18005bf4e  lea     rdx, [rsp+0A8h+var_50]
0x18005bf53  mov     rcx, rsi
0x18005bf56  call    ?SetString@RegistryKeyBroker@AssignedAccess@Internal@Windows@@QEBAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; Windows::Internal::AssignedAccess::RegistryKeyBroker::SetString(std::wstring const &,std::wstring const &)
0x18005bf5b  nop
0x18005bf5c  lea     rcx, [rsp+0A8h+var_50]
0x18005bf61  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005bf66  nop
0x18005bf67  lea     rcx, [rsp+0A8h+var_30]
0x18005bf6c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005bf71  mov     [rsp+0A8h+var_58], 0
0x18005bf79  mov     rax, [rdi]
0x18005bf7c  lea     rdx, [rsp+0A8h+var_58]
0x18005bf81  mov     rcx, rdi
0x18005bf84  mov     rax, [rax+40h]
0x18005bf88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bf8d  mov     ebx, eax
0x18005bf8f  test    eax, eax
0x18005bf91  jns     short loc_18005BFD7
0x18005bf93  mov     rcx, [rsp+0A8h]; this
0x18005bf9b  mov     r9d, eax; char *
0x18005bf9e  lea     r8, aOnecoreuapBase_40; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x18005bfa5  mov     edx, 248h; void *
0x18005bfaa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005bfaf  nop
0x18005bfb0  lea     rcx, [rsp+0A8h+var_60]
0x18005bfb5  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x18005bfba  nop
0x18005bfbb  lea     rcx, [rsp+0A8h+var_68]
0x18005bfc0  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x18005bfc5  nop
0x18005bfc6  lea     rcx, [rsp+0A8h+string]
0x18005bfcb  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x18005bfd0  mov     eax, ebx
0x18005bfd2  jmp     loc_18005C156
0x18005bfd7  mov     eax, [rsp+0A8h+var_58]
0x18005bfdb  mov     dword ptr [rsp+0A8h+Data], eax
0x18005bfdf  lea     rdx, aApptype; "AppType"
0x18005bfe6  lea     rcx, [rsp+0A8h+var_50]
0x18005bfeb  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18005bff0  nop
0x18005bff1  lea     rcx, [rsp+0A8h+var_50]
0x18005bff6  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18005bffb  mov     rdx, rax; lpValueName
0x18005bffe  mov     [rsp+0A8h+cbData], 4; cbData
0x18005c006  lea     rax, [rsp+0A8h+Data]
0x18005c00b  mov     [rsp+0A8h+lpData], rax; int
0x18005c010  mov     r9d, 4; dwType
0x18005c016  xor     r8d, r8d; Reserved
0x18005c019  mov     rcx, [rsi+10h]; hKey
0x18005c01d  call    cs:__imp_RegSetValueExW
0x18005c023  mov     rcx, [rsp+0A8h]; this
0x18005c02b  test    eax, eax
0x18005c02d  jz      short loc_18005C044
0x18005c02f  mov     r9d, eax; char *
0x18005c032  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\base\\inc\\embedd"...
0x18005c039  mov     edx, 0CDh; void *
0x18005c03e  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18005c044  lea     rcx, [rsp+0A8h+var_50]
0x18005c049  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005c04e  mov     [rsp+0A8h+var_78], 0
0x18005c053  mov     rax, [rdi]
0x18005c056  lea     rdx, [rsp+0A8h+var_78]
0x18005c05b  mov     rcx, rdi
0x18005c05e  mov     rax, [rax+60h]
0x18005c062  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c067  mov     ebx, eax
0x18005c069  test    eax, eax
0x18005c06b  jns     short loc_18005C0B1
0x18005c06d  mov     rcx, [rsp+0A8h]; this
0x18005c075  mov     r9d, eax; char *
0x18005c078  lea     r8, aOnecoreuapBase_40; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x18005c07f  mov     edx, 24Ch; void *
0x18005c084  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005c089  nop
0x18005c08a  lea     rcx, [rsp+0A8h+var_60]
0x18005c08f  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x18005c094  nop
0x18005c095  lea     rcx, [rsp+0A8h+var_68]
0x18005c09a  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x18005c09f  nop
0x18005c0a0  lea     rcx, [rsp+0A8h+string]
0x18005c0a5  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x18005c0aa  mov     eax, ebx
0x18005c0ac  jmp     loc_18005C156
0x18005c0b1  xor     eax, eax
0x18005c0b3  cmp     [rsp+0A8h+var_78], al
0x18005c0b7  setnz   al
0x18005c0ba  mov     dword ptr [rsp+0A8h+Data], eax
0x18005c0be  lea     rdx, aAutolaunch; "AutoLaunch"
0x18005c0c5  lea     rcx, [rsp+0A8h+var_50]
0x18005c0ca  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18005c0cf  nop
0x18005c0d0  lea     rcx, [rsp+0A8h+var_50]
0x18005c0d5  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18005c0da  mov     rdx, rax; lpValueName
0x18005c0dd  mov     [rsp+0A8h+cbData], 4; cbData
0x18005c0e5  lea     rax, [rsp+0A8h+Data]
0x18005c0ea  mov     [rsp+0A8h+lpData], rax; unsigned int
0x18005c0ef  mov     r9d, 4; dwType
0x18005c0f5  xor     r8d, r8d; Reserved
0x18005c0f8  mov     rcx, [rsi+10h]; hKey
0x18005c0fc  call    cs:__imp_RegSetValueExW
0x18005c102  mov     rcx, [rsp+0A8h]; this
0x18005c10a  test    eax, eax
0x18005c10c  jz      short loc_18005C123
0x18005c10e  mov     r9d, eax; char *
0x18005c111  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\base\\inc\\embedd"...
0x18005c118  mov     edx, 0CDh; void *
0x18005c11d  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18005c123  lea     rcx, [rsp+0A8h+var_50]
0x18005c128  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005c12d  nop
0x18005c12e  lea     rcx, [rsp+0A8h+var_60]
0x18005c133  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x18005c138  nop
0x18005c139  lea     rcx, [rsp+0A8h+var_68]
0x18005c13e  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x18005c143  nop
0x18005c144  lea     rcx, [rsp+0A8h+string]
0x18005c149  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x18005c14e  xor     eax, eax
0x18005c150  jmp     short loc_18005C156
0x18005c152  mov     eax, dword ptr [rsp+0A8h+Data]
0x18005c156  mov     rcx, [rsp+0A8h+var_10]
0x18005c15e  xor     rcx, rsp; StackCookie
0x18005c161  call    __security_check_cookie
0x18005c166  lea     r11, [rsp+0A8h+var_8]
0x18005c16e  mov     rbx, [r11+20h]
0x18005c172  mov     rsi, [r11+28h]
0x18005c176  mov     rsp, r11
0x18005c179  pop     rdi
0x18005c17a  retn
```
