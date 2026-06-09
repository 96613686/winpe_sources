# CRdpIdMonitor::SetDisplayAdapterProperties(void)

- ea: `0x180027724`
- end: `0x180027845`
- name: `?SetDisplayAdapterProperties@CRdpIdMonitor@@AEAAXXZ`
- size: `289`
- prototype: `void __fastcall(CRdpIdMonitor *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180025180`

## callees

- `0x18000ead8`
- `0x1800178c8`
- `0x180017914`
- `0x180017ac8`
- `0x18001ddf4`
- `0x18003f010`

## string_xrefs

- `0x18002775c`: `Failed to open property store`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CRdpIdMonitor::SetDisplayAdapterProperties(CRdpIdMonitor *this)
{
  __int64 *v2; // rcx
  __int64 v3; // rax
  unsigned int v4; // eax
  const struct _LUID *v5; // r9
  unsigned int v6; // eax
  unsigned int v7; // r9d
  unsigned int v8; // eax
  unsigned int v9; // eax
  const char *v10; // [rsp+28h] [rbp-10h]
  const char *v11; // [rsp+28h] [rbp-10h]
  const char *v12; // [rsp+28h] [rbp-10h]
  const char *v13; // [rsp+28h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  Rdp::Utils::Props *v15; // [rsp+40h] [rbp+8h] BYREF

  v15 = 0;
  v2 = (__int64 *)*((_QWORD *)this + 39);
  v3 = *v2;
  v15 = 0;
  v4 = (*(__int64 (__fastcall **)(__int64 *, Rdp::Utils::Props **))(v3 + 24))(v2, &v15);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x32B,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\monitor.cpp",
    (const char *)v4,
    (int)"Failed to open property store",
    v10);
  v6 = Rdp::Utils::Props::IPropertyStore_SetLuid(
         v15,
         (struct IPropertyStore *)&PKEY_Display_Adapter_Luid,
         (const struct _tagpropertykey *)((char *)this + 292),
         v5);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x332,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\monitor.cpp",
    (const char *)v6,
    (int)"Failed to set PKEY_Display_Adapter_Luid property",
    v11);
  v8 = Rdp::Utils::Props::IPropertyStore_SetUInt32(
         v15,
         (struct IPropertyStore *)&PKEY_Display_Adapter_Target_Id,
         (const struct _tagpropertykey *)*((unsigned int *)this + 72),
         v7);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x339,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\monitor.cpp",
    (const char *)v8,
    (int)"Failed to set PKEY_Display_Adapter_Target_Id property",
    v12);
  v9 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 39) + 64LL))(*((_QWORD *)this + 39), 32);
  wil::details::in1diag3::Log_IfFailedMsg(
    retaddr,
    (void *)0x33C,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\monitor.cpp",
    (const char *)v9,
    (int)"Failed to set display adapter info",
    v13);
  wil::com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>::~com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>((__int64 *)&v15);
}

```

## disassembly

```asm
0x180027724  push    rbx
0x180027726  sub     rsp, 30h
0x18002772a  mov     rbx, rcx
0x18002772d  mov     [rsp+38h+arg_0], 0
0x180027736  mov     rcx, [rcx+138h]
0x18002773d  mov     rax, [rcx]
0x180027740  mov     [rsp+38h+arg_0], 0
0x180027749  lea     rdx, [rsp+38h+arg_0]
0x18002774e  mov     rax, [rax+18h]
0x180027752  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027757  mov     rcx, [rsp+38h]; this
0x18002775c  lea     rdx, aFailedToOpenPr; "Failed to open property store"
0x180027763  mov     qword ptr [rsp+38h+var_18], rdx; int
0x180027768  mov     r9d, eax; char *
0x18002776b  lea     r8, aOnecoreuapTerm_12; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x180027772  mov     edx, 32Bh; void *
0x180027777  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18002777c  lea     r8, [rbx+124h]; struct _tagpropertykey *
0x180027783  lea     rdx, PKEY_Display_Adapter_Luid; struct IPropertyStore *
0x18002778a  mov     rcx, [rsp+38h+arg_0]; this
0x18002778f  call    ?IPropertyStore_SetLuid@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@AEBU_LUID@@@Z; Rdp::Utils::Props::IPropertyStore_SetLuid(IPropertyStore *,_tagpropertykey const &,_LUID const &)
0x180027794  mov     rcx, [rsp+38h]; this
0x180027799  lea     rdx, aFailedToSetPke_8; "Failed to set PKEY_Display_Adapter_Luid"...
0x1800277a0  mov     qword ptr [rsp+38h+var_18], rdx; int
0x1800277a5  mov     r9d, eax; char *
0x1800277a8  lea     r8, aOnecoreuapTerm_12; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x1800277af  mov     edx, 332h; void *
0x1800277b4  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800277b9  mov     r8d, [rbx+120h]; struct _tagpropertykey *
0x1800277c0  lea     rdx, PKEY_Display_Adapter_Target_Id; struct IPropertyStore *
0x1800277c7  mov     rcx, [rsp+38h+arg_0]; this
0x1800277cc  call    ?IPropertyStore_SetUInt32@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@I@Z; Rdp::Utils::Props::IPropertyStore_SetUInt32(IPropertyStore *,_tagpropertykey const &,uint)
0x1800277d1  mov     rcx, [rsp+38h]; this
0x1800277d6  lea     rdx, aFailedToSetPke_31; "Failed to set PKEY_Display_Adapter_Targ"...
0x1800277dd  mov     qword ptr [rsp+38h+var_18], rdx; int
0x1800277e2  mov     r9d, eax; char *
0x1800277e5  lea     r8, aOnecoreuapTerm_12; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x1800277ec  mov     edx, 339h; void *
0x1800277f1  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800277f6  mov     rcx, [rbx+138h]
0x1800277fd  mov     rax, [rcx]
0x180027800  mov     edx, 20h ; ' '
0x180027805  mov     rax, [rax+40h]
0x180027809  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002780e  mov     rcx, [rsp+38h]; this
0x180027813  lea     rdx, aFailedToSetDis; "Failed to set display adapter info"
0x18002781a  mov     qword ptr [rsp+38h+var_18], rdx; int
0x18002781f  mov     r9d, eax; char *
0x180027822  lea     r8, aOnecoreuapTerm_12; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x180027829  mov     edx, 33Ch; void *
0x18002782e  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180027833  nop
0x180027834  lea     rcx, [rsp+38h+arg_0]
0x180027839  call    ??1?$com_ptr_t@UIColorSpaceTransform@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>::~com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>(void)
0x18002783e  add     rsp, 30h
0x180027842  pop     rbx
0x180027843  retn
```
