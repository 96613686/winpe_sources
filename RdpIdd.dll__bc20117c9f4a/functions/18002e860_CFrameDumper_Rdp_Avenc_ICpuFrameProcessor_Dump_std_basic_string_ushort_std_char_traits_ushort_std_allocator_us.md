# CFrameDumper<Rdp::Avenc::ICpuFrameProcessor>::Dump(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::function<void (IWICBitmapFrameEncode *)>)

- ea: `0x18002e860`
- end: `0x18002eac8`
- name: `?Dump@?$CFrameDumper@UICpuFrameProcessor@Avenc@Rdp@@@@IEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$function@$$A6AXPEAUIWICBitmapFrameEncode@@@Z@3@@Z`
- size: `616`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002ee40`
- `0x18002f0b0`

## callees

- `0x18000ead8`
- `0x18001ddf4`
- `0x180020d00`
- `0x18002e7a4`
- `0x18002e860`
- `0x18003f010`

## string_xrefs

- `0x18002e8a3`: `Failed to create file stream`
- `0x18002e93f`: `CreateEncoder failed`
- `0x18002e9c0`: `wicBitmapEncoder->CreateNewFrame failed`
- `0x18002ea2e`: `wicFrameEncode->Commit failed`
- `0x18002ea5e`: `wicBitmapEncoder->Commit failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CFrameDumper<Rdp::Avenc::ICpuFrameProcessor>::Dump(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 *v6; // rcx
  __int64 v7; // rax
  unsigned int v8; // eax
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // rax
  __int64 v12; // r10
  unsigned int v13; // eax
  __int64 *v14; // rcx
  __int64 v15; // rax
  unsigned int v16; // eax
  unsigned int v17; // eax
  __int64 v18; // rax
  unsigned int v19; // eax
  unsigned int v20; // eax
  unsigned int v21; // eax
  unsigned int v22; // eax
  __int64 result; // rax
  __int64 v24; // rdx
  __int64 v25; // rcx
  const char *v26; // [rsp+28h] [rbp-8h]
  const char *v27; // [rsp+28h] [rbp-8h]
  const char *v28; // [rsp+28h] [rbp-8h]
  const char *v29; // [rsp+28h] [rbp-8h]
  const char *v30; // [rsp+28h] [rbp-8h]
  const char *v31; // [rsp+28h] [rbp-8h]
  const char *v32; // [rsp+28h] [rbp-8h]
  const char *v33; // [rsp+28h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+28h]
  __int64 v35; // [rsp+60h] [rbp+30h] BYREF
  __int64 *v36; // [rsp+68h] [rbp+38h] BYREF
  __int64 v37; // [rsp+70h] [rbp+40h]
  __int64 v38; // [rsp+78h] [rbp+48h] BYREF

  v37 = a3;
  v38 = 0;
  v6 = *(__int64 **)(a1 + 24);
  v7 = *v6;
  v38 = 0;
  v8 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v7 + 112))(v6, &v38);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x60,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\framebuffer.cpp",
    (const char *)v8,
    (int)"Failed to create file stream",
    v26);
  v11 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2, v9, v10);
  v13 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v12 + 120LL))(v12, v11, 0x40000000);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x63,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\framebuffer.cpp",
    (const char *)v13,
    (int)"Failed to intialize frame dump file stream",
    v27);
  v36 = 0;
  v14 = *(__int64 **)(a1 + 24);
  v15 = *v14;
  v36 = 0;
  v16 = (*(__int64 (__fastcall **)(__int64 *, GUID *, _QWORD, __int64 **))(v15 + 64))(
          v14,
          &GUID_ContainerFormatJpeg,
          0,
          &v36);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x6E,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\framebuffer.cpp",
    (const char *)v16,
    (int)"CreateEncoder failed",
    v28);
  v17 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64))(*v36 + 24))(v36, v38, 2);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x74,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\framebuffer.cpp",
    (const char *)v17,
    (int)"wicBitmapEncoder->Initialize failed",
    v29);
  v35 = 0;
  v18 = *v36;
  v35 = 0;
  v19 = (*(__int64 (__fastcall **)(__int64 *, __int64 *, _QWORD))(v18 + 80))(v36, &v35, 0);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x7E,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\framebuffer.cpp",
    (const char *)v19,
    (int)"wicBitmapEncoder->CreateNewFrame failed",
    v30);
  v20 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v35 + 24LL))(v35, 0);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x81,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\framebuffer.cpp",
    (const char *)v20,
    (int)"wicFrameEncode->Initialize failed",
    v31);
  std::_Func_class<void,IWICBitmapFrameEncode *>::operator()(a3, v35);
  v21 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v35 + 96LL))(v35);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x8C,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\framebuffer.cpp",
    (const char *)v21,
    (int)"wicFrameEncode->Commit failed",
    v32);
  v22 = (*(__int64 (__fastcall **)(__int64 *))(*v36 + 88))(v36);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x8F,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\framebuffer.cpp",
    (const char *)v22,
    (int)"wicBitmapEncoder->Commit failed",
    v33);
  wil::com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>::~com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>(&v35);
  wil::com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>::~com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>(&v36);
  result = wil::com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>::~com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>(&v38);
  v25 = *(_QWORD *)(a3 + 56);
  if ( v25 )
  {
    LOBYTE(v24) = v25 != a3;
    result = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v25 + 32LL))(v25, v24);
    *(_QWORD *)(a3 + 56) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x18002e860  mov     [rsp-28h+arg_10], r8
0x18002e865  push    rbp
0x18002e866  push    rbx
0x18002e867  push    rsi
0x18002e868  push    rdi
0x18002e869  push    r14
0x18002e86b  mov     rbp, rsp
0x18002e86e  sub     rsp, 30h
0x18002e872  mov     rsi, r8
0x18002e875  mov     rbx, rdx
0x18002e878  mov     rdi, rcx
0x18002e87b  mov     [rbp+arg_18], 0
0x18002e883  mov     rcx, [rcx+18h]
0x18002e887  mov     rax, [rcx]
0x18002e88a  mov     [rbp+arg_18], 0
0x18002e892  lea     rdx, [rbp+arg_18]
0x18002e896  mov     rax, [rax+70h]
0x18002e89a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e89f  mov     rcx, [rbp+28h]; this
0x18002e8a3  lea     rdx, aFailedToCreate_10; "Failed to create file stream"
0x18002e8aa  mov     qword ptr [rsp+30h+var_10], rdx; int
0x18002e8af  mov     r9d, eax; char *
0x18002e8b2  lea     r14, aOnecoreuapTerm_17; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x18002e8b9  mov     r8, r14; unsigned int
0x18002e8bc  mov     edx, 60h ; '`'; void *
0x18002e8c1  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18002e8c6  mov     r10, [rbp+arg_18]
0x18002e8ca  mov     rcx, rbx
0x18002e8cd  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002e8d2  mov     rdx, [r10]
0x18002e8d5  mov     r9, [rdx+78h]
0x18002e8d9  mov     r8d, 40000000h
0x18002e8df  mov     rdx, rax
0x18002e8e2  mov     rcx, r10
0x18002e8e5  mov     rax, r9
0x18002e8e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e8ed  mov     rcx, [rbp+28h]; this
0x18002e8f1  lea     rdx, aFailedToIntial; "Failed to intialize frame dump file str"...
0x18002e8f8  mov     qword ptr [rsp+30h+var_10], rdx; int
0x18002e8fd  mov     r9d, eax; char *
0x18002e900  mov     r8, r14; unsigned int
0x18002e903  mov     edx, 63h ; 'c'; void *
0x18002e908  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18002e90d  mov     [rbp+arg_8], 0
0x18002e915  mov     rcx, [rdi+18h]
0x18002e919  mov     rax, [rcx]
0x18002e91c  mov     [rbp+arg_8], 0
0x18002e924  lea     r9, [rbp+arg_8]
0x18002e928  xor     r8d, r8d
0x18002e92b  lea     rdx, GUID_ContainerFormatJpeg
0x18002e932  mov     rax, [rax+40h]
0x18002e936  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e93b  mov     rcx, [rbp+28h]; this
0x18002e93f  lea     rdx, aCreateencoderF; "CreateEncoder failed"
0x18002e946  mov     qword ptr [rsp+30h+var_10], rdx; int
0x18002e94b  mov     r9d, eax; char *
0x18002e94e  mov     r8, r14; unsigned int
0x18002e951  mov     edx, 6Eh ; 'n'; void *
0x18002e956  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18002e95b  mov     rcx, [rbp+arg_8]
0x18002e95f  mov     rax, [rcx]
0x18002e962  mov     r8d, 2
0x18002e968  mov     rdx, [rbp+arg_18]
0x18002e96c  mov     rax, [rax+18h]
0x18002e970  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e975  mov     rcx, [rbp+28h]; this
0x18002e979  lea     rdx, aWicbitmapencod_1; "wicBitmapEncoder->Initialize failed"
0x18002e980  mov     qword ptr [rsp+30h+var_10], rdx; int
0x18002e985  mov     r9d, eax; char *
0x18002e988  mov     r8, r14; unsigned int
0x18002e98b  mov     edx, 74h ; 't'; void *
0x18002e990  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18002e995  mov     [rbp+arg_0], 0
0x18002e99d  mov     rcx, [rbp+arg_8]
0x18002e9a1  mov     rax, [rcx]
0x18002e9a4  mov     [rbp+arg_0], 0
0x18002e9ac  xor     r8d, r8d
0x18002e9af  lea     rdx, [rbp+arg_0]
0x18002e9b3  mov     rax, [rax+50h]
0x18002e9b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e9bc  mov     rcx, [rbp+28h]; this
0x18002e9c0  lea     rdx, aWicbitmapencod_0; "wicBitmapEncoder->CreateNewFrame failed"
0x18002e9c7  mov     qword ptr [rsp+30h+var_10], rdx; int
0x18002e9cc  mov     r9d, eax; char *
0x18002e9cf  mov     r8, r14; unsigned int
0x18002e9d2  mov     edx, 7Eh ; '~'; void *
0x18002e9d7  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18002e9dc  mov     rcx, [rbp+arg_0]
0x18002e9e0  mov     rax, [rcx]
0x18002e9e3  xor     edx, edx
0x18002e9e5  mov     rax, [rax+18h]
0x18002e9e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e9ee  mov     rcx, [rbp+28h]; this
0x18002e9f2  lea     rdx, aWicframeencode_1; "wicFrameEncode->Initialize failed"
0x18002e9f9  mov     qword ptr [rsp+30h+var_10], rdx; int
0x18002e9fe  mov     r9d, eax; char *
0x18002ea01  mov     r8, r14; unsigned int
0x18002ea04  mov     edx, 81h; void *
0x18002ea09  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18002ea0e  mov     rdx, [rbp+arg_0]
0x18002ea12  mov     rcx, rsi
0x18002ea15  call    ??R?$_Func_class@XPEAUIWICBitmapFrameEncode@@@std@@QEBAXPEAUIWICBitmapFrameEncode@@@Z; std::_Func_class<void,IWICBitmapFrameEncode *>::operator()(IWICBitmapFrameEncode *)
0x18002ea1a  mov     rcx, [rbp+arg_0]
0x18002ea1e  mov     rax, [rcx]
0x18002ea21  mov     rax, [rax+60h]
0x18002ea25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ea2a  mov     rcx, [rbp+28h]; this
0x18002ea2e  lea     rdx, aWicframeencode; "wicFrameEncode->Commit failed"
0x18002ea35  mov     qword ptr [rsp+30h+var_10], rdx; int
0x18002ea3a  mov     r9d, eax; char *
0x18002ea3d  mov     r8, r14; unsigned int
0x18002ea40  mov     edx, 8Ch; void *
0x18002ea45  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18002ea4a  mov     rcx, [rbp+arg_8]
0x18002ea4e  mov     rax, [rcx]
0x18002ea51  mov     rax, [rax+58h]
0x18002ea55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ea5a  mov     rcx, [rbp+28h]; this
0x18002ea5e  lea     rdx, aWicbitmapencod; "wicBitmapEncoder->Commit failed"
0x18002ea65  mov     qword ptr [rsp+30h+var_10], rdx; int
0x18002ea6a  mov     r9d, eax; char *
0x18002ea6d  mov     r8, r14; unsigned int
0x18002ea70  mov     edx, 8Fh; void *
0x18002ea75  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18002ea7a  nop
0x18002ea7b  lea     rcx, [rbp+arg_0]
0x18002ea7f  call    ??1?$com_ptr_t@UIColorSpaceTransform@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>::~com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>(void)
0x18002ea84  nop
0x18002ea85  lea     rcx, [rbp+arg_8]
0x18002ea89  call    ??1?$com_ptr_t@UIColorSpaceTransform@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>::~com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>(void)
0x18002ea8e  nop
0x18002ea8f  lea     rcx, [rbp+arg_18]
0x18002ea93  call    ??1?$com_ptr_t@UIColorSpaceTransform@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>::~com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>(void)
0x18002ea98  nop
0x18002ea99  mov     rcx, [rsi+38h]
0x18002ea9d  test    rcx, rcx
0x18002eaa0  jz      short loc_18002EABC
0x18002eaa2  mov     rax, [rcx]
0x18002eaa5  cmp     rcx, rsi
0x18002eaa8  setnz   dl
0x18002eaab  mov     rax, [rax+20h]
0x18002eaaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002eab4  mov     qword ptr [rsi+38h], 0
0x18002eabc  add     rsp, 30h
0x18002eac0  pop     r14
0x18002eac2  pop     rdi
0x18002eac3  pop     rsi
0x18002eac4  pop     rbx
0x18002eac5  pop     rbp
0x18002eac6  retn
```
