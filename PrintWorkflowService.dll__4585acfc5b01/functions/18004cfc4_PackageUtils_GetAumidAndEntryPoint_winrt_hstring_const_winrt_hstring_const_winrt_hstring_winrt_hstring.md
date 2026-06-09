# PackageUtils::GetAumidAndEntryPoint(winrt::hstring const &,winrt::hstring const &,winrt::hstring &,winrt::hstring &)

- ea: `0x18004cfc4`
- end: `0x18004d1e1`
- name: `?GetAumidAndEntryPoint@PackageUtils@@YAXAEBUhstring@winrt@@0AEAU23@1@Z`
- size: `541`
- prototype: `void __fastcall(PackageUtils *this, const struct winrt::hstring *, const struct winrt::hstring *, struct winrt::hstring *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18004d518`

## callees

- `0x180003ca0`
- `0x180012784`
- `0x1800127a4`
- `0x180012820`
- `0x1800129dc`
- `0x1800253ec`
- `0x180027fd8`
- `0x180029f38`
- `0x1800317d4`
- `0x1800421b0`
- `0x18004cfc4`
- `0x18004d1e8`
- `0x18004d454`
- `0x18004d750`

## import_xrefs

- `Print.PrintSupport.Source!GetAppUserModelId` at `0x18004d112`
- `Print.PrintSupport.Source!GetAppUserModelId` at `0x18004d112`
- `Print.PrintSupport.Source!GetEntryPoint` at `0x18004d0c8`
- `Print.PrintSupport.Source!GetEntryPoint` at `0x18004d15d`
- `Print.PrintSupport.Source!GetEntryPoint` at `0x18004d0c8`
- `Print.PrintSupport.Source!GetEntryPoint` at `0x18004d15d`

## string_xrefs

- `0x18004d1a5`: `onecoreuap\printscan\print\workflow\broker\psa_lib\packageutils.cpp`
- `0x18004d1ba`: `onecoreuap\printscan\print\workflow\broker\psa_lib\packageutils.cpp`
- `0x18004d1cf`: `onecoreuap\printscan\print\workflow\broker\psa_lib\packageutils.cpp`

## pseudocode

```c
void __fastcall PackageUtils::GetAumidAndEntryPoint(
        PackageUtils *this,
        const struct winrt::hstring *a2,
        const struct winrt::hstring *a3,
        struct winrt::hstring *a4)
{
  VirtualPrinterHelper *v8; // rax
  const unsigned __int16 *v9; // rdx
  const unsigned __int16 *v10; // rax
  __int64 AumidForVirtualPrinter; // rax
  __int64 v12; // rdx
  const unsigned __int16 *v13; // rax
  __int64 EntryPointForVirtualPrinter; // rax
  __int64 v15; // rdx
  const unsigned __int16 *v16; // rax
  __int64 v17; // rdx
  int EntryPoint; // eax
  __int64 *v19; // rcx
  const unsigned __int16 *v20; // rax
  int AppUserModelId; // eax
  const unsigned __int16 *v22; // rax
  __int64 v23; // rdx
  int v24; // eax
  __int64 v25; // [rsp+20h] [rbp-50h] BYREF
  __int64 v26; // [rsp+28h] [rbp-48h]
  __int64 v27; // [rsp+30h] [rbp-40h] BYREF
  __int64 v28; // [rsp+38h] [rbp-38h] BYREF
  _BYTE v29[32]; // [rsp+40h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]

  v8 = (VirtualPrinterHelper *)winrt::hstring::c_str(this);
  if ( VirtualPrinterHelper::IsVirtualPrinter(v8, v9) )
  {
    v10 = winrt::hstring::c_str(this);
    AumidForVirtualPrinter = VirtualPrinterHelper::GetAumidForVirtualPrinter(v29, v10);
    v25 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(AumidForVirtualPrinter);
    v26 = *(_QWORD *)(v12 + 16);
    winrt::hstring::operator=(a3, &v25);
    std::wstring::_Tidy_deallocate(v29);
    if ( (unsigned __int8)winrt::operator==(a2, L"Windows.PrintSupportVirtualPrinterWorkflow") )
    {
      v13 = winrt::hstring::c_str(this);
      EntryPointForVirtualPrinter = VirtualPrinterHelper::GetEntryPointForVirtualPrinter(v29, v13);
      v25 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(EntryPointForVirtualPrinter);
      v26 = *(_QWORD *)(v15 + 16);
      winrt::hstring::operator=(a4, &v25);
      std::wstring::_Tidy_deallocate(v29);
      return;
    }
    v25 = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &v25,
      0);
    winrt::hstring::c_str(a3);
    v16 = winrt::hstring::c_str(a2);
    EntryPoint = GetEntryPoint(v16, v17, &v25);
    if ( EntryPoint < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x3F,
        (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\psa_lib\\packageutils.cpp",
        (const char *)(unsigned int)EntryPoint,
        v25);
    winrt::hstring::operator=(a4, v25);
    v19 = &v25;
  }
  else
  {
    v28 = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &v28,
      0);
    v20 = winrt::hstring::c_str(this);
    AppUserModelId = GetAppUserModelId(v20, &v28);
    if ( AppUserModelId < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x46,
        (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\psa_lib\\packageutils.cpp",
        (const char *)(unsigned int)AppUserModelId,
        v25);
    winrt::hstring::operator=(a3, v28);
    v27 = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &v27,
      0);
    winrt::hstring::c_str(a3);
    v22 = winrt::hstring::c_str(a2);
    v24 = GetEntryPoint(v22, v23, &v27);
    if ( v24 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x4A,
        (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\psa_lib\\packageutils.cpp",
        (const char *)(unsigned int)v24,
        v25);
    winrt::hstring::operator=(a4, v27);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v27);
    v19 = &v28;
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v19);
}

```

## disassembly

```asm
0x18004cfc4  push    rbp
0x18004cfc6  push    rbx
0x18004cfc7  push    rsi
0x18004cfc8  push    rdi
0x18004cfc9  push    r14
0x18004cfcb  mov     rbp, rsp
0x18004cfce  sub     rsp, 70h
0x18004cfd2  mov     rax, cs:__security_cookie
0x18004cfd9  xor     rax, rsp
0x18004cfdc  mov     [rbp+var_10], rax
0x18004cfe0  mov     rbx, r9
0x18004cfe3  mov     rsi, r8
0x18004cfe6  mov     r14, rdx
0x18004cfe9  mov     rdi, rcx
0x18004cfec  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x18004cff1  mov     rcx, rax; this
0x18004cff4  call    ?IsVirtualPrinter@VirtualPrinterHelper@@YA_NPEBG@Z; VirtualPrinterHelper::IsVirtualPrinter(ushort const *)
0x18004cff9  test    al, al
0x18004cffb  jz      loc_18004D0F0
0x18004d001  mov     rcx, rdi; this
0x18004d004  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x18004d009  mov     rdx, rax
0x18004d00c  lea     rcx, [rbp+var_30]
0x18004d010  call    ?GetAumidForVirtualPrinter@VirtualPrinterHelper@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG@Z; VirtualPrinterHelper::GetAumidForVirtualPrinter(ushort const *)
0x18004d015  mov     rdx, rax
0x18004d018  mov     rcx, rax
0x18004d01b  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004d020  mov     [rbp+var_50], rax
0x18004d024  mov     rax, [rdx+10h]
0x18004d028  mov     [rbp+var_48], rax
0x18004d02c  lea     rdx, [rbp+var_50]
0x18004d030  mov     rcx, rsi
0x18004d033  call    ??4hstring@winrt@@QEAAAEAU01@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::hstring::operator=(std::basic_string_view<ushort> const &)
0x18004d038  nop
0x18004d039  lea     rcx, [rbp+var_30]
0x18004d03d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004d042  lea     rdx, aWindowsPrintsu_1; "Windows.PrintSupportVirtualPrinterWorkf"...
0x18004d049  mov     rcx, r14
0x18004d04c  call    ??8winrt@@YA_NAEBUhstring@0@PEBG@Z; winrt::operator==(winrt::hstring const &,ushort const *)
0x18004d051  test    al, al
0x18004d053  jz      short loc_18004D09B
0x18004d055  mov     rcx, rdi; this
0x18004d058  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x18004d05d  mov     rdx, rax
0x18004d060  lea     rcx, [rbp+var_30]
0x18004d064  call    ?GetEntryPointForVirtualPrinter@VirtualPrinterHelper@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG@Z; VirtualPrinterHelper::GetEntryPointForVirtualPrinter(ushort const *)
0x18004d069  mov     rdx, rax
0x18004d06c  mov     rcx, rax
0x18004d06f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004d074  mov     [rbp+var_50], rax
0x18004d078  mov     rax, [rdx+10h]
0x18004d07c  mov     [rbp+var_48], rax
0x18004d080  lea     rdx, [rbp+var_50]
0x18004d084  mov     rcx, rbx
0x18004d087  call    ??4hstring@winrt@@QEAAAEAU01@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::hstring::operator=(std::basic_string_view<ushort> const &)
0x18004d08c  nop
0x18004d08d  lea     rcx, [rbp+var_30]
0x18004d091  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004d096  jmp     loc_18004D18B
0x18004d09b  mov     [rbp+var_50], 0
0x18004d0a3  xor     edx, edx
0x18004d0a5  lea     rcx, [rbp+var_50]
0x18004d0a9  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18004d0ae  mov     rcx, rsi; this
0x18004d0b1  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x18004d0b6  mov     rdx, rax
0x18004d0b9  mov     rcx, r14; this
0x18004d0bc  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x18004d0c1  lea     r8, [rbp+var_50]
0x18004d0c5  mov     rcx, rax
0x18004d0c8  call    cs:__imp_GetEntryPoint
0x18004d0ce  mov     rcx, [rbp+28h]; this
0x18004d0d2  test    eax, eax
0x18004d0d4  js      loc_18004D1B7
0x18004d0da  mov     rdx, [rbp+var_50]
0x18004d0de  mov     rcx, rbx
0x18004d0e1  call    ??4hstring@winrt@@QEAAAEAU01@QEBG@Z; winrt::hstring::operator=(ushort const * const)
0x18004d0e6  nop
0x18004d0e7  lea     rcx, [rbp+var_50]
0x18004d0eb  jmp     loc_18004D186
0x18004d0f0  mov     [rbp+var_38], 0
0x18004d0f8  xor     edx, edx
0x18004d0fa  lea     rcx, [rbp+var_38]
0x18004d0fe  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18004d103  mov     rcx, rdi; this
0x18004d106  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x18004d10b  lea     rdx, [rbp+var_38]
0x18004d10f  mov     rcx, rax
0x18004d112  call    cs:__imp_GetAppUserModelId
0x18004d118  mov     rcx, [rbp+28h]; this
0x18004d11c  test    eax, eax
0x18004d11e  js      loc_18004D1CC
0x18004d124  mov     rdx, [rbp+var_38]
0x18004d128  mov     rcx, rsi
0x18004d12b  call    ??4hstring@winrt@@QEAAAEAU01@QEBG@Z; winrt::hstring::operator=(ushort const * const)
0x18004d130  mov     [rbp+var_40], 0
0x18004d138  xor     edx, edx
0x18004d13a  lea     rcx, [rbp+var_40]
0x18004d13e  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18004d143  mov     rcx, rsi; this
0x18004d146  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x18004d14b  mov     rdx, rax
0x18004d14e  mov     rcx, r14; this
0x18004d151  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x18004d156  lea     r8, [rbp+var_40]
0x18004d15a  mov     rcx, rax
0x18004d15d  call    cs:__imp_GetEntryPoint
0x18004d163  mov     rcx, [rbp+28h]; this
0x18004d167  test    eax, eax
0x18004d169  js      short loc_18004D1A2
0x18004d16b  mov     rdx, [rbp+var_40]
0x18004d16f  mov     rcx, rbx
0x18004d172  call    ??4hstring@winrt@@QEAAAEAU01@QEBG@Z; winrt::hstring::operator=(ushort const * const)
0x18004d177  nop
0x18004d178  lea     rcx, [rbp+var_40]
0x18004d17c  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18004d181  nop
0x18004d182  lea     rcx, [rbp+var_38]
0x18004d186  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18004d18b  mov     rcx, [rbp+var_10]
0x18004d18f  xor     rcx, rsp; StackCookie
0x18004d192  call    __security_check_cookie
0x18004d197  add     rsp, 70h
0x18004d19b  pop     r14
0x18004d19d  pop     rdi
0x18004d19e  pop     rsi
0x18004d19f  pop     rbx
0x18004d1a0  pop     rbp
0x18004d1a1  retn
0x18004d1a2  mov     r9d, eax; char *
0x18004d1a5  lea     r8, aOnecoreuapPrin_10; "onecoreuap\\printscan\\print\\workflow"...
0x18004d1ac  mov     edx, 4Ah ; 'J'; void *
0x18004d1b1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004d1b7  mov     r9d, eax; char *
0x18004d1ba  lea     r8, aOnecoreuapPrin_10; "onecoreuap\\printscan\\print\\workflow"...
0x18004d1c1  mov     edx, 3Fh ; '?'; void *
0x18004d1c6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004d1cc  mov     r9d, eax; char *
0x18004d1cf  lea     r8, aOnecoreuapPrin_10; "onecoreuap\\printscan\\print\\workflow"...
0x18004d1d6  mov     edx, 46h ; 'F'; void *
0x18004d1db  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
