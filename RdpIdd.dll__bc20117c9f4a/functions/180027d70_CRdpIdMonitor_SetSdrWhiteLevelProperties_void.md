# CRdpIdMonitor::SetSdrWhiteLevelProperties(void)

- ea: `0x180027d70`
- end: `0x180027e1e`
- name: `?SetSdrWhiteLevelProperties@CRdpIdMonitor@@QEAAXXZ`
- size: `174`
- prototype: `void __fastcall(CRdpIdMonitor *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001e634`
- `0x18001f2a0`

## callees

- `0x18000ead8`
- `0x180017914`
- `0x18001ddf4`
- `0x18003f010`

## string_xrefs

- `0x180027da8`: `Failed to open property store`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CRdpIdMonitor::SetSdrWhiteLevelProperties(CRdpIdMonitor *this)
{
  __int64 *v2; // rcx
  __int64 v3; // rax
  unsigned int v4; // eax
  unsigned int v5; // r9d
  unsigned int v6; // eax
  const char *v7; // [rsp+28h] [rbp-10h]
  const char *v8; // [rsp+28h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  Rdp::Utils::Props *v10; // [rsp+40h] [rbp+8h] BYREF

  v10 = 0;
  v2 = (__int64 *)*((_QWORD *)this + 39);
  v3 = *v2;
  v10 = 0;
  v4 = (*(__int64 (__fastcall **)(__int64 *, Rdp::Utils::Props **))(v3 + 24))(v2, &v10);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x46D,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\monitor.cpp",
    (const char *)v4,
    (int)"Failed to open property store",
    v7);
  v6 = Rdp::Utils::Props::IPropertyStore_SetUInt32(
         v10,
         (struct IPropertyStore *)&PKEY_Sdr_White_Level,
         (const struct _tagpropertykey *)*(unsigned int *)(*((_QWORD *)this + 26) + 244LL),
         v5);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x474,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\monitor.cpp",
    (const char *)v6,
    (int)"Failed to set PKEY_Sdr_White_Level property",
    v8);
  wil::com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>::~com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>((__int64 *)&v10);
}

```

## disassembly

```asm
0x180027d70  push    rbx
0x180027d72  sub     rsp, 30h
0x180027d76  mov     rbx, rcx
0x180027d79  mov     [rsp+38h+arg_0], 0
0x180027d82  mov     rcx, [rcx+138h]
0x180027d89  mov     rax, [rcx]
0x180027d8c  mov     [rsp+38h+arg_0], 0
0x180027d95  lea     rdx, [rsp+38h+arg_0]
0x180027d9a  mov     rax, [rax+18h]
0x180027d9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027da3  mov     rcx, [rsp+38h]; this
0x180027da8  lea     rdx, aFailedToOpenPr; "Failed to open property store"
0x180027daf  mov     qword ptr [rsp+38h+var_18], rdx; int
0x180027db4  mov     r9d, eax; char *
0x180027db7  lea     r8, aOnecoreuapTerm_12; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x180027dbe  mov     edx, 46Dh; void *
0x180027dc3  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180027dc8  mov     r8, [rbx+0D0h]
0x180027dcf  mov     r8d, [r8+0F4h]; struct _tagpropertykey *
0x180027dd6  lea     rdx, PKEY_Sdr_White_Level; struct IPropertyStore *
0x180027ddd  mov     rcx, [rsp+38h+arg_0]; this
0x180027de2  call    ?IPropertyStore_SetUInt32@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@I@Z; Rdp::Utils::Props::IPropertyStore_SetUInt32(IPropertyStore *,_tagpropertykey const &,uint)
0x180027de7  mov     rcx, [rsp+38h]; this
0x180027dec  lea     rdx, aFailedToSetPke_19; "Failed to set PKEY_Sdr_White_Level prop"...
0x180027df3  mov     qword ptr [rsp+38h+var_18], rdx; int
0x180027df8  mov     r9d, eax; char *
0x180027dfb  lea     r8, aOnecoreuapTerm_12; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x180027e02  mov     edx, 474h; void *
0x180027e07  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180027e0c  nop
0x180027e0d  lea     rcx, [rsp+38h+arg_0]
0x180027e12  call    ??1?$com_ptr_t@UIColorSpaceTransform@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>::~com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>(void)
0x180027e17  add     rsp, 30h
0x180027e1b  pop     rbx
0x180027e1c  retn
```
