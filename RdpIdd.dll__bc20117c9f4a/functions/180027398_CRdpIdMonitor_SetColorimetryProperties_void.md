# CRdpIdMonitor::SetColorimetryProperties(void)

- ea: `0x180027398`
- end: `0x18002771c`
- name: `?SetColorimetryProperties@CRdpIdMonitor@@QEAAXXZ`
- size: `900`
- prototype: `void __fastcall(CRdpIdMonitor *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001e634`
- `0x18001f2a0`

## callees

- `0x18000ead8`
- `0x180017914`
- `0x18001ddf4`
- `0x180027398`
- `0x18003f010`

## string_xrefs

- `0x1800273d8`: `Failed to open property store`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CRdpIdMonitor::SetColorimetryProperties(CRdpIdMonitor *this)
{
  __int64 *v2; // rcx
  __int64 v3; // rax
  unsigned int v4; // eax
  unsigned int v5; // r9d
  unsigned int v6; // eax
  unsigned int v7; // r9d
  unsigned int v8; // eax
  unsigned int v9; // r9d
  unsigned int v10; // eax
  unsigned int v11; // r9d
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
  unsigned int v26; // eax
  unsigned int v27; // r9d
  int v28; // ecx
  unsigned __int64 v29; // r8
  unsigned int v30; // eax
  const char *v31; // [rsp+28h] [rbp-8h]
  const char *v32; // [rsp+28h] [rbp-8h]
  const char *v33; // [rsp+28h] [rbp-8h]
  const char *v34; // [rsp+28h] [rbp-8h]
  const char *v35; // [rsp+28h] [rbp-8h]
  const char *v36; // [rsp+28h] [rbp-8h]
  const char *v37; // [rsp+28h] [rbp-8h]
  const char *v38; // [rsp+28h] [rbp-8h]
  const char *v39; // [rsp+28h] [rbp-8h]
  const char *v40; // [rsp+28h] [rbp-8h]
  const char *v41; // [rsp+28h] [rbp-8h]
  const char *v42; // [rsp+28h] [rbp-8h]
  const char *v43; // [rsp+28h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+8h]
  Rdp::Utils::Props *v45; // [rsp+40h] [rbp+10h] BYREF

  v45 = 0;
  v2 = (__int64 *)*((_QWORD *)this + 39);
  v3 = *v2;
  v45 = 0;
  v4 = (*(__int64 (__fastcall **)(__int64 *, Rdp::Utils::Props **))(v3 + 24))(v2, &v45);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x3FE,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\monitor.cpp",
    (const char *)v4,
    (int)"Failed to open property store",
    v31);
  v6 = Rdp::Utils::Props::IPropertyStore_SetUInt32(
         v45,
         (struct IPropertyStore *)&PKEY_Red_Point_X,
         (const struct _tagpropertykey *)*(unsigned int *)(*((_QWORD *)this + 26) + 168LL),
         v5);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x405,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\monitor.cpp",
    (const char *)v6,
    (int)"Failed to set PKEY_Red_Point_X property",
    v32);
  v8 = Rdp::Utils::Props::IPropertyStore_SetUInt32(
         v45,
         (struct IPropertyStore *)&PKEY_Red_Point_Y,
         (const struct _tagpropertykey *)*(unsigned int *)(*((_QWORD *)this + 26) + 172LL),
         v7);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x40C,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\monitor.cpp",
    (const char *)v8,
    (int)"Failed to set PKEY_Red_Point_Y property",
    v33);
  v10 = Rdp::Utils::Props::IPropertyStore_SetUInt32(
          v45,
          (struct IPropertyStore *)&PKEY_Green_Point_X,
          (const struct _tagpropertykey *)*(unsigned int *)(*((_QWORD *)this + 26) + 176LL),
          v9);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x413,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\monitor.cpp",
    (const char *)v10,
    (int)"Failed to set PKEY_Green_Point_X property",
    v34);
  v12 = Rdp::Utils::Props::IPropertyStore_SetUInt32(
          v45,
          (struct IPropertyStore *)&PKEY_Green_Point_Y,
          (const struct _tagpropertykey *)*(unsigned int *)(*((_QWORD *)this + 26) + 180LL),
          v11);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x41A,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\monitor.cpp",
    (const char *)v12,
    (int)"Failed to set PKEY_Green_Point_Y property",
    v35);
  v14 = Rdp::Utils::Props::IPropertyStore_SetUInt32(
          v45,
          (struct IPropertyStore *)&PKEY_Blue_Point_X,
          (const struct _tagpropertykey *)*(unsigned int *)(*((_QWORD *)this + 26) + 184LL),
          v13);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x421,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\monitor.cpp",
    (const char *)v14,
    (int)"Failed to set PKEY_Blue_Point_X property",
    v36);
  v16 = Rdp::Utils::Props::IPropertyStore_SetUInt32(
          v45,
          (struct IPropertyStore *)&PKEY_Blue_Point_Y,
          (const struct _tagpropertykey *)*(unsigned int *)(*((_QWORD *)this + 26) + 188LL),
          v15);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x428,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\monitor.cpp",
    (const char *)v16,
    (int)"Failed to set PKEY_Blue_Point_Y property",
    v37);
  v18 = Rdp::Utils::Props::IPropertyStore_SetUInt32(
          v45,
          (struct IPropertyStore *)&PKEY_White_Point_X,
          (const struct _tagpropertykey *)*(unsigned int *)(*((_QWORD *)this + 26) + 192LL),
          v17);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x42F,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\monitor.cpp",
    (const char *)v18,
    (int)"Failed to set PKEY_White_Point_X property",
    v38);
  v20 = Rdp::Utils::Props::IPropertyStore_SetUInt32(
          v45,
          (struct IPropertyStore *)&PKEY_White_Point_Y,
          (const struct _tagpropertykey *)*(unsigned int *)(*((_QWORD *)this + 26) + 196LL),
          v19);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x436,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\monitor.cpp",
    (const char *)v20,
    (int)"Failed to set PKEY_White_Point_Y property",
    v39);
  v22 = Rdp::Utils::Props::IPropertyStore_SetUInt32(
          v45,
          (struct IPropertyStore *)&PKEY_Min_Luminance,
          (const struct _tagpropertykey *)*(unsigned int *)(*((_QWORD *)this + 26) + 200LL),
          v21);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x43D,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\monitor.cpp",
    (const char *)v22,
    (int)"Failed to set PKEY_Min_Luminance property",
    v40);
  v24 = Rdp::Utils::Props::IPropertyStore_SetUInt32(
          v45,
          (struct IPropertyStore *)&PKEY_Max_Luminance,
          (const struct _tagpropertykey *)*(unsigned int *)(*((_QWORD *)this + 26) + 204LL),
          v23);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x444,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\monitor.cpp",
    (const char *)v24,
    (int)"Failed to set PKEY_Max_Luminance property",
    v41);
  v26 = Rdp::Utils::Props::IPropertyStore_SetUInt32(
          v45,
          (struct IPropertyStore *)&PKEY_Max_Full_Frame_Luminance,
          (const struct _tagpropertykey *)*(unsigned int *)(*((_QWORD *)this + 26) + 208LL),
          v25);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x44B,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\monitor.cpp",
    (const char *)v26,
    (int)"Failed to set PKEY_Max_Full_Frame_Luminance property",
    v42);
  v28 = *(_DWORD *)(*((_QWORD *)this + 26) + 228LL);
  v29 = (v28 & 1) != 0;
  if ( (v28 & 2) != 0 )
    v29 = (unsigned int)v29 | 2;
  if ( (v28 & 4) != 0 )
    v29 = (unsigned int)v29 | 4;
  v30 = Rdp::Utils::Props::IPropertyStore_SetUInt32(
          v45,
          (struct IPropertyStore *)&PKEY_Colorimetry_Flags,
          (const struct _tagpropertykey *)v29,
          v27);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x452,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\monitor.cpp",
    (const char *)v30,
    (int)"Failed to set PKEY_Colorimetry_Flags property",
    v43);
  wil::com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>::~com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>(&v45);
}

```

## disassembly

```asm
0x180027398  mov     [rsp-8+arg_8], rbx
0x18002739d  mov     [rsp-8+arg_10], rdi
0x1800273a2  push    rbp
0x1800273a3  mov     rbp, rsp
0x1800273a6  sub     rsp, 30h
0x1800273aa  mov     rbx, rcx
0x1800273ad  mov     [rbp+arg_0], 0
0x1800273b5  mov     rcx, [rcx+138h]
0x1800273bc  mov     rax, [rcx]
0x1800273bf  mov     [rbp+arg_0], 0
0x1800273c7  lea     rdx, [rbp+arg_0]
0x1800273cb  mov     rax, [rax+18h]
0x1800273cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800273d4  mov     rcx, [rbp+8]; this
0x1800273d8  lea     rdx, aFailedToOpenPr; "Failed to open property store"
0x1800273df  mov     qword ptr [rsp+30h+var_10], rdx; int
0x1800273e4  mov     r9d, eax; char *
0x1800273e7  lea     rdi, aOnecoreuapTerm_12; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x1800273ee  mov     r8, rdi; unsigned int
0x1800273f1  mov     edx, 3FEh; void *
0x1800273f6  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800273fb  mov     r8, [rbx+0D0h]
0x180027402  mov     r8d, [r8+0A8h]; struct _tagpropertykey *
0x180027409  lea     rdx, PKEY_Red_Point_X; struct IPropertyStore *
0x180027410  mov     rcx, [rbp+arg_0]; this
0x180027414  call    ?IPropertyStore_SetUInt32@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@I@Z; Rdp::Utils::Props::IPropertyStore_SetUInt32(IPropertyStore *,_tagpropertykey const &,uint)
0x180027419  mov     rcx, [rbp+8]; this
0x18002741d  lea     rdx, aFailedToSetPke_24; "Failed to set PKEY_Red_Point_X property"
0x180027424  mov     qword ptr [rsp+30h+var_10], rdx; int
0x180027429  mov     r9d, eax; char *
0x18002742c  mov     r8, rdi; unsigned int
0x18002742f  mov     edx, 405h; void *
0x180027434  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180027439  mov     r8, [rbx+0D0h]
0x180027440  mov     r8d, [r8+0ACh]; struct _tagpropertykey *
0x180027447  lea     rdx, PKEY_Red_Point_Y; struct IPropertyStore *
0x18002744e  mov     rcx, [rbp+arg_0]; this
0x180027452  call    ?IPropertyStore_SetUInt32@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@I@Z; Rdp::Utils::Props::IPropertyStore_SetUInt32(IPropertyStore *,_tagpropertykey const &,uint)
0x180027457  mov     rcx, [rbp+8]; this
0x18002745b  lea     rdx, aFailedToSetPke_10; "Failed to set PKEY_Red_Point_Y property"
0x180027462  mov     qword ptr [rsp+30h+var_10], rdx; int
0x180027467  mov     r9d, eax; char *
0x18002746a  mov     r8, rdi; unsigned int
0x18002746d  mov     edx, 40Ch; void *
0x180027472  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180027477  mov     r8, [rbx+0D0h]
0x18002747e  mov     r8d, [r8+0B0h]; struct _tagpropertykey *
0x180027485  lea     rdx, PKEY_Green_Point_X; struct IPropertyStore *
0x18002748c  mov     rcx, [rbp+arg_0]; this
0x180027490  call    ?IPropertyStore_SetUInt32@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@I@Z; Rdp::Utils::Props::IPropertyStore_SetUInt32(IPropertyStore *,_tagpropertykey const &,uint)
0x180027495  mov     rcx, [rbp+8]; this
0x180027499  lea     rdx, aFailedToSetPke_4; "Failed to set PKEY_Green_Point_X proper"...
0x1800274a0  mov     qword ptr [rsp+30h+var_10], rdx; int
0x1800274a5  mov     r9d, eax; char *
0x1800274a8  mov     r8, rdi; unsigned int
0x1800274ab  mov     edx, 413h; void *
0x1800274b0  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800274b5  mov     r8, [rbx+0D0h]
0x1800274bc  mov     r8d, [r8+0B4h]; struct _tagpropertykey *
0x1800274c3  lea     rdx, PKEY_Green_Point_Y; struct IPropertyStore *
0x1800274ca  mov     rcx, [rbp+arg_0]; this
0x1800274ce  call    ?IPropertyStore_SetUInt32@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@I@Z; Rdp::Utils::Props::IPropertyStore_SetUInt32(IPropertyStore *,_tagpropertykey const &,uint)
0x1800274d3  mov     rcx, [rbp+8]; this
0x1800274d7  lea     rdx, aFailedToSetPke_0; "Failed to set PKEY_Green_Point_Y proper"...
0x1800274de  mov     qword ptr [rsp+30h+var_10], rdx; int
0x1800274e3  mov     r9d, eax; char *
0x1800274e6  mov     r8, rdi; unsigned int
0x1800274e9  mov     edx, 41Ah; void *
0x1800274ee  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800274f3  mov     r8, [rbx+0D0h]
0x1800274fa  mov     r8d, [r8+0B8h]; struct _tagpropertykey *
0x180027501  lea     rdx, PKEY_Blue_Point_X; struct IPropertyStore *
0x180027508  mov     rcx, [rbp+arg_0]; this
0x18002750c  call    ?IPropertyStore_SetUInt32@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@I@Z; Rdp::Utils::Props::IPropertyStore_SetUInt32(IPropertyStore *,_tagpropertykey const &,uint)
0x180027511  mov     rcx, [rbp+8]; this
0x180027515  lea     rdx, aFailedToSetPke_15; "Failed to set PKEY_Blue_Point_X propert"...
0x18002751c  mov     qword ptr [rsp+30h+var_10], rdx; int
0x180027521  mov     r9d, eax; char *
0x180027524  mov     r8, rdi; unsigned int
0x180027527  mov     edx, 421h; void *
0x18002752c  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180027531  mov     r8, [rbx+0D0h]
0x180027538  mov     r8d, [r8+0BCh]; struct _tagpropertykey *
0x18002753f  lea     rdx, PKEY_Blue_Point_Y; struct IPropertyStore *
0x180027546  mov     rcx, [rbp+arg_0]; this
0x18002754a  call    ?IPropertyStore_SetUInt32@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@I@Z; Rdp::Utils::Props::IPropertyStore_SetUInt32(IPropertyStore *,_tagpropertykey const &,uint)
0x18002754f  mov     rcx, [rbp+8]; this
0x180027553  lea     rdx, aFailedToSetPke_13; "Failed to set PKEY_Blue_Point_Y propert"...
0x18002755a  mov     qword ptr [rsp+30h+var_10], rdx; int
0x18002755f  mov     r9d, eax; char *
0x180027562  mov     r8, rdi; unsigned int
0x180027565  mov     edx, 428h; void *
0x18002756a  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18002756f  mov     r8, [rbx+0D0h]
0x180027576  mov     r8d, [r8+0C0h]; struct _tagpropertykey *
0x18002757d  lea     rdx, PKEY_White_Point_X; struct IPropertyStore *
0x180027584  mov     rcx, [rbp+arg_0]; this
0x180027588  call    ?IPropertyStore_SetUInt32@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@I@Z; Rdp::Utils::Props::IPropertyStore_SetUInt32(IPropertyStore *,_tagpropertykey const &,uint)
0x18002758d  mov     rcx, [rbp+8]; this
0x180027591  lea     rdx, aFailedToSetPke_7; "Failed to set PKEY_White_Point_X proper"...
0x180027598  mov     qword ptr [rsp+30h+var_10], rdx; int
0x18002759d  mov     r9d, eax; char *
0x1800275a0  mov     r8, rdi; unsigned int
0x1800275a3  mov     edx, 42Fh; void *
0x1800275a8  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800275ad  mov     r8, [rbx+0D0h]
0x1800275b4  mov     r8d, [r8+0C4h]; struct _tagpropertykey *
0x1800275bb  lea     rdx, PKEY_White_Point_Y; struct IPropertyStore *
0x1800275c2  mov     rcx, [rbp+arg_0]; this
0x1800275c6  call    ?IPropertyStore_SetUInt32@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@I@Z; Rdp::Utils::Props::IPropertyStore_SetUInt32(IPropertyStore *,_tagpropertykey const &,uint)
0x1800275cb  mov     rcx, [rbp+8]; this
0x1800275cf  lea     rdx, aFailedToSetPke_40; "Failed to set PKEY_White_Point_Y proper"...
0x1800275d6  mov     qword ptr [rsp+30h+var_10], rdx; int
0x1800275db  mov     r9d, eax; char *
0x1800275de  mov     r8, rdi; unsigned int
0x1800275e1  mov     edx, 436h; void *
0x1800275e6  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800275eb  mov     r8, [rbx+0D0h]
0x1800275f2  mov     r8d, [r8+0C8h]; struct _tagpropertykey *
0x1800275f9  lea     rdx, PKEY_Min_Luminance; struct IPropertyStore *
0x180027600  mov     rcx, [rbp+arg_0]; this
0x180027604  call    ?IPropertyStore_SetUInt32@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@I@Z; Rdp::Utils::Props::IPropertyStore_SetUInt32(IPropertyStore *,_tagpropertykey const &,uint)
0x180027609  mov     rcx, [rbp+8]; this
0x18002760d  lea     rdx, aFailedToSetPke_33; "Failed to set PKEY_Min_Luminance proper"...
0x180027614  mov     qword ptr [rsp+30h+var_10], rdx; int
0x180027619  mov     r9d, eax; char *
0x18002761c  mov     r8, rdi; unsigned int
0x18002761f  mov     edx, 43Dh; void *
0x180027624  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180027629  mov     r8, [rbx+0D0h]
0x180027630  mov     r8d, [r8+0CCh]; struct _tagpropertykey *
0x180027637  lea     rdx, PKEY_Max_Luminance; struct IPropertyStore *
0x18002763e  mov     rcx, [rbp+arg_0]; this
0x180027642  call    ?IPropertyStore_SetUInt32@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@I@Z; Rdp::Utils::Props::IPropertyStore_SetUInt32(IPropertyStore *,_tagpropertykey const &,uint)
0x180027647  mov     rcx, [rbp+8]; this
0x18002764b  lea     rdx, aFailedToSetPke_14; "Failed to set PKEY_Max_Luminance proper"...
0x180027652  mov     qword ptr [rsp+30h+var_10], rdx; int
0x180027657  mov     r9d, eax; char *
0x18002765a  mov     r8, rdi; unsigned int
0x18002765d  mov     edx, 444h; void *
0x180027662  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180027667  mov     r8, [rbx+0D0h]
0x18002766e  mov     r8d, [r8+0D0h]; struct _tagpropertykey *
0x180027675  lea     rdx, PKEY_Max_Full_Frame_Luminance; struct IPropertyStore *
0x18002767c  mov     rcx, [rbp+arg_0]; this
0x180027680  call    ?IPropertyStore_SetUInt32@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@I@Z; Rdp::Utils::Props::IPropertyStore_SetUInt32(IPropertyStore *,_tagpropertykey const &,uint)
0x180027685  mov     rcx, [rbp+8]; this
0x180027689  lea     rdx, aFailedToSetPke_27; "Failed to set PKEY_Max_Full_Frame_Lumin"...
0x180027690  mov     qword ptr [rsp+30h+var_10], rdx; int
0x180027695  mov     r9d, eax; char *
0x180027698  mov     r8, rdi; unsigned int
0x18002769b  mov     edx, 44Bh; void *
0x1800276a0  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800276a5  xor     r8d, r8d
0x1800276a8  mov     rax, [rbx+0D0h]
0x1800276af  mov     ecx, [rax+0E4h]
0x1800276b5  lea     eax, [r8+1]
0x1800276b9  test    al, cl
0x1800276bb  cmovnz  r8d, eax
0x1800276bf  test    cl, 2
0x1800276c2  jz      short loc_1800276C8
0x1800276c4  or      r8d, 2
0x1800276c8  test    cl, 4
0x1800276cb  jz      short loc_1800276D1
0x1800276cd  or      r8d, 4; struct _tagpropertykey *
0x1800276d1  lea     rdx, PKEY_Colorimetry_Flags; struct IPropertyStore *
0x1800276d8  mov     rcx, [rbp+arg_0]; this
0x1800276dc  call    ?IPropertyStore_SetUInt32@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@I@Z; Rdp::Utils::Props::IPropertyStore_SetUInt32(IPropertyStore *,_tagpropertykey const &,uint)
0x1800276e1  mov     rcx, [rbp+8]; this
0x1800276e5  lea     rdx, aFailedToSetPke_20; "Failed to set PKEY_Colorimetry_Flags pr"...
0x1800276ec  mov     qword ptr [rsp+30h+var_10], rdx; int
0x1800276f1  mov     r9d, eax; char *
0x1800276f4  mov     r8, rdi; unsigned int
0x1800276f7  mov     edx, 452h; void *
0x1800276fc  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180027701  nop
0x180027702  lea     rcx, [rbp+arg_0]
0x180027706  call    ??1?$com_ptr_t@UIColorSpaceTransform@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>::~com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>(void)
0x18002770b  mov     rbx, [rsp+30h+arg_8]
0x180027710  mov     rdi, [rsp+30h+arg_10]
0x180027715  add     rsp, 30h
0x180027719  pop     rbp
0x18002771a  retn
```
