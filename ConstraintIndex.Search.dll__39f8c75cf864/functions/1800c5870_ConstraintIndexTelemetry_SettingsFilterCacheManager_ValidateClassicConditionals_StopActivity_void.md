# ConstraintIndexTelemetry::SettingsFilterCacheManager_ValidateClassicConditionals::StopActivity(void)

- ea: `0x1800c5870`
- end: `0x1800c5ac2`
- name: `?StopActivity@SettingsFilterCacheManager_ValidateClassicConditionals@ConstraintIndexTelemetry@@MEAAXXZ`
- size: `594`
- prototype: `void __fastcall(ConstraintIndexTelemetry::SettingsFilterCacheManager_ValidateClassicConditionals *__hidden this)`
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
- `0x1800c5870`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800c5a63`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800c5a63`

## pseudocode

```c
void __fastcall ConstraintIndexTelemetry::SettingsFilterCacheManager_ValidateClassicConditionals::StopActivity(
        ConstraintIndexTelemetry::SettingsFilterCacheManager_ValidateClassicConditionals *this)
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
        (int)&byte_180114239,
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
        (unsigned int)word_1801141C2,
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
0x1800c5870  push    rbp
0x1800c5872  push    rbx
0x1800c5873  push    rdi
0x1800c5874  lea     rbp, [rsp+10h]
0x1800c5879  sub     rsp, 130h
0x1800c5880  mov     rdi, [rcx+110h]
0x1800c5887  mov     rbx, rcx
0x1800c588a  mov     eax, [rdi+48h]
0x1800c588d  test    eax, eax
0x1800c588f  jns     loc_1800C5A3E
0x1800c5895  add     rdi, 50h ; 'P'
0x1800c5899  cmp     eax, [rdi+8]
0x1800c589c  jnz     loc_1800C5A3E
0x1800c58a2  test    rdi, rdi
0x1800c58a5  jz      loc_1800C5A3E
0x1800c58ab  call    ?zInternalStop@?$ActivityBase@VCortanaSearchTelemetryLogging@@$00$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CortanaSearchTelemetryLogging,1,1,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x1800c58b0  call    ?Provider@CortanaSearchTelemetryLogging@@SAPEBU_tlgProvider_t@@XZ; CortanaSearchTelemetryLogging::Provider(void)
0x1800c58b5  mov     r9, rax
0x1800c58b8  mov     ecx, [rax]
0x1800c58ba  cmp     ecx, 5
0x1800c58bd  jbe     loc_1800C5AB0
0x1800c58c3  mov     edx, 1
0x1800c58c8  mov     rcx, rax
0x1800c58cb  call    _tlgKeywordOn
0x1800c58d0  test    al, al
0x1800c58d2  jz      loc_1800C5AB0
0x1800c58d8  mov     rax, [rdi+30h]
0x1800c58dc  lea     rdx, byte_180114239; int
0x1800c58e3  mov     [rbp+var_70], rax
0x1800c58e7  mov     rcx, r9; int
0x1800c58ea  mov     eax, [rdi+44h]
0x1800c58ed  mov     dword ptr [rbp+arg_0], eax
0x1800c58f0  mov     eax, [rdi+10h]
0x1800c58f3  mov     dword ptr [rbp+arg_8], eax
0x1800c58f6  mov     rax, [rdi+78h]
0x1800c58fa  mov     [rbp+var_68], rax
0x1800c58fe  mov     rax, [rdi+70h]
0x1800c5902  mov     [rbp+var_60], rax
0x1800c5906  mov     eax, [rdi+68h]
0x1800c5909  mov     r8, [rbx+110h]
0x1800c5910  mov     dword ptr [rbp+arg_10], eax
0x1800c5913  add     r8, 8; int
0x1800c5917  mov     rax, [rdi+60h]
0x1800c591b  mov     [rbp+var_58], rax
0x1800c591f  mov     rax, [rdi+58h]
0x1800c5923  mov     [rbp+var_50], rax
0x1800c5927  mov     eax, [rdi+50h]
0x1800c592a  mov     dword ptr [rbp+arg_18], eax
0x1800c592d  mov     rax, [rdi+48h]
0x1800c5931  mov     [rbp+var_48], rax
0x1800c5935  mov     eax, [rdi+20h]
0x1800c5938  mov     dword ptr [rbp+var_80], eax
0x1800c593b  mov     rax, [rdi+18h]
0x1800c593f  mov     [rbp+var_40], rax
0x1800c5943  mov     eax, [rdi]
0x1800c5945  mov     dword ptr [rbp+var_80+4], eax
0x1800c5948  mov     rax, [rdi+80h]
0x1800c594f  mov     [rbp+var_38], rax
0x1800c5953  mov     eax, [rdi+40h]
0x1800c5956  mov     dword ptr [rbp+var_78], eax
0x1800c5959  mov     rax, [rdi+38h]
0x1800c595d  mov     [rbp+var_30], rax
0x1800c5961  mov     eax, [rdi+8]
0x1800c5964  mov     dword ptr [rbp+var_78+4], eax
0x1800c5967  lea     rax, [rbp+var_70]
0x1800c596b  mov     [rsp+140h+var_90], rax; __int64
0x1800c5973  lea     rax, [rbp+arg_0]
0x1800c5977  mov     [rsp+140h+var_98], rax; __int64
0x1800c597f  lea     rax, [rbp+arg_8]
0x1800c5983  mov     [rsp+140h+var_A0], rax; __int64
0x1800c598b  lea     rax, [rbp+var_68]
0x1800c598f  mov     [rsp+140h+var_A8], rax; __int64
0x1800c5997  lea     rax, [rbp+var_60]
0x1800c599b  mov     [rsp+140h+var_B0], rax; __int64
0x1800c59a3  lea     rax, [rbp+arg_10]
0x1800c59a7  mov     [rsp+140h+var_B8], rax; __int64
0x1800c59af  lea     rax, [rbp+var_58]
0x1800c59b3  mov     [rsp+140h+var_C0], rax; __int64
0x1800c59bb  lea     rax, [rbp+var_50]
0x1800c59bf  mov     [rsp+140h+var_C8], rax; __int64
0x1800c59c4  lea     rax, [rbp+arg_18]
0x1800c59c8  mov     [rsp+140h+var_D0], rax; __int64
0x1800c59cd  lea     rax, [rbp+var_48]
0x1800c59d1  mov     [rsp+140h+var_D8], rax; __int64
0x1800c59d6  lea     rax, [rbp+var_80]
0x1800c59da  mov     [rsp+140h+var_E0], rax; __int64
0x1800c59df  lea     rax, [rbp+var_40]
0x1800c59e3  mov     [rsp+140h+var_E8], rax; __int64
0x1800c59e8  lea     rax, [rbp+var_80+4]
0x1800c59ec  mov     [rsp+140h+var_F0], rax; __int64
0x1800c59f1  lea     rax, [rbp+var_38]
0x1800c59f5  mov     [rsp+140h+var_F8], rax; __int64
0x1800c59fa  lea     rax, [rbp+var_78]
0x1800c59fe  mov     [rsp+140h+var_100], rax; __int64
0x1800c5a03  lea     rax, [rbp+var_30]
0x1800c5a07  mov     [rsp+140h+var_108], rax; __int64
0x1800c5a0c  lea     rax, [rbp+var_78+4]
0x1800c5a10  mov     [rsp+140h+var_110], rax; __int64
0x1800c5a15  lea     rax, [rbp+var_28]
0x1800c5a19  mov     [rsp+140h+var_118], rax; __int64
0x1800c5a1e  lea     rax, [rbp+var_20]
0x1800c5a22  mov     [rsp+140h+var_120], rax; __int64
0x1800c5a27  mov     [rbp+var_28], 1000000h
0x1800c5a2f  mov     [rbp+var_20], 0
0x1800c5a37  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@_W@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@_W@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800c5a3c  jmp     short loc_1800C5AB0
0x1800c5a3e  call    ?zInternalStop@?$ActivityBase@VCortanaSearchTelemetryLogging@@$00$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CortanaSearchTelemetryLogging,1,1,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x1800c5a43  call    ?Provider@CortanaSearchTelemetryLogging@@SAPEBU_tlgProvider_t@@XZ; CortanaSearchTelemetryLogging::Provider(void)
0x1800c5a48  mov     rdi, rax
0x1800c5a4b  mov     ecx, [rax]
0x1800c5a4d  cmp     ecx, 5
0x1800c5a50  jbe     short loc_1800C5AB0
0x1800c5a52  mov     edx, 1
0x1800c5a57  mov     rcx, rax
0x1800c5a5a  call    _tlgKeywordOn
0x1800c5a5f  test    al, al
0x1800c5a61  jz      short loc_1800C5AB0
0x1800c5a63  call    cs:__imp_GetCurrentThreadId
0x1800c5a69  mov     r8, [rbx+110h]
0x1800c5a70  lea     rdx, word_1801141C2
0x1800c5a77  mov     dword ptr [rbp+arg_0], eax
0x1800c5a7a  mov     rcx, rdi
0x1800c5a7d  mov     eax, [r8+48h]
0x1800c5a81  add     r8, 8
0x1800c5a85  mov     dword ptr [rbp+arg_8], eax
0x1800c5a88  lea     rax, [rbp+arg_0]
0x1800c5a8c  mov     [rsp+140h+var_110], rax
0x1800c5a91  lea     rax, [rbp+arg_8]
0x1800c5a95  mov     [rsp+140h+var_118], rax
0x1800c5a9a  lea     rax, [rbp+arg_10]
0x1800c5a9e  mov     [rsp+140h+var_120], rax
0x1800c5aa3  mov     [rbp+arg_10], 0
0x1800c5aab  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800c5ab0  mov     rcx, rbx
0x1800c5ab3  add     rsp, 130h
0x1800c5aba  pop     rdi
0x1800c5abb  pop     rbx
0x1800c5abc  pop     rbp
0x1800c5abd  jmp     ?IgnoreCurrentThread@?$ActivityBase@VCortanaSearchTelemetryLogging@@$00$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CortanaSearchTelemetryLogging,1,1,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
