# CRdpIdMonitor::HPDMonitor(void)

- ea: `0x180025180`
- end: `0x180025520`
- name: `?HPDMonitor@CRdpIdMonitor@@QEAAXXZ`
- size: `928`
- prototype: `void __fastcall(CRdpIdMonitor *__hidden this)`
- caller_count: `1`
- callee_count: `18`
- tags: `broker_com_uri`

## callers

- `0x18001556c`

## callees

- `0x180001af0`
- `0x180004c5c`
- `0x180006f60`
- `0x180006f84`
- `0x18000d614`
- `0x18001072c`
- `0x180012274`
- `0x180014c00`
- `0x1800153c4`
- `0x180021570`
- `0x180021830`
- `0x180023364`
- `0x18002476c`
- `0x180025180`
- `0x180027724`
- `0x1800280b8`
- `0x180030a28`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800252c4`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800252c4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CRdpIdMonitor::HPDMonitor(CRdpIdMonitor *this)
{
  _DWORD *v2; // r8
  int v3; // r8d
  int v4; // r9d
  __int64 v5; // rcx
  int v6; // eax
  int v7; // eax
  unsigned int v8; // r8d
  __int64 v9; // rdx
  __int64 v10; // rbx
  __int64 v11; // rax
  __int64 v12; // rbx
  __int64 v13; // rax
  __int64 v14; // rdx
  unsigned int v15; // r8d
  int v16; // eax
  unsigned int v17; // r8d
  int v18; // [rsp+20h] [rbp-E0h]
  __int64 v19; // [rsp+28h] [rbp-D8h]
  int v20; // [rsp+50h] [rbp-B0h] BYREF
  int v21; // [rsp+54h] [rbp-ACh] BYREF
  const char *v22; // [rsp+58h] [rbp-A8h] BYREF
  std::_Ref_count_base *v23; // [rsp+60h] [rbp-A0h]
  __int64 v24; // [rsp+68h] [rbp-98h] BYREF
  GUID *v25; // [rsp+70h] [rbp-90h] BYREF
  const char *v26; // [rsp+78h] [rbp-88h] BYREF
  __int64 v27; // [rsp+80h] [rbp-80h] BYREF
  std::_Ref_count_base *v28; // [rsp+88h] [rbp-78h]
  _QWORD v29[2]; // [rsp+90h] [rbp-70h] BYREF
  _QWORD v30[3]; // [rsp+A0h] [rbp-60h] BYREF
  int v31; // [rsp+B8h] [rbp-48h]
  int v32; // [rsp+BCh] [rbp-44h]
  __int128 v33; // [rsp+C0h] [rbp-40h]
  __int64 *v34; // [rsp+D0h] [rbp-30h]
  __int128 v35; // [rsp+D8h] [rbp-28h] BYREF
  __int128 v36; // [rsp+E8h] [rbp-18h]
  GUID pguid; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v38; // [rsp+108h] [rbp+8h]
  __int64 v39; // [rsp+110h] [rbp+10h] BYREF
  int v40; // [rsp+118h] [rbp+18h]
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+38h]

  if ( !*((_BYTE *)this + 16) )
  {
    v2 = *(_DWORD **)(wil::details::static_lazy<RdpIddLoggingProvider>::get() + 8);
    if ( *v2 > 4u && (unsigned __int8)tlgKeywordOn(v2, 0x470000000000LL) )
    {
      v21 = *(_DWORD *)(*((_QWORD *)this + 29) + 516LL);
      v20 = *((_DWORD *)this + 70);
      v25 = &RdpIddLoggingProviderWithCorrelationId::g_CorrelationId;
      v26 = "RdpIdd";
      v27 = 0x1000000;
      v22 = "Checkpoint";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v3,
        (unsigned int)&byte_18004E9B7,
        v3,
        v4,
        (__int64)&v22,
        (__int64)&v27,
        (__int64)&v26,
        (__int64)&v25,
        (__int64)&v20,
        (__int64)&v21);
    }
    LODWORD(v19) = *((_DWORD *)this + 70);
    Rdp::Modern::Utils::CInflightRecorder::pushN(
      (Rdp::Modern::Utils::CInflightRecorder *)&Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
      (wchar_t *)L"MonitorHPD: Id %d",
      "CRdpIdMonitor::HPDMonitor",
      "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\monitor.cpp",
      0x257u,
      v19);
    v35 = 0;
    v36 = 0;
    pguid = 0;
    v38 = 0;
    LODWORD(v35) = 56;
    CoCreateGuid((GUID *)pguid.Data4);
    DWORD1(v35) = -1;
    DWORD2(v35) = *((_DWORD *)this + 71);
    *(_QWORD *)&v36 = 0x100000018LL;
    v5 = *((_QWORD *)this + 26);
    if ( (*(_BYTE *)(v5 + 28) & 0x40) != 0 )
    {
      v6 = 1;
      if ( *(_DWORD *)(v5 + 304) == 2 )
        v6 = 2;
      DWORD1(v36) = v6;
      DWORD2(v36) = *(_DWORD *)(v5 + 288) - *(_DWORD *)(v5 + 280);
      *(_QWORD *)&pguid.Data1 = *(_QWORD *)(v5 + 280);
    }
    v30[0] = 56;
    v30[2] = 0;
    v33 = 0;
    v31 = 1;
    v32 = 1;
    v34 = off_1800570A8;
    v30[1] = RdpIdEvtMonitorCleanup;
    v24 = 0;
    v29[0] = v30;
    v29[1] = &v35;
    v7 = ((__int64 (__fastcall *)(__int64, _QWORD, _QWORD *, __int64 *))qword_180057B28)(
           IddDriverGlobals,
           *(_QWORD *)(*((_QWORD *)this + 29) + 464LL),
           v29,
           &v24);
    if ( v7 < 0 )
      wil::details::in1diag3::_Throw_NtStatus(retaddr, (void *)0x27D, v8, (const char *)(unsigned int)v7, v18);
    v9 = v24;
    *((_QWORD *)this + 28) = v24;
    v10 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(WdfFunctions_02025 + 984))(
            WdfDriverGlobals,
            v9,
            off_1800570A8);
    v11 = std::enable_shared_from_this<CRdpIdAdapter>::shared_from_this(this, &v22);
    std::weak_ptr<CRdpIdMonitor>::operator=<CRdpIdMonitor,0>(v10, v11);
    if ( v23 )
      std::_Ref_count_base::_Decref(v23);
    CRdpIdMonitor::CreateEncodingMonitorContext(this);
    v12 = std::enable_shared_from_this<CRdpIdAdapter>::shared_from_this(this, &v27);
    v22 = (const char *)operator new(0x118u);
    v13 = CRdpIdCursor::CRdpIdCursor(v22, v12);
    v22 = 0;
    v14 = *((_QWORD *)this + 3);
    *((_QWORD *)this + 3) = v13;
    if ( v14 )
      std::default_delete<CRdpIdCursor>::operator()();
    std::unique_ptr<CRdpIdCursor>::~unique_ptr<CRdpIdCursor>(&v22);
    if ( v28 )
      std::_Ref_count_base::_Decref(v28);
    v15 = (*(_DWORD *)(*((_QWORD *)this + 29) + 444LL) & 1) != 0 ? 384 : 96;
    CRdpIdCursor::Initialize(*((CRdpIdCursor **)this + 3), v15, v15);
    v39 = 0;
    v40 = 0;
    v16 = ((__int64 (__fastcall *)(__int64, _QWORD, __int64 *))qword_180057B30)(
            IddDriverGlobals,
            *((_QWORD *)this + 28),
            &v39);
    if ( v16 < 0 )
      wil::details::in1diag3::_Throw_NtStatus(retaddr, (void *)0x2A8, v17, (const char *)(unsigned int)v16, v18);
    *(_QWORD *)((char *)this + 292) = v39;
    *((_DWORD *)this + 72) = v40;
    CRdpIdMonitor::SetDisplayAdapterProperties(this);
    *((_BYTE *)this + 16) = 1;
  }
}

```

## disassembly

```asm
0x180025180  mov     [rsp-8+arg_8], rbx
0x180025185  mov     [rsp-8+arg_10], rdi
0x18002518a  push    rbp
0x18002518b  lea     rbp, [rsp-30h]
0x180025190  sub     rsp, 130h
0x180025197  mov     rax, cs:__security_cookie
0x18002519e  xor     rax, rsp
0x1800251a1  mov     [rbp+30h+var_10], rax
0x1800251a5  mov     rdi, rcx
0x1800251a8  cmp     byte ptr [rcx+10h], 0
0x1800251ac  jnz     loc_1800254DE
0x1800251b2  call    ?get@?$static_lazy@VRdpIddLoggingProvider@@@details@wil@@QEAAPEAVRdpIddLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<RdpIddLoggingProvider>::get(void (*)(void))
0x1800251b7  mov     r8, [rax+8]
0x1800251bb  mov     eax, [r8]
0x1800251be  cmp     eax, 4
0x1800251c1  jbe     loc_180025272
0x1800251c7  mov     rdx, 470000000000h
0x1800251d1  mov     rcx, r8
0x1800251d4  call    _tlgKeywordOn
0x1800251d9  test    al, al
0x1800251db  jz      loc_180025272
0x1800251e1  mov     rax, [rdi+0E8h]
0x1800251e8  mov     ecx, [rax+204h]
0x1800251ee  mov     [rsp+130h+var_DC], ecx
0x1800251f2  mov     eax, [rdi+118h]
0x1800251f8  mov     [rsp+130h+var_E0], eax
0x1800251fc  lea     rax, ?g_CorrelationId@RdpIddLoggingProviderWithCorrelationId@@2U_GUID@@A; _GUID RdpIddLoggingProviderWithCorrelationId::g_CorrelationId
0x180025203  mov     [rsp+130h+var_C0], rax
0x180025208  lea     rax, aRdpidd; "RdpIdd"
0x18002520f  mov     [rsp+130h+var_B8], rax
0x180025214  mov     [rbp+30h+var_B0], 1000000h
0x18002521c  lea     rax, aCheckpoint; "Checkpoint"
0x180025223  mov     [rsp+130h+var_D8], rax
0x180025228  lea     rax, [rsp+130h+var_DC]
0x18002522d  mov     [rsp+130h+var_E8], rax
0x180025232  lea     rax, [rsp+130h+var_E0]
0x180025237  mov     [rsp+130h+var_F0], rax
0x18002523c  lea     rax, [rsp+130h+var_C0]
0x180025241  mov     [rsp+130h+var_F8], rax
0x180025246  lea     rax, [rsp+130h+var_B8]
0x18002524b  mov     [rsp+130h+var_100], rax
0x180025250  lea     rax, [rbp+30h+var_B0]
0x180025254  mov     [rsp+130h+var_108], rax
0x180025259  lea     rax, [rsp+130h+var_D8]
0x18002525e  mov     qword ptr [rsp+130h+var_110], rax
0x180025263  lea     rdx, byte_18004E9B7
0x18002526a  mov     rcx, r8
0x18002526d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@6@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180025272  mov     eax, [rdi+118h]
0x180025278  mov     dword ptr [rsp+130h+var_108], eax
0x18002527c  mov     [rsp+130h+var_110], 257h; int
0x180025284  lea     r9, aOnecoreuapTerm_12; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x18002528b  lea     r8, aCrdpidmonitorH; "CRdpIdMonitor::HPDMonitor"
0x180025292  lea     rdx, aMonitorhpdIdD; "MonitorHPD: Id %d"
0x180025299  lea     rcx, ?g_Ifr@CInflightRecorder@Utils@Modern@Rdp@@0V1234@A; this
0x1800252a0  call    ?pushN@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1IZZ; Rdp::Modern::Utils::CInflightRecorder::pushN(ushort const *,char const *,char const *,uint,...)
0x1800252a5  xorps   xmm0, xmm0
0x1800252a8  xor     eax, eax
0x1800252aa  movups  [rbp+30h+var_58], xmm0
0x1800252ae  movups  [rbp+30h+var_48], xmm0
0x1800252b2  movups  xmmword ptr [rbp+30h+pguid.Data1], xmm0
0x1800252b6  mov     [rbp+30h+var_28], rax
0x1800252ba  lea     ebx, [rax+38h]
0x1800252bd  mov     dword ptr [rbp+30h+var_58], ebx
0x1800252c0  lea     rcx, [rbp+30h+pguid.Data4]; pguid
0x1800252c4  call    cs:__imp_CoCreateGuid
0x1800252cb  nop     dword ptr [rax+rax+00h]
0x1800252d0  mov     dword ptr [rbp+30h+var_58+4], 0FFFFFFFFh
0x1800252d7  mov     eax, [rdi+11Ch]
0x1800252dd  mov     dword ptr [rbp+30h+var_58+8], eax
0x1800252e0  mov     dword ptr [rbp+30h+var_48], 18h
0x1800252e7  mov     dword ptr [rbp+30h+var_48+4], 1
0x1800252ee  mov     rcx, [rdi+0D0h]
0x1800252f5  test    byte ptr [rcx+1Ch], 40h
0x1800252f9  jz      short loc_180025327
0x1800252fb  lea     eax, [rbx-37h]
0x1800252fe  lea     edx, [rbx-36h]
0x180025301  cmp     [rcx+130h], edx
0x180025307  cmovz   eax, edx
0x18002530a  mov     dword ptr [rbp+30h+var_48+4], eax
0x18002530d  mov     eax, [rcx+120h]
0x180025313  sub     eax, [rcx+118h]
0x180025319  mov     dword ptr [rbp+30h+var_48+8], eax
0x18002531c  mov     rax, [rcx+118h]
0x180025323  mov     qword ptr [rbp+30h+pguid.Data1], rax
0x180025327  mov     [rbp+30h+var_90], rbx
0x18002532b  mov     [rbp+30h+var_80], 0
0x180025333  xorps   xmm0, xmm0
0x180025336  movdqu  [rbp+30h+var_70], xmm0
0x18002533b  mov     [rbp+30h+var_78], 1
0x180025342  mov     [rbp+30h+var_74], 1
0x180025349  mov     rax, cs:off_1800570A8
0x180025350  mov     [rbp+30h+var_60], rax
0x180025354  lea     rax, ?RdpIdEvtMonitorCleanup@@YAXPEAX@Z; RdpIdEvtMonitorCleanup(void *)
0x18002535b  mov     [rbp+30h+var_88], rax
0x18002535f  mov     [rsp+130h+var_C8], 0
0x180025368  lea     rax, [rbp+30h+var_90]
0x18002536c  mov     [rbp+30h+var_A0], rax
0x180025370  lea     rax, [rbp+30h+var_58]
0x180025374  mov     [rbp+30h+var_98], rax
0x180025378  mov     rdx, [rdi+0E8h]
0x18002537f  lea     r9, [rsp+130h+var_C8]
0x180025384  lea     r8, [rbp+30h+var_A0]
0x180025388  mov     rdx, [rdx+1D0h]
0x18002538f  mov     rcx, cs:IddDriverGlobals
0x180025396  mov     rax, cs:qword_180057B28
0x18002539d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800253a2  mov     rcx, [rbp+38h]; this
0x1800253a6  test    eax, eax
0x1800253a8  js      loc_180025512
0x1800253ae  mov     rdx, [rsp+130h+var_C8]
0x1800253b3  mov     [rdi+0E0h], rdx
0x1800253ba  mov     rax, cs:WdfFunctions_02025
0x1800253c1  mov     r8, cs:off_1800570A8
0x1800253c8  mov     rcx, cs:WdfDriverGlobals
0x1800253cf  mov     rax, [rax+3D8h]
0x1800253d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800253db  mov     rbx, rax
0x1800253de  lea     rdx, [rsp+130h+var_D8]
0x1800253e3  mov     rcx, rdi
0x1800253e6  call    ?shared_from_this@?$enable_shared_from_this@VCRdpIdAdapter@@@std@@QEAA?AV?$shared_ptr@VCRdpIdAdapter@@@2@XZ; std::enable_shared_from_this<CRdpIdAdapter>::shared_from_this(void)
0x1800253eb  mov     rdx, rax
0x1800253ee  mov     rcx, rbx
0x1800253f1  call    ??$?4VCRdpIdMonitor@@$0A@@?$weak_ptr@VCRdpIdMonitor@@@std@@QEAAAEAV01@AEBV?$shared_ptr@VCRdpIdMonitor@@@1@@Z; std::weak_ptr<CRdpIdMonitor>::operator=<CRdpIdMonitor,0>(std::shared_ptr<CRdpIdMonitor> const &)
0x1800253f6  mov     rcx, [rsp+130h+var_D0]; this
0x1800253fb  test    rcx, rcx
0x1800253fe  jz      short loc_180025405
0x180025400  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180025405  mov     rcx, rdi; this
0x180025408  call    ?CreateEncodingMonitorContext@CRdpIdMonitor@@AEAAXXZ; CRdpIdMonitor::CreateEncodingMonitorContext(void)
0x18002540d  lea     rdx, [rbp+30h+var_B0]
0x180025411  mov     rcx, rdi
0x180025414  call    ?shared_from_this@?$enable_shared_from_this@VCRdpIdAdapter@@@std@@QEAA?AV?$shared_ptr@VCRdpIdAdapter@@@2@XZ; std::enable_shared_from_this<CRdpIdAdapter>::shared_from_this(void)
0x180025419  mov     rbx, rax
0x18002541c  mov     ecx, 118h; Size
0x180025421  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180025426  mov     [rsp+130h+var_D8], rax
0x18002542b  mov     rdx, rbx
0x18002542e  mov     rcx, rax
0x180025431  call    ??0CRdpIdCursor@@QEAA@AEBV?$shared_ptr@VCRdpIdMonitor@@@std@@@Z; CRdpIdCursor::CRdpIdCursor(std::shared_ptr<CRdpIdMonitor> const &)
0x180025436  mov     [rsp+130h+var_D8], 0
0x18002543f  mov     rdx, [rdi+18h]
0x180025443  mov     [rdi+18h], rax
0x180025447  test    rdx, rdx
0x18002544a  jz      short loc_180025451
0x18002544c  call    ??R?$default_delete@VCRdpIdCursor@@@std@@QEBAXPEAVCRdpIdCursor@@@Z; std::default_delete<CRdpIdCursor>::operator()(CRdpIdCursor *)
0x180025451  lea     rcx, [rsp+130h+var_D8]
0x180025456  call    ??1?$unique_ptr@VCRdpIdCursor@@U?$default_delete@VCRdpIdCursor@@@std@@@std@@QEAA@XZ; std::unique_ptr<CRdpIdCursor>::~unique_ptr<CRdpIdCursor>(void)
0x18002545b  nop
0x18002545c  mov     rcx, [rbp+30h+var_A8]; this
0x180025460  test    rcx, rcx
0x180025463  jz      short loc_18002546A
0x180025465  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002546a  mov     rax, [rdi+0E8h]
0x180025471  mov     ecx, [rax+1BCh]
0x180025477  and     cl, 1
0x18002547a  neg     cl
0x18002547c  sbb     edx, edx
0x18002547e  and     edx, 120h
0x180025484  add     edx, 60h ; '`'; unsigned int
0x180025487  mov     r8d, edx; unsigned int
0x18002548a  mov     rcx, [rdi+18h]; this
0x18002548e  call    ?Initialize@CRdpIdCursor@@QEAAXII@Z; CRdpIdCursor::Initialize(uint,uint)
0x180025493  xor     eax, eax
0x180025495  mov     [rbp+30h+var_20], rax
0x180025499  mov     [rbp+30h+var_18], eax
0x18002549c  lea     r8, [rbp+30h+var_20]
0x1800254a0  mov     rdx, [rdi+0E0h]
0x1800254a7  mov     rcx, cs:IddDriverGlobals
0x1800254ae  mov     rax, cs:qword_180057B30
0x1800254b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800254ba  test    eax, eax
0x1800254bc  js      short loc_180025500
0x1800254be  mov     rax, [rbp+30h+var_20]
0x1800254c2  mov     [rdi+124h], rax
0x1800254c9  mov     eax, [rbp+30h+var_18]
0x1800254cc  mov     [rdi+120h], eax
0x1800254d2  mov     rcx, rdi; this
0x1800254d5  call    ?SetDisplayAdapterProperties@CRdpIdMonitor@@AEAAXXZ; CRdpIdMonitor::SetDisplayAdapterProperties(void)
0x1800254da  mov     byte ptr [rdi+10h], 1
0x1800254de  mov     rcx, [rbp+30h+var_10]
0x1800254e2  xor     rcx, rsp; StackCookie
0x1800254e5  call    __security_check_cookie
0x1800254ea  lea     r11, [rsp+130h+var_s0]
0x1800254f2  mov     rbx, [r11+18h]
0x1800254f6  mov     rdi, [r11+20h]
0x1800254fa  mov     rsp, r11
0x1800254fd  pop     rbp
0x1800254fe  retn
0x180025500  mov     rcx, [rbp+38h]; this
0x180025504  mov     r9d, eax; char *
0x180025507  mov     edx, 2A8h; void *
0x18002550c  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x180025512  mov     r9d, eax; char *
0x180025515  mov     edx, 27Dh; void *
0x18002551a  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
```
