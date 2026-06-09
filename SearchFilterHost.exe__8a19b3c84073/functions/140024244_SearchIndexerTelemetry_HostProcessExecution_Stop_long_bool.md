# SearchIndexerTelemetry::HostProcessExecution::Stop(long,bool)

- ea: `0x140024244`
- end: `0x14002451b`
- name: `?Stop@HostProcessExecution@SearchIndexerTelemetry@@QEAAXJ_N@Z`
- size: `727`
- prototype: `void __fastcall(SearchIndexerTelemetry::HostProcessExecution *__hidden this, int, bool)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x14002753c`

## callees

- `0x14000185c`
- `0x140001888`
- `0x140001928`
- `0x1400030a0`
- `0x1400213f0`
- `0x140022688`
- `0x140024244`
- `0x1400272e0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140024459`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140024459`

## pseudocode

```c
void __fastcall SearchIndexerTelemetry::HostProcessExecution::Stop(
        SearchIndexerTelemetry::HostProcessExecution *this,
        int a2,
        unsigned __int8 a3)
{
  __int64 v3; // rdi
  int v5; // esi
  int v7; // eax
  __int64 v8; // rdi
  const struct _tlgProvider_t *v9; // rax
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // r9
  __int64 v13; // r8
  const struct _tlgProvider_t *v14; // rax
  __int64 v15; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v17; // r8
  int v18; // [rsp+B0h] [rbp-80h] BYREF
  DWORD v19; // [rsp+B4h] [rbp-7Ch] BYREF
  int v20; // [rsp+B8h] [rbp-78h] BYREF
  int v21; // [rsp+BCh] [rbp-74h] BYREF
  int v22; // [rsp+C0h] [rbp-70h] BYREF
  int v23; // [rsp+C4h] [rbp-6Ch] BYREF
  int v24; // [rsp+C8h] [rbp-68h] BYREF
  int v25; // [rsp+CCh] [rbp-64h] BYREF
  __int64 v26; // [rsp+D0h] [rbp-60h] BYREF
  const wchar_t *v27; // [rsp+D8h] [rbp-58h] BYREF
  const wchar_t *v28; // [rsp+E0h] [rbp-50h] BYREF
  const wchar_t *v29; // [rsp+E8h] [rbp-48h] BYREF
  const wchar_t *v30; // [rsp+F0h] [rbp-40h] BYREF
  const wchar_t *v31; // [rsp+F8h] [rbp-38h] BYREF
  const wchar_t *v32; // [rsp+100h] [rbp-30h] BYREF
  const wchar_t *v33; // [rsp+108h] [rbp-28h] BYREF
  const wchar_t *v34; // [rsp+110h] [rbp-20h] BYREF
  __int64 v35; // [rsp+118h] [rbp-18h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v36; // [rsp+120h] [rbp-10h] BYREF
  __int64 *v37; // [rsp+140h] [rbp+10h]
  __int64 v38; // [rsp+148h] [rbp+18h]
  int *v39; // [rsp+150h] [rbp+20h]
  __int64 v40; // [rsp+158h] [rbp+28h]
  DWORD *v41; // [rsp+160h] [rbp+30h]
  __int64 v42; // [rsp+168h] [rbp+38h]
  int *v43; // [rsp+170h] [rbp+40h]
  __int64 v44; // [rsp+178h] [rbp+48h]
  int *v45; // [rsp+180h] [rbp+50h]
  __int64 v46; // [rsp+188h] [rbp+58h]

  v3 = *((_QWORD *)this + 34);
  v5 = a3;
  v7 = *(_DWORD *)(v3 + 72);
  if ( v7 < 0 && (v8 = v3 + 80, v7 == *(_DWORD *)(v8 + 8)) && v8 )
  {
    wil::ActivityBase<SearchIndexerLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v9 = SearchIndexerLogging::Provider();
    v12 = (__int64)v9;
    if ( *(_DWORD *)v9 > 5u && (unsigned __int8)tlgKeywordOn(v9, 0x400000000000LL, v11, v9) )
    {
      v27 = *(const wchar_t **)(v8 + 120);
      v13 = *((_QWORD *)this + 34);
      v28 = *(const wchar_t **)(v8 + 112);
      v24 = *(_DWORD *)(v8 + 104);
      v29 = *(const wchar_t **)(v8 + 96);
      v30 = *(const wchar_t **)(v8 + 88);
      v25 = *(_DWORD *)(v8 + 80);
      v31 = *(const wchar_t **)(v8 + 72);
      v18 = *(_DWORD *)(v8 + 32);
      v32 = *(const wchar_t **)(v8 + 24);
      v19 = *(_DWORD *)v8;
      v33 = *(const wchar_t **)(v8 + 128);
      v20 = *(_DWORD *)(v8 + 64);
      v34 = *(const wchar_t **)(v8 + 56);
      v21 = *(_DWORD *)(v8 + 8);
      v22 = a2;
      v23 = v5;
      v35 = 0x1000000;
      v26 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v12,
        (__int64)&word_14005CFDE,
        v13 + 8,
        v12,
        (__int64)&v26,
        (__int64)&v35,
        (__int64)&v21,
        &v34,
        (__int64)&v20,
        &v33,
        (__int64)&v19,
        &v32,
        (__int64)&v18,
        &v31,
        (__int64)&v25,
        &v30,
        &v29,
        (__int64)&v24,
        &v28,
        &v27,
        (__int64)&v23,
        (__int64)&v22);
    }
  }
  else
  {
    wil::ActivityBase<SearchIndexerLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v14 = SearchIndexerLogging::Provider();
    v15 = (__int64)v14;
    if ( *(_DWORD *)v14 > 5u && (unsigned __int8)tlgKeywordOn(v14, 0x400000000000LL, v11, v12) )
    {
      v21 = a2;
      v20 = v5;
      CurrentThreadId = GetCurrentThreadId();
      v17 = *((_QWORD *)this + 34);
      v19 = CurrentThreadId;
      v46 = 4;
      v44 = 4;
      v18 = *(_DWORD *)(v17 + 72);
      v45 = &v21;
      v43 = &v20;
      v41 = &v19;
      v39 = &v18;
      v37 = &v26;
      v26 = 0;
      v42 = 4;
      v40 = 4;
      v38 = 8;
      tlgWriteTransfer_EventWriteTransfer(v15, (unsigned __int8 *)byte_14005D133, (const GUID *)(v17 + 8), 0, 7u, &v36);
    }
  }
  wil::ActivityBase<SearchIndexerLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
    this,
    v10,
    v11,
    v12);
}

```

## disassembly

```asm
0x140024244  mov     [rsp-8+arg_8], rbx
0x140024249  mov     [rsp-8+arg_10], rsi
0x14002424e  push    rbp
0x14002424f  push    rdi
0x140024250  push    r14
0x140024252  lea     rbp, [rsp-70h]
0x140024257  sub     rsp, 1A0h
0x14002425e  mov     rax, cs:__security_cookie
0x140024265  xor     rax, rsp
0x140024268  mov     [rbp+80h+var_20], rax
0x14002426c  mov     rdi, [rcx+110h]
0x140024273  mov     r14d, edx
0x140024276  movzx   esi, r8b
0x14002427a  mov     rbx, rcx
0x14002427d  mov     eax, [rdi+48h]
0x140024280  test    eax, eax
0x140024282  jns     loc_140024420
0x140024288  add     rdi, 50h ; 'P'
0x14002428c  cmp     eax, [rdi+8]
0x14002428f  jnz     loc_140024420
0x140024295  test    rdi, rdi
0x140024298  jz      loc_140024420
0x14002429e  call    ?zInternalStop@?$ActivityBase@VSearchIndexerLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<SearchIndexerLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x1400242a3  call    ?Provider@SearchIndexerLogging@@SAPEBU_tlgProvider_t@@XZ; SearchIndexerLogging::Provider(void)
0x1400242a8  mov     r9, rax
0x1400242ab  mov     ecx, [rax]
0x1400242ad  cmp     ecx, 5
0x1400242b0  jbe     loc_1400244EF
0x1400242b6  mov     rdx, 400000000000h
0x1400242c0  mov     rcx, rax
0x1400242c3  call    _tlgKeywordOn
0x1400242c8  test    al, al
0x1400242ca  jz      loc_1400244EF
0x1400242d0  mov     rax, [rdi+78h]
0x1400242d4  lea     rdx, word_14005CFDE
0x1400242db  mov     [rbp+80h+var_D8], rax
0x1400242df  mov     rcx, r9
0x1400242e2  mov     rax, [rdi+70h]
0x1400242e6  mov     r8, [rbx+110h]
0x1400242ed  mov     [rbp+80h+var_D0], rax
0x1400242f1  add     r8, 8
0x1400242f5  mov     eax, [rdi+68h]
0x1400242f8  mov     [rbp+80h+var_E8], eax
0x1400242fb  mov     rax, [rdi+60h]
0x1400242ff  mov     [rbp+80h+var_C8], rax
0x140024303  mov     rax, [rdi+58h]
0x140024307  mov     [rbp+80h+var_C0], rax
0x14002430b  mov     eax, [rdi+50h]
0x14002430e  mov     [rbp+80h+var_E4], eax
0x140024311  mov     rax, [rdi+48h]
0x140024315  mov     [rbp+80h+var_B8], rax
0x140024319  mov     eax, [rdi+20h]
0x14002431c  mov     [rbp+80h+var_100], eax
0x14002431f  mov     rax, [rdi+18h]
0x140024323  mov     [rbp+80h+var_B0], rax
0x140024327  mov     eax, [rdi]
0x140024329  mov     [rbp+80h+var_FC], eax
0x14002432c  mov     rax, [rdi+80h]
0x140024333  mov     [rbp+80h+var_A8], rax
0x140024337  mov     eax, [rdi+40h]
0x14002433a  mov     [rbp+80h+var_F8], eax
0x14002433d  mov     rax, [rdi+38h]
0x140024341  mov     [rbp+80h+var_A0], rax
0x140024345  mov     eax, [rdi+8]
0x140024348  mov     [rbp+80h+var_F4], eax
0x14002434b  lea     rax, [rbp+80h+var_F0]
0x14002434f  mov     [rsp+1B0h+var_108], rax
0x140024357  lea     rax, [rbp+80h+var_EC]
0x14002435b  mov     [rsp+1B0h+var_110], rax
0x140024363  lea     rax, [rbp+80h+var_D8]
0x140024367  mov     [rsp+1B0h+var_118], rax
0x14002436f  lea     rax, [rbp+80h+var_D0]
0x140024373  mov     [rsp+1B0h+var_120], rax
0x14002437b  lea     rax, [rbp+80h+var_E8]
0x14002437f  mov     [rsp+1B0h+var_128], rax
0x140024387  lea     rax, [rbp+80h+var_C8]
0x14002438b  mov     [rsp+1B0h+var_130], rax
0x140024393  lea     rax, [rbp+80h+var_C0]
0x140024397  mov     [rsp+1B0h+var_138], rax
0x14002439c  lea     rax, [rbp+80h+var_E4]
0x1400243a0  mov     [rsp+1B0h+var_140], rax
0x1400243a5  lea     rax, [rbp+80h+var_B8]
0x1400243a9  mov     [rsp+1B0h+var_148], rax
0x1400243ae  lea     rax, [rbp+80h+var_100]
0x1400243b2  mov     [rsp+1B0h+var_150], rax
0x1400243b7  lea     rax, [rbp+80h+var_B0]
0x1400243bb  mov     [rsp+1B0h+var_158], rax
0x1400243c0  lea     rax, [rbp+80h+var_FC]
0x1400243c4  mov     [rsp+1B0h+var_160], rax
0x1400243c9  lea     rax, [rbp+80h+var_A8]
0x1400243cd  mov     [rsp+1B0h+var_168], rax
0x1400243d2  lea     rax, [rbp+80h+var_F8]
0x1400243d6  mov     [rsp+1B0h+var_170], rax
0x1400243db  lea     rax, [rbp+80h+var_A0]
0x1400243df  mov     [rsp+1B0h+var_178], rax
0x1400243e4  lea     rax, [rbp+80h+var_F4]
0x1400243e8  mov     [rsp+1B0h+var_180], rax
0x1400243ed  lea     rax, [rbp+80h+var_98]
0x1400243f1  mov     [rsp+1B0h+var_188], rax
0x1400243f6  lea     rax, [rbp+80h+var_E0]
0x1400243fa  mov     [rsp+1B0h+var_190], rax
0x1400243ff  mov     [rbp+80h+var_F0], r14d
0x140024403  mov     [rbp+80h+var_EC], esi
0x140024406  mov     [rbp+80h+var_98], 1000000h
0x14002440e  mov     [rbp+80h+var_E0], 0
0x140024416  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@_W@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@_W@@4545645644@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14002441b  jmp     loc_1400244EF
0x140024420  call    ?zInternalStop@?$ActivityBase@VSearchIndexerLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<SearchIndexerLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x140024425  call    ?Provider@SearchIndexerLogging@@SAPEBU_tlgProvider_t@@XZ; SearchIndexerLogging::Provider(void)
0x14002442a  mov     rdi, rax
0x14002442d  mov     ecx, [rax]
0x14002442f  cmp     ecx, 5
0x140024432  jbe     loc_1400244EF
0x140024438  mov     rdx, 400000000000h
0x140024442  mov     rcx, rax
0x140024445  call    _tlgKeywordOn
0x14002444a  test    al, al
0x14002444c  jz      loc_1400244EF
0x140024452  mov     [rbp+80h+var_F4], r14d
0x140024456  mov     [rbp+80h+var_F8], esi
0x140024459  call    cs:__imp_GetCurrentThreadId
0x14002445f  mov     r8, [rbx+110h]
0x140024466  lea     rdx, byte_14005D133
0x14002446d  mov     [rbp+80h+var_FC], eax
0x140024470  xor     r9d, r9d
0x140024473  mov     rcx, rdi
0x140024476  mov     [rbp+80h+var_28], 4
0x14002447e  mov     [rbp+80h+var_38], 4
0x140024486  mov     eax, [r8+48h]
0x14002448a  add     r8, 8
0x14002448e  mov     [rbp+80h+var_100], eax
0x140024491  lea     rax, [rbp+80h+var_F4]
0x140024495  mov     [rbp+80h+var_30], rax
0x140024499  lea     rax, [rbp+80h+var_F8]
0x14002449d  mov     [rbp+80h+var_40], rax
0x1400244a1  lea     rax, [rbp+80h+var_FC]
0x1400244a5  mov     [rbp+80h+var_50], rax
0x1400244a9  lea     rax, [rbp+80h+var_100]
0x1400244ad  mov     [rbp+80h+var_60], rax
0x1400244b1  lea     rax, [rbp+80h+var_E0]
0x1400244b5  mov     [rbp+80h+var_70], rax
0x1400244b9  lea     rax, [rbp+80h+var_90]
0x1400244bd  mov     [rsp+1B0h+var_188], rax
0x1400244c2  mov     dword ptr [rsp+1B0h+var_190], 7
0x1400244ca  mov     [rbp+80h+var_E0], 0
0x1400244d2  mov     [rbp+80h+var_48], 4
0x1400244da  mov     [rbp+80h+var_58], 4
0x1400244e2  mov     [rbp+80h+var_68], 8
0x1400244ea  call    _tlgWriteTransfer_EventWriteTransfer
0x1400244ef  mov     rcx, rbx
0x1400244f2  call    ?IgnoreCurrentThread@?$ActivityBase@VSearchIndexerLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<SearchIndexerLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
0x1400244f7  mov     rcx, [rbp+80h+var_20]
0x1400244fb  xor     rcx, rsp; StackCookie
0x1400244fe  call    __security_check_cookie
0x140024503  lea     r11, [rsp+1B0h+var_10]
0x14002450b  mov     rbx, [r11+28h]
0x14002450f  mov     rsi, [r11+30h]
0x140024513  mov     rsp, r11
0x140024516  pop     r14
0x140024518  pop     rdi
0x140024519  pop     rbp
0x14002451a  retn
```
