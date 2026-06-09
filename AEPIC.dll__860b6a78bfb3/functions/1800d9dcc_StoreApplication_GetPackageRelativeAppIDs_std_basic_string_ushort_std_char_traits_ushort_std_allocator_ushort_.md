# StoreApplication::GetPackageRelativeAppIDs(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::vector<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>> &)

- ea: `0x1800d9dcc`
- end: `0x1800da07c`
- name: `?GetPackageRelativeAppIDs@StoreApplication@@SAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@3@@Z`
- size: `688`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800c8770`
- `0x1800dc88c`

## callees

- `0x180005890`
- `0x18000a2d4`
- `0x18000faf0`
- `0x18001c5f0`
- `0x1800c30d4`
- `0x1800c97f0`
- `0x1800c9810`
- `0x1800cea08`
- `0x1800d904c`
- `0x1800d9dcc`
- `0x1800dba8c`
- `0x1800e02ec`
- `0x1800eb010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d9f08`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800da024`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d9f08`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800da024`

## string_xrefs

- `0x1800d9e4a`: `onecore\base\appcompat\inventory\software\inv\lib\storeapplication.cpp`
- `0x1800d9e6a`: `onecore\base\appcompat\inventory\software\inv\lib\storeapplication.cpp`
- `0x1800da03c`: `onecore\base\appcompat\inventory\software\inv\lib\storeapplication.cpp`
- `0x1800da055`: `onecore\base\appcompat\inventory\software\inv\lib\storeapplication.cpp`
- `0x1800da06a`: `onecore\base\appcompat\inventory\software\inv\lib\storeapplication.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall StoreApplication::GetPackageRelativeAppIDs(__int64 a1)
{
  __int64 v2; // rdi
  __int64 (__fastcall *v3)(__int64, __int64 *); // rbx
  int v4; // eax
  const char *v5; // r9
  int v7; // [rsp+20h] [rbp-99h] BYREF
  __int64 v8; // [rsp+30h] [rbp-89h] BYREF
  __int64 v9; // [rsp+48h] [rbp-71h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  v9 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v9);
  StoreApplication::GetStoreAppManifestReaderFromManifestPath(a1, &v9);
  v8 = 0;
  v2 = v9;
  v3 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v9 + 80LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v8);
  v4 = v3(v2, &v8);
  if ( v4 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x406,
      (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeapplication.cpp",
      (const char *)(unsigned int)v4,
      v7);
  if ( !v8 )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x407,
      (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeapplication.cpp",
      v5);
  v7 = 0;
  (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v8 + 32LL))(v8, &v7);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v8);
  return Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v9);
}

```

## disassembly

```asm
0x1800d9dcc  mov     [rsp-8+arg_10], rbx
0x1800d9dd1  push    rbp
0x1800d9dd2  push    rsi
0x1800d9dd3  push    rdi
0x1800d9dd4  lea     rbp, [rsp-47h]
0x1800d9dd9  sub     rsp, 100h
0x1800d9de0  mov     rax, cs:__security_cookie
0x1800d9de7  xor     rax, rsp
0x1800d9dea  mov     [rbp+57h+var_20], rax
0x1800d9dee  mov     rsi, rdx
0x1800d9df1  mov     rbx, rcx
0x1800d9df4  mov     [rbp+57h+var_C8], 0
0x1800d9dfc  lea     rcx, [rbp+57h+var_C8]
0x1800d9e00  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800d9e05  lea     rdx, [rbp+57h+var_C8]
0x1800d9e09  mov     rcx, rbx
0x1800d9e0c  call    ?GetStoreAppManifestReaderFromManifestPath@StoreApplication@@SAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAPEAUIAppxManifestReader@@@Z; StoreApplication::GetStoreAppManifestReaderFromManifestPath(std::wstring const &,IAppxManifestReader * *)
0x1800d9e11  mov     [rsp+110h+var_E0], 0
0x1800d9e1a  mov     rdi, [rbp+57h+var_C8]
0x1800d9e1e  mov     rax, [rdi]
0x1800d9e21  mov     rbx, [rax+50h]
0x1800d9e25  lea     rcx, [rsp+110h+var_E0]
0x1800d9e2a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800d9e2f  lea     rdx, [rsp+110h+var_E0]
0x1800d9e34  mov     rcx, rdi
0x1800d9e37  mov     rax, rbx
0x1800d9e3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d9e3f  mov     rcx, [rbp+5Fh]; this
0x1800d9e43  test    eax, eax
0x1800d9e45  jns     short loc_1800D9E5C
0x1800d9e47  mov     r9d, eax; char *
0x1800d9e4a  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appcompat\\inventory\\so"...
0x1800d9e51  mov     edx, 406h; void *
0x1800d9e56  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800d9e5c  mov     rax, [rbp+5Fh]
0x1800d9e60  mov     rcx, [rsp+110h+var_E0]
0x1800d9e65  test    rcx, rcx
0x1800d9e68  jnz     short loc_1800D9E7F
0x1800d9e6a  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appcompat\\inventory\\so"...
0x1800d9e71  mov     edx, 407h; void *
0x1800d9e76  mov     rcx, rax; this
0x1800d9e79  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x1800d9e7f  mov     [rsp+110h+var_F0], 0
0x1800d9e87  mov     rax, [rcx]
0x1800d9e8a  mov     rax, [rax+20h]
0x1800d9e8e  jmp     loc_1800D9F25
0x1800d9e93  mov     [rsp+110h+var_E8], 0
0x1800d9e9c  mov     rdi, [rsp+110h+var_E0]
0x1800d9ea1  mov     rax, [rdi]
0x1800d9ea4  mov     rbx, [rax+18h]
0x1800d9ea8  lea     rcx, [rsp+110h+var_E8]
0x1800d9ead  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800d9eb2  lea     rdx, [rsp+110h+var_E8]
0x1800d9eb7  mov     rcx, rdi
0x1800d9eba  mov     rax, rbx
0x1800d9ebd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d9ec2  mov     rcx, [rbp+5Fh]; this
0x1800d9ec6  test    eax, eax
0x1800d9ec8  js      loc_1800DA067
0x1800d9ece  mov     [rsp+110h+pv], 0
0x1800d9ed7  mov     rcx, [rsp+110h+var_E8]
0x1800d9edc  mov     rax, [rcx]
0x1800d9edf  lea     r8, [rsp+110h+pv]
0x1800d9ee4  lea     rdx, aId; "Id"
0x1800d9eeb  mov     rax, [rax+18h]
0x1800d9eef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d9ef4  mov     rcx, [rsp+110h+pv]; pv
0x1800d9ef9  test    eax, eax
0x1800d9efb  jns     short loc_1800D9F6D
0x1800d9efd  cmp     eax, 80070057h
0x1800d9f02  jnz     loc_1800DA035
0x1800d9f08  call    cs:__imp_CoTaskMemFree
0x1800d9f0e  nop
0x1800d9f0f  lea     rcx, [rsp+110h+var_E8]
0x1800d9f14  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800d9f19  mov     rcx, [rsp+110h+var_E0]
0x1800d9f1e  mov     rax, [rcx]
0x1800d9f21  mov     rax, [rax+28h]
0x1800d9f25  lea     rdx, [rsp+110h+var_F0]
0x1800d9f2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d9f2f  cmp     [rsp+110h+var_F0], 0
0x1800d9f34  jnz     loc_1800D9E93
0x1800d9f3a  lea     rcx, [rsp+110h+var_E0]
0x1800d9f3f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800d9f44  nop
0x1800d9f45  lea     rcx, [rbp+57h+var_C8]
0x1800d9f49  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800d9f4e  mov     rcx, [rbp+57h+var_20]
0x1800d9f52  xor     rcx, rsp; StackCookie
0x1800d9f55  call    __security_check_cookie
0x1800d9f5a  mov     rbx, [rsp+110h+arg_10]
0x1800d9f62  add     rsp, 100h
0x1800d9f69  pop     rdi
0x1800d9f6a  pop     rsi
0x1800d9f6b  pop     rbp
0x1800d9f6c  retn
0x1800d9f6d  test    rcx, rcx
0x1800d9f70  jz      short loc_1800D9F08
0x1800d9f72  mov     [rbp+57h+var_D0], 0
0x1800d9f7a  mov     rcx, [rsp+110h+var_E8]
0x1800d9f7f  mov     rax, [rcx]
0x1800d9f82  lea     r8, [rbp+57h+var_D0]
0x1800d9f86  lea     rdx, aExecutable; "Executable"
0x1800d9f8d  mov     rax, [rax+18h]
0x1800d9f91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d9f96  mov     rcx, [rbp+57h+var_D0]
0x1800d9f9a  test    eax, eax
0x1800d9f9c  jns     short loc_1800D9FAB
0x1800d9f9e  cmp     eax, 80070057h
0x1800d9fa3  jnz     loc_1800DA04E
0x1800d9fa9  jmp     short loc_1800DA024
0x1800d9fab  test    rcx, rcx
0x1800d9fae  jz      short loc_1800D9FA9
0x1800d9fb0  mov     rdx, [rsp+110h+pv]
0x1800d9fb5  lea     rcx, [rbp+57h+var_A0]
0x1800d9fb9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800d9fbe  nop
0x1800d9fbf  mov     rdx, [rbp+57h+var_D0]
0x1800d9fc3  lea     rcx, [rbp+57h+var_C0]
0x1800d9fc7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800d9fcc  nop
0x1800d9fcd  lea     rdx, [rbp+57h+var_C0]
0x1800d9fd1  lea     rcx, [rbp+57h+var_80]
0x1800d9fd5  call    ?ToLower@Utility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z; Utility::ToLower(std::wstring const &)
0x1800d9fda  nop
0x1800d9fdb  mov     r8, rax
0x1800d9fde  lea     rdx, [rbp+57h+var_A0]
0x1800d9fe2  lea     rcx, [rbp+57h+var_60]
0x1800d9fe6  call    ??$make_pair@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@YA?AU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@0@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV20@@Z; std::make_pair<std::wstring &,std::wstring>(std::wstring &,std::wstring &&)
0x1800d9feb  nop
0x1800d9fec  mov     rdx, rax
0x1800d9fef  mov     rcx, rsi
0x1800d9ff2  call    ?push_back@?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAAX$$QEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@2@@Z; std::vector<std::pair<std::wstring,std::wstring>>::push_back(std::pair<std::wstring,std::wstring> &&)
0x1800d9ff7  nop
0x1800d9ff8  lea     rcx, [rbp+57h+var_60]
0x1800d9ffc  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@QEAA@XZ; std::pair<std::wstring,std::wstring>::~pair<std::wstring,std::wstring>(void)
0x1800da001  nop
0x1800da002  lea     rcx, [rbp+57h+var_80]
0x1800da006  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800da00b  nop
0x1800da00c  lea     rcx, [rbp+57h+var_C0]
0x1800da010  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800da015  nop
0x1800da016  lea     rcx, [rbp+57h+var_A0]
0x1800da01a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800da01f  nop
0x1800da020  mov     rcx, [rbp+57h+var_D0]; pv
0x1800da024  call    cs:__imp_CoTaskMemFree
0x1800da02a  nop
0x1800da02b  mov     rcx, [rsp+110h+pv]
0x1800da030  jmp     loc_1800D9F08
0x1800da035  mov     rcx, [rbp+5Fh]; this
0x1800da039  mov     r9d, eax; char *
0x1800da03c  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appcompat\\inventory\\so"...
0x1800da043  mov     edx, 415h; void *
0x1800da048  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800da04e  mov     rcx, [rbp+5Fh]; this
0x1800da052  mov     r9d, eax; char *
0x1800da055  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appcompat\\inventory\\so"...
0x1800da05c  mov     edx, 422h; void *
0x1800da061  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800da067  mov     r9d, eax; char *
0x1800da06a  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appcompat\\inventory\\so"...
0x1800da071  mov     edx, 40Eh; void *
0x1800da076  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
