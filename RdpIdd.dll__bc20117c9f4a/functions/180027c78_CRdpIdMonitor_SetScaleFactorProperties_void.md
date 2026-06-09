# CRdpIdMonitor::SetScaleFactorProperties(void)

- ea: `0x180027c78`
- end: `0x180027d6a`
- name: `?SetScaleFactorProperties@CRdpIdMonitor@@QEAAXXZ`
- size: `242`
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

- `0x180027cb0`: `Failed to open property store`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CRdpIdMonitor::SetScaleFactorProperties(CRdpIdMonitor *this)
{
  __int64 *v2; // rcx
  __int64 v3; // rax
  unsigned int v4; // eax
  unsigned int v5; // r9d
  unsigned int v6; // eax
  unsigned int v7; // r9d
  unsigned int v8; // eax
  const char *v9; // [rsp+28h] [rbp-10h]
  const char *v10; // [rsp+28h] [rbp-10h]
  const char *v11; // [rsp+28h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  Rdp::Utils::Props *v13; // [rsp+40h] [rbp+8h] BYREF

  v13 = 0;
  v2 = (__int64 *)*((_QWORD *)this + 39);
  v3 = *v2;
  v13 = 0;
  v4 = (*(__int64 (__fastcall **)(__int64 *, Rdp::Utils::Props **))(v3 + 24))(v2, &v13);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x3D5,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\monitor.cpp",
    (const char *)v4,
    (int)"Failed to open property store",
    v9);
  v6 = Rdp::Utils::Props::IPropertyStore_SetUInt32(
         v13,
         (struct IPropertyStore *)&PKEY_Desktop_Scale_Factor,
         (const struct _tagpropertykey *)*(unsigned int *)(*((_QWORD *)this + 26) + 136LL),
         v5);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x3DC,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\monitor.cpp",
    (const char *)v6,
    (int)"Failed to set PKEY_Desktop_Scale_Factor property",
    v10);
  v8 = Rdp::Utils::Props::IPropertyStore_SetUInt32(
         v13,
         (struct IPropertyStore *)&PKEY_Device_Scale_Factor,
         (const struct _tagpropertykey *)*(unsigned int *)(*((_QWORD *)this + 26) + 140LL),
         v7);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x3E3,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\monitor.cpp",
    (const char *)v8,
    (int)"Failed to set PKEY_Device_Scale_Factor property",
    v11);
  wil::com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>::~com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>((__int64 *)&v13);
}

```

## disassembly

```asm
0x180027c78  push    rbx
0x180027c7a  sub     rsp, 30h
0x180027c7e  mov     rbx, rcx
0x180027c81  mov     [rsp+38h+arg_0], 0
0x180027c8a  mov     rcx, [rcx+138h]
0x180027c91  mov     rax, [rcx]
0x180027c94  mov     [rsp+38h+arg_0], 0
0x180027c9d  lea     rdx, [rsp+38h+arg_0]
0x180027ca2  mov     rax, [rax+18h]
0x180027ca6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027cab  mov     rcx, [rsp+38h]; this
0x180027cb0  lea     rdx, aFailedToOpenPr; "Failed to open property store"
0x180027cb7  mov     qword ptr [rsp+38h+var_18], rdx; int
0x180027cbc  mov     r9d, eax; char *
0x180027cbf  lea     r8, aOnecoreuapTerm_12; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x180027cc6  mov     edx, 3D5h; void *
0x180027ccb  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180027cd0  mov     r8, [rbx+0D0h]
0x180027cd7  mov     r8d, [r8+88h]; struct _tagpropertykey *
0x180027cde  lea     rdx, PKEY_Desktop_Scale_Factor; struct IPropertyStore *
0x180027ce5  mov     rcx, [rsp+38h+arg_0]; this
0x180027cea  call    ?IPropertyStore_SetUInt32@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@I@Z; Rdp::Utils::Props::IPropertyStore_SetUInt32(IPropertyStore *,_tagpropertykey const &,uint)
0x180027cef  mov     rcx, [rsp+38h]; this
0x180027cf4  lea     rdx, aFailedToSetPke_1; "Failed to set PKEY_Desktop_Scale_Factor"...
0x180027cfb  mov     qword ptr [rsp+38h+var_18], rdx; int
0x180027d00  mov     r9d, eax; char *
0x180027d03  lea     r8, aOnecoreuapTerm_12; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x180027d0a  mov     edx, 3DCh; void *
0x180027d0f  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180027d14  mov     r8, [rbx+0D0h]
0x180027d1b  mov     r8d, [r8+8Ch]; struct _tagpropertykey *
0x180027d22  lea     rdx, PKEY_Device_Scale_Factor; struct IPropertyStore *
0x180027d29  mov     rcx, [rsp+38h+arg_0]; this
0x180027d2e  call    ?IPropertyStore_SetUInt32@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@I@Z; Rdp::Utils::Props::IPropertyStore_SetUInt32(IPropertyStore *,_tagpropertykey const &,uint)
0x180027d33  mov     rcx, [rsp+38h]; this
0x180027d38  lea     rdx, aFailedToSetPke_37; "Failed to set PKEY_Device_Scale_Factor "...
0x180027d3f  mov     qword ptr [rsp+38h+var_18], rdx; int
0x180027d44  mov     r9d, eax; char *
0x180027d47  lea     r8, aOnecoreuapTerm_12; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x180027d4e  mov     edx, 3E3h; void *
0x180027d53  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180027d58  nop
0x180027d59  lea     rcx, [rsp+38h+arg_0]
0x180027d5e  call    ??1?$com_ptr_t@UIColorSpaceTransform@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>::~com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>(void)
0x180027d63  add     rsp, 30h
0x180027d67  pop     rbx
0x180027d68  retn
```
