# CIoPacket::CIoPacket(CFileIoChannel *,unsigned __int64,uint *,unsigned __int64,void *,Rdp::Avenc::IIoPacketCompleteEvents *)

- ea: `0x180032398`
- end: `0x180032990`
- name: `??0CIoPacket@@QEAA@PEAVCFileIoChannel@@_KPEAI1PEAXPEAUIIoPacketCompleteEvents@Avenc@Rdp@@@Z`
- size: `1528`
- prototype: `CIoPacket *__fastcall(CIoPacket *__hidden this, struct CFileIoChannel *, unsigned __int64, unsigned int *, unsigned __int64 Buf2, void *Buf1, struct Rdp::Avenc::IIoPacketCompleteEvents *)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180032c90`

## callees

- `0x180001010`
- `0x180005a48`
- `0x180005b70`
- `0x180007b14`
- `0x18000d614`
- `0x180012ba0`
- `0x180013b38`
- `0x180031e74`
- `0x180032398`
- `0x180032a94`
- `0x180033498`
- `0x180034848`
- `0x180035e7c`
- `0x180036294`
- `0x18003f010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x1800327b3`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x1800327b3`
- `api-ms-win-core-synch-l1-1-0!SleepEx` at `0x1800325ec`
- `api-ms-win-core-synch-l1-1-0!SleepEx` at `0x1800325ec`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
CIoPacket *__fastcall CIoPacket::CIoPacket(
        CIoPacket *this,
        struct CFileIoChannel *a2,
        __int64 a3,
        unsigned int *a4,
        unsigned __int64 Buf2,
        void *Buf1,
        struct Rdp::Avenc::IIoPacketCompleteEvents *a7)
{
  CFileIoChannel **v9; // r13
  struct Rdp::Avenc::IIoPacketCompleteEvents *v10; // rcx
  __int64 *v11; // rsi
  _QWORD *v12; // rbx
  __m128i si128; // xmm0
  CFileIoChannel *v14; // rax
  unsigned int *v15; // r9
  unsigned int v16; // r15d
  DWORD v17; // r12d
  unsigned __int64 v18; // r14
  __int64 v19; // rcx
  int i; // ebx
  _DWORD *v21; // rcx
  int v22; // r8d
  int v23; // r9d
  int v24; // r8d
  int v25; // r9d
  struct WDFREQUEST__ *v26; // rbx
  unsigned __int64 v27; // rbx
  _OWORD *v28; // rdx
  __int64 v29; // rdx
  __int64 v30; // r8
  int v31; // ebx
  __int64 v32; // rdx
  size_t v33; // rcx
  void *v34; // rax
  _DWORD *v35; // rcx
  int v36; // r8d
  int v37; // r9d
  void *v39; // [rsp+78h] [rbp-41h] BYREF
  void *v40; // [rsp+80h] [rbp-39h] BYREF
  const char *v41; // [rsp+88h] [rbp-31h] BYREF
  const char *v42; // [rsp+90h] [rbp-29h] BYREF
  const char *v43; // [rsp+98h] [rbp-21h] BYREF
  __int128 v44; // [rsp+A0h] [rbp-19h] BYREF
  __int128 v45; // [rsp+B0h] [rbp-9h]
  void *retaddr; // [rsp+100h] [rbp+47h]
  CIoPacket *v47; // [rsp+108h] [rbp+4Fh] BYREF
  unsigned __int64 v48; // [rsp+118h] [rbp+5Fh] BYREF
  unsigned int *v49; // [rsp+120h] [rbp+67h] BYREF

  v49 = a4;
  v47 = this;
  *(_QWORD *)this = &winrt::impl::producers_base<CIoPacket,std::tuple<Rdp::Avenc::IIoPacket>>::`vftable';
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  *((_QWORD *)this + 2) = 1;
  *(_QWORD *)this = &CIoPacket::`vftable'{for `winrt::impl::producers_base<CIoPacket,std::tuple<Rdp::Avenc::IIoPacket>>'};
  *((_QWORD *)this + 1) = &CIoPacket::`vftable'{for `winrt::impl::root_implements<CIoPacket,Rdp::Avenc::IIoPacket>'};
  v9 = (CFileIoChannel **)((char *)this + 24);
  wil::com_ptr_t<CIoPacket,wil::err_exception_policy>::com_ptr_t<CIoPacket,wil::err_exception_policy>(
    (char *)this + 24,
    a2);
  *((_QWORD *)this + 4) = a3;
  *((_QWORD *)this + 5) = Buf2;
  *((_QWORD *)this + 6) = Buf1;
  v10 = a7;
  *((_QWORD *)this + 7) = a7;
  if ( v10 )
    (*(void (__fastcall **)(struct Rdp::Avenc::IIoPacketCompleteEvents *))(*(_QWORD *)v10 + 8LL))(v10);
  v11 = (__int64 *)((char *)this + 64);
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 10) = 0;
  *((_QWORD *)this + 11) = 0;
  v12 = (_QWORD *)((char *)this + 96);
  *((_QWORD *)this + 12) = 0;
  *((_QWORD *)this + 13) = 0;
  *((_QWORD *)this + 14) = 0;
  *((_QWORD *)this + 15) = 0;
  *((_DWORD *)this + 32) = 0;
  *((_QWORD *)this + 17) = 0;
  *((_QWORD *)this + 23) = 0;
  *((_WORD *)this + 96) = 0;
  LODWORD(Buf1) = 8;
  LODWORD(Buf2) = 0;
  if ( !memcmp_0(&Buf1, &Buf2, 4u) )
  {
    *((_OWORD *)this + 9) = 0;
    *((_OWORD *)this + 10) = 0;
    *((_QWORD *)this + 22) = 0;
  }
  else
  {
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    *((__m128i *)this + 9) = si128;
    *((__m128i *)this + 10) = si128;
    *((_QWORD *)this + 22) = si128.m128i_i64[0];
  }
  v14 = *v9;
  if ( *((_DWORD *)*v9 + 94) == 2 )
    *((_QWORD *)this + 4) += 16LL;
  v15 = v49;
  if ( !v49 || (v16 = *v49) == 0 )
    v16 = 0;
  v17 = *((_DWORD *)v14 + 91);
  v18 = *((_QWORD *)this + 4);
  if ( v18 )
  {
    while ( 1 )
    {
      v19 = (__int64)*v9;
      if ( *((_DWORD *)*v9 + 93) >= *((_DWORD *)*v9 + 92) )
        break;
      a7 = 0;
      v40 = 0;
      v48 = 0;
      for ( i = 0; ; ++i )
      {
        v19 = (unsigned int)(v17 != 0) + 1;
        if ( i >= (int)v19 )
          break;
        if ( CFileIoChannel::DequeuePendingIrp(*v9, &a7, &v40, &v48) )
        {
          v19 = *(_QWORD *)(wil::details::static_lazy<RdpIddLoggingProvider>::get() + 8);
          if ( *(_DWORD *)v19 > 5u )
          {
            Buf1 = (void *)v48;
            v26 = a7;
            v43 = "CIoPacket: Retrieved pending IRP";
            v42 = "CIoPacket::CIoPacket";
            LODWORD(Buf2) = 1304;
            v41 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\fileio.cpp";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
              v19,
              (unsigned int)byte_1800500D3,
              v24,
              v25,
              (__int64)&v41,
              (__int64)&Buf2,
              (__int64)&v42,
              (__int64)&v43,
              (__int64)&a7,
              (__int64)&Buf1);
            goto LABEL_24;
          }
          break;
        }
        if ( v17 )
        {
          v21 = *(_DWORD **)(wil::details::static_lazy<RdpIddLoggingProvider>::get() + 8);
          if ( *v21 > 5u )
          {
            LODWORD(Buf2) = v17;
            v41 = "CIoPacket: No pending IRP found, waiting for first IRP";
            v42 = "CIoPacket::CIoPacket";
            LODWORD(Buf1) = 1315;
            v43 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\fileio.cpp";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
              (_DWORD)v21,
              (unsigned int)&word_18005008E,
              v22,
              v23,
              (__int64)&v43,
              (__int64)&Buf1,
              (__int64)&v42,
              (__int64)&v41,
              (__int64)&Buf2);
          }
          SleepEx(v17, 0);
          v17 = 0;
        }
      }
      v26 = a7;
LABEL_24:
      if ( !v26 )
        break;
      if ( v16 && (unsigned int)((*((_QWORD *)this + 9) - *v11) >> 5) + 1 + (v48 < v18) > v16 )
      {
        CFileIoChannel::QueuePendingIrp(*v9, v26);
        break;
      }
      *(_QWORD *)&v44 = v26;
      *((_QWORD *)&v44 + 1) = v40;
      *(_QWORD *)&v45 = v48;
      v27 = v18;
      if ( v48 < v18 )
        v27 = v48;
      *((_QWORD *)&v45 + 1) = v27;
      v28 = (_OWORD *)*((_QWORD *)this + 9);
      if ( v28 == *((_OWORD **)this + 10) )
      {
        std::vector<CIoPacket::IrpBufferEntry>::_Emplace_reallocate<CIoPacket::IrpBufferEntry const &>(
          (char *)this + 64,
          v28,
          &v44);
      }
      else
      {
        *v28 = v44;
        v28[1] = v45;
        *((_QWORD *)this + 9) += 32LL;
      }
      ++*((_DWORD *)*v9 + 93);
      ++*((_DWORD *)this + 47);
      v18 -= v27;
      if ( !v18 )
      {
        v15 = v49;
        v12 = (_QWORD *)((char *)this + 96);
        goto LABEL_34;
      }
    }
    if ( v16 )
    {
      v32 = (__int64)(*((_QWORD *)this + 9) - *((_QWORD *)this + 8)) >> 5;
      if ( (unsigned int)v32 >= v16 )
        MicrosoftTelemetryAssertTriggeredArgs(v19, v32, v16);
    }
    *((_QWORD *)this + 14) = v18;
    v33 = (v18 + 4095) & 0xFFFFFFFFFFFFF000uLL;
    *((_QWORD *)this + 13) = v33;
    v34 = _aligned_malloc(v33, 0x1000u);
    v39 = v34;
    v12 = (_QWORD *)((char *)this + 96);
    if ( (void **)((char *)this + 96) != &v39 )
    {
      wil::details::unique_storage<wil::details::resource_policy<unsigned char *,void (*)(void *),&void _aligned_free(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>::reset(
        (char *)this + 96,
        v34);
      v39 = 0;
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned char *,void (*)(void *),&void _aligned_free(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned char *,void (*)(void *),&void _aligned_free(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>(&v39);
    wil::details::in1diag3::Throw_HrIfNullMsg<wil::com_ptr_t<Rdp::Avenc::ISerializePropertyBag,wil::err_exception_policy>,0>(
      retaddr,
      1388,
      "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\fileio.cpp",
      2147942414LL,
      (char *)this + 96,
      "Failed to allocate Aux buffer");
    *((_QWORD *)this + 15) = *v12;
    v15 = v49;
  }
LABEL_34:
  v29 = *v12;
  v30 = *v11;
  *((_DWORD *)this + 32) = (*v12 != 0) + (unsigned int)((__int64)(*((_QWORD *)this + 9) - *((_QWORD *)this + 8)) >> 5);
  if ( v30 == *((_QWORD *)this + 9) )
    v31 = 4;
  else
    v31 = v29 != 0;
  if ( *((_DWORD *)*v9 + 94) == 2 )
  {
    if ( v30 == *((_QWORD *)this + 9) )
    {
      if ( v29 )
        *((_QWORD *)this + 17) = v29;
    }
    else
    {
      *((_QWORD *)this + 17) = *(_QWORD *)(v30 + 8);
    }
    **((_QWORD **)this + 17) = *((_QWORD *)this + 4);
    *(_QWORD *)(*((_QWORD *)this + 17) + 8LL) = 0;
  }
  *((_DWORD *)this + *((unsigned int *)this + 46) + 36) = v31;
  if ( v15 )
    *v15 = *((_DWORD *)this + 32);
  v35 = *(_DWORD **)(wil::details::static_lazy<RdpIddLoggingProvider>::get() + 8);
  if ( *v35 > 5u )
  {
    Buf1 = (void *)*((_QWORD *)this + 14);
    LODWORD(v49) = (__int64)(*((_QWORD *)this + 9) - *((_QWORD *)this + 8)) >> 5;
    LODWORD(v47) = *((_DWORD *)this + 32);
    a7 = (struct Rdp::Avenc::IIoPacketCompleteEvents *)off_180041250[v31];
    v48 = *((_QWORD *)this + 4);
    v43 = (const char *)this;
    v42 = "Allocate IoPacket";
    v41 = "CIoPacket::CIoPacket";
    LODWORD(Buf2) = 1452;
    v40 = (void *)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\fileio.cpp";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
      (_DWORD)v35,
      (unsigned int)byte_180050009,
      v36,
      v37,
      (__int64)&v40,
      (__int64)&Buf2,
      (__int64)&v41,
      (__int64)&v42,
      (__int64)&v43,
      (__int64)&v48,
      (__int64)&a7,
      (__int64)&v47,
      (__int64)&v49,
      (__int64)&Buf1);
  }
  return this;
}

```

## disassembly

```asm
0x180032398  mov     rax, rsp
0x18003239b  mov     [rax+10h], rbx
0x18003239f  mov     [rax+20h], r9
0x1800323a3  mov     [rax+8], rcx
0x1800323a7  push    rbp
0x1800323a8  push    rsi
0x1800323a9  push    rdi
0x1800323aa  push    r12
0x1800323ac  push    r13
0x1800323ae  push    r14
0x1800323b0  push    r15
0x1800323b2  lea     rbp, [rax-47h]
0x1800323b6  sub     rsp, 0C0h
0x1800323bd  mov     rbx, r8
0x1800323c0  mov     rdi, rcx
0x1800323c3  lea     rax, ??_7?$producers_base@VCIoPacket@@V?$tuple@UIIoPacket@Avenc@Rdp@@@std@@@impl@winrt@@6B@; const winrt::impl::producers_base<CIoPacket,std::tuple<Rdp::Avenc::IIoPacket>>::`vftable'
0x1800323ca  mov     [rcx], rax
0x1800323cd  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x1800323d4  mov     qword ptr [rcx+10h], 1
0x1800323dc  lea     rax, ??_7CIoPacket@@6B?$producers_base@VCIoPacket@@V?$tuple@UIIoPacket@Avenc@Rdp@@@std@@@impl@winrt@@@; const CIoPacket::`vftable'{for `winrt::impl::producers_base<CIoPacket,std::tuple<Rdp::Avenc::IIoPacket>>'}
0x1800323e3  mov     [rcx], rax
0x1800323e6  lea     rax, ??_7CIoPacket@@6B?$root_implements@VCIoPacket@@UIIoPacket@Avenc@Rdp@@@impl@winrt@@@; const CIoPacket::`vftable'{for `winrt::impl::root_implements<CIoPacket,Rdp::Avenc::IIoPacket>'}
0x1800323ed  mov     [rcx+8], rax
0x1800323f1  lea     r13, [rcx+18h]
0x1800323f5  mov     rcx, r13
0x1800323f8  call    ??0?$com_ptr_t@VCIoPacket@@Uerr_exception_policy@wil@@@wil@@QEAA@PEAVCIoPacket@@@Z; wil::com_ptr_t<CIoPacket,wil::err_exception_policy>::com_ptr_t<CIoPacket,wil::err_exception_policy>(CIoPacket *)
0x1800323fd  nop
0x1800323fe  mov     [rdi+20h], rbx
0x180032402  mov     rax, [rbp+3Fh+Buf2]
0x180032406  mov     [rdi+28h], rax
0x18003240a  mov     rax, [rbp+3Fh+Buf1]
0x18003240e  mov     [rdi+30h], rax
0x180032412  mov     rcx, [rbp+3Fh+arg_30]
0x180032416  mov     [rdi+38h], rcx
0x18003241a  xor     r14d, r14d
0x18003241d  test    rcx, rcx
0x180032420  jz      short loc_18003242F
0x180032422  mov     rax, [rcx]
0x180032425  mov     rax, [rax+8]
0x180032429  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003242e  nop
0x18003242f  lea     rsi, [rdi+40h]
0x180032433  mov     [rsi], r14
0x180032436  mov     [rsi+8], r14
0x18003243a  mov     [rsi+10h], r14
0x18003243e  mov     [rdi+58h], r14
0x180032442  lea     rbx, [rdi+60h]
0x180032446  mov     [rbx], r14
0x180032449  mov     [rdi+68h], r14
0x18003244d  mov     [rdi+70h], r14
0x180032451  mov     [rdi+78h], r14
0x180032455  mov     [rdi+80h], r14d
0x18003245c  mov     [rdi+88h], r14
0x180032463  mov     [rdi+0B8h], r14
0x18003246a  mov     [rdi+0C0h], r14w
0x180032472  mov     dword ptr [rbp+3Fh+Buf1], 8
0x180032479  mov     dword ptr [rbp+3Fh+Buf2], r14d
0x18003247d  mov     r8d, 4; Size
0x180032483  lea     rdx, [rbp+3Fh+Buf2]; Buf2
0x180032487  lea     rcx, [rbp+3Fh+Buf1]; Buf1
0x18003248b  call    memcmp_0
0x180032490  test    eax, eax
0x180032492  jnz     short loc_1800324B0
0x180032494  xorps   xmm0, xmm0
0x180032497  xor     eax, eax
0x180032499  movups  xmmword ptr [rdi+90h], xmm0
0x1800324a0  movups  xmmword ptr [rdi+0A0h], xmm0
0x1800324a7  mov     [rdi+0B0h], rax
0x1800324ae  jmp     short loc_1800324CF
0x1800324b0  movdqa  xmm0, cs:__xmm@00000008000000080000000800000008
0x1800324b8  movups  xmmword ptr [rdi+90h], xmm0
0x1800324bf  movups  xmmword ptr [rdi+0A0h], xmm0
0x1800324c6  movq    qword ptr [rdi+0B0h], xmm0
0x1800324cf  mov     rax, [r13+0]
0x1800324d3  cmp     dword ptr [rax+178h], 2
0x1800324da  jnz     short loc_1800324E1
0x1800324dc  add     qword ptr [rdi+20h], 10h
0x1800324e1  mov     r9, [rbp+3Fh+arg_18]
0x1800324e5  test    r9, r9
0x1800324e8  jz      short loc_1800324F2
0x1800324ea  mov     r15d, [r9]
0x1800324ed  test    r15d, r15d
0x1800324f0  jnz     short loc_1800324F5
0x1800324f2  mov     r15d, r14d
0x1800324f5  mov     r12d, [rax+16Ch]
0x1800324fc  mov     r14, [rdi+20h]
0x180032500  test    r14, r14
0x180032503  jz      loc_18003272E
0x180032509  mov     rcx, [r13+0]
0x18003250d  mov     eax, [rcx+170h]
0x180032513  cmp     [rcx+174h], eax
0x180032519  jnb     loc_18003277B
0x18003251f  mov     [rbp+3Fh+arg_30], 0
0x180032527  mov     [rbp+3Fh+var_78], 0
0x18003252f  mov     [rbp+3Fh+arg_10], 0
0x180032537  xor     ebx, ebx
0x180032539  mov     eax, r12d
0x18003253c  neg     eax
0x18003253e  sbb     ecx, ecx
0x180032540  neg     ecx
0x180032542  inc     ecx
0x180032544  cmp     ebx, ecx
0x180032546  jge     loc_18003268E
0x18003254c  lea     r9, [rbp+3Fh+arg_10]; unsigned __int64 *
0x180032550  lea     r8, [rbp+3Fh+var_78]; void **
0x180032554  lea     rdx, [rbp+3Fh+arg_30]; struct WDFREQUEST__ **
0x180032558  mov     rcx, [r13+0]; this
0x18003255c  call    ?DequeuePendingIrp@CFileIoChannel@@QEAA_NPEAPEAUWDFREQUEST__@@PEAPEAXPEA_K@Z; CFileIoChannel::DequeuePendingIrp(WDFREQUEST__ * *,void * *,unsigned __int64 *)
0x180032561  test    al, al
0x180032563  jnz     loc_180032602
0x180032569  test    r12d, r12d
0x18003256c  jz      loc_1800325FB
0x180032572  call    ?get@?$static_lazy@VRdpIddLoggingProvider@@@details@wil@@QEAAPEAVRdpIddLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<RdpIddLoggingProvider>::get(void (*)(void))
0x180032577  mov     rcx, [rax+8]
0x18003257b  mov     eax, [rcx]
0x18003257d  cmp     eax, 5
0x180032580  jbe     short loc_1800325E7
0x180032582  mov     dword ptr [rbp+3Fh+Buf2], r12d
0x180032586  lea     rax, aCiopacketNoPen; "CIoPacket: No pending IRP found, waitin"...
0x18003258d  mov     [rbp+3Fh+var_70], rax
0x180032591  lea     rax, aCiopacketCiopa; "CIoPacket::CIoPacket"
0x180032598  mov     [rbp+3Fh+var_68], rax
0x18003259c  mov     dword ptr [rbp+3Fh+Buf1], 523h
0x1800325a3  lea     rax, aOnecoreuapTerm_11; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x1800325aa  mov     [rbp+3Fh+var_60], rax
0x1800325ae  lea     rax, [rbp+3Fh+Buf2]
0x1800325b2  mov     [rsp+0F0h+var_B0], rax
0x1800325b7  lea     rax, [rbp+3Fh+var_70]
0x1800325bb  mov     [rsp+0F0h+var_B8], rax
0x1800325c0  lea     rax, [rbp+3Fh+var_68]
0x1800325c4  mov     [rsp+0F0h+var_C0], rax
0x1800325c9  lea     rax, [rbp+3Fh+Buf1]
0x1800325cd  mov     [rsp+0F0h+var_C8], rax
0x1800325d2  lea     rax, [rbp+3Fh+var_60]
0x1800325d6  mov     [rsp+0F0h+var_D0], rax
0x1800325db  lea     rdx, word_18005008E
0x1800325e2  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@334@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800325e7  xor     edx, edx; bAlertable
0x1800325e9  mov     ecx, r12d; dwMilliseconds
0x1800325ec  call    cs:__imp_SleepEx
0x1800325f3  nop     dword ptr [rax+rax+00h]
0x1800325f8  xor     r12d, r12d
0x1800325fb  inc     ebx
0x1800325fd  jmp     loc_180032539
0x180032602  call    ?get@?$static_lazy@VRdpIddLoggingProvider@@@details@wil@@QEAAPEAVRdpIddLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<RdpIddLoggingProvider>::get(void (*)(void))
0x180032607  mov     rcx, [rax+8]
0x18003260b  mov     eax, [rcx]
0x18003260d  cmp     eax, 5
0x180032610  jbe     short loc_18003268E
0x180032612  mov     rax, [rbp+3Fh+arg_10]
0x180032616  mov     [rbp+3Fh+Buf1], rax
0x18003261a  mov     rbx, [rbp+3Fh+arg_30]
0x18003261e  mov     [rbp+3Fh+arg_30], rbx
0x180032622  lea     rax, aCiopacketRetri; "CIoPacket: Retrieved pending IRP"
0x180032629  mov     [rbp+3Fh+var_60], rax
0x18003262d  lea     rax, aCiopacketCiopa; "CIoPacket::CIoPacket"
0x180032634  mov     [rbp+3Fh+var_68], rax
0x180032638  mov     dword ptr [rbp+3Fh+Buf2], 518h
0x18003263f  lea     rax, aOnecoreuapTerm_11; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x180032646  mov     [rbp+3Fh+var_70], rax
0x18003264a  lea     rax, [rbp+3Fh+Buf1]
0x18003264e  mov     [rsp+0F0h+var_A8], rax
0x180032653  lea     rax, [rbp+3Fh+arg_30]
0x180032657  mov     [rsp+0F0h+var_B0], rax
0x18003265c  lea     rax, [rbp+3Fh+var_60]
0x180032660  mov     [rsp+0F0h+var_B8], rax
0x180032665  lea     rax, [rbp+3Fh+var_68]
0x180032669  mov     [rsp+0F0h+var_C0], rax
0x18003266e  lea     rax, [rbp+3Fh+Buf2]
0x180032672  mov     [rsp+0F0h+var_C8], rax
0x180032677  lea     rax, [rbp+3Fh+var_70]
0x18003267b  mov     [rsp+0F0h+var_D0], rax
0x180032680  lea     rdx, byte_1800500D3
0x180032687  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U?$_tlgWrapperByVal@$07@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33AEBU?$_tlgWrapperByVal@$07@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)
0x18003268c  jmp     short loc_180032692
0x18003268e  mov     rbx, [rbp+3Fh+arg_30]
0x180032692  test    rbx, rbx
0x180032695  jz      loc_180032776
0x18003269b  mov     rdx, [rbp+3Fh+arg_10]
0x18003269f  test    r15d, r15d
0x1800326a2  jz      short loc_1800326C3
0x1800326a4  mov     rcx, [rdi+48h]
0x1800326a8  sub     rcx, [rsi]
0x1800326ab  sar     rcx, 5
0x1800326af  cmp     rdx, r14
0x1800326b2  sbb     eax, eax
0x1800326b4  neg     eax
0x1800326b6  inc     ecx
0x1800326b8  add     eax, ecx
0x1800326ba  cmp     eax, r15d
0x1800326bd  ja      loc_18003276A
0x1800326c3  mov     qword ptr [rbp+3Fh+var_58], rbx
0x1800326c7  mov     rax, [rbp+3Fh+var_78]
0x1800326cb  mov     qword ptr [rbp+3Fh+var_58+8], rax
0x1800326cf  mov     qword ptr [rbp+3Fh+var_48], rdx
0x1800326d3  mov     rbx, r14
0x1800326d6  cmp     rdx, r14
0x1800326d9  cmovb   rbx, rdx
0x1800326dd  mov     qword ptr [rbp+3Fh+var_48+8], rbx
0x1800326e1  mov     rdx, [rsi+8]
0x1800326e5  cmp     rdx, [rsi+10h]
0x1800326e9  jz      short loc_180032701
0x1800326eb  movups  xmm0, [rbp+3Fh+var_58]
0x1800326ef  movups  xmmword ptr [rdx], xmm0
0x1800326f2  movups  xmm1, [rbp+3Fh+var_48]
0x1800326f6  movups  xmmword ptr [rdx+10h], xmm1
0x1800326fa  add     qword ptr [rsi+8], 20h ; ' '
0x1800326ff  jmp     short loc_18003270D
0x180032701  lea     r8, [rbp+3Fh+var_58]
0x180032705  mov     rcx, rsi
0x180032708  call    ??$_Emplace_reallocate@AEBUIrpBufferEntry@CIoPacket@@@?$vector@UIrpBufferEntry@CIoPacket@@V?$allocator@UIrpBufferEntry@CIoPacket@@@std@@@std@@AEAAPEAUIrpBufferEntry@CIoPacket@@QEAU23@AEBU23@@Z; std::vector<CIoPacket::IrpBufferEntry>::_Emplace_reallocate<CIoPacket::IrpBufferEntry const &>(CIoPacket::IrpBufferEntry * const,CIoPacket::IrpBufferEntry const &)
0x18003270d  mov     rax, [r13+0]
0x180032711  inc     dword ptr [rax+174h]
0x180032717  inc     dword ptr [rdi+0BCh]
0x18003271d  sub     r14, rbx
0x180032720  jnz     loc_180032509
0x180032726  mov     r9, [rbp+3Fh+arg_18]
0x18003272a  lea     rbx, [rdi+60h]
0x18003272e  lea     r14, aOnecoreuapTerm_11; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x180032735  mov     rdx, [rbx]
0x180032738  mov     r8, [rsi]
0x18003273b  mov     rcx, [rsi+8]
0x18003273f  sub     rcx, r8
0x180032742  sar     rcx, 5
0x180032746  xor     eax, eax
0x180032748  test    rdx, rdx
0x18003274b  setnz   al
0x18003274e  add     ecx, eax
0x180032750  mov     [rdi+80h], ecx
0x180032756  cmp     r8, [rsi+8]
0x18003275a  jnz     loc_18003282B
0x180032760  mov     ebx, 4
0x180032765  jmp     loc_180032835
0x18003276a  mov     rdx, rbx; struct WDFREQUEST__ *
0x18003276d  mov     rcx, [r13+0]; this
0x180032771  call    ?QueuePendingIrp@CFileIoChannel@@QEAAXPEAUWDFREQUEST__@@@Z; CFileIoChannel::QueuePendingIrp(WDFREQUEST__ *)
0x180032776  test    r14, r14
0x180032779  jz      short loc_180032726
0x18003277b  test    r15d, r15d
0x18003277e  jz      short loc_180032798
0x180032780  mov     rdx, [rsi+8]
0x180032784  sub     rdx, [rsi]
0x180032787  sar     rdx, 5
0x18003278b  cmp     edx, r15d
0x18003278e  jb      short loc_180032798
0x180032790  mov     r8d, r15d
0x180032793  call    MicrosoftTelemetryAssertTriggeredArgs
0x180032798  mov     [rdi+70h], r14
0x18003279c  lea     rcx, [r14+0FFFh]
0x1800327a3  and     rcx, 0FFFFFFFFFFFFF000h; Size
0x1800327aa  mov     [rdi+68h], rcx
0x1800327ae  mov     edx, 1000h; Alignment
0x1800327b3  call    cs:__imp__aligned_malloc
0x1800327ba  nop     dword ptr [rax+rax+00h]
0x1800327bf  mov     [rbp+3Fh+var_80], rax
0x1800327c3  lea     rcx, [rbp+3Fh+var_80]
0x1800327c7  lea     rbx, [rdi+60h]
0x1800327cb  cmp     rbx, rcx
0x1800327ce  jz      short loc_1800327E3
0x1800327d0  mov     rdx, rax
0x1800327d3  mov     rcx, rbx
0x1800327d6  call    ?reset@?$unique_storage@U?$resource_policy@PEAEP6AXPEAX@Z$1?_aligned_free@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAEPEAE$0A@$$T@details@wil@@@details@wil@@QEAAXPEAE@Z; wil::details::unique_storage<wil::details::resource_policy<uchar *,void (*)(void *),&_aligned_free(void *),wistd::integral_constant<unsigned __int64,0>,uchar *,uchar *,0,std::nullptr_t>>::reset(uchar *)
0x1800327db  mov     [rbp+3Fh+var_80], 0
0x1800327e3  lea     rcx, [rbp+3Fh+var_80]
0x1800327e7  call    ??1?$unique_storage@U?$resource_policy@PEAEP6AXPEAX@Z$1?_aligned_free@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAEPEAE$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<uchar *,void (*)(void *),&_aligned_free(void *),wistd::integral_constant<unsigned __int64,0>,uchar *,uchar *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<uchar *,void (*)(void *),&_aligned_free(void *),wistd::integral_constant<unsigned __int64,0>,uchar *,uchar *,0,std::nullptr_t>>(void)
0x1800327ec  mov     rcx, [rbp+47h]
0x1800327f0  lea     rax, aFailedToAlloca_0; "Failed to allocate Aux buffer"
0x1800327f7  mov     [rsp+0F0h+var_C8], rax
0x1800327fc  mov     [rsp+0F0h+var_D0], rbx
0x180032801  mov     r9d, 8007000Eh
0x180032807  lea     r14, aOnecoreuapTerm_11; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x18003280e  mov     r8, r14
0x180032811  mov     edx, 56Ch
0x180032816  call    ??$Throw_HrIfNullMsg@V?$com_ptr_t@UISerializePropertyBag@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@$0A@@in1diag3@details@wil@@YAXPEAXIPEBDJAEBV?$com_ptr_t@UISerializePropertyBag@Avenc@Rdp@@Uerr_exception_policy@wil@@@2@1ZZ; wil::details::in1diag3::Throw_HrIfNullMsg<wil::com_ptr_t<Rdp::Avenc::ISerializePropertyBag,wil::err_exception_policy>,0>(void *,uint,char const *,long,wil::com_ptr_t<Rdp::Avenc::ISerializePropertyBag,wil::err_exception_policy> const &,char const *,...)
0x18003281b  mov     rax, [rbx]
0x18003281e  mov     [rdi+78h], rax
0x180032822  mov     r9, [rbp+3Fh+arg_18]
0x180032826  jmp     loc_180032735
0x18003282b  xor     eax, eax
0x18003282d  test    rdx, rdx
0x180032830  setnz   al
0x180032833  mov     ebx, eax
0x180032835  mov     rax, [r13+0]
0x180032839  cmp     dword ptr [rax+178h], 2
0x180032840  jnz     short loc_18003287E
0x180032842  cmp     r8, [rsi+8]
0x180032846  jnz     short loc_180032856
0x180032848  test    rdx, rdx
0x18003284b  jz      short loc_180032861
0x18003284d  mov     [rdi+88h], rdx
0x180032854  jmp     short loc_180032861
0x180032856  mov     rax, [r8+8]
0x18003285a  mov     [rdi+88h], rax
0x180032861  mov     rcx, [rdi+88h]
0x180032868  mov     rax, [rdi+20h]
0x18003286c  mov     [rcx], rax
0x18003286f  mov     rax, [rdi+88h]
0x180032876  mov     qword ptr [rax+8], 0
0x18003287e  mov     eax, [rdi+0B8h]
0x180032884  mov     [rdi+rax*4+90h], ebx
  ... truncated ...
```
