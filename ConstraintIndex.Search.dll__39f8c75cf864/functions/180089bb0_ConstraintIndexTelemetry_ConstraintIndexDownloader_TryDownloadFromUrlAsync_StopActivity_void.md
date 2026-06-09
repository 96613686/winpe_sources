# ConstraintIndexTelemetry::ConstraintIndexDownloader_TryDownloadFromUrlAsync::StopActivity(void)

- ea: `0x180089bb0`
- end: `0x180089e02`
- name: `?StopActivity@ConstraintIndexDownloader_TryDownloadFromUrlAsync@ConstraintIndexTelemetry@@MEAAXXZ`
- size: `594`
- prototype: `void __fastcall(ConstraintIndexTelemetry::ConstraintIndexDownloader_TryDownloadFromUrlAsync *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180001314`
- `0x1800019ec`
- `0x18000243c`
- `0x18003bf74`
- `0x18003c9b8`
- `0x180040bb8`
- `0x180089bb0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180089da3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180089da3`

## pseudocode

```c
void __fastcall ConstraintIndexTelemetry::ConstraintIndexDownloader_TryDownloadFromUrlAsync::StopActivity(
        ConstraintIndexTelemetry::ConstraintIndexDownloader_TryDownloadFromUrlAsync *this)
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
        (int)&unk_180112A08,
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
        (unsigned int)&dword_180112B74,
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
0x180089bb0  push    rbp
0x180089bb2  push    rbx
0x180089bb3  push    rdi
0x180089bb4  lea     rbp, [rsp+10h]
0x180089bb9  sub     rsp, 130h
0x180089bc0  mov     rdi, [rcx+110h]
0x180089bc7  mov     rbx, rcx
0x180089bca  mov     eax, [rdi+48h]
0x180089bcd  test    eax, eax
0x180089bcf  jns     loc_180089D7E
0x180089bd5  add     rdi, 50h ; 'P'
0x180089bd9  cmp     eax, [rdi+8]
0x180089bdc  jnz     loc_180089D7E
0x180089be2  test    rdi, rdi
0x180089be5  jz      loc_180089D7E
0x180089beb  call    ?zInternalStop@?$ActivityBase@VCortanaSearchTelemetryLogging@@$00$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CortanaSearchTelemetryLogging,1,1,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180089bf0  call    ?Provider@CortanaSearchTelemetryLogging@@SAPEBU_tlgProvider_t@@XZ; CortanaSearchTelemetryLogging::Provider(void)
0x180089bf5  mov     r9, rax
0x180089bf8  mov     ecx, [rax]
0x180089bfa  cmp     ecx, 5
0x180089bfd  jbe     loc_180089DF0
0x180089c03  mov     edx, 1
0x180089c08  mov     rcx, rax
0x180089c0b  call    _tlgKeywordOn
0x180089c10  test    al, al
0x180089c12  jz      loc_180089DF0
0x180089c18  mov     rax, [rdi+30h]
0x180089c1c  lea     rdx, unk_180112A08; int
0x180089c23  mov     [rbp+var_70], rax
0x180089c27  mov     rcx, r9; int
0x180089c2a  mov     eax, [rdi+44h]
0x180089c2d  mov     dword ptr [rbp+arg_0], eax
0x180089c30  mov     eax, [rdi+10h]
0x180089c33  mov     dword ptr [rbp+arg_8], eax
0x180089c36  mov     rax, [rdi+78h]
0x180089c3a  mov     [rbp+var_68], rax
0x180089c3e  mov     rax, [rdi+70h]
0x180089c42  mov     [rbp+var_60], rax
0x180089c46  mov     eax, [rdi+68h]
0x180089c49  mov     r8, [rbx+110h]
0x180089c50  mov     dword ptr [rbp+arg_10], eax
0x180089c53  add     r8, 8; int
0x180089c57  mov     rax, [rdi+60h]
0x180089c5b  mov     [rbp+var_58], rax
0x180089c5f  mov     rax, [rdi+58h]
0x180089c63  mov     [rbp+var_50], rax
0x180089c67  mov     eax, [rdi+50h]
0x180089c6a  mov     dword ptr [rbp+arg_18], eax
0x180089c6d  mov     rax, [rdi+48h]
0x180089c71  mov     [rbp+var_48], rax
0x180089c75  mov     eax, [rdi+20h]
0x180089c78  mov     dword ptr [rbp+var_80], eax
0x180089c7b  mov     rax, [rdi+18h]
0x180089c7f  mov     [rbp+var_40], rax
0x180089c83  mov     eax, [rdi]
0x180089c85  mov     dword ptr [rbp+var_80+4], eax
0x180089c88  mov     rax, [rdi+80h]
0x180089c8f  mov     [rbp+var_38], rax
0x180089c93  mov     eax, [rdi+40h]
0x180089c96  mov     dword ptr [rbp+var_78], eax
0x180089c99  mov     rax, [rdi+38h]
0x180089c9d  mov     [rbp+var_30], rax
0x180089ca1  mov     eax, [rdi+8]
0x180089ca4  mov     dword ptr [rbp+var_78+4], eax
0x180089ca7  lea     rax, [rbp+var_70]
0x180089cab  mov     [rsp+140h+var_90], rax; __int64
0x180089cb3  lea     rax, [rbp+arg_0]
0x180089cb7  mov     [rsp+140h+var_98], rax; __int64
0x180089cbf  lea     rax, [rbp+arg_8]
0x180089cc3  mov     [rsp+140h+var_A0], rax; __int64
0x180089ccb  lea     rax, [rbp+var_68]
0x180089ccf  mov     [rsp+140h+var_A8], rax; __int64
0x180089cd7  lea     rax, [rbp+var_60]
0x180089cdb  mov     [rsp+140h+var_B0], rax; __int64
0x180089ce3  lea     rax, [rbp+arg_10]
0x180089ce7  mov     [rsp+140h+var_B8], rax; __int64
0x180089cef  lea     rax, [rbp+var_58]
0x180089cf3  mov     [rsp+140h+var_C0], rax; __int64
0x180089cfb  lea     rax, [rbp+var_50]
0x180089cff  mov     [rsp+140h+var_C8], rax; __int64
0x180089d04  lea     rax, [rbp+arg_18]
0x180089d08  mov     [rsp+140h+var_D0], rax; __int64
0x180089d0d  lea     rax, [rbp+var_48]
0x180089d11  mov     [rsp+140h+var_D8], rax; __int64
0x180089d16  lea     rax, [rbp+var_80]
0x180089d1a  mov     [rsp+140h+var_E0], rax; __int64
0x180089d1f  lea     rax, [rbp+var_40]
0x180089d23  mov     [rsp+140h+var_E8], rax; __int64
0x180089d28  lea     rax, [rbp+var_80+4]
0x180089d2c  mov     [rsp+140h+var_F0], rax; __int64
0x180089d31  lea     rax, [rbp+var_38]
0x180089d35  mov     [rsp+140h+var_F8], rax; __int64
0x180089d3a  lea     rax, [rbp+var_78]
0x180089d3e  mov     [rsp+140h+var_100], rax; __int64
0x180089d43  lea     rax, [rbp+var_30]
0x180089d47  mov     [rsp+140h+var_108], rax; __int64
0x180089d4c  lea     rax, [rbp+var_78+4]
0x180089d50  mov     [rsp+140h+var_110], rax; __int64
0x180089d55  lea     rax, [rbp+var_28]
0x180089d59  mov     [rsp+140h+var_118], rax; __int64
0x180089d5e  lea     rax, [rbp+var_20]
0x180089d62  mov     [rsp+140h+var_120], rax; __int64
0x180089d67  mov     [rbp+var_28], 1000000h
0x180089d6f  mov     [rbp+var_20], 0
0x180089d77  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@_W@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@_W@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180089d7c  jmp     short loc_180089DF0
0x180089d7e  call    ?zInternalStop@?$ActivityBase@VCortanaSearchTelemetryLogging@@$00$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CortanaSearchTelemetryLogging,1,1,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180089d83  call    ?Provider@CortanaSearchTelemetryLogging@@SAPEBU_tlgProvider_t@@XZ; CortanaSearchTelemetryLogging::Provider(void)
0x180089d88  mov     rdi, rax
0x180089d8b  mov     ecx, [rax]
0x180089d8d  cmp     ecx, 5
0x180089d90  jbe     short loc_180089DF0
0x180089d92  mov     edx, 1
0x180089d97  mov     rcx, rax
0x180089d9a  call    _tlgKeywordOn
0x180089d9f  test    al, al
0x180089da1  jz      short loc_180089DF0
0x180089da3  call    cs:__imp_GetCurrentThreadId
0x180089da9  mov     r8, [rbx+110h]
0x180089db0  lea     rdx, dword_180112B74
0x180089db7  mov     dword ptr [rbp+arg_0], eax
0x180089dba  mov     rcx, rdi
0x180089dbd  mov     eax, [r8+48h]
0x180089dc1  add     r8, 8
0x180089dc5  mov     dword ptr [rbp+arg_8], eax
0x180089dc8  lea     rax, [rbp+arg_0]
0x180089dcc  mov     [rsp+140h+var_110], rax
0x180089dd1  lea     rax, [rbp+arg_8]
0x180089dd5  mov     [rsp+140h+var_118], rax
0x180089dda  lea     rax, [rbp+arg_10]
0x180089dde  mov     [rsp+140h+var_120], rax
0x180089de3  mov     [rbp+arg_10], 0
0x180089deb  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180089df0  mov     rcx, rbx
0x180089df3  add     rsp, 130h
0x180089dfa  pop     rdi
0x180089dfb  pop     rbx
0x180089dfc  pop     rbp
0x180089dfd  jmp     ?IgnoreCurrentThread@?$ActivityBase@VCortanaSearchTelemetryLogging@@$00$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CortanaSearchTelemetryLogging,1,1,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
