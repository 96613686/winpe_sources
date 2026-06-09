# Rdp::Avenc::RdpProg::CRdpProgFrameProcessor::SendFrame(uint,unsigned __int64,uint,uint)

- ea: `0x180067508`
- end: `0x180067c20`
- name: `?SendFrame@CRdpProgFrameProcessor@RdpProg@Avenc@Rdp@@IEAAJI_KII@Z`
- size: `1816`
- prototype: `__int64 __fastcall(Rdp::Avenc::RdpProg::CRdpProgFrameProcessor *__hidden this, unsigned int, unsigned __int64, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `22`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180066960`

## callees

- `0x180002b38`
- `0x180003744`
- `0x180006580`
- `0x180007018`
- `0x18000e848`
- `0x1800103c0`
- `0x180010bc8`
- `0x18001143c`
- `0x180011490`
- `0x180022fb8`
- `0x180023b34`
- `0x180028840`
- `0x1800290d4`
- `0x18002b614`
- `0x18002b6c8`
- `0x18002b9a8`
- `0x18002d1bc`
- `0x18002dd40`
- `0x18002e014`
- `0x18005418c`
- `0x180067508`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180067687`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180067694`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180067a36`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180067a8a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180067687`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180067694`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180067a36`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180067a8a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18006761e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18006761e`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x180067592`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x180067592`
- `api-ms-win-core-synch-l1-2-0!WakeConditionVariable` at `0x180067a97`
- `api-ms-win-core-synch-l1-2-0!WakeConditionVariable` at `0x180067a97`

## string_xrefs

- `0x18006785d`: `onecoreuap\termsrv\rdp_bin\win\common/protocol/RdpEgfx/RdpEgfx.h`
- `0x1800678c8`: `onecoreuap\termsrv\rdp_bin\win\common/protocol/RdpEgfx/RdpEgfx.h`
- `0x180067927`: `onecoreuap\termsrv\rdp_bin\win\common/protocol/RdpEgfx/RdpEgfx.h`
- `0x180067983`: `onecoreuap\termsrv\rdp_bin\win\common/protocol/RdpEgfx/RdpEgfx.h`
- `0x1800675a1`: `Egfx protocol object is not available`
- `0x18006796c`: `Unable to ensure RDPGFX_DELETE_ENCODING_CONTEXT_PDU_SIZE`
- `0x1800678b1`: `CommitWireToSurface2 called with null Pdu`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall Rdp::Avenc::RdpProg::CRdpProgFrameProcessor::SendFrame(
        Rdp::Avenc::RdpProg::CRdpProgFrameProcessor *this,
        int a2,
        unsigned __int64 a3,
        int a4,
        unsigned int a5)
{
  volatile __int64 *v7; // rbx
  __int64 v8; // rax
  volatile signed __int32 *v9; // rdi
  Rdp::Avenc::CFcWireEncoderWithBulkUncompressed *v10; // r13
  char v11; // al
  char *v12; // r14
  RTL_SRWLOCK *v13; // rcx
  const struct _tlgProvider_t *v14; // rax
  int v15; // r8d
  int v16; // r9d
  _QWORD *v17; // r12
  __int64 v18; // rdx
  unsigned __int64 v19; // rcx
  size_t v20; // r8
  size_t v21; // rbx
  unsigned int v22; // eax
  unsigned __int64 v23; // rbx
  char *v24; // rbx
  bool v25; // cf
  void *v26; // r12
  unsigned int v27; // ecx
  _DWORD *v28; // rbx
  char *v29; // r15
  unsigned __int64 v30; // rax
  bool v31; // zf
  const struct _tlgProvider_t *v32; // rax
  int v33; // r8d
  int v34; // r9d
  const char *v35; // r9
  __int64 result; // rax
  volatile signed __int32 *v37; // rdi
  const struct _tlgProvider_t *v38; // rax
  _QWORD *v39; // [rsp+20h] [rbp-158h]
  _DWORD *v40; // [rsp+20h] [rbp-158h]
  char *v41; // [rsp+28h] [rbp-150h]
  char *v42; // [rsp+28h] [rbp-150h]
  char v43; // [rsp+40h] [rbp-138h]
  char v44[8]; // [rsp+48h] [rbp-130h] BYREF
  int v45; // [rsp+50h] [rbp-128h] BYREF
  unsigned __int64 v46; // [rsp+58h] [rbp-120h] BYREF
  int v47; // [rsp+60h] [rbp-118h]
  const char *v48; // [rsp+68h] [rbp-110h] BYREF
  unsigned __int64 v49; // [rsp+70h] [rbp-108h] BYREF
  unsigned __int64 v50; // [rsp+78h] [rbp-100h] BYREF
  unsigned __int64 v51; // [rsp+80h] [rbp-F8h] BYREF
  unsigned __int64 *v52; // [rsp+88h] [rbp-F0h]
  __int64 v53; // [rsp+90h] [rbp-E8h]
  char *v54; // [rsp+98h] [rbp-E0h]
  _QWORD v55[4]; // [rsp+A0h] [rbp-D8h] BYREF
  _OWORD v56[3]; // [rsp+C0h] [rbp-B8h] BYREF
  _OWORD v57[2]; // [rsp+F0h] [rbp-88h]
  _QWORD v58[6]; // [rsp+110h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+0h]

  v47 = a4;
  v49 = a3;
  LODWORD(v46) = a2;
  v51 = a3;
  v7 = (volatile __int64 *)((char *)this + 120);
  v8 = std::_Locked_pointer<std::_Ref_count_base>::_Lock_and_load((char *)this + 120);
  v9 = (volatile signed __int32 *)v8;
  v52 = (unsigned __int64 *)v8;
  v10 = (Rdp::Avenc::CFcWireEncoderWithBulkUncompressed *)*((_QWORD *)this + 14);
  v55[0] = v10;
  v55[1] = v8;
  if ( v8 )
    _InterlockedIncrement((volatile signed __int32 *)(v8 + 8));
  v11 = _InterlockedExchange64(v7, v8) & 3;
  if ( v11 == 2 )
    WakeByAddressAll((PVOID)v7);
  try
  {
    v41 = "Egfx protocol object is not available";
    v39 = v55;
    wil::details::in1diag3::Throw_HrIfNullMsg<wil::com_ptr_t<IPropertyStore,wil::err_exception_policy>,0>(
      retaddr,
      541,
      "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\rdpprogprocessor\\rdpprogframeprocessor.cpp",
      2147500035LL);
    v12 = *(char **)(*((_QWORD *)this + 16) + 112LL);
    v54 = v12;
    v55[2] = v12;
    if ( v12 )
      (*(void (__fastcall **)(char *))(*(_QWORD *)v12 + 8LL))(v12);
    memset_0(v56, 0, 0x4Cu);
    AcquireSRWLockExclusive((PSRWLOCK)v12 + 18);
    v13 = (RTL_SRWLOCK *)(v12 + 144);
    if ( v12[257] )
    {
      v56[0] = *(_OWORD *)(v12 + 180);
      v56[1] = *(_OWORD *)(v12 + 196);
      v56[2] = *(_OWORD *)(v12 + 212);
      v57[0] = *(_OWORD *)(v12 + 228);
      *(_OWORD *)((char *)v57 + 12) = *((_OWORD *)v12 + 15);
      v12[257] = 0;
      ReleaseSRWLockExclusive(v13);
      v43 = 1;
    }
    else
    {
      ReleaseSRWLockExclusive(v13);
      v43 = 0;
    }
    v14 = RdpGrfxPipelinePerfProvider::Provider();
    if ( *(_DWORD *)v14 > 5u )
    {
      *(_QWORD *)v44 = a3;
      v48 = "Begin";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
        (_DWORD)v14,
        (unsigned int)qword_1800B54F8,
        v15,
        v16,
        (__int64)&v48,
        (__int64)v44);
    }
    v45 = 0;
    v17 = (_QWORD *)((char *)this + 328);
    v18 = *((_QWORD *)this + 41);
    v19 = *((_QWORD *)this + 42) - v18;
    if ( a5 >= v19 )
    {
      if ( a5 > v19 )
      {
        if ( a5 <= (unsigned __int64)(*((_QWORD *)this + 43) - v18) )
        {
          v20 = a5 - v19;
          v21 = v20 + *((_QWORD *)this + 42);
          memset_0(*((void **)this + 42), 0, v20);
          *((_QWORD *)this + 42) = v21;
        }
        else
        {
          std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>((char *)this + 328, a5);
        }
      }
    }
    else
    {
      *((_QWORD *)this + 42) = v18 + a5;
    }
    v22 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, int *, _QWORD *, char *))(**((_QWORD **)this + 39) + 24LL))(
            *((_QWORD *)this + 39),
            *v17,
            a5,
            &v45,
            v39,
            v41);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0x22A,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\rdpprogprocessor\\rdpprogframeprocessor.cpp",
      (const char *)v22,
      (int)"EndEncodeFrame failed",
      v42);
    try
    {
      v23 = v49;
      Rdp::Avenc::CFcWireEncoderWithBulkUncompressed::AllocatePool(v10, ((v45 + 4095) & 0xFFFFF000) + 4096, 0x9C4u, v49);
    }
    catch ( ... )
    {
      v38 = RdpGrfxPipelinePerfProvider::Provider();
      if ( *(_DWORD *)v38 > 5u )
      {
        v58[4] = &v51;
        v58[5] = 8;
        tlgWriteTransfer_EventWriteTransfer(v38, byte_1800B54BB, 0, 0, 3, v58);
      }
      (*(void (__fastcall **)(char *))(*(_QWORD *)v54 + 16LL))(v54);
      v37 = (volatile signed __int32 *)v52;
      if ( v52 )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v52 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v37)(v37);
          if ( _InterlockedExchangeAdd(v37 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v37 + 8LL))(v37);
        }
      }
      return 0;
    }
    Rdp::Protocol::CRdpEgfx<Rdp::Avenc::CFcWireEncoderWithBulkUncompressed>::StartFrame(
      v10,
      (unsigned int)v46,
      v23,
      *((_QWORD *)this + 16) + 120LL);
    if ( v43 )
    {
      v52 = (unsigned __int64 *)((char *)v56 + 12);
      v53 = 64;
      Rdp::Protocol::CRdpEgfx<Rdp::Avenc::CFcWireEncoderWithBulkUncompressed>::DiagnosticInfo(v10);
    }
    LODWORD(v48) = *((_DWORD *)this + 80);
    *(_DWORD *)v44 = *(_DWORD *)(*((_QWORD *)this + 16) + 136LL);
    v24 = (char *)Rdp::Avenc::CFcWireEncoderWithBulkUncompressed::EnsureBuffer(v10, 0x15u);
    wil::details::in1diag3::Throw_HrIfNullMsg<void *,0>(
      retaddr,
      501,
      "onecoreuap\\termsrv\\rdp_bin\\win\\common/protocol/RdpEgfx/RdpEgfx.h",
      2147942414LL);
    *(_QWORD *)v24 = 2;
    *((_WORD *)v24 + 4) = *(_WORD *)v44;
    v25 = (_DWORD)v48 != 0;
    LODWORD(v48) = -(int)v48;
    *((_WORD *)v24 + 5) = v25 ? 0 : 9;
    *((_DWORD *)v24 + 3) = v47;
    v24[16] = 32;
    *(_DWORD *)(v24 + 17) = 0;
    *(_DWORD *)v44 = v45;
    v26 = (void *)*v17;
    wil::details::in1diag3::Throw_HrIfNullMsg<void *,0>(
      retaddr,
      525,
      "onecoreuap\\termsrv\\rdp_bin\\win\\common/protocol/RdpEgfx/RdpEgfx.h",
      2147942487LL);
    v27 = *(_DWORD *)v44;
    *((_DWORD *)v24 + 1) = *(_DWORD *)v44 + 21;
    *(_DWORD *)(v24 + 17) = v27;
    Rdp::Avenc::CFcWireEncoder::WriteBuffer(v10, v26, v27);
    v28 = Rdp::Avenc::CFcWireEncoderWithBulkUncompressed::EnsureBuffer(v10, 0xCu);
    wil::details::in1diag3::Throw_HrIfNullMsg<void *,0>(
      retaddr,
      420,
      "onecoreuap\\termsrv\\rdp_bin\\win\\common/protocol/RdpEgfx/RdpEgfx.h",
      2147942414LL);
    *v28 = 12;
    v28[1] = 12;
    v28[2] = *((_DWORD *)v10 + 22);
    LODWORD(v26) = *(_DWORD *)(*((_QWORD *)this + 16) + 136LL);
    v40 = Rdp::Avenc::CFcWireEncoderWithBulkUncompressed::EnsureBuffer(v10, 0xEu);
    wil::details::in1diag3::Throw_HrIfNullMsg<void *,0>(
      retaddr,
      362,
      "onecoreuap\\termsrv\\rdp_bin\\win\\common/protocol/RdpEgfx/RdpEgfx.h",
      2147942414LL);
    *v40 = 3;
    v40[1] = 14;
    *((_WORD *)v40 + 4) = (_WORD)v26;
    *(_DWORD *)((char *)v40 + 10) = v47;
    Rdp::Avenc::ClientFrameRateTracker::OnFrameEncoded(
      *((Rdp::Avenc::ClientFrameRateTracker **)this + 17),
      (unsigned int)v46);
    Rdp::Avenc::CFcWireEncoder::DetachPacket(v10, &v50);
    v29 = (char *)this + 192;
    v30 = v50;
    v50 = 0;
    v46 = v30;
    v52 = &v46;
    v54 = v29;
    if ( (unsigned int)mtx_do_lock(v29) )
      std::_Throw_Cpp_error(5);
    if ( *((_DWORD *)v29 + 19) == 0x7FFFFFFF )
    {
      *((_DWORD *)v29 + 19) = 2147483646;
      std::_Throw_Cpp_error(6);
    }
    std::deque<wil::com_ptr_t<Rdp::Avenc::IIoPacket,wil::err_exception_policy>>::push_back(v29 + 80, &v46);
    v31 = (*((_DWORD *)v29 + 19))-- == 1;
    if ( v31 )
    {
      *((_DWORD *)v29 + 18) = -1;
      ReleaseSRWLockExclusive((PSRWLOCK)v29 + 2);
    }
    if ( v46 )
      (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v46 + 16LL))(v46);
    if ( (unsigned int)mtx_do_lock(v12 + 344) )
      std::_Throw_Cpp_error(5);
    if ( *((_DWORD *)v12 + 105) == 0x7FFFFFFF )
    {
      *((_DWORD *)v12 + 105) = 2147483646;
      std::_Throw_Cpp_error(6);
    }
    ++*((_DWORD *)v12 + 125);
    v31 = (*((_DWORD *)v12 + 105))-- == 1;
    if ( v31 )
    {
      *((_DWORD *)v12 + 104) = -1;
      ReleaseSRWLockExclusive((PSRWLOCK)v12 + 45);
    }
    WakeConditionVariable((PCONDITION_VARIABLE)v12 + 54);
    v32 = RdpGrfxPipelinePerfProvider::Provider();
    if ( *(_DWORD *)v32 > 5u )
    {
      *(_DWORD *)v44 = v45;
      v46 = (unsigned __int64)"Stats";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
        (_DWORD)v32,
        (unsigned int)&word_1800B546E,
        v33,
        v34,
        (__int64)&v46,
        (__int64)&v49,
        (__int64)v44);
    }
    if ( v50 )
      (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v50 + 16LL))(v50);
    (*(void (__fastcall **)(char *))(*(_QWORD *)v12 + 16LL))(v12);
    if ( v9 )
    {
      if ( _InterlockedExchangeAdd(v9 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v9)(v9);
        if ( _InterlockedExchangeAdd(v9 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 8LL))(v9);
      }
    }
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x263,
                           (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\rdpprogprocessor\\rdpprogframeprocessor.cpp",
                           v35);
  }
  return result;
}

```

## disassembly

```asm
0x180067508  mov     [rsp+arg_8], rbx
0x18006750d  mov     [rsp+arg_18], rsi
0x180067512  push    rdi
0x180067513  push    r12
0x180067515  push    r13
0x180067517  push    r14
0x180067519  push    r15
0x18006751b  sub     rsp, 150h
0x180067522  mov     rax, cs:__security_cookie
0x180067529  xor     rax, rsp
0x18006752c  mov     [rsp+178h+var_38], rax
0x180067534  mov     [rsp+178h+var_118], r9d
0x180067539  mov     r12, r8
0x18006753c  mov     [rsp+178h+var_108], r8
0x180067541  mov     dword ptr [rsp+178h+var_120], edx
0x180067545  mov     r15, rcx
0x180067548  mov     [rsp+178h+var_F8], r8
0x180067550  lea     rbx, [rcx+78h]
0x180067554  mov     rcx, rbx; Address
0x180067557  call    ?_Lock_and_load@?$_Locked_pointer@V_Ref_count_base@std@@@std@@QEAAPEAV_Ref_count_base@2@XZ; std::_Locked_pointer<std::_Ref_count_base>::_Lock_and_load(void)
0x18006755c  mov     rdi, rax
0x18006755f  mov     [rsp+178h+var_F0], rax
0x180067567  mov     r13, [r15+70h]
0x18006756b  mov     [rsp+178h+var_D8], r13
0x180067573  mov     [rsp+178h+var_D0], rax
0x18006757b  xor     esi, esi
0x18006757d  test    rax, rax
0x180067580  jz      short loc_180067586
0x180067582  lock inc dword ptr [rax+8]
0x180067586  xchg    rax, [rbx]
0x180067589  and     al, 3
0x18006758b  cmp     al, 2
0x18006758d  jnz     short loc_180067599
0x18006758f  mov     rcx, rbx; Address
0x180067592  call    cs:__imp_WakeByAddressAll
0x180067598  nop
0x180067599  mov     rcx, [rsp+178h]
0x1800675a1  lea     rax, aEgfxProtocolOb; "Egfx protocol object is not available"
0x1800675a8  mov     [rsp+178h+var_150], rax
0x1800675ad  lea     rax, [rsp+178h+var_D8]
0x1800675b5  mov     qword ptr [rsp+178h+var_158], rax
0x1800675ba  mov     r9d, 80004003h
0x1800675c0  lea     r8, aOnecoreuapTerm_35; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x1800675c7  mov     edx, 21Dh
0x1800675cc  call    ??$Throw_HrIfNullMsg@V?$com_ptr_t@UIPropertyStore@@Uerr_exception_policy@wil@@@wil@@$0A@@in1diag3@details@wil@@YAXPEAXIPEBDJAEBV?$com_ptr_t@UIPropertyStore@@Uerr_exception_policy@wil@@@2@1ZZ; wil::details::in1diag3::Throw_HrIfNullMsg<wil::com_ptr_t<IPropertyStore,wil::err_exception_policy>,0>(void *,uint,char const *,long,wil::com_ptr_t<IPropertyStore,wil::err_exception_policy> const &,char const *,...)
0x1800675d1  mov     rax, [r15+80h]
0x1800675d8  mov     r14, [rax+70h]
0x1800675dc  mov     [rsp+178h+var_E0], r14
0x1800675e4  mov     [rsp+178h+var_C8], r14
0x1800675ec  test    r14, r14
0x1800675ef  jz      short loc_180067601
0x1800675f1  mov     rax, [r14]
0x1800675f4  mov     rcx, r14
0x1800675f7  mov     rax, [rax+8]
0x1800675fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067600  nop
0x180067601  xor     edx, edx; Val
0x180067603  lea     r8d, [rdx+4Ch]; Size
0x180067607  lea     rcx, [rsp+178h+var_B8]; void *
0x18006760f  call    memset_0
0x180067614  lea     rbx, [r14+90h]
0x18006761b  mov     rcx, rbx; SRWLock
0x18006761e  call    cs:__imp_AcquireSRWLockExclusive
0x180067624  mov     rcx, rbx; SRWLock
0x180067627  cmp     [r14+101h], sil
0x18006762e  jz      short loc_180067694
0x180067630  movups  xmm0, xmmword ptr [r14+0B4h]
0x180067638  movaps  [rsp+178h+var_B8], xmm0
0x180067640  movups  xmm1, xmmword ptr [r14+0C4h]
0x180067648  movaps  [rsp+178h+var_A8], xmm1
0x180067650  movups  xmm0, xmmword ptr [r14+0D4h]
0x180067658  movaps  [rsp+178h+var_98], xmm0
0x180067660  movups  xmm1, xmmword ptr [r14+0E4h]
0x180067668  movaps  xmmword ptr [rsp+178h+var_88], xmm1
0x180067670  movups  xmm0, xmmword ptr [r14+0F0h]
0x180067678  movups  xmmword ptr [rsp+178h+var_88+0Ch], xmm0
0x180067680  mov     [r14+101h], sil
0x180067687  call    cs:__imp_ReleaseSRWLockExclusive
0x18006768d  mov     [rsp+178h+var_138], 1
0x180067692  jmp     short loc_18006769F
0x180067694  call    cs:__imp_ReleaseSRWLockExclusive
0x18006769a  mov     [rsp+178h+var_138], sil
0x18006769f  call    ?Provider@RdpGrfxPipelinePerfProvider@@SAPEBU_tlgProvider_t@@XZ; RdpGrfxPipelinePerfProvider::Provider(void)
0x1800676a4  mov     ecx, [rax]
0x1800676a6  cmp     ecx, 5
0x1800676a9  jbe     short loc_1800676DF
0x1800676ab  mov     qword ptr [rsp+178h+var_130], r12
0x1800676b0  lea     rcx, aBegin; "Begin"
0x1800676b7  mov     [rsp+178h+var_110], rcx
0x1800676bc  lea     rcx, [rsp+178h+var_130]
0x1800676c1  mov     [rsp+178h+var_150], rcx; char *
0x1800676c6  lea     rcx, [rsp+178h+var_110]
0x1800676cb  mov     qword ptr [rsp+178h+var_158], rcx
0x1800676d0  lea     rdx, qword_1800B54F8
0x1800676d7  mov     rcx, rax
0x1800676da  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x1800676df  mov     [rsp+178h+var_128], esi
0x1800676e3  lea     r12, [r15+148h]
0x1800676ea  mov     rdx, [r12]
0x1800676ee  mov     r9, [r12+8]
0x1800676f3  mov     rcx, r9
0x1800676f6  sub     rcx, rdx
0x1800676f9  mov     r8d, [rsp+178h+arg_20]
0x180067701  cmp     r8, rcx
0x180067704  jnb     short loc_180067711
0x180067706  lea     rax, [rdx+r8]
0x18006770a  mov     [r12+8], rax
0x18006770f  jmp     short loc_180067743
0x180067711  jbe     short loc_180067743
0x180067713  mov     rax, [r12+10h]
0x180067718  sub     rax, rdx
0x18006771b  cmp     r8, rax
0x18006771e  jbe     short loc_18006772D
0x180067720  mov     rdx, r8
0x180067723  mov     rcx, r12
0x180067726  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18006772b  jmp     short loc_180067743
0x18006772d  sub     r8, rcx; Size
0x180067730  lea     rbx, [r8+r9]
0x180067734  xor     edx, edx; Val
0x180067736  mov     rcx, r9; void *
0x180067739  call    memset_0
0x18006773e  mov     [r12+8], rbx
0x180067743  mov     rcx, [r15+138h]
0x18006774a  mov     rax, [rcx]
0x18006774d  lea     r9, [rsp+178h+var_128]
0x180067752  mov     r8d, [rsp+178h+arg_20]
0x18006775a  mov     rdx, [r12]
0x18006775e  mov     rax, [rax+18h]
0x180067762  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067767  mov     rcx, [rsp+178h]; this
0x18006776f  lea     rdx, aEndencodeframe; "EndEncodeFrame failed"
0x180067776  mov     qword ptr [rsp+178h+var_158], rdx; int
0x18006777b  mov     r9d, eax; char *
0x18006777e  lea     r8, aOnecoreuapTerm_35; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180067785  mov     edx, 22Ah; void *
0x18006778a  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18006778f  nop
0x180067790  mov     edx, [rsp+178h+var_128]
0x180067794  add     edx, 0FFFh
0x18006779a  and     edx, 0FFFFF000h
0x1800677a0  add     edx, 1000h; unsigned __int64
0x1800677a6  mov     rbx, [rsp+178h+var_108]
0x1800677ab  mov     r9, rbx; unsigned __int64
0x1800677ae  mov     r8d, 9C4h; unsigned int
0x1800677b4  mov     rcx, r13; this
0x1800677b7  call    ?AllocatePool@CFcWireEncoderWithBulkUncompressed@Avenc@Rdp@@QEAAX_KI0@Z; Rdp::Avenc::CFcWireEncoderWithBulkUncompressed::AllocatePool(unsigned __int64,uint,unsigned __int64)
0x1800677bc  nop
0x1800677bd  mov     r9, [r15+80h]
0x1800677c4  add     r9, 78h ; 'x'
0x1800677c8  mov     r8, rbx
0x1800677cb  mov     edx, dword ptr [rsp+178h+var_120]
0x1800677cf  mov     rcx, r13
0x1800677d2  call    ?StartFrame@?$CRdpEgfx@VCFcWireEncoderWithBulkUncompressed@Avenc@Rdp@@@Protocol@Rdp@@QEAAXI_KAEBU_GUID@@@Z; Rdp::Protocol::CRdpEgfx<Rdp::Avenc::CFcWireEncoderWithBulkUncompressed>::StartFrame(uint,unsigned __int64,_GUID const &)
0x1800677d7  cmp     [rsp+178h+var_138], sil
0x1800677dc  jz      short loc_18006780A
0x1800677de  lea     rax, [rsp+178h+var_B8+0Ch]
0x1800677e6  mov     [rsp+178h+var_F0], rax
0x1800677ee  mov     [rsp+178h+var_E8], 40h ; '@'
0x1800677fa  lea     rdx, [rsp+178h+var_F0]
0x180067802  mov     rcx, r13; this
0x180067805  call    ?DiagnosticInfo@?$CRdpEgfx@VCFcWireEncoderWithBulkUncompressed@Avenc@Rdp@@@Protocol@Rdp@@QEAAXAEBV?$span@E$0?0@std@@@Z; Rdp::Protocol::CRdpEgfx<Rdp::Avenc::CFcWireEncoderWithBulkUncompressed>::DiagnosticInfo(std::span<uchar,-1> const &)
0x18006780a  mov     eax, [r15+140h]
0x180067811  mov     dword ptr [rsp+178h+var_110], eax
0x180067815  mov     rax, [r15+80h]
0x18006781c  mov     eax, [rax+88h]
0x180067822  mov     dword ptr [rsp+178h+var_130], eax
0x180067826  mov     edx, 15h; unsigned __int64
0x18006782b  mov     rcx, r13; this
0x18006782e  call    ?EnsureBuffer@CFcWireEncoderWithBulkUncompressed@Avenc@Rdp@@QEAAPEAX_K@Z; Rdp::Avenc::CFcWireEncoderWithBulkUncompressed::EnsureBuffer(unsigned __int64)
0x180067833  mov     rbx, rax
0x180067836  mov     rcx, [rsp+178h]
0x18006783e  mov     dword ptr [rsp+178h+var_148], 15h
0x180067846  lea     rax, aUnableToEnsure_12; "Unable to ensure RDPGFX_WIRE_TO_SURFACE"...
0x18006784d  mov     [rsp+178h+var_150], rax
0x180067852  mov     qword ptr [rsp+178h+var_158], rbx
0x180067857  mov     r9d, 8007000Eh
0x18006785d  lea     r8, aOnecoreuapTerm_14; "onecoreuap\\termsrv\\rdp_bin\\win\\comm"...
0x180067864  mov     edx, 1F5h
0x180067869  call    ??$Throw_HrIfNullMsg@PEAX$0A@@in1diag3@details@wil@@YAPEAXPEAXIPEBDJ01ZZ; wil::details::in1diag3::Throw_HrIfNullMsg<void *,0>(void *,uint,char const *,long,void *,char const *,...)
0x18006786e  mov     qword ptr [rbx], 2
0x180067875  mov     eax, dword ptr [rsp+178h+var_130]
0x180067879  mov     [rbx+8], ax
0x18006787d  neg     dword ptr [rsp+178h+var_110]
0x180067881  sbb     ax, ax
0x180067884  not     ax
0x180067887  and     ax, 9
0x18006788b  mov     [rbx+0Ah], ax
0x18006788f  mov     eax, [rsp+178h+var_118]
0x180067893  mov     [rbx+0Ch], eax
0x180067896  mov     byte ptr [rbx+10h], 20h ; ' '
0x18006789a  mov     [rbx+11h], esi
0x18006789d  mov     eax, [rsp+178h+var_128]
0x1800678a1  mov     dword ptr [rsp+178h+var_130], eax
0x1800678a5  mov     r12, [r12]
0x1800678a9  mov     rcx, [rsp+178h]
0x1800678b1  lea     rax, aCommitwiretosu; "CommitWireToSurface2 called with null P"...
0x1800678b8  mov     [rsp+178h+var_150], rax
0x1800678bd  mov     qword ptr [rsp+178h+var_158], rbx
0x1800678c2  mov     r9d, 80070057h
0x1800678c8  lea     r8, aOnecoreuapTerm_14; "onecoreuap\\termsrv\\rdp_bin\\win\\comm"...
0x1800678cf  mov     edx, 20Dh
0x1800678d4  call    ??$Throw_HrIfNullMsg@PEAX$0A@@in1diag3@details@wil@@YAPEAXPEAXIPEBDJ01ZZ; wil::details::in1diag3::Throw_HrIfNullMsg<void *,0>(void *,uint,char const *,long,void *,char const *,...)
0x1800678d9  mov     ecx, dword ptr [rsp+178h+var_130]
0x1800678dd  lea     eax, [rcx+15h]
0x1800678e0  mov     [rbx+4], eax
0x1800678e3  mov     [rbx+11h], ecx
0x1800678e6  mov     r8d, ecx; unsigned __int64
0x1800678e9  mov     rdx, r12; void *
0x1800678ec  mov     rcx, r13; this
0x1800678ef  call    ?WriteBuffer@CFcWireEncoder@Avenc@Rdp@@QEAAXPEAX_K@Z; Rdp::Avenc::CFcWireEncoder::WriteBuffer(void *,unsigned __int64)
0x1800678f4  mov     r12d, 0Ch
0x1800678fa  mov     edx, r12d; unsigned __int64
0x1800678fd  mov     rcx, r13; this
0x180067900  call    ?EnsureBuffer@CFcWireEncoderWithBulkUncompressed@Avenc@Rdp@@QEAAPEAX_K@Z; Rdp::Avenc::CFcWireEncoderWithBulkUncompressed::EnsureBuffer(unsigned __int64)
0x180067905  mov     rbx, rax
0x180067908  mov     rcx, [rsp+178h]
0x180067910  lea     rax, aUnableToEnsure_14; "Unable to ensure RDPGFX_END_FRAME_PDU_S"...
0x180067917  mov     [rsp+178h+var_150], rax
0x18006791c  mov     qword ptr [rsp+178h+var_158], rbx
0x180067921  mov     r9d, 8007000Eh
0x180067927  lea     r8, aOnecoreuapTerm_14; "onecoreuap\\termsrv\\rdp_bin\\win\\comm"...
0x18006792e  mov     edx, 1A4h
0x180067933  call    ??$Throw_HrIfNullMsg@PEAX$0A@@in1diag3@details@wil@@YAPEAXPEAXIPEBDJ01ZZ; wil::details::in1diag3::Throw_HrIfNullMsg<void *,0>(void *,uint,char const *,long,void *,char const *,...)
0x180067938  mov     [rbx], r12d
0x18006793b  mov     [rbx+4], r12d
0x18006793f  mov     eax, [r13+58h]
0x180067943  mov     [rbx+8], eax
0x180067946  mov     rax, [r15+80h]
0x18006794d  mov     r12d, [rax+88h]
0x180067954  mov     edx, 0Eh; unsigned __int64
0x180067959  mov     rcx, r13; this
0x18006795c  call    ?EnsureBuffer@CFcWireEncoderWithBulkUncompressed@Avenc@Rdp@@QEAAPEAX_K@Z; Rdp::Avenc::CFcWireEncoderWithBulkUncompressed::EnsureBuffer(unsigned __int64)
0x180067961  mov     rbx, rax
0x180067964  mov     rcx, [rsp+178h]
0x18006796c  lea     rax, aUnableToEnsure_3; "Unable to ensure RDPGFX_DELETE_ENCODING"...
0x180067973  mov     [rsp+178h+var_150], rax
0x180067978  mov     qword ptr [rsp+178h+var_158], rbx
0x18006797d  mov     r9d, 8007000Eh
0x180067983  lea     r8, aOnecoreuapTerm_14; "onecoreuap\\termsrv\\rdp_bin\\win\\comm"...
0x18006798a  mov     edx, 16Ah
0x18006798f  call    ??$Throw_HrIfNullMsg@PEAX$0A@@in1diag3@details@wil@@YAPEAXPEAXIPEBDJ01ZZ; wil::details::in1diag3::Throw_HrIfNullMsg<void *,0>(void *,uint,char const *,long,void *,char const *,...)
0x180067994  mov     dword ptr [rbx], 3
0x18006799a  mov     dword ptr [rbx+4], 0Eh
0x1800679a1  mov     [rbx+8], r12w
0x1800679a6  mov     eax, [rsp+178h+var_118]
0x1800679aa  mov     [rbx+0Ah], eax
0x1800679ad  mov     edx, dword ptr [rsp+178h+var_120]; unsigned __int64
0x1800679b1  mov     rcx, [r15+88h]; this
0x1800679b8  call    ?OnFrameEncoded@ClientFrameRateTracker@Avenc@Rdp@@QEAAX_K@Z; Rdp::Avenc::ClientFrameRateTracker::OnFrameEncoded(unsigned __int64)
0x1800679bd  lea     rdx, [rsp+178h+var_100]
0x1800679c2  mov     rcx, r13
0x1800679c5  call    ?DetachPacket@CFcWireEncoder@Avenc@Rdp@@QEAA?AV?$com_ptr_t@UIIoPacket@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@XZ; Rdp::Avenc::CFcWireEncoder::DetachPacket(void)
0x1800679ca  nop
0x1800679cb  add     r15, 0C0h
0x1800679d2  mov     rax, [rsp+178h+var_100]
0x1800679d7  mov     [rsp+178h+var_100], rsi
0x1800679dc  mov     [rsp+178h+var_120], rax
0x1800679e1  lea     rax, [rsp+178h+var_120]
0x1800679e6  mov     [rsp+178h+var_F0], rax
0x1800679ee  mov     [rsp+178h+var_E0], r15
0x1800679f6  mov     rcx, r15
0x1800679f9  call    mtx_do_lock
0x1800679fe  test    eax, eax
0x180067a00  jnz     loc_180067BE5
0x180067a06  mov     r12d, 7FFFFFFFh
0x180067a0c  cmp     [r15+4Ch], r12d
0x180067a10  jz      loc_180067BEF
0x180067a16  lea     rcx, [r15+50h]
0x180067a1a  lea     rdx, [rsp+178h+var_120]
0x180067a1f  call    ?push_back@?$deque@V?$com_ptr_t@UIIoPacket@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UIIoPacket@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@QEAAX$$QEAV?$com_ptr_t@UIIoPacket@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@@Z; std::deque<wil::com_ptr_t<Rdp::Avenc::IIoPacket,wil::err_exception_policy>>::push_back(wil::com_ptr_t<Rdp::Avenc::IIoPacket,wil::err_exception_policy> &&)
0x180067a24  nop
0x180067a25  or      ebx, 0FFFFFFFFh
0x180067a28  add     [r15+4Ch], ebx
0x180067a2c  jnz     short loc_180067A3D
0x180067a2e  mov     [r15+48h], ebx
0x180067a32  lea     rcx, [r15+10h]; SRWLock
0x180067a36  call    cs:__imp_ReleaseSRWLockExclusive
0x180067a3c  nop
0x180067a3d  mov     rcx, [rsp+178h+var_120]
0x180067a42  test    rcx, rcx
0x180067a45  jz      short loc_180067A54
0x180067a47  mov     rax, [rcx]
0x180067a4a  mov     rax, [rax+10h]
0x180067a4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067a53  nop
0x180067a54  lea     r15, [r14+158h]
0x180067a5b  mov     rcx, r15
0x180067a5e  call    mtx_do_lock
0x180067a63  test    eax, eax
0x180067a65  jnz     loc_180067C02
0x180067a6b  cmp     [r15+4Ch], r12d
0x180067a6f  jz      loc_180067C0C
0x180067a75  inc     dword ptr [r14+1F4h]
0x180067a7c  add     [r15+4Ch], ebx
0x180067a80  jnz     short loc_180067A90
0x180067a82  mov     [r15+48h], ebx
0x180067a86  lea     rcx, [r15+10h]; SRWLock
0x180067a8a  call    cs:__imp_ReleaseSRWLockExclusive
0x180067a90  lea     rcx, [r14+1B0h]; ConditionVariable
  ... truncated ...
```
