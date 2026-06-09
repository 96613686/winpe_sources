# StoreApplication::IsInboxStoreApp(ConfigSettings const &,Microsoft::WRL::ComPtr<Windows::ApplicationModel::IPackage> const &)

- ea: `0x1800de63c`
- end: `0x1800de915`
- name: `?IsInboxStoreApp@StoreApplication@@SA_NAEBVConfigSettings@@AEBV?$ComPtr@UIPackage@ApplicationModel@Windows@@@WRL@Microsoft@@@Z`
- size: `729`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800dc88c`

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
- `0x1800de63c`
- `0x1800eb010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800de875`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800de8a7`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800de875`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800de8a7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800de79f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800de809`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800de79f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800de809`

## string_xrefs

- `0x1800de739`: `onecore\base\appcompat\inventory\software\inv\lib\storeapplication.cpp`
- `0x1800de77e`: `onecore\base\appcompat\inventory\software\inv\lib\storeapplication.cpp`
- `0x1800de7e5`: `onecore\base\appcompat\inventory\software\inv\lib\storeapplication.cpp`

## pseudocode

```c
char __fastcall StoreApplication::IsInboxStoreApp(__int64 a1, __int64 *a2)
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

  if ( dword_180122EE8 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_180122EE8);
    if ( dword_180122EE8 == -1 )
    {
      atexit(StoreApplication::IsInboxStoreApp_::_2_::_dynamic_atexit_destructor_for__inboxStoreAppPackageIds__);
      Init_thread_footer(&dword_180122EE8);
    }
  }
  if ( byte_180120D9E )
  {
    ListOfInboxStoreApps = StoreAppFinder::GetListOfInboxStoreApps((HKEY)&p_string, a1);
    std::vector<std::wstring>::operator=(&qword_180122EF0, ListOfInboxStoreApps);
    std::vector<std::wstring>::_Tidy(&p_string);
    byte_180120D9E = 0;
  }
  if ( qword_180122EF8 == qword_180122EF0 )
    return 0;
  v24 = 0;
  v6 = *a2;
  v7 = *(__int64 (__fastcall **)(__int64, __int64 **))(*(_QWORD *)v6 + 48LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v24);
  v8 = v7(v6, &v24);
  if ( v8 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x548,
      (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeapplication.cpp",
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
      (void *)0x54C,
      (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeapplication.cpp",
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
      (void *)0x551,
      (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeapplication.cpp",
      (const char *)(unsigned int)v13,
      (int)v24);
  v14 = 0;
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(&p_string);
  v15 = WindowsGetStringRawBuffer(v25, 0);
  std::wstring::wstring(v30, v15);
  for ( i = (_QWORD *)qword_180122EF0; i != (_QWORD *)qword_180122EF8; i += 4 )
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
0x1800de63c  mov     [rsp-8+arg_10], rbx
0x1800de641  mov     [rsp-8+arg_18], rsi
0x1800de646  push    rbp
0x1800de647  push    rdi
0x1800de648  push    r14
0x1800de64a  lea     rbp, [rsp-47h]
0x1800de64f  sub     rsp, 0A0h
0x1800de656  mov     rax, cs:__security_cookie
0x1800de65d  xor     rax, rsp
0x1800de660  mov     [rbp+57h+var_20], rax
0x1800de664  mov     rdi, rdx
0x1800de667  mov     rbx, rcx
0x1800de66a  mov     ecx, cs:_tls_index
0x1800de670  mov     rax, gs:58h
0x1800de679  mov     edx, 4
0x1800de67e  mov     rax, [rax+rcx*8]
0x1800de682  mov     eax, [rdx+rax]
0x1800de685  cmp     cs:dword_180122EE8, eax
0x1800de68b  jle     short loc_1800DE6BA
0x1800de68d  lea     rcx, dword_180122EE8
0x1800de694  call    _Init_thread_header
0x1800de699  cmp     cs:dword_180122EE8, 0FFFFFFFFh
0x1800de6a0  jnz     short loc_1800DE6BA
0x1800de6a2  lea     rcx, _StoreApplication__IsInboxStoreApp____2____dynamic_atexit_destructor_for__inboxStoreAppPackageIds__; void (__cdecl *)()
0x1800de6a9  call    atexit
0x1800de6ae  lea     rcx, dword_180122EE8
0x1800de6b5  call    _Init_thread_footer
0x1800de6ba  xor     r14d, r14d
0x1800de6bd  cmp     cs:byte_180120D9E, r14b
0x1800de6c4  jz      short loc_1800DE6F1
0x1800de6c6  mov     rdx, rbx
0x1800de6c9  lea     rcx, [rbp+57h+var_78]
0x1800de6cd  call    ?GetListOfInboxStoreApps@StoreAppFinder@@SA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEBVConfigSettings@@@Z; StoreAppFinder::GetListOfInboxStoreApps(ConfigSettings const &)
0x1800de6d2  mov     rdx, rax
0x1800de6d5  lea     rcx, qword_180122EF0
0x1800de6dc  call    ??4?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<std::wstring>::operator=(std::vector<std::wstring> &&)
0x1800de6e1  lea     rcx, [rbp+57h+var_78]
0x1800de6e5  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800de6ea  mov     cs:byte_180120D9E, r14b
0x1800de6f1  mov     rax, cs:qword_180122EF8
0x1800de6f8  cmp     rax, cs:qword_180122EF0
0x1800de6ff  jnz     short loc_1800DE708
0x1800de701  xor     al, al
0x1800de703  jmp     loc_1800DE8F1
0x1800de708  mov     [rbp+57h+var_90], r14
0x1800de70c  mov     rdi, [rdi]
0x1800de70f  mov     rax, [rdi]
0x1800de712  mov     rbx, [rax+30h]
0x1800de716  lea     rcx, [rbp+57h+var_90]
0x1800de71a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800de71f  lea     rdx, [rbp+57h+var_90]
0x1800de723  mov     rcx, rdi
0x1800de726  mov     rax, rbx
0x1800de729  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800de72e  mov     rcx, [rbp+5Fh]; this
0x1800de732  test    eax, eax
0x1800de734  jns     short loc_1800DE74B
0x1800de736  mov     r9d, eax; char *
0x1800de739  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appcompat\\inventory\\so"...
0x1800de740  mov     edx, 548h; void *
0x1800de745  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800de74b  mov     [rbp+57h+string], r14
0x1800de74f  mov     rcx, [rbp+57h+var_90]
0x1800de753  mov     rax, [rcx]
0x1800de756  lea     rdx, [rbp+57h+string]
0x1800de75a  mov     [rbp+57h+var_78], rdx
0x1800de75e  mov     [rbp+57h+var_70], r14
0x1800de762  mov     [rbp+57h+var_68], 1
0x1800de766  lea     rdx, [rbp+57h+var_70]
0x1800de76a  mov     rax, [rax+30h]
0x1800de76e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800de773  mov     rcx, [rbp+5Fh]; this
0x1800de777  test    eax, eax
0x1800de779  jns     short loc_1800DE790
0x1800de77b  mov     r9d, eax; char *
0x1800de77e  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appcompat\\inventory\\so"...
0x1800de785  mov     edx, 54Ch; void *
0x1800de78a  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800de790  lea     rcx, [rbp+57h+var_78]
0x1800de794  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(void)
0x1800de799  xor     edx, edx; length
0x1800de79b  mov     rcx, [rbp+57h+string]; string
0x1800de79f  call    cs:__imp_WindowsGetStringRawBuffer
0x1800de7a5  mov     rdx, rax
0x1800de7a8  lea     rcx, [rbp+57h+var_40]
0x1800de7ac  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800de7b1  nop
0x1800de7b2  mov     [rbp+57h+var_88], r14
0x1800de7b6  mov     rcx, [rbp+57h+var_90]
0x1800de7ba  mov     rax, [rcx]
0x1800de7bd  lea     rdx, [rbp+57h+var_88]
0x1800de7c1  mov     [rbp+57h+var_78], rdx
0x1800de7c5  mov     [rbp+57h+var_70], r14
0x1800de7c9  mov     [rbp+57h+var_68], 1
0x1800de7cd  lea     rdx, [rbp+57h+var_70]
0x1800de7d1  mov     rax, [rax+58h]
0x1800de7d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800de7da  mov     rcx, [rbp+5Fh]; this
0x1800de7de  test    eax, eax
0x1800de7e0  jns     short loc_1800DE7F7
0x1800de7e2  mov     r9d, eax; char *
0x1800de7e5  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appcompat\\inventory\\so"...
0x1800de7ec  mov     edx, 551h; void *
0x1800de7f1  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800de7f7  mov     sil, r14b
0x1800de7fa  lea     rcx, [rbp+57h+var_78]
0x1800de7fe  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(void)
0x1800de803  xor     edx, edx; length
0x1800de805  mov     rcx, [rbp+57h+var_88]; string
0x1800de809  call    cs:__imp_WindowsGetStringRawBuffer
0x1800de80f  mov     rdx, rax
0x1800de812  lea     rcx, [rbp+57h+var_60]
0x1800de816  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800de81b  mov     rbx, cs:qword_180122EF0
0x1800de822  cmp     rbx, cs:qword_180122EF8
0x1800de829  jz      loc_1800DE8BD
0x1800de82f  cmp     qword ptr [rbx+18h], 7
0x1800de834  jbe     short loc_1800DE83B
0x1800de836  mov     rcx, [rbx]
0x1800de839  jmp     short loc_1800DE83E
0x1800de83b  mov     rcx, rbx
0x1800de83e  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800de842  inc     rax
0x1800de845  cmp     [rcx+rax*2], r14w
0x1800de84a  jnz     short loc_1800DE842
0x1800de84c  mov     edi, eax
0x1800de84e  cmp     [rbp+57h+var_50], rdi
0x1800de852  ja      short loc_1800DE8BD
0x1800de854  lea     rdx, [rbp+57h+var_40]
0x1800de858  cmp     [rbp+57h+var_28], 7
0x1800de85d  cmova   rdx, [rbp+57h+var_40]
0x1800de862  cmp     qword ptr [rbx+18h], 7
0x1800de867  jbe     short loc_1800DE86E
0x1800de869  mov     rcx, [rbx]
0x1800de86c  jmp     short loc_1800DE871
0x1800de86e  mov     rcx, rbx
0x1800de871  mov     r8, [rbp+57h+var_30]
0x1800de875  call    cs:__imp__o__wcsnicmp
0x1800de87b  test    eax, eax
0x1800de87d  jnz     short loc_1800DE8B1
0x1800de87f  mov     r8, [rbp+57h+var_50]
0x1800de883  lea     rdx, [rbp+57h+var_60]
0x1800de887  cmp     [rbp+57h+var_48], 7
0x1800de88c  cmova   rdx, [rbp+57h+var_60]
0x1800de891  cmp     qword ptr [rbx+18h], 7
0x1800de896  jbe     short loc_1800DE89D
0x1800de898  mov     rax, [rbx]
0x1800de89b  jmp     short loc_1800DE8A0
0x1800de89d  mov     rax, rbx
0x1800de8a0  sub     rdi, r8
0x1800de8a3  lea     rcx, [rax+rdi*2]
0x1800de8a7  call    cs:__imp__o__wcsnicmp
0x1800de8ad  test    eax, eax
0x1800de8af  jz      short loc_1800DE8BA
0x1800de8b1  add     rbx, 20h ; ' '
0x1800de8b5  jmp     loc_1800DE822
0x1800de8ba  mov     sil, 1
0x1800de8bd  lea     rcx, [rbp+57h+var_60]
0x1800de8c1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800de8c6  nop
0x1800de8c7  lea     rcx, [rbp+57h+var_88]; this
0x1800de8cb  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800de8d0  nop
0x1800de8d1  lea     rcx, [rbp+57h+var_40]
0x1800de8d5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800de8da  nop
0x1800de8db  lea     rcx, [rbp+57h+string]; this
0x1800de8df  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800de8e4  nop
0x1800de8e5  lea     rcx, [rbp+57h+var_90]
0x1800de8e9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800de8ee  mov     al, sil
0x1800de8f1  mov     rcx, [rbp+57h+var_20]
0x1800de8f5  xor     rcx, rsp; StackCookie
0x1800de8f8  call    __security_check_cookie
0x1800de8fd  lea     r11, [rsp+0B0h+var_10]
0x1800de905  mov     rbx, [r11+30h]
0x1800de909  mov     rsi, [r11+38h]
0x1800de90d  mov     rsp, r11
0x1800de910  pop     r14
0x1800de912  pop     rdi
0x1800de913  pop     rbp
0x1800de914  retn
```
