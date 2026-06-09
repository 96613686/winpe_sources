# StoreAppFinder::IsInboxStoreApp(ConfigSettings const &,Microsoft::WRL::ComPtr<Windows::ApplicationModel::IPackage> const &)

- ea: `0x1800d7e1c`
- end: `0x1800d80f5`
- name: `?IsInboxStoreApp@StoreAppFinder@@SA_NAEBVConfigSettings@@AEBV?$ComPtr@UIPackage@ApplicationModel@Windows@@@WRL@Microsoft@@@Z`
- size: `729`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800d5ab4`

## callees

- `0x180005890`
- `0x180005d10`
- `0x180005ec0`
- `0x180005f28`
- `0x18000a2d4`
- `0x18000faf0`
- `0x18001082c`
- `0x18001c5f0`
- `0x18002248c`
- `0x1800c97f0`
- `0x1800d59dc`
- `0x1800d5a60`
- `0x1800d799c`
- `0x1800d7e1c`
- `0x1800eb010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800d8055`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800d8087`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800d8055`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800d8087`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d7f7f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d7fe9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d7f7f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d7fe9`

## string_xrefs

- `0x1800d7f19`: `onecore\base\appcompat\inventory\software\inv\lib\storeappfinder.cpp`
- `0x1800d7f5e`: `onecore\base\appcompat\inventory\software\inv\lib\storeappfinder.cpp`
- `0x1800d7fc5`: `onecore\base\appcompat\inventory\software\inv\lib\storeappfinder.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
char __fastcall StoreAppFinder::IsInboxStoreApp(__int64 a1, __int64 *a2)
{
  HKEY ListOfInboxStoreApps; // rax
  __int64 v6; // rdi
  __int64 (__fastcall *v7)(__int64, __int64 **); // rbx
  int v8; // eax
  __int64 v9; // rax
  int v10; // eax
  PCWSTR StringRawBuffer; // rax
  __int64 v12; // rax
  int v13; // eax
  char v14; // si
  PCWSTR v15; // rax
  _QWORD *i; // rbx
  _QWORD *v17; // rcx
  __int64 v18; // rax
  __int64 v19; // rdi
  _QWORD *v20; // rdx
  _QWORD *v21; // rcx
  _QWORD *v22; // rdx
  _QWORD *v23; // rax
  __int64 *v24; // [rsp+20h] [rbp-39h] BYREF
  HSTRING v25; // [rsp+28h] [rbp-31h] BYREF
  HSTRING string; // [rsp+30h] [rbp-29h] BYREF
  HSTRING *p_string; // [rsp+38h] [rbp-21h] BYREF
  __int64 v28; // [rsp+40h] [rbp-19h] BYREF
  char v29; // [rsp+48h] [rbp-11h]
  _QWORD v30[2]; // [rsp+50h] [rbp-9h] BYREF
  unsigned __int64 v31; // [rsp+60h] [rbp+7h]
  unsigned __int64 v32; // [rsp+68h] [rbp+Fh]
  _QWORD v33[4]; // [rsp+70h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  if ( dword_180122EC8 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_180122EC8);
    if ( dword_180122EC8 == -1 )
    {
      atexit(StoreAppFinder::IsInboxStoreApp_::_2_::_dynamic_atexit_destructor_for__inboxStoreAppPackageIds__);
      Init_thread_footer(&dword_180122EC8);
    }
  }
  if ( byte_180120D9D )
  {
    ListOfInboxStoreApps = StoreAppFinder::GetListOfInboxStoreApps((HKEY)&p_string, a1);
    std::vector<std::wstring>::operator=(&qword_180122ED0, ListOfInboxStoreApps);
    std::vector<std::wstring>::_Tidy(&p_string);
    byte_180120D9D = 0;
  }
  if ( qword_180122ED8 == qword_180122ED0 )
    return 0;
  v24 = 0;
  v6 = *a2;
  v7 = *(__int64 (__fastcall **)(__int64, __int64 **))(*(_QWORD *)v6 + 48LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v24);
  v8 = v7(v6, &v24);
  if ( v8 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0xB8,
      (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeappfinder.cpp",
      (const char *)(unsigned int)v8,
      (int)v24);
  string = 0;
  v9 = *v24;
  p_string = &string;
  v28 = 0;
  v29 = 1;
  v10 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v9 + 48))(v24, &v28);
  if ( v10 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0xBC,
      (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeappfinder.cpp",
      (const char *)(unsigned int)v10,
      (int)v24);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(&p_string);
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  std::wstring::wstring(v33, StringRawBuffer);
  v25 = 0;
  v12 = *v24;
  p_string = &v25;
  v28 = 0;
  v29 = 1;
  v13 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v12 + 88))(v24, &v28);
  if ( v13 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0xC1,
      (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeappfinder.cpp",
      (const char *)(unsigned int)v13,
      (int)v24);
  v14 = 0;
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(&p_string);
  v15 = WindowsGetStringRawBuffer(v25, 0);
  std::wstring::wstring(v30, v15);
  for ( i = (_QWORD *)qword_180122ED0; i != (_QWORD *)qword_180122ED8; i += 4 )
  {
    v17 = i[3] <= 7u ? i : (_QWORD *)*i;
    v18 = -1;
    do
      ++v18;
    while ( *((_WORD *)v17 + v18) );
    v19 = (unsigned int)v18;
    if ( v31 > (unsigned int)v18 )
      break;
    v20 = v33;
    if ( v33[3] > 7u )
      v20 = (_QWORD *)v33[0];
    if ( i[3] <= 7u )
      v21 = i;
    else
      v21 = (_QWORD *)*i;
    if ( !(unsigned int)_o__wcsnicmp(v21, v20, v33[2]) )
    {
      v22 = v30;
      if ( v32 > 7 )
        v22 = (_QWORD *)v30[0];
      v23 = i[3] <= 7u ? i : (_QWORD *)*i;
      if ( !(unsigned int)_o__wcsnicmp((char *)v23 + 2 * (v19 - v31), v22, v31) )
      {
        v14 = 1;
        break;
      }
    }
  }
  std::wstring::_Tidy_deallocate(v30);
  Windows::Internal::String::~String(&v25);
  std::wstring::_Tidy_deallocate(v33);
  Windows::Internal::String::~String(&string);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v24);
  return v14;
}

```

## disassembly

```asm
0x1800d7e1c  mov     [rsp-8+arg_10], rbx
0x1800d7e21  mov     [rsp-8+arg_18], rsi
0x1800d7e26  push    rbp
0x1800d7e27  push    rdi
0x1800d7e28  push    r14
0x1800d7e2a  lea     rbp, [rsp-47h]
0x1800d7e2f  sub     rsp, 0A0h
0x1800d7e36  mov     rax, cs:__security_cookie
0x1800d7e3d  xor     rax, rsp
0x1800d7e40  mov     [rbp+57h+var_20], rax
0x1800d7e44  mov     rdi, rdx
0x1800d7e47  mov     rbx, rcx
0x1800d7e4a  mov     ecx, cs:_tls_index
0x1800d7e50  mov     rax, gs:58h
0x1800d7e59  mov     edx, 4
0x1800d7e5e  mov     rax, [rax+rcx*8]
0x1800d7e62  mov     eax, [rdx+rax]
0x1800d7e65  cmp     cs:dword_180122EC8, eax
0x1800d7e6b  jle     short loc_1800D7E9A
0x1800d7e6d  lea     rcx, dword_180122EC8
0x1800d7e74  call    _Init_thread_header
0x1800d7e79  cmp     cs:dword_180122EC8, 0FFFFFFFFh
0x1800d7e80  jnz     short loc_1800D7E9A
0x1800d7e82  lea     rcx, _StoreAppFinder__IsInboxStoreApp____2____dynamic_atexit_destructor_for__inboxStoreAppPackageIds__; void (__cdecl *)()
0x1800d7e89  call    atexit
0x1800d7e8e  lea     rcx, dword_180122EC8
0x1800d7e95  call    _Init_thread_footer
0x1800d7e9a  xor     r14d, r14d
0x1800d7e9d  cmp     cs:byte_180120D9D, r14b
0x1800d7ea4  jz      short loc_1800D7ED1
0x1800d7ea6  mov     rdx, rbx
0x1800d7ea9  lea     rcx, [rbp+57h+var_78]
0x1800d7ead  call    ?GetListOfInboxStoreApps@StoreAppFinder@@SA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEBVConfigSettings@@@Z; StoreAppFinder::GetListOfInboxStoreApps(ConfigSettings const &)
0x1800d7eb2  mov     rdx, rax
0x1800d7eb5  lea     rcx, qword_180122ED0
0x1800d7ebc  call    ??4?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<std::wstring>::operator=(std::vector<std::wstring> &&)
0x1800d7ec1  lea     rcx, [rbp+57h+var_78]
0x1800d7ec5  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800d7eca  mov     cs:byte_180120D9D, r14b
0x1800d7ed1  mov     rax, cs:qword_180122ED8
0x1800d7ed8  cmp     rax, cs:qword_180122ED0
0x1800d7edf  jnz     short loc_1800D7EE8
0x1800d7ee1  xor     al, al
0x1800d7ee3  jmp     loc_1800D80D1
0x1800d7ee8  mov     [rbp+57h+var_90], r14
0x1800d7eec  mov     rdi, [rdi]
0x1800d7eef  mov     rax, [rdi]
0x1800d7ef2  mov     rbx, [rax+30h]
0x1800d7ef6  lea     rcx, [rbp+57h+var_90]
0x1800d7efa  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800d7eff  lea     rdx, [rbp+57h+var_90]
0x1800d7f03  mov     rcx, rdi
0x1800d7f06  mov     rax, rbx
0x1800d7f09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d7f0e  mov     rcx, [rbp+5Fh]; this
0x1800d7f12  test    eax, eax
0x1800d7f14  jns     short loc_1800D7F2B
0x1800d7f16  mov     r9d, eax; char *
0x1800d7f19  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appcompat\\inventory\\so"...
0x1800d7f20  mov     edx, 0B8h; void *
0x1800d7f25  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800d7f2b  mov     [rbp+57h+string], r14
0x1800d7f2f  mov     rcx, [rbp+57h+var_90]
0x1800d7f33  mov     rax, [rcx]
0x1800d7f36  lea     rdx, [rbp+57h+string]
0x1800d7f3a  mov     [rbp+57h+var_78], rdx
0x1800d7f3e  mov     [rbp+57h+var_70], r14
0x1800d7f42  mov     [rbp+57h+var_68], 1
0x1800d7f46  lea     rdx, [rbp+57h+var_70]
0x1800d7f4a  mov     rax, [rax+30h]
0x1800d7f4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d7f53  mov     rcx, [rbp+5Fh]; this
0x1800d7f57  test    eax, eax
0x1800d7f59  jns     short loc_1800D7F70
0x1800d7f5b  mov     r9d, eax; char *
0x1800d7f5e  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appcompat\\inventory\\so"...
0x1800d7f65  mov     edx, 0BCh; void *
0x1800d7f6a  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800d7f70  lea     rcx, [rbp+57h+var_78]
0x1800d7f74  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(void)
0x1800d7f79  xor     edx, edx; length
0x1800d7f7b  mov     rcx, [rbp+57h+string]; string
0x1800d7f7f  call    cs:__imp_WindowsGetStringRawBuffer
0x1800d7f85  mov     rdx, rax
0x1800d7f88  lea     rcx, [rbp+57h+var_40]
0x1800d7f8c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800d7f91  nop
0x1800d7f92  mov     [rbp+57h+var_88], r14
0x1800d7f96  mov     rcx, [rbp+57h+var_90]
0x1800d7f9a  mov     rax, [rcx]
0x1800d7f9d  lea     rdx, [rbp+57h+var_88]
0x1800d7fa1  mov     [rbp+57h+var_78], rdx
0x1800d7fa5  mov     [rbp+57h+var_70], r14
0x1800d7fa9  mov     [rbp+57h+var_68], 1
0x1800d7fad  lea     rdx, [rbp+57h+var_70]
0x1800d7fb1  mov     rax, [rax+58h]
0x1800d7fb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d7fba  mov     rcx, [rbp+5Fh]; this
0x1800d7fbe  test    eax, eax
0x1800d7fc0  jns     short loc_1800D7FD7
0x1800d7fc2  mov     r9d, eax; char *
0x1800d7fc5  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appcompat\\inventory\\so"...
0x1800d7fcc  mov     edx, 0C1h; void *
0x1800d7fd1  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800d7fd7  mov     sil, r14b
0x1800d7fda  lea     rcx, [rbp+57h+var_78]
0x1800d7fde  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(void)
0x1800d7fe3  xor     edx, edx; length
0x1800d7fe5  mov     rcx, [rbp+57h+var_88]; string
0x1800d7fe9  call    cs:__imp_WindowsGetStringRawBuffer
0x1800d7fef  mov     rdx, rax
0x1800d7ff2  lea     rcx, [rbp+57h+var_60]
0x1800d7ff6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800d7ffb  mov     rbx, cs:qword_180122ED0
0x1800d8002  cmp     rbx, cs:qword_180122ED8
0x1800d8009  jz      loc_1800D809D
0x1800d800f  cmp     qword ptr [rbx+18h], 7
0x1800d8014  jbe     short loc_1800D801B
0x1800d8016  mov     rcx, [rbx]
0x1800d8019  jmp     short loc_1800D801E
0x1800d801b  mov     rcx, rbx
0x1800d801e  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800d8022  inc     rax
0x1800d8025  cmp     [rcx+rax*2], r14w
0x1800d802a  jnz     short loc_1800D8022
0x1800d802c  mov     edi, eax
0x1800d802e  cmp     [rbp+57h+var_50], rdi
0x1800d8032  ja      short loc_1800D809D
0x1800d8034  lea     rdx, [rbp+57h+var_40]
0x1800d8038  cmp     [rbp+57h+var_28], 7
0x1800d803d  cmova   rdx, [rbp+57h+var_40]
0x1800d8042  cmp     qword ptr [rbx+18h], 7
0x1800d8047  jbe     short loc_1800D804E
0x1800d8049  mov     rcx, [rbx]
0x1800d804c  jmp     short loc_1800D8051
0x1800d804e  mov     rcx, rbx
0x1800d8051  mov     r8, [rbp+57h+var_30]
0x1800d8055  call    cs:__imp__o__wcsnicmp
0x1800d805b  test    eax, eax
0x1800d805d  jnz     short loc_1800D8091
0x1800d805f  mov     r8, [rbp+57h+var_50]
0x1800d8063  lea     rdx, [rbp+57h+var_60]
0x1800d8067  cmp     [rbp+57h+var_48], 7
0x1800d806c  cmova   rdx, [rbp+57h+var_60]
0x1800d8071  cmp     qword ptr [rbx+18h], 7
0x1800d8076  jbe     short loc_1800D807D
0x1800d8078  mov     rax, [rbx]
0x1800d807b  jmp     short loc_1800D8080
0x1800d807d  mov     rax, rbx
0x1800d8080  sub     rdi, r8
0x1800d8083  lea     rcx, [rax+rdi*2]
0x1800d8087  call    cs:__imp__o__wcsnicmp
0x1800d808d  test    eax, eax
0x1800d808f  jz      short loc_1800D809A
0x1800d8091  add     rbx, 20h ; ' '
0x1800d8095  jmp     loc_1800D8002
0x1800d809a  mov     sil, 1
0x1800d809d  lea     rcx, [rbp+57h+var_60]
0x1800d80a1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800d80a6  nop
0x1800d80a7  lea     rcx, [rbp+57h+var_88]; this
0x1800d80ab  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800d80b0  nop
0x1800d80b1  lea     rcx, [rbp+57h+var_40]
0x1800d80b5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800d80ba  nop
0x1800d80bb  lea     rcx, [rbp+57h+string]; this
0x1800d80bf  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800d80c4  nop
0x1800d80c5  lea     rcx, [rbp+57h+var_90]
0x1800d80c9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800d80ce  mov     al, sil
0x1800d80d1  mov     rcx, [rbp+57h+var_20]
0x1800d80d5  xor     rcx, rsp; StackCookie
0x1800d80d8  call    __security_check_cookie
0x1800d80dd  lea     r11, [rsp+0B0h+var_10]
0x1800d80e5  mov     rbx, [r11+30h]
0x1800d80e9  mov     rsi, [r11+38h]
0x1800d80ed  mov     rsp, r11
0x1800d80f0  pop     r14
0x1800d80f2  pop     rdi
0x1800d80f3  pop     rbp
0x1800d80f4  retn
```
