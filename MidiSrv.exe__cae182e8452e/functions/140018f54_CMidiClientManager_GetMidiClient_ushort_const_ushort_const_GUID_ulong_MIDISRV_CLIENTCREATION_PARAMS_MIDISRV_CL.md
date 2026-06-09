# CMidiClientManager::GetMidiClient(ushort const *,ushort const *,_GUID,ulong,MIDISRV_CLIENTCREATION_PARAMS *,MIDISRV_CLIENT *,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &,wil::com_ptr_t<CMidiPipe,wil::err_returncode_policy> &,int)

- ea: `0x140018f54`
- end: `0x1400193bb`
- name: `?GetMidiClient@CMidiClientManager@@AEAAJPEBG0U_GUID@@KPEAUMIDISRV_CLIENTCREATION_PARAMS@@PEAUMIDISRV_CLIENT@@AEAV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@AEAV?$com_ptr_t@VCMidiPipe@@Uerr_returncode_policy@wil@@@6@H@Z`
- size: `1127`
- prototype: `__int64 __fastcall(unsigned int *, const wchar_t *, __int64, struct _GUID *, unsigned int, struct MIDISRV_CLIENTCREATION_PARAMS *, struct MIDISRV_CLIENT *, void **, CMidiClientPipe **, int)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1400152d0`

## callees

- `0x14000179c`
- `0x140001e00`
- `0x1400054c0`
- `0x1400058ac`
- `0x1400072d4`
- `0x140007c20`
- `0x14000984c`
- `0x14000a6b4`
- `0x140012cd0`
- `0x140013a38`
- `0x140013b08`
- `0x1400182d4`
- `0x140018f54`
- `0x14001dccc`
- `0x14001fe88`
- `0x14005a010`

## string_xrefs

- `0x1400190db`: `avcore\midi2\service\exe\midiclientmanager.cpp`
- `0x140019179`: `avcore\midi2\service\exe\midiclientmanager.cpp`
- `0x14001927f`: `avcore\midi2\service\exe\midiclientmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CMidiClientManager::GetMidiClient(
        unsigned int *a1,
        const wchar_t *a2,
        __int64 a3,
        struct _GUID *a4,
        unsigned int a5,
        struct MIDISRV_CLIENTCREATION_PARAMS *a6,
        struct MIDISRV_CLIENT *a7,
        void **a8,
        CMidiClientPipe **a9,
        int a10)
{
  _DWORD *v14; // r10
  __int64 v15; // rbx
  const wchar_t *v16; // rcx
  __int64 v17; // rax
  int v18; // eax
  __int64 v19; // r8
  int EndpointGroupIndex; // eax
  unsigned int v21; // edi
  __int64 v23; // rax
  CMidiPipe *v24; // rax
  CMidiClientPipe *v25; // rbx
  unsigned __int16 **v26; // r8
  struct MIDISRV_CLIENT *v27; // rsi
  int v28; // eax
  CMidiClientPipe *v29; // rdi
  _DWORD *v30; // rcx
  int v31; // r8d
  int v32; // r9d
  unsigned __int16 **v33; // rax
  int v34; // [rsp+20h] [rbp-E0h]
  int v35; // [rsp+20h] [rbp-E0h]
  CMidiClientPipe *v36; // [rsp+58h] [rbp-A8h] BYREF
  CMidiPipe *v37; // [rsp+60h] [rbp-A0h] BYREF
  const char *v38; // [rsp+68h] [rbp-98h] BYREF
  struct MIDISRV_CLIENT *v39; // [rsp+70h] [rbp-90h] BYREF
  struct MIDISRV_CLIENTCREATION_PARAMS *v40; // [rsp+78h] [rbp-88h] BYREF
  void **v41; // [rsp+80h] [rbp-80h] BYREF
  char v42[40]; // [rsp+88h] [rbp-78h] BYREF
  struct _GUID v43; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v44; // [rsp+C0h] [rbp-40h]
  unsigned __int16 *v45[3]; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int64 v46; // [rsp+E8h] [rbp-18h]
  const char *v47; // [rsp+110h] [rbp+10h]
  __int64 v48; // [rsp+118h] [rbp+18h]
  CMidiPipe **v49; // [rsp+120h] [rbp+20h]
  __int64 v50; // [rsp+128h] [rbp+28h]
  const wchar_t *v51; // [rsp+130h] [rbp+30h]
  __int64 v52; // [rsp+138h] [rbp+38h]
  const wchar_t *v53; // [rsp+140h] [rbp+40h]
  int v54; // [rsp+148h] [rbp+48h]
  int v55; // [rsp+14Ch] [rbp+4Ch]
  struct _GUID *v56; // [rsp+150h] [rbp+50h]
  __int64 v57; // [rsp+158h] [rbp+58h]
  CMidiClientPipe **v58; // [rsp+160h] [rbp+60h]
  __int64 v59; // [rsp+168h] [rbp+68h]
  wil::details::in1diag3 *retaddr; // [rsp+1C8h] [rbp+C8h]

  v40 = a6;
  v39 = a7;
  v41 = a8;
  v14 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
  v15 = -1;
  if ( *v14 > 4u )
  {
    LODWORD(v36) = a5;
    v37 = (CMidiPipe *)a1;
    v58 = &v36;
    v59 = 4;
    v56 = a4;
    v57 = 16;
    if ( a2 )
    {
      v16 = a2;
      v17 = -1;
      do
        ++v17;
      while ( a2[v17] );
      v18 = 2 * v17 + 2;
    }
    else
    {
      v16 = &S2;
      v18 = 2;
    }
    v53 = v16;
    v54 = v18;
    v55 = 0;
    v51 = L"Enter";
    v52 = 12;
    v49 = &v37;
    v50 = 8;
    v47 = "CMidiClientManager::GetMidiClient";
    v48 = 34;
    v34 = 8;
    tlgWriteTransfer_EventWriteTransfer(v14, &unk_140087AF0, 0, 0);
  }
  v36 = 0;
  v43 = 0;
  v44 = 0u;
  v19 = -1;
  do
    ++v19;
  while ( *(_WORD *)(a3 + 2 * v19) );
  std::wstring::_Construct<1,unsigned short const *>(&v43, a3, v19);
  EndpointGroupIndex = GetEndpointGroupIndex(&v43);
  v21 = EndpointGroupIndex;
  if ( EndpointGroupIndex < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x196,
      (unsigned int)"avcore\\midi2\\service\\exe\\midiclientmanager.cpp",
      (const char *)(unsigned int)EndpointGroupIndex,
      v34);
    return v21;
  }
  v43 = 0;
  v44 = 0;
  do
    ++v15;
  while ( a2[v15] );
  std::wstring::_Construct<1,unsigned short const *>(&v43, a2, v15);
  v23 = std::wstring::wstring(v42, &v43);
  WindowsMidiServicesInternal::ToLowerTrimmedWStringCopy(v45, v23);
  std::wstring::~wstring(&v43);
  v36 = 0;
  v24 = (CMidiPipe *)operator new(0xB8u, (const struct std::nothrow_t *)&std::nothrow);
  v25 = v24;
  v37 = v24;
  v38 = (const char *)v24;
  if ( v24 )
  {
    *(_QWORD *)&v43.Data1 = v24;
    CMidiPipe::CMidiPipe(v24);
    *(_QWORD *)v25 = &CMidiClientPipe::`vftable';
    *((_QWORD *)v25 + 15) = 0;
    *((_QWORD *)v25 + 16) = 0;
    *((_QWORD *)v25 + 17) = 0;
    *((_OWORD *)v25 + 9) = 0;
    *((_QWORD *)v25 + 20) = 0;
    *((_BYTE *)v25 + 168) = 0;
    *(_QWORD *)((char *)v25 + 172) = 0;
    v37 = 0;
    (*(void (__fastcall **)(CMidiClientPipe *))(*(_QWORD *)v25 + 8LL))(v25);
    v36 = v25;
    (*(void (__fastcall **)(CMidiClientPipe *))(*(_QWORD *)v25 + 16LL))(v25);
    v26 = v45;
    if ( v46 > 7 )
      v26 = (unsigned __int16 **)v45[0];
    v43 = *a4;
    v27 = v39;
    v28 = CMidiClientPipe::Initialize(
            v25,
            *v41,
            (MEMORY_MAPPED_PIPE *)v26,
            0,
            &v43,
            a5,
            v40,
            (HANDLE *)v39,
            a1 + 30,
            a10);
    v21 = v28;
    if ( v28 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x19E,
        (unsigned int)"avcore\\midi2\\service\\exe\\midiclientmanager.cpp",
        (const char *)(unsigned int)v28,
        v35);
      std::wstring::~wstring(v45);
      (*(void (__fastcall **)(CMidiClientPipe *))(*(_QWORD *)v25 + 16LL))(v25);
      return v21;
    }
    *((_QWORD *)v27 + 9) = v25;
    v29 = *a9;
    *a9 = v25;
    (*(void (__fastcall **)(CMidiClientPipe *))(*(_QWORD *)v25 + 8LL))(v25);
    if ( v29 )
      (*(void (__fastcall **)(CMidiClientPipe *))(*(_QWORD *)v29 + 16LL))(v29);
    std::_Tree<std::_Tmap_traits<unsigned __int64,wil::com_ptr_t<CMidiPipe,wil::err_returncode_policy>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,wil::com_ptr_t<CMidiPipe,wil::err_returncode_policy>>>,0>>::emplace<unsigned __int64 &,wil::com_ptr_t<CMidiClientPipe,wil::err_returncode_policy>>(
      a1 + 18,
      &v43,
      (char *)v27 + 72,
      &v36);
    v30 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
    if ( *v30 > 4u )
    {
      v41 = (void **)a4;
      v33 = v45;
      if ( v46 > 7 )
        v33 = (unsigned __int16 **)v45[0];
      v40 = (struct MIDISRV_CLIENTCREATION_PARAMS *)v33;
      v39 = (struct MIDISRV_CLIENT *)L"Exit success";
      v37 = (CMidiPipe *)a1;
      v38 = "CMidiClientManager::GetMidiClient";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByRef<16>>(
        (_DWORD)v30,
        (unsigned int)&byte_1400881EF,
        v31,
        v32,
        (__int64)&v38,
        (__int64)&v37,
        (__int64)&v39,
        (__int64)&v40,
        (__int64)&v41);
    }
    std::wstring::~wstring(v45);
    if ( v36 )
      (*(void (__fastcall **)(CMidiClientPipe *))(*(_QWORD *)v36 + 16LL))(v36);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x19B,
      (unsigned int)"avcore\\midi2\\service\\exe\\midiclientmanager.cpp",
      (const char *)0x8007000ELL,
      v34);
    std::wstring::~wstring(v45);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x140018f54  push    rbp
0x140018f56  push    rbx
0x140018f57  push    rsi
0x140018f58  push    rdi
0x140018f59  push    r12
0x140018f5b  push    r13
0x140018f5d  push    r14
0x140018f5f  push    r15
0x140018f61  lea     rbp, [rsp-88h]
0x140018f69  sub     rsp, 188h
0x140018f70  mov     rax, cs:__security_cookie
0x140018f77  xor     rax, rsp
0x140018f7a  mov     [rbp+0C0h+var_50], rax
0x140018f7e  mov     r15, r9
0x140018f81  mov     rdi, r8
0x140018f84  mov     rsi, rdx
0x140018f87  mov     r14, rcx
0x140018f8a  mov     r12, [rbp+0C0h+arg_40]
0x140018f91  mov     rax, [rbp+0C0h+arg_28]
0x140018f98  mov     [rsp+1C0h+var_148], rax
0x140018f9d  mov     rax, [rbp+0C0h+arg_30]
0x140018fa4  mov     [rsp+1C0h+var_150], rax
0x140018fa9  mov     rax, [rbp+0C0h+arg_38]
0x140018fb0  mov     [rbp+0C0h+var_140], rax
0x140018fb4  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x140018fb9  mov     r10, [rax+8]
0x140018fbd  mov     eax, [r10]
0x140018fc0  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140018fc4  lea     r8, aCmidiclientman_5; "CMidiClientManager::GetMidiClient"
0x140018fcb  mov     r13d, [rbp+0C0h+arg_20]
0x140018fd2  cmp     eax, 4
0x140018fd5  jbe     loc_14001908A
0x140018fdb  mov     dword ptr [rsp+1C0h+var_168], r13d
0x140018fe0  mov     [rsp+1C0h+var_160], r14
0x140018fe5  lea     rax, [rsp+1C0h+var_168]
0x140018fea  mov     [rbp+0C0h+var_60], rax
0x140018fee  mov     [rbp+0C0h+var_58], 4
0x140018ff6  xor     edx, edx
0x140018ff8  mov     [rbp+0C0h+var_70], r15
0x140018ffc  mov     [rbp+0C0h+var_68], 10h
0x140019004  test    rsi, rsi
0x140019007  jz      short loc_140019021
0x140019009  mov     rcx, rsi
0x14001900c  mov     rax, rbx
0x14001900f  inc     rax
0x140019012  cmp     [rsi+rax*2], dx
0x140019016  jnz     short loc_14001900F
0x140019018  lea     eax, ds:2[rax*2]
0x14001901f  jmp     short loc_14001902D
0x140019021  lea     rcx, S2
0x140019028  mov     eax, 2
0x14001902d  mov     [rbp+0C0h+var_80], rcx
0x140019031  mov     [rbp+0C0h+var_78], eax
0x140019034  mov     [rbp+0C0h+var_74], edx
0x140019037  lea     rax, aEnter; "Enter"
0x14001903e  mov     [rbp+0C0h+var_90], rax
0x140019042  mov     [rbp+0C0h+var_88], 0Ch
0x14001904a  lea     rax, [rsp+1C0h+var_160]
0x14001904f  mov     [rbp+0C0h+var_A0], rax
0x140019053  mov     ecx, 8
0x140019058  mov     [rbp+0C0h+var_98], rcx
0x14001905c  mov     [rbp+0C0h+var_B0], r8
0x140019060  mov     [rbp+0C0h+var_A8], 22h ; '"'
0x140019068  lea     rax, [rbp+0C0h+var_D0]
0x14001906c  mov     qword ptr [rsp+1C0h+var_198], rax
0x140019071  mov     dword ptr [rsp+1C0h+var_1A0], ecx; int
0x140019075  xor     r9d, r9d
0x140019078  xor     r8d, r8d
0x14001907b  lea     rdx, unk_140087AF0
0x140019082  mov     rcx, r10
0x140019085  call    _tlgWriteTransfer_EventWriteTransfer
0x14001908a  xor     ecx, ecx
0x14001908c  mov     [rsp+1C0h+var_168], rcx
0x140019091  mov     [rsp+1C0h+var_170], cl
0x140019095  xorps   xmm0, xmm0
0x140019098  movups  xmmword ptr [rbp+0C0h+var_110.Data1], xmm0
0x14001909c  mov     qword ptr [rbp+0C0h+var_100], rcx
0x1400190a0  mov     qword ptr [rbp+0C0h+var_100+8], rcx
0x1400190a4  mov     r8, rbx
0x1400190a7  inc     r8
0x1400190aa  cmp     [rdi+r8*2], cx
0x1400190af  jnz     short loc_1400190A7
0x1400190b1  mov     rdx, rdi
0x1400190b4  lea     rcx, [rbp+0C0h+var_110]
0x1400190b8  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1400190bd  lea     rdx, [rsp+1C0h+var_170]
0x1400190c2  lea     rcx, [rbp+0C0h+var_110]; void *
0x1400190c6  call    ?GetEndpointGroupIndex@@YAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAE@Z; GetEndpointGroupIndex(std::wstring,uchar &)
0x1400190cb  mov     edi, eax
0x1400190cd  test    eax, eax
0x1400190cf  jns     short loc_1400190F4
0x1400190d1  mov     rcx, [rbp+0C8h]; this
0x1400190d8  mov     r9d, eax; char *
0x1400190db  lea     r8, aAvcoreMidi2Ser_1; "avcore\\midi2\\service\\exe\\midiclient"...
0x1400190e2  mov     edx, 196h; void *
0x1400190e7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400190ec  nop
0x1400190ed  mov     eax, edi
0x1400190ef  jmp     loc_14001939B
0x1400190f4  xorps   xmm0, xmm0
0x1400190f7  movups  xmmword ptr [rbp+0C0h+var_110.Data1], xmm0
0x1400190fb  xorps   xmm1, xmm1
0x1400190fe  movdqu  [rbp+0C0h+var_100], xmm1
0x140019103  xor     edi, edi
0x140019105  inc     rbx
0x140019108  cmp     [rsi+rbx*2], di
0x14001910c  jnz     short loc_140019105
0x14001910e  mov     r8, rbx
0x140019111  mov     rdx, rsi
0x140019114  lea     rcx, [rbp+0C0h+var_110]
0x140019118  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14001911d  nop
0x14001911e  lea     rdx, [rbp+0C0h+var_110]
0x140019122  lea     rcx, [rbp+0C0h+var_138]
0x140019126  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14001912b  mov     rdx, rax
0x14001912e  lea     rcx, [rbp+0C0h+var_F0]
0x140019132  call    ?ToLowerTrimmedWStringCopy@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@@Z; WindowsMidiServicesInternal::ToLowerTrimmedWStringCopy(std::wstring)
0x140019137  nop
0x140019138  lea     rcx, [rbp+0C0h+var_110]; void *
0x14001913c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140019141  nop
0x140019142  mov     [rsp+1C0h+var_168], rdi
0x140019147  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14001914e  mov     ecx, 0B8h; unsigned __int64
0x140019153  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140019158  mov     rbx, rax
0x14001915b  mov     [rsp+1C0h+var_160], rax
0x140019160  mov     [rsp+1C0h+var_158], rax
0x140019165  test    rax, rax
0x140019168  jnz     short loc_14001919C
0x14001916a  mov     rcx, [rbp+0C8h]; this
0x140019171  mov     ebx, 8007000Eh
0x140019176  mov     r9d, ebx; char *
0x140019179  lea     r8, aAvcoreMidi2Ser_1; "avcore\\midi2\\service\\exe\\midiclient"...
0x140019180  mov     edx, 19Bh; void *
0x140019185  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001918a  nop
0x14001918b  lea     rcx, [rbp+0C0h+var_F0]; void *
0x14001918f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140019194  nop
0x140019195  mov     eax, ebx
0x140019197  jmp     loc_14001939B
0x14001919c  mov     qword ptr [rbp+0C0h+var_110.Data1], rbx
0x1400191a0  mov     rcx, rbx; this
0x1400191a3  call    ??0CMidiPipe@@QEAA@XZ; CMidiPipe::CMidiPipe(void)
0x1400191a8  lea     rax, ??_7CMidiClientPipe@@6B@; const CMidiClientPipe::`vftable'
0x1400191af  mov     [rbx], rax
0x1400191b2  xor     eax, eax
0x1400191b4  mov     [rbx+78h], rax
0x1400191b8  mov     [rbx+80h], rdi
0x1400191bf  mov     [rbx+88h], rdi
0x1400191c6  xorps   xmm0, xmm0
0x1400191c9  movups  xmmword ptr [rbx+90h], xmm0
0x1400191d0  mov     [rbx+0A0h], rdi
0x1400191d7  mov     [rbx+0A8h], dil
0x1400191de  mov     [rbx+0ACh], rdi
0x1400191e5  mov     [rsp+1C0h+var_160], rdi
0x1400191ea  mov     rax, [rbx]
0x1400191ed  mov     rcx, rbx
0x1400191f0  mov     rax, [rax+8]
0x1400191f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400191f9  nop
0x1400191fa  mov     [rsp+1C0h+var_168], rbx
0x1400191ff  mov     rax, [rbx]
0x140019202  mov     rcx, rbx
0x140019205  mov     rax, [rax+10h]
0x140019209  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001920e  nop
0x14001920f  lea     r8, [rbp+0C0h+var_F0]
0x140019213  cmp     [rbp+0C0h+var_D8], 7
0x140019218  cmova   r8, [rbp+0C0h+var_F0]; unsigned __int16 *
0x14001921d  movups  xmm0, xmmword ptr [r15]
0x140019221  movdqu  xmmword ptr [rbp+0C0h+var_110.Data1], xmm0
0x140019226  lea     rcx, [r14+78h]
0x14001922a  mov     eax, [rbp+0C0h+arg_48]
0x140019230  mov     [rsp+1C0h+var_178], eax; int
0x140019234  mov     [rsp+1C0h+var_180], rcx; unsigned int *
0x140019239  mov     rsi, [rsp+1C0h+var_150]
0x14001923e  mov     [rsp+1C0h+var_188], rsi; struct MIDISRV_CLIENT *
0x140019243  mov     rax, [rsp+1C0h+var_148]
0x140019248  mov     [rsp+1C0h+var_190], rax; struct MIDISRV_CLIENTCREATION_PARAMS *
0x14001924d  mov     [rsp+1C0h+var_198], r13d; unsigned int
0x140019252  lea     rax, [rbp+0C0h+var_110]
0x140019256  mov     [rsp+1C0h+var_1A0], rax; int
0x14001925b  mov     r9b, [rsp+1C0h+var_170]; unsigned __int8
0x140019260  mov     rdx, [rbp+0C0h+var_140]
0x140019264  mov     rdx, [rdx]; void *
0x140019267  mov     rcx, rbx; this
0x14001926a  call    ?Initialize@CMidiClientPipe@@QEAAJPEAXPEBGEU_GUID@@KPEAUMIDISRV_CLIENTCREATION_PARAMS@@PEAUMIDISRV_CLIENT@@PEAKH@Z; CMidiClientPipe::Initialize(void *,ushort const *,uchar,_GUID,ulong,MIDISRV_CLIENTCREATION_PARAMS *,MIDISRV_CLIENT *,ulong *,int)
0x14001926f  mov     edi, eax
0x140019271  test    eax, eax
0x140019273  jns     short loc_1400192B0
0x140019275  mov     rcx, [rbp+0C8h]; this
0x14001927c  mov     r9d, eax; char *
0x14001927f  lea     r8, aAvcoreMidi2Ser_1; "avcore\\midi2\\service\\exe\\midiclient"...
0x140019286  mov     edx, 19Eh; void *
0x14001928b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140019290  nop
0x140019291  lea     rcx, [rbp+0C0h+var_F0]; void *
0x140019295  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14001929a  nop
0x14001929b  mov     rax, [rbx]
0x14001929e  mov     rcx, rbx
0x1400192a1  mov     rax, [rax+10h]
0x1400192a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400192aa  nop
0x1400192ab  jmp     loc_1400190ED
0x1400192b0  mov     [rsi+48h], rbx
0x1400192b4  mov     rdi, [r12]
0x1400192b8  mov     [r12], rbx
0x1400192bc  mov     rax, [rbx]
0x1400192bf  mov     rcx, rbx
0x1400192c2  mov     rax, [rax+8]
0x1400192c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400192cb  test    rdi, rdi
0x1400192ce  jz      short loc_1400192E0
0x1400192d0  mov     rax, [rdi]
0x1400192d3  mov     rcx, rdi
0x1400192d6  mov     rax, [rax+10h]
0x1400192da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400192df  nop
0x1400192e0  lea     rcx, [r14+48h]
0x1400192e4  lea     r9, [rsp+1C0h+var_168]
0x1400192e9  lea     r8, [rsi+48h]
0x1400192ed  lea     rdx, [rbp+0C0h+var_110]
0x1400192f1  call    ??$emplace@AEA_KV?$com_ptr_t@VCMidiClientPipe@@Uerr_returncode_policy@wil@@@wil@@@?$_Tree@V?$_Tmap_traits@_KV?$com_ptr_t@VCMidiPipe@@Uerr_returncode_policy@wil@@@wil@@U?$less@_K@std@@V?$allocator@U?$pair@$$CB_KV?$com_ptr_t@VCMidiPipe@@Uerr_returncode_policy@wil@@@wil@@@std@@@4@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$com_ptr_t@VCMidiPipe@@Uerr_returncode_policy@wil@@@wil@@@std@@@std@@@std@@@std@@_N@1@AEA_K$$QEAV?$com_ptr_t@VCMidiClientPipe@@Uerr_returncode_policy@wil@@@wil@@@Z; std::_Tree<std::_Tmap_traits<unsigned __int64,wil::com_ptr_t<CMidiPipe,wil::err_returncode_policy>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,wil::com_ptr_t<CMidiPipe,wil::err_returncode_policy>>>,0>>::emplace<unsigned __int64 &,wil::com_ptr_t<CMidiClientPipe,wil::err_returncode_policy>>(unsigned __int64 &,wil::com_ptr_t<CMidiClientPipe,wil::err_returncode_policy> &&)
0x1400192f6  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x1400192fb  mov     rcx, [rax+8]
0x1400192ff  mov     eax, [rcx]
0x140019301  cmp     eax, 4
0x140019304  jbe     short loc_140019378
0x140019306  mov     [rbp+0C0h+var_140], r15
0x14001930a  lea     rax, [rbp+0C0h+var_F0]
0x14001930e  cmp     [rbp+0C0h+var_D8], 7
0x140019313  cmova   rax, [rbp+0C0h+var_F0]
0x140019318  mov     [rsp+1C0h+var_148], rax
0x14001931d  lea     rax, aExitSuccess_0; "Exit success"
0x140019324  mov     [rsp+1C0h+var_150], rax
0x140019329  mov     [rsp+1C0h+var_160], r14
0x14001932e  lea     rax, aCmidiclientman_5; "CMidiClientManager::GetMidiClient"
0x140019335  mov     [rsp+1C0h+var_158], rax
0x14001933a  lea     rax, [rbp+0C0h+var_140]
0x14001933e  mov     [rsp+1C0h+var_180], rax
0x140019343  lea     rax, [rsp+1C0h+var_148]
0x140019348  mov     [rsp+1C0h+var_188], rax
0x14001934d  lea     rax, [rsp+1C0h+var_150]
0x140019352  mov     [rsp+1C0h+var_190], rax
0x140019357  lea     rax, [rsp+1C0h+var_160]
0x14001935c  mov     qword ptr [rsp+1C0h+var_198], rax
0x140019361  lea     rax, [rsp+1C0h+var_158]
0x140019366  mov     [rsp+1C0h+var_1A0], rax
0x14001936b  lea     rdx, byte_1400881EF
0x140019372  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByRef<16> const &)
0x140019377  nop
0x140019378  lea     rcx, [rbp+0C0h+var_F0]; void *
0x14001937c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140019381  nop
0x140019382  mov     rcx, [rsp+1C0h+var_168]
0x140019387  test    rcx, rcx
0x14001938a  jz      short loc_140019399
0x14001938c  mov     rax, [rcx]
0x14001938f  mov     rax, [rax+10h]
0x140019393  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140019398  nop
0x140019399  xor     eax, eax
0x14001939b  mov     rcx, [rbp+0C0h+var_50]
0x14001939f  xor     rcx, rsp; StackCookie
0x1400193a2  call    __security_check_cookie
0x1400193a7  add     rsp, 188h
0x1400193ae  pop     r15
0x1400193b0  pop     r14
0x1400193b2  pop     r13
0x1400193b4  pop     r12
0x1400193b6  pop     rdi
0x1400193b7  pop     rsi
0x1400193b8  pop     rbx
0x1400193b9  pop     rbp
0x1400193ba  retn
```
