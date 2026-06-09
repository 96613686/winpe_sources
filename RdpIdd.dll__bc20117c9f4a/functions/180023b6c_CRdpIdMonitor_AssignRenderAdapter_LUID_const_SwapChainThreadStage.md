# CRdpIdMonitor::AssignRenderAdapter(_LUID const &,SwapChainThreadStage &)

- ea: `0x180023b6c`
- end: `0x180024364`
- name: `?AssignRenderAdapter@CRdpIdMonitor@@QEAAXAEBU_LUID@@AEAW4SwapChainThreadStage@@@Z`
- size: `2040`
- prototype: `void __fastcall(CRdpIdMonitor *__hidden this, const struct _LUID *, enum SwapChainThreadStage *)`
- caller_count: `1`
- callee_count: `22`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002badc`

## callees

- `0x180001bc4`
- `0x180004588`
- `0x1800046c4`
- `0x180006f84`
- `0x18000d614`
- `0x18000ead8`
- `0x18001072c`
- `0x180014c40`
- `0x180017ac8`
- `0x18001ddf4`
- `0x180021750`
- `0x180021830`
- `0x180022f50`
- `0x180022f84`
- `0x180023308`
- `0x180023a40`
- `0x180023b6c`
- `0x180024a28`
- `0x1800280e0`
- `0x18002da80`
- `0x18002e41c`
- `0x18003f010`

## string_xrefs

- `0x180023ebe`: `Failed to create Warp frame processor`
- `0x180023f18`: `Create Cpu frame dumper processor`
- `0x1800240bd`: `Failed to create Gpu frame processor`
- `0x180024117`: `Create Gpu frame dumper processor`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
void __fastcall CRdpIdMonitor::AssignRenderAdapter(
        CRdpIdMonitor *this,
        const struct _LUID *a2,
        enum SwapChainThreadStage *a3)
{
  enum SwapChainThreadStage *v3; // r12
  char **v6; // r15
  __int64 v7; // rcx
  _DWORD *v8; // r8
  int v9; // r9d
  __int64 v10; // rax
  char v11; // di
  char v12; // bl
  _DWORD *v13; // r8
  int v14; // r9d
  __int64 v15; // rax
  char *v16; // rbx
  __int64 v17; // rcx
  unsigned int v18; // eax
  _DWORD *v19; // r8
  int v20; // r9d
  __int64 *v21; // rcx
  __int64 v22; // rax
  unsigned int v23; // eax
  _DWORD *v24; // r8
  int v25; // r9d
  _QWORD *v26; // rdi
  __int64 v27; // rbx
  __int64 v28; // rax
  _DWORD *v29; // r8
  int v30; // r9d
  char *v31; // r12
  __int64 *v32; // rcx
  __int64 v33; // rax
  unsigned int v34; // eax
  _DWORD *v35; // r8
  int v36; // r9d
  _QWORD *v37; // rdi
  __int64 v38; // rbx
  __int64 v39; // rax
  __int64 v40; // rax
  const char *v41; // rdx
  unsigned int v42; // eax
  __int64 *v43; // rax
  __int64 v44; // rcx
  __int64 v45; // rdx
  std::_Ref_count_base *v46; // rcx
  _DWORD *v47; // r8
  int v48; // r9d
  unsigned int v49; // eax
  char *v50; // [rsp+28h] [rbp-51h]
  char *v51; // [rsp+28h] [rbp-51h]
  char v52[4]; // [rsp+60h] [rbp-19h] BYREF
  const char *v53; // [rsp+68h] [rbp-11h] BYREF
  char *v54; // [rsp+70h] [rbp-9h] BYREF
  const char *v55; // [rsp+78h] [rbp-1h] BYREF
  const char *v56; // [rsp+80h] [rbp+7h] BYREF
  const char *v57; // [rsp+88h] [rbp+Fh] BYREF
  const char *v58; // [rsp+90h] [rbp+17h] BYREF
  std::_Ref_count_base *v59; // [rsp+98h] [rbp+1Fh]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]
  int v61; // [rsp+E0h] [rbp+67h] BYREF
  enum SwapChainThreadStage *v62; // [rsp+F0h] [rbp+77h]
  _QWORD *v63; // [rsp+F8h] [rbp+7Fh] BYREF

  v62 = a3;
  v3 = a3;
  v61 = 0;
  v54 = 0;
  v6 = (char **)((char *)this + 256);
  v7 = *((_QWORD *)this + 32);
  if ( !v7 )
  {
    v13 = *(_DWORD **)(wil::details::static_lazy<RdpIddLoggingProvider>::get() + 8);
    if ( *v13 > 4u )
    {
      v58 = (const char *)*a2;
      v61 = *(_DWORD *)(*((_QWORD *)this + 29) + 516LL);
      LODWORD(v63) = *((_DWORD *)this + 70);
      v57 = "Creating render adapter";
      v56 = "CRdpIdMonitor::AssignRenderAdapter";
      *(_DWORD *)v52 = 454;
      v55 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\monitor.cpp";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        (_DWORD)v13,
        (unsigned int)byte_18004EC9D,
        (_DWORD)v13,
        v14,
        (__int64)&v55,
        (__int64)v52,
        (__int64)&v56,
        (__int64)&v57,
        (__int64)&v63,
        (__int64)&v61,
        (__int64)&v58);
    }
    *(_DWORD *)v3 = 2;
    v15 = std::make_unique<Rdp::Utils::Graphics::CRenderAdapter,_LUID const &,0>(&v61, a2);
    std::unique_ptr<Rdp::Utils::Graphics::CRenderAdapter>::operator=<std::default_delete<Rdp::Utils::Graphics::CRenderAdapter>,0>(
      v6,
      v15);
    std::unique_ptr<Rdp::Utils::Graphics::CRenderAdapter>::~unique_ptr<Rdp::Utils::Graphics::CRenderAdapter>(&v61);
LABEL_11:
    *(_DWORD *)v3 = 8;
    v16 = (char *)this + 304;
    v17 = *((_QWORD *)this + 38);
    if ( v17 )
    {
      v18 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v17 + 40LL))(v17);
      wil::details::in1diag3::Log_IfFailedMsg(
        retaddr,
        (void *)0x1DB,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\monitor.cpp",
        (const char *)v18,
        (int)"Failed to stop frame processor",
        v50);
      wil::com_ptr_t<Rdp::Avenc::IFileIoChannelEvents,wil::err_exception_policy>::reset((char *)this + 304);
      v16 = (char *)this + 304;
    }
    if ( **v6 )
    {
      v19 = *(_DWORD **)(wil::details::static_lazy<RdpIddLoggingProvider>::get() + 8);
      if ( *v19 > 4u )
      {
        v61 = *(_DWORD *)(*((_QWORD *)this + 29) + 516LL);
        LODWORD(v63) = *((_DWORD *)this + 70);
        v58 = "Creating Cpu frame encoding processor";
        v57 = "CRdpIdMonitor::AssignRenderAdapter";
        *(_DWORD *)v52 = 486;
        v56 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\monitor.cpp";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          (_DWORD)v19,
          (unsigned int)&byte_18004EC4F,
          (_DWORD)v19,
          v20,
          (__int64)&v56,
          (__int64)v52,
          (__int64)&v57,
          (__int64)&v58,
          (__int64)&v63,
          (__int64)&v61);
      }
      v53 = 0;
      v21 = (__int64 *)*((_QWORD *)this + 39);
      v22 = *v21;
      v53 = 0;
      v23 = (*(__int64 (__fastcall **)(__int64 *, const char **, _QWORD))(v22 + 56))(v21, &v53, 0);
      wil::details::in1diag3::Throw_IfFailedMsg(
        retaddr,
        (void *)0x1E9,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\monitor.cpp",
        (const char *)v23,
        (int)"Failed to create Warp frame processor",
        v50);
      if ( *(_BYTE *)(*((_QWORD *)this + 29) + 504LL) )
      {
        v24 = *(_DWORD **)(wil::details::static_lazy<RdpIddLoggingProvider>::get() + 8);
        if ( *v24 > 4u )
        {
          v61 = *(_DWORD *)(*((_QWORD *)this + 29) + 516LL);
          LODWORD(v63) = *((_DWORD *)this + 70);
          v58 = "Create Cpu frame dumper processor";
          v57 = "CRdpIdMonitor::AssignRenderAdapter";
          *(_DWORD *)v52 = 499;
          v56 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\monitor.cpp";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            (_DWORD)v24,
            (unsigned int)byte_18004EC01,
            (_DWORD)v24,
            v25,
            (__int64)&v56,
            (__int64)v52,
            (__int64)&v57,
            (__int64)&v58,
            (__int64)&v63,
            (__int64)&v61);
        }
        v26 = operator new(0x60u);
        v63 = v26;
        v27 = (__int64)v53;
        v28 = std::enable_shared_from_this<CRdpIdAdapter>::shared_from_this(this, &v58);
        v61 = 1;
        CFrameDumper<Rdp::Avenc::ICpuFrameProcessor>::CFrameDumper<Rdp::Avenc::ICpuFrameProcessor>(
          (__int64)v26,
          v28,
          v27);
        *v26 = &CCpuFrameDumper::`vftable'{for `winrt::impl::producers_base<CFrameDumper<Rdp::Avenc::ICpuFrameProcessor>,std::tuple<Rdp::Avenc::ICpuFrameProcessor>>'};
        v26[1] = &CCpuFrameDumper::`vftable'{for `winrt::impl::root_implements<CFrameDumper<Rdp::Avenc::ICpuFrameProcessor>,Rdp::Avenc::ICpuFrameProcessor>'};
        wil::com_ptr_t<Rdp::Avenc::IFrameProcessor,wil::err_exception_policy>::operator=((char *)this + 304, v26);
        if ( v59 )
          std::_Ref_count_base::_Decref(v59);
      }
      else
      {
        wil::com_ptr_t<Rdp::Avenc::IFrameProcessor,wil::err_exception_policy>::operator=<Rdp::Avenc::ICpuFrameProcessor,wil::err_exception_policy,void>(
          v16,
          &v53);
      }
      wil::com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>::~com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>(&v53);
    }
    else
    {
      v29 = *(_DWORD **)(wil::details::static_lazy<RdpIddLoggingProvider>::get() + 8);
      if ( *v29 <= 4u )
      {
        v31 = v16;
      }
      else
      {
        v61 = *(_DWORD *)(*((_QWORD *)this + 29) + 516LL);
        LODWORD(v63) = *((_DWORD *)this + 70);
        v58 = "Creating Gpu frame encoding processor";
        v57 = "CRdpIdMonitor::AssignRenderAdapter";
        *(_DWORD *)v52 = 518;
        v56 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\monitor.cpp";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          (_DWORD)v29,
          (unsigned int)byte_18004EBB3,
          (_DWORD)v29,
          v30,
          (__int64)&v56,
          (__int64)v52,
          (__int64)&v57,
          (__int64)&v58,
          (__int64)&v63,
          (__int64)&v61);
        v31 = (char *)this + 304;
      }
      v53 = 0;
      v32 = (__int64 *)*((_QWORD *)this + 39);
      v33 = *v32;
      v53 = 0;
      v34 = (*(__int64 (__fastcall **)(__int64 *, const char **, _QWORD))(v33 + 48))(v32, &v53, 0);
      wil::details::in1diag3::Throw_IfFailedMsg(
        retaddr,
        (void *)0x209,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\monitor.cpp",
        (const char *)v34,
        (int)"Failed to create Gpu frame processor",
        v50);
      if ( *(_BYTE *)(*((_QWORD *)this + 29) + 504LL) )
      {
        v35 = *(_DWORD **)(wil::details::static_lazy<RdpIddLoggingProvider>::get() + 8);
        if ( *v35 <= 4u )
        {
          v31 = v16;
        }
        else
        {
          v61 = *(_DWORD *)(*((_QWORD *)this + 29) + 516LL);
          LODWORD(v63) = *((_DWORD *)this + 70);
          v58 = "Create Gpu frame dumper processor";
          v57 = "CRdpIdMonitor::AssignRenderAdapter";
          *(_DWORD *)v52 = 531;
          v56 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\monitor.cpp";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            (_DWORD)v35,
            (unsigned int)byte_18004EB65,
            (_DWORD)v35,
            v36,
            (__int64)&v56,
            (__int64)v52,
            (__int64)&v57,
            (__int64)&v58,
            (__int64)&v63,
            (__int64)&v61);
        }
        v37 = operator new(0x90u);
        v63 = v37;
        v38 = (__int64)v53;
        v39 = std::enable_shared_from_this<CRdpIdAdapter>::shared_from_this(this, &v58);
        v61 = 2;
        v40 = CGpuFrameDumper::CGpuFrameDumper((__int64)v37, v39, v38);
        wil::com_ptr_t<Rdp::Avenc::IFrameProcessor,wil::err_exception_policy>::operator=(v31, v40);
        if ( v59 )
          std::_Ref_count_base::_Decref(v59);
      }
      else
      {
        v41 = v53;
        v53 = 0;
        wil::com_ptr_t<Rdp::Avenc::IFrameProcessor,wil::err_exception_policy>::attach(v31, v41);
      }
      wil::com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>::~com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>(&v53);
      v3 = v62;
    }
    v42 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 38) + 32LL))(*((_QWORD *)this + 38));
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0x224,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\monitor.cpp",
      (const char *)v42,
      (int)"Failed to start frame processor",
      v51);
    goto LABEL_35;
  }
  if ( *(_DWORD *)(v7 + 304) == a2->LowPart && *(_DWORD *)(v7 + 308) == a2->HighPart )
    goto LABEL_42;
  v8 = *(_DWORD **)(wil::details::static_lazy<RdpIddLoggingProvider>::get() + 8);
  if ( *v8 > 4u )
  {
    v53 = (const char *)*a2;
    v55 = (const char *)*((_QWORD *)*v6 + 38);
    v61 = *(_DWORD *)(*((_QWORD *)this + 29) + 516LL);
    LODWORD(v63) = *((_DWORD *)this + 70);
    v56 = "Re-creating render adapter";
    v57 = "CRdpIdMonitor::AssignRenderAdapter";
    *(_DWORD *)v52 = 424;
    v58 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\monitor.cpp";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
      (_DWORD)v8,
      (unsigned int)qword_18004ECF8,
      (_DWORD)v8,
      v9,
      (__int64)&v58,
      (__int64)v52,
      (__int64)&v57,
      (__int64)&v56,
      (__int64)&v63,
      (__int64)&v61,
      (__int64)&v55,
      (__int64)&v53);
  }
  *(_DWORD *)v3 = 2;
  v10 = std::make_unique<Rdp::Utils::Graphics::CRenderAdapter,_LUID const &,0>(&v61, a2);
  std::unique_ptr<Rdp::Utils::Graphics::CRenderAdapter>::operator=<std::default_delete<Rdp::Utils::Graphics::CRenderAdapter>,0>(
    &v54,
    v10);
  std::unique_ptr<Rdp::Utils::Graphics::CRenderAdapter>::~unique_ptr<Rdp::Utils::Graphics::CRenderAdapter>(&v61);
  v11 = *v54;
  v12 = **v6;
  std::unique_ptr<Rdp::Utils::Graphics::CRenderAdapter>::operator=<std::default_delete<Rdp::Utils::Graphics::CRenderAdapter>,0>(
    v6,
    &v54);
  if ( v11 != v12 )
    goto LABEL_11;
LABEL_35:
  *(_DWORD *)v3 = 3;
  v43 = (__int64 *)Rdp::Utils::Graphics::CRenderAdapter::CreateRenderDevice(*v6, &v58);
  v44 = *v43;
  v45 = v43[1];
  *v43 = 0;
  v43[1] = 0;
  *((_QWORD *)this + 33) = v44;
  v46 = (std::_Ref_count_base *)*((_QWORD *)this + 34);
  *((_QWORD *)this + 34) = v45;
  if ( v46 )
    std::_Ref_count_base::_Decref(v46);
  if ( v59 )
    std::_Ref_count_base::_Decref(v59);
  v47 = *(_DWORD **)(wil::details::static_lazy<RdpIddLoggingProvider>::get() + 8);
  if ( *v47 > 4u )
  {
    v61 = *(_DWORD *)(*((_QWORD *)this + 29) + 516LL);
    LODWORD(v63) = *((_DWORD *)this + 70);
    v58 = "Assigning render device to frame processor";
    v57 = "CRdpIdMonitor::AssignRenderAdapter";
    *(_DWORD *)v52 = 567;
    v56 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\monitor.cpp";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (_DWORD)v47,
      (unsigned int)&byte_18004EA17,
      (_DWORD)v47,
      v48,
      (__int64)&v56,
      (__int64)v52,
      (__int64)&v57,
      (__int64)&v58,
      (__int64)&v63,
      (__int64)&v61);
  }
  v49 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 38) + 48LL))(
          *((_QWORD *)this + 38),
          *(_QWORD *)(*((_QWORD *)this + 33) + 16LL));
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x239,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\monitor.cpp",
    (const char *)v49,
    (int)"Failed to set render device to frame processor",
    v50);
LABEL_42:
  std::unique_ptr<Rdp::Utils::Graphics::CRenderAdapter>::~unique_ptr<Rdp::Utils::Graphics::CRenderAdapter>(&v54);
}

```

## disassembly

```asm
0x180023b6c  mov     [rsp-8+arg_8], rbx
0x180023b71  mov     [rsp-8+arg_10], r8
0x180023b76  push    rbp
0x180023b77  push    rsi
0x180023b78  push    rdi
0x180023b79  push    r12
0x180023b7b  push    r13
0x180023b7d  push    r14
0x180023b7f  push    r15
0x180023b81  lea     rbp, [rsp-27h]
0x180023b86  sub     rsp, 0A0h
0x180023b8d  mov     r12, r8
0x180023b90  mov     rbx, rdx
0x180023b93  mov     rsi, rcx
0x180023b96  xor     edi, edi
0x180023b98  mov     [rbp+57h+arg_0], edi
0x180023b9b  mov     [rbp+57h+var_60], rdi
0x180023b9f  lea     r15, [rcx+100h]
0x180023ba6  mov     rcx, [r15]
0x180023ba9  test    rcx, rcx
0x180023bac  jz      loc_180023CDE
0x180023bb2  mov     eax, [rdx]
0x180023bb4  cmp     [rcx+130h], eax
0x180023bba  jnz     short loc_180023BCB
0x180023bbc  mov     eax, [rdx+4]
0x180023bbf  cmp     [rcx+134h], eax
0x180023bc5  jz      loc_18002433F
0x180023bcb  call    ?get@?$static_lazy@VRdpIddLoggingProvider@@@details@wil@@QEAAPEAVRdpIddLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<RdpIddLoggingProvider>::get(void (*)(void))
0x180023bd0  mov     r8, [rax+8]
0x180023bd4  mov     eax, [r8]
0x180023bd7  lea     r13, aCrdpidmonitorA; "CRdpIdMonitor::AssignRenderAdapter"
0x180023bde  lea     r14, aOnecoreuapTerm_12; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x180023be5  cmp     eax, 4
0x180023be8  jbe     loc_180023C8D
0x180023bee  mov     rax, [rbx]
0x180023bf1  mov     [rbp+57h+var_68], rax
0x180023bf5  mov     rax, [r15]
0x180023bf8  mov     rcx, [rax+130h]
0x180023bff  mov     [rbp+57h+var_58], rcx
0x180023c03  mov     rax, [rsi+0E8h]
0x180023c0a  mov     ecx, [rax+204h]
0x180023c10  mov     [rbp+57h+arg_0], ecx
0x180023c13  mov     eax, [rsi+118h]
0x180023c19  mov     dword ptr [rbp+57h+arg_18], eax
0x180023c1c  lea     rax, aReCreatingRend; "Re-creating render adapter"
0x180023c23  mov     [rbp+57h+var_50], rax
0x180023c27  mov     [rbp+57h+var_48], r13
0x180023c2b  mov     dword ptr [rbp+57h+var_70], 1A8h
0x180023c32  mov     [rbp+57h+var_40], r14
0x180023c36  lea     rax, [rbp+57h+var_68]
0x180023c3a  mov     [rsp+0D0h+var_78], rax
0x180023c3f  lea     rax, [rbp+57h+var_58]
0x180023c43  mov     [rsp+0D0h+var_80], rax
0x180023c48  lea     rax, [rbp+57h+arg_0]
0x180023c4c  mov     [rsp+0D0h+var_88], rax
0x180023c51  lea     rax, [rbp+57h+arg_18]
0x180023c55  mov     [rsp+0D0h+var_90], rax
0x180023c5a  lea     rax, [rbp+57h+var_50]
0x180023c5e  mov     [rsp+0D0h+var_98], rax
0x180023c63  lea     rax, [rbp+57h+var_48]
0x180023c67  mov     [rsp+0D0h+var_A0], rax
0x180023c6c  lea     rax, [rbp+57h+var_70]
0x180023c70  mov     [rsp+0D0h+var_A8], rax
0x180023c75  lea     rax, [rbp+57h+var_40]
0x180023c79  mov     qword ptr [rsp+0D0h+var_B0], rax
0x180023c7e  lea     rdx, qword_18004ECF8
0x180023c85  mov     rcx, r8
0x180023c88  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U2@U?$_tlgWrapperByVal@$07@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3344AEBU?$_tlgWrapperByVal@$07@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)
0x180023c8d  mov     dword ptr [r12], 2
0x180023c95  mov     rdx, rbx
0x180023c98  lea     rcx, [rbp+57h+arg_0]
0x180023c9c  call    ??$make_unique@VCRenderAdapter@Graphics@Utils@Rdp@@AEBU_LUID@@$0A@@std@@YA?AV?$unique_ptr@VCRenderAdapter@Graphics@Utils@Rdp@@U?$default_delete@VCRenderAdapter@Graphics@Utils@Rdp@@@std@@@0@AEBU_LUID@@@Z; std::make_unique<Rdp::Utils::Graphics::CRenderAdapter,_LUID const &,0>(_LUID const &)
0x180023ca1  mov     rdx, rax
0x180023ca4  lea     rcx, [rbp+57h+var_60]
0x180023ca8  call    ??$?4U?$default_delete@VCRenderAdapter@Graphics@Utils@Rdp@@@std@@$0A@@?$unique_ptr@VCRenderAdapter@Graphics@Utils@Rdp@@U?$default_delete@VCRenderAdapter@Graphics@Utils@Rdp@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<Rdp::Utils::Graphics::CRenderAdapter>::operator=<std::default_delete<Rdp::Utils::Graphics::CRenderAdapter>,0>(std::unique_ptr<Rdp::Utils::Graphics::CRenderAdapter> &&)
0x180023cad  lea     rcx, [rbp+57h+arg_0]
0x180023cb1  call    ??1?$unique_ptr@VCRenderAdapter@Graphics@Utils@Rdp@@U?$default_delete@VCRenderAdapter@Graphics@Utils@Rdp@@@std@@@std@@QEAA@XZ; std::unique_ptr<Rdp::Utils::Graphics::CRenderAdapter>::~unique_ptr<Rdp::Utils::Graphics::CRenderAdapter>(void)
0x180023cb6  mov     rax, [rbp+57h+var_60]
0x180023cba  mov     dil, [rax]
0x180023cbd  mov     rax, [r15]
0x180023cc0  mov     bl, [rax]
0x180023cc2  lea     rdx, [rbp+57h+var_60]
0x180023cc6  mov     rcx, r15
0x180023cc9  call    ??$?4U?$default_delete@VCRenderAdapter@Graphics@Utils@Rdp@@@std@@$0A@@?$unique_ptr@VCRenderAdapter@Graphics@Utils@Rdp@@U?$default_delete@VCRenderAdapter@Graphics@Utils@Rdp@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<Rdp::Utils::Graphics::CRenderAdapter>::operator=<std::default_delete<Rdp::Utils::Graphics::CRenderAdapter>,0>(std::unique_ptr<Rdp::Utils::Graphics::CRenderAdapter> &&)
0x180023cce  cmp     dil, bl
0x180023cd1  jz      loc_180024220
0x180023cd7  xor     edi, edi
0x180023cd9  jmp     loc_180023DB1
0x180023cde  call    ?get@?$static_lazy@VRdpIddLoggingProvider@@@details@wil@@QEAAPEAVRdpIddLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<RdpIddLoggingProvider>::get(void (*)(void))
0x180023ce3  mov     r8, [rax+8]
0x180023ce7  mov     eax, [r8]
0x180023cea  lea     r13, aCrdpidmonitorA; "CRdpIdMonitor::AssignRenderAdapter"
0x180023cf1  lea     r14, aOnecoreuapTerm_12; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x180023cf8  cmp     eax, 4
0x180023cfb  jbe     loc_180023D89
0x180023d01  mov     rax, [rbx]
0x180023d04  mov     [rbp+57h+var_40], rax
0x180023d08  mov     rax, [rsi+0E8h]
0x180023d0f  mov     ecx, [rax+204h]
0x180023d15  mov     [rbp+57h+arg_0], ecx
0x180023d18  mov     eax, [rsi+118h]
0x180023d1e  mov     dword ptr [rbp+57h+arg_18], eax
0x180023d21  lea     rax, aCreatingRender_0; "Creating render adapter"
0x180023d28  mov     [rbp+57h+var_48], rax
0x180023d2c  mov     [rbp+57h+var_50], r13
0x180023d30  mov     dword ptr [rbp+57h+var_70], 1C6h
0x180023d37  mov     [rbp+57h+var_58], r14
0x180023d3b  lea     rax, [rbp+57h+var_40]
0x180023d3f  mov     [rsp+0D0h+var_80], rax
0x180023d44  lea     rax, [rbp+57h+arg_0]
0x180023d48  mov     [rsp+0D0h+var_88], rax
0x180023d4d  lea     rax, [rbp+57h+arg_18]
0x180023d51  mov     [rsp+0D0h+var_90], rax
0x180023d56  lea     rax, [rbp+57h+var_48]
0x180023d5a  mov     [rsp+0D0h+var_98], rax
0x180023d5f  lea     rax, [rbp+57h+var_50]
0x180023d63  mov     [rsp+0D0h+var_A0], rax
0x180023d68  lea     rax, [rbp+57h+var_70]
0x180023d6c  mov     [rsp+0D0h+var_A8], rax; char *
0x180023d71  lea     rax, [rbp+57h+var_58]
0x180023d75  mov     qword ptr [rsp+0D0h+var_B0], rax
0x180023d7a  lea     rdx, byte_18004EC9D
0x180023d81  mov     rcx, r8
0x180023d84  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U2@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3344AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x180023d89  mov     dword ptr [r12], 2
0x180023d91  mov     rdx, rbx
0x180023d94  lea     rcx, [rbp+57h+arg_0]
0x180023d98  call    ??$make_unique@VCRenderAdapter@Graphics@Utils@Rdp@@AEBU_LUID@@$0A@@std@@YA?AV?$unique_ptr@VCRenderAdapter@Graphics@Utils@Rdp@@U?$default_delete@VCRenderAdapter@Graphics@Utils@Rdp@@@std@@@0@AEBU_LUID@@@Z; std::make_unique<Rdp::Utils::Graphics::CRenderAdapter,_LUID const &,0>(_LUID const &)
0x180023d9d  mov     rdx, rax
0x180023da0  mov     rcx, r15
0x180023da3  call    ??$?4U?$default_delete@VCRenderAdapter@Graphics@Utils@Rdp@@@std@@$0A@@?$unique_ptr@VCRenderAdapter@Graphics@Utils@Rdp@@U?$default_delete@VCRenderAdapter@Graphics@Utils@Rdp@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<Rdp::Utils::Graphics::CRenderAdapter>::operator=<std::default_delete<Rdp::Utils::Graphics::CRenderAdapter>,0>(std::unique_ptr<Rdp::Utils::Graphics::CRenderAdapter> &&)
0x180023da8  lea     rcx, [rbp+57h+arg_0]
0x180023dac  call    ??1?$unique_ptr@VCRenderAdapter@Graphics@Utils@Rdp@@U?$default_delete@VCRenderAdapter@Graphics@Utils@Rdp@@@std@@@std@@QEAA@XZ; std::unique_ptr<Rdp::Utils::Graphics::CRenderAdapter>::~unique_ptr<Rdp::Utils::Graphics::CRenderAdapter>(void)
0x180023db1  mov     dword ptr [r12], 8
0x180023db9  lea     rbx, [rsi+130h]
0x180023dc0  mov     rcx, [rbx]
0x180023dc3  test    rcx, rcx
0x180023dc6  jz      short loc_180023E03
0x180023dc8  mov     rax, [rcx]
0x180023dcb  mov     rax, [rax+28h]
0x180023dcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023dd4  mov     rcx, [rbp+5Fh]; this
0x180023dd8  lea     rdx, aFailedToStopFr; "Failed to stop frame processor"
0x180023ddf  mov     qword ptr [rsp+0D0h+var_B0], rdx; int
0x180023de4  mov     r9d, eax; char *
0x180023de7  mov     r8, r14; unsigned int
0x180023dea  mov     edx, 1DBh; void *
0x180023def  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180023df4  mov     rcx, rbx
0x180023df7  call    ?reset@?$com_ptr_t@UIFileIoChannelEvents@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<Rdp::Avenc::IFileIoChannelEvents,wil::err_exception_policy>::reset(void)
0x180023dfc  lea     rbx, [rsi+130h]
0x180023e03  mov     rax, [r15]
0x180023e06  cmp     [rax], dil
0x180023e09  jz      loc_180023FFE
0x180023e0f  call    ?get@?$static_lazy@VRdpIddLoggingProvider@@@details@wil@@QEAAPEAVRdpIddLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<RdpIddLoggingProvider>::get(void (*)(void))
0x180023e14  mov     r8, [rax+8]
0x180023e18  mov     eax, [r8]
0x180023e1b  cmp     eax, 4
0x180023e1e  jbe     short loc_180023E98
0x180023e20  mov     rax, [rsi+0E8h]
0x180023e27  mov     ecx, [rax+204h]
0x180023e2d  mov     [rbp+57h+arg_0], ecx
0x180023e30  mov     eax, [rsi+118h]
0x180023e36  mov     dword ptr [rbp+57h+arg_18], eax
0x180023e39  lea     rax, aCreatingCpuFra; "Creating Cpu frame encoding processor"
0x180023e40  mov     [rbp+57h+var_40], rax
0x180023e44  mov     [rbp+57h+var_48], r13
0x180023e48  mov     dword ptr [rbp+57h+var_70], 1E6h
0x180023e4f  mov     [rbp+57h+var_50], r14
0x180023e53  lea     rax, [rbp+57h+arg_0]
0x180023e57  mov     [rsp+0D0h+var_88], rax
0x180023e5c  lea     rax, [rbp+57h+arg_18]
0x180023e60  mov     [rsp+0D0h+var_90], rax
0x180023e65  lea     rax, [rbp+57h+var_40]
0x180023e69  mov     [rsp+0D0h+var_98], rax
0x180023e6e  lea     rax, [rbp+57h+var_48]
0x180023e72  mov     [rsp+0D0h+var_A0], rax
0x180023e77  lea     rax, [rbp+57h+var_70]
0x180023e7b  mov     [rsp+0D0h+var_A8], rax; char *
0x180023e80  lea     rax, [rbp+57h+var_50]
0x180023e84  mov     qword ptr [rsp+0D0h+var_B0], rax
0x180023e89  lea     rdx, byte_18004EC4F
0x180023e90  mov     rcx, r8
0x180023e93  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3344@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180023e98  mov     [rbp+57h+var_68], rdi
0x180023e9c  mov     rcx, [rsi+138h]
0x180023ea3  mov     rax, [rcx]
0x180023ea6  mov     [rbp+57h+var_68], rdi
0x180023eaa  xor     r8d, r8d
0x180023ead  lea     rdx, [rbp+57h+var_68]
0x180023eb1  mov     rax, [rax+38h]
0x180023eb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023eba  mov     rcx, [rbp+5Fh]; this
0x180023ebe  lea     rdx, aFailedToCreate_4; "Failed to create Warp frame processor"
0x180023ec5  mov     qword ptr [rsp+0D0h+var_B0], rdx; int
0x180023eca  mov     r9d, eax; char *
0x180023ecd  mov     r8, r14; unsigned int
0x180023ed0  mov     edx, 1E9h; void *
0x180023ed5  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180023eda  mov     rax, [rsi+0E8h]
0x180023ee1  cmp     [rax+1F8h], dil
0x180023ee8  jz      loc_180023FE3
0x180023eee  call    ?get@?$static_lazy@VRdpIddLoggingProvider@@@details@wil@@QEAAPEAVRdpIddLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<RdpIddLoggingProvider>::get(void (*)(void))
0x180023ef3  mov     r8, [rax+8]
0x180023ef7  mov     eax, [r8]
0x180023efa  cmp     eax, 4
0x180023efd  jbe     short loc_180023F77
0x180023eff  mov     rax, [rsi+0E8h]
0x180023f06  mov     ecx, [rax+204h]
0x180023f0c  mov     [rbp+57h+arg_0], ecx
0x180023f0f  mov     eax, [rsi+118h]
0x180023f15  mov     dword ptr [rbp+57h+arg_18], eax
0x180023f18  lea     rax, aCreateCpuFrame; "Create Cpu frame dumper processor"
0x180023f1f  mov     [rbp+57h+var_40], rax
0x180023f23  mov     [rbp+57h+var_48], r13
0x180023f27  mov     dword ptr [rbp+57h+var_70], 1F3h
0x180023f2e  mov     [rbp+57h+var_50], r14
0x180023f32  lea     rax, [rbp+57h+arg_0]
0x180023f36  mov     [rsp+0D0h+var_88], rax
0x180023f3b  lea     rax, [rbp+57h+arg_18]
0x180023f3f  mov     [rsp+0D0h+var_90], rax
0x180023f44  lea     rax, [rbp+57h+var_40]
0x180023f48  mov     [rsp+0D0h+var_98], rax
0x180023f4d  lea     rax, [rbp+57h+var_48]
0x180023f51  mov     [rsp+0D0h+var_A0], rax
0x180023f56  lea     rax, [rbp+57h+var_70]
0x180023f5a  mov     [rsp+0D0h+var_A8], rax
0x180023f5f  lea     rax, [rbp+57h+var_50]
0x180023f63  mov     qword ptr [rsp+0D0h+var_B0], rax
0x180023f68  lea     rdx, byte_18004EC01
0x180023f6f  mov     rcx, r8
0x180023f72  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3344@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180023f77  mov     ecx, 60h ; '`'; Size
0x180023f7c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180023f81  mov     rdi, rax
0x180023f84  mov     [rbp+57h+arg_18], rax
0x180023f88  mov     rbx, [rbp+57h+var_68]
0x180023f8c  lea     rdx, [rbp+57h+var_40]
0x180023f90  mov     rcx, rsi
0x180023f93  call    ?shared_from_this@?$enable_shared_from_this@VCRdpIdAdapter@@@std@@QEAA?AV?$shared_ptr@VCRdpIdAdapter@@@2@XZ; std::enable_shared_from_this<CRdpIdAdapter>::shared_from_this(void)
0x180023f98  nop
0x180023f99  mov     [rbp+57h+arg_0], 1
0x180023fa0  mov     r8, rbx
0x180023fa3  mov     rdx, rax
0x180023fa6  mov     rcx, rdi
0x180023fa9  call    ??0?$CFrameDumper@UICpuFrameProcessor@Avenc@Rdp@@@@QEAA@AEBV?$shared_ptr@VCRdpIdMonitor@@@std@@PEAUICpuFrameProcessor@Avenc@Rdp@@@Z; CFrameDumper<Rdp::Avenc::ICpuFrameProcessor>::CFrameDumper<Rdp::Avenc::ICpuFrameProcessor>(std::shared_ptr<CRdpIdMonitor> const &,Rdp::Avenc::ICpuFrameProcessor *)
0x180023fae  lea     rax, ??_7CCpuFrameDumper@@6B?$producers_base@V?$CFrameDumper@UICpuFrameProcessor@Avenc@Rdp@@@@V?$tuple@UICpuFrameProcessor@Avenc@Rdp@@@std@@@impl@winrt@@@; const CCpuFrameDumper::`vftable'{for `winrt::impl::producers_base<CFrameDumper<Rdp::Avenc::ICpuFrameProcessor>,std::tuple<Rdp::Avenc::ICpuFrameProcessor>>'}
0x180023fb5  mov     [rdi], rax
0x180023fb8  lea     rax, ??_7CCpuFrameDumper@@6B?$root_implements@V?$CFrameDumper@UICpuFrameProcessor@Avenc@Rdp@@@@UICpuFrameProcessor@Avenc@Rdp@@@impl@winrt@@@; const CCpuFrameDumper::`vftable'{for `winrt::impl::root_implements<CFrameDumper<Rdp::Avenc::ICpuFrameProcessor>,Rdp::Avenc::ICpuFrameProcessor>'}
0x180023fbf  mov     [rdi+8], rax
0x180023fc3  lea     rcx, [rsi+130h]
0x180023fca  mov     rdx, rdi
0x180023fcd  call    ??4?$com_ptr_t@UIFrameProcessor@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@QEAAAEAV01@PEAUIFrameProcessor@Avenc@Rdp@@@Z; wil::com_ptr_t<Rdp::Avenc::IFrameProcessor,wil::err_exception_policy>::operator=(Rdp::Avenc::IFrameProcessor *)
0x180023fd2  nop
0x180023fd3  mov     rcx, [rbp+57h+var_38]; this
0x180023fd7  test    rcx, rcx
0x180023fda  jz      short loc_180023FF0
0x180023fdc  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180023fe1  jmp     short loc_180023FF0
0x180023fe3  lea     rdx, [rbp+57h+var_68]
0x180023fe7  mov     rcx, rbx
0x180023fea  call    ??$?4UICpuFrameProcessor@Avenc@Rdp@@Uerr_exception_policy@wil@@X@?$com_ptr_t@UIFrameProcessor@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@QEAAAEAV01@$$QEAV?$com_ptr_t@UICpuFrameProcessor@Avenc@Rdp@@Uerr_exception_policy@wil@@@1@@Z; wil::com_ptr_t<Rdp::Avenc::IFrameProcessor,wil::err_exception_policy>::operator=<Rdp::Avenc::ICpuFrameProcessor,wil::err_exception_policy,void>(wil::com_ptr_t<Rdp::Avenc::ICpuFrameProcessor,wil::err_exception_policy> &&)
0x180023fef  nop
0x180023ff0  lea     rcx, [rbp+57h+var_68]
0x180023ff4  call    ??1?$com_ptr_t@UIColorSpaceTransform@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>::~com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>(void)
0x180023ff9  jmp     loc_1800241ED
0x180023ffe  call    ?get@?$static_lazy@VRdpIddLoggingProvider@@@details@wil@@QEAAPEAVRdpIddLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<RdpIddLoggingProvider>::get(void (*)(void))
0x180024003  mov     r8, [rax+8]
0x180024007  mov     eax, [r8]
0x18002400a  cmp     eax, 4
0x18002400d  jbe     loc_180024094
0x180024013  mov     rax, [rsi+0E8h]
0x18002401a  mov     ecx, [rax+204h]
0x180024020  mov     [rbp+57h+arg_0], ecx
0x180024023  mov     eax, [rsi+118h]
0x180024029  mov     dword ptr [rbp+57h+arg_18], eax
0x18002402c  lea     rax, aCreatingGpuFra; "Creating Gpu frame encoding processor"
0x180024033  mov     [rbp+57h+var_40], rax
0x180024037  mov     [rbp+57h+var_48], r13
0x18002403b  mov     dword ptr [rbp+57h+var_70], 206h
0x180024042  mov     [rbp+57h+var_50], r14
0x180024046  lea     rax, [rbp+57h+arg_0]
0x18002404a  mov     [rsp+0D0h+var_88], rax
0x18002404f  lea     rax, [rbp+57h+arg_18]
0x180024053  mov     [rsp+0D0h+var_90], rax
0x180024058  lea     rax, [rbp+57h+var_40]
0x18002405c  mov     [rsp+0D0h+var_98], rax
0x180024061  lea     rax, [rbp+57h+var_48]
0x180024065  mov     [rsp+0D0h+var_A0], rax
0x18002406a  lea     rax, [rbp+57h+var_70]
0x18002406e  mov     [rsp+0D0h+var_A8], rax
0x180024073  lea     rax, [rbp+57h+var_50]
0x180024077  mov     qword ptr [rsp+0D0h+var_B0], rax
0x18002407c  lea     rdx, byte_18004EBB3
0x180024083  mov     rcx, r8
0x180024086  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3344@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18002408b  lea     r12, [rsi+130h]
0x180024092  jmp     short loc_180024097
0x180024094  mov     r12, rbx
0x180024097  mov     [rbp+57h+var_68], rdi
  ... truncated ...
```
