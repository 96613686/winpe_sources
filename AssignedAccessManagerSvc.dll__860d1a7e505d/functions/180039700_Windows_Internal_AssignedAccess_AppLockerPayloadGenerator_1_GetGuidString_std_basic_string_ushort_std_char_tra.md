# Windows::Internal::AssignedAccess::AppLockerPayloadGenerator<1>::GetGuidString(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x180039700`
- end: `0x180039807`
- name: `?GetGuidString@?$AppLockerPayloadGenerator@$00@AssignedAccess@Internal@Windows@@AEAAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `263`
- prototype: ``
- caller_count: `4`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180038dd8`
- `0x180038f44`
- `0x180039088`
- `0x1800391d4`

## callees

- `0x180006640`
- `0x18000b6b4`
- `0x180010c98`
- `0x18002074c`
- `0x1800221e0`
- `0x180022d00`
- `0x180022e34`
- `0x180037454`
- `0x180039700`
- `0x18003bd0c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180039736`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180039736`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180039768`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180039768`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Internal::AssignedAccess::AppLockerPayloadGenerator<1>::GetGuidString(
        __int64 a1,
        __int64 a2)
{
  HRESULT v3; // eax
  HRESULT v4; // ebx
  unsigned __int64 v5; // r9
  __int64 v6; // rdx
  unsigned __int64 v7; // rax
  __int64 v8; // rcx
  __int64 v9; // rax
  __int64 v11; // [rsp+20h] [rbp-40h] BYREF
  __int64 *v12; // [rsp+28h] [rbp-38h] BYREF
  LPOLESTR lpsz; // [rsp+30h] [rbp-30h] BYREF
  char v14; // [rsp+38h] [rbp-28h]
  GUID pguid; // [rsp+48h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+8h]

  pguid = 0;
  v11 = 0;
  v3 = CoCreateGuid(&pguid);
  v4 = v3;
  if ( v3 >= 0 )
  {
    v12 = &v11;
    lpsz = 0;
    v14 = 1;
    v4 = StringFromCLSID(&pguid, &lpsz);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&v12);
    if ( v4 >= 0 )
    {
      v7 = std::_WChar_traits<unsigned short>::length(v11);
      std::wstring::_Assign<unsigned short>(a2, v8, v7);
      v9 = std::wstring::substr(a2, &v12, 1, *(_QWORD *)(a2 + 16) - 2LL);
      std::wstring::operator=(a2, v9);
      std::wstring::_Tidy_deallocate(&v12);
      v4 = 0;
      goto LABEL_7;
    }
    v5 = (unsigned int)v4;
    v6 = 69;
  }
  else
  {
    v5 = (unsigned int)v3;
    v6 = 68;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v6,
    (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\libsrv\\applockerpayloadgenerator.h",
    (const char *)v5,
    v11);
LABEL_7:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v11);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180039700  mov     [rsp-8+arg_0], rbx
0x180039705  mov     [rsp-8+arg_10], rdi
0x18003970a  push    rbp
0x18003970b  mov     rbp, rsp
0x18003970e  sub     rsp, 60h
0x180039712  mov     rax, cs:__security_cookie
0x180039719  xor     rax, rsp
0x18003971c  mov     [rbp+var_8], rax
0x180039720  mov     rdi, rdx
0x180039723  xorps   xmm0, xmm0
0x180039726  movups  xmmword ptr [rbp+pguid.Data1], xmm0
0x18003972a  mov     [rbp+var_40], 0
0x180039732  lea     rcx, [rbp+pguid]; pguid
0x180039736  call    cs:__imp_CoCreateGuid
0x18003973c  mov     ebx, eax
0x18003973e  test    eax, eax
0x180039740  jns     short loc_18003974C
0x180039742  mov     r9d, eax
0x180039745  mov     edx, 44h ; 'D'
0x18003974a  jmp     short loc_180039785
0x18003974c  lea     rax, [rbp+var_40]
0x180039750  mov     [rbp+var_38], rax
0x180039754  mov     [rbp+lpsz], 0
0x18003975c  mov     [rbp+var_28], 1
0x180039760  lea     rdx, [rbp+lpsz]; lplpsz
0x180039764  lea     rcx, [rbp+pguid]; rclsid
0x180039768  call    cs:__imp_StringFromCLSID
0x18003976e  mov     ebx, eax
0x180039770  lea     rcx, [rbp+var_38]
0x180039774  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x180039779  test    ebx, ebx
0x18003977b  jns     short loc_180039797
0x18003977d  mov     r9d, ebx; char *
0x180039780  mov     edx, 45h ; 'E'; void *
0x180039785  lea     r8, aOnecoreuapBase_38; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x18003978c  mov     rcx, [rbp+8]; this
0x180039790  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039795  jmp     short loc_1800397DE
0x180039797  mov     rcx, [rbp+var_40]
0x18003979b  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x1800397a0  mov     r8, rax
0x1800397a3  mov     rdx, rcx
0x1800397a6  mov     rcx, rdi
0x1800397a9  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800397ae  mov     r9, [rdi+10h]
0x1800397b2  sub     r9, 2
0x1800397b6  mov     r8d, 1
0x1800397bc  lea     rdx, [rbp+var_38]
0x1800397c0  mov     rcx, rdi
0x1800397c3  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x1800397c8  mov     rdx, rax
0x1800397cb  mov     rcx, rdi
0x1800397ce  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800397d3  lea     rcx, [rbp+var_38]
0x1800397d7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800397dc  xor     ebx, ebx
0x1800397de  lea     rcx, [rbp+var_40]
0x1800397e2  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800397e7  mov     eax, ebx
0x1800397e9  mov     rcx, [rbp+var_8]
0x1800397ed  xor     rcx, rsp; StackCookie
0x1800397f0  call    __security_check_cookie
0x1800397f5  lea     r11, [rsp+60h+var_s0]
0x1800397fa  mov     rbx, [r11+10h]
0x1800397fe  mov     rdi, [r11+20h]
0x180039802  mov     rsp, r11
0x180039805  pop     rbp
0x180039806  retn
```
