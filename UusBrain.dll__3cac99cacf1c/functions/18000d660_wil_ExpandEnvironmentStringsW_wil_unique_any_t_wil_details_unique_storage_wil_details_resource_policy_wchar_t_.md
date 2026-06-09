# wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,256>(wchar_t const *)

- ea: `0x18000d660`
- end: `0x18000d703`
- name: `??$ExpandEnvironmentStringsW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@PEB_W@Z`
- size: `163`
- prototype: `__int64(_QWORD, _QWORD, ...)`
- caller_count: `8`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180009e64`
- `0x18000b024`
- `0x18000cf18`
- `0x180032760`
- `0x1800340c0`
- `0x180038884`
- `0x1800397cc`
- `0x18003a2cc`

## callees

- `0x18000d660`
- `0x180018f44`
- `0x180026cd8`
- `0x1800427d0`

## string_xrefs

- `0x18000d6f1`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\win32_helpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char *wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,256>(
        char *a1,
        __int64 a2,
        ...)
{
  int v3; // eax
  _BYTE v5[8]; // [rsp+30h] [rbp-98h] BYREF
  _QWORD v6[14]; // [rsp+38h] [rbp-90h] BYREF
  __int64 v7; // [rsp+A8h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]

  *(_QWORD *)a1 = 0;
  v7 = a2;
  v6[0] = &wistd::__function::__func<_lambda_e92a0cc36032b557b0292d38c83af5d4_,long (wchar_t *,unsigned __int64,unsigned __int64 *)>::`vftable';
  v6[1] = &v7;
  v6[13] = v6;
  v3 = wil::AdaptFixedSizeToAllocatedResult<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,256>(
         a1,
         (__int64)v5);
  if ( v3 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x240,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\win32_helpers.h",
      (const char *)(unsigned int)v3,
      1);
  return a1;
}

```

## disassembly

```asm
0x18000d660  mov     r11, rsp
0x18000d663  push    rbx
0x18000d664  sub     rsp, 0C0h
0x18000d66b  mov     rax, cs:__security_cookie
0x18000d672  xor     rax, rsp
0x18000d675  mov     [rsp+0C8h+var_18], rax
0x18000d67d  mov     rbx, rcx
0x18000d680  mov     [rsp+0C8h+var_A0], rcx
0x18000d685  mov     [rsp+0C8h+var_A8], 0
0x18000d68d  xor     eax, eax
0x18000d68f  mov     [rcx], rax
0x18000d692  mov     [rsp+0C8h+var_A8], 1; int
0x18000d69a  mov     [r11-20h], rdx
0x18000d69e  lea     rax, ??_7?$__func@V_lambda_e92a0cc36032b557b0292d38c83af5d4_@@$$A6AJPEA_W_KPEA_K@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_e92a0cc36032b557b0292d38c83af5d4_,long (wchar_t *,unsigned __int64,unsigned __int64 *)>::`vftable'
0x18000d6a5  mov     [rsp+0C8h+var_90], rax
0x18000d6aa  lea     rax, [r11-20h]
0x18000d6ae  mov     [rsp+0C8h+var_88], rax
0x18000d6b3  lea     rax, [rsp+0C8h+var_90]
0x18000d6b8  mov     [r11-28h], rax
0x18000d6bc  lea     rdx, [rsp+0C8h+var_98]
0x18000d6c1  call    ??$AdaptFixedSizeToAllocatedResult@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@V?$function@$$A6AJPEA_W_KPEA_K@Z@wistd@@@Z; wil::AdaptFixedSizeToAllocatedResult<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,256>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> &,wistd::function<long (wchar_t *,unsigned __int64,unsigned __int64 *)>)
0x18000d6c6  test    eax, eax
0x18000d6c8  js      short loc_18000D6E6
0x18000d6ca  mov     rax, rbx
0x18000d6cd  mov     rcx, [rsp+0C8h+var_18]
0x18000d6d5  xor     rcx, rsp; StackCookie
0x18000d6d8  call    __security_check_cookie
0x18000d6dd  add     rsp, 0C0h
0x18000d6e4  pop     rbx
0x18000d6e5  retn
0x18000d6e6  mov     rcx, [rsp+0C8h]; this
0x18000d6ee  mov     r9d, eax; char *
0x18000d6f1  lea     r8, aCW1SPackagesMi; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x18000d6f8  mov     edx, 240h; void *
0x18000d6fd  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
