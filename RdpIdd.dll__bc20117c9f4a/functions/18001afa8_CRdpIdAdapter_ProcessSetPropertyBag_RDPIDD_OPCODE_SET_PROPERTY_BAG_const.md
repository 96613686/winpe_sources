# CRdpIdAdapter::ProcessSetPropertyBag(_RDPIDD_OPCODE_SET_PROPERTY_BAG * const)

- ea: `0x18001afa8`
- end: `0x18001b0fe`
- name: `?ProcessSetPropertyBag@CRdpIdAdapter@@AEAAXQEAU_RDPIDD_OPCODE_SET_PROPERTY_BAG@@@Z`
- size: `342`
- prototype: `void(CRdpIdAdapter *__hidden this, struct _RDPIDD_OPCODE_SET_PROPERTY_BAG *const)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800185bc`

## callees

- `0x18000ead8`
- `0x180012ba0`
- `0x180015d80`
- `0x18001dd70`
- `0x18001ddf4`
- `0x18003f010`

## import_xrefs

- `PROPSYS!PSCreateMemoryPropertyStore` at `0x18001b05f`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x18001b05f`

## string_xrefs

- `0x18001b070`: `Failed to create property store`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall CRdpIdAdapter::ProcessSetPropertyBag(
        CRdpIdAdapter *this,
        struct _RDPIDD_OPCODE_SET_PROPERTY_BAG *const a2)
{
  void (__fastcall ***v4)(_QWORD, GUID *, __int64 *); // rcx
  unsigned int v5; // eax
  CRdpIdAdapter *v6; // rcx
  unsigned int v7; // eax
  char *v8; // [rsp+28h] [rbp-10h]
  char *v9; // [rsp+28h] [rbp-10h]
  const char *v10; // [rsp+30h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  void *ppv; // [rsp+40h] [rbp+8h] BYREF
  __int64 v13; // [rsp+48h] [rbp+10h] BYREF

  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0xF6A,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
    (const char *)0x80070057LL,
    *((_QWORD *)this + 70) == 0,
    (bool)"Encoding processor has not been started",
    v10);
  v4 = (void (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 70);
  v13 = 0;
  (**v4)(v4, &GUID_1217a55d_d382_404e_ad5c_47a51893b321, &v13);
  wil::details::in1diag3::Throw_HrIfNullMsg<wil::com_ptr_t<Rdp::Avenc::ISerializePropertyBag,wil::err_exception_policy>,0>(
    retaddr,
    3953,
    "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
    2147500034LL,
    &v13,
    "Encoding processor does not support ISerializePropertyBag interface");
  ppv = 0;
  v5 = PSCreateMemoryPropertyStore(&GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99, &ppv);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0xF7B,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
    (const char *)v5,
    (int)"Failed to create property store",
    v8);
  CRdpIdAdapter::DeserializePropertyBag(v6, a2, (struct IPropertyStore *)ppv);
  v7 = (*(__int64 (__fastcall **)(__int64, char *, void *))(*(_QWORD *)v13 + 24LL))(v13, (char *)a2 + 12, ppv);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0xF89,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
    (const char *)v7,
    (int)"Failed to set property bag",
    v9);
  wil::com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>::~com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>(&ppv);
  wil::com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>::~com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>(&v13);
}

```

## disassembly

```asm
0x18001afa8  mov     [rsp+arg_10], rbx
0x18001afad  push    rdi; char *
0x18001afae  sub     rsp, 30h
0x18001afb2  mov     rdi, rdx
0x18001afb5  mov     rbx, rcx
0x18001afb8  cmp     qword ptr [rcx+230h], 0
0x18001afc0  setz    al
0x18001afc3  mov     rcx, [rsp+38h]; this
0x18001afc8  lea     rdx, aEncodingProces; "Encoding processor has not been started"
0x18001afcf  mov     [rsp+38h+var_10], rdx; bool
0x18001afd4  mov     [rsp+38h+var_18], al; char
0x18001afd8  mov     r9d, 80070057h; char *
0x18001afde  lea     r8, aOnecoreuapTerm_15; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x18001afe5  mov     edx, 0F6Ah; void *
0x18001afea  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x18001afef  mov     rcx, [rbx+230h]
0x18001aff6  mov     [rsp+38h+arg_8], 0
0x18001afff  mov     rax, [rcx]
0x18001b002  lea     r8, [rsp+38h+arg_8]
0x18001b007  lea     rdx, _GUID_1217a55d_d382_404e_ad5c_47a51893b321
0x18001b00e  mov     rax, [rax]
0x18001b011  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b016  nop
0x18001b017  mov     rcx, [rsp+38h]
0x18001b01c  lea     rax, aEncodingProces_0; "Encoding processor does not support ISe"...
0x18001b023  mov     [rsp+38h+var_10], rax; char *
0x18001b028  lea     rax, [rsp+38h+arg_8]
0x18001b02d  mov     qword ptr [rsp+38h+var_18], rax
0x18001b032  mov     r9d, 80004002h
0x18001b038  lea     r8, aOnecoreuapTerm_15; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x18001b03f  mov     edx, 0F71h
0x18001b044  call    ??$Throw_HrIfNullMsg@V?$com_ptr_t@UISerializePropertyBag@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@$0A@@in1diag3@details@wil@@YAXPEAXIPEBDJAEBV?$com_ptr_t@UISerializePropertyBag@Avenc@Rdp@@Uerr_exception_policy@wil@@@2@1ZZ; wil::details::in1diag3::Throw_HrIfNullMsg<wil::com_ptr_t<Rdp::Avenc::ISerializePropertyBag,wil::err_exception_policy>,0>(void *,uint,char const *,long,wil::com_ptr_t<Rdp::Avenc::ISerializePropertyBag,wil::err_exception_policy> const &,char const *,...)
0x18001b049  nop
0x18001b04a  mov     [rsp+38h+ppv], 0
0x18001b053  lea     rdx, [rsp+38h+ppv]; ppv
0x18001b058  lea     rcx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99; riid
0x18001b05f  call    cs:__imp_PSCreateMemoryPropertyStore
0x18001b066  nop     dword ptr [rax+rax+00h]
0x18001b06b  mov     rcx, [rsp+38h]; this
0x18001b070  lea     rdx, aFailedToCreate_8; "Failed to create property store"
0x18001b077  mov     qword ptr [rsp+38h+var_18], rdx; int
0x18001b07c  mov     r9d, eax; char *
0x18001b07f  lea     r8, aOnecoreuapTerm_15; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x18001b086  mov     edx, 0F7Bh; void *
0x18001b08b  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18001b090  mov     r8, [rsp+38h+ppv]; struct IPropertyStore *
0x18001b095  mov     rdx, rdi; struct _RDPIDD_OPCODE_SET_PROPERTY_BAG *
0x18001b098  call    ?DeserializePropertyBag@CRdpIdAdapter@@AEAAXQEAU_RDPIDD_OPCODE_SET_PROPERTY_BAG@@PEAUIPropertyStore@@@Z; CRdpIdAdapter::DeserializePropertyBag(_RDPIDD_OPCODE_SET_PROPERTY_BAG * const,IPropertyStore *)
0x18001b09d  mov     rcx, [rsp+38h+arg_8]
0x18001b0a2  mov     rax, [rcx]
0x18001b0a5  lea     rdx, [rdi+0Ch]
0x18001b0a9  mov     r8, [rsp+38h+ppv]
0x18001b0ae  mov     rax, [rax+18h]
0x18001b0b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b0b7  mov     rcx, [rsp+38h]; this
0x18001b0bc  lea     rdx, aFailedToSetPro; "Failed to set property bag"
0x18001b0c3  mov     qword ptr [rsp+38h+var_18], rdx; int
0x18001b0c8  mov     r9d, eax; char *
0x18001b0cb  lea     r8, aOnecoreuapTerm_15; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x18001b0d2  mov     edx, 0F89h; void *
0x18001b0d7  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18001b0dc  nop
0x18001b0dd  lea     rcx, [rsp+38h+ppv]
0x18001b0e2  call    ??1?$com_ptr_t@UIColorSpaceTransform@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>::~com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>(void)
0x18001b0e7  nop
0x18001b0e8  lea     rcx, [rsp+38h+arg_8]
0x18001b0ed  call    ??1?$com_ptr_t@UIColorSpaceTransform@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>::~com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>(void)
0x18001b0f2  mov     rbx, [rsp+38h+arg_10]
0x18001b0f7  add     rsp, 30h
0x18001b0fb  pop     rdi
0x18001b0fc  retn
```
