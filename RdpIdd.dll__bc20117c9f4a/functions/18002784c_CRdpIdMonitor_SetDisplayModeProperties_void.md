# CRdpIdMonitor::SetDisplayModeProperties(void)

- ea: `0x18002784c`
- end: `0x180027b81`
- name: `?SetDisplayModeProperties@CRdpIdMonitor@@QEAAXXZ`
- size: `821`
- prototype: `void __fastcall(CRdpIdMonitor *__hidden this)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001e634`
- `0x18001f2a0`

## callees

- `0x18000ead8`
- `0x180017888`
- `0x180017914`
- `0x18001ddf4`
- `0x180021264`
- `0x18002784c`
- `0x18003f010`

## string_xrefs

- `0x18002788c`: `Failed to open property store`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CRdpIdMonitor::SetDisplayModeProperties(CRdpIdMonitor *this)
{
  __int64 *v2; // rcx
  __int64 v3; // rax
  unsigned int v4; // eax
  int v5; // r9d
  unsigned int v6; // eax
  int v7; // r9d
  unsigned int v8; // eax
  int v9; // r9d
  unsigned int v10; // eax
  int v11; // r9d
  unsigned int v12; // eax
  unsigned int v13; // r9d
  unsigned int v14; // eax
  unsigned int v15; // r9d
  unsigned int v16; // eax
  unsigned int v17; // r9d
  unsigned int v18; // eax
  unsigned int v19; // r9d
  unsigned int v20; // eax
  unsigned int v21; // r9d
  unsigned int v22; // eax
  unsigned int v23; // r9d
  unsigned int v24; // eax
  unsigned int v25; // r9d
  __int64 v26; // r8
  unsigned int v27; // eax
  const char *v28; // [rsp+28h] [rbp-18h]
  const char *v29; // [rsp+28h] [rbp-18h]
  const char *v30; // [rsp+28h] [rbp-18h]
  const char *v31; // [rsp+28h] [rbp-18h]
  const char *v32; // [rsp+28h] [rbp-18h]
  const char *v33; // [rsp+28h] [rbp-18h]
  const char *v34; // [rsp+28h] [rbp-18h]
  const char *v35; // [rsp+28h] [rbp-18h]
  const char *v36; // [rsp+28h] [rbp-18h]
  const char *v37; // [rsp+28h] [rbp-18h]
  const char *v38; // [rsp+28h] [rbp-18h]
  const char *v39; // [rsp+28h] [rbp-18h]
  _DWORD v40[4]; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+8h]
  Rdp::Utils::Props *v42; // [rsp+50h] [rbp+10h] BYREF

  v42 = 0;
  v2 = (__int64 *)*((_QWORD *)this + 39);
  v3 = *v2;
  v42 = 0;
  v4 = (*(__int64 (__fastcall **)(__int64 *, Rdp::Utils::Props **))(v3 + 24))(v2, &v42);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x357,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\monitor.cpp",
    (const char *)v4,
    (int)"Failed to open property store",
    v28);
  v6 = Rdp::Utils::Props::IPropertyStore_SetInt32(
         v42,
         (struct IPropertyStore *)&PKEY_Primary_Monitor_Offset_X,
         (const struct _tagpropertykey *)*(unsigned int *)(*((_QWORD *)this + 26) + 88LL),
         v5);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x361,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\monitor.cpp",
    (const char *)v6,
    (int)"Failed to set PKEY_Primary_Monitor_Offset_X property",
    v29);
  v8 = Rdp::Utils::Props::IPropertyStore_SetInt32(
         v42,
         (struct IPropertyStore *)&PKEY_Primary_Monitor_Offset_Y,
         (const struct _tagpropertykey *)*(unsigned int *)(*((_QWORD *)this + 26) + 92LL),
         v7);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x368,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\monitor.cpp",
    (const char *)v8,
    (int)"Failed to set PKEY_Primary_Monitor_Offset_Y property",
    v30);
  std::_Atomic_storage<RDP_MONITORCONFIG_2DRECTANGLE,16>::load(*((_QWORD *)this + 29) + 568LL, v40);
  v10 = Rdp::Utils::Props::IPropertyStore_SetInt32(
          v42,
          (struct IPropertyStore *)&PKEY_Desktop_Monitor_Offset_X,
          (const struct _tagpropertykey *)v40[0],
          v9);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x373,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\monitor.cpp",
    (const char *)v10,
    (int)"Failed to set PKEY_Desktop_Monitor_Offset_X property",
    v31);
  v12 = Rdp::Utils::Props::IPropertyStore_SetInt32(
          v42,
          (struct IPropertyStore *)&PKEY_Desktop_Monitor_Offset_Y,
          (const struct _tagpropertykey *)v40[1],
          v11);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x37A,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\monitor.cpp",
    (const char *)v12,
    (int)"Failed to set PKEY_Desktop_Monitor_Offset_Y property",
    v32);
  v14 = Rdp::Utils::Props::IPropertyStore_SetUInt32(
          v42,
          (struct IPropertyStore *)&PKEY_Width_In_Pixels,
          (const struct _tagpropertykey *)*(unsigned int *)(*((_QWORD *)this + 26) + 96LL),
          v13);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x384,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\monitor.cpp",
    (const char *)v14,
    (int)"Failed to set PKEY_Width_In_Pixels property",
    v33);
  v16 = Rdp::Utils::Props::IPropertyStore_SetUInt32(
          v42,
          (struct IPropertyStore *)&PKEY_Height_In_Pixels,
          (const struct _tagpropertykey *)*(unsigned int *)(*((_QWORD *)this + 26) + 100LL),
          v15);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x38B,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\monitor.cpp",
    (const char *)v16,
    (int)"Failed to set PKEY_Height_In_Pixels property",
    v34);
  v18 = Rdp::Utils::Props::IPropertyStore_SetUInt32(
          v42,
          (struct IPropertyStore *)&PKEY_Orientation,
          (const struct _tagpropertykey *)*(unsigned int *)(*((_QWORD *)this + 26) + 108LL),
          v17);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x395,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\monitor.cpp",
    (const char *)v18,
    (int)"Failed to set PKEY_Orientation property",
    v35);
  v20 = Rdp::Utils::Props::IPropertyStore_SetUInt32(
          v42,
          (struct IPropertyStore *)&PKEY_RefreshRate_Numerator,
          (const struct _tagpropertykey *)*(unsigned int *)(*((_QWORD *)this + 26) + 112LL),
          v19);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x39F,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\monitor.cpp",
    (const char *)v20,
    (int)"Failed to set PKEY_RefreshRate_Numerator property",
    v36);
  v22 = Rdp::Utils::Props::IPropertyStore_SetUInt32(
          v42,
          (struct IPropertyStore *)&PKEY_RefreshRate_Denominator,
          (const struct _tagpropertykey *)*(unsigned int *)(*((_QWORD *)this + 26) + 116LL),
          v21);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x3A6,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\monitor.cpp",
    (const char *)v22,
    (int)"Failed to set PKEY_RefreshRate_Denominator property",
    v37);
  v24 = Rdp::Utils::Props::IPropertyStore_SetUInt32(
          v42,
          (struct IPropertyStore *)&PKEY_VSyncFreqDivider,
          (const struct _tagpropertykey *)*(unsigned int *)(*((_QWORD *)this + 26) + 120LL),
          v23);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x3B0,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\monitor.cpp",
    (const char *)v24,
    (int)"Failed to set PKEY_VSyncFreqDivider property",
    v38);
  v26 = 0;
  switch ( *(_DWORD *)(*((_QWORD *)this + 26) + 124LL) )
  {
    case 1:
      v26 = 1;
      break;
    case 2:
      v26 = 2;
      break;
    case 3:
      v26 = 3;
      break;
  }
  v27 = Rdp::Utils::Props::IPropertyStore_SetUInt32(
          v42,
          (struct IPropertyStore *)&PKEY_Color_Mode,
          (const struct _tagpropertykey *)v26,
          v25);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x3BA,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\monitor.cpp",
    (const char *)v27,
    (int)"Failed to set PKEY_Color_Mode property",
    v39);
  wil::com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>::~com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>(&v42);
}

```

## disassembly

```asm
0x18002784c  mov     [rsp-8+arg_8], rbx
0x180027851  mov     [rsp-8+arg_10], rdi
0x180027856  push    rbp
0x180027857  mov     rbp, rsp
0x18002785a  sub     rsp, 40h
0x18002785e  mov     rbx, rcx
0x180027861  mov     [rbp+arg_0], 0
0x180027869  mov     rcx, [rcx+138h]
0x180027870  mov     rax, [rcx]
0x180027873  mov     [rbp+arg_0], 0
0x18002787b  lea     rdx, [rbp+arg_0]
0x18002787f  mov     rax, [rax+18h]
0x180027883  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027888  mov     rcx, [rbp+8]; this
0x18002788c  lea     rdx, aFailedToOpenPr; "Failed to open property store"
0x180027893  mov     qword ptr [rsp+40h+var_20], rdx; int
0x180027898  mov     r9d, eax; char *
0x18002789b  lea     rdi, aOnecoreuapTerm_12; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x1800278a2  mov     r8, rdi; unsigned int
0x1800278a5  mov     edx, 357h; void *
0x1800278aa  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800278af  mov     r8, [rbx+0D0h]
0x1800278b6  mov     r8d, [r8+58h]; struct _tagpropertykey *
0x1800278ba  lea     rdx, PKEY_Primary_Monitor_Offset_X; struct IPropertyStore *
0x1800278c1  mov     rcx, [rbp+arg_0]; this
0x1800278c5  call    ?IPropertyStore_SetInt32@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@H@Z; Rdp::Utils::Props::IPropertyStore_SetInt32(IPropertyStore *,_tagpropertykey const &,int)
0x1800278ca  mov     rcx, [rbp+8]; this
0x1800278ce  lea     rdx, aFailedToSetPke_26; "Failed to set PKEY_Primary_Monitor_Offs"...
0x1800278d5  mov     qword ptr [rsp+40h+var_20], rdx; int
0x1800278da  mov     r9d, eax; char *
0x1800278dd  mov     r8, rdi; unsigned int
0x1800278e0  mov     edx, 361h; void *
0x1800278e5  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800278ea  mov     r8, [rbx+0D0h]
0x1800278f1  mov     r8d, [r8+5Ch]; struct _tagpropertykey *
0x1800278f5  lea     rdx, PKEY_Primary_Monitor_Offset_Y; struct IPropertyStore *
0x1800278fc  mov     rcx, [rbp+arg_0]; this
0x180027900  call    ?IPropertyStore_SetInt32@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@H@Z; Rdp::Utils::Props::IPropertyStore_SetInt32(IPropertyStore *,_tagpropertykey const &,int)
0x180027905  mov     rcx, [rbp+8]; this
0x180027909  lea     rdx, aFailedToSetPke_25; "Failed to set PKEY_Primary_Monitor_Offs"...
0x180027910  mov     qword ptr [rsp+40h+var_20], rdx; int
0x180027915  mov     r9d, eax; char *
0x180027918  mov     r8, rdi; unsigned int
0x18002791b  mov     edx, 368h; void *
0x180027920  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180027925  mov     rcx, [rbx+0E8h]
0x18002792c  add     rcx, 238h
0x180027933  lea     rdx, [rbp+var_10]
0x180027937  call    ?load@?$_Atomic_storage@URDP_MONITORCONFIG_2DRECTANGLE@@$0BA@@std@@QEBA?AURDP_MONITORCONFIG_2DRECTANGLE@@W4memory_order@2@@Z; std::_Atomic_storage<RDP_MONITORCONFIG_2DRECTANGLE,16>::load(std::memory_order)
0x18002793c  mov     r8d, [rbp+var_10]; struct _tagpropertykey *
0x180027940  lea     rdx, PKEY_Desktop_Monitor_Offset_X; struct IPropertyStore *
0x180027947  mov     rcx, [rbp+arg_0]; this
0x18002794b  call    ?IPropertyStore_SetInt32@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@H@Z; Rdp::Utils::Props::IPropertyStore_SetInt32(IPropertyStore *,_tagpropertykey const &,int)
0x180027950  mov     rcx, [rbp+8]; this
0x180027954  lea     rdx, aFailedToSetPke_42; "Failed to set PKEY_Desktop_Monitor_Offs"...
0x18002795b  mov     qword ptr [rsp+40h+var_20], rdx; int
0x180027960  mov     r9d, eax; char *
0x180027963  mov     r8, rdi; unsigned int
0x180027966  mov     edx, 373h; void *
0x18002796b  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180027970  mov     r8d, [rbp+var_10+4]; struct _tagpropertykey *
0x180027974  lea     rdx, PKEY_Desktop_Monitor_Offset_Y; struct IPropertyStore *
0x18002797b  mov     rcx, [rbp+arg_0]; this
0x18002797f  call    ?IPropertyStore_SetInt32@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@H@Z; Rdp::Utils::Props::IPropertyStore_SetInt32(IPropertyStore *,_tagpropertykey const &,int)
0x180027984  mov     rcx, [rbp+8]; this
0x180027988  lea     rdx, aFailedToSetPke_12; "Failed to set PKEY_Desktop_Monitor_Offs"...
0x18002798f  mov     qword ptr [rsp+40h+var_20], rdx; int
0x180027994  mov     r9d, eax; char *
0x180027997  mov     r8, rdi; unsigned int
0x18002799a  mov     edx, 37Ah; void *
0x18002799f  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800279a4  mov     r8, [rbx+0D0h]
0x1800279ab  mov     r8d, [r8+60h]; struct _tagpropertykey *
0x1800279af  lea     rdx, PKEY_Width_In_Pixels; struct IPropertyStore *
0x1800279b6  mov     rcx, [rbp+arg_0]; this
0x1800279ba  call    ?IPropertyStore_SetUInt32@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@I@Z; Rdp::Utils::Props::IPropertyStore_SetUInt32(IPropertyStore *,_tagpropertykey const &,uint)
0x1800279bf  mov     rcx, [rbp+8]; this
0x1800279c3  lea     rdx, aFailedToSetPke_34; "Failed to set PKEY_Width_In_Pixels prop"...
0x1800279ca  mov     qword ptr [rsp+40h+var_20], rdx; int
0x1800279cf  mov     r9d, eax; char *
0x1800279d2  mov     r8, rdi; unsigned int
0x1800279d5  mov     edx, 384h; void *
0x1800279da  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800279df  mov     r8, [rbx+0D0h]
0x1800279e6  mov     r8d, [r8+64h]; struct _tagpropertykey *
0x1800279ea  lea     rdx, PKEY_Height_In_Pixels; struct IPropertyStore *
0x1800279f1  mov     rcx, [rbp+arg_0]; this
0x1800279f5  call    ?IPropertyStore_SetUInt32@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@I@Z; Rdp::Utils::Props::IPropertyStore_SetUInt32(IPropertyStore *,_tagpropertykey const &,uint)
0x1800279fa  mov     rcx, [rbp+8]; this
0x1800279fe  lea     rdx, aFailedToSetPke_21; "Failed to set PKEY_Height_In_Pixels pro"...
0x180027a05  mov     qword ptr [rsp+40h+var_20], rdx; int
0x180027a0a  mov     r9d, eax; char *
0x180027a0d  mov     r8, rdi; unsigned int
0x180027a10  mov     edx, 38Bh; void *
0x180027a15  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180027a1a  mov     r8, [rbx+0D0h]
0x180027a21  mov     r8d, [r8+6Ch]; struct _tagpropertykey *
0x180027a25  lea     rdx, PKEY_Orientation; struct IPropertyStore *
0x180027a2c  mov     rcx, [rbp+arg_0]; this
0x180027a30  call    ?IPropertyStore_SetUInt32@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@I@Z; Rdp::Utils::Props::IPropertyStore_SetUInt32(IPropertyStore *,_tagpropertykey const &,uint)
0x180027a35  mov     rcx, [rbp+8]; this
0x180027a39  lea     rdx, aFailedToSetPke_30; "Failed to set PKEY_Orientation property"
0x180027a40  mov     qword ptr [rsp+40h+var_20], rdx; int
0x180027a45  mov     r9d, eax; char *
0x180027a48  mov     r8, rdi; unsigned int
0x180027a4b  mov     edx, 395h; void *
0x180027a50  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180027a55  mov     r8, [rbx+0D0h]
0x180027a5c  mov     r8d, [r8+70h]; struct _tagpropertykey *
0x180027a60  lea     rdx, PKEY_RefreshRate_Numerator; struct IPropertyStore *
0x180027a67  mov     rcx, [rbp+arg_0]; this
0x180027a6b  call    ?IPropertyStore_SetUInt32@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@I@Z; Rdp::Utils::Props::IPropertyStore_SetUInt32(IPropertyStore *,_tagpropertykey const &,uint)
0x180027a70  mov     rcx, [rbp+8]; this
0x180027a74  lea     rdx, aFailedToSetPke_35; "Failed to set PKEY_RefreshRate_Numerato"...
0x180027a7b  mov     qword ptr [rsp+40h+var_20], rdx; int
0x180027a80  mov     r9d, eax; char *
0x180027a83  mov     r8, rdi; unsigned int
0x180027a86  mov     edx, 39Fh; void *
0x180027a8b  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180027a90  mov     r8, [rbx+0D0h]
0x180027a97  mov     r8d, [r8+74h]; struct _tagpropertykey *
0x180027a9b  lea     rdx, PKEY_RefreshRate_Denominator; struct IPropertyStore *
0x180027aa2  mov     rcx, [rbp+arg_0]; this
0x180027aa6  call    ?IPropertyStore_SetUInt32@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@I@Z; Rdp::Utils::Props::IPropertyStore_SetUInt32(IPropertyStore *,_tagpropertykey const &,uint)
0x180027aab  mov     rcx, [rbp+8]; this
0x180027aaf  lea     rdx, aFailedToSetPke; "Failed to set PKEY_RefreshRate_Denomina"...
0x180027ab6  mov     qword ptr [rsp+40h+var_20], rdx; int
0x180027abb  mov     r9d, eax; char *
0x180027abe  mov     r8, rdi; unsigned int
0x180027ac1  mov     edx, 3A6h; void *
0x180027ac6  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180027acb  mov     r8, [rbx+0D0h]
0x180027ad2  mov     r8d, [r8+78h]; struct _tagpropertykey *
0x180027ad6  lea     rdx, PKEY_VSyncFreqDivider; struct IPropertyStore *
0x180027add  mov     rcx, [rbp+arg_0]; this
0x180027ae1  call    ?IPropertyStore_SetUInt32@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@I@Z; Rdp::Utils::Props::IPropertyStore_SetUInt32(IPropertyStore *,_tagpropertykey const &,uint)
0x180027ae6  mov     rcx, [rbp+8]; this
0x180027aea  lea     rdx, aFailedToSetPke_18; "Failed to set PKEY_VSyncFreqDivider pro"...
0x180027af1  mov     qword ptr [rsp+40h+var_20], rdx; int
0x180027af6  mov     r9d, eax; char *
0x180027af9  mov     r8, rdi; unsigned int
0x180027afc  mov     edx, 3B0h; void *
0x180027b01  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180027b06  xor     r8d, r8d
0x180027b09  mov     rcx, [rbx+0D0h]
0x180027b10  mov     edx, [rcx+7Ch]
0x180027b13  sub     edx, 1
0x180027b16  jz      short loc_180027B30
0x180027b18  sub     edx, 1
0x180027b1b  jz      short loc_180027B28
0x180027b1d  cmp     edx, 1
0x180027b20  jnz     short loc_180027B36
0x180027b22  lea     r8d, [rdx+2]
0x180027b26  jmp     short loc_180027B36
0x180027b28  mov     r8d, 2
0x180027b2e  jmp     short loc_180027B36
0x180027b30  mov     r8d, 1; struct _tagpropertykey *
0x180027b36  lea     rdx, PKEY_Color_Mode; struct IPropertyStore *
0x180027b3d  mov     rcx, [rbp+arg_0]; this
0x180027b41  call    ?IPropertyStore_SetUInt32@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@I@Z; Rdp::Utils::Props::IPropertyStore_SetUInt32(IPropertyStore *,_tagpropertykey const &,uint)
0x180027b46  mov     rcx, [rbp+8]; this
0x180027b4a  lea     rdx, aFailedToSetPke_22; "Failed to set PKEY_Color_Mode property"
0x180027b51  mov     qword ptr [rsp+40h+var_20], rdx; int
0x180027b56  mov     r9d, eax; char *
0x180027b59  mov     r8, rdi; unsigned int
0x180027b5c  mov     edx, 3BAh; void *
0x180027b61  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180027b66  nop
0x180027b67  lea     rcx, [rbp+arg_0]
0x180027b6b  call    ??1?$com_ptr_t@UIColorSpaceTransform@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>::~com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>(void)
0x180027b70  mov     rbx, [rsp+40h+arg_8]
0x180027b75  mov     rdi, [rsp+40h+arg_10]
0x180027b7a  add     rsp, 40h
0x180027b7e  pop     rbp
0x180027b7f  retn
```
