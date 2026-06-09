# CMidi2DiagnosticsEndpointManager::CreatePingEndpoint(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0002)

- ea: `0x18000d31c`
- end: `0x18000d6d7`
- name: `?CreatePingEndpoint@CMidi2DiagnosticsEndpointManager@@AEAAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00W4__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0002@@@Z`
- size: `955`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000f4f0`

## callees

- `0x1800016dc`
- `0x1800033d0`
- `0x180004170`
- `0x180008f64`
- `0x18000add8`
- `0x18000b7fc`
- `0x18000c4c0`
- `0x18000c758`
- `0x18000c944`
- `0x18000cb4c`
- `0x18000d31c`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d646`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d658`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d646`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d658`

## string_xrefs

- `0x18000d370`: `CMidi2DiagnosticsEndpointManager::CreatePingEndpoint`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall CMidi2DiagnosticsEndpointManager::CreatePingEndpoint(__int64 a1, _QWORD *a2, _QWORD *a3, _QWORD *a4)
{
  _DWORD *v8; // rcx
  int v9; // r8d
  int v10; // r9d
  _QWORD *v11; // rax
  _QWORD *v12; // rax
  _QWORD *v13; // rax
  __int128 *v14; // rax
  _QWORD *v15; // rax
  __int128 *v16; // rax
  _QWORD *v17; // rax
  _QWORD *v18; // rdx
  int v19; // eax
  unsigned int v20; // r14d
  __int64 v22; // [rsp+68h] [rbp-98h] BYREF
  const char *v23; // [rsp+70h] [rbp-90h] BYREF
  __int128 v24; // [rsp+78h] [rbp-88h] BYREF
  __int64 v25; // [rsp+88h] [rbp-78h]
  int v26; // [rsp+90h] [rbp-70h] BYREF
  _QWORD *v27; // [rsp+98h] [rbp-68h]
  int v28; // [rsp+B8h] [rbp-48h]
  _QWORD *v29; // [rsp+C0h] [rbp-40h]
  int v30[4]; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v31; // [rsp+F0h] [rbp-10h]
  _QWORD *v32; // [rsp+F8h] [rbp-8h]
  __int128 *v33; // [rsp+100h] [rbp+0h]
  _QWORD *v34; // [rsp+108h] [rbp+8h]
  __int128 *v35; // [rsp+110h] [rbp+10h]
  __int64 v36; // [rsp+118h] [rbp+18h]
  __int64 v37; // [rsp+120h] [rbp+20h]
  _QWORD *v38; // [rsp+128h] [rbp+28h]
  const wchar_t *v39; // [rsp+130h] [rbp+30h]
  int v40; // [rsp+138h] [rbp+38h]
  int v41; // [rsp+13Ch] [rbp+3Ch]
  int v42; // [rsp+140h] [rbp+40h]
  int v43; // [rsp+144h] [rbp+44h]
  _QWORD *v44; // [rsp+150h] [rbp+50h]
  _QWORD *v45; // [rsp+158h] [rbp+58h]
  _QWORD *v46; // [rsp+160h] [rbp+60h]
  __int128 v47; // [rsp+168h] [rbp+68h] BYREF
  __int128 v48; // [rsp+178h] [rbp+78h]
  __int128 v49; // [rsp+188h] [rbp+88h] BYREF
  __int128 v50; // [rsp+198h] [rbp+98h]
  _QWORD v51[4]; // [rsp+1A8h] [rbp+A8h] BYREF
  _OWORD v52[2]; // [rsp+1C8h] [rbp+C8h] BYREF
  _OWORD v53[2]; // [rsp+1E8h] [rbp+E8h] BYREF
  _QWORD Src[4]; // [rsp+208h] [rbp+108h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+258h] [rbp+158h]

  v44 = a2;
  v45 = a3;
  v46 = a4;
  v8 = (_DWORD *)*((_QWORD *)MidiDiagnosticsTransportTelemetryProvider::Instance() + 1);
  if ( *v8 > 4u )
  {
    v22 = a1;
    v23 = "CMidi2DiagnosticsEndpointManager::CreatePingEndpoint";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
      (_DWORD)v8,
      (unsigned int)byte_180016D65,
      v9,
      v10,
      (__int64)&v23,
      (__int64)&v22);
  }
  v49 = 0;
  v50 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v49, L"DIAG", 4);
  std::wstring::wstring(v51, a4);
  v47 = 0;
  v48 = 0;
  std::wstring::_Construct<1,unsigned short const *>(
    &v47,
    L"Internal UMP Ping endpoint. Do not send messages to this endpoint.",
    66);
  v24 = 0;
  v25 = 0;
  memset(v53, 0, sizeof(v53));
  std::wstring::_Construct<1,unsigned short const *>(v53, qword_1800159A0, 0);
  memset(v52, 0, sizeof(v52));
  std::wstring::_Construct<1,unsigned short const *>(v52, qword_1800159A0, 0);
  WindowsMidiServicesInternal::CalculateEndpointDevicePrimaryName(Src);
  std::wstring::~wstring(v52);
  std::wstring::~wstring(v53);
  memset_0(&v26, 0, 0x48u);
  v26 = 72;
  if ( a2[3] <= 7u )
    v11 = a2;
  else
    v11 = (_QWORD *)*a2;
  v27 = v11;
  v28 = 0;
  if ( a4[3] <= 7u )
    v12 = a4;
  else
    v12 = (_QWORD *)*a4;
  v29 = v12;
  v31 = 510;
  v43 = 0;
  *(_OWORD *)v30 = *(_OWORD *)(a1 + 32);
  v13 = Src;
  if ( Src[3] > 7u )
    v13 = (_QWORD *)Src[0];
  v32 = v13;
  v14 = &v49;
  if ( *((_QWORD *)&v50 + 1) > 7u )
    v14 = (__int128 *)v49;
  v33 = v14;
  v15 = v51;
  if ( v51[3] > 7u )
    v15 = (_QWORD *)v51[0];
  v34 = v15;
  v16 = &v47;
  if ( *((_QWORD *)&v48 + 1) > 7u )
    v16 = (__int128 *)v47;
  v35 = v16;
  v36 = 0;
  v37 = 0;
  if ( a3[3] <= 7u )
    v17 = a3;
  else
    v17 = (_QWORD *)*a3;
  v38 = v17;
  v40 = 2;
  v41 = 2;
  v39 = L"Microsoft";
  v42 = 12;
  v18 = (_QWORD *)(a1 + 56);
  if ( *(_QWORD *)(a1 + 80) > 7u )
    v18 = (_QWORD *)*v18;
  v19 = (*(__int64 (__fastcall **)(_QWORD, _QWORD *, __int64))(**(_QWORD **)(a1 + 48) + 40LL))(
          *(_QWORD *)(a1 + 48),
          v18,
          1);
  v20 = v19;
  if ( v19 >= 0 )
    v20 = 0;
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x121,
      (unsigned int)"avcore\\midi2\\transport\\diagnosticstransport\\midi2.diagnosticsendpointmanager.cpp",
      (const char *)(unsigned int)v19,
      (int)v30);
  std::wstring::~wstring(Src);
  std::vector<_DEVPROPERTY>::~vector<_DEVPROPERTY>(&v24);
  std::wstring::~wstring(&v47);
  std::wstring::~wstring(v51);
  std::wstring::~wstring(&v49);
  std::wstring::~wstring(a2);
  std::wstring::~wstring(a3);
  std::wstring::~wstring(a4);
  return v20;
}

```

## disassembly

```asm
0x18000d31c  push    rbp
0x18000d31e  push    rbx
0x18000d31f  push    rsi
0x18000d320  push    rdi
0x18000d321  push    r14
0x18000d323  lea     rbp, [rsp-130h]
0x18000d32b  sub     rsp, 230h
0x18000d332  mov     rax, cs:__security_cookie
0x18000d339  xor     rax, rsp
0x18000d33c  mov     [rbp+150h+var_28], rax
0x18000d343  mov     rbx, r9
0x18000d346  mov     rdi, r8
0x18000d349  mov     rsi, rdx
0x18000d34c  mov     r14, rcx
0x18000d34f  mov     [rbp+150h+var_100], rdx
0x18000d353  mov     [rbp+150h+var_F8], r8
0x18000d357  mov     [rbp+150h+var_F0], rbx
0x18000d35b  call    ?Instance@MidiDiagnosticsTransportTelemetryProvider@@KAPEAV1@XZ; MidiDiagnosticsTransportTelemetryProvider::Instance(void)
0x18000d360  mov     rcx, [rax+8]
0x18000d364  mov     eax, [rcx]
0x18000d366  cmp     eax, 4
0x18000d369  jbe     short loc_18000D39C
0x18000d36b  mov     [rsp+250h+var_1E8], r14
0x18000d370  lea     rax, aCmidi2diagnost_5; "CMidi2DiagnosticsEndpointManager::Creat"...
0x18000d377  mov     [rsp+250h+var_1E0], rax
0x18000d37c  lea     rax, [rsp+250h+var_1E8]
0x18000d381  mov     [rsp+250h+var_228], rax
0x18000d386  lea     rax, [rsp+250h+var_1E0]
0x18000d38b  mov     qword ptr [rsp+250h+var_230], rax
0x18000d390  lea     rdx, byte_180016D65
0x18000d397  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x18000d39c  xorps   xmm0, xmm0
0x18000d39f  movups  [rbp+150h+var_C8], xmm0
0x18000d3a6  xorps   xmm1, xmm1
0x18000d3a9  movdqu  [rbp+150h+var_B8], xmm1
0x18000d3b1  mov     r8d, 4
0x18000d3b7  lea     rdx, aDiag; "DIAG"
0x18000d3be  lea     rcx, [rbp+150h+var_C8]
0x18000d3c5  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000d3ca  nop
0x18000d3cb  mov     rdx, rbx
0x18000d3ce  lea     rcx, [rbp+150h+var_A8]
0x18000d3d5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000d3da  nop
0x18000d3db  xorps   xmm0, xmm0
0x18000d3de  movups  [rbp+150h+var_E8], xmm0
0x18000d3e2  xorps   xmm1, xmm1
0x18000d3e5  movdqu  [rbp+150h+var_D8], xmm1
0x18000d3ea  mov     r8d, 42h ; 'B'
0x18000d3f0  lea     rdx, aInternalUmpPin; "Internal UMP Ping endpoint. Do not send"...
0x18000d3f7  lea     rcx, [rbp+150h+var_E8]
0x18000d3fb  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000d400  nop
0x18000d401  xorps   xmm0, xmm0
0x18000d404  movdqu  [rsp+250h+var_1D8], xmm0
0x18000d40a  mov     [rbp+150h+var_1C8], 0
0x18000d412  movups  [rbp+150h+var_68], xmm0
0x18000d419  xorps   xmm1, xmm1
0x18000d41c  movdqu  [rbp+150h+var_58], xmm1
0x18000d424  xor     r8d, r8d
0x18000d427  lea     rdx, qword_1800159A0
0x18000d42e  lea     rcx, [rbp+150h+var_68]
0x18000d435  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000d43a  nop
0x18000d43b  xorps   xmm0, xmm0
0x18000d43e  movups  [rbp+150h+var_88], xmm0
0x18000d445  xorps   xmm1, xmm1
0x18000d448  movdqu  [rbp+150h+var_78], xmm1
0x18000d450  xor     r8d, r8d
0x18000d453  lea     rdx, qword_1800159A0
0x18000d45a  lea     rcx, [rbp+150h+var_88]
0x18000d461  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000d466  nop
0x18000d467  lea     r9, [rbp+150h+var_68]
0x18000d46e  lea     r8, [rbp+150h+var_88]
0x18000d475  lea     rdx, [rbp+150h+var_A8]
0x18000d47c  lea     rcx, [rbp+150h+Src]; Src
0x18000d483  call    ?CalculateEndpointDevicePrimaryName@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@00@Z; WindowsMidiServicesInternal::CalculateEndpointDevicePrimaryName(std::wstring const &,std::wstring const &,std::wstring const &)
0x18000d488  nop
0x18000d489  lea     rcx, [rbp+150h+var_88]
0x18000d490  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000d495  nop
0x18000d496  lea     rcx, [rbp+150h+var_68]
0x18000d49d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000d4a2  xor     edx, edx; Val
0x18000d4a4  lea     r8d, [rdx+48h]; Size
0x18000d4a8  lea     rcx, [rbp+150h+var_1C0]; void *
0x18000d4ac  call    memset_0
0x18000d4b1  mov     [rbp+150h+var_1C0], 48h ; 'H'
0x18000d4b8  cmp     qword ptr [rsi+18h], 7
0x18000d4bd  jbe     short loc_18000D4C4
0x18000d4bf  mov     rax, [rsi]
0x18000d4c2  jmp     short loc_18000D4C7
0x18000d4c4  mov     rax, rsi
0x18000d4c7  mov     [rbp+150h+var_1B8], rax
0x18000d4cb  mov     [rbp+150h+var_198], 0
0x18000d4d2  cmp     qword ptr [rbx+18h], 7
0x18000d4d7  jbe     short loc_18000D4DE
0x18000d4d9  mov     rax, [rbx]
0x18000d4dc  jmp     short loc_18000D4E1
0x18000d4de  mov     rax, rbx
0x18000d4e1  mov     [rbp+150h+var_190], rax
0x18000d4e5  mov     [rsp+250h+pv], 0
0x18000d4ee  mov     [rbp+150h+var_160], 1FEh
0x18000d4f6  xor     eax, eax
0x18000d4f8  mov     [rbp+150h+var_10C], eax
0x18000d4fb  movups  xmm0, xmmword ptr [r14+20h]
0x18000d500  movdqu  xmmword ptr [rbp+150h+var_170], xmm0
0x18000d505  lea     rax, [rbp+150h+Src]
0x18000d50c  cmp     [rbp+150h+var_30], 7
0x18000d514  cmova   rax, [rbp+150h+Src]
0x18000d51c  mov     [rbp+150h+var_158], rax
0x18000d520  lea     rax, [rbp+150h+var_C8]
0x18000d527  cmp     qword ptr [rbp+150h+var_B8+8], 7
0x18000d52f  cmova   rax, qword ptr [rbp+150h+var_C8]
0x18000d537  mov     [rbp+150h+var_150], rax
0x18000d53b  lea     rax, [rbp+150h+var_A8]
0x18000d542  cmp     [rbp+150h+var_90], 7
0x18000d54a  cmova   rax, [rbp+150h+var_A8]
0x18000d552  mov     [rbp+150h+var_148], rax
0x18000d556  lea     rax, [rbp+150h+var_E8]
0x18000d55a  cmp     qword ptr [rbp+150h+var_D8+8], 7
0x18000d562  cmova   rax, qword ptr [rbp+150h+var_E8]
0x18000d567  mov     [rbp+150h+var_140], rax
0x18000d56b  mov     [rbp+150h+var_138], 0
0x18000d573  mov     [rbp+150h+var_130], 0
0x18000d57b  cmp     qword ptr [rdi+18h], 7
0x18000d580  jbe     short loc_18000D587
0x18000d582  mov     rax, [rdi]
0x18000d585  jmp     short loc_18000D58A
0x18000d587  mov     rax, rdi
0x18000d58a  mov     [rbp+150h+var_128], rax
0x18000d58e  mov     r9d, 2
0x18000d594  mov     [rbp+150h+var_118], r9d
0x18000d598  mov     [rbp+150h+var_114], r9d
0x18000d59c  lea     rax, aMicrosoft; "Microsoft"
0x18000d5a3  mov     [rbp+150h+var_120], rax
0x18000d5a7  mov     [rbp+150h+var_110], 0Ch
0x18000d5ae  mov     rcx, [r14+30h]
0x18000d5b2  mov     rax, [rcx]
0x18000d5b5  mov     [rsp+250h+pv], 0
0x18000d5be  lea     rdx, [r14+38h]
0x18000d5c2  cmp     qword ptr [rdx+18h], 7
0x18000d5c7  jbe     short loc_18000D5CC
0x18000d5c9  mov     rdx, [rdx]
0x18000d5cc  lea     r8, [rsp+250h+pv]
0x18000d5d1  mov     [rsp+250h+var_200], r8
0x18000d5d6  lea     r8, [rbp+150h+var_1C0]
0x18000d5da  mov     [rsp+250h+var_208], r8
0x18000d5df  mov     [rsp+250h+var_210], 0
0x18000d5e8  mov     [rsp+250h+var_218], 0
0x18000d5f1  mov     [rsp+250h+var_220], 0
0x18000d5f9  mov     dword ptr [rsp+250h+var_228], 0
0x18000d601  lea     r8, [rbp+150h+var_170]
0x18000d605  mov     qword ptr [rsp+250h+var_230], r8; int
0x18000d60a  mov     r8d, 1
0x18000d610  mov     rax, [rax+28h]
0x18000d614  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d619  mov     r14d, eax
0x18000d61c  test    eax, eax
0x18000d61e  jns     short loc_18000D64E
0x18000d620  mov     rcx, [rbp+158h]; this
0x18000d627  mov     r9d, eax; char *
0x18000d62a  lea     r8, aAvcoreMidi2Tra_3; "avcore\\midi2\\transport\\diagnosticstr"...
0x18000d631  mov     edx, 121h; void *
0x18000d636  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d63b  nop
0x18000d63c  mov     rcx, [rsp+250h+pv]; pv
0x18000d641  test    rcx, rcx
0x18000d644  jz      short loc_18000D661
0x18000d646  call    cs:__imp_CoTaskMemFree
0x18000d64c  jmp     short loc_18000D661
0x18000d64e  mov     rcx, [rsp+250h+pv]; pv
0x18000d653  test    rcx, rcx
0x18000d656  jz      short loc_18000D65E
0x18000d658  call    cs:__imp_CoTaskMemFree
0x18000d65e  xor     r14d, r14d
0x18000d661  lea     rcx, [rbp+150h+Src]
0x18000d668  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000d66d  nop
0x18000d66e  lea     rcx, [rsp+250h+var_1D8]
0x18000d673  call    ??1?$vector@U_DEVPROPERTY@@V?$allocator@U_DEVPROPERTY@@@std@@@std@@QEAA@XZ; std::vector<_DEVPROPERTY>::~vector<_DEVPROPERTY>(void)
0x18000d678  nop
0x18000d679  lea     rcx, [rbp+150h+var_E8]
0x18000d67d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000d682  nop
0x18000d683  lea     rcx, [rbp+150h+var_A8]
0x18000d68a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000d68f  nop
0x18000d690  lea     rcx, [rbp+150h+var_C8]
0x18000d697  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000d69c  nop
0x18000d69d  mov     rcx, rsi
0x18000d6a0  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000d6a5  nop
0x18000d6a6  mov     rcx, rdi
0x18000d6a9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000d6ae  nop
0x18000d6af  mov     rcx, rbx
0x18000d6b2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000d6b7  mov     eax, r14d
0x18000d6ba  mov     rcx, [rbp+150h+var_28]
0x18000d6c1  xor     rcx, rsp; StackCookie
0x18000d6c4  call    __security_check_cookie
0x18000d6c9  add     rsp, 230h
0x18000d6d0  pop     r14
0x18000d6d2  pop     rdi
0x18000d6d3  pop     rsi
0x18000d6d4  pop     rbx
0x18000d6d5  pop     rbp
0x18000d6d6  retn
```
