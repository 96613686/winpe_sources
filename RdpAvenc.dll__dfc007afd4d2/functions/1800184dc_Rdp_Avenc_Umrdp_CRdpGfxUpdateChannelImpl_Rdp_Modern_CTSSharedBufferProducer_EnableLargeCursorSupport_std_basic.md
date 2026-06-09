# Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<Rdp::Modern::CTSSharedBufferProducer>::EnableLargeCursorSupport(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,uint,bool)

- ea: `0x1800184dc`
- end: `0x1800188dd`
- name: `?EnableLargeCursorSupport@?$CRdpGfxUpdateChannelImpl@VCTSSharedBufferProducer@Modern@Rdp@@@Umrdp@Avenc@Rdp@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@I_N@Z`
- size: `1025`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `27`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x180013264`

## callees

- `0x180001114`
- `0x180006580`
- `0x1800065a4`
- `0x1800069a0`
- `0x1800080cc`
- `0x18000abb8`
- `0x18000b07c`
- `0x18000d0ac`
- `0x18000e848`
- `0x180011298`
- `0x180011654`
- `0x1800118c0`
- `0x180011c4c`
- `0x180013ce4`
- `0x1800156d0`
- `0x180016a9c`
- `0x180017cf8`
- `0x180018108`
- `0x180018194`
- `0x1800184dc`
- `0x1800188e4`
- `0x1800199cc`
- `0x180019c04`
- `0x180019d6c`
- `0x18007d7a4`
- `0x180082e9c`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180018804`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180018804`

## string_xrefs

- `0x180018635`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\umrdpprocessor\updatechannel.cpp`
- `0x1800186eb`: `Created shared buffer for Rdp cursor shape`
- `0x1800186fe`: `Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<class Rdp::Modern::CTSSharedBufferProducer>::EnableLargeCursorSupport`
- `0x1800187cd`: `Failed to copy pwszCursorBufferName`
- `0x1800188c3`: `Failed to commit event %d to shared memory`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<Rdp::Modern::CTSSharedBufferProducer>::EnableLargeCursorSupport(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        bool a4)
{
  __int64 v8; // rax
  Rdp::Avenc::Umrdp::CRdpSharedMemoryServerWithSA *v9; // rbx
  __int64 v10; // rax
  __int64 v11; // rax
  const void *v12; // r9
  unsigned __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // rdi
  _QWORD *v16; // rbx
  __int64 v17; // rcx
  const WCHAR *v18; // rax
  const WCHAR *v19; // rcx
  int v20; // r8d
  __int64 v21; // rdx
  int v22; // edx
  __int64 v23; // rax
  Rdp::Avenc::Umrdp::CRdpSharedMemoryServerWithSA *v24; // rbx
  __int64 v25; // rdx
  _QWORD *v26; // rax
  unsigned int v27; // eax
  int v28; // edi
  unsigned int v29; // r8d
  const char *v30; // r9
  volatile signed __int32 *v31; // rbx
  __int64 v33; // rax
  int v34; // ebx
  __int64 v35; // rcx
  unsigned __int8 *Header; // rax
  Rdp::Modern::CTSSharedBufferProducer *v37; // rcx
  unsigned int v38; // eax
  char *v39; // [rsp+28h] [rbp-D8h]
  char *v40; // [rsp+28h] [rbp-D8h]
  unsigned int v41; // [rsp+30h] [rbp-D0h] BYREF
  Rdp::Avenc::Umrdp::CRdpSharedMemoryServerWithSA *v42; // [rsp+38h] [rbp-C8h] BYREF
  volatile signed __int32 *v43; // [rsp+40h] [rbp-C0h]
  _QWORD Src[2]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v45; // [rsp+68h] [rbp-98h]
  unsigned __int64 v46; // [rsp+70h] [rbp-90h]
  char v47[40]; // [rsp+78h] [rbp-88h] BYREF
  char v48[32]; // [rsp+A0h] [rbp-60h] BYREF
  const char *v49; // [rsp+C0h] [rbp-40h]
  __int64 v50; // [rsp+C8h] [rbp-38h]
  Rdp::Avenc::Umrdp::CRdpSharedMemoryServerWithSA **v51; // [rsp+D0h] [rbp-30h]
  __int64 v52; // [rsp+D8h] [rbp-28h]
  const char *v53; // [rsp+E0h] [rbp-20h]
  __int64 v54; // [rsp+E8h] [rbp-18h]
  const char *v55; // [rsp+F0h] [rbp-10h]
  __int64 v56; // [rsp+F8h] [rbp-8h]
  int *v57; // [rsp+100h] [rbp+0h]
  __int64 v58; // [rsp+108h] [rbp+8h]
  const WCHAR *v59; // [rsp+110h] [rbp+10h]
  int v60; // [rsp+118h] [rbp+18h]
  int v61; // [rsp+11Ch] [rbp+1Ch]
  const WCHAR *v62; // [rsp+120h] [rbp+20h]
  int v63; // [rsp+128h] [rbp+28h]
  int v64; // [rsp+12Ch] [rbp+2Ch]
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+78h]

  if ( !*(_BYTE *)(a1 + 144) )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  v42 = (Rdp::Avenc::Umrdp::CRdpSharedMemoryServerWithSA *)operator new(0x60u);
  v8 = Rdp::Avenc::Umrdp::CRdpSharedMemoryServerWithSA::CRdpSharedMemoryServerWithSA(v42, a4);
  v9 = *(Rdp::Avenc::Umrdp::CRdpSharedMemoryServerWithSA **)(a1 + 152);
  *(_QWORD *)(a1 + 152) = v8;
  if ( v9 )
  {
    Rdp::Avenc::Umrdp::CRdpSharedMemoryServerWithSA::~CRdpSharedMemoryServerWithSA(v9);
    operator delete(v9);
  }
  std::wstring::wstring(Src, L"RdpCursorShape");
  v10 = std::to_wstring(v47, a3);
  v11 = std::operator+<unsigned short>(&v42, L"_S", v10);
  v12 = (const void *)v11;
  v13 = *(_QWORD *)(v11 + 16);
  if ( *(_QWORD *)(v11 + 24) > 7u )
    v12 = *(const void **)v11;
  v14 = v45;
  if ( v13 > v46 - v45 )
  {
    ____Reallocate_grow_by_V_lambda_1___1_____Append_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV23_QEBG_K_Z_PEBG_K___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1_____Append_G_01_AEAAAEAV01_QEBG0_Z_PEBG_K_Z(
      Src,
      v13);
  }
  else
  {
    v15 = v13 + v45;
    v45 += v13;
    v16 = Src;
    if ( v46 > 7 )
      v16 = (_QWORD *)Src[0];
    memmove_0((char *)v16 + 2 * v14, v12, 2 * v13);
    *((_WORD *)v16 + v15) = 0;
  }
  std::wstring::~wstring(&v42);
  std::wstring::~wstring(v47);
  Rdp::Avenc::Umrdp::CRdpSharedMemoryServerWithSA::Create(*(_QWORD *)(a1 + 152), a2, Src, 608292);
  if ( (unsigned int)dword_1800C1058 > 4 )
  {
    v17 = *(_QWORD *)(a1 + 152);
    v18 = (const WCHAR *)(v17 + 16);
    if ( *(_QWORD *)(v17 + 40) > 7u )
      v18 = *(const WCHAR **)v18;
    v19 = (const WCHAR *)(v17 + 48);
    if ( *((_QWORD *)v19 + 3) > 7u )
      v19 = *(const WCHAR **)v19;
    v41 = a3;
    LODWORD(v42) = 188;
    v20 = 2;
    if ( v18 )
    {
      v21 = -1;
      do
        ++v21;
      while ( v18[v21] );
      v22 = 2 * v21 + 2;
    }
    else
    {
      v18 = &word_18008F93C;
      v22 = 2;
    }
    v62 = v18;
    v63 = v22;
    v64 = 0;
    if ( v19 )
    {
      v23 = -1;
      do
        ++v23;
      while ( v19[v23] );
      v20 = 2 * v23 + 2;
    }
    else
    {
      v19 = &word_18008F93C;
    }
    v59 = v19;
    v60 = v20;
    v61 = 0;
    v57 = (int *)&v41;
    v58 = 4;
    v55 = "Created shared buffer for Rdp cursor shape";
    v56 = 43;
    v53 = "Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<class Rdp::Modern::CTSSharedBufferProducer>::EnableLargeCursorSupport";
    v54 = 114;
    v51 = &v42;
    v52 = 4;
    v49 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\updatechannel.cpp";
    v50 = 73;
    tlgWriteTransfer_EventWriteTransfer(&dword_1800C1058, byte_1800ACA31, 0, 0, 9, v48);
  }
  Rdp::Modern::CTSSharedBufferProducer::SetCursorSharedBuffer(
    *(Rdp::Modern::CTSSharedBufferProducer **)(a1 + 104),
    *(unsigned __int8 **)(*(_QWORD *)(a1 + 152) + 8LL),
    *(_DWORD *)(*(_QWORD *)(a1 + 152) + 80LL));
  Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<Rdp::Modern::CTSSharedBufferProducer>::AllocSharedBufEvent<tagUMRDP_MAP_CURSOR_BUFFER_EVENT>(
    a1,
    &v42);
  v24 = v42;
  v25 = *((_QWORD *)v42 + 2);
  *(_DWORD *)(v25 + 144) = *(_DWORD *)(*(_QWORD *)(a1 + 152) + 80LL);
  v26 = (_QWORD *)(*(_QWORD *)(a1 + 152) + 48LL);
  if ( *(_QWORD *)(*(_QWORD *)(a1 + 152) + 72LL) > 7u )
    v26 = (_QWORD *)*v26;
  v27 = StringCchPrintfW((unsigned __int16 *)(v25 + 16), 0x40u, L"%s%s", L"Global\\", v26);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0xD2,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\updatechannel.cpp",
    (const char *)v27,
    (int)"Failed to copy pwszCursorBufferName",
    v39);
  v28 = Rdp::Modern::CTSSharedBufferProducer::CommitBuffer(
          *(Rdp::Modern::CTSSharedBufferProducer **)(a1 + 104),
          *((unsigned __int8 **)v24 + 2));
  if ( v28 < 0 )
  {
    v33 = std::shared_ptr<Rdp::Avenc::Umrdp::CRdpSharedBufEvent<UMRDP_CREATE_SURFACE_EVENT_EX>>::operator-><Rdp::Avenc::Umrdp::CRdpSharedBufEvent<UMRDP_CREATE_SURFACE_EVENT_EX>,0>(&v42);
    v34 = *(_DWORD *)Rdp::Avenc::Umrdp::CRdpSharedBufEvent<tagUMRDP_MAP_CURSOR_BUFFER_EVENT>::getHeader(v33);
    Header = (unsigned __int8 *)Rdp::Avenc::Umrdp::CRdpSharedBufEvent<tagUMRDP_MAP_CURSOR_BUFFER_EVENT>::getHeader(v35);
    Rdp::Modern::CTSSharedBufferProducer::FreeBuffer(v37, Header);
    v38 = wil::verify_hresult<long>((unsigned int)v28);
    LODWORD(v40) = v34;
    wil::details::in1diag3::Throw_HrMsg(
      retaddr,
      (void *)0x14D,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\updatechannel.cpp",
      (const char *)v38,
      (int)"Failed to commit event %d to shared memory",
      v40);
  }
  if ( !SetEvent(*(HANDLE *)(a1 + 112)) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA01, v29, v30);
  v31 = v43;
  if ( v43 )
  {
    if ( _InterlockedExchangeAdd(v43 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v31)(v31);
      if ( _InterlockedExchangeAdd(v31 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v31 + 8LL))(v31);
    }
  }
  return std::wstring::~wstring(Src);
}

```

## disassembly

```asm
0x1800184dc  mov     [rsp-8+arg_18], rbx
0x1800184e1  push    rbp
0x1800184e2  push    rsi
0x1800184e3  push    rdi
0x1800184e4  push    r12
0x1800184e6  push    r13
0x1800184e8  push    r14
0x1800184ea  push    r15
0x1800184ec  lea     rbp, [rsp-40h]
0x1800184f1  sub     rsp, 140h
0x1800184f8  mov     rax, cs:__security_cookie
0x1800184ff  xor     rax, rsp
0x180018502  mov     [rbp+70h+var_40], rax
0x180018506  mov     bl, r9b
0x180018509  mov     r14d, r8d
0x18001850c  mov     r15, rdx
0x18001850f  mov     rsi, rcx
0x180018512  xor     r12d, r12d
0x180018515  cmp     [rcx+90h], r12b
0x18001851c  jnz     short loc_180018523
0x18001851e  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180018523  mov     edi, 60h ; '`'
0x180018528  mov     ecx, edi; Size
0x18001852a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001852f  mov     [rsp+170h+var_138], rax
0x180018534  mov     dl, bl; bool
0x180018536  mov     rcx, rax; this
0x180018539  call    ??0CRdpSharedMemoryServerWithSA@Umrdp@Avenc@Rdp@@QEAA@_N@Z; Rdp::Avenc::Umrdp::CRdpSharedMemoryServerWithSA::CRdpSharedMemoryServerWithSA(bool)
0x18001853e  nop
0x18001853f  mov     rbx, [rsi+98h]
0x180018546  mov     [rsi+98h], rax
0x18001854d  test    rbx, rbx
0x180018550  jz      short loc_180018564
0x180018552  mov     rcx, rbx; this
0x180018555  call    ??1CRdpSharedMemoryServerWithSA@Umrdp@Avenc@Rdp@@QEAA@XZ; Rdp::Avenc::Umrdp::CRdpSharedMemoryServerWithSA::~CRdpSharedMemoryServerWithSA(void)
0x18001855a  mov     edx, edi
0x18001855c  mov     rcx, rbx; Block
0x18001855f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180018564  lea     rdx, aRdpcursorshape; "RdpCursorShape"
0x18001856b  lea     rcx, [rsp+170h+Src]
0x180018570  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180018575  nop
0x180018576  mov     edx, r14d
0x180018579  lea     rcx, [rsp+170h+var_F8]
0x18001857e  call    ?to_wstring@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@I@Z; std::to_wstring(uint)
0x180018583  nop
0x180018584  mov     r8, rax
0x180018587  lea     rdx, aS; "_S"
0x18001858e  lea     rcx, [rsp+170h+var_138]
0x180018593  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEBG$$QEAV10@@Z; std::operator+<ushort>(ushort const * const,std::wstring &&)
0x180018598  mov     r9, rax
0x18001859b  mov     rdx, [rax+10h]
0x18001859f  cmp     qword ptr [rax+18h], 7
0x1800185a4  jbe     short loc_1800185A9
0x1800185a6  mov     r9, [rax]
0x1800185a9  mov     rcx, [rsp+170h+var_108]
0x1800185ae  mov     rax, [rsp+170h+var_100]
0x1800185b3  sub     rax, rcx
0x1800185b6  cmp     rdx, rax
0x1800185b9  ja      short loc_1800185EC
0x1800185bb  lea     rdi, [rdx+rcx]
0x1800185bf  mov     [rsp+170h+var_108], rdi
0x1800185c4  lea     rbx, [rsp+170h+Src]
0x1800185c9  cmp     [rsp+170h+var_100], 7
0x1800185cf  cmova   rbx, [rsp+170h+Src]
0x1800185d5  lea     r8, [rdx+rdx]; Size
0x1800185d9  lea     rcx, [rbx+rcx*2]; void *
0x1800185dd  mov     rdx, r9; Src
0x1800185e0  call    memmove_0
0x1800185e5  mov     [rbx+rdi*2], r12w
0x1800185ea  jmp     short loc_1800185FC
0x1800185ec  mov     [rsp+170h+var_150], rdx; __int64
0x1800185f1  lea     rcx, [rsp+170h+Src]; Src
0x1800185f6  call    ??$_Reallocate_grow_by@V_lambda_1_@?1???$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV23@QEBG_K@Z@PEBG_K@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1???$_Append@G@01@AEAAAEAV01@QEBG0@Z@PEBG_K@Z; std::wstring::_Reallocate_grow_by<`std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *,unsigned __int64>(unsigned __int64,`std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *,unsigned __int64)
0x1800185fb  nop
0x1800185fc  lea     rcx, [rsp+170h+var_138]
0x180018601  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180018606  nop
0x180018607  lea     rcx, [rsp+170h+var_F8]
0x18001860c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180018611  mov     r9d, 94824h
0x180018617  lea     r8, [rsp+170h+Src]
0x18001861c  mov     rdx, r15
0x18001861f  mov     rcx, [rsi+98h]
0x180018626  call    ?Create@CRdpSharedMemoryServerWithSA@Umrdp@Avenc@Rdp@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0_KI@Z; Rdp::Avenc::Umrdp::CRdpSharedMemoryServerWithSA::Create(std::wstring const &,std::wstring const &,unsigned __int64,uint)
0x18001862b  mov     eax, cs:dword_1800C1058
0x180018631  or      r15, 0FFFFFFFFFFFFFFFFh
0x180018635  lea     r13, aOnecoreuapTerm_36; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18001863c  lea     r9d, [r15+5]
0x180018640  cmp     eax, r9d
0x180018643  jbe     loc_180018754
0x180018649  mov     rcx, [rsi+98h]
0x180018650  lea     rax, [rcx+10h]
0x180018654  cmp     qword ptr [rax+18h], 7
0x180018659  jbe     short loc_18001865E
0x18001865b  mov     rax, [rax]
0x18001865e  add     rcx, 30h ; '0'
0x180018662  cmp     qword ptr [rcx+18h], 7
0x180018667  jbe     short loc_18001866C
0x180018669  mov     rcx, [rcx]
0x18001866c  mov     [rsp+170h+var_140], r14d
0x180018671  mov     dword ptr [rsp+170h+var_138], 0BCh
0x180018679  mov     r8d, 2
0x18001867f  test    rax, rax
0x180018682  jz      short loc_18001869A
0x180018684  mov     rdx, r15
0x180018687  inc     rdx
0x18001868a  cmp     [rax+rdx*2], r12w
0x18001868f  jnz     short loc_180018687
0x180018691  lea     edx, ds:2[rdx*2]
0x180018698  jmp     short loc_1800186A4
0x18001869a  lea     rax, word_18008F93C
0x1800186a1  mov     edx, r8d
0x1800186a4  mov     [rbp+70h+var_50], rax
0x1800186a8  mov     [rbp+70h+var_48], edx
0x1800186ab  mov     [rbp+70h+var_44], r12d
0x1800186af  test    rcx, rcx
0x1800186b2  jz      short loc_1800186CB
0x1800186b4  mov     rax, r15
0x1800186b7  inc     rax
0x1800186ba  cmp     [rcx+rax*2], r12w
0x1800186bf  jnz     short loc_1800186B7
0x1800186c1  lea     r8d, ds:2[rax*2]
0x1800186c9  jmp     short loc_1800186D2
0x1800186cb  lea     rcx, word_18008F93C
0x1800186d2  mov     [rbp+70h+var_60], rcx
0x1800186d6  mov     [rbp+70h+var_58], r8d
0x1800186da  mov     [rbp+70h+var_54], r12d
0x1800186de  lea     rax, [rsp+170h+var_140]
0x1800186e3  mov     [rbp+70h+var_70], rax
0x1800186e7  mov     [rbp+70h+var_68], r9
0x1800186eb  lea     rax, aCreatedSharedB; "Created shared buffer for Rdp cursor sh"...
0x1800186f2  mov     [rbp+70h+var_80], rax
0x1800186f6  mov     [rbp+70h+var_78], 2Bh ; '+'
0x1800186fe  lea     rax, aRdpAvencUmrdpC_15; "Rdp::Avenc::Umrdp::CRdpGfxUpdateChannel"...
0x180018705  mov     [rbp+70h+var_90], rax
0x180018709  mov     [rbp+70h+var_88], 72h ; 'r'
0x180018711  lea     rax, [rsp+170h+var_138]
0x180018716  mov     [rbp+70h+var_A0], rax
0x18001871a  mov     [rbp+70h+var_98], r9
0x18001871e  mov     [rbp+70h+var_B0], r13
0x180018722  mov     [rbp+70h+var_A8], 49h ; 'I'
0x18001872a  lea     rax, [rbp+70h+var_D0]
0x18001872e  mov     [rsp+170h+var_148], rax; char *
0x180018733  mov     dword ptr [rsp+170h+var_150], 9
0x18001873b  xor     r9d, r9d
0x18001873e  xor     r8d, r8d
0x180018741  lea     rdx, byte_1800ACA31
0x180018748  lea     rcx, dword_1800C1058
0x18001874f  call    _tlgWriteTransfer_EventWriteTransfer
0x180018754  mov     rdx, [rsi+98h]
0x18001875b  mov     r8d, [rdx+50h]; unsigned int
0x18001875f  mov     rdx, [rdx+8]; unsigned __int8 *
0x180018763  mov     rcx, [rsi+68h]; this
0x180018767  call    ?SetCursorSharedBuffer@CTSSharedBufferProducer@Modern@Rdp@@QEAAJPEAEK@Z; Rdp::Modern::CTSSharedBufferProducer::SetCursorSharedBuffer(uchar *,ulong)
0x18001876c  lea     rdx, [rsp+170h+var_138]
0x180018771  mov     rcx, rsi
0x180018774  call    ??$AllocSharedBufEvent@UtagUMRDP_MAP_CURSOR_BUFFER_EVENT@@@?$CRdpGfxUpdateChannelImpl@VCTSSharedBufferProducer@Modern@Rdp@@@Umrdp@Avenc@Rdp@@AEAA?AV?$shared_ptr@V?$CRdpSharedBufEvent@UtagUMRDP_MAP_CURSOR_BUFFER_EVENT@@@Umrdp@Avenc@Rdp@@@std@@W4UMRDP_EVENT_TYPE@@I@Z; Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<Rdp::Modern::CTSSharedBufferProducer>::AllocSharedBufEvent<tagUMRDP_MAP_CURSOR_BUFFER_EVENT>(UMRDP_EVENT_TYPE,uint)
0x180018779  nop
0x18001877a  mov     rbx, [rsp+170h+var_138]
0x18001877f  mov     rdx, [rbx+10h]
0x180018783  mov     rax, [rsi+98h]
0x18001878a  mov     ecx, [rax+50h]
0x18001878d  mov     [rdx+90h], ecx
0x180018793  mov     rax, [rsi+98h]
0x18001879a  add     rax, 30h ; '0'
0x18001879e  cmp     qword ptr [rax+18h], 7
0x1800187a3  jbe     short loc_1800187A8
0x1800187a5  mov     rax, [rax]
0x1800187a8  lea     rcx, [rdx+10h]; unsigned __int16 *
0x1800187ac  mov     [rsp+170h+var_150], rax
0x1800187b1  lea     r9, aGlobal; "Global\\"
0x1800187b8  lea     r8, aSS; "%s%s"
0x1800187bf  mov     edx, 40h ; '@'; unsigned __int64
0x1800187c4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800187c9  mov     rcx, [rbp+78h]; this
0x1800187cd  lea     rdx, aFailedToCopyPw; "Failed to copy pwszCursorBufferName"
0x1800187d4  mov     [rsp+170h+var_150], rdx; int
0x1800187d9  mov     r9d, eax; char *
0x1800187dc  mov     r8, r13; unsigned int
0x1800187df  mov     edx, 0D2h; void *
0x1800187e4  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800187e9  mov     rdx, [rbx+10h]; unsigned __int8 *
0x1800187ed  mov     rcx, [rsi+68h]; this
0x1800187f1  call    ?CommitBuffer@CTSSharedBufferProducer@Modern@Rdp@@QEAAJPEAE@Z; Rdp::Modern::CTSSharedBufferProducer::CommitBuffer(uchar *)
0x1800187f6  mov     edi, eax
0x1800187f8  test    eax, eax
0x1800187fa  js      loc_180018890
0x180018800  mov     rcx, [rsi+70h]; hEvent
0x180018804  call    cs:__imp_SetEvent
0x18001880a  mov     rcx, [rbp+78h]; this
0x18001880e  test    eax, eax
0x180018810  jz      short loc_180018885
0x180018812  mov     rbx, [rsp+170h+var_130]
0x180018817  test    rbx, rbx
0x18001881a  jz      short loc_180018854
0x18001881c  mov     eax, r15d
0x18001881f  lock xadd [rbx+8], eax
0x180018824  add     eax, r15d
0x180018827  jnz     short loc_180018854
0x180018829  mov     rax, [rbx]
0x18001882c  mov     rcx, rbx
0x18001882f  mov     rax, [rax]
0x180018832  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018837  mov     eax, r15d
0x18001883a  lock xadd [rbx+0Ch], eax
0x18001883f  add     eax, r15d
0x180018842  jnz     short loc_180018854
0x180018844  mov     rax, [rbx]
0x180018847  mov     rcx, rbx
0x18001884a  mov     rax, [rax+8]
0x18001884e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018853  nop
0x180018854  lea     rcx, [rsp+170h+Src]
0x180018859  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001885e  mov     rcx, [rbp+70h+var_40]
0x180018862  xor     rcx, rsp; StackCookie
0x180018865  call    __security_check_cookie
0x18001886a  mov     rbx, [rsp+170h+arg_18]
0x180018872  add     rsp, 140h
0x180018879  pop     r15
0x18001887b  pop     r14
0x18001887d  pop     r13
0x18001887f  pop     r12
0x180018881  pop     rdi
0x180018882  pop     rsi
0x180018883  pop     rbp
0x180018884  retn
0x180018885  mov     edx, 0A01h; void *
0x18001888a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180018890  lea     rcx, [rsp+170h+var_138]
0x180018895  call    ??$?CV?$CRdpSharedBufEvent@UUMRDP_CREATE_SURFACE_EVENT_EX@@@Umrdp@Avenc@Rdp@@$0A@@?$shared_ptr@V?$CRdpSharedBufEvent@UUMRDP_CREATE_SURFACE_EVENT_EX@@@Umrdp@Avenc@Rdp@@@std@@QEBAPEAV?$CRdpSharedBufEvent@UUMRDP_CREATE_SURFACE_EVENT_EX@@@Umrdp@Avenc@Rdp@@XZ; std::shared_ptr<Rdp::Avenc::Umrdp::CRdpSharedBufEvent<UMRDP_CREATE_SURFACE_EVENT_EX>>::operator-><Rdp::Avenc::Umrdp::CRdpSharedBufEvent<UMRDP_CREATE_SURFACE_EVENT_EX>,0>(void)
0x18001889a  mov     rcx, rax
0x18001889d  call    ?getHeader@?$CRdpSharedBufEvent@UtagUMRDP_MAP_CURSOR_BUFFER_EVENT@@@Umrdp@Avenc@Rdp@@QEAAPEAUUMRDP_EVENT_HEADER@@XZ; Rdp::Avenc::Umrdp::CRdpSharedBufEvent<tagUMRDP_MAP_CURSOR_BUFFER_EVENT>::getHeader(void)
0x1800188a2  mov     ebx, [rax]
0x1800188a4  call    ?getHeader@?$CRdpSharedBufEvent@UtagUMRDP_MAP_CURSOR_BUFFER_EVENT@@@Umrdp@Avenc@Rdp@@QEAAPEAUUMRDP_EVENT_HEADER@@XZ; Rdp::Avenc::Umrdp::CRdpSharedBufEvent<tagUMRDP_MAP_CURSOR_BUFFER_EVENT>::getHeader(void)
0x1800188a9  mov     rdx, rax; unsigned __int8 *
0x1800188ac  call    ?FreeBuffer@CTSSharedBufferProducer@Modern@Rdp@@QEAAJPEAE@Z; Rdp::Modern::CTSSharedBufferProducer::FreeBuffer(uchar *)
0x1800188b1  mov     ecx, edi
0x1800188b3  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x1800188b8  mov     r9d, eax; char *
0x1800188bb  mov     rcx, [rbp+78h]; this
0x1800188bf  mov     dword ptr [rsp+170h+var_148], ebx; char *
0x1800188c3  lea     rax, aFailedToCommit; "Failed to commit event %d to shared mem"...
0x1800188ca  mov     [rsp+170h+var_150], rax; int
0x1800188cf  mov     r8, r13; unsigned int
0x1800188d2  mov     edx, 14Dh; void *
0x1800188d7  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
```
