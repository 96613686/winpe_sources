# Windows::Internal::AssignedAccess::Details::Serialize<Windows::Internal::AssignedAccess::RegistryKey>(Windows::Internal::AssignedAccess::RegistryKey &,Windows::Internal::AssignedAccess::IAssignedAccessApplication *)

- ea: `0x18005b968`
- end: `0x18005bd00`
- name: `??$Serialize@VRegistryKey@AssignedAccess@Internal@Windows@@@Details@AssignedAccess@Internal@Windows@@YAJAEAVRegistryKey@123@PEAUIAssignedAccessApplication@123@@Z`
- size: `920`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x18005cac0`

## callees

- `0x180006640`
- `0x18000b6b4`
- `0x180010c98`
- `0x180014a5c`
- `0x1800271e4`
- `0x18002901c`
- `0x1800295e4`
- `0x18002b190`
- `0x180054894`
- `0x18005b968`
- `0x180096010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005b9f5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005ba9a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005bb4a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005b9f5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005ba9a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005bb4a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005bc8e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005bc8e`

## string_xrefs

- `0x18005bca3`: `onecoreuap\internal\base\inc\embedded\registrykey.h`
- `0x18005b9cb`: `onecoreuap\base\embedded\sys\lockdown\runtime\worker\registryserializer.cpp`
- `0x18005ba65`: `onecoreuap\base\embedded\sys\lockdown\runtime\worker\registryserializer.cpp`
- `0x18005bb0a`: `onecoreuap\base\embedded\sys\lockdown\runtime\worker\registryserializer.cpp`
- `0x18005bbaa`: `onecoreuap\base\embedded\sys\lockdown\runtime\worker\registryserializer.cpp`
- `0x18005bc29`: `onecoreuap\base\embedded\sys\lockdown\runtime\worker\registryserializer.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=1
__int64 __fastcall Windows::Internal::AssignedAccess::Details::Serialize<Windows::Internal::AssignedAccess::RegistryKey>(
        HKEY *a1,
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
  int v19; // eax
  unsigned int v20; // ebx
  unsigned int v21; // eax
  int lpData; // [rsp+20h] [rbp-68h]
  unsigned int lpDataa; // [rsp+20h] [rbp-68h]
  _BYTE v24[4]; // [rsp+30h] [rbp-58h] BYREF
  BYTE Data[4]; // [rsp+34h] [rbp-54h] BYREF
  HSTRING string; // [rsp+38h] [rbp-50h] BYREF
  HSTRING v27; // [rsp+40h] [rbp-48h] BYREF
  HSTRING v28; // [rsp+48h] [rbp-40h] BYREF
  int v29; // [rsp+50h] [rbp-38h] BYREF
  _BYTE v30[32]; // [rsp+58h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

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
    std::wstring::wstring(v30, StringRawBuffer);
    Windows::Internal::AssignedAccess::RegistryKey::SetString<unsigned short const *>(a1, L"AppId", v30);
    std::wstring::_Tidy_deallocate(v30);
    v27 = 0;
    v9 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)a2 + 112LL);
    wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
      &v27,
      0);
    v10 = v9(a2, &v27);
    v11 = v10;
    if ( v10 >= 0 )
    {
      v12 = WindowsGetStringRawBuffer(v27, 0);
      std::wstring::wstring(v30, v12);
      Windows::Internal::AssignedAccess::RegistryKey::SetString<unsigned short const *>(a1, L"Publisher", v30);
      std::wstring::_Tidy_deallocate(v30);
      v28 = 0;
      v13 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)a2 + 80LL);
      wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
        &v28,
        0);
      v14 = v13(a2, &v28);
      v15 = v14;
      if ( v14 >= 0 )
      {
        v16 = WindowsGetStringRawBuffer(v28, 0);
        std::wstring::wstring(v30, v16);
        Windows::Internal::AssignedAccess::RegistryKey::SetString<unsigned short const *>(a1, L"Arguments", v30);
        std::wstring::_Tidy_deallocate(v30);
        v29 = 0;
        v17 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)a2 + 64LL))(a2, &v29);
        v18 = v17;
        if ( v17 >= 0 )
        {
          *(_DWORD *)Data = v29;
          Windows::Internal::AssignedAccess::RegistryKey::SetDWORD<unsigned short const [8]>(a1, L"AppType", Data);
          v24[0] = 0;
          v19 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)a2 + 96LL))(a2, v24);
          v20 = v19;
          if ( v19 >= 0 )
          {
            *(_DWORD *)Data = v24[0] != 0;
            v21 = RegSetValueExW(*a1, L"AutoLaunch", 0, 4u, Data, 4u);
            if ( v21 )
              wil::details::in1diag3::_Throw_Win32(
                retaddr,
                (void *)0xCD,
                (unsigned int)"onecoreuap\\internal\\base\\inc\\embedded\\registrykey.h",
                (const char *)v21,
                lpDataa);
            wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v28);
            wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v27);
            wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&string);
            return 0;
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x24C,
              (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\registryserializer.cpp",
              (const char *)(unsigned int)v19,
              lpData);
            wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v28);
            wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v27);
            wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&string);
            return v20;
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
          wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v28);
          wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v27);
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
        wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v28);
        wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v27);
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
      wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v27);
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
0x18005b968  mov     r11, rsp
0x18005b96b  mov     [r11+18h], rbx
0x18005b96f  mov     [r11+20h], rsi
0x18005b973  push    rdi
0x18005b974  sub     rsp, 80h
0x18005b97b  mov     rax, cs:__security_cookie
0x18005b982  xor     rax, rsp
0x18005b985  mov     [rsp+88h+var_10], rax
0x18005b98a  mov     rdi, rdx
0x18005b98d  mov     rsi, rcx
0x18005b990  mov     qword ptr [r11-50h], 0
0x18005b998  mov     rax, [rdx]
0x18005b99b  mov     rbx, [rax+30h]
0x18005b99f  xor     edx, edx
0x18005b9a1  lea     rcx, [r11-50h]
0x18005b9a5  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x18005b9aa  lea     rdx, [rsp+88h+string]
0x18005b9af  mov     rcx, rdi
0x18005b9b2  mov     rax, rbx
0x18005b9b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b9ba  mov     ebx, eax
0x18005b9bc  test    eax, eax
0x18005b9be  jns     short loc_18005B9EE
0x18005b9c0  mov     rcx, [rsp+88h]; this
0x18005b9c8  mov     r9d, eax; char *
0x18005b9cb  lea     r8, aOnecoreuapBase_40; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x18005b9d2  mov     edx, 23Ch; void *
0x18005b9d7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005b9dc  nop
0x18005b9dd  lea     rcx, [rsp+88h+string]
0x18005b9e2  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x18005b9e7  mov     eax, ebx
0x18005b9e9  jmp     loc_18005BCDD
0x18005b9ee  xor     edx, edx; length
0x18005b9f0  mov     rcx, [rsp+88h+string]; string
0x18005b9f5  call    cs:__imp_WindowsGetStringRawBuffer
0x18005b9fb  mov     rdx, rax
0x18005b9fe  lea     rcx, [rsp+88h+var_30]
0x18005ba03  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18005ba08  nop
0x18005ba09  lea     r8, [rsp+88h+var_30]
0x18005ba0e  lea     rdx, aAppid; "AppId"
0x18005ba15  mov     rcx, rsi
0x18005ba18  call    ??$SetString@PEBG@RegistryKey@AssignedAccess@Internal@Windows@@QEBAXPEBGAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::Internal::AssignedAccess::RegistryKey::SetString<ushort const *>(ushort const *,std::wstring const &)
0x18005ba1d  nop
0x18005ba1e  lea     rcx, [rsp+88h+var_30]
0x18005ba23  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005ba28  mov     [rsp+88h+var_48], 0
0x18005ba31  mov     rax, [rdi]
0x18005ba34  mov     rbx, [rax+70h]
0x18005ba38  xor     edx, edx
0x18005ba3a  lea     rcx, [rsp+88h+var_48]
0x18005ba3f  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x18005ba44  lea     rdx, [rsp+88h+var_48]
0x18005ba49  mov     rcx, rdi
0x18005ba4c  mov     rax, rbx
0x18005ba4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ba54  mov     ebx, eax
0x18005ba56  test    eax, eax
0x18005ba58  jns     short loc_18005BA93
0x18005ba5a  mov     rcx, [rsp+88h]; this
0x18005ba62  mov     r9d, eax; char *
0x18005ba65  lea     r8, aOnecoreuapBase_40; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x18005ba6c  mov     edx, 240h; void *
0x18005ba71  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005ba76  nop
0x18005ba77  lea     rcx, [rsp+88h+var_48]
0x18005ba7c  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x18005ba81  nop
0x18005ba82  lea     rcx, [rsp+88h+string]
0x18005ba87  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x18005ba8c  mov     eax, ebx
0x18005ba8e  jmp     loc_18005BCDD
0x18005ba93  xor     edx, edx; length
0x18005ba95  mov     rcx, [rsp+88h+var_48]; string
0x18005ba9a  call    cs:__imp_WindowsGetStringRawBuffer
0x18005baa0  mov     rdx, rax
0x18005baa3  lea     rcx, [rsp+88h+var_30]
0x18005baa8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18005baad  nop
0x18005baae  lea     r8, [rsp+88h+var_30]
0x18005bab3  lea     rdx, aPublisher; "Publisher"
0x18005baba  mov     rcx, rsi
0x18005babd  call    ??$SetString@PEBG@RegistryKey@AssignedAccess@Internal@Windows@@QEBAXPEBGAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::Internal::AssignedAccess::RegistryKey::SetString<ushort const *>(ushort const *,std::wstring const &)
0x18005bac2  nop
0x18005bac3  lea     rcx, [rsp+88h+var_30]
0x18005bac8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005bacd  mov     [rsp+88h+var_40], 0
0x18005bad6  mov     rax, [rdi]
0x18005bad9  mov     rbx, [rax+50h]
0x18005badd  xor     edx, edx
0x18005badf  lea     rcx, [rsp+88h+var_40]
0x18005bae4  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x18005bae9  lea     rdx, [rsp+88h+var_40]
0x18005baee  mov     rcx, rdi
0x18005baf1  mov     rax, rbx
0x18005baf4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005baf9  mov     ebx, eax
0x18005bafb  test    eax, eax
0x18005bafd  jns     short loc_18005BB43
0x18005baff  mov     rcx, [rsp+88h]; this
0x18005bb07  mov     r9d, eax; char *
0x18005bb0a  lea     r8, aOnecoreuapBase_40; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x18005bb11  mov     edx, 244h; void *
0x18005bb16  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005bb1b  nop
0x18005bb1c  lea     rcx, [rsp+88h+var_40]
0x18005bb21  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x18005bb26  nop
0x18005bb27  lea     rcx, [rsp+88h+var_48]
0x18005bb2c  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x18005bb31  nop
0x18005bb32  lea     rcx, [rsp+88h+string]
0x18005bb37  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x18005bb3c  mov     eax, ebx
0x18005bb3e  jmp     loc_18005BCDD
0x18005bb43  xor     edx, edx; length
0x18005bb45  mov     rcx, [rsp+88h+var_40]; string
0x18005bb4a  call    cs:__imp_WindowsGetStringRawBuffer
0x18005bb50  mov     rdx, rax
0x18005bb53  lea     rcx, [rsp+88h+var_30]
0x18005bb58  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18005bb5d  nop
0x18005bb5e  lea     r8, [rsp+88h+var_30]
0x18005bb63  lea     rdx, aArguments; "Arguments"
0x18005bb6a  mov     rcx, rsi
0x18005bb6d  call    ??$SetString@PEBG@RegistryKey@AssignedAccess@Internal@Windows@@QEBAXPEBGAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::Internal::AssignedAccess::RegistryKey::SetString<ushort const *>(ushort const *,std::wstring const &)
0x18005bb72  nop
0x18005bb73  lea     rcx, [rsp+88h+var_30]
0x18005bb78  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005bb7d  mov     [rsp+88h+var_38], 0
0x18005bb85  mov     rax, [rdi]
0x18005bb88  lea     rdx, [rsp+88h+var_38]
0x18005bb8d  mov     rcx, rdi
0x18005bb90  mov     rax, [rax+40h]
0x18005bb94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bb99  mov     ebx, eax
0x18005bb9b  test    eax, eax
0x18005bb9d  jns     short loc_18005BBE3
0x18005bb9f  mov     rcx, [rsp+88h]; this
0x18005bba7  mov     r9d, eax; char *
0x18005bbaa  lea     r8, aOnecoreuapBase_40; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x18005bbb1  mov     edx, 248h; void *
0x18005bbb6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005bbbb  nop
0x18005bbbc  lea     rcx, [rsp+88h+var_40]
0x18005bbc1  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x18005bbc6  nop
0x18005bbc7  lea     rcx, [rsp+88h+var_48]
0x18005bbcc  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x18005bbd1  nop
0x18005bbd2  lea     rcx, [rsp+88h+string]
0x18005bbd7  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x18005bbdc  mov     eax, ebx
0x18005bbde  jmp     loc_18005BCDD
0x18005bbe3  mov     eax, [rsp+88h+var_38]
0x18005bbe7  mov     dword ptr [rsp+88h+Data], eax
0x18005bbeb  lea     r8, [rsp+88h+Data]
0x18005bbf0  lea     rdx, aApptype; "AppType"
0x18005bbf7  mov     rcx, rsi
0x18005bbfa  call    ??$SetDWORD@$$BY07$$CBG@RegistryKey@AssignedAccess@Internal@Windows@@QEBAXAEAY07$$CBGAEBK@Z; Windows::Internal::AssignedAccess::RegistryKey::SetDWORD<ushort const [8]>(ushort const (&)[8],ulong const &)
0x18005bbff  mov     [rsp+88h+var_58], 0
0x18005bc04  mov     rax, [rdi]
0x18005bc07  lea     rdx, [rsp+88h+var_58]
0x18005bc0c  mov     rcx, rdi
0x18005bc0f  mov     rax, [rax+60h]
0x18005bc13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bc18  mov     ebx, eax
0x18005bc1a  test    eax, eax
0x18005bc1c  jns     short loc_18005BC5F
0x18005bc1e  mov     rcx, [rsp+88h]; this
0x18005bc26  mov     r9d, eax; char *
0x18005bc29  lea     r8, aOnecoreuapBase_40; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x18005bc30  mov     edx, 24Ch; void *
0x18005bc35  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005bc3a  nop
0x18005bc3b  lea     rcx, [rsp+88h+var_40]
0x18005bc40  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x18005bc45  nop
0x18005bc46  lea     rcx, [rsp+88h+var_48]
0x18005bc4b  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x18005bc50  nop
0x18005bc51  lea     rcx, [rsp+88h+string]
0x18005bc56  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x18005bc5b  mov     eax, ebx
0x18005bc5d  jmp     short loc_18005BCDD
0x18005bc5f  xor     eax, eax
0x18005bc61  cmp     [rsp+88h+var_58], al
0x18005bc65  setnz   al
0x18005bc68  mov     dword ptr [rsp+88h+Data], eax
0x18005bc6c  mov     r9d, 4; dwType
0x18005bc72  mov     [rsp+88h+cbData], r9d; cbData
0x18005bc77  lea     rax, [rsp+88h+Data]
0x18005bc7c  mov     [rsp+88h+lpData], rax; unsigned int
0x18005bc81  xor     r8d, r8d; Reserved
0x18005bc84  lea     rdx, aAutolaunch; "AutoLaunch"
0x18005bc8b  mov     rcx, [rsi]; hKey
0x18005bc8e  call    cs:__imp_RegSetValueExW
0x18005bc94  mov     rcx, [rsp+88h]; this
0x18005bc9c  test    eax, eax
0x18005bc9e  jz      short loc_18005BCB5
0x18005bca0  mov     r9d, eax; char *
0x18005bca3  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\base\\inc\\embedd"...
0x18005bcaa  mov     edx, 0CDh; void *
0x18005bcaf  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18005bcb5  lea     rcx, [rsp+88h+var_40]
0x18005bcba  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x18005bcbf  nop
0x18005bcc0  lea     rcx, [rsp+88h+var_48]
0x18005bcc5  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x18005bcca  nop
0x18005bccb  lea     rcx, [rsp+88h+string]
0x18005bcd0  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x18005bcd5  xor     eax, eax
0x18005bcd7  jmp     short loc_18005BCDD
0x18005bcd9  mov     eax, dword ptr [rsp+88h+Data]
0x18005bcdd  mov     rcx, [rsp+88h+var_10]
0x18005bce2  xor     rcx, rsp; StackCookie
0x18005bce5  call    __security_check_cookie
0x18005bcea  lea     r11, [rsp+88h+var_8]
0x18005bcf2  mov     rbx, [r11+20h]
0x18005bcf6  mov     rsi, [r11+28h]
0x18005bcfa  mov     rsp, r11
0x18005bcfd  pop     rdi
0x18005bcfe  retn
```
