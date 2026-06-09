# _lambda_c2c25eefbfbc7b986f8ea0b2addf2ae2_::operator()

- ea: `0x18002c900`
- end: `0x18002c9c7`
- name: `_lambda_c2c25eefbfbc7b986f8ea0b2addf2ae2_::operator()`
- size: `199`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18002cc70`

## callees

- `0x180008bbc`
- `0x18001094c`
- `0x180010a60`
- `0x18002c900`
- `0x180050010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002c942`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002c942`

## string_xrefs

- `0x18002c954`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\backupthemetask.cpp`
- `0x18002c99b`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\backupthemetask.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall lambda_c2c25eefbfbc7b986f8ea0b2addf2ae2_::operator()(__int64 *a1, __int64 a2, __int64 a3)
{
  HRESULT v4; // eax
  LPVOID v5; // rsi
  __int64 (__fastcall *v6)(LPVOID, _QWORD, __int64); // rdi
  __int64 v7; // rbx
  int v8; // eax
  __int64 v9; // rdx
  __int64 v10; // r8
  int ppv; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  LPVOID v14; // [rsp+48h] [rbp+10h] BYREF

  v14 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v14, a2, a3);
  v4 = CoCreateInstance(&CLSID_DesktopWallpaper, 0, 4u, &GUID_b92b56a9_8b55_4e14_9a89_0199bbb6f93b, &v14);
  if ( v4 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x31,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\backupthemetask.cpp",
      (const char *)(unsigned int)v4,
      ppv);
  v5 = v14;
  v6 = *(__int64 (__fastcall **)(LPVOID, _QWORD, __int64))(*(_QWORD *)v14 + 32LL);
  v7 = *a1;
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
    v7,
    0);
  v8 = v6(v5, 0, v7);
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x32,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\backupthemetask.cpp",
      (const char *)(unsigned int)v8,
      ppv);
  return Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v14, v9, v10);
}

```

## disassembly

```asm
0x18002c900  mov     rax, rsp
0x18002c903  mov     [rax+8], rbx
0x18002c907  mov     [rax+18h], rsi
0x18002c90b  push    rdi
0x18002c90c  sub     rsp, 30h
0x18002c910  mov     rbx, rcx
0x18002c913  mov     qword ptr [rax+10h], 0
0x18002c91b  lea     rcx, [rax+10h]
0x18002c91f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002c924  lea     rax, [rsp+38h+arg_8]
0x18002c929  mov     qword ptr [rsp+38h+ppv], rax; int
0x18002c92e  lea     r9, _GUID_b92b56a9_8b55_4e14_9a89_0199bbb6f93b; riid
0x18002c935  xor     edx, edx; pUnkOuter
0x18002c937  lea     r8d, [rdx+4]; dwClsContext
0x18002c93b  lea     rcx, CLSID_DesktopWallpaper; rclsid
0x18002c942  call    cs:__imp_CoCreateInstance
0x18002c948  mov     rcx, [rsp+38h]; this
0x18002c94d  test    eax, eax
0x18002c94f  jns     short loc_18002C966
0x18002c951  mov     r9d, eax; char *
0x18002c954  lea     r8, aPcshellShellRe_4; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18002c95b  mov     edx, 31h ; '1'; void *
0x18002c960  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002c966  mov     rsi, [rsp+38h+arg_8]
0x18002c96b  mov     rax, [rsi]
0x18002c96e  mov     rdi, [rax+20h]
0x18002c972  mov     rbx, [rbx]
0x18002c975  xor     edx, edx
0x18002c977  mov     rcx, rbx
0x18002c97a  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x18002c97f  mov     r8, rbx
0x18002c982  xor     edx, edx
0x18002c984  mov     rcx, rsi
0x18002c987  mov     rax, rdi
0x18002c98a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c98f  mov     rcx, [rsp+38h]; this
0x18002c994  test    eax, eax
0x18002c996  jns     short loc_18002C9AD
0x18002c998  mov     r9d, eax; char *
0x18002c99b  lea     r8, aPcshellShellRe_4; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18002c9a2  mov     edx, 32h ; '2'; void *
0x18002c9a7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002c9ad  lea     rcx, [rsp+38h+arg_8]
0x18002c9b2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002c9b7  mov     rbx, [rsp+38h+arg_0]
0x18002c9bc  mov     rsi, [rsp+38h+arg_10]
0x18002c9c1  add     rsp, 30h
0x18002c9c5  pop     rdi
0x18002c9c6  retn
```
