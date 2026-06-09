# CMidi2DiagnosticsEndpointManager::CreateLoopbackEndpoint(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0002)

- ea: `0x18000ccf8`
- end: `0x18000d0ae`
- name: `?CreateLoopbackEndpoint@CMidi2DiagnosticsEndpointManager@@AEAAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00W4__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0002@@@Z`
- size: `950`
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
- `0x18000ccf8`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d01d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d02f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d01d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d02f`

## string_xrefs

- `0x18000cd4c`: `CMidi2DiagnosticsEndpointManager::CreateLoopbackEndpoint`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall CMidi2DiagnosticsEndpointManager::CreateLoopbackEndpoint(
        __int64 a1,
        _QWORD *a2,
        _QWORD *a3,
        _QWORD *a4)
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
    v23 = "CMidi2DiagnosticsEndpointManager::CreateLoopbackEndpoint";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
      (_DWORD)v8,
      (unsigned int)&word_180016D8E,
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
    L"Diagnostics loopback endpoint. For testing and development purposes.",
    68);
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
  v31 = 500;
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
  v42 = 7;
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
      (void *)0xC5,
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
0x18000ccf8  push    rbp
0x18000ccfa  push    rbx
0x18000ccfb  push    rsi
0x18000ccfc  push    rdi
0x18000ccfd  push    r14
0x18000ccff  lea     rbp, [rsp-130h]
0x18000cd07  sub     rsp, 230h
0x18000cd0e  mov     rax, cs:__security_cookie
0x18000cd15  xor     rax, rsp
0x18000cd18  mov     [rbp+150h+var_28], rax
0x18000cd1f  mov     rbx, r9
0x18000cd22  mov     rdi, r8
0x18000cd25  mov     rsi, rdx
0x18000cd28  mov     r14, rcx
0x18000cd2b  mov     [rbp+150h+var_100], rdx
0x18000cd2f  mov     [rbp+150h+var_F8], r8
0x18000cd33  mov     [rbp+150h+var_F0], rbx
0x18000cd37  call    ?Instance@MidiDiagnosticsTransportTelemetryProvider@@KAPEAV1@XZ; MidiDiagnosticsTransportTelemetryProvider::Instance(void)
0x18000cd3c  mov     rcx, [rax+8]
0x18000cd40  mov     eax, [rcx]
0x18000cd42  cmp     eax, 4
0x18000cd45  jbe     short loc_18000CD78
0x18000cd47  mov     [rsp+250h+var_1E8], r14
0x18000cd4c  lea     rax, aCmidi2diagnost_4; "CMidi2DiagnosticsEndpointManager::Creat"...
0x18000cd53  mov     [rsp+250h+var_1E0], rax
0x18000cd58  lea     rax, [rsp+250h+var_1E8]
0x18000cd5d  mov     [rsp+250h+var_228], rax
0x18000cd62  lea     rax, [rsp+250h+var_1E0]
0x18000cd67  mov     qword ptr [rsp+250h+var_230], rax
0x18000cd6c  lea     rdx, word_180016D8E
0x18000cd73  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x18000cd78  xorps   xmm0, xmm0
0x18000cd7b  movups  [rbp+150h+var_C8], xmm0
0x18000cd82  xorps   xmm1, xmm1
0x18000cd85  movdqu  [rbp+150h+var_B8], xmm1
0x18000cd8d  mov     r8d, 4
0x18000cd93  lea     rdx, aDiag; "DIAG"
0x18000cd9a  lea     rcx, [rbp+150h+var_C8]
0x18000cda1  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000cda6  nop
0x18000cda7  mov     rdx, rbx
0x18000cdaa  lea     rcx, [rbp+150h+var_A8]
0x18000cdb1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000cdb6  nop
0x18000cdb7  xorps   xmm0, xmm0
0x18000cdba  movups  [rbp+150h+var_E8], xmm0
0x18000cdbe  xorps   xmm1, xmm1
0x18000cdc1  movdqu  [rbp+150h+var_D8], xmm1
0x18000cdc6  mov     r8d, 44h ; 'D'
0x18000cdcc  lea     rdx, aDiagnosticsLoo; "Diagnostics loopback endpoint. For test"...
0x18000cdd3  lea     rcx, [rbp+150h+var_E8]
0x18000cdd7  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000cddc  nop
0x18000cddd  xorps   xmm0, xmm0
0x18000cde0  movdqu  [rsp+250h+var_1D8], xmm0
0x18000cde6  mov     [rbp+150h+var_1C8], 0
0x18000cdee  movups  [rbp+150h+var_68], xmm0
0x18000cdf5  xorps   xmm1, xmm1
0x18000cdf8  movdqu  [rbp+150h+var_58], xmm1
0x18000ce00  xor     r8d, r8d
0x18000ce03  lea     rdx, qword_1800159A0
0x18000ce0a  lea     rcx, [rbp+150h+var_68]
0x18000ce11  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000ce16  nop
0x18000ce17  xorps   xmm0, xmm0
0x18000ce1a  movups  [rbp+150h+var_88], xmm0
0x18000ce21  xorps   xmm1, xmm1
0x18000ce24  movdqu  [rbp+150h+var_78], xmm1
0x18000ce2c  xor     r8d, r8d
0x18000ce2f  lea     rdx, qword_1800159A0
0x18000ce36  lea     rcx, [rbp+150h+var_88]
0x18000ce3d  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000ce42  nop
0x18000ce43  lea     r9, [rbp+150h+var_68]
0x18000ce4a  lea     r8, [rbp+150h+var_88]
0x18000ce51  lea     rdx, [rbp+150h+var_A8]
0x18000ce58  lea     rcx, [rbp+150h+Src]; Src
0x18000ce5f  call    ?CalculateEndpointDevicePrimaryName@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@00@Z; WindowsMidiServicesInternal::CalculateEndpointDevicePrimaryName(std::wstring const &,std::wstring const &,std::wstring const &)
0x18000ce64  nop
0x18000ce65  lea     rcx, [rbp+150h+var_88]
0x18000ce6c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000ce71  nop
0x18000ce72  lea     rcx, [rbp+150h+var_68]
0x18000ce79  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000ce7e  xor     edx, edx; Val
0x18000ce80  lea     r8d, [rdx+48h]; Size
0x18000ce84  lea     rcx, [rbp+150h+var_1C0]; void *
0x18000ce88  call    memset_0
0x18000ce8d  mov     [rbp+150h+var_1C0], 48h ; 'H'
0x18000ce94  mov     r8d, 7
0x18000ce9a  cmp     [rsi+18h], r8
0x18000ce9e  jbe     short loc_18000CEA5
0x18000cea0  mov     rax, [rsi]
0x18000cea3  jmp     short loc_18000CEA8
0x18000cea5  mov     rax, rsi
0x18000cea8  mov     [rbp+150h+var_1B8], rax
0x18000ceac  mov     [rbp+150h+var_198], 0
0x18000ceb3  cmp     [rbx+18h], r8
0x18000ceb7  jbe     short loc_18000CEBE
0x18000ceb9  mov     rax, [rbx]
0x18000cebc  jmp     short loc_18000CEC1
0x18000cebe  mov     rax, rbx
0x18000cec1  mov     [rbp+150h+var_190], rax
0x18000cec5  mov     [rsp+250h+pv], 0
0x18000cece  mov     [rbp+150h+var_160], 1F4h
0x18000ced6  xor     eax, eax
0x18000ced8  mov     [rbp+150h+var_10C], eax
0x18000cedb  movups  xmm0, xmmword ptr [r14+20h]
0x18000cee0  movdqu  xmmword ptr [rbp+150h+var_170], xmm0
0x18000cee5  lea     rax, [rbp+150h+Src]
0x18000ceec  cmp     [rbp+150h+var_30], r8
0x18000cef3  cmova   rax, [rbp+150h+Src]
0x18000cefb  mov     [rbp+150h+var_158], rax
0x18000ceff  lea     rax, [rbp+150h+var_C8]
0x18000cf06  cmp     qword ptr [rbp+150h+var_B8+8], r8
0x18000cf0d  cmova   rax, qword ptr [rbp+150h+var_C8]
0x18000cf15  mov     [rbp+150h+var_150], rax
0x18000cf19  lea     rax, [rbp+150h+var_A8]
0x18000cf20  cmp     [rbp+150h+var_90], r8
0x18000cf27  cmova   rax, [rbp+150h+var_A8]
0x18000cf2f  mov     [rbp+150h+var_148], rax
0x18000cf33  lea     rax, [rbp+150h+var_E8]
0x18000cf37  cmp     qword ptr [rbp+150h+var_D8+8], r8
0x18000cf3e  cmova   rax, qword ptr [rbp+150h+var_E8]
0x18000cf43  mov     [rbp+150h+var_140], rax
0x18000cf47  mov     [rbp+150h+var_138], 0
0x18000cf4f  mov     [rbp+150h+var_130], 0
0x18000cf57  cmp     [rdi+18h], r8
0x18000cf5b  jbe     short loc_18000CF62
0x18000cf5d  mov     rax, [rdi]
0x18000cf60  jmp     short loc_18000CF65
0x18000cf62  mov     rax, rdi
0x18000cf65  mov     [rbp+150h+var_128], rax
0x18000cf69  mov     r9d, 2
0x18000cf6f  mov     [rbp+150h+var_118], r9d
0x18000cf73  mov     [rbp+150h+var_114], r9d
0x18000cf77  lea     rax, aMicrosoft; "Microsoft"
0x18000cf7e  mov     [rbp+150h+var_120], rax
0x18000cf82  mov     [rbp+150h+var_110], r8d
0x18000cf86  mov     rcx, [r14+30h]
0x18000cf8a  mov     rax, [rcx]
0x18000cf8d  mov     [rsp+250h+pv], 0
0x18000cf96  lea     rdx, [r14+38h]
0x18000cf9a  cmp     [rdx+18h], r8
0x18000cf9e  jbe     short loc_18000CFA3
0x18000cfa0  mov     rdx, [rdx]
0x18000cfa3  lea     r8, [rsp+250h+pv]
0x18000cfa8  mov     [rsp+250h+var_200], r8
0x18000cfad  lea     r8, [rbp+150h+var_1C0]
0x18000cfb1  mov     [rsp+250h+var_208], r8
0x18000cfb6  mov     [rsp+250h+var_210], 0
0x18000cfbf  mov     [rsp+250h+var_218], 0
0x18000cfc8  mov     [rsp+250h+var_220], 0
0x18000cfd0  mov     dword ptr [rsp+250h+var_228], 0
0x18000cfd8  lea     r8, [rbp+150h+var_170]
0x18000cfdc  mov     qword ptr [rsp+250h+var_230], r8; int
0x18000cfe1  mov     r8d, 1
0x18000cfe7  mov     rax, [rax+28h]
0x18000cfeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cff0  mov     r14d, eax
0x18000cff3  test    eax, eax
0x18000cff5  jns     short loc_18000D025
0x18000cff7  mov     rcx, [rbp+158h]; this
0x18000cffe  mov     r9d, eax; char *
0x18000d001  lea     r8, aAvcoreMidi2Tra_3; "avcore\\midi2\\transport\\diagnosticstr"...
0x18000d008  mov     edx, 0C5h; void *
0x18000d00d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d012  nop
0x18000d013  mov     rcx, [rsp+250h+pv]; pv
0x18000d018  test    rcx, rcx
0x18000d01b  jz      short loc_18000D038
0x18000d01d  call    cs:__imp_CoTaskMemFree
0x18000d023  jmp     short loc_18000D038
0x18000d025  mov     rcx, [rsp+250h+pv]; pv
0x18000d02a  test    rcx, rcx
0x18000d02d  jz      short loc_18000D035
0x18000d02f  call    cs:__imp_CoTaskMemFree
0x18000d035  xor     r14d, r14d
0x18000d038  lea     rcx, [rbp+150h+Src]
0x18000d03f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000d044  nop
0x18000d045  lea     rcx, [rsp+250h+var_1D8]
0x18000d04a  call    ??1?$vector@U_DEVPROPERTY@@V?$allocator@U_DEVPROPERTY@@@std@@@std@@QEAA@XZ; std::vector<_DEVPROPERTY>::~vector<_DEVPROPERTY>(void)
0x18000d04f  nop
0x18000d050  lea     rcx, [rbp+150h+var_E8]
0x18000d054  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000d059  nop
0x18000d05a  lea     rcx, [rbp+150h+var_A8]
0x18000d061  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000d066  nop
0x18000d067  lea     rcx, [rbp+150h+var_C8]
0x18000d06e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000d073  nop
0x18000d074  mov     rcx, rsi
0x18000d077  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000d07c  nop
0x18000d07d  mov     rcx, rdi
0x18000d080  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000d085  nop
0x18000d086  mov     rcx, rbx
0x18000d089  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000d08e  mov     eax, r14d
0x18000d091  mov     rcx, [rbp+150h+var_28]
0x18000d098  xor     rcx, rsp; StackCookie
0x18000d09b  call    __security_check_cookie
0x18000d0a0  add     rsp, 230h
0x18000d0a7  pop     r14
0x18000d0a9  pop     rdi
0x18000d0aa  pop     rsi
0x18000d0ab  pop     rbx
0x18000d0ac  pop     rbp
0x18000d0ad  retn
```
