# CRdpIdMonitor::SetWireFormatInfoProperties(void)

- ea: `0x180027e24`
- end: `0x180027ecb`
- name: `?SetWireFormatInfoProperties@CRdpIdMonitor@@QEAAXXZ`
- size: `167`
- prototype: `void __fastcall(CRdpIdMonitor *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180024494`

## callees

- `0x18000ead8`
- `0x180017914`
- `0x18001ddf4`
- `0x18003f010`

## string_xrefs

- `0x180027e5c`: `Failed to open property store`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CRdpIdMonitor::SetWireFormatInfoProperties(CRdpIdMonitor *this)
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
    (void *)0x48F,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\monitor.cpp",
    (const char *)v4,
    (int)"Failed to open property store",
    v7);
  v6 = Rdp::Utils::Props::IPropertyStore_SetUInt32(
         v10,
         (struct IPropertyStore *)&PKEY_Color_Space,
         (const struct _tagpropertykey *)*((unsigned int *)this + 46),
         v5);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x496,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\monitor.cpp",
    (const char *)v6,
    (int)"Failed to set PKEY_Color_Space property",
    v8);
  wil::com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>::~com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>((__int64 *)&v10);
}

```

## disassembly

```asm
0x180027e24  push    rbx
0x180027e26  sub     rsp, 30h
0x180027e2a  mov     rbx, rcx
0x180027e2d  mov     [rsp+38h+arg_0], 0
0x180027e36  mov     rcx, [rcx+138h]
0x180027e3d  mov     rax, [rcx]
0x180027e40  mov     [rsp+38h+arg_0], 0
0x180027e49  lea     rdx, [rsp+38h+arg_0]
0x180027e4e  mov     rax, [rax+18h]
0x180027e52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027e57  mov     rcx, [rsp+38h]; this
0x180027e5c  lea     rdx, aFailedToOpenPr; "Failed to open property store"
0x180027e63  mov     qword ptr [rsp+38h+var_18], rdx; int
0x180027e68  mov     r9d, eax; char *
0x180027e6b  lea     r8, aOnecoreuapTerm_12; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x180027e72  mov     edx, 48Fh; void *
0x180027e77  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180027e7c  mov     r8d, [rbx+0B8h]; struct _tagpropertykey *
0x180027e83  lea     rdx, PKEY_Color_Space; struct IPropertyStore *
0x180027e8a  mov     rcx, [rsp+38h+arg_0]; this
0x180027e8f  call    ?IPropertyStore_SetUInt32@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@I@Z; Rdp::Utils::Props::IPropertyStore_SetUInt32(IPropertyStore *,_tagpropertykey const &,uint)
0x180027e94  mov     rcx, [rsp+38h]; this
0x180027e99  lea     rdx, aFailedToSetPke_28; "Failed to set PKEY_Color_Space property"
0x180027ea0  mov     qword ptr [rsp+38h+var_18], rdx; int
0x180027ea5  mov     r9d, eax; char *
0x180027ea8  lea     r8, aOnecoreuapTerm_12; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x180027eaf  mov     edx, 496h; void *
0x180027eb4  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180027eb9  nop
0x180027eba  lea     rcx, [rsp+38h+arg_0]
0x180027ebf  call    ??1?$com_ptr_t@UIColorSpaceTransform@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>::~com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>(void)
0x180027ec4  add     rsp, 30h
0x180027ec8  pop     rbx
0x180027ec9  retn
```
