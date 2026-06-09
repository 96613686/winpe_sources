# CXPolicy::GetClientRequestId

- ea: `0x180012774`
- end: `0x18001289d`
- name: `CXPolicy::GetClientRequestId`
- size: `297`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800d3500`
- `0x1800d3bd0`

## callees

- `0x180010c8c`
- `0x180012774`
- `0x1800128a4`
- `0x1800128e8`
- `0x1800135ec`
- `0x180013b70`
- `0x180013c14`
- `0x1800145d8`
- `0x18001a540`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800127c8`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800127c8`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180012800`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180012800`

## string_xrefs

- `0x1800127d9`: `onecore\ds\security\cfl\policy\lib\allowlistimpl.cpp`
- `0x180012811`: `onecore\ds\security\cfl\policy\lib\allowlistimpl.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CXPolicy::GetClientRequestId(__int64 a1, __int64 a2, __int64 a3)
{
  HRESULT v4; // eax
  HRESULT v5; // eax
  __int64 v6; // r8
  __int64 v7; // rdx
  LPOLESTR v8; // rdx
  const unsigned __int16 *v9; // rax
  const unsigned __int16 *v10; // rdx
  Reg *v11; // rcx
  LPOLESTR lpsz; // [rsp+20h] [rbp-30h] BYREF
  int v14; // [rsp+28h] [rbp-28h]
  __int64 v15; // [rsp+30h] [rbp-20h]
  GUID pguid; // [rsp+38h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+8h]

  v15 = a1;
  Reg::GetStringValue(a1, a2, a3, L"ClientRequestId");
  v14 = 1;
  if ( !*(_QWORD *)(a1 + 16) )
  {
    pguid = 0;
    v4 = CoCreateGuid(&pguid);
    if ( v4 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x2A,
        (unsigned int)"onecore\\ds\\security\\cfl\\policy\\lib\\allowlistimpl.cpp",
        (const char *)(unsigned int)v4,
        (int)lpsz);
    lpsz = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &lpsz,
      0);
    v5 = StringFromCLSID(&pguid, &lpsz);
    if ( v5 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x2C,
        (unsigned int)"onecore\\ds\\security\\cfl\\policy\\lib\\allowlistimpl.cpp",
        (const char *)(unsigned int)v5,
        (int)lpsz);
    v6 = -1;
    v7 = -1;
    do
      ++v7;
    while ( lpsz[v7] );
    lpsz[v7 - 1] = 0;
    v8 = lpsz + 1;
    do
      ++v6;
    while ( v8[v6] );
    std::wstring::_Assign<unsigned short>(a1, v8, (2 * v6) >> 1);
    v9 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1);
    Reg::SetStringValue(v11, v10, L"ClientRequestId", v9, lpsz);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpsz);
  }
  return a1;
}

```

## disassembly

```asm
0x180012774  mov     [rsp-8+arg_8], rbx
0x180012779  mov     [rsp-8+arg_10], rdi
0x18001277e  push    rbp
0x18001277f  mov     rbp, rsp
0x180012782  sub     rsp, 50h
0x180012786  mov     rax, cs:__security_cookie
0x18001278d  xor     rax, rsp
0x180012790  mov     [rbp+var_8], rax
0x180012794  mov     rbx, rcx
0x180012797  mov     [rbp+var_20], rcx
0x18001279b  xor     edi, edi
0x18001279d  mov     [rbp+var_28], edi
0x1800127a0  lea     r9, aClientrequesti; "ClientRequestId"
0x1800127a7  call    ?GetStringValue@Reg@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG00@Z; Reg::GetStringValue(ushort const *,ushort const *,ushort const *)
0x1800127ac  mov     [rbp+var_28], 1
0x1800127b3  cmp     [rbx+10h], rdi
0x1800127b7  jnz     loc_18001287D
0x1800127bd  xorps   xmm0, xmm0
0x1800127c0  movups  xmmword ptr [rbp+pguid.Data1], xmm0
0x1800127c4  lea     rcx, [rbp+pguid]; pguid
0x1800127c8  call    cs:__imp_CoCreateGuid
0x1800127ce  mov     rcx, [rbp+8]; this
0x1800127d2  test    eax, eax
0x1800127d4  jns     short loc_1800127E9
0x1800127d6  mov     r9d, eax; char *
0x1800127d9  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cfl\\policy\\lib"...
0x1800127e0  lea     edx, [rdi+2Ah]; void *
0x1800127e3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800127e9  mov     [rbp+lpsz], rdi
0x1800127ed  xor     edx, edx
0x1800127ef  lea     rcx, [rbp+lpsz]
0x1800127f3  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800127f8  lea     rdx, [rbp+lpsz]; lplpsz
0x1800127fc  lea     rcx, [rbp+pguid]; rclsid
0x180012800  call    cs:__imp_StringFromCLSID
0x180012806  mov     rcx, [rbp+8]; this
0x18001280a  test    eax, eax
0x18001280c  jns     short loc_180012823
0x18001280e  mov     r9d, eax; char *
0x180012811  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cfl\\policy\\lib"...
0x180012818  mov     edx, 2Ch ; ','; void *
0x18001281d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180012823  mov     rax, [rbp+lpsz]
0x180012827  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001282b  mov     rdx, r8
0x18001282e  inc     rdx
0x180012831  cmp     [rax+rdx*2], di
0x180012835  jnz     short loc_18001282E
0x180012837  mov     [rax+rdx*2-2], di
0x18001283c  mov     rdx, [rbp+lpsz]
0x180012840  add     rdx, 2
0x180012844  inc     r8
0x180012847  cmp     [rdx+r8*2], di
0x18001284c  jnz     short loc_180012844
0x18001284e  add     r8, r8
0x180012851  sar     r8, 1
0x180012854  mov     rcx, rbx
0x180012857  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18001285c  mov     rcx, rbx
0x18001285f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180012864  mov     r9, rax; unsigned __int16 *
0x180012867  lea     r8, aClientrequesti; "ClientRequestId"
0x18001286e  call    ?SetStringValue@Reg@@YAXPEBG000@Z; Reg::SetStringValue(ushort const *,ushort const *,ushort const *,ushort const *)
0x180012873  nop
0x180012874  lea     rcx, [rbp+lpsz]
0x180012878  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001287d  mov     rax, rbx
0x180012880  mov     rcx, [rbp+var_8]
0x180012884  xor     rcx, rsp; StackCookie
0x180012887  call    __security_check_cookie
0x18001288c  mov     rbx, [rsp+50h+arg_8]
0x180012891  mov     rdi, [rsp+50h+arg_10]
0x180012896  add     rsp, 50h
0x18001289a  pop     rbp
0x18001289b  retn
```
