# ContainerManagerApi::CreateSecurityDescriptor(void)

- ea: `0x180024370`
- end: `0x18002449f`
- name: `?CreateSecurityDescriptor@ContainerManagerApi@@UEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@XZ`
- size: `303`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180024370`
- `0x1800245f0`
- `0x180024710`
- `0x180024794`
- `0x180024820`
- `0x1800249ec`
- `0x18002a514`
- `0x180031540`
- `0x180043680`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18002443f`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18002443f`

## string_xrefs

- `0x180024406`: `onecore\windows\accessibletech\common\containermanagerapi.cpp`
- `0x180024450`: `onecore\windows\accessibletech\common\containermanagerapi.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
WCHAR *__fastcall ContainerManagerApi::CreateSecurityDescriptor(__int64 a1, WCHAR *a2)
{
  int v4; // eax
  const char *v5; // r9
  int v7; // [rsp+20h] [rbp-E0h]
  LPWSTR v8; // [rsp+38h] [rbp-C8h] BYREF
  LPWSTR StringSid[2]; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v10; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR StringSecurityDescriptor[264]; // [rsp+60h] [rbp-A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  StringSid[1] = a2;
  BasicUtils::GetUserSidString(StringSid);
  v10 = *(_OWORD *)(a1 + 8);
  BasicUtils::GetMachineSidString(&v8, (DWORD *)&v10);
  v7 = (int)v8;
  v4 = StringCchPrintfW(StringSecurityDescriptor, 0x104u, L"D:(A;;FRFWGA;;;%ws)(A;;FRFWGA;;;%ws)", StringSid[0]);
  if ( v4 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x101,
      (unsigned int)"onecore\\windows\\accessibletech\\common\\containermanagerapi.cpp",
      (const char *)(unsigned int)v4,
      v7);
  *(_QWORD *)a2 = 0;
  wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
    a2,
    0);
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
          StringSecurityDescriptor,
          1u,
          (PSECURITY_DESCRIPTOR *)a2,
          0) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x105,
      (unsigned int)"onecore\\windows\\accessibletech\\common\\containermanagerapi.cpp",
      v5);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v8);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(StringSid);
  return a2;
}

```

## disassembly

```asm
0x180024370  mov     [rsp-8+arg_0], rbx
0x180024375  mov     [rsp-8+arg_10], rdi
0x18002437a  push    rbp
0x18002437b  lea     rbp, [rsp-180h]
0x180024383  sub     rsp, 280h
0x18002438a  mov     rax, cs:__security_cookie
0x180024391  xor     rax, rsp
0x180024394  mov     [rbp+180h+var_10], rax
0x18002439b  mov     rdi, rdx
0x18002439e  mov     rbx, rcx
0x1800243a1  mov     [rsp+280h+var_238], rdx
0x1800243a6  mov     [rsp+280h+var_250], 0
0x1800243ae  lea     rcx, [rsp+280h+StringSid]; StringSid
0x1800243b3  call    ?GetUserSidString@BasicUtils@@SA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@XZ; BasicUtils::GetUserSidString(void)
0x1800243b8  nop
0x1800243b9  movups  xmm0, xmmword ptr [rbx+8]
0x1800243bd  movdqu  [rsp+280h+var_230], xmm0
0x1800243c3  lea     rdx, [rsp+280h+var_230]
0x1800243c8  lea     rcx, [rsp+280h+var_248]; StringSid
0x1800243cd  call    ?GetMachineSidString@BasicUtils@@SA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@AEBU_GUID@@@Z; BasicUtils::GetMachineSidString(_GUID const &)
0x1800243d2  nop
0x1800243d3  mov     rax, [rsp+280h+var_248]
0x1800243d8  mov     qword ptr [rsp+280h+var_260], rax; int
0x1800243dd  mov     r9, [rsp+280h+StringSid]
0x1800243e2  lea     r8, aDAFrfwgaWsAFrf_1; "D:(A;;FRFWGA;;;%ws)(A;;FRFWGA;;;%ws)"
0x1800243e9  mov     edx, 104h; unsigned __int64
0x1800243ee  lea     rcx, [rsp+280h+StringSecurityDescriptor]; unsigned __int16 *
0x1800243f3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800243f8  mov     rcx, [rbp+188h]; this
0x1800243ff  test    eax, eax
0x180024401  jns     short loc_180024418
0x180024403  mov     r9d, eax; char *
0x180024406  lea     r8, aOnecoreWindows_19; "onecore\\windows\\accessibletech\\commo"...
0x18002440d  mov     edx, 101h; void *
0x180024412  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180024418  mov     qword ptr [rdi], 0
0x18002441f  mov     ebx, 1
0x180024424  mov     [rsp+280h+var_250], ebx
0x180024428  xor     edx, edx
0x18002442a  mov     rcx, rdi
0x18002442d  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x180024432  xor     r9d, r9d; SecurityDescriptorSize
0x180024435  mov     r8, rdi; SecurityDescriptor
0x180024438  mov     edx, ebx; StringSDRevision
0x18002443a  lea     rcx, [rsp+280h+StringSecurityDescriptor]; StringSecurityDescriptor
0x18002443f  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180024445  mov     rcx, [rbp+188h]; this
0x18002444c  test    eax, eax
0x18002444e  jnz     short loc_180024462
0x180024450  lea     r8, aOnecoreWindows_19; "onecore\\windows\\accessibletech\\commo"...
0x180024457  mov     edx, 105h; void *
0x18002445c  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180024462  lea     rcx, [rsp+280h+var_248]
0x180024467  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002446c  nop
0x18002446d  lea     rcx, [rsp+280h+StringSid]
0x180024472  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180024477  mov     rax, rdi
0x18002447a  mov     rcx, [rbp+180h+var_10]
0x180024481  xor     rcx, rsp; StackCookie
0x180024484  call    __security_check_cookie
0x180024489  lea     r11, [rsp+280h+var_s0]
0x180024491  mov     rbx, [r11+10h]
0x180024495  mov     rdi, [r11+20h]
0x180024499  mov     rsp, r11
0x18002449c  pop     rbp
0x18002449d  retn
```
