# Rdp::Avenc::SinkWriter::CSinkWriterProcessor::CommitMonitors(void)

- ea: `0x180032970`
- end: `0x180032cc0`
- name: `?CommitMonitors@CSinkWriterProcessor@SinkWriter@Avenc@Rdp@@UEAAJXZ`
- size: `848`
- prototype: `__int64 __fastcall(Rdp::Avenc::SinkWriter::CSinkWriterProcessor *__hidden this)`
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000e848`
- `0x1800126b0`
- `0x1800146bc`
- `0x180015480`
- `0x18001a810`
- `0x180021dac`
- `0x1800222d8`
- `0x180022c1c`
- `0x180022fb8`
- `0x180023ee4`
- `0x180025a10`
- `0x180026d7c`
- `0x180032970`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180032b64`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180032b64`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180032bcf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180032bcf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800329dc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180032c61`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800329dc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180032c61`

## string_xrefs

- `0x180032a77`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\common/ProcessorBase.h`
- `0x180032a3b`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\sinkwriterprocessor\sinkwriterprocessor.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Rdp::Avenc::SinkWriter::CSinkWriterProcessor::CommitMonitors(
        Rdp::Avenc::SinkWriter::CSinkWriterProcessor *this)
{
  char v2; // di
  bool v3; // si
  bool v4; // r14
  char CurrentThreadId; // al
  int v6; // r8d
  int v7; // edx
  int *v8; // r9
  unsigned int Int32; // eax
  int *v10; // r9
  unsigned int v11; // eax
  unsigned int *v12; // r9
  unsigned int UInt32; // eax
  unsigned int *v14; // r9
  unsigned int v15; // eax
  const char *v16; // r9
  unsigned __int64 v17; // rcx
  unsigned int v18; // edx
  bool v19; // bl
  char v20; // al
  int v21; // r8d
  int v22; // edx
  __int64 result; // rax
  int v24; // [rsp+20h] [rbp-88h]
  int v25; // [rsp+20h] [rbp-88h]
  int v26; // [rsp+28h] [rbp-80h]
  char *v27; // [rsp+28h] [rbp-80h]
  char *v28; // [rsp+28h] [rbp-80h]
  char *v29; // [rsp+28h] [rbp-80h]
  char *v30; // [rsp+28h] [rbp-80h]
  int v31; // [rsp+28h] [rbp-80h]
  char *v32; // [rsp+30h] [rbp-78h]
  __int64 v33[2]; // [rsp+60h] [rbp-48h] BYREF
  __int64 v34; // [rsp+70h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]
  unsigned __int64 v36; // [rsp+B0h] [rbp+8h] BYREF

  v2 = 1;
  v3 = WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
  v4 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v3 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    CurrentThreadId = GetCurrentThreadId();
    LOBYTE(v6) = v4;
    LOBYTE(v7) = v3;
    WPP_RECORDER_AND_TRACE_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v7,
      v6,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v24,
      v26,
      16,
      &WPP_f1a190f3335e3be81643dcf04f2aa623_Traceguids,
      CurrentThreadId);
  }
  try
  {
    LOBYTE(v24) = *((_BYTE *)this + 176) == 0;
    wil::details::in1diag3::Throw_HrIfMsg(
      retaddr,
      (void *)0xC0,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\sinkwriterprocessor\\sinkwriterprocessor.cpp",
      (const char *)0x8000FFFFLL,
      v24,
      (bool)"Processor is not started",
      v32);
    Int32 = Rdp::Utils::Props::IPropertyStore_GetInt32(
              *((Rdp::Utils::Props **)this + 4),
              (struct IPropertyStore *)&PKEY_VirtualDesktop_Origin_X,
              (const struct _tagpropertykey *)((char *)this + 84),
              v8);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0x10B,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\common/ProcessorBase.h",
      (const char *)Int32,
      (int)"Failed to retrieve PKEY_VirtualDesktop_Origin_X",
      v27);
    v11 = Rdp::Utils::Props::IPropertyStore_GetInt32(
            *((Rdp::Utils::Props **)this + 4),
            (struct IPropertyStore *)&PKEY_VirtualDesktop_Origin_Y,
            (const struct _tagpropertykey *)((char *)this + 88),
            v10);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0x112,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\common/ProcessorBase.h",
      (const char *)v11,
      (int)"Failed to retrieve PKEY_VirtualDesktop_Origin_Y",
      v28);
    UInt32 = Rdp::Utils::Props::IPropertyStore_GetUInt32(
               *((Rdp::Utils::Props **)this + 4),
               (struct IPropertyStore *)&PKEY_VirtualDesktop_Width,
               (const struct _tagpropertykey *)((char *)this + 92),
               v12);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0x11C,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\common/ProcessorBase.h",
      (const char *)UInt32,
      (int)"Failed to retrieve PKEY_VirtualDesktop_Width property",
      v29);
    v15 = Rdp::Utils::Props::IPropertyStore_GetUInt32(
            *((Rdp::Utils::Props **)this + 4),
            (struct IPropertyStore *)&PKEY_VirtualDesktop_Height,
            (const struct _tagpropertykey *)((char *)this + 96),
            v14);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0x123,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\common/ProcessorBase.h",
      (const char *)v15,
      (int)"Failed to retrieve PKEY_VirtualDesktop_Height property",
      v30);
    if ( *((_QWORD *)this + 23) )
    {
      *(_OWORD *)v33 = 0;
      v34 = 0;
      AcquireSRWLockShared((PSRWLOCK)this + 8);
      v17 = *((_QWORD *)this + 7);
      v36 = v17;
      if ( v17 )
      {
        if ( v17 > 0xFFFFFFFFFFFFFFFLL )
          std::vector<wil::com_ptr_t<ds::nanocom::IStreamFormat,wil::err_exception_policy>>::_Xlength();
        std::vector<tagRECT>::_Reallocate<0>(v33, &v36);
      }
      std::transform_std::_Tree_iterator_std::_Tree_val_std::_Tree_simple_types_std::pair__GUID_const__wil::com_ptr_t_Rdp::Avenc::RdpProg::CRdpProgMonitorContext_wil::err_exception_policy__________std::back_insert_iterator_std::vector_tagRECT_std::allocator_tagRECT_______Rdp::Avenc::RdpProg::CRdpProgProcessor::CommitMonitors_::_12_::_lambda_1___(
        &v36,
        **((_QWORD **)this + 6),
        *((_QWORD *)this + 6),
        v33);
      ReleaseSRWLockShared((PSRWLOCK)this + 8);
      Rdp::Avenc::CFcWireEncoderWithBulkUncompressed::AllocatePool(
        *((Rdp::Avenc::CFcWireEncoderWithBulkUncompressed **)this + 23),
        0x1000u,
        0,
        0);
      Rdp::Protocol::CRdpEgfx<Rdp::Avenc::CFcWireEncoderWithBulkUncompressed>::ResetGraphics(
        *((Rdp::Avenc::CFcWireEncoderWithBulkUncompressed **)this + 23),
        *((_DWORD *)this + 23),
        *((_DWORD *)this + 24),
        (v33[1] - v33[0]) >> 4,
        v33[0]);
      Rdp::Avenc::CFcWireEncoder::Flush(*((Rdp::Avenc::CFcWireEncoder **)this + 23), v18);
      std::vector<tagRECT>::~vector<tagRECT>(v33);
    }
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
    {
      v2 = 0;
    }
    v19 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v20 = GetCurrentThreadId();
      LOBYTE(v21) = v19;
      LOBYTE(v22) = v2;
      WPP_RECORDER_AND_TRACE_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v22,
        v21,
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v25,
        v31,
        17,
        &WPP_f1a190f3335e3be81643dcf04f2aa623_Traceguids,
        v20);
    }
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xE7,
                           (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\sinkwriterprocessor\\sinkwriterprocessor.cpp",
                           v16);
  }
  return result;
}

```

## disassembly

```asm
0x180032970  mov     [rsp+arg_8], rbx
0x180032975  mov     [rsp+arg_10], rsi
0x18003297a  push    rdi
0x18003297b  push    r12
0x18003297d  push    r13
0x18003297f  push    r14
0x180032981  push    r15
0x180032983  sub     rsp, 80h
0x18003298a  mov     rbx, rcx
0x18003298d  lea     r13, WPP_GLOBAL_Control
0x180032994  mov     rax, cs:WPP_GLOBAL_Control
0x18003299b  mov     dil, 1
0x18003299e  cmp     rax, r13
0x1800329a1  jz      short loc_1800329B4
0x1800329a3  test    [rax+1Ch], dil
0x1800329a7  jz      short loc_1800329B4
0x1800329a9  cmp     byte ptr [rax+19h], 4
0x1800329ad  jb      short loc_1800329B4
0x1800329af  mov     sil, dil
0x1800329b2  jmp     short loc_1800329B7
0x1800329b4  xor     sil, sil
0x1800329b7  lea     rax, WPP_RECORDER_INITIALIZED
0x1800329be  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1800329c5  setnz   r14b
0x1800329c9  test    sil, sil
0x1800329cc  jnz     short loc_1800329DC
0x1800329ce  test    r14b, r14b
0x1800329d1  jnz     short loc_1800329DC
0x1800329d3  lea     r15, WPP_f1a190f3335e3be81643dcf04f2aa623_Traceguids
0x1800329da  jmp     short loc_180032A13
0x1800329dc  call    cs:__imp_GetCurrentThreadId
0x1800329e2  mov     dword ptr [rsp+0A8h+var_68], eax; char
0x1800329e6  lea     r15, WPP_f1a190f3335e3be81643dcf04f2aa623_Traceguids
0x1800329ed  mov     [rsp+0A8h+MessageGuid], r15; MessageGuid
0x1800329f2  mov     word ptr [rsp+0A8h+var_78], 10h; char *
0x1800329f9  mov     rcx, cs:WPP_GLOBAL_Control
0x180032a00  mov     r9, [rcx+28h]; int
0x180032a04  mov     r8b, r14b; int
0x180032a07  mov     dl, sil; int
0x180032a0a  mov     rcx, [rcx+10h]; int
0x180032a0e  call    WPP_RECORDER_AND_TRACE_SF_D
0x180032a13  cmp     byte ptr [rbx+0B0h], 0
0x180032a1a  setz    al
0x180032a1d  mov     rcx, [rsp+0A8h]; this
0x180032a25  lea     rdx, aProcessorIsNot; "Processor is not started"
0x180032a2c  mov     [rsp+0A8h+var_80], rdx; int
0x180032a31  mov     byte ptr [rsp+0A8h+var_88], al; int
0x180032a35  mov     r9d, 8000FFFFh; char *
0x180032a3b  lea     r8, aOnecoreuapTerm_30; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180032a42  mov     edx, 0C0h; void *
0x180032a47  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x180032a4c  lea     r8, [rbx+54h]; struct _tagpropertykey *
0x180032a50  lea     rdx, PKEY_VirtualDesktop_Origin_X; struct IPropertyStore *
0x180032a57  mov     rcx, [rbx+20h]; this
0x180032a5b  call    ?IPropertyStore_GetInt32@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@PEAH@Z; Rdp::Utils::Props::IPropertyStore_GetInt32(IPropertyStore *,_tagpropertykey const &,int *)
0x180032a60  mov     rcx, [rsp+0A8h]; this
0x180032a68  lea     rdx, aFailedToRetrie_18; "Failed to retrieve PKEY_VirtualDesktop_"...
0x180032a6f  mov     [rsp+0A8h+var_88], rdx; int
0x180032a74  mov     r9d, eax; char *
0x180032a77  lea     rsi, aOnecoreuapTerm_44; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180032a7e  mov     r8, rsi; unsigned int
0x180032a81  mov     edx, 10Bh; void *
0x180032a86  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180032a8b  lea     r8, [rbx+58h]; struct _tagpropertykey *
0x180032a8f  lea     rdx, PKEY_VirtualDesktop_Origin_Y; struct IPropertyStore *
0x180032a96  mov     rcx, [rbx+20h]; this
0x180032a9a  call    ?IPropertyStore_GetInt32@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@PEAH@Z; Rdp::Utils::Props::IPropertyStore_GetInt32(IPropertyStore *,_tagpropertykey const &,int *)
0x180032a9f  mov     rcx, [rsp+0A8h]; this
0x180032aa7  lea     rdx, aFailedToRetrie_2; "Failed to retrieve PKEY_VirtualDesktop_"...
0x180032aae  mov     [rsp+0A8h+var_88], rdx; int
0x180032ab3  mov     r9d, eax; char *
0x180032ab6  mov     r8, rsi; unsigned int
0x180032ab9  mov     edx, 112h; void *
0x180032abe  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180032ac3  lea     r8, [rbx+5Ch]; struct _tagpropertykey *
0x180032ac7  lea     rdx, PKEY_VirtualDesktop_Width; struct IPropertyStore *
0x180032ace  mov     rcx, [rbx+20h]; this
0x180032ad2  call    ?IPropertyStore_GetUInt32@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@PEAI@Z; Rdp::Utils::Props::IPropertyStore_GetUInt32(IPropertyStore *,_tagpropertykey const &,uint *)
0x180032ad7  mov     rcx, [rsp+0A8h]; this
0x180032adf  lea     rdx, aFailedToRetrie_15; "Failed to retrieve PKEY_VirtualDesktop_"...
0x180032ae6  mov     [rsp+0A8h+var_88], rdx; int
0x180032aeb  mov     r9d, eax; char *
0x180032aee  mov     r8, rsi; unsigned int
0x180032af1  mov     edx, 11Ch; void *
0x180032af6  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180032afb  lea     r8, [rbx+60h]; struct _tagpropertykey *
0x180032aff  lea     rdx, PKEY_VirtualDesktop_Height; struct IPropertyStore *
0x180032b06  mov     rcx, [rbx+20h]; this
0x180032b0a  call    ?IPropertyStore_GetUInt32@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@PEAI@Z; Rdp::Utils::Props::IPropertyStore_GetUInt32(IPropertyStore *,_tagpropertykey const &,uint *)
0x180032b0f  mov     rcx, [rsp+0A8h]; this
0x180032b17  lea     rdx, aFailedToRetrie_23; "Failed to retrieve PKEY_VirtualDesktop_"...
0x180032b1e  mov     [rsp+0A8h+var_88], rdx; int
0x180032b23  mov     r9d, eax; char *
0x180032b26  mov     r8, rsi; unsigned int
0x180032b29  mov     edx, 123h; void *
0x180032b2e  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180032b33  cmp     qword ptr [rbx+0B8h], 0
0x180032b3b  jz      loc_180032C2C
0x180032b41  xorps   xmm0, xmm0
0x180032b44  movdqu  xmmword ptr [rsp+0A8h+var_48], xmm0
0x180032b4a  mov     [rsp+0A8h+var_38], 0
0x180032b53  lea     rsi, [rbx+40h]
0x180032b57  mov     [rsp+0A8h+var_58], rsi
0x180032b5c  mov     [rsp+0A8h+var_50], dil
0x180032b61  mov     rcx, rsi; SRWLock
0x180032b64  call    cs:__imp_AcquireSRWLockShared
0x180032b6a  nop
0x180032b6b  mov     rcx, [rbx+38h]
0x180032b6f  mov     [rsp+0A8h+arg_0], rcx
0x180032b77  mov     rax, [rsp+0A8h+var_38]
0x180032b7c  sub     rax, [rsp+0A8h+var_48]
0x180032b81  sar     rax, 4
0x180032b85  cmp     rcx, rax
0x180032b88  jbe     short loc_180032BAF
0x180032b8a  mov     rax, 0FFFFFFFFFFFFFFFh
0x180032b94  cmp     rcx, rax
0x180032b97  ja      loc_180032CB9
0x180032b9d  lea     rdx, [rsp+0A8h+arg_0]
0x180032ba5  lea     rcx, [rsp+0A8h+var_48]
0x180032baa  call    ??$_Reallocate@$0A@@?$vector@UtagRECT@@V?$allocator@UtagRECT@@@std@@@std@@AEAAXAEA_K@Z; std::vector<tagRECT>::_Reallocate<0>(unsigned __int64 &)
0x180032baf  mov     rdx, [rbx+30h]
0x180032bb3  lea     r9, [rsp+0A8h+var_48]
0x180032bb8  mov     r8, rdx
0x180032bbb  mov     rdx, [rdx]
0x180032bbe  lea     rcx, [rsp+0A8h+arg_0]
0x180032bc6  call    std__transform_std___Tree_iterator_std___Tree_val_std___Tree_simple_types_std__pair__GUID_const__wil__com_ptr_t_Rdp__Avenc__RdpProg__CRdpProgMonitorContext_wil__err_exception_policy__________std__back_insert_iterator_std__vector_tagRECT_std__allocator_tagRECT_______Rdp__Avenc__RdpProg__CRdpProgProcessor__CommitMonitors____12____lambda_1___
0x180032bcb  nop
0x180032bcc  mov     rcx, rsi; SRWLock
0x180032bcf  call    cs:__imp_ReleaseSRWLockShared
0x180032bd5  xor     r9d, r9d; unsigned __int64
0x180032bd8  xor     r8d, r8d; unsigned int
0x180032bdb  mov     edx, 1000h; unsigned __int64
0x180032be0  mov     rcx, [rbx+0B8h]; this
0x180032be7  call    ?AllocatePool@CFcWireEncoderWithBulkUncompressed@Avenc@Rdp@@QEAAX_KI0@Z; Rdp::Avenc::CFcWireEncoderWithBulkUncompressed::AllocatePool(unsigned __int64,uint,unsigned __int64)
0x180032bec  mov     r9, [rsp+0A8h+var_48+8]
0x180032bf1  mov     rax, [rsp+0A8h+var_48]
0x180032bf6  sub     r9, rax
0x180032bf9  sar     r9, 4
0x180032bfd  mov     [rsp+0A8h+var_88], rax; int
0x180032c02  mov     r8d, [rbx+60h]
0x180032c06  mov     edx, [rbx+5Ch]
0x180032c09  mov     rcx, [rbx+0B8h]; this
0x180032c10  call    ?ResetGraphics@?$CRdpEgfx@VCFcWireEncoderWithBulkUncompressed@Avenc@Rdp@@@Protocol@Rdp@@QEAAXIIIPEAUtagRECT@@@Z; Rdp::Protocol::CRdpEgfx<Rdp::Avenc::CFcWireEncoderWithBulkUncompressed>::ResetGraphics(uint,uint,uint,tagRECT *)
0x180032c15  mov     rcx, [rbx+0B8h]; this
0x180032c1c  call    ?Flush@CFcWireEncoder@Avenc@Rdp@@QEAAXI@Z; Rdp::Avenc::CFcWireEncoder::Flush(uint)
0x180032c21  nop
0x180032c22  lea     rcx, [rsp+0A8h+var_48]
0x180032c27  call    ??1?$vector@UtagRECT@@V?$allocator@UtagRECT@@@std@@@std@@QEAA@XZ; std::vector<tagRECT>::~vector<tagRECT>(void)
0x180032c2c  mov     rax, cs:WPP_GLOBAL_Control
0x180032c33  cmp     rax, r13
0x180032c36  jz      short loc_180032C44
0x180032c38  test    [rax+1Ch], dil
0x180032c3c  jz      short loc_180032C44
0x180032c3e  cmp     byte ptr [rax+19h], 4
0x180032c42  jnb     short loc_180032C47
0x180032c44  xor     dil, dil
0x180032c47  lea     rax, WPP_RECORDER_INITIALIZED
0x180032c4e  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180032c55  setnz   bl
0x180032c58  test    dil, dil
0x180032c5b  jnz     short loc_180032C61
0x180032c5d  test    bl, bl
0x180032c5f  jz      short loc_180032C91
0x180032c61  call    cs:__imp_GetCurrentThreadId
0x180032c67  mov     dword ptr [rsp+0A8h+var_68], eax; char
0x180032c6b  mov     [rsp+0A8h+MessageGuid], r15; MessageGuid
0x180032c70  mov     word ptr [rsp+0A8h+var_78], 11h; __int16
0x180032c77  mov     rcx, cs:WPP_GLOBAL_Control
0x180032c7e  mov     r9, [rcx+28h]; int
0x180032c82  mov     r8b, bl; int
0x180032c85  mov     dl, dil; int
0x180032c88  mov     rcx, [rcx+10h]; int
0x180032c8c  call    WPP_RECORDER_AND_TRACE_SF_D
0x180032c91  xor     eax, eax
0x180032c93  jmp     short loc_180032C9C
0x180032c95  mov     eax, dword ptr [rsp+0A8h+arg_0]
0x180032c9c  lea     r11, [rsp+0A8h+var_28]
0x180032ca4  mov     rbx, [r11+38h]
0x180032ca8  mov     rsi, [r11+40h]
0x180032cac  mov     rsp, r11
0x180032caf  pop     r15
0x180032cb1  pop     r14
0x180032cb3  pop     r13
0x180032cb5  pop     r12
0x180032cb7  pop     rdi
0x180032cb8  retn
0x180032cb9  call    ?_Xlength@?$vector@V?$com_ptr_t@UIStreamFormat@nanocom@ds@@Uerr_exception_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UIStreamFormat@nanocom@ds@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@CAXXZ; std::vector<wil::com_ptr_t<ds::nanocom::IStreamFormat,wil::err_exception_policy>>::_Xlength(void)
```
