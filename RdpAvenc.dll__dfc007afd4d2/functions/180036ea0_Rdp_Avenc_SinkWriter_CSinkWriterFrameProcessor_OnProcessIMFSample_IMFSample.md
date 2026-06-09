# Rdp::Avenc::SinkWriter::CSinkWriterFrameProcessor::OnProcessIMFSample(IMFSample *)

- ea: `0x180036ea0`
- end: `0x180037558`
- name: `?OnProcessIMFSample@CSinkWriterFrameProcessor@SinkWriter@Avenc@Rdp@@UEAAJPEAUIMFSample@@@Z`
- size: `1720`
- prototype: `__int64 __fastcall(Rdp::Avenc::SinkWriter::CSinkWriterFrameProcessor *__hidden this, struct IMFSample *)`
- caller_count: `0`
- callee_count: `20`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000154c`
- `0x1800069a0`
- `0x180007018`
- `0x1800072b0`
- `0x18000b07c`
- `0x18000e848`
- `0x18000ec04`
- `0x18001143c`
- `0x180011490`
- `0x180022fb8`
- `0x180023b34`
- `0x180023ee4`
- `0x180026af8`
- `0x1800290d4`
- `0x18002b9a8`
- `0x18002d1bc`
- `0x18002d844`
- `0x18002dd40`
- `0x180036ea0`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180036ecc`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180036ecc`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x180036f1a`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x180036f1a`

## string_xrefs

- `0x1800372be`: `onecoreuap\termsrv\rdp_bin\win\common/protocol/RdpEgfx/RdpEgfx.h`
- `0x180037301`: `onecoreuap\termsrv\rdp_bin\win\common/protocol/RdpEgfx/RdpEgfx.h`
- `0x180037392`: `onecoreuap\termsrv\rdp_bin\win\common/protocol/RdpEgfx/RdpEgfx.h`
- `0x1800373d3`: `onecoreuap\termsrv\rdp_bin\win\common/protocol/RdpEgfx/RdpEgfx.h`
- `0x18003743b`: `onecoreuap\termsrv\rdp_bin\win\common/protocol/RdpEgfx/RdpEgfx.h`
- `0x180036f29`: `Egfx protocol object is not available`
- `0x180036f48`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\sinkwriterprocessor\sinkwriterframeprocessor.cpp`
- `0x180037035`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\sinkwriterprocessor\sinkwriterframeprocessor.cpp`
- `0x18003712f`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\sinkwriterprocessor\sinkwriterframeprocessor.cpp`
- `0x18003706f`: `Rdp::Avenc::SinkWriter::CSinkWriterFrameProcessor::OnProcessIMFSample`
- `0x180037486`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\SinkWriterProcessor/SinkWriterFrameProcessor.h`
- `0x180037545`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\SinkWriterProcessor/SinkWriterFrameProcessor.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall Rdp::Avenc::SinkWriter::CSinkWriterFrameProcessor::OnProcessIMFSample(
        Rdp::Avenc::SinkWriter::CSinkWriterFrameProcessor *this,
        struct IMFSample *a2)
{
  unsigned int v4; // r13d
  BOOL v5; // eax
  unsigned int v6; // r8d
  const char *v7; // r9
  __int64 v8; // rax
  volatile signed __int32 *v9; // rbx
  Rdp::Avenc::CFcWireEncoderWithBulkUncompressed *v10; // r14
  int v11; // eax
  unsigned int v12; // eax
  unsigned int v13; // edi
  unsigned int *v14; // r12
  unsigned int v15; // eax
  int v16; // r8d
  int v17; // r9d
  HRESULT (__stdcall *ConvertToContiguousBuffer)(IMFSample *, IMFMediaBuffer **); // rdi
  unsigned int v19; // eax
  __int64 v20; // rcx
  int v21; // eax
  int v22; // r8d
  int v23; // r9d
  __int64 v24; // rdx
  unsigned int v25; // edi
  unsigned int v26; // r15d
  __int64 v27; // r9
  unsigned int *v28; // rsi
  unsigned int v29; // r8d
  __int64 v30; // rdx
  unsigned int v31; // edi
  unsigned int v32; // esi
  __int64 v33; // r9
  _WORD *v34; // r15
  __int64 i; // rcx
  unsigned int v36; // edx
  __int64 v37; // rcx
  int v38; // eax
  const char *v39; // r9
  __int64 result; // rax
  int v41; // [rsp+20h] [rbp-C8h]
  _DWORD *v42; // [rsp+20h] [rbp-C8h]
  char *v43; // [rsp+28h] [rbp-C0h]
  char *v44; // [rsp+28h] [rbp-C0h]
  char *v45; // [rsp+28h] [rbp-C0h]
  __int64 v46; // [rsp+30h] [rbp-B8h]
  __int64 v47; // [rsp+50h] [rbp-98h] BYREF
  __int64 v48; // [rsp+58h] [rbp-90h] BYREF
  void *v49; // [rsp+60h] [rbp-88h] BYREF
  __int64 v50; // [rsp+68h] [rbp-80h] BYREF
  __int64 v51; // [rsp+70h] [rbp-78h] BYREF
  const char *v52; // [rsp+78h] [rbp-70h] BYREF
  const char *v53; // [rsp+80h] [rbp-68h] BYREF
  __int128 v54; // [rsp+88h] [rbp-60h] BYREF
  int v55[2]; // [rsp+98h] [rbp-50h] BYREF
  __int64 v56; // [rsp+A0h] [rbp-48h]
  unsigned int *v57; // [rsp+A8h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+0h]
  size_t Size; // [rsp+F0h] [rbp+8h] BYREF
  void *v60; // [rsp+100h] [rbp+18h] BYREF
  __int64 *v61; // [rsp+108h] [rbp+20h] BYREF

  v4 = 0;
  v47 = 0;
  v5 = SetEvent(*(HANDLE *)(*((_QWORD *)this + 4) + 144LL));
  try
  {
    if ( !v5 )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA01, v6, v7);
    v8 = std::_Locked_pointer<std::_Ref_count_base>::_Lock_and_load((char *)this + 24);
    v9 = (volatile signed __int32 *)v8;
    v10 = (Rdp::Avenc::CFcWireEncoderWithBulkUncompressed *)*((_QWORD *)this + 2);
    *(_QWORD *)v55 = v10;
    v56 = v8;
    if ( v8 )
      _InterlockedIncrement((volatile signed __int32 *)(v8 + 8));
    if ( (_InterlockedExchange64((volatile __int64 *)this + 3, v8) & 3) == 2 )
      WakeByAddressAll((char *)this + 24);
    wil::details::in1diag3::Throw_HrIfNullMsg<wil::com_ptr_t<IPropertyStore,wil::err_exception_policy>,0>(
      retaddr,
      323,
      "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\sinkwriterprocessor\\sinkwriterframeprocessor.cpp",
      2147500035LL);
    v51 = 0;
    v11 = ((__int64 (__fastcall *)(struct IMFSample *, __int64 *))a2->lpVtbl->GetSampleTime)(a2, &v51);
    if ( v11 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x146,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\sinkwriterprocessor\\sinkwriterframeprocessor.cpp",
        (const char *)(unsigned int)v11,
        (int)v55);
    LODWORD(Size) = 0;
    v12 = ((__int64 (__fastcall *)(struct IMFSample *, __int64 *, size_t *))a2->lpVtbl->GetBlobSize)(
            a2,
            MFSampleExtension_DirtyRects,
            &Size);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0x150,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\sinkwriterprocessor\\sinkwriterframeprocessor.cpp",
      (const char *)v12,
      (int)"Failed to get size of dirty rect info blob",
      "Egfx protocol object is not available");
    v13 = Size;
    v14 = (unsigned int *)operator new[]((unsigned int)Size);
    memset_0(v14, 0, v13);
    v57 = v14;
    v15 = ((__int64 (__fastcall *)(struct IMFSample *, __int64 *, unsigned int *, _QWORD, _QWORD))a2->lpVtbl->GetBlob)(
            a2,
            MFSampleExtension_DirtyRects,
            v14,
            (unsigned int)Size,
            0);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0x159,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\sinkwriterprocessor\\sinkwriterframeprocessor.cpp",
      (const char *)v15,
      (int)"Failed to get dirty rect info",
      v43);
    if ( (unsigned int)dword_1800C1058 > 5 )
    {
      LODWORD(v60) = *v14;
      v52 = "EncodeFrameEnd";
      v53 = "Rdp::Avenc::SinkWriter::CSinkWriterFrameProcessor::OnProcessIMFSample";
      LODWORD(v61) = 351;
      *(_QWORD *)&v54 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\sinkwriterprocessor\\sinkwriterframeprocessor.cpp";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        (unsigned int)&dword_1800C1058,
        (unsigned int)byte_1800AF3C5,
        v16,
        v17,
        (__int64)&v54,
        (__int64)&v61,
        (__int64)&v53,
        (__int64)&v52,
        (__int64)&v60);
    }
    ConvertToContiguousBuffer = a2->lpVtbl->ConvertToContiguousBuffer;
    v47 = 0;
    v19 = ((__int64 (__fastcall *)(struct IMFSample *, __int64 *))ConvertToContiguousBuffer)(a2, &v47);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0x162,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\sinkwriterprocessor\\sinkwriterframeprocessor.cpp",
      (const char *)v19,
      (int)"Failed to get media buffer",
      v44);
    v20 = v47;
    v48 = v47;
    if ( v47 )
    {
      (*(void (**)(void))(*(_QWORD *)v47 + 8LL))();
      v20 = v48;
    }
    v60 = 0;
    v49 = 0;
    v50 = 0;
    v61 = &v48;
    if ( v20 )
    {
      v21 = (*(__int64 (__fastcall **)(__int64, void **, __int64 *, char *))(*(_QWORD *)v20 + 24LL))(
              v20,
              &v49,
              &v50,
              (char *)&v50 + 4);
      if ( v21 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x24,
          (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\SinkWriterProcessor/SinkWriterFrameProcessor.h",
          (const char *)(unsigned int)v21,
          v41);
      v4 = HIDWORD(v50);
      v60 = v49;
    }
    Rdp::Avenc::ClientFrameRateTracker::OnFrameEncoded(*((Rdp::Avenc::ClientFrameRateTracker **)this + 5), *v14);
    Rdp::Avenc::CFcWireEncoderWithBulkUncompressed::AllocatePool(v10, ((v4 + 4095) & 0xFFFFF000) + 4096, 0, 0);
    Rdp::Protocol::CRdpEgfx<Rdp::Avenc::CFcWireEncoderWithBulkUncompressed>::StartFrame(
      v10,
      *v14,
      v51,
      *((_QWORD *)this + 1) + 120LL);
    v22 = 0;
    v23 = 0;
    v24 = v14[1];
    if ( (unsigned __int64)(8 * v24) <= 0xFFFFFFFF && 8 * (int)v24 + 4 >= (unsigned int)(8 * v24) )
      v22 = 8 * v24 + 4;
    if ( (unsigned __int64)(2 * v24) <= 0xFFFFFFFF )
      v23 = 2 * v24;
    v54 = 0;
    Rdp::Protocol::CRdpEgfx<Rdp::Avenc::CFcWireEncoderWithBulkUncompressed>::WireToSurface1(
      (_DWORD)v10,
      *(_DWORD *)(*((_QWORD *)this + 1) + 136LL),
      11,
      v23,
      (__int64)&v54,
      v4 + v23 + v22);
    v25 = v14[1];
    v26 = 0;
    v27 = 2147942934LL;
    if ( 8 * (unsigned __int64)v25 <= 0xFFFFFFFF && 8 * v25 + 4 >= 8 * v25 )
    {
      v26 = 8 * v25 + 4;
      v27 = 0;
    }
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0x278,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\common/protocol/RdpEgfx/RdpEgfx.h",
      (const char *)v27,
      (int)"Failed to calculate size of Avc420Metablock1",
      v45);
    v28 = (unsigned int *)Rdp::Avenc::CFcWireEncoderWithBulkUncompressed::EnsureBuffer(v10, v26);
    LODWORD(v46) = v26;
    wil::details::in1diag3::Throw_HrIfNullMsg<void *,0>(
      retaddr,
      637,
      "onecoreuap\\termsrv\\rdp_bin\\win\\common/protocol/RdpEgfx/RdpEgfx.h",
      2147942414LL);
    *v28 = v25;
    v29 = 0;
    if ( v25 )
    {
      v30 = 0;
      do
      {
        LOWORD(v28[2 * v30 + 1]) = v14[4 * v30 + 2];
        HIWORD(v28[2 * v30 + 1]) = v14[4 * v30 + 3];
        LOWORD(v28[2 * v30 + 2]) = v14[4 * v30 + 4];
        HIWORD(v28[2 * v30 + 2]) = v14[4 * v30 + 5];
        ++v29;
        ++v30;
      }
      while ( v29 < v25 );
    }
    v31 = v14[1];
    if ( 2 * (unsigned __int64)v31 > 0xFFFFFFFF )
    {
      v32 = 0;
      v33 = 2147942934LL;
    }
    else
    {
      v32 = 2 * v31;
      v33 = 0;
    }
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0x292,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\common/protocol/RdpEgfx/RdpEgfx.h",
      (const char *)v33,
      (int)"Failed to calculate size of Avc420Metablock2",
      "Unable to ensure RFX_AVC420_METABLOCK1_UA %d bytes",
      v46);
    v34 = Rdp::Avenc::CFcWireEncoderWithBulkUncompressed::EnsureBuffer(v10, v32);
    wil::details::in1diag3::Throw_HrIfNullMsg<void *,0>(
      retaddr,
      663,
      "onecoreuap\\termsrv\\rdp_bin\\win\\common/protocol/RdpEgfx/RdpEgfx.h",
      2147942414LL);
    for ( i = 0; (unsigned int)i < v31; i = (unsigned int)(i + 1) )
      v34[i] = 25620;
    Rdp::Avenc::CFcWireEncoder::WriteBuffer(v10, v60, v4);
    v42 = Rdp::Avenc::CFcWireEncoderWithBulkUncompressed::EnsureBuffer(v10, 0xCu);
    wil::details::in1diag3::Throw_HrIfNullMsg<void *,0>(
      retaddr,
      420,
      "onecoreuap\\termsrv\\rdp_bin\\win\\common/protocol/RdpEgfx/RdpEgfx.h",
      2147942414LL);
    *v42 = 12;
    v42[1] = 12;
    v42[2] = *((_DWORD *)v10 + 22);
    Rdp::Avenc::CFcWireEncoder::Flush(v10, v36);
    v37 = v48;
    if ( v48 )
    {
      v38 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v48 + 32LL))(v48);
      if ( v38 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x2C,
          (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\SinkWriterProcessor/SinkWriterFrameProcessor.h",
          (const char *)(unsigned int)v38,
          (int)v42);
      v37 = v48;
    }
    if ( v37 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
    operator delete(v14);
    if ( v9 )
    {
      if ( _InterlockedExchangeAdd(v9 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v9)(v9);
        if ( _InterlockedExchangeAdd(v9 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 8LL))(v9);
      }
    }
    if ( v47 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
    result = 0;
  }
  catch ( ... )
  {
    LODWORD(Size) = wil::details::in1diag3::Return_CaughtException(
                      retaddr,
                      (void *)0x194,
                      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\sinkwriterprocessor\\sinkwriterframeprocessor.cpp",
                      v39);
    return (unsigned int)Size;
  }
  return result;
}

```

## disassembly

```asm
0x180036ea0  push    rbx
0x180036ea2  push    rsi
0x180036ea3  push    rdi
0x180036ea4  push    r12
0x180036ea6  push    r13
0x180036ea8  push    r14
0x180036eaa  push    r15
0x180036eac  sub     rsp, 0B0h
0x180036eb3  mov     rsi, rdx
0x180036eb6  mov     r15, rcx
0x180036eb9  xor     r13d, r13d
0x180036ebc  mov     [rsp+0E8h+var_98], r13
0x180036ec1  mov     rcx, [rcx+20h]
0x180036ec5  mov     rcx, [rcx+90h]; hEvent
0x180036ecc  call    cs:__imp_SetEvent
0x180036ed2  mov     rcx, [rsp+0E8h]; this
0x180036eda  test    eax, eax
0x180036edc  jz      loc_180037526
0x180036ee2  lea     rdi, [r15+18h]
0x180036ee6  mov     rcx, rdi; Address
0x180036ee9  call    ?_Lock_and_load@?$_Locked_pointer@V_Ref_count_base@std@@@std@@QEAAPEAV_Ref_count_base@2@XZ; std::_Locked_pointer<std::_Ref_count_base>::_Lock_and_load(void)
0x180036eee  mov     rbx, rax
0x180036ef1  mov     r14, [r15+10h]
0x180036ef5  mov     qword ptr [rsp+0E8h+var_50], r14
0x180036efd  mov     [rsp+0E8h+var_48], rax
0x180036f05  test    rax, rax
0x180036f08  jz      short loc_180036F0E
0x180036f0a  lock inc dword ptr [rax+8]
0x180036f0e  xchg    rax, [rdi]
0x180036f11  and     al, 3
0x180036f13  cmp     al, 2
0x180036f15  jnz     short loc_180036F21
0x180036f17  mov     rcx, rdi; Address
0x180036f1a  call    cs:__imp_WakeByAddressAll
0x180036f20  nop
0x180036f21  mov     rcx, [rsp+0E8h]
0x180036f29  lea     rax, aEgfxProtocolOb; "Egfx protocol object is not available"
0x180036f30  mov     [rsp+0E8h+var_C0], rax; char *
0x180036f35  lea     rax, [rsp+0E8h+var_50]
0x180036f3d  mov     qword ptr [rsp+0E8h+var_C8], rax; int
0x180036f42  mov     r9d, 80004003h
0x180036f48  lea     rdi, aOnecoreuapTerm_10; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180036f4f  mov     r8, rdi
0x180036f52  mov     edx, 143h
0x180036f57  call    ??$Throw_HrIfNullMsg@V?$com_ptr_t@UIPropertyStore@@Uerr_exception_policy@wil@@@wil@@$0A@@in1diag3@details@wil@@YAXPEAXIPEBDJAEBV?$com_ptr_t@UIPropertyStore@@Uerr_exception_policy@wil@@@2@1ZZ; wil::details::in1diag3::Throw_HrIfNullMsg<wil::com_ptr_t<IPropertyStore,wil::err_exception_policy>,0>(void *,uint,char const *,long,wil::com_ptr_t<IPropertyStore,wil::err_exception_policy> const &,char const *,...)
0x180036f5c  mov     [rsp+0E8h+var_78], r13
0x180036f61  mov     rax, [rsi]
0x180036f64  lea     rdx, [rsp+0E8h+var_78]
0x180036f69  mov     rcx, rsi
0x180036f6c  mov     rax, [rax+118h]
0x180036f73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036f78  mov     rcx, [rsp+0E8h]; this
0x180036f80  test    eax, eax
0x180036f82  js      loc_180037531
0x180036f88  mov     dword ptr [rsp+0E8h+Size], r13d
0x180036f90  mov     rax, [rsi]
0x180036f93  lea     r8, [rsp+0E8h+Size]
0x180036f9b  lea     rdx, MFSampleExtension_DirtyRects
0x180036fa2  mov     rcx, rsi
0x180036fa5  mov     rax, [rax+70h]
0x180036fa9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036fae  mov     rcx, [rsp+0E8h]; this
0x180036fb6  lea     rdx, aFailedToGetSiz; "Failed to get size of dirty rect info b"...
0x180036fbd  mov     qword ptr [rsp+0E8h+var_C8], rdx; int
0x180036fc2  mov     r9d, eax; char *
0x180036fc5  mov     r8, rdi; unsigned int
0x180036fc8  mov     edx, 150h; void *
0x180036fcd  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180036fd2  mov     edi, dword ptr [rsp+0E8h+Size]
0x180036fd9  mov     ecx, edi; unsigned __int64
0x180036fdb  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180036fe0  mov     r12, rax
0x180036fe3  mov     r8d, edi; Size
0x180036fe6  xor     edx, edx; Val
0x180036fe8  mov     rcx, rax; void *
0x180036feb  call    memset_0
0x180036ff0  mov     [rsp+0E8h+var_40], r12
0x180036ff8  mov     rax, [rsi]
0x180036ffb  mov     qword ptr [rsp+0E8h+var_C8], r13
0x180037000  mov     r9d, dword ptr [rsp+0E8h+Size]
0x180037008  mov     r8, r12
0x18003700b  lea     rdx, MFSampleExtension_DirtyRects
0x180037012  mov     rcx, rsi
0x180037015  mov     rax, [rax+78h]
0x180037019  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003701e  mov     rcx, [rsp+0E8h]; this
0x180037026  lea     rdx, aFailedToGetDir; "Failed to get dirty rect info"
0x18003702d  mov     qword ptr [rsp+0E8h+var_C8], rdx; int
0x180037032  mov     r9d, eax; char *
0x180037035  lea     rdi, aOnecoreuapTerm_10; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18003703c  mov     r8, rdi; unsigned int
0x18003703f  mov     edx, 159h; void *
0x180037044  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180037049  mov     eax, cs:dword_1800C1058
0x18003704f  cmp     eax, 5
0x180037052  jbe     loc_1800370E2
0x180037058  mov     eax, [r12]
0x18003705c  mov     dword ptr [rsp+0E8h+arg_10], eax
0x180037063  lea     rax, aEncodeframeend; "EncodeFrameEnd"
0x18003706a  mov     [rsp+0E8h+var_70], rax
0x18003706f  lea     rax, aRdpAvencSinkwr_1; "Rdp::Avenc::SinkWriter::CSinkWriterFram"...
0x180037076  mov     [rsp+0E8h+var_68], rax
0x18003707e  mov     dword ptr [rsp+0E8h+arg_18], 15Fh
0x180037089  mov     qword ptr [rsp+0E8h+var_60], rdi
0x180037091  lea     rax, [rsp+0E8h+arg_10]
0x180037099  mov     [rsp+0E8h+var_A8], rax
0x18003709e  lea     rax, [rsp+0E8h+var_70]
0x1800370a3  mov     [rsp+0E8h+var_B0], rax
0x1800370a8  lea     rax, [rsp+0E8h+var_68]
0x1800370b0  mov     [rsp+0E8h+var_B8], rax
0x1800370b5  lea     rax, [rsp+0E8h+arg_18]
0x1800370bd  mov     [rsp+0E8h+var_C0], rax; char *
0x1800370c2  lea     rax, [rsp+0E8h+var_60]
0x1800370ca  mov     qword ptr [rsp+0E8h+var_C8], rax
0x1800370cf  lea     rdx, byte_1800AF3C5
0x1800370d6  lea     rcx, dword_1800C1058
0x1800370dd  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@334@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800370e2  mov     rax, [rsi]
0x1800370e5  mov     rdi, [rax+148h]
0x1800370ec  mov     rcx, [rsp+0E8h+var_98]
0x1800370f1  mov     [rsp+0E8h+var_98], r13
0x1800370f6  test    rcx, rcx
0x1800370f9  jz      short loc_180037108
0x1800370fb  mov     rdx, [rcx]
0x1800370fe  mov     rax, [rdx+10h]
0x180037102  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037107  nop
0x180037108  lea     rdx, [rsp+0E8h+var_98]
0x18003710d  mov     rcx, rsi
0x180037110  mov     rax, rdi
0x180037113  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037118  mov     rcx, [rsp+0E8h]; this
0x180037120  lea     rdx, aFailedToGetMed; "Failed to get media buffer"
0x180037127  mov     qword ptr [rsp+0E8h+var_C8], rdx; int
0x18003712c  mov     r9d, eax; char *
0x18003712f  lea     r8, aOnecoreuapTerm_10; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180037136  mov     edx, 162h; void *
0x18003713b  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180037140  mov     rcx, [rsp+0E8h+var_98]
0x180037145  mov     [rsp+0E8h+var_90], rcx
0x18003714a  test    rcx, rcx
0x18003714d  jz      short loc_180037160
0x18003714f  mov     rax, [rcx]
0x180037152  mov     rax, [rax+8]
0x180037156  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003715b  mov     rcx, [rsp+0E8h+var_90]
0x180037160  mov     [rsp+0E8h+arg_10], r13
0x180037168  mov     [rsp+0E8h+var_88], r13
0x18003716d  mov     [rsp+0E8h+var_80], r13
0x180037172  lea     rax, [rsp+0E8h+var_90]
0x180037177  mov     [rsp+0E8h+arg_18], rax
0x18003717f  test    rcx, rcx
0x180037182  jz      short loc_1800371C1
0x180037184  mov     rax, [rcx]
0x180037187  lea     r9, [rsp+0E8h+var_80+4]
0x18003718c  lea     r8, [rsp+0E8h+var_80]
0x180037191  lea     rdx, [rsp+0E8h+var_88]
0x180037196  mov     rax, [rax+18h]
0x18003719a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003719f  mov     rcx, [rsp+0E8h]; this
0x1800371a7  test    eax, eax
0x1800371a9  js      loc_180037542
0x1800371af  mov     r13d, dword ptr [rsp+0E8h+var_80+4]
0x1800371b4  mov     rax, [rsp+0E8h+var_88]
0x1800371b9  mov     [rsp+0E8h+arg_10], rax
0x1800371c1  mov     edx, [r12]; unsigned __int64
0x1800371c5  mov     rcx, [r15+28h]; this
0x1800371c9  call    ?OnFrameEncoded@ClientFrameRateTracker@Avenc@Rdp@@QEAAX_K@Z; Rdp::Avenc::ClientFrameRateTracker::OnFrameEncoded(unsigned __int64)
0x1800371ce  lea     edx, [r13+0FFFh]
0x1800371d5  and     edx, 0FFFFF000h
0x1800371db  add     edx, 1000h; unsigned __int64
0x1800371e1  xor     r9d, r9d; unsigned __int64
0x1800371e4  xor     r8d, r8d; unsigned int
0x1800371e7  mov     rcx, r14; this
0x1800371ea  call    ?AllocatePool@CFcWireEncoderWithBulkUncompressed@Avenc@Rdp@@QEAAX_KI0@Z; Rdp::Avenc::CFcWireEncoderWithBulkUncompressed::AllocatePool(unsigned __int64,uint,unsigned __int64)
0x1800371ef  mov     r9, [r15+8]
0x1800371f3  add     r9, 78h ; 'x'
0x1800371f7  mov     r8, [rsp+0E8h+var_78]
0x1800371fc  mov     edx, [r12]
0x180037200  mov     rcx, r14
0x180037203  call    ?StartFrame@?$CRdpEgfx@VCFcWireEncoderWithBulkUncompressed@Avenc@Rdp@@@Protocol@Rdp@@QEAAXI_KAEBU_GUID@@@Z; Rdp::Protocol::CRdpEgfx<Rdp::Avenc::CFcWireEncoderWithBulkUncompressed>::StartFrame(uint,unsigned __int64,_GUID const &)
0x180037208  xor     r8d, r8d
0x18003720b  xor     r9d, r9d
0x18003720e  mov     edx, [r12+4]
0x180037213  lea     rax, ds:0[rdx*8]
0x18003721b  mov     esi, 0FFFFFFFFh
0x180037220  cmp     rax, rsi
0x180037223  ja      short loc_180037235
0x180037225  lea     eax, ds:0[rdx*8]
0x18003722c  lea     ecx, [rax+4]
0x18003722f  cmp     ecx, eax
0x180037231  cmovnb  r8d, ecx
0x180037235  lea     rax, [rdx+rdx]
0x180037239  cmp     rax, rsi
0x18003723c  ja      short loc_180037242
0x18003723e  lea     r9d, [rdx+rdx]
0x180037242  xorps   xmm0, xmm0
0x180037245  movups  [rsp+0E8h+var_60], xmm0
0x18003724d  lea     eax, [r9+r8]
0x180037251  add     eax, r13d
0x180037254  mov     rdx, [r15+8]
0x180037258  mov     dword ptr [rsp+0E8h+var_C0], eax; char *
0x18003725c  lea     rax, [rsp+0E8h+var_60]
0x180037264  mov     qword ptr [rsp+0E8h+var_C8], rax
0x180037269  mov     r8d, 0Bh
0x18003726f  mov     edx, [rdx+88h]
0x180037275  mov     rcx, r14
0x180037278  call    ?WireToSurface1@?$CRdpEgfx@VCFcWireEncoderWithBulkUncompressed@Avenc@Rdp@@@Protocol@Rdp@@QEAAXIW4RDPGFX_CODECID@@W4RdpPixelFormat@@AEBUtagRECT@@I@Z; Rdp::Protocol::CRdpEgfx<Rdp::Avenc::CFcWireEncoderWithBulkUncompressed>::WireToSurface1(uint,RDPGFX_CODECID,RdpPixelFormat,tagRECT const &,uint)
0x18003727d  mov     edi, [r12+4]
0x180037282  xor     r15d, r15d
0x180037285  mov     r9d, 80070216h
0x18003728b  mov     eax, edi
0x18003728d  shl     rax, 3
0x180037291  cmp     rax, rsi
0x180037294  ja      short loc_1800372AA
0x180037296  lea     eax, ds:0[rdi*8]
0x18003729d  lea     ecx, [rax+4]
0x1800372a0  cmp     ecx, eax
0x1800372a2  jb      short loc_1800372AA
0x1800372a4  mov     r15d, ecx
0x1800372a7  xor     r9d, r9d; char *
0x1800372aa  mov     rcx, [rsp+0E8h]; this
0x1800372b2  lea     rax, aFailedToCalcul_0; "Failed to calculate size of Avc420Metab"...
0x1800372b9  mov     qword ptr [rsp+0E8h+var_C8], rax; int
0x1800372be  lea     r8, aOnecoreuapTerm_14; "onecoreuap\\termsrv\\rdp_bin\\win\\comm"...
0x1800372c5  mov     edx, 278h; void *
0x1800372ca  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800372cf  mov     edx, r15d; unsigned __int64
0x1800372d2  mov     rcx, r14; this
0x1800372d5  call    ?EnsureBuffer@CFcWireEncoderWithBulkUncompressed@Avenc@Rdp@@QEAAPEAX_K@Z; Rdp::Avenc::CFcWireEncoderWithBulkUncompressed::EnsureBuffer(unsigned __int64)
0x1800372da  mov     rsi, rax
0x1800372dd  mov     rcx, [rsp+0E8h]
0x1800372e5  mov     dword ptr [rsp+0E8h+var_B8], r15d
0x1800372ea  lea     rax, aUnableToEnsure_6; "Unable to ensure RFX_AVC420_METABLOCK1_"...
0x1800372f1  mov     [rsp+0E8h+var_C0], rax; char *
0x1800372f6  mov     qword ptr [rsp+0E8h+var_C8], rsi
0x1800372fb  mov     r9d, 8007000Eh
0x180037301  lea     r8, aOnecoreuapTerm_14; "onecoreuap\\termsrv\\rdp_bin\\win\\comm"...
0x180037308  mov     edx, 27Dh
0x18003730d  call    ??$Throw_HrIfNullMsg@PEAX$0A@@in1diag3@details@wil@@YAPEAXPEAXIPEBDJ01ZZ; wil::details::in1diag3::Throw_HrIfNullMsg<void *,0>(void *,uint,char const *,long,void *,char const *,...)
0x180037312  mov     [rsi], edi
0x180037314  xor     r8d, r8d
0x180037317  test    edi, edi
0x180037319  jz      short loc_18003735A
0x18003731b  xor     edx, edx
0x18003731d  mov     rcx, rdx
0x180037320  add     rcx, rcx
0x180037323  movzx   eax, word ptr [r12+rcx*8+8]
0x180037329  mov     [rsi+rdx*8+4], ax
0x18003732e  movzx   eax, word ptr [r12+rcx*8+0Ch]
0x180037334  mov     [rsi+rdx*8+6], ax
0x180037339  movzx   eax, word ptr [r12+rcx*8+10h]
0x18003733f  mov     [rsi+rdx*8+8], ax
0x180037344  movzx   eax, word ptr [r12+rcx*8+14h]
0x18003734a  mov     [rsi+rdx*8+0Ah], ax
0x18003734f  inc     r8d
0x180037352  inc     rdx
0x180037355  cmp     r8d, edi
0x180037358  jb      short loc_18003731D
0x18003735a  mov     edi, [r12+4]
0x18003735f  mov     eax, edi
0x180037361  add     rax, rax
0x180037364  mov     ecx, 0FFFFFFFFh
0x180037369  cmp     rax, rcx
0x18003736c  ja      short loc_180037376
0x18003736e  lea     esi, [rdi+rdi]
0x180037371  xor     r9d, r9d
0x180037374  jmp     short loc_18003737E
0x180037376  xor     esi, esi
0x180037378  mov     r9d, 80070216h; char *
0x18003737e  mov     rcx, [rsp+0E8h]; this
0x180037386  lea     rax, aFailedToCalcul; "Failed to calculate size of Avc420Metab"...
0x18003738d  mov     qword ptr [rsp+0E8h+var_C8], rax; int
0x180037392  lea     r8, aOnecoreuapTerm_14; "onecoreuap\\termsrv\\rdp_bin\\win\\comm"...
0x180037399  mov     edx, 292h; void *
0x18003739e  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800373a3  mov     edx, esi; unsigned __int64
0x1800373a5  mov     rcx, r14; this
0x1800373a8  call    ?EnsureBuffer@CFcWireEncoderWithBulkUncompressed@Avenc@Rdp@@QEAAPEAX_K@Z; Rdp::Avenc::CFcWireEncoderWithBulkUncompressed::EnsureBuffer(unsigned __int64)
0x1800373ad  mov     r15, rax
0x1800373b0  mov     rcx, [rsp+0E8h]
0x1800373b8  mov     dword ptr [rsp+0E8h+var_B8], esi
0x1800373bc  lea     rax, aUnableToEnsure_8; "Unable to ensure RFX_AVC420_METABLOCK2_"...
0x1800373c3  mov     [rsp+0E8h+var_C0], rax
0x1800373c8  mov     qword ptr [rsp+0E8h+var_C8], r15
0x1800373cd  mov     r9d, 8007000Eh
0x1800373d3  lea     r8, aOnecoreuapTerm_14; "onecoreuap\\termsrv\\rdp_bin\\win\\comm"...
0x1800373da  mov     edx, 297h
0x1800373df  call    ??$Throw_HrIfNullMsg@PEAX$0A@@in1diag3@details@wil@@YAPEAXPEAXIPEBDJ01ZZ; wil::details::in1diag3::Throw_HrIfNullMsg<void *,0>(void *,uint,char const *,long,void *,char const *,...)
0x1800373e4  xor     ecx, ecx
0x1800373e6  test    edi, edi
0x1800373e8  jz      short loc_1800373F7
0x1800373ea  mov     word ptr [r15+rcx*2], 6414h
0x1800373f1  inc     ecx
0x1800373f3  cmp     ecx, edi
0x1800373f5  jb      short loc_1800373EA
0x1800373f7  mov     r8d, r13d; unsigned __int64
0x1800373fa  mov     rdx, [rsp+0E8h+arg_10]; void *
0x180037402  mov     rcx, r14; this
0x180037405  call    ?WriteBuffer@CFcWireEncoder@Avenc@Rdp@@QEAAXPEAX_K@Z; Rdp::Avenc::CFcWireEncoder::WriteBuffer(void *,unsigned __int64)
  ... truncated ...
```
