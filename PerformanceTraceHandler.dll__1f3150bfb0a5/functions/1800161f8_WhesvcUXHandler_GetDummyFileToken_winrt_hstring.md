# WhesvcUXHandler::GetDummyFileToken(winrt::hstring &)

- ea: `0x1800161f8`
- end: `0x180016426`
- name: `?GetDummyFileToken@WhesvcUXHandler@@AEAAJAEAUhstring@winrt@@@Z`
- size: `558`
- prototype: `__int64 __fastcall(WhesvcUXHandler *__hidden this, struct winrt::hstring *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180016b6c`

## callees

- `0x180002c00`
- `0x180003710`
- `0x180007f3c`
- `0x180009654`
- `0x180010a6c`
- `0x180010b08`
- `0x180012d98`
- `0x1800161f8`
- `0x18001c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800162e6`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800162e6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800162d0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800162d0`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800162fe`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800162fe`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18001624a`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18001624a`
- `ext-ms-win-winrt-storage-l1-1-0!CreateStorageItemFromPath_FullTrustCaller` at `0x18001627c`
- `ext-ms-win-winrt-storage-l1-1-0!CreateStorageItemFromPath_FullTrustCaller` at `0x18001627c`

## string_xrefs

- `0x1800162c9`: `Windows.ApplicationModel.DataTransfer.SharedStorageAccessManager`
- `0x180016243`: `%TEMP%\whesvc_hotkey_traces`
- `0x180016292`: `pcshell\shell\performancetracehandler\dll\whesvcuxhandler.cpp`
- `0x180016314`: `pcshell\shell\performancetracehandler\dll\whesvcuxhandler.cpp`
- `0x18001635b`: `pcshell\shell\performancetracehandler\dll\whesvcuxhandler.cpp`
- `0x1800163ef`: `pcshell\shell\performancetracehandler\dll\whesvcuxhandler.cpp`

## pseudocode

```c
__int64 __fastcall WhesvcUXHandler::GetDummyFileToken(WhesvcUXHandler *this, struct winrt::hstring *a2)
{
  int v3; // eax
  unsigned int v4; // ebx
  HRESULT v5; // eax
  int ActivationFactory; // eax
  int v7; // eax
  unsigned int v8; // r8d
  struct winrt::impl::hstring_header *hstring_on_heap; // rax
  int v11[2]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v12; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v13; // [rsp+30h] [rbp-D0h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+38h] [rbp-C8h] BYREF
  HSTRING string; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Dst[264]; // [rsp+60h] [rbp-A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  memset_0(Dst, 0, 0x208u);
  if ( ExpandEnvironmentStringsW(L"%TEMP%\\whesvc_hotkey_traces", Dst, 0x104u) - 1 > 0x103 )
  {
    v4 = -2147467259;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1E2,
      (unsigned int)"pcshell\\shell\\performancetracehandler\\dll\\whesvcuxhandler.cpp",
      (const char *)0x80004005LL,
      v11[0]);
    return v4;
  }
  v13 = 0;
  v3 = CreateStorageItemFromPath_FullTrustCaller(Dst, 0x2000, &GUID_fa3f6186_4214_428c_a64c_14c9ac7315ea, &v13);
  v4 = v3;
  if ( v3 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1E5,
      (unsigned int)"pcshell\\shell\\performancetracehandler\\dll\\whesvcuxhandler.cpp",
      (const char *)(unsigned int)v3,
      v11[0]);
LABEL_11:
    wil::com_ptr_t<Windows::Storage::IStorageItem,wil::err_returncode_policy>::~com_ptr_t<Windows::Storage::IStorageItem,wil::err_returncode_policy>(&v13);
    return v4;
  }
  *(_QWORD *)v11 = 0;
  string = 0;
  v5 = WindowsCreateStringReference(
         L"Windows.ApplicationModel.DataTransfer.SharedStorageAccessManager",
         0x40u,
         &hstringHeader,
         &string);
  if ( v5 < 0 )
  {
    RaiseException(v5, 1u, 0, 0);
    __debugbreak();
  }
  ActivationFactory = RoGetActivationFactory(string, &GUID_c6132ada_34b1_4849_bd5f_d09fee3158c5, v11);
  v4 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1E8,
      (unsigned int)"pcshell\\shell\\performancetracehandler\\dll\\whesvcuxhandler.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v11[0]);
LABEL_10:
    wil::com_ptr_t<Windows::Storage::IStorageItem,wil::err_returncode_policy>::~com_ptr_t<Windows::Storage::IStorageItem,wil::err_returncode_policy>(v11);
    goto LABEL_11;
  }
  v12 = 0;
  v7 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64 *))(**(_QWORD **)v11 + 48LL))(*(_QWORD *)v11, v13, &v12);
  v4 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1EA,
      (unsigned int)"pcshell\\shell\\performancetracehandler\\dll\\whesvcuxhandler.cpp",
      (const char *)(unsigned int)v7,
      v11[0]);
    wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v12);
    goto LABEL_10;
  }
  hstring_on_heap = (struct winrt::impl::hstring_header *)v12;
  if ( v12 )
  {
    if ( (*(_BYTE *)v12 & 1) != 0 )
      hstring_on_heap = winrt::impl::create_hstring_on_heap(
                          *(winrt::impl **)(v12 + 16),
                          (winrt::impl *)*(unsigned int *)(v12 + 4),
                          v8);
    else
      _InterlockedIncrement((volatile signed __int32 *)(v12 + 24));
  }
  winrt::handle_type<winrt::impl::hstring_traits>::attach(a2, hstring_on_heap);
  wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v12);
  wil::com_ptr_t<Windows::Storage::IStorageItem,wil::err_returncode_policy>::~com_ptr_t<Windows::Storage::IStorageItem,wil::err_returncode_policy>(v11);
  wil::com_ptr_t<Windows::Storage::IStorageItem,wil::err_returncode_policy>::~com_ptr_t<Windows::Storage::IStorageItem,wil::err_returncode_policy>(&v13);
  return 0;
}

```

## disassembly

```asm
0x1800161f8  mov     [rsp-8+arg_0], rbx
0x1800161fd  mov     [rsp-8+arg_10], rdi
0x180016202  push    rbp
0x180016203  lea     rbp, [rsp-180h]
0x18001620b  sub     rsp, 280h
0x180016212  mov     rax, cs:__security_cookie
0x180016219  xor     rax, rsp
0x18001621c  mov     [rbp+180h+var_10], rax
0x180016223  mov     rdi, rdx
0x180016226  xor     edx, edx; Val
0x180016228  mov     r8d, 208h; Size
0x18001622e  lea     rcx, [rsp+280h+Dst]; void *
0x180016233  call    memset_0
0x180016238  mov     r8d, 104h; nSize
0x18001623e  lea     rdx, [rsp+280h+Dst]; lpDst
0x180016243  lea     rcx, Src; "%TEMP%\\whesvc_hotkey_traces"
0x18001624a  call    cs:__imp_ExpandEnvironmentStringsW
0x180016250  dec     eax
0x180016252  cmp     eax, 103h
0x180016257  ja      loc_1800163E0
0x18001625d  mov     [rsp+280h+var_250], 0
0x180016266  lea     r9, [rsp+280h+var_250]
0x18001626b  lea     r8, _GUID_fa3f6186_4214_428c_a64c_14c9ac7315ea
0x180016272  mov     edx, 2000h
0x180016277  lea     rcx, [rsp+280h+Dst]
0x18001627c  call    cs:__imp_CreateStorageItemFromPath_FullTrustCaller
0x180016282  mov     ebx, eax
0x180016284  test    eax, eax
0x180016286  jns     short loc_1800162A8
0x180016288  mov     rcx, [rbp+188h]; this
0x18001628f  mov     r9d, eax; char *
0x180016292  lea     r8, aPcshellShellPe; "pcshell\\shell\\performancetracehandler"...
0x180016299  mov     edx, 1E5h; void *
0x18001629e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800162a3  jmp     loc_180016383
0x1800162a8  mov     qword ptr [rsp+280h+var_260], 0; int
0x1800162b1  mov     [rsp+280h+string], 0
0x1800162ba  lea     r9, [rsp+280h+string]; string
0x1800162bf  lea     r8, [rsp+280h+hstringHeader]; hstringHeader
0x1800162c4  mov     edx, 40h ; '@'; length
0x1800162c9  lea     rcx, ?RuntimeClass_Windows_ApplicationModel_DataTransfer_SharedStorageAccessManager@@3QBGB; "Windows.ApplicationModel.DataTransfer.S"...
0x1800162d0  call    cs:__imp_WindowsCreateStringReference
0x1800162d6  test    eax, eax
0x1800162d8  jns     short loc_1800162ED
0x1800162da  xor     r9d, r9d; lpArguments
0x1800162dd  xor     r8d, r8d; nNumberOfArguments
0x1800162e0  lea     edx, [r9+1]; dwExceptionFlags
0x1800162e4  mov     ecx, eax; dwExceptionCode
0x1800162e6  call    cs:__imp_RaiseException
0x1800162ec  int     3; Trap to Debugger
0x1800162ed  lea     r8, [rsp+280h+var_260]
0x1800162f2  lea     rdx, _GUID_c6132ada_34b1_4849_bd5f_d09fee3158c5
0x1800162f9  mov     rcx, [rsp+280h+string]
0x1800162fe  call    cs:__imp_RoGetActivationFactory
0x180016304  mov     ebx, eax
0x180016306  test    eax, eax
0x180016308  jns     short loc_180016327
0x18001630a  mov     rcx, [rbp+188h]; this
0x180016311  mov     r9d, eax; char *
0x180016314  lea     r8, aPcshellShellPe; "pcshell\\shell\\performancetracehandler"...
0x18001631b  mov     edx, 1E8h; void *
0x180016320  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016325  jmp     short loc_180016378
0x180016327  mov     [rsp+280h+var_258], 0
0x180016330  mov     rcx, qword ptr [rsp+280h+var_260]
0x180016335  mov     rax, [rcx]
0x180016338  lea     r8, [rsp+280h+var_258]
0x18001633d  mov     rdx, [rsp+280h+var_250]
0x180016342  mov     rax, [rax+30h]
0x180016346  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001634b  mov     ebx, eax
0x18001634d  test    eax, eax
0x18001634f  jns     short loc_18001638F
0x180016351  mov     rcx, [rbp+188h]; this
0x180016358  mov     r9d, eax; char *
0x18001635b  lea     r8, aPcshellShellPe; "pcshell\\shell\\performancetracehandler"...
0x180016362  mov     edx, 1EAh; void *
0x180016367  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001636c  nop
0x18001636d  lea     rcx, [rsp+280h+var_258]
0x180016372  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x180016377  nop
0x180016378  lea     rcx, [rsp+280h+var_260]
0x18001637d  call    ??1?$com_ptr_t@UIStorageItem@Storage@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageItem,wil::err_returncode_policy>::~com_ptr_t<Windows::Storage::IStorageItem,wil::err_returncode_policy>(void)
0x180016382  nop
0x180016383  lea     rcx, [rsp+280h+var_250]
0x180016388  call    ??1?$com_ptr_t@UIStorageItem@Storage@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageItem,wil::err_returncode_policy>::~com_ptr_t<Windows::Storage::IStorageItem,wil::err_returncode_policy>(void)
0x18001638d  jmp     short loc_180016400
0x18001638f  mov     rax, [rsp+280h+var_258]
0x180016394  test    rax, rax
0x180016397  jz      short loc_1800163B0
0x180016399  test    byte ptr [rax], 1
0x18001639c  jnz     short loc_1800163A4
0x18001639e  lock inc dword ptr [rax+18h]
0x1800163a2  jmp     short loc_1800163B0
0x1800163a4  mov     edx, [rax+4]; winrt::impl *
0x1800163a7  mov     rcx, [rax+10h]; this
0x1800163ab  call    ?create_hstring_on_heap@impl@winrt@@YAPEAUhstring_header@12@PEBGI@Z; winrt::impl::create_hstring_on_heap(ushort const *,uint)
0x1800163b0  mov     rdx, rax
0x1800163b3  mov     rcx, rdi
0x1800163b6  call    ?attach@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXPEAUhstring_header@impl@2@@Z; winrt::handle_type<winrt::impl::hstring_traits>::attach(winrt::impl::hstring_header *)
0x1800163bb  nop
0x1800163bc  lea     rcx, [rsp+280h+var_258]
0x1800163c1  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x1800163c6  nop
0x1800163c7  lea     rcx, [rsp+280h+var_260]
0x1800163cc  call    ??1?$com_ptr_t@UIStorageItem@Storage@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageItem,wil::err_returncode_policy>::~com_ptr_t<Windows::Storage::IStorageItem,wil::err_returncode_policy>(void)
0x1800163d1  nop
0x1800163d2  lea     rcx, [rsp+280h+var_250]
0x1800163d7  call    ??1?$com_ptr_t@UIStorageItem@Storage@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageItem,wil::err_returncode_policy>::~com_ptr_t<Windows::Storage::IStorageItem,wil::err_returncode_policy>(void)
0x1800163dc  xor     eax, eax
0x1800163de  jmp     short loc_180016402
0x1800163e0  mov     rcx, [rbp+188h]; this
0x1800163e7  mov     ebx, 80004005h
0x1800163ec  mov     r9d, ebx; char *
0x1800163ef  lea     r8, aPcshellShellPe; "pcshell\\shell\\performancetracehandler"...
0x1800163f6  mov     edx, 1E2h; void *
0x1800163fb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016400  mov     eax, ebx
0x180016402  mov     rcx, [rbp+180h+var_10]
0x180016409  xor     rcx, rsp; StackCookie
0x18001640c  call    __security_check_cookie
0x180016411  lea     r11, [rsp+280h+var_s0]
0x180016419  mov     rbx, [r11+10h]
0x18001641d  mov     rdi, [r11+20h]
0x180016421  mov     rsp, r11
0x180016424  pop     rbp
0x180016425  retn
```
