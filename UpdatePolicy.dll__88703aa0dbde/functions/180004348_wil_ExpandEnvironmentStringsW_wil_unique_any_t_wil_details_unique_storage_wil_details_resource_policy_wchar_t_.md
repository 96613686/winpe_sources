# wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,256>(wchar_t const *)

- ea: `0x180004348`
- end: `0x1800043f2`
- name: `??$ExpandEnvironmentStringsW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@PEB_W@Z`
- size: `170`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180002db0`
- `0x180002f78`

## callees

- `0x180004348`
- `0x180004ea4`
- `0x180006540`
- `0x18000ed40`

## string_xrefs

- `0x1800043e0`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\win32_helpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char *__fastcall wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,256>(
        char *a1)
{
  int v2; // eax
  _BYTE v4[8]; // [rsp+30h] [rbp-98h] BYREF
  _QWORD v5[14]; // [rsp+38h] [rbp-90h] BYREF
  const wchar_t *v6; // [rsp+A8h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]

  *(_QWORD *)a1 = 0;
  v6 = L"%SystemRoot%\\uus";
  v5[0] = &wistd::__function::__func<_lambda_e92a0cc36032b557b0292d38c83af5d4_,long (wchar_t *,unsigned __int64,unsigned __int64 *)>::`vftable';
  v5[1] = &v6;
  v5[13] = v5;
  v2 = wil::AdaptFixedSizeToAllocatedResult<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,256>(
         a1,
         (__int64)v4);
  if ( v2 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x240,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\win32_helpers.h",
      (const char *)(unsigned int)v2,
      1);
  return a1;
}

```

## disassembly

```asm
0x180004348  mov     r11, rsp
0x18000434b  push    rbx
0x18000434c  sub     rsp, 0C0h
0x180004353  mov     rax, cs:__security_cookie
0x18000435a  xor     rax, rsp
0x18000435d  mov     [rsp+0C8h+var_18], rax
0x180004365  mov     rbx, rcx
0x180004368  mov     [rsp+0C8h+var_A0], rcx
0x18000436d  mov     [rsp+0C8h+var_A8], 0
0x180004375  xor     eax, eax
0x180004377  mov     [rcx], rax
0x18000437a  mov     [rsp+0C8h+var_A8], 1; int
0x180004382  lea     rax, aSystemrootUus; "%SystemRoot%\\uus"
0x180004389  mov     [r11-20h], rax
0x18000438d  lea     rax, ??_7?$__func@V_lambda_e92a0cc36032b557b0292d38c83af5d4_@@$$A6AJPEA_W_KPEA_K@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_e92a0cc36032b557b0292d38c83af5d4_,long (wchar_t *,unsigned __int64,unsigned __int64 *)>::`vftable'
0x180004394  mov     [rsp+0C8h+var_90], rax
0x180004399  lea     rax, [r11-20h]
0x18000439d  mov     [rsp+0C8h+var_88], rax
0x1800043a2  lea     rax, [rsp+0C8h+var_90]
0x1800043a7  mov     [r11-28h], rax
0x1800043ab  lea     rdx, [rsp+0C8h+var_98]
0x1800043b0  call    ??$AdaptFixedSizeToAllocatedResult@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@V?$function@$$A6AJPEA_W_KPEA_K@Z@wistd@@@Z; wil::AdaptFixedSizeToAllocatedResult<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,256>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> &,wistd::function<long (wchar_t *,unsigned __int64,unsigned __int64 *)>)
0x1800043b5  test    eax, eax
0x1800043b7  js      short loc_1800043D5
0x1800043b9  mov     rax, rbx
0x1800043bc  mov     rcx, [rsp+0C8h+var_18]
0x1800043c4  xor     rcx, rsp; StackCookie
0x1800043c7  call    __security_check_cookie
0x1800043cc  add     rsp, 0C0h
0x1800043d3  pop     rbx
0x1800043d4  retn
0x1800043d5  mov     rcx, [rsp+0C8h]; this
0x1800043dd  mov     r9d, eax; char *
0x1800043e0  lea     r8, aCW1SPackagesMi; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x1800043e7  mov     edx, 240h; void *
0x1800043ec  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
