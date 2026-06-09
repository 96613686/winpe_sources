# ConstraintIndexTelemetry::ConstraintIndexDownloader_BuildSettingsConstraintIndex::StopActivity(void)

- ea: `0x180089490`
- end: `0x1800896e2`
- name: `?StopActivity@ConstraintIndexDownloader_BuildSettingsConstraintIndex@ConstraintIndexTelemetry@@MEAAXXZ`
- size: `594`
- prototype: `void __fastcall(ConstraintIndexTelemetry::ConstraintIndexDownloader_BuildSettingsConstraintIndex *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config`

## callees

- `0x180001314`
- `0x1800019ec`
- `0x18000243c`
- `0x18003bf74`
- `0x18003c9b8`
- `0x180040bb8`
- `0x180089490`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180089683`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180089683`

## pseudocode

```c
void __fastcall ConstraintIndexTelemetry::ConstraintIndexDownloader_BuildSettingsConstraintIndex::StopActivity(
        ConstraintIndexTelemetry::ConstraintIndexDownloader_BuildSettingsConstraintIndex *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  const struct _tlgProvider_t *v5; // rax
  __int64 v6; // r8
  int v7; // r9d
  __int64 v8; // r8
  const struct _tlgProvider_t *v9; // rax
  __int64 v10; // r8
  __int64 v11; // r9
  int v12; // edi
  DWORD CurrentThreadId; // eax
  __int64 v14; // r8
  int v15; // r9d
  int v16; // [rsp+C0h] [rbp-80h] BYREF
  int v17; // [rsp+C4h] [rbp-7Ch] BYREF
  int v18; // [rsp+C8h] [rbp-78h] BYREF
  int v19; // [rsp+CCh] [rbp-74h] BYREF
  __int64 v20; // [rsp+D0h] [rbp-70h] BYREF
  __int64 v21; // [rsp+D8h] [rbp-68h] BYREF
  __int64 v22; // [rsp+E0h] [rbp-60h] BYREF
  __int64 v23; // [rsp+E8h] [rbp-58h] BYREF
  __int64 v24; // [rsp+F0h] [rbp-50h] BYREF
  __int64 v25; // [rsp+F8h] [rbp-48h] BYREF
  __int64 v26; // [rsp+100h] [rbp-40h] BYREF
  __int64 v27; // [rsp+108h] [rbp-38h] BYREF
  __int64 v28; // [rsp+110h] [rbp-30h] BYREF
  __int64 v29; // [rsp+118h] [rbp-28h] BYREF
  __int64 v30[4]; // [rsp+120h] [rbp-20h] BYREF
  __int64 v31; // [rsp+150h] [rbp+10h] BYREF
  __int64 v32; // [rsp+158h] [rbp+18h] BYREF
  __int64 v33; // [rsp+160h] [rbp+20h] BYREF
  __int64 v34; // [rsp+168h] [rbp+28h] BYREF

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = (int *)(v1 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<CortanaSearchTelemetryLogging,1,1,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v5 = CortanaSearchTelemetryLogging::Provider();
    if ( *(_DWORD *)v5 > 5u && (unsigned __int8)tlgKeywordOn(v5, 1, v6, v5) )
    {
      v20 = *((_QWORD *)v4 + 6);
      LODWORD(v31) = v4[17];
      LODWORD(v32) = v4[4];
      v21 = *((_QWORD *)v4 + 15);
      v22 = *((_QWORD *)v4 + 14);
      v8 = *((_QWORD *)this + 34);
      LODWORD(v33) = v4[26];
      v23 = *((_QWORD *)v4 + 12);
      v24 = *((_QWORD *)v4 + 11);
      LODWORD(v34) = v4[20];
      v25 = *((_QWORD *)v4 + 9);
      v16 = v4[8];
      v26 = *((_QWORD *)v4 + 3);
      v17 = *v4;
      v27 = *((_QWORD *)v4 + 16);
      v18 = v4[16];
      v28 = *((_QWORD *)v4 + 7);
      v19 = v4[2];
      v29 = 0x1000000;
      v30[0] = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v7,
        (int)&word_180111FEA,
        v8 + 8,
        (__int64)v30,
        (__int64)&v29,
        (__int64)&v19,
        (__int64)&v28,
        (__int64)&v18,
        (__int64)&v27,
        (__int64)&v17,
        (__int64)&v26,
        (__int64)&v16,
        (__int64)&v25,
        (__int64)&v34,
        (__int64)&v24,
        (__int64)&v23,
        (__int64)&v33,
        (__int64)&v22,
        (__int64)&v21,
        (__int64)&v32,
        (__int64)&v31,
        (__int64)&v20);
    }
  }
  else
  {
    wil::ActivityBase<CortanaSearchTelemetryLogging,1,1,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v9 = CortanaSearchTelemetryLogging::Provider();
    v12 = (int)v9;
    if ( *(_DWORD *)v9 > 5u && (unsigned __int8)tlgKeywordOn(v9, 1, v10, v11) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v14 = *((_QWORD *)this + 34);
      LODWORD(v31) = CurrentThreadId;
      LODWORD(v32) = *(_DWORD *)(v14 + 72);
      v33 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v12,
        (unsigned int)byte_18011215B,
        v14 + 8,
        v15,
        (__int64)&v33,
        (__int64)&v32,
        (__int64)&v31);
    }
  }
  wil::ActivityBase<CortanaSearchTelemetryLogging,1,1,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(this);
}

```

## disassembly

```asm
0x180089490  push    rbp
0x180089492  push    rbx
0x180089493  push    rdi
0x180089494  lea     rbp, [rsp+10h]
0x180089499  sub     rsp, 130h
0x1800894a0  mov     rdi, [rcx+110h]
0x1800894a7  mov     rbx, rcx
0x1800894aa  mov     eax, [rdi+48h]
0x1800894ad  test    eax, eax
0x1800894af  jns     loc_18008965E
0x1800894b5  add     rdi, 50h ; 'P'
0x1800894b9  cmp     eax, [rdi+8]
0x1800894bc  jnz     loc_18008965E
0x1800894c2  test    rdi, rdi
0x1800894c5  jz      loc_18008965E
0x1800894cb  call    ?zInternalStop@?$ActivityBase@VCortanaSearchTelemetryLogging@@$00$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CortanaSearchTelemetryLogging,1,1,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x1800894d0  call    ?Provider@CortanaSearchTelemetryLogging@@SAPEBU_tlgProvider_t@@XZ; CortanaSearchTelemetryLogging::Provider(void)
0x1800894d5  mov     r9, rax
0x1800894d8  mov     ecx, [rax]
0x1800894da  cmp     ecx, 5
0x1800894dd  jbe     loc_1800896D0
0x1800894e3  mov     edx, 1
0x1800894e8  mov     rcx, rax
0x1800894eb  call    _tlgKeywordOn
0x1800894f0  test    al, al
0x1800894f2  jz      loc_1800896D0
0x1800894f8  mov     rax, [rdi+30h]
0x1800894fc  lea     rdx, word_180111FEA; int
0x180089503  mov     [rbp+var_70], rax
0x180089507  mov     rcx, r9; int
0x18008950a  mov     eax, [rdi+44h]
0x18008950d  mov     dword ptr [rbp+arg_0], eax
0x180089510  mov     eax, [rdi+10h]
0x180089513  mov     dword ptr [rbp+arg_8], eax
0x180089516  mov     rax, [rdi+78h]
0x18008951a  mov     [rbp+var_68], rax
0x18008951e  mov     rax, [rdi+70h]
0x180089522  mov     [rbp+var_60], rax
0x180089526  mov     eax, [rdi+68h]
0x180089529  mov     r8, [rbx+110h]
0x180089530  mov     dword ptr [rbp+arg_10], eax
0x180089533  add     r8, 8; int
0x180089537  mov     rax, [rdi+60h]
0x18008953b  mov     [rbp+var_58], rax
0x18008953f  mov     rax, [rdi+58h]
0x180089543  mov     [rbp+var_50], rax
0x180089547  mov     eax, [rdi+50h]
0x18008954a  mov     dword ptr [rbp+arg_18], eax
0x18008954d  mov     rax, [rdi+48h]
0x180089551  mov     [rbp+var_48], rax
0x180089555  mov     eax, [rdi+20h]
0x180089558  mov     dword ptr [rbp+var_80], eax
0x18008955b  mov     rax, [rdi+18h]
0x18008955f  mov     [rbp+var_40], rax
0x180089563  mov     eax, [rdi]
0x180089565  mov     dword ptr [rbp+var_80+4], eax
0x180089568  mov     rax, [rdi+80h]
0x18008956f  mov     [rbp+var_38], rax
0x180089573  mov     eax, [rdi+40h]
0x180089576  mov     dword ptr [rbp+var_78], eax
0x180089579  mov     rax, [rdi+38h]
0x18008957d  mov     [rbp+var_30], rax
0x180089581  mov     eax, [rdi+8]
0x180089584  mov     dword ptr [rbp+var_78+4], eax
0x180089587  lea     rax, [rbp+var_70]
0x18008958b  mov     [rsp+140h+var_90], rax; __int64
0x180089593  lea     rax, [rbp+arg_0]
0x180089597  mov     [rsp+140h+var_98], rax; __int64
0x18008959f  lea     rax, [rbp+arg_8]
0x1800895a3  mov     [rsp+140h+var_A0], rax; __int64
0x1800895ab  lea     rax, [rbp+var_68]
0x1800895af  mov     [rsp+140h+var_A8], rax; __int64
0x1800895b7  lea     rax, [rbp+var_60]
0x1800895bb  mov     [rsp+140h+var_B0], rax; __int64
0x1800895c3  lea     rax, [rbp+arg_10]
0x1800895c7  mov     [rsp+140h+var_B8], rax; __int64
0x1800895cf  lea     rax, [rbp+var_58]
0x1800895d3  mov     [rsp+140h+var_C0], rax; __int64
0x1800895db  lea     rax, [rbp+var_50]
0x1800895df  mov     [rsp+140h+var_C8], rax; __int64
0x1800895e4  lea     rax, [rbp+arg_18]
0x1800895e8  mov     [rsp+140h+var_D0], rax; __int64
0x1800895ed  lea     rax, [rbp+var_48]
0x1800895f1  mov     [rsp+140h+var_D8], rax; __int64
0x1800895f6  lea     rax, [rbp+var_80]
0x1800895fa  mov     [rsp+140h+var_E0], rax; __int64
0x1800895ff  lea     rax, [rbp+var_40]
0x180089603  mov     [rsp+140h+var_E8], rax; __int64
0x180089608  lea     rax, [rbp+var_80+4]
0x18008960c  mov     [rsp+140h+var_F0], rax; __int64
0x180089611  lea     rax, [rbp+var_38]
0x180089615  mov     [rsp+140h+var_F8], rax; __int64
0x18008961a  lea     rax, [rbp+var_78]
0x18008961e  mov     [rsp+140h+var_100], rax; __int64
0x180089623  lea     rax, [rbp+var_30]
0x180089627  mov     [rsp+140h+var_108], rax; __int64
0x18008962c  lea     rax, [rbp+var_78+4]
0x180089630  mov     [rsp+140h+var_110], rax; __int64
0x180089635  lea     rax, [rbp+var_28]
0x180089639  mov     [rsp+140h+var_118], rax; __int64
0x18008963e  lea     rax, [rbp+var_20]
0x180089642  mov     [rsp+140h+var_120], rax; __int64
0x180089647  mov     [rbp+var_28], 1000000h
0x18008964f  mov     [rbp+var_20], 0
0x180089657  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@_W@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@_W@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18008965c  jmp     short loc_1800896D0
0x18008965e  call    ?zInternalStop@?$ActivityBase@VCortanaSearchTelemetryLogging@@$00$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CortanaSearchTelemetryLogging,1,1,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180089663  call    ?Provider@CortanaSearchTelemetryLogging@@SAPEBU_tlgProvider_t@@XZ; CortanaSearchTelemetryLogging::Provider(void)
0x180089668  mov     rdi, rax
0x18008966b  mov     ecx, [rax]
0x18008966d  cmp     ecx, 5
0x180089670  jbe     short loc_1800896D0
0x180089672  mov     edx, 1
0x180089677  mov     rcx, rax
0x18008967a  call    _tlgKeywordOn
0x18008967f  test    al, al
0x180089681  jz      short loc_1800896D0
0x180089683  call    cs:__imp_GetCurrentThreadId
0x180089689  mov     r8, [rbx+110h]
0x180089690  lea     rdx, byte_18011215B
0x180089697  mov     dword ptr [rbp+arg_0], eax
0x18008969a  mov     rcx, rdi
0x18008969d  mov     eax, [r8+48h]
0x1800896a1  add     r8, 8
0x1800896a5  mov     dword ptr [rbp+arg_8], eax
0x1800896a8  lea     rax, [rbp+arg_0]
0x1800896ac  mov     [rsp+140h+var_110], rax
0x1800896b1  lea     rax, [rbp+arg_8]
0x1800896b5  mov     [rsp+140h+var_118], rax
0x1800896ba  lea     rax, [rbp+arg_10]
0x1800896be  mov     [rsp+140h+var_120], rax
0x1800896c3  mov     [rbp+arg_10], 0
0x1800896cb  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800896d0  mov     rcx, rbx
0x1800896d3  add     rsp, 130h
0x1800896da  pop     rdi
0x1800896db  pop     rbx
0x1800896dc  pop     rbp
0x1800896dd  jmp     ?IgnoreCurrentThread@?$ActivityBase@VCortanaSearchTelemetryLogging@@$00$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CortanaSearchTelemetryLogging,1,1,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
