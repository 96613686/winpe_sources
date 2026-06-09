# Windows::Internal::AssignedAccess::XmlSerializer::VisitGuidValue(ushort,_GUID)

- ea: `0x18006c4e0`
- end: `0x18006c5a9`
- name: `?VisitGuidValue@XmlSerializer@AssignedAccess@Internal@Windows@@UEAAJGU_GUID@@@Z`
- size: `201`
- prototype: `int(Windows::Internal::AssignedAccess::XmlSerializer *__hidden this, unsigned __int16, struct _GUID *__struct_ptr)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x18000b6b4`
- `0x180022d00`
- `0x180037454`
- `0x18006aa3c`
- `0x18006acfc`
- `0x18006c4e0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18006c518`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18006c518`
- `OLEAUT32!__imp_VariantClear` at `0x18006c566`
- `OLEAUT32!__imp_VariantClear` at `0x18006c566`

## string_xrefs

- `0x18006c575`: `onecoreuap\base\embedded\sys\lockdown\mdmalert\lib\xmlserializer.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::Internal::AssignedAccess::XmlSerializer::VisitGuidValue(
        Windows::Internal::AssignedAccess::XmlSerializer *this,
        __int64 a2,
        struct _GUID *a3)
{
  HRESULT v4; // ebx
  __int64 v5; // rdx
  unsigned __int16 *v7[2]; // [rsp+20h] [rbp-50h] BYREF
  struct tagVARIANT lpsz; // [rsp+30h] [rbp-40h] BYREF
  VARIANTARG pvarg; // [rsp+50h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+8h]

  v7[0] = 0;
  *(_QWORD *)&lpsz.vt = v7;
  lpsz.llVal = 0;
  *((_BYTE *)&lpsz.decVal + 16) = 1;
  v4 = StringFromCLSID(a3, &lpsz.bstrVal);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&lpsz);
  if ( v4 >= 0 )
  {
    lpsz = *(struct tagVARIANT *)_variant_t::_variant_t((_variant_t *)&pvarg, v7[0]);
    v4 = Windows::Internal::AssignedAccess::XmlSerializer::AddNonStructValue(
           (Windows::Internal::AssignedAccess::XmlSerializer *)((char *)this - 8),
           &lpsz);
    VariantClear(&pvarg);
    if ( v4 >= 0 )
    {
      v4 = 0;
      goto LABEL_7;
    }
    v5 = 122;
  }
  else
  {
    v5 = 121;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v5,
    (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\mdmalert\\lib\\xmlserializer.cpp",
    (const char *)(unsigned int)v4,
    (int)v7[0]);
LABEL_7:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v7);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18006c4e0  mov     [rsp-8+arg_8], rbx
0x18006c4e5  mov     [rsp-8+arg_18], rdi
0x18006c4ea  push    rbp
0x18006c4eb  mov     rbp, rsp
0x18006c4ee  sub     rsp, 70h
0x18006c4f2  mov     rdi, rcx
0x18006c4f5  mov     [rbp+var_50], 0
0x18006c4fd  lea     rax, [rbp+var_50]
0x18006c501  mov     [rbp+lpsz], rax
0x18006c505  mov     [rbp+lpsz+8], 0
0x18006c50d  mov     byte ptr [rbp+var_30], 1
0x18006c511  lea     rdx, [rbp+lpsz+8]; lplpsz
0x18006c515  mov     rcx, r8; rclsid
0x18006c518  call    cs:__imp_StringFromCLSID
0x18006c51e  mov     ebx, eax
0x18006c520  lea     rcx, [rbp+lpsz]
0x18006c524  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x18006c529  test    ebx, ebx
0x18006c52b  jns     short loc_18006C534
0x18006c52d  mov     edx, 79h ; 'y'
0x18006c532  jmp     short loc_18006C575
0x18006c534  mov     rdx, [rbp+var_50]; unsigned __int16 *
0x18006c538  lea     rcx, [rbp+pvarg]; this
0x18006c53c  call    ??0_variant_t@@QEAA@PEBG@Z; _variant_t::_variant_t(ushort const *)
0x18006c541  nop
0x18006c542  movups  xmm0, xmmword ptr [rax]
0x18006c545  movaps  xmmword ptr [rbp+lpsz], xmm0
0x18006c549  movsd   xmm1, qword ptr [rax+10h]
0x18006c54e  movsd   [rbp+var_30], xmm1
0x18006c553  lea     rcx, [rdi-8]; this
0x18006c557  lea     rdx, [rbp+lpsz]; struct tagVARIANT
0x18006c55b  call    ?AddNonStructValue@XmlSerializer@AssignedAccess@Internal@Windows@@AEAAJUtagVARIANT@@@Z; Windows::Internal::AssignedAccess::XmlSerializer::AddNonStructValue(tagVARIANT)
0x18006c560  mov     ebx, eax
0x18006c562  lea     rcx, [rbp+pvarg]; pvarg
0x18006c566  call    cs:__imp_VariantClear
0x18006c56c  test    ebx, ebx
0x18006c56e  jns     short loc_18006C58A
0x18006c570  mov     edx, 7Ah ; 'z'; void *
0x18006c575  lea     r8, aOnecoreuapBase_61; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x18006c57c  mov     r9d, ebx; char *
0x18006c57f  mov     rcx, [rbp+8]; this
0x18006c583  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006c588  jmp     short loc_18006C58C
0x18006c58a  xor     ebx, ebx
0x18006c58c  lea     rcx, [rbp+var_50]
0x18006c590  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18006c595  mov     eax, ebx
0x18006c597  lea     r11, [rsp+70h+var_s0]
0x18006c59c  mov     rbx, [r11+18h]
0x18006c5a0  mov     rdi, [r11+28h]
0x18006c5a4  mov     rsp, r11
0x18006c5a7  pop     rbp
0x18006c5a8  retn
```
