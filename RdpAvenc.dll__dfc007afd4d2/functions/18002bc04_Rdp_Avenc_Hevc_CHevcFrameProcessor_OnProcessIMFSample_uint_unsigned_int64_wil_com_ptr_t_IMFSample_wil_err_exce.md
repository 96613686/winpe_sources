# Rdp::Avenc::Hevc::CHevcFrameProcessor::OnProcessIMFSample(uint,unsigned __int64,wil::com_ptr_t<IMFSample,wil::err_exception_policy>,Rdp::Protocol::_RDPGFX_AVC420_QUANT_QUALITY const *,uint,tagRECT const *)

- ea: `0x18002bc04`
- end: `0x18002c689`
- name: `?OnProcessIMFSample@CHevcFrameProcessor@Hevc@Avenc@Rdp@@QEAAJI_KV?$com_ptr_t@UIMFSample@@Uerr_exception_policy@wil@@@wil@@PEBU_RDPGFX_AVC420_QUANT_QUALITY@Protocol@4@IPEBUtagRECT@@@Z`
- size: `2693`
- prototype: `__int64 __fastcall(__int64, int, unsigned __int64, __int64 *, __int64, unsigned int, __int64)`
- caller_count: `1`
- callee_count: `29`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18002e960`

## callees

- `0x180002b38`
- `0x180003744`
- `0x180006580`
- `0x1800069a0`
- `0x180006f8a`
- `0x180007018`
- `0x1800072b0`
- `0x18000e848`
- `0x18000ec04`
- `0x1800103c0`
- `0x180010bc8`
- `0x18001143c`
- `0x180011490`
- `0x180022fb8`
- `0x180023b34`
- `0x180026af8`
- `0x180028840`
- `0x1800290d4`
- `0x18002b614`
- `0x18002b6c8`
- `0x18002b9a8`
- `0x18002bc04`
- `0x18002d1bc`
- `0x18002d844`
- `0x18002dd40`
- `0x18002e014`
- `0x1800327cc`
- `0x180082e90`
- `0x180089010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18002c1fd`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18002c1fd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002bd87`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002bd94`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002c39f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002c3f3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002bd87`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002bd94`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002c39f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002c3f3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002bd1e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002bd1e`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x18002bc9a`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x18002bc9a`
- `api-ms-win-core-synch-l1-2-0!WakeConditionVariable` at `0x18002c400`
- `api-ms-win-core-synch-l1-2-0!WakeConditionVariable` at `0x18002c400`

## string_xrefs

- `0x18002c0f5`: `onecoreuap\termsrv\rdp_bin\win\common/protocol/RdpEgfx/RdpEgfx.h`
- `0x18002c136`: `onecoreuap\termsrv\rdp_bin\win\common/protocol/RdpEgfx/RdpEgfx.h`
- `0x18002c25b`: `onecoreuap\termsrv\rdp_bin\win\common/protocol/RdpEgfx/RdpEgfx.h`
- `0x18002bca9`: `Egfx protocol object is not available`

## pseudocode

```c
__int64 __fastcall Rdp::Avenc::Hevc::CHevcFrameProcessor::OnProcessIMFSample(
        __int64 a1,
        int a2,
        unsigned __int64 a3,
        __int64 *a4,
        __int64 a5,
        unsigned int a6,
        __int64 a7)
{
  void *v9; // rdi
  __int64 v10; // rax
  volatile signed __int32 *v11; // r14
  Rdp::Avenc::CFcWireEncoderWithBulkUncompressed *v12; // r12
  __int64 v13; // r15
  RTL_SRWLOCK *v14; // rcx
  unsigned int v15; // eax
  unsigned int v16; // edi
  void *v17; // rsi
  __int64 *v18; // rdi
  unsigned int v19; // eax
  __int64 v20; // rcx
  int v21; // eax
  __int64 v22; // rdi
  __int64 (__fastcall *v23)(__int64, __int64 *); // rsi
  __int64 v24; // rcx
  unsigned int v25; // eax
  __int64 v26; // rcx
  int v27; // esi
  int v28; // eax
  const struct _tlgProvider_t *v29; // rax
  int v30; // r8d
  int v31; // r9d
  unsigned __int64 v32; // rdi
  int v33; // r9d
  int v34; // edi
  __int64 v35; // rcx
  _WORD *v36; // rdx
  __int64 v37; // r8
  _WORD *v38; // r9
  int v39; // eax
  __int64 v40; // rsi
  _WORD *v41; // rdi
  void *v42; // rcx
  int v43; // esi
  __int64 v44; // rdi
  Rdp::Avenc::Hevc::RateControlHW *v45; // rcx
  const struct _tlgProvider_t *v46; // rax
  int v47; // r8d
  int v48; // r9d
  const char *v49; // rax
  bool v50; // zf
  __int64 v51; // rcx
  int v52; // eax
  __int64 v54; // rcx
  int v55; // eax
  volatile signed __int32 *v56; // rsi
  const struct _tlgProvider_t *v57; // rax
  int v58; // [rsp+20h] [rbp-1B8h]
  unsigned int *v59; // [rsp+20h] [rbp-1B8h]
  _DWORD *v60; // [rsp+20h] [rbp-1B8h]
  char *v61; // [rsp+28h] [rbp-1B0h]
  char *v62; // [rsp+28h] [rbp-1B0h]
  char *v63; // [rsp+28h] [rbp-1B0h]
  char v64; // [rsp+40h] [rbp-198h]
  bool v65; // [rsp+41h] [rbp-197h]
  _DWORD v66[3]; // [rsp+44h] [rbp-194h] BYREF
  size_t Size; // [rsp+50h] [rbp-188h] BYREF
  const char *v68; // [rsp+58h] [rbp-180h] BYREF
  __int64 v69; // [rsp+60h] [rbp-178h] BYREF
  unsigned __int64 v70; // [rsp+68h] [rbp-170h]
  unsigned __int64 v71; // [rsp+70h] [rbp-168h] BYREF
  __int64 v72; // [rsp+78h] [rbp-160h] BYREF
  void *v73; // [rsp+80h] [rbp-158h] BYREF
  int v74; // [rsp+88h] [rbp-150h] BYREF
  int v75; // [rsp+8Ch] [rbp-14Ch] BYREF
  void *v76; // [rsp+90h] [rbp-148h] BYREF
  __int128 v77; // [rsp+98h] [rbp-140h] BYREF
  const char *v78; // [rsp+A8h] [rbp-130h] BYREF
  void *Src; // [rsp+B0h] [rbp-128h]
  unsigned __int64 v80; // [rsp+B8h] [rbp-120h] BYREF
  __int64 *v81; // [rsp+C0h] [rbp-118h]
  __int64 *v82; // [rsp+C8h] [rbp-110h]
  __int64 v83; // [rsp+D0h] [rbp-108h]
  void *Block; // [rsp+D8h] [rbp-100h]
  Rdp::Avenc::CFcWireEncoderWithBulkUncompressed *v85; // [rsp+E0h] [rbp-F8h]
  __int64 v86; // [rsp+E8h] [rbp-F0h]
  __int64 v87; // [rsp+F0h] [rbp-E8h]
  void *v88; // [rsp+F8h] [rbp-E0h]
  __int64 *v89; // [rsp+100h] [rbp-D8h]
  _OWORD v90[3]; // [rsp+110h] [rbp-C8h] BYREF
  _OWORD v91[2]; // [rsp+140h] [rbp-98h]
  _QWORD v92[6]; // [rsp+160h] [rbp-78h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1D8h] [rbp+0h]

  v81 = a4;
  v71 = a3;
  LODWORD(v70) = a2;
  v80 = a3;
  v82 = a4;
  v69 = 0;
  v9 = (void *)(a1 + 120);
  v10 = std::_Locked_pointer<std::_Ref_count_base>::_Lock_and_load((volatile void *)(a1 + 120));
  v11 = (volatile signed __int32 *)v10;
  *(_QWORD *)&v77 = v10;
  v12 = *(Rdp::Avenc::CFcWireEncoderWithBulkUncompressed **)(a1 + 112);
  v85 = v12;
  v86 = v10;
  if ( v10 )
    _InterlockedIncrement((volatile signed __int32 *)(v10 + 8));
  if ( (_InterlockedExchange64((volatile __int64 *)v9, v10) & 3) == 2 )
    WakeByAddressAll(v9);
  wil::details::in1diag3::Throw_HrIfNullMsg<wil::com_ptr_t<IPropertyStore,wil::err_exception_policy>,0>(
    retaddr,
    502,
    "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\hevcprocessor\\hevcframeprocessor.cpp",
    2147500035LL);
  v13 = *(_QWORD *)(*(_QWORD *)(a1 + 136) + 112LL);
  v87 = v13;
  if ( v13 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 8LL))(v13);
  memset_0(v90, 0, 0x4Cu);
  AcquireSRWLockExclusive((PSRWLOCK)(v13 + 144));
  v14 = (RTL_SRWLOCK *)(v13 + 144);
  if ( *(_BYTE *)(v13 + 257) )
  {
    v90[0] = *(_OWORD *)(v13 + 180);
    v90[1] = *(_OWORD *)(v13 + 196);
    v90[2] = *(_OWORD *)(v13 + 212);
    v91[0] = *(_OWORD *)(v13 + 228);
    *(_OWORD *)((char *)v91 + 12) = *(_OWORD *)(v13 + 240);
    *(_BYTE *)(v13 + 257) = 0;
    ReleaseSRWLockExclusive(v14);
    v64 = 1;
  }
  else
  {
    ReleaseSRWLockExclusive(v14);
    v64 = 0;
  }
  LODWORD(Size) = 0;
  v15 = (*(__int64 (__fastcall **)(__int64, const IID *, size_t *))(*(_QWORD *)*a4 + 112LL))(
          *a4,
          &MF_NALU_LENGTH_INFORMATION,
          &Size);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x1FE,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\hevcprocessor\\hevcframeprocessor.cpp",
    (const char *)v15,
    (int)"InternalOutSample->GetBlobSize failed - NALU length info required by MF decoder",
    "Egfx protocol object is not available");
  v16 = Size;
  v17 = operator new[]((unsigned int)Size);
  Src = v17;
  memset_0(v17, 0, v16);
  v88 = v17;
  v18 = v81;
  v19 = (*(__int64 (__fastcall **)(__int64, const IID *, void *, _QWORD, _QWORD))(*(_QWORD *)*v81 + 120LL))(
          *v81,
          &MF_NALU_LENGTH_INFORMATION,
          v17,
          (unsigned int)Size,
          0);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x202,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\hevcprocessor\\hevcframeprocessor.cpp",
    (const char *)v19,
    (int)"Failed to get NALU length info",
    v61);
  v20 = *v18;
  v66[0] = 0;
  if ( (*(int (__fastcall **)(__int64, const GUID *, _DWORD *))(*(_QWORD *)v20 + 56LL))(
         v20,
         &MFSampleExtension_CleanPoint,
         v66) >= 0 )
  {
    v21 = v66[0];
  }
  else
  {
    v21 = 0;
    v66[0] = 0;
  }
  v65 = v21 != 0;
  v22 = *v18;
  v23 = *(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)v22 + 328LL);
  v24 = v69;
  v69 = 0;
  if ( v24 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
  v25 = v23(v22, &v69);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x209,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\hevcprocessor\\hevcframeprocessor.cpp",
    (const char *)v25,
    (int)"Failed to get media buffer",
    v62);
  v26 = v69;
  v72 = v69;
  if ( v69 )
  {
    (*(void (**)(void))(*(_QWORD *)v69 + 8LL))();
    v26 = v72;
  }
  v76 = 0;
  v73 = 0;
  v74 = 0;
  v27 = 0;
  v66[0] = 0;
  v75 = 0;
  v89 = &v72;
  if ( v26 )
  {
    v28 = (*(__int64 (__fastcall **)(__int64, void **, int *, int *))(*(_QWORD *)v26 + 24LL))(v26, &v73, &v74, &v75);
    if ( v28 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x75,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\HevcProcessor/HevcFrameProcessor.h",
        (const char *)(unsigned int)v28,
        v58);
    v27 = v75;
    v66[0] = v75;
    v76 = v73;
  }
  v83 = v13;
  Block = Src;
  v29 = RdpGrfxPipelinePerfProvider::Provider();
  v32 = v71;
  if ( *(_DWORD *)v29 > 5u )
  {
    *(_QWORD *)&v66[1] = v71;
    v68 = "Begin";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
      (_DWORD)v29,
      (unsigned int)byte_1800AE76B,
      v30,
      v31,
      (__int64)&v68,
      (__int64)&v66[1]);
  }
  try
  {
    Rdp::Avenc::CFcWireEncoderWithBulkUncompressed::AllocatePool(v12, ((v27 + 4095) & 0xFFFFF000) + 4096, 0x9C4u, v32);
  }
  catch ( ... )
  {
    v57 = RdpGrfxPipelinePerfProvider::Provider();
    if ( *(_DWORD *)v57 > 5u )
    {
      v92[4] = &v80;
      v92[5] = 8;
      tlgWriteTransfer_EventWriteTransfer(v57, &word_1800AE72E, 0, 0, 3, v92);
    }
    v54 = v72;
    if ( v72 )
    {
      v55 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v72 + 32LL))(v72);
      if ( v55 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x7D,
          (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\HevcProcessor/HevcFrameProcessor.h",
          (const char *)(unsigned int)v55,
          v58);
      v54 = v72;
    }
    if ( v54 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
    if ( Block )
      operator delete(Block);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v83 + 16LL))(v83);
    v56 = (volatile signed __int32 *)v77;
    if ( (_QWORD)v77 )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v77 + 8), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v56)(v56);
        if ( _InterlockedExchangeAdd(v56 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v56 + 8LL))(v56);
      }
    }
    if ( v69 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v69 + 16LL))(v69);
    if ( *v82 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)*v82 + 16LL))(*v82);
    return 0;
  }
  Rdp::Protocol::CRdpEgfx<Rdp::Avenc::CFcWireEncoderWithBulkUncompressed>::StartFrame(
    v12,
    (unsigned int)v70,
    v32,
    *(_QWORD *)(a1 + 136) + 120LL);
  if ( v64 )
  {
    *(_QWORD *)&v77 = (char *)v90 + 12;
    *((_QWORD *)&v77 + 1) = 64;
    Rdp::Protocol::CRdpEgfx<Rdp::Avenc::CFcWireEncoderWithBulkUncompressed>::DiagnosticInfo(v12);
  }
  v34 = Size;
  v66[1] = Size;
  LODWORD(v68) = v27 + Size + 10 * a6 + 9;
  v77 = 0;
  Rdp::Protocol::CRdpEgfx<Rdp::Avenc::CFcWireEncoderWithBulkUncompressed>::WireToSurface1(
    (_DWORD)v12,
    *(_DWORD *)(*(_QWORD *)(a1 + 136) + 136LL),
    16,
    v33,
    (__int64)&v77,
    (_DWORD)v68);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x2AC,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\common/protocol/RdpEgfx/RdpEgfx.h",
    0,
    (int)"Failed to calculate size of Hevc420Metablock",
    v63);
  v59 = (unsigned int *)Rdp::Avenc::CFcWireEncoderWithBulkUncompressed::EnsureBuffer(v12, v34 + 10 * a6 + 9);
  wil::details::in1diag3::Throw_HrIfNullMsg<void *,0>(
    retaddr,
    688,
    "onecoreuap\\termsrv\\rdp_bin\\win\\common/protocol/RdpEgfx/RdpEgfx.h",
    2147942414LL);
  *v59 = a6;
  v36 = v59 + 1;
  v37 = 0;
  if ( a6 )
  {
    do
    {
      *v36 = *(_WORD *)(a7 + 16LL * (unsigned int)v37);
      v36[1] = *(_WORD *)(a7 + 16LL * (unsigned int)v37 + 4);
      v36[2] = *(_WORD *)(a7 + 16LL * (unsigned int)v37 + 8);
      v36[3] = *(_WORD *)(a7 + 16LL * (unsigned int)v37 + 12);
      v36 += 4;
      LODWORD(v37) = v37 + 1;
    }
    while ( (unsigned int)v37 < a6 );
    v38 = v36;
    LODWORD(v37) = 0;
    do
    {
      v35 = (unsigned int)v37;
      v38[(unsigned int)v37] = *(_WORD *)(a5 + 2LL * (unsigned int)v37);
      ++v36;
      v37 = (unsigned int)(v37 + 1);
    }
    while ( (unsigned int)v37 < a6 );
  }
  v39 = v66[1];
  v40 = v66[1];
  *(_DWORD *)v36 = v66[1];
  v41 = v36 + 2;
  if ( v39 )
  {
    if ( v36 != (_WORD *)-4LL )
    {
      v42 = v36 + 2;
      if ( Src )
      {
        memcpy_0(v42, Src, (unsigned int)v40);
        goto LABEL_34;
      }
      memset_0(v42, 0, (unsigned int)v40);
    }
    *(_DWORD *)_o__errno(v35, v36, v37) = 22;
    invalid_parameter_noinfo();
  }
LABEL_34:
  *((_BYTE *)v41 + v40) = v65;
  v43 = v66[0];
  Rdp::Avenc::CFcWireEncoder::WriteBuffer(v12, v76, v66[0]);
  v60 = Rdp::Avenc::CFcWireEncoderWithBulkUncompressed::EnsureBuffer(v12, 0xCu);
  wil::details::in1diag3::Throw_HrIfNullMsg<void *,0>(
    retaddr,
    420,
    "onecoreuap\\termsrv\\rdp_bin\\win\\common/protocol/RdpEgfx/RdpEgfx.h",
    2147942414LL);
  *v60 = 12;
  v60[1] = 12;
  v60[2] = *((_DWORD *)v12 + 22);
  Rdp::Avenc::ClientFrameRateTracker::OnFrameEncoded(
    *(Rdp::Avenc::ClientFrameRateTracker **)(a1 + 144),
    (unsigned int)v70);
  v44 = *(_QWORD *)(*(_QWORD *)(a1 + 128) + 88LL);
  v45 = *(Rdp::Avenc::Hevc::RateControlHW **)(v44 + 96);
  if ( v45 )
    Rdp::Avenc::Hevc::RateControlHW::Update(v45, 8 * (_DWORD)v68);
  *(_DWORD *)(a1 + 196) = *(unsigned __int8 *)(v44 + 90);
  *(_DWORD *)(a1 + 192) += (_DWORD)v68;
  v46 = RdpGrfxPipelinePerfProvider::Provider();
  if ( *(_DWORD *)v46 > 5u )
  {
    v66[1] = v43;
    v76 = (void *)v71;
    v71 = (unsigned __int64)"Stats";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      (_DWORD)v46,
      (unsigned int)byte_1800AE6E1,
      v47,
      v48,
      (__int64)&v71,
      (__int64)&v76,
      (__int64)&v66[1]);
  }
  Rdp::Avenc::CFcWireEncoder::DetachPacket(v12, &v78);
  v49 = v78;
  v78 = 0;
  v68 = v49;
  *(_QWORD *)&v77 = &v68;
  v83 = a1 + 200;
  if ( (unsigned int)mtx_do_lock(a1 + 200) )
    std::_Throw_Cpp_error(5);
  if ( *(_DWORD *)(a1 + 276) == 0x7FFFFFFF )
  {
    *(_DWORD *)(a1 + 276) = 2147483646;
    std::_Throw_Cpp_error(6);
  }
  std::deque<wil::com_ptr_t<Rdp::Avenc::IIoPacket,wil::err_exception_policy>>::push_back(a1 + 280, &v68);
  v50 = (*(_DWORD *)(a1 + 276))-- == 1;
  if ( v50 )
  {
    *(_DWORD *)(a1 + 272) = -1;
    ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 216));
  }
  if ( v68 )
    (*(void (__fastcall **)(const char *))(*(_QWORD *)v68 + 16LL))(v68);
  if ( (unsigned int)mtx_do_lock(v13 + 368) )
    std::_Throw_Cpp_error(5);
  if ( *(_DWORD *)(v13 + 444) == 0x7FFFFFFF )
  {
    *(_DWORD *)(v13 + 444) = 2147483646;
    std::_Throw_Cpp_error(6);
  }
  ++*(_DWORD *)(v13 + 524);
  v50 = (*(_DWORD *)(v13 + 444))-- == 1;
  if ( v50 )
  {
    *(_DWORD *)(v13 + 440) = -1;
    ReleaseSRWLockExclusive((PSRWLOCK)(v13 + 384));
  }
  WakeConditionVariable((PCONDITION_VARIABLE)(v13 + 456));
  if ( v78 )
    (*(void (__fastcall **)(const char *))(*(_QWORD *)v78 + 16LL))(v78);
  v51 = v72;
  if ( v72 )
  {
    v52 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v72 + 32LL))(v72);
    if ( v52 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x7D,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\HevcProcessor/HevcFrameProcessor.h",
        (const char *)(unsigned int)v52,
        (int)v60);
    v51 = v72;
  }
  if ( v51 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
  if ( Src )
    operator delete(Src);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  if ( v11 )
  {
    if ( _InterlockedExchangeAdd(v11 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v11)(v11);
      if ( _InterlockedExchangeAdd(v11 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 8LL))(v11);
    }
  }
  if ( v69 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v69 + 16LL))(v69);
  if ( *v81 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)*v81 + 16LL))(*v81);
  return 0;
}

```

## disassembly

```asm
0x18002bc04  push    rbx
0x18002bc06  push    rsi
0x18002bc07  push    rdi
0x18002bc08  push    r12
0x18002bc0a  push    r13
0x18002bc0c  push    r14
0x18002bc0e  push    r15
0x18002bc10  sub     rsp, 1A0h
0x18002bc17  mov     rax, cs:__security_cookie
0x18002bc1e  xor     rax, rsp
0x18002bc21  mov     [rsp+1D8h+var_48], rax
0x18002bc29  mov     rsi, r9
0x18002bc2c  mov     [rsp+1D8h+var_118], r9
0x18002bc34  mov     rax, r8
0x18002bc37  mov     [rsp+1D8h+var_168], rax
0x18002bc3c  mov     dword ptr [rsp+1D8h+var_170], edx
0x18002bc40  mov     r13, rcx
0x18002bc43  mov     [rsp+1D8h+var_120], rax
0x18002bc4b  mov     [rsp+1D8h+var_110], r9
0x18002bc53  xor     ebx, ebx
0x18002bc55  mov     [rsp+1D8h+var_178], rbx
0x18002bc5a  lea     rdi, [rcx+78h]
0x18002bc5e  mov     rcx, rdi; Address
0x18002bc61  call    ?_Lock_and_load@?$_Locked_pointer@V_Ref_count_base@std@@@std@@QEAAPEAV_Ref_count_base@2@XZ; std::_Locked_pointer<std::_Ref_count_base>::_Lock_and_load(void)
0x18002bc66  mov     r14, rax
0x18002bc69  mov     qword ptr [rsp+1D8h+var_140], rax
0x18002bc71  mov     r12, [r13+70h]
0x18002bc75  mov     [rsp+1D8h+var_F8], r12
0x18002bc7d  mov     [rsp+1D8h+var_F0], rax
0x18002bc85  test    rax, rax
0x18002bc88  jz      short loc_18002BC8E
0x18002bc8a  lock inc dword ptr [rax+8]
0x18002bc8e  xchg    rax, [rdi]
0x18002bc91  and     al, 3
0x18002bc93  cmp     al, 2
0x18002bc95  jnz     short loc_18002BCA1
0x18002bc97  mov     rcx, rdi; Address
0x18002bc9a  call    cs:__imp_WakeByAddressAll
0x18002bca0  nop
0x18002bca1  mov     rcx, [rsp+1D8h]
0x18002bca9  lea     rax, aEgfxProtocolOb; "Egfx protocol object is not available"
0x18002bcb0  mov     [rsp+1D8h+var_1B0], rax; char *
0x18002bcb5  lea     rax, [rsp+1D8h+var_F8]
0x18002bcbd  mov     qword ptr [rsp+1D8h+var_1B8], rax
0x18002bcc2  mov     r9d, 80004003h
0x18002bcc8  lea     r8, aOnecoreuapTerm_57; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18002bccf  mov     edx, 1F6h
0x18002bcd4  call    ??$Throw_HrIfNullMsg@V?$com_ptr_t@UIPropertyStore@@Uerr_exception_policy@wil@@@wil@@$0A@@in1diag3@details@wil@@YAXPEAXIPEBDJAEBV?$com_ptr_t@UIPropertyStore@@Uerr_exception_policy@wil@@@2@1ZZ; wil::details::in1diag3::Throw_HrIfNullMsg<wil::com_ptr_t<IPropertyStore,wil::err_exception_policy>,0>(void *,uint,char const *,long,wil::com_ptr_t<IPropertyStore,wil::err_exception_policy> const &,char const *,...)
0x18002bcd9  mov     rax, [r13+88h]
0x18002bce0  mov     r15, [rax+70h]
0x18002bce4  mov     [rsp+1D8h+var_E8], r15
0x18002bcec  test    r15, r15
0x18002bcef  jz      short loc_18002BD01
0x18002bcf1  mov     rax, [r15]
0x18002bcf4  mov     rcx, r15
0x18002bcf7  mov     rax, [rax+8]
0x18002bcfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bd00  nop
0x18002bd01  xor     edx, edx; Val
0x18002bd03  lea     r8d, [rdx+4Ch]; Size
0x18002bd07  lea     rcx, [rsp+1D8h+var_C8]; void *
0x18002bd0f  call    memset_0
0x18002bd14  lea     rdi, [r15+90h]
0x18002bd1b  mov     rcx, rdi; SRWLock
0x18002bd1e  call    cs:__imp_AcquireSRWLockExclusive
0x18002bd24  mov     rcx, rdi; SRWLock
0x18002bd27  cmp     [r15+101h], bl
0x18002bd2e  jz      short loc_18002BD94
0x18002bd30  movups  xmm0, xmmword ptr [r15+0B4h]
0x18002bd38  movaps  [rsp+1D8h+var_C8], xmm0
0x18002bd40  movups  xmm1, xmmword ptr [r15+0C4h]
0x18002bd48  movaps  [rsp+1D8h+var_B8], xmm1
0x18002bd50  movups  xmm0, xmmword ptr [r15+0D4h]
0x18002bd58  movaps  [rsp+1D8h+var_A8], xmm0
0x18002bd60  movups  xmm1, xmmword ptr [r15+0E4h]
0x18002bd68  movaps  xmmword ptr [rsp+1D8h+var_98], xmm1
0x18002bd70  movups  xmm0, xmmword ptr [r15+0F0h]
0x18002bd78  movups  xmmword ptr [rsp+1D8h+var_98+0Ch], xmm0
0x18002bd80  mov     [r15+101h], bl
0x18002bd87  call    cs:__imp_ReleaseSRWLockExclusive
0x18002bd8d  mov     [rsp+1D8h+var_198], 1
0x18002bd92  jmp     short loc_18002BD9E
0x18002bd94  call    cs:__imp_ReleaseSRWLockExclusive
0x18002bd9a  mov     [rsp+1D8h+var_198], bl
0x18002bd9e  mov     dword ptr [rsp+1D8h+Size], ebx
0x18002bda2  mov     rcx, [rsi]
0x18002bda5  mov     rax, [rcx]
0x18002bda8  lea     r8, [rsp+1D8h+Size]
0x18002bdad  lea     rdx, MF_NALU_LENGTH_INFORMATION
0x18002bdb4  mov     rax, [rax+70h]
0x18002bdb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bdbd  mov     rcx, [rsp+1D8h]; this
0x18002bdc5  lea     rdx, aInternaloutsam; "InternalOutSample->GetBlobSize failed -"...
0x18002bdcc  mov     qword ptr [rsp+1D8h+var_1B8], rdx; int
0x18002bdd1  mov     r9d, eax; char *
0x18002bdd4  lea     r8, aOnecoreuapTerm_57; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18002bddb  mov     edx, 1FEh; void *
0x18002bde0  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18002bde5  mov     edi, dword ptr [rsp+1D8h+Size]
0x18002bde9  mov     ecx, edi; unsigned __int64
0x18002bdeb  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18002bdf0  mov     rsi, rax
0x18002bdf3  mov     [rsp+1D8h+Src], rax
0x18002bdfb  mov     r8d, edi; Size
0x18002bdfe  xor     edx, edx; Val
0x18002be00  mov     rcx, rax; void *
0x18002be03  call    memset_0
0x18002be08  mov     [rsp+1D8h+var_E0], rsi
0x18002be10  mov     rdi, [rsp+1D8h+var_118]
0x18002be18  mov     rcx, [rdi]
0x18002be1b  mov     rax, [rcx]
0x18002be1e  mov     qword ptr [rsp+1D8h+var_1B8], rbx
0x18002be23  mov     r9d, dword ptr [rsp+1D8h+Size]
0x18002be28  mov     r8, rsi
0x18002be2b  lea     rdx, MF_NALU_LENGTH_INFORMATION
0x18002be32  mov     rax, [rax+78h]
0x18002be36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002be3b  mov     rcx, [rsp+1D8h]; this
0x18002be43  lea     rdx, aFailedToGetNal; "Failed to get NALU length info"
0x18002be4a  mov     qword ptr [rsp+1D8h+var_1B8], rdx; int
0x18002be4f  mov     r9d, eax; char *
0x18002be52  lea     r8, aOnecoreuapTerm_57; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18002be59  mov     edx, 202h; void *
0x18002be5e  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18002be63  mov     rcx, [rdi]
0x18002be66  mov     dword ptr [rsp+1D8h+var_194], ebx
0x18002be6a  mov     rax, [rcx]
0x18002be6d  lea     r8, [rsp+1D8h+var_194]
0x18002be72  lea     rdx, MFSampleExtension_CleanPoint
0x18002be79  mov     rax, [rax+38h]
0x18002be7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002be82  test    eax, eax
0x18002be84  jns     short loc_18002BE8E
0x18002be86  mov     eax, ebx
0x18002be88  mov     dword ptr [rsp+1D8h+var_194], ebx
0x18002be8c  jmp     short loc_18002BE92
0x18002be8e  mov     eax, dword ptr [rsp+1D8h+var_194]
0x18002be92  test    eax, eax
0x18002be94  setnz   [rsp+1D8h+var_197]
0x18002be99  mov     rdi, [rdi]
0x18002be9c  mov     rax, [rdi]
0x18002be9f  mov     rsi, [rax+148h]
0x18002bea6  mov     rcx, [rsp+1D8h+var_178]
0x18002beab  mov     [rsp+1D8h+var_178], rbx
0x18002beb0  test    rcx, rcx
0x18002beb3  jz      short loc_18002BEC2
0x18002beb5  mov     rdx, [rcx]
0x18002beb8  mov     rax, [rdx+10h]
0x18002bebc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bec1  nop
0x18002bec2  lea     rdx, [rsp+1D8h+var_178]
0x18002bec7  mov     rcx, rdi
0x18002beca  mov     rax, rsi
0x18002becd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bed2  mov     rcx, [rsp+1D8h]; this
0x18002beda  lea     rdx, aFailedToGetMed; "Failed to get media buffer"
0x18002bee1  mov     qword ptr [rsp+1D8h+var_1B8], rdx; int
0x18002bee6  mov     r9d, eax; char *
0x18002bee9  lea     r8, aOnecoreuapTerm_57; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18002bef0  mov     edx, 209h; void *
0x18002bef5  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18002befa  mov     rcx, [rsp+1D8h+var_178]
0x18002beff  mov     [rsp+1D8h+var_160], rcx
0x18002bf04  test    rcx, rcx
0x18002bf07  jz      short loc_18002BF1A
0x18002bf09  mov     rax, [rcx]
0x18002bf0c  mov     rax, [rax+8]
0x18002bf10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bf15  mov     rcx, [rsp+1D8h+var_160]
0x18002bf1a  mov     [rsp+1D8h+var_148], rbx
0x18002bf22  mov     [rsp+1D8h+var_158], rbx
0x18002bf2a  mov     [rsp+1D8h+var_150], ebx
0x18002bf31  mov     esi, ebx
0x18002bf33  mov     dword ptr [rsp+1D8h+var_194], ebx
0x18002bf37  mov     [rsp+1D8h+var_14C], ebx
0x18002bf3e  lea     rax, [rsp+1D8h+var_160]
0x18002bf43  mov     [rsp+1D8h+var_D8], rax
0x18002bf4b  test    rcx, rcx
0x18002bf4e  jz      short loc_18002BF9F
0x18002bf50  mov     rax, [rcx]
0x18002bf53  lea     r9, [rsp+1D8h+var_14C]
0x18002bf5b  lea     r8, [rsp+1D8h+var_150]
0x18002bf63  lea     rdx, [rsp+1D8h+var_158]
0x18002bf6b  mov     rax, [rax+18h]
0x18002bf6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bf74  mov     rcx, [rsp+1D8h]; this
0x18002bf7c  test    eax, eax
0x18002bf7e  js      loc_18002C63F
0x18002bf84  mov     esi, [rsp+1D8h+var_14C]
0x18002bf8b  mov     dword ptr [rsp+1D8h+var_194], esi
0x18002bf8f  mov     rax, [rsp+1D8h+var_158]
0x18002bf97  mov     [rsp+1D8h+var_148], rax
0x18002bf9f  mov     [rsp+1D8h+var_108], r15
0x18002bfa7  mov     rax, [rsp+1D8h+Src]
0x18002bfaf  mov     [rsp+1D8h+Block], rax
0x18002bfb7  call    ?Provider@RdpGrfxPipelinePerfProvider@@SAPEBU_tlgProvider_t@@XZ; RdpGrfxPipelinePerfProvider::Provider(void)
0x18002bfbc  mov     ecx, [rax]
0x18002bfbe  cmp     ecx, 5
0x18002bfc1  jbe     short loc_18002BFFE
0x18002bfc3  mov     rdi, [rsp+1D8h+var_168]
0x18002bfc8  mov     qword ptr [rsp+1D8h+var_194+4], rdi
0x18002bfcd  lea     rcx, aBegin; "Begin"
0x18002bfd4  mov     [rsp+1D8h+var_180], rcx
0x18002bfd9  lea     rcx, [rsp+1D8h+var_194+4]
0x18002bfde  mov     [rsp+1D8h+var_1B0], rcx
0x18002bfe3  lea     rcx, [rsp+1D8h+var_180]
0x18002bfe8  mov     qword ptr [rsp+1D8h+var_1B8], rcx
0x18002bfed  lea     rdx, byte_1800AE76B
0x18002bff4  mov     rcx, rax
0x18002bff7  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x18002bffc  jmp     short loc_18002C003
0x18002bffe  mov     rdi, [rsp+1D8h+var_168]
0x18002c003  lea     edx, [rsi+0FFFh]
0x18002c009  and     edx, 0FFFFF000h
0x18002c00f  add     edx, 1000h; unsigned __int64
0x18002c015  mov     r9, rdi; unsigned __int64
0x18002c018  mov     r8d, 9C4h; unsigned int
0x18002c01e  mov     rcx, r12; this
0x18002c021  call    ?AllocatePool@CFcWireEncoderWithBulkUncompressed@Avenc@Rdp@@QEAAX_KI0@Z; Rdp::Avenc::CFcWireEncoderWithBulkUncompressed::AllocatePool(unsigned __int64,uint,unsigned __int64)
0x18002c026  nop
0x18002c027  mov     r9, [r13+88h]
0x18002c02e  add     r9, 78h ; 'x'
0x18002c032  mov     r8, rdi
0x18002c035  mov     edx, dword ptr [rsp+1D8h+var_170]
0x18002c039  mov     rcx, r12
0x18002c03c  call    ?StartFrame@?$CRdpEgfx@VCFcWireEncoderWithBulkUncompressed@Avenc@Rdp@@@Protocol@Rdp@@QEAAXI_KAEBU_GUID@@@Z; Rdp::Protocol::CRdpEgfx<Rdp::Avenc::CFcWireEncoderWithBulkUncompressed>::StartFrame(uint,unsigned __int64,_GUID const &)
0x18002c041  cmp     [rsp+1D8h+var_198], bl
0x18002c045  jz      short loc_18002C073
0x18002c047  lea     rax, [rsp+1D8h+var_C8+0Ch]
0x18002c04f  mov     qword ptr [rsp+1D8h+var_140], rax
0x18002c057  mov     qword ptr [rsp+1D8h+var_140+8], 40h ; '@'
0x18002c063  lea     rdx, [rsp+1D8h+var_140]
0x18002c06b  mov     rcx, r12; this
0x18002c06e  call    ?DiagnosticInfo@?$CRdpEgfx@VCFcWireEncoderWithBulkUncompressed@Avenc@Rdp@@@Protocol@Rdp@@QEAAXAEBV?$span@E$0?0@std@@@Z; Rdp::Protocol::CRdpEgfx<Rdp::Avenc::CFcWireEncoderWithBulkUncompressed>::DiagnosticInfo(std::span<uchar,-1> const &)
0x18002c073  mov     edi, dword ptr [rsp+1D8h+Size]
0x18002c077  mov     dword ptr [rsp+1D8h+var_194+4], edi
0x18002c07b  mov     eax, [rsp+1D8h+arg_28]
0x18002c082  lea     eax, [rax+rax*4]
0x18002c085  lea     eax, ds:9[rax*2]
0x18002c08c  add     eax, edi
0x18002c08e  add     eax, esi
0x18002c090  mov     dword ptr [rsp+1D8h+var_180], eax
0x18002c094  xorps   xmm0, xmm0
0x18002c097  movups  [rsp+1D8h+var_140], xmm0
0x18002c09f  mov     rdx, [r13+88h]
0x18002c0a6  mov     dword ptr [rsp+1D8h+var_1B0], eax; char *
0x18002c0aa  lea     rax, [rsp+1D8h+var_140]
0x18002c0b2  mov     qword ptr [rsp+1D8h+var_1B8], rax
0x18002c0b7  mov     r8d, 10h
0x18002c0bd  mov     edx, [rdx+88h]
0x18002c0c3  mov     rcx, r12
0x18002c0c6  call    ?WireToSurface1@?$CRdpEgfx@VCFcWireEncoderWithBulkUncompressed@Avenc@Rdp@@@Protocol@Rdp@@QEAAXIW4RDPGFX_CODECID@@W4RdpPixelFormat@@AEBUtagRECT@@I@Z; Rdp::Protocol::CRdpEgfx<Rdp::Avenc::CFcWireEncoderWithBulkUncompressed>::WireToSurface1(uint,RDPGFX_CODECID,RdpPixelFormat,tagRECT const &,uint)
0x18002c0cb  mov     eax, [rsp+1D8h+arg_28]
0x18002c0d2  lea     eax, [rax+rax*4]
0x18002c0d5  lea     esi, ds:9[rax*2]
0x18002c0dc  add     esi, edi
0x18002c0de  mov     rcx, [rsp+1D8h]; this
0x18002c0e6  lea     rax, aFailedToCalcul_1; "Failed to calculate size of Hevc420Meta"...
0x18002c0ed  mov     qword ptr [rsp+1D8h+var_1B8], rax; int
0x18002c0f2  xor     r9d, r9d; char *
0x18002c0f5  lea     r8, aOnecoreuapTerm_14; "onecoreuap\\termsrv\\rdp_bin\\win\\comm"...
0x18002c0fc  mov     edx, 2ACh; void *
0x18002c101  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18002c106  mov     edx, esi; unsigned __int64
0x18002c108  mov     rcx, r12; this
0x18002c10b  call    ?EnsureBuffer@CFcWireEncoderWithBulkUncompressed@Avenc@Rdp@@QEAAPEAX_K@Z; Rdp::Avenc::CFcWireEncoderWithBulkUncompressed::EnsureBuffer(unsigned __int64)
0x18002c110  mov     rdi, rax
0x18002c113  mov     rcx, [rsp+1D8h]
0x18002c11b  mov     dword ptr [rsp+1D8h+var_1A8], esi
0x18002c11f  lea     rax, aUnableToEnsure_15; "Unable to ensure RFX_HEVC420_METABLOCK_"...
0x18002c126  mov     [rsp+1D8h+var_1B0], rax
0x18002c12b  mov     qword ptr [rsp+1D8h+var_1B8], rdi
0x18002c130  mov     r9d, 8007000Eh
0x18002c136  lea     r8, aOnecoreuapTerm_14; "onecoreuap\\termsrv\\rdp_bin\\win\\comm"...
0x18002c13d  mov     edx, 2B0h
0x18002c142  call    ??$Throw_HrIfNullMsg@PEAX$0A@@in1diag3@details@wil@@YAPEAXPEAXIPEBDJ01ZZ; wil::details::in1diag3::Throw_HrIfNullMsg<void *,0>(void *,uint,char const *,long,void *,char const *,...)
0x18002c147  mov     r10d, [rsp+1D8h+arg_28]
0x18002c14f  mov     [rdi], r10d
0x18002c152  lea     rdx, [rdi+4]
0x18002c156  mov     r8d, ebx
0x18002c159  test    r10d, r10d
0x18002c15c  jz      short loc_18002C1C4
0x18002c15e  mov     r9, [rsp+1D8h+arg_30]
0x18002c166  mov     ecx, r8d
0x18002c169  add     rcx, rcx
0x18002c16c  movzx   eax, word ptr [r9+rcx*8]
0x18002c171  mov     [rdx], ax
0x18002c174  movzx   eax, word ptr [r9+rcx*8+4]
0x18002c17a  mov     [rdx+2], ax
0x18002c17e  movzx   eax, word ptr [r9+rcx*8+8]
0x18002c184  mov     [rdx+4], ax
0x18002c188  movzx   eax, word ptr [r9+rcx*8+0Ch]
0x18002c18e  mov     [rdx+6], ax
0x18002c192  add     rdx, 8
0x18002c196  inc     r8d
0x18002c199  cmp     r8d, r10d
0x18002c19c  jb      short loc_18002C166
0x18002c19e  mov     r9, rdx
0x18002c1a1  mov     r8d, ebx
0x18002c1a4  mov     ecx, r8d
  ... truncated ...
```
