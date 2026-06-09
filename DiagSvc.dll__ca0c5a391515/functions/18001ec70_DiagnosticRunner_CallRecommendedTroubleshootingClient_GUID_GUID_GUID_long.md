# DiagnosticRunner::CallRecommendedTroubleshootingClient(_GUID,_GUID,_GUID,long *)

- ea: `0x18001ec70`
- end: `0x18001ee4b`
- name: `?CallRecommendedTroubleshootingClient@DiagnosticRunner@@MEAAJU_GUID@@00PEAJ@Z`
- size: `475`
- prototype: `__int64 __fastcall(DiagnosticRunner *__hidden this, struct _GUID *, struct _GUID *, struct _GUID *, int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180001720`
- `0x18000374c`
- `0x18000517c`
- `0x18001ec70`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x18001ecd3`
- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x18001ecd3`

## string_xrefs

- `0x18001ed90`: `DiagnosticRunner::CallRecommendedTroubleshootingClient`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall DiagnosticRunner::CallRecommendedTroubleshootingClient(
        DiagnosticRunner *this,
        struct _GUID *a2,
        struct _GUID *a3,
        struct _GUID *a4,
        int *a5)
{
  __int64 v9; // rdx
  __int64 v10; // rcx
  HRESULT ClassObject; // ebx
  __int64 v12; // r8
  LPVOID v13; // rdi
  __int64 (__fastcall *v14)(LPVOID, _QWORD, GUID *, __int64 *); // rbx
  int v15; // ecx
  int v16; // r8d
  int v17; // r9d
  LPVOID ppv; // [rsp+70h] [rbp-51h] BYREF
  __int64 v20; // [rsp+78h] [rbp-49h] BYREF
  int v21; // [rsp+80h] [rbp-41h] BYREF
  HRESULT v22; // [rsp+84h] [rbp-3Dh] BYREF
  struct _GUID *v23; // [rsp+88h] [rbp-39h] BYREF
  struct _GUID *v24; // [rsp+90h] [rbp-31h] BYREF
  struct _GUID *v25; // [rsp+98h] [rbp-29h] BYREF
  char *v26; // [rsp+A0h] [rbp-21h] BYREF
  const char *v27; // [rsp+A8h] [rbp-19h] BYREF
  struct _GUID v28; // [rsp+B0h] [rbp-11h] BYREF
  struct _GUID v29; // [rsp+C0h] [rbp-1h] BYREF
  _OWORD v30[4]; // [rsp+D0h] [rbp+Fh] BYREF

  v20 = 0;
  ppv = 0;
  Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(&ppv);
  ClassObject = CoGetClassObject(&CLSID_MitigationAPIBroker, 4u, 0, &GUID_00000001_0000_0000_c000_000000000046, &ppv);
  if ( ClassObject >= 0 )
  {
    v13 = ppv;
    v14 = *(__int64 (__fastcall **)(LPVOID, _QWORD, GUID *, __int64 *))(*(_QWORD *)ppv + 24LL);
    Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(&v20);
    ClassObject = v14(v13, 0, &GUID_c79a68dd_baba_4cab_bc48_b0af313ea5fe, &v20);
    if ( ClassObject >= 0 )
    {
      v30[0] = *a4;
      v29 = *a3;
      v28 = *a2;
      ClassObject = (*(__int64 (__fastcall **)(__int64, struct _GUID *, struct _GUID *, _OWORD *, int *))(*(_QWORD *)v20 + 48LL))(
                      v20,
                      &v28,
                      &v29,
                      v30,
                      a5);
    }
  }
  if ( (unsigned int)dword_180039000 > 5 && (unsigned __int8)tlgKeywordOn(v10, v9, v12) )
  {
    v23 = a4;
    v24 = a3;
    v25 = a2;
    v26 = (char *)this + 64;
    v21 = 216;
    v27 = "onecoreuap\\base\\diagnosis\\pdi\\diagsvc\\engine\\diagnosticrunner\\lib\\diagnosticrunner.cpp";
    *(_QWORD *)&v28.Data1 = "DiagnosticRunner::CallRecommendedTroubleshootingClient";
    *(_QWORD *)&v29.Data1 = "Call RTP's RunSelfHelpTroubleshooter";
    v22 = ClassObject;
    *(_QWORD *)&v30[0] = (char *)this + 193;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByRef<16>>(
      v15,
      (unsigned int)&unk_180032780,
      v16,
      v17,
      (__int64)v30,
      (__int64)&v22,
      (__int64)&v29,
      (__int64)&v28,
      (__int64)&v27,
      (__int64)&v21,
      (__int64)&v26,
      (__int64)&v25,
      (__int64)&v24,
      (__int64)&v23);
  }
  Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(&ppv);
  Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(&v20);
  return (unsigned int)ClassObject;
}

```

## disassembly

```asm
0x18001ec70  mov     [rsp-8+arg_0], rbx
0x18001ec75  push    rbp
0x18001ec76  push    rsi
0x18001ec77  push    rdi
0x18001ec78  push    r12
0x18001ec7a  push    r13
0x18001ec7c  push    r14
0x18001ec7e  push    r15
0x18001ec80  lea     rbp, [rsp-1Fh]
0x18001ec85  sub     rsp, 0E0h
0x18001ec8c  mov     r15, r9
0x18001ec8f  mov     r14, r8
0x18001ec92  mov     rsi, rdx
0x18001ec95  mov     r13, rcx
0x18001ec98  mov     r12, [rbp+4Fh+arg_20]
0x18001ec9c  mov     [rbp+4Fh+var_98], 0
0x18001eca4  mov     [rbp+4Fh+var_A0], 0
0x18001ecac  lea     rcx, [rbp+4Fh+var_A0]
0x18001ecb0  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x18001ecb5  lea     rax, [rbp+4Fh+var_A0]
0x18001ecb9  mov     [rsp+110h+ppv], rax; ppv
0x18001ecbe  lea     r9, _GUID_00000001_0000_0000_c000_000000000046; riid
0x18001ecc5  xor     r8d, r8d; pvReserved
0x18001ecc8  lea     edx, [r8+4]; dwClsContext
0x18001eccc  lea     rcx, CLSID_MitigationAPIBroker; rclsid
0x18001ecd3  call    cs:__imp_CoGetClassObject
0x18001ecd9  mov     ebx, eax
0x18001ecdb  test    eax, eax
0x18001ecdd  js      short loc_18001ED4E
0x18001ecdf  mov     rdi, [rbp+4Fh+var_A0]
0x18001ece3  mov     rax, [rdi]
0x18001ece6  mov     rbx, [rax+18h]
0x18001ecea  lea     rcx, [rbp+4Fh+var_98]
0x18001ecee  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x18001ecf3  lea     r9, [rbp+4Fh+var_98]
0x18001ecf7  lea     r8, _GUID_c79a68dd_baba_4cab_bc48_b0af313ea5fe
0x18001ecfe  xor     edx, edx
0x18001ed00  mov     rcx, rdi
0x18001ed03  mov     rax, rbx
0x18001ed06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ed0b  mov     ebx, eax
0x18001ed0d  test    eax, eax
0x18001ed0f  js      short loc_18001ED4E
0x18001ed11  mov     rcx, [rbp+4Fh+var_98]
0x18001ed15  movups  xmm0, xmmword ptr [r15]
0x18001ed19  movdqu  [rbp+4Fh+var_40], xmm0
0x18001ed1e  movups  xmm1, xmmword ptr [r14]
0x18001ed22  movdqu  [rbp+4Fh+var_50], xmm1
0x18001ed27  movups  xmm0, xmmword ptr [rsi]
0x18001ed2a  movdqu  [rbp+4Fh+var_60], xmm0
0x18001ed2f  mov     rax, [rcx]
0x18001ed32  mov     [rsp+110h+ppv], r12
0x18001ed37  lea     r9, [rbp+4Fh+var_40]
0x18001ed3b  lea     r8, [rbp+4Fh+var_50]
0x18001ed3f  lea     rdx, [rbp+4Fh+var_60]
0x18001ed43  mov     rax, [rax+30h]
0x18001ed47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ed4c  mov     ebx, eax
0x18001ed4e  mov     eax, cs:dword_180039000
0x18001ed54  cmp     eax, 5
0x18001ed57  jbe     loc_18001EE1B
0x18001ed5d  call    _tlgKeywordOn
0x18001ed62  test    al, al
0x18001ed64  jz      loc_18001EE1B
0x18001ed6a  mov     [rbp+4Fh+var_88], r15
0x18001ed6e  mov     [rbp+4Fh+var_80], r14
0x18001ed72  mov     [rbp+4Fh+var_78], rsi
0x18001ed76  lea     rax, [r13+40h]
0x18001ed7a  mov     [rbp+4Fh+var_70], rax
0x18001ed7e  mov     [rbp+4Fh+var_90], 0D8h
0x18001ed85  lea     rax, aOnecoreuapBase_0; "onecoreuap\\base\\diagnosis\\pdi\\diags"...
0x18001ed8c  mov     [rbp+4Fh+var_68], rax
0x18001ed90  lea     rax, aDiagnosticrunn; "DiagnosticRunner::CallRecommendedTroubl"...
0x18001ed97  mov     qword ptr [rbp+4Fh+var_60], rax
0x18001ed9b  lea     rax, aCallRtpSRunsel; "Call RTP's RunSelfHelpTroubleshooter"
0x18001eda2  mov     qword ptr [rbp+4Fh+var_50], rax
0x18001eda6  mov     [rbp+4Fh+var_8C], ebx
0x18001eda9  lea     rax, [r13+0C1h]
0x18001edb0  mov     qword ptr [rbp+4Fh+var_40], rax
0x18001edb4  lea     rax, [rbp+4Fh+var_88]
0x18001edb8  mov     [rsp+110h+var_A8], rax
0x18001edbd  lea     rax, [rbp+4Fh+var_80]
0x18001edc1  mov     [rsp+110h+var_B0], rax
0x18001edc6  lea     rax, [rbp+4Fh+var_78]
0x18001edca  mov     [rsp+110h+var_B8], rax
0x18001edcf  lea     rax, [rbp+4Fh+var_70]
0x18001edd3  mov     [rsp+110h+var_C0], rax
0x18001edd8  lea     rax, [rbp+4Fh+var_90]
0x18001eddc  mov     [rsp+110h+var_C8], rax
0x18001ede1  lea     rax, [rbp+4Fh+var_68]
0x18001ede5  mov     [rsp+110h+var_D0], rax
0x18001edea  lea     rax, [rbp+4Fh+var_60]
0x18001edee  mov     [rsp+110h+var_D8], rax
0x18001edf3  lea     rax, [rbp+4Fh+var_50]
0x18001edf7  mov     [rsp+110h+var_E0], rax
0x18001edfc  lea     rax, [rbp+4Fh+var_8C]
0x18001ee00  mov     [rsp+110h+var_E8], rax
0x18001ee05  lea     rax, [rbp+4Fh+var_40]
0x18001ee09  mov     [rsp+110h+ppv], rax
0x18001ee0e  lea     rdx, unk_180032780
0x18001ee15  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U2@U1@U?$_tlgWrapperByRef@$0BA@@@U3@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33343AEBU?$_tlgWrapperByRef@$0BA@@@55@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &)
0x18001ee1a  nop
0x18001ee1b  lea     rcx, [rbp+4Fh+var_A0]
0x18001ee1f  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x18001ee24  nop
0x18001ee25  lea     rcx, [rbp+4Fh+var_98]
0x18001ee29  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x18001ee2e  mov     eax, ebx
0x18001ee30  mov     rbx, [rsp+110h+arg_0]
0x18001ee38  add     rsp, 0E0h
0x18001ee3f  pop     r15
0x18001ee41  pop     r14
0x18001ee43  pop     r13
0x18001ee45  pop     r12
0x18001ee47  pop     rdi
0x18001ee48  pop     rsi
0x18001ee49  pop     rbp
0x18001ee4a  retn
```
