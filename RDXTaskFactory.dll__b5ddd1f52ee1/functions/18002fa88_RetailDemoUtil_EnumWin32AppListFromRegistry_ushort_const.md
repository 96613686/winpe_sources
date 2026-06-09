# RetailDemoUtil::EnumWin32AppListFromRegistry(ushort const *)

- ea: `0x18002fa88`
- end: `0x18002fc60`
- name: `?EnumWin32AppListFromRegistry@RetailDemoUtil@@YA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@PEBG@Z`
- size: `472`
- prototype: ``
- caller_count: `3`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002b150`
- `0x180039b80`
- `0x1800415c8`

## callees

- `0x180003390`
- `0x18000649c`
- `0x180008bbc`
- `0x18000c168`
- `0x18000e0f0`
- `0x18000e3bc`
- `0x18001094c`
- `0x180010a60`
- `0x18002fa88`
- `0x180030de0`
- `0x18003262c`
- `0x180050010`

## import_xrefs

- `SHCORE!__imp_QuerySourceCreateFromKeyEx` at `0x18002fb26`
- `SHCORE!__imp_QuerySourceCreateFromKeyEx` at `0x18002fb26`

## string_xrefs

- `0x18002fada`: `shellcommon\shell\retaildemo\util\retaildemoutil.cpp`
- `0x18002fb3a`: `shellcommon\shell\retaildemo\util\retaildemoutil.cpp`
- `0x18002fb89`: `shellcommon\shell\retaildemo\util\retaildemoutil.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
RetailDemoUtil *__fastcall RetailDemoUtil::EnumWin32AppListFromRegistry(
        RetailDemoUtil *a1,
        unsigned __int16 *a2,
        __int64 a3,
        const unsigned __int16 *a4)
{
  int RetailDemoOriginRegistryLocation; // eax
  __int64 v6; // rdx
  __int64 v7; // r8
  int v8; // eax
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, __int64 *); // rbx
  int v13; // eax
  __int64 v14; // rdi
  unsigned int (__fastcall *v15)(__int64, __int64, __int64 *); // rbx
  __int64 v16; // rdx
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v19; // rdx
  __int64 v20; // r8
  int v22; // [rsp+20h] [rbp-E0h]
  __int64 v23; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v24; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v25; // [rsp+40h] [rbp-C0h] BYREF
  int v26; // [rsp+48h] [rbp-B8h]
  RetailDemoUtil *v27; // [rsp+50h] [rbp-B0h]
  _BYTE v28[40]; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v29[256]; // [rsp+80h] [rbp-80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4A8h] [rbp+3A8h]

  v27 = a1;
  v26 = 0;
  RetailDemoOriginRegistryLocation = RetailDemoUtil::GetRetailDemoOriginRegistryLocation(a1, (unsigned int)v29, a2, a4);
  if ( RetailDemoOriginRegistryLocation < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2F7,
      (unsigned int)"shellcommon\\shell\\retaildemo\\util\\retaildemoutil.cpp",
      (const char *)(unsigned int)RetailDemoOriginRegistryLocation,
      v22);
  v25 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v25, v6, v7);
  v8 = QuerySourceCreateFromKeyEx(-2147483646, v29, 0, 0);
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2FA,
      (unsigned int)"shellcommon\\shell\\retaildemo\\util\\retaildemoutil.cpp",
      (const char *)(unsigned int)v8,
      (int)&GUID_7bc28ac2_0d9c_4941_bb9a_72becb184fac);
  v24 = 0;
  v11 = v25;
  v12 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v25 + 24LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v24, v9, v10);
  v13 = v12(v11, &v24);
  if ( v13 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2FD,
      (unsigned int)"shellcommon\\shell\\retaildemo\\util\\retaildemoutil.cpp",
      (const char *)(unsigned int)v13,
      (int)&GUID_7bc28ac2_0d9c_4941_bb9a_72becb184fac);
  v23 = 0;
  std::vector<std::wstring>::vector<std::wstring>(a1);
  v26 = 1;
  while ( 1 )
  {
    v14 = v24;
    v15 = *(unsigned int (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v24 + 24LL);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
      &v23,
      0);
    if ( v15(v14, 1, &v23) )
      break;
    v16 = v23;
    v23 = 0;
    std::wstring::wstring((__int64)v28, v16);
    std::vector<std::wstring>::push_back(a1, v28);
    std::wstring::_Tidy_deallocate(v28);
  }
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v23);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v24, v17, v18);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v25, v19, v20);
  return a1;
}

```

## disassembly

```asm
0x18002fa88  mov     [rsp-8+arg_10], rbx
0x18002fa8d  push    rbp
0x18002fa8e  push    rsi
0x18002fa8f  push    rdi
0x18002fa90  lea     rbp, [rsp-390h]
0x18002fa98  sub     rsp, 490h
0x18002fa9f  mov     rax, cs:__security_cookie
0x18002faa6  xor     rax, rsp
0x18002faa9  mov     [rbp+3A0h+var_20], rax
0x18002fab0  mov     rsi, rcx
0x18002fab3  mov     [rsp+4A0h+var_450], rcx
0x18002fab8  mov     [rsp+4A0h+var_458], 0
0x18002fac0  mov     r8, rdx; unsigned __int16 *
0x18002fac3  lea     rdx, [rbp+3A0h+var_420]; unsigned int
0x18002fac7  call    ?GetRetailDemoOriginRegistryLocation@RetailDemoUtil@@YAJKPEAGPEBG@Z; RetailDemoUtil::GetRetailDemoOriginRegistryLocation(ulong,ushort *,ushort const *)
0x18002facc  mov     rcx, [rbp+3A8h]; this
0x18002fad3  test    eax, eax
0x18002fad5  jns     short loc_18002FAEC
0x18002fad7  mov     r9d, eax; char *
0x18002fada  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\retaildemo\\util\\r"...
0x18002fae1  mov     edx, 2F7h; void *
0x18002fae6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002faec  mov     [rsp+4A0h+var_460], 0
0x18002faf5  lea     rcx, [rsp+4A0h+var_460]
0x18002fafa  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002faff  lea     rax, [rsp+4A0h+var_460]
0x18002fb04  mov     [rsp+4A0h+var_478], rax
0x18002fb09  lea     rax, _GUID_7bc28ac2_0d9c_4941_bb9a_72becb184fac
0x18002fb10  mov     qword ptr [rsp+4A0h+var_480], rax; int
0x18002fb15  xor     r9d, r9d
0x18002fb18  xor     r8d, r8d
0x18002fb1b  lea     rdx, [rbp+3A0h+var_420]
0x18002fb1f  mov     rcx, 0FFFFFFFF80000002h
0x18002fb26  call    cs:__imp_QuerySourceCreateFromKeyEx
0x18002fb2c  mov     rcx, [rbp+3A8h]; this
0x18002fb33  test    eax, eax
0x18002fb35  jns     short loc_18002FB4C
0x18002fb37  mov     r9d, eax; char *
0x18002fb3a  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\retaildemo\\util\\r"...
0x18002fb41  mov     edx, 2FAh; void *
0x18002fb46  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002fb4c  mov     [rsp+4A0h+var_468], 0
0x18002fb55  mov     rdi, [rsp+4A0h+var_460]
0x18002fb5a  mov     rax, [rdi]
0x18002fb5d  mov     rbx, [rax+18h]
0x18002fb61  lea     rcx, [rsp+4A0h+var_468]
0x18002fb66  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002fb6b  lea     rdx, [rsp+4A0h+var_468]
0x18002fb70  mov     rcx, rdi
0x18002fb73  mov     rax, rbx
0x18002fb76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fb7b  mov     rcx, [rbp+3A8h]; this
0x18002fb82  test    eax, eax
0x18002fb84  jns     short loc_18002FB9B
0x18002fb86  mov     r9d, eax; char *
0x18002fb89  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\retaildemo\\util\\r"...
0x18002fb90  mov     edx, 2FDh; void *
0x18002fb95  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002fb9b  mov     [rsp+4A0h+var_470], 0
0x18002fba4  mov     rcx, rsi
0x18002fba7  call    ??0?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::vector<std::wstring>(void)
0x18002fbac  mov     [rsp+4A0h+var_458], 1
0x18002fbb4  mov     rdi, [rsp+4A0h+var_468]
0x18002fbb9  mov     rax, [rdi]
0x18002fbbc  mov     rbx, [rax+18h]
0x18002fbc0  xor     edx, edx
0x18002fbc2  lea     rcx, [rsp+4A0h+var_470]
0x18002fbc7  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x18002fbcc  xor     r9d, r9d
0x18002fbcf  lea     r8, [rsp+4A0h+var_470]
0x18002fbd4  lea     edx, [r9+1]
0x18002fbd8  mov     rcx, rdi
0x18002fbdb  mov     rax, rbx
0x18002fbde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fbe3  test    eax, eax
0x18002fbe5  jnz     short loc_18002FC1A
0x18002fbe7  mov     rdx, [rsp+4A0h+var_470]
0x18002fbec  mov     [rsp+4A0h+var_470], 0
0x18002fbf5  lea     rcx, [rsp+4A0h+var_448]
0x18002fbfa  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002fbff  nop
0x18002fc00  lea     rdx, [rsp+4A0h+var_448]
0x18002fc05  mov     rcx, rsi
0x18002fc08  call    ?push_back@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAX$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::vector<std::wstring>::push_back(std::wstring &&)
0x18002fc0d  nop
0x18002fc0e  lea     rcx, [rsp+4A0h+var_448]
0x18002fc13  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002fc18  jmp     short loc_18002FBB4
0x18002fc1a  lea     rcx, [rsp+4A0h+var_470]
0x18002fc1f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18002fc24  nop
0x18002fc25  lea     rcx, [rsp+4A0h+var_468]
0x18002fc2a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002fc2f  nop
0x18002fc30  lea     rcx, [rsp+4A0h+var_460]
0x18002fc35  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002fc3a  mov     rax, rsi
0x18002fc3d  mov     rcx, [rbp+3A0h+var_20]
0x18002fc44  xor     rcx, rsp; StackCookie
0x18002fc47  call    __security_check_cookie
0x18002fc4c  mov     rbx, [rsp+4A0h+arg_10]
0x18002fc54  add     rsp, 490h
0x18002fc5b  pop     rdi
0x18002fc5c  pop     rsi
0x18002fc5d  pop     rbp
0x18002fc5e  retn
```
