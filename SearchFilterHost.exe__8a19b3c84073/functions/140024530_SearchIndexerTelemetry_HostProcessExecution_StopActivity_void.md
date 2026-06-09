# SearchIndexerTelemetry::HostProcessExecution::StopActivity(void)

- ea: `0x140024530`
- end: `0x1400247b0`
- name: `?StopActivity@HostProcessExecution@SearchIndexerTelemetry@@MEAAXXZ`
- size: `640`
- prototype: `void __fastcall(SearchIndexerTelemetry::HostProcessExecution *__hidden this)`
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x140001158`
- `0x14000185c`
- `0x140001888`
- `0x1400030a0`
- `0x1400213f0`
- `0x140022688`
- `0x140024530`
- `0x1400272e0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140024711`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140024711`

## pseudocode

```c
void __fastcall SearchIndexerTelemetry::HostProcessExecution::StopActivity(
        SearchIndexerTelemetry::HostProcessExecution *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  const struct _tlgProvider_t *v5; // rax
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // r9
  const wchar_t *v9; // rcx
  __int64 v10; // r8
  const struct _tlgProvider_t *v11; // rax
  __int64 v12; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v14; // r8
  int v15; // [rsp+A0h] [rbp-80h] BYREF
  DWORD v16; // [rsp+A4h] [rbp-7Ch] BYREF
  int v17; // [rsp+A8h] [rbp-78h] BYREF
  int v18; // [rsp+ACh] [rbp-74h] BYREF
  int v19; // [rsp+B0h] [rbp-70h] BYREF
  int v20; // [rsp+B4h] [rbp-6Ch] BYREF
  __int64 v21; // [rsp+B8h] [rbp-68h] BYREF
  const wchar_t *v22; // [rsp+C0h] [rbp-60h] BYREF
  const wchar_t *v23; // [rsp+C8h] [rbp-58h] BYREF
  const wchar_t *v24; // [rsp+D0h] [rbp-50h] BYREF
  const wchar_t *v25; // [rsp+D8h] [rbp-48h] BYREF
  const wchar_t *v26; // [rsp+E0h] [rbp-40h] BYREF
  const wchar_t *v27; // [rsp+E8h] [rbp-38h] BYREF
  const wchar_t *v28; // [rsp+F0h] [rbp-30h] BYREF
  const wchar_t *v29; // [rsp+F8h] [rbp-28h] BYREF
  __int64 v30; // [rsp+100h] [rbp-20h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v31; // [rsp+110h] [rbp-10h] BYREF
  __int64 *v32; // [rsp+130h] [rbp+10h]
  __int64 v33; // [rsp+138h] [rbp+18h]
  int *v34; // [rsp+140h] [rbp+20h]
  __int64 v35; // [rsp+148h] [rbp+28h]
  DWORD *v36; // [rsp+150h] [rbp+30h]
  __int64 v37; // [rsp+158h] [rbp+38h]

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = (int *)(v1 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<SearchIndexerLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v5 = SearchIndexerLogging::Provider();
    v8 = (__int64)v5;
    if ( *(_DWORD *)v5 > 5u && (unsigned __int8)tlgKeywordOn(v5, 0x400000000000LL, v7, v5) )
    {
      v9 = (const wchar_t *)*((_QWORD *)v4 + 15);
      v10 = *((_QWORD *)this + 34);
      v23 = (const wchar_t *)*((_QWORD *)v4 + 14);
      v17 = v4[26];
      v24 = (const wchar_t *)*((_QWORD *)v4 + 12);
      v25 = (const wchar_t *)*((_QWORD *)v4 + 11);
      v18 = v4[20];
      v26 = (const wchar_t *)*((_QWORD *)v4 + 9);
      v19 = v4[8];
      v27 = (const wchar_t *)*((_QWORD *)v4 + 3);
      v20 = *v4;
      v28 = (const wchar_t *)*((_QWORD *)v4 + 16);
      v15 = v4[16];
      v29 = (const wchar_t *)*((_QWORD *)v4 + 7);
      v16 = v4[2];
      v22 = v9;
      v30 = 0x1000000;
      v21 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>>(
        v8,
        (__int64)&word_14005D3FE,
        v10 + 8,
        v8,
        (__int64)&v21,
        (__int64)&v30,
        (__int64)&v16,
        &v29,
        (__int64)&v15,
        &v28,
        (__int64)&v20,
        &v27,
        (__int64)&v19,
        &v26,
        (__int64)&v18,
        &v25,
        &v24,
        (__int64)&v17,
        &v23,
        &v22);
    }
  }
  else
  {
    wil::ActivityBase<SearchIndexerLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v11 = SearchIndexerLogging::Provider();
    v12 = (__int64)v11;
    if ( *(_DWORD *)v11 > 5u && (unsigned __int8)tlgKeywordOn(v11, 0x400000000000LL, v7, v8) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v14 = *((_QWORD *)this + 34);
      v16 = CurrentThreadId;
      v37 = 4;
      v35 = 4;
      v15 = *(_DWORD *)(v14 + 72);
      v36 = &v16;
      v34 = &v15;
      v32 = &v21;
      v21 = 0;
      v33 = 8;
      tlgWriteTransfer_EventWriteTransfer(v12, (unsigned __int8 *)word_14005D52A, (const GUID *)(v14 + 8), 0, 5u, &v31);
    }
  }
  wil::ActivityBase<SearchIndexerLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
    this,
    v6,
    v7,
    v8);
}

```

## disassembly

```asm
0x140024530  mov     [rsp-8+arg_8], rbx
0x140024535  mov     [rsp-8+arg_10], rdi
0x14002453a  push    rbp
0x14002453b  lea     rbp, [rsp-50h]
0x140024540  sub     rsp, 170h
0x140024547  mov     rax, cs:__security_cookie
0x14002454e  xor     rax, rsp
0x140024551  mov     [rbp+50h+var_10], rax
0x140024555  mov     rdi, [rcx+110h]
0x14002455c  mov     rbx, rcx
0x14002455f  mov     eax, [rdi+48h]
0x140024562  test    eax, eax
0x140024564  jns     loc_1400246E3
0x14002456a  add     rdi, 50h ; 'P'
0x14002456e  cmp     eax, [rdi+8]
0x140024571  jnz     loc_1400246E3
0x140024577  test    rdi, rdi
0x14002457a  jz      loc_1400246E3
0x140024580  call    ?zInternalStop@?$ActivityBase@VSearchIndexerLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<SearchIndexerLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x140024585  call    ?Provider@SearchIndexerLogging@@SAPEBU_tlgProvider_t@@XZ; SearchIndexerLogging::Provider(void)
0x14002458a  mov     r9, rax
0x14002458d  mov     ecx, [rax]
0x14002458f  cmp     ecx, 5
0x140024592  jbe     loc_140024787
0x140024598  mov     rdx, 400000000000h
0x1400245a2  mov     rcx, rax
0x1400245a5  call    _tlgKeywordOn
0x1400245aa  test    al, al
0x1400245ac  jz      loc_140024787
0x1400245b2  mov     rax, [rdi+70h]
0x1400245b6  lea     rdx, word_14005D3FE
0x1400245bd  mov     rcx, [rdi+78h]
0x1400245c1  mov     r8, [rbx+110h]
0x1400245c8  mov     [rbp+50h+var_A8], rax
0x1400245cc  add     r8, 8
0x1400245d0  mov     eax, [rdi+68h]
0x1400245d3  mov     [rbp+50h+var_C8], eax
0x1400245d6  mov     rax, [rdi+60h]
0x1400245da  mov     [rbp+50h+var_A0], rax
0x1400245de  mov     rax, [rdi+58h]
0x1400245e2  mov     [rbp+50h+var_98], rax
0x1400245e6  mov     eax, [rdi+50h]
0x1400245e9  mov     [rbp+50h+var_C4], eax
0x1400245ec  mov     rax, [rdi+48h]
0x1400245f0  mov     [rbp+50h+var_90], rax
0x1400245f4  mov     eax, [rdi+20h]
0x1400245f7  mov     [rbp+50h+var_C0], eax
0x1400245fa  mov     rax, [rdi+18h]
0x1400245fe  mov     [rbp+50h+var_88], rax
0x140024602  mov     eax, [rdi]
0x140024604  mov     [rbp+50h+var_BC], eax
0x140024607  mov     rax, [rdi+80h]
0x14002460e  mov     [rbp+50h+var_80], rax
0x140024612  mov     eax, [rdi+40h]
0x140024615  mov     [rbp+50h+var_D0], eax
0x140024618  mov     rax, [rdi+38h]
0x14002461c  mov     [rbp+50h+var_78], rax
0x140024620  mov     eax, [rdi+8]
0x140024623  mov     [rbp+50h+var_CC], eax
0x140024626  lea     rax, [rbp+50h+var_B0]
0x14002462a  mov     [rsp+170h+var_D8], rax
0x140024632  lea     rax, [rbp+50h+var_A8]
0x140024636  mov     [rsp+170h+var_E0], rax
0x14002463e  lea     rax, [rbp+50h+var_C8]
0x140024642  mov     [rsp+170h+var_E8], rax
0x14002464a  lea     rax, [rbp+50h+var_A0]
0x14002464e  mov     [rsp+170h+var_F0], rax
0x140024656  lea     rax, [rbp+50h+var_98]
0x14002465a  mov     [rsp+170h+var_F8], rax
0x14002465f  lea     rax, [rbp+50h+var_C4]
0x140024663  mov     [rsp+170h+var_100], rax
0x140024668  lea     rax, [rbp+50h+var_90]
0x14002466c  mov     [rsp+170h+var_108], rax
0x140024671  lea     rax, [rbp+50h+var_C0]
0x140024675  mov     [rsp+170h+var_110], rax
0x14002467a  lea     rax, [rbp+50h+var_88]
0x14002467e  mov     [rsp+170h+var_118], rax
0x140024683  lea     rax, [rbp+50h+var_BC]
0x140024687  mov     [rsp+170h+var_120], rax
0x14002468c  lea     rax, [rbp+50h+var_80]
0x140024690  mov     [rsp+170h+var_128], rax
0x140024695  lea     rax, [rbp+50h+var_D0]
0x140024699  mov     [rsp+170h+var_130], rax
0x14002469e  lea     rax, [rbp+50h+var_78]
0x1400246a2  mov     [rsp+170h+var_138], rax
0x1400246a7  lea     rax, [rbp+50h+var_CC]
0x1400246ab  mov     [rsp+170h+var_140], rax
0x1400246b0  lea     rax, [rbp+50h+var_70]
0x1400246b4  mov     [rsp+170h+var_148], rax
0x1400246b9  lea     rax, [rbp+50h+var_B8]
0x1400246bd  mov     [rbp+50h+var_B0], rcx
0x1400246c1  mov     rcx, r9
0x1400246c4  mov     [rsp+170h+var_150], rax
0x1400246c9  mov     [rbp+50h+var_70], 1000000h
0x1400246d1  mov     [rbp+50h+var_B8], 0
0x1400246d9  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@_W@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@_W@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &)
0x1400246de  jmp     loc_140024787
0x1400246e3  call    ?zInternalStop@?$ActivityBase@VSearchIndexerLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<SearchIndexerLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x1400246e8  call    ?Provider@SearchIndexerLogging@@SAPEBU_tlgProvider_t@@XZ; SearchIndexerLogging::Provider(void)
0x1400246ed  mov     rdi, rax
0x1400246f0  mov     ecx, [rax]
0x1400246f2  cmp     ecx, 5
0x1400246f5  jbe     loc_140024787
0x1400246fb  mov     rdx, 400000000000h
0x140024705  mov     rcx, rax
0x140024708  call    _tlgKeywordOn
0x14002470d  test    al, al
0x14002470f  jz      short loc_140024787
0x140024711  call    cs:__imp_GetCurrentThreadId
0x140024717  mov     r8, [rbx+110h]
0x14002471e  lea     rdx, word_14005D52A
0x140024725  mov     [rbp+50h+var_CC], eax
0x140024728  xor     r9d, r9d
0x14002472b  mov     rcx, rdi
0x14002472e  mov     [rbp+50h+var_18], 4
0x140024736  mov     [rbp+50h+var_28], 4
0x14002473e  mov     eax, [r8+48h]
0x140024742  add     r8, 8
0x140024746  mov     [rbp+50h+var_D0], eax
0x140024749  lea     rax, [rbp+50h+var_CC]
0x14002474d  mov     [rbp+50h+var_20], rax
0x140024751  lea     rax, [rbp+50h+var_D0]
0x140024755  mov     [rbp+50h+var_30], rax
0x140024759  lea     rax, [rbp+50h+var_B8]
0x14002475d  mov     [rbp+50h+var_40], rax
0x140024761  lea     rax, [rbp+50h+var_60]
0x140024765  mov     [rsp+170h+var_148], rax
0x14002476a  mov     dword ptr [rsp+170h+var_150], 5
0x140024772  mov     [rbp+50h+var_B8], 0
0x14002477a  mov     [rbp+50h+var_38], 8
0x140024782  call    _tlgWriteTransfer_EventWriteTransfer
0x140024787  mov     rcx, rbx
0x14002478a  call    ?IgnoreCurrentThread@?$ActivityBase@VSearchIndexerLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<SearchIndexerLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
0x14002478f  mov     rcx, [rbp+50h+var_10]
0x140024793  xor     rcx, rsp; StackCookie
0x140024796  call    __security_check_cookie
0x14002479b  lea     r11, [rsp+170h+var_s0]
0x1400247a3  mov     rbx, [r11+18h]
0x1400247a7  mov     rdi, [r11+20h]
0x1400247ab  mov     rsp, r11
0x1400247ae  pop     rbp
0x1400247af  retn
```
