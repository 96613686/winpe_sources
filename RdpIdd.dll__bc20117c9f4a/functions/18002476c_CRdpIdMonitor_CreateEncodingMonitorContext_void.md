# CRdpIdMonitor::CreateEncodingMonitorContext(void)

- ea: `0x18002476c`
- end: `0x180024a22`
- name: `?CreateEncodingMonitorContext@CRdpIdMonitor@@AEAAXXZ`
- size: `694`
- prototype: `void __fastcall(CRdpIdMonitor *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180025180`

## callees

- `0x1800089f0`
- `0x18000ead8`
- `0x1800177fc`
- `0x180017914`
- `0x18001dd50`
- `0x18001ddbc`
- `0x18001ddf4`
- `0x180023a90`
- `0x18002476c`
- `0x18003f010`

## import_xrefs

- `PROPSYS!PSCreateMemoryPropertyStore` at `0x180024792`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x180024792`

## string_xrefs

- `0x180024a10`: `onecore\internal\sdk\inc\wil\opensource/wil/result_macros.h`
- `0x1800247a2`: `Failed to create property store`
- `0x18002491f`: `CreateMonitor failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall CRdpIdMonitor::CreateEncodingMonitorContext(CRdpIdMonitor *this)
{
  unsigned int v2; // eax
  unsigned int v3; // r9d
  unsigned int v4; // eax
  const struct _GUID *v5; // r9
  unsigned int v6; // eax
  unsigned int v7; // r9d
  unsigned int v8; // eax
  unsigned int v9; // r9d
  unsigned int v10; // eax
  unsigned int v11; // r9d
  unsigned int v12; // eax
  __int64 *v13; // rcx
  __int64 v14; // rax
  unsigned int v15; // eax
  int v16; // eax
  __int64 v17; // rax
  __int64 v18; // rcx
  int v19; // edi
  unsigned int v20; // eax
  int v21; // [rsp+20h] [rbp-10h]
  const char *v22; // [rsp+28h] [rbp-8h]
  const char *v23; // [rsp+28h] [rbp-8h]
  const char *v24; // [rsp+28h] [rbp-8h]
  const char *v25; // [rsp+28h] [rbp-8h]
  const char *v26; // [rsp+28h] [rbp-8h]
  const char *v27; // [rsp+28h] [rbp-8h]
  const char *v28; // [rsp+28h] [rbp-8h]
  const char *v29; // [rsp+28h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+18h]
  void *ppv; // [rsp+50h] [rbp+20h] BYREF
  __int64 v32; // [rsp+58h] [rbp+28h] BYREF
  __int64 (__fastcall ***v33)(_QWORD, GUID *, __int64 *); // [rsp+60h] [rbp+30h] BYREF

  ppv = 0;
  v2 = PSCreateMemoryPropertyStore(&GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99, &ppv);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x2D3,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\monitor.cpp",
    (const char *)v2,
    (int)"Failed to create property store",
    v22);
  v4 = Rdp::Utils::Props::IPropertyStore_SetUInt32(
         (Rdp::Utils::Props *)ppv,
         (struct IPropertyStore *)&PKEY_Monitor_Index,
         (const struct _tagpropertykey *)*((unsigned int *)this + 70),
         v3);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x2DA,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\monitor.cpp",
    (const char *)v4,
    (int)"Failed to set PKEY_Monitor_Index property",
    v23);
  v6 = Rdp::Utils::Props::IPropertyStore_SetCLSID(
         (Rdp::Utils::Props *)ppv,
         (struct IPropertyStore *)&PKEY_Monitor_Id,
         (const struct _tagpropertykey *)(*((_QWORD *)this + 26) + 36LL),
         v5);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x2E1,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\monitor.cpp",
    (const char *)v6,
    (int)"Failed to set PKEY_Monitor_Id property",
    v24);
  v8 = Rdp::Utils::Props::IPropertyStore_SetUInt32(
         (Rdp::Utils::Props *)ppv,
         (struct IPropertyStore *)&PKEY_Physical_Width,
         (const struct _tagpropertykey *)*(unsigned int *)(*((_QWORD *)this + 26) + 152LL),
         v7);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x2E8,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\monitor.cpp",
    (const char *)v8,
    (int)"Failed to set PKEY_Physical_Width property",
    v25);
  v10 = Rdp::Utils::Props::IPropertyStore_SetUInt32(
          (Rdp::Utils::Props *)ppv,
          (struct IPropertyStore *)&PKEY_Physical_Height,
          (const struct _tagpropertykey *)*(unsigned int *)(*((_QWORD *)this + 26) + 156LL),
          v9);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x2EF,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\monitor.cpp",
    (const char *)v10,
    (int)"Failed to set PKEY_Physical_Height property",
    v26);
  v12 = Rdp::Utils::Props::IPropertyStore_SetUInt32(
          (Rdp::Utils::Props *)ppv,
          (struct IPropertyStore *)&PKEY_Bytes_Per_Pixel,
          (const struct _tagpropertykey *)4,
          v11);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x2F6,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\monitor.cpp",
    (const char *)v12,
    (int)"Failed to set PKEY_Bytes_Per_Pixel property",
    v27);
  v33 = 0;
  v13 = *(__int64 **)(*((_QWORD *)this + 29) + 560LL);
  v14 = *v13;
  v33 = 0;
  v15 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, void *))(v14 + 56))(v13, &v33, ppv);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x300,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\monitor.cpp",
    (const char *)v15,
    (int)"CreateMonitor failed",
    v28);
  v32 = 0;
  v16 = (**v33)(v33, &GUID_3abc23a0_4a59_4064_b114_d56a60c75c0a, &v32);
  if ( v16 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1CBE,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/result_macros.h",
      (const char *)(unsigned int)v16,
      v21);
  v17 = v32;
  v32 = 0;
  v18 = *((_QWORD *)this + 39);
  *((_QWORD *)this + 39) = v17;
  if ( v18 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
  wil::com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>::~com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>(&v32);
  v19 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 39) + 32LL))(*((_QWORD *)this + 39));
  if ( v19 < 0 )
  {
    wil::com_ptr_t<Rdp::Avenc::IMonitorContext1,wil::err_exception_policy>::operator=((char *)this + 312);
    v20 = wil::verify_hresult<long>((unsigned int)v19);
    wil::details::in1diag3::Throw_HrMsg(
      retaddr,
      (void *)0x30E,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\monitor.cpp",
      (const char *)v20,
      (int)"Failed to start monitor encoding context",
      v29);
  }
  wil::com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>::~com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>(&v33);
  wil::com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>::~com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>(&ppv);
}

```

## disassembly

```asm
0x18002476c  mov     [rsp-18h+arg_18], rbx
0x180024771  push    rbp
0x180024772  push    rdi
0x180024773  push    r14
0x180024775  mov     rbp, rsp
0x180024778  sub     rsp, 30h
0x18002477c  mov     rbx, rcx
0x18002477f  mov     [rbp+ppv], 0
0x180024787  lea     rdx, [rbp+ppv]; ppv
0x18002478b  lea     rcx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99; riid
0x180024792  call    cs:__imp_PSCreateMemoryPropertyStore
0x180024799  nop     dword ptr [rax+rax+00h]
0x18002479e  mov     rcx, [rbp+18h]; this
0x1800247a2  lea     rdx, aFailedToCreate_8; "Failed to create property store"
0x1800247a9  mov     qword ptr [rsp+30h+var_10], rdx; int
0x1800247ae  mov     r9d, eax; char *
0x1800247b1  lea     r14, aOnecoreuapTerm_12; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x1800247b8  mov     r8, r14; unsigned int
0x1800247bb  mov     edx, 2D3h; void *
0x1800247c0  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800247c5  mov     r8d, [rbx+118h]; struct _tagpropertykey *
0x1800247cc  lea     rdx, PKEY_Monitor_Index; struct IPropertyStore *
0x1800247d3  mov     rcx, [rbp+ppv]; this
0x1800247d7  call    ?IPropertyStore_SetUInt32@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@I@Z; Rdp::Utils::Props::IPropertyStore_SetUInt32(IPropertyStore *,_tagpropertykey const &,uint)
0x1800247dc  mov     rcx, [rbp+18h]; this
0x1800247e0  lea     rdx, aFailedToSetPke_2; "Failed to set PKEY_Monitor_Index proper"...
0x1800247e7  mov     qword ptr [rsp+30h+var_10], rdx; int
0x1800247ec  mov     r9d, eax; char *
0x1800247ef  mov     r8, r14; unsigned int
0x1800247f2  mov     edx, 2DAh; void *
0x1800247f7  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800247fc  mov     r8, [rbx+0D0h]
0x180024803  add     r8, 24h ; '$'; struct _tagpropertykey *
0x180024807  lea     rdx, PKEY_Monitor_Id; struct IPropertyStore *
0x18002480e  mov     rcx, [rbp+ppv]; this
0x180024812  call    ?IPropertyStore_SetCLSID@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@AEBU_GUID@@@Z; Rdp::Utils::Props::IPropertyStore_SetCLSID(IPropertyStore *,_tagpropertykey const &,_GUID const &)
0x180024817  mov     rcx, [rbp+18h]; this
0x18002481b  lea     rdx, aFailedToSetPke_11; "Failed to set PKEY_Monitor_Id property"
0x180024822  mov     qword ptr [rsp+30h+var_10], rdx; int
0x180024827  mov     r9d, eax; char *
0x18002482a  mov     r8, r14; unsigned int
0x18002482d  mov     edx, 2E1h; void *
0x180024832  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180024837  mov     r8, [rbx+0D0h]
0x18002483e  mov     r8d, [r8+98h]; struct _tagpropertykey *
0x180024845  lea     rdx, PKEY_Physical_Width; struct IPropertyStore *
0x18002484c  mov     rcx, [rbp+ppv]; this
0x180024850  call    ?IPropertyStore_SetUInt32@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@I@Z; Rdp::Utils::Props::IPropertyStore_SetUInt32(IPropertyStore *,_tagpropertykey const &,uint)
0x180024855  mov     rcx, [rbp+18h]; this
0x180024859  lea     rdx, aFailedToSetPke_39; "Failed to set PKEY_Physical_Width prope"...
0x180024860  mov     qword ptr [rsp+30h+var_10], rdx; int
0x180024865  mov     r9d, eax; char *
0x180024868  mov     r8, r14; unsigned int
0x18002486b  mov     edx, 2E8h; void *
0x180024870  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180024875  mov     r8, [rbx+0D0h]
0x18002487c  mov     r8d, [r8+9Ch]; struct _tagpropertykey *
0x180024883  lea     rdx, PKEY_Physical_Height; struct IPropertyStore *
0x18002488a  mov     rcx, [rbp+ppv]; this
0x18002488e  call    ?IPropertyStore_SetUInt32@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@I@Z; Rdp::Utils::Props::IPropertyStore_SetUInt32(IPropertyStore *,_tagpropertykey const &,uint)
0x180024893  mov     rcx, [rbp+18h]; this
0x180024897  lea     rdx, aFailedToSetPke_29; "Failed to set PKEY_Physical_Height prop"...
0x18002489e  mov     qword ptr [rsp+30h+var_10], rdx; int
0x1800248a3  mov     r9d, eax; char *
0x1800248a6  mov     r8, r14; unsigned int
0x1800248a9  mov     edx, 2EFh; void *
0x1800248ae  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800248b3  mov     r8d, 4; struct _tagpropertykey *
0x1800248b9  lea     rdx, PKEY_Bytes_Per_Pixel; struct IPropertyStore *
0x1800248c0  mov     rcx, [rbp+ppv]; this
0x1800248c4  call    ?IPropertyStore_SetUInt32@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@I@Z; Rdp::Utils::Props::IPropertyStore_SetUInt32(IPropertyStore *,_tagpropertykey const &,uint)
0x1800248c9  mov     rcx, [rbp+18h]; this
0x1800248cd  lea     rdx, aFailedToSetPke_16; "Failed to set PKEY_Bytes_Per_Pixel prop"...
0x1800248d4  mov     qword ptr [rsp+30h+var_10], rdx; int
0x1800248d9  mov     r9d, eax; char *
0x1800248dc  mov     r8, r14; unsigned int
0x1800248df  mov     edx, 2F6h; void *
0x1800248e4  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800248e9  mov     [rbp+arg_10], 0
0x1800248f1  mov     rax, [rbx+0E8h]
0x1800248f8  mov     rcx, [rax+230h]
0x1800248ff  mov     rax, [rcx]
0x180024902  mov     [rbp+arg_10], 0
0x18002490a  mov     r8, [rbp+ppv]
0x18002490e  lea     rdx, [rbp+arg_10]
0x180024912  mov     rax, [rax+38h]
0x180024916  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002491b  mov     rcx, [rbp+18h]; this
0x18002491f  lea     rdx, aCreatemonitorF; "CreateMonitor failed"
0x180024926  mov     qword ptr [rsp+30h+var_10], rdx; int
0x18002492b  mov     r9d, eax; char *
0x18002492e  mov     r8, r14; unsigned int
0x180024931  mov     edx, 300h; void *
0x180024936  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18002493b  mov     rcx, [rbp+arg_10]
0x18002493f  mov     [rbp+arg_8], 0
0x180024947  mov     rax, [rcx]
0x18002494a  lea     r8, [rbp+arg_8]
0x18002494e  lea     rdx, _GUID_3abc23a0_4a59_4064_b114_d56a60c75c0a
0x180024955  mov     rax, [rax]
0x180024958  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002495d  mov     rcx, [rbp+18h]; this
0x180024961  test    eax, eax
0x180024963  js      loc_180024A0D
0x180024969  mov     rax, [rbp+arg_8]
0x18002496d  mov     [rbp+arg_8], 0
0x180024975  mov     rcx, [rbx+138h]
0x18002497c  mov     [rbx+138h], rax
0x180024983  test    rcx, rcx
0x180024986  jz      short loc_180024995
0x180024988  mov     rax, [rcx]
0x18002498b  mov     rax, [rax+10h]
0x18002498f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024994  nop
0x180024995  lea     rcx, [rbp+arg_8]
0x180024999  call    ??1?$com_ptr_t@UIColorSpaceTransform@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>::~com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>(void)
0x18002499e  mov     rcx, [rbx+138h]
0x1800249a5  mov     rax, [rcx]
0x1800249a8  mov     rax, [rax+20h]
0x1800249ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800249b1  mov     edi, eax
0x1800249b3  test    eax, eax
0x1800249b5  js      short loc_1800249D9
0x1800249b7  lea     rcx, [rbp+arg_10]
0x1800249bb  call    ??1?$com_ptr_t@UIColorSpaceTransform@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>::~com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>(void)
0x1800249c0  nop
0x1800249c1  lea     rcx, [rbp+ppv]
0x1800249c5  call    ??1?$com_ptr_t@UIColorSpaceTransform@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>::~com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>(void)
0x1800249ca  mov     rbx, [rsp+30h+arg_18]
0x1800249cf  add     rsp, 30h
0x1800249d3  pop     r14
0x1800249d5  pop     rdi
0x1800249d6  pop     rbp
0x1800249d7  retn
0x1800249d9  lea     rcx, [rbx+138h]
0x1800249e0  call    ??4?$com_ptr_t@UIMonitorContext1@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@QEAAAEAV01@$$T@Z; wil::com_ptr_t<Rdp::Avenc::IMonitorContext1,wil::err_exception_policy>::operator=(std::nullptr_t)
0x1800249e5  mov     ecx, edi
0x1800249e7  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x1800249ec  mov     r9d, eax; char *
0x1800249ef  mov     rcx, [rbp+18h]; this
0x1800249f3  lea     rax, aFailedToStartM; "Failed to start monitor encoding contex"...
0x1800249fa  mov     qword ptr [rsp+30h+var_10], rax; int
0x1800249ff  mov     r8, r14; unsigned int
0x180024a02  mov     edx, 30Eh; void *
0x180024a07  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
0x180024a0d  mov     r9d, eax; char *
0x180024a10  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180024a17  mov     edx, 1CBEh; void *
0x180024a1c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
