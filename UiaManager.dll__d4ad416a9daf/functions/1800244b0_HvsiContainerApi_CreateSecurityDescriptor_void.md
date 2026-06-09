# HvsiContainerApi::CreateSecurityDescriptor(void)

- ea: `0x1800244b0`
- end: `0x1800245dd`
- name: `?CreateSecurityDescriptor@HvsiContainerApi@@UEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@XZ`
- size: `301`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x1800244b0`
- `0x1800245f0`
- `0x180024710`
- `0x180024794`
- `0x180024820`
- `0x1800249ec`
- `0x18002a514`
- `0x180031540`
- `0x180043680`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18002457f`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18002457f`

## string_xrefs

- `0x180024546`: `onecore\windows\accessibletech\common\hvsicontainerapi.cpp`
- `0x180024590`: `onecore\windows\accessibletech\common\hvsicontainerapi.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
WCHAR *__fastcall HvsiContainerApi::CreateSecurityDescriptor(__int64 a1, WCHAR *a2)
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
      (void *)0x53,
      (unsigned int)"onecore\\windows\\accessibletech\\common\\hvsicontainerapi.cpp",
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
      (void *)0x57,
      (unsigned int)"onecore\\windows\\accessibletech\\common\\hvsicontainerapi.cpp",
      v5);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v8);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(StringSid);
  return a2;
}

```

## disassembly

```asm
0x1800244b0  mov     [rsp-8+arg_0], rbx
0x1800244b5  mov     [rsp-8+arg_10], rdi
0x1800244ba  push    rbp
0x1800244bb  lea     rbp, [rsp-180h]
0x1800244c3  sub     rsp, 280h
0x1800244ca  mov     rax, cs:__security_cookie
0x1800244d1  xor     rax, rsp
0x1800244d4  mov     [rbp+180h+var_10], rax
0x1800244db  mov     rdi, rdx
0x1800244de  mov     rbx, rcx
0x1800244e1  mov     [rsp+280h+var_238], rdx
0x1800244e6  mov     [rsp+280h+var_250], 0
0x1800244ee  lea     rcx, [rsp+280h+StringSid]; StringSid
0x1800244f3  call    ?GetUserSidString@BasicUtils@@SA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@XZ; BasicUtils::GetUserSidString(void)
0x1800244f8  nop
0x1800244f9  movups  xmm0, xmmword ptr [rbx+8]
0x1800244fd  movdqu  [rsp+280h+var_230], xmm0
0x180024503  lea     rdx, [rsp+280h+var_230]
0x180024508  lea     rcx, [rsp+280h+var_248]; StringSid
0x18002450d  call    ?GetMachineSidString@BasicUtils@@SA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@AEBU_GUID@@@Z; BasicUtils::GetMachineSidString(_GUID const &)
0x180024512  nop
0x180024513  mov     rax, [rsp+280h+var_248]
0x180024518  mov     qword ptr [rsp+280h+var_260], rax; int
0x18002451d  mov     r9, [rsp+280h+StringSid]
0x180024522  lea     r8, aDAFrfwgaWsAFrf_1; "D:(A;;FRFWGA;;;%ws)(A;;FRFWGA;;;%ws)"
0x180024529  mov     edx, 104h; unsigned __int64
0x18002452e  lea     rcx, [rsp+280h+StringSecurityDescriptor]; unsigned __int16 *
0x180024533  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180024538  mov     rcx, [rbp+188h]; this
0x18002453f  test    eax, eax
0x180024541  jns     short loc_180024558
0x180024543  mov     r9d, eax; char *
0x180024546  lea     r8, aOnecoreWindows_23; "onecore\\windows\\accessibletech\\commo"...
0x18002454d  mov     edx, 53h ; 'S'; void *
0x180024552  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180024558  mov     qword ptr [rdi], 0
0x18002455f  mov     ebx, 1
0x180024564  mov     [rsp+280h+var_250], ebx
0x180024568  xor     edx, edx
0x18002456a  mov     rcx, rdi
0x18002456d  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x180024572  xor     r9d, r9d; SecurityDescriptorSize
0x180024575  mov     r8, rdi; SecurityDescriptor
0x180024578  mov     edx, ebx; StringSDRevision
0x18002457a  lea     rcx, [rsp+280h+StringSecurityDescriptor]; StringSecurityDescriptor
0x18002457f  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180024585  mov     rcx, [rbp+188h]; this
0x18002458c  test    eax, eax
0x18002458e  jnz     short loc_1800245A0
0x180024590  lea     r8, aOnecoreWindows_23; "onecore\\windows\\accessibletech\\commo"...
0x180024597  lea     edx, [rbx+56h]; void *
0x18002459a  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800245a0  lea     rcx, [rsp+280h+var_248]
0x1800245a5  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800245aa  nop
0x1800245ab  lea     rcx, [rsp+280h+StringSid]
0x1800245b0  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800245b5  mov     rax, rdi
0x1800245b8  mov     rcx, [rbp+180h+var_10]
0x1800245bf  xor     rcx, rsp; StackCookie
0x1800245c2  call    __security_check_cookie
0x1800245c7  lea     r11, [rsp+280h+var_s0]
0x1800245cf  mov     rbx, [r11+10h]
0x1800245d3  mov     rdi, [r11+20h]
0x1800245d7  mov     rsp, r11
0x1800245da  pop     rbp
0x1800245db  retn
```
