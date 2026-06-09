# ConstraintIndexTelemetry::SettingsFilterCacheManager_ReadSettingsCacheFromDiskAsync::StopActivity(void)

- ea: `0x1800c5610`
- end: `0x1800c5862`
- name: `?StopActivity@SettingsFilterCacheManager_ReadSettingsCacheFromDiskAsync@ConstraintIndexTelemetry@@MEAAXXZ`
- size: `594`
- prototype: `void __fastcall(ConstraintIndexTelemetry::SettingsFilterCacheManager_ReadSettingsCacheFromDiskAsync *__hidden this)`
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
- `0x1800c5610`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800c5803`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800c5803`

## pseudocode

```c
void __fastcall ConstraintIndexTelemetry::SettingsFilterCacheManager_ReadSettingsCacheFromDiskAsync::StopActivity(
        ConstraintIndexTelemetry::SettingsFilterCacheManager_ReadSettingsCacheFromDiskAsync *this)
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
        (int)&word_180113DF2,
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
        (unsigned int)&word_180113F66,
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
0x1800c5610  push    rbp
0x1800c5612  push    rbx
0x1800c5613  push    rdi
0x1800c5614  lea     rbp, [rsp+10h]
0x1800c5619  sub     rsp, 130h
0x1800c5620  mov     rdi, [rcx+110h]
0x1800c5627  mov     rbx, rcx
0x1800c562a  mov     eax, [rdi+48h]
0x1800c562d  test    eax, eax
0x1800c562f  jns     loc_1800C57DE
0x1800c5635  add     rdi, 50h ; 'P'
0x1800c5639  cmp     eax, [rdi+8]
0x1800c563c  jnz     loc_1800C57DE
0x1800c5642  test    rdi, rdi
0x1800c5645  jz      loc_1800C57DE
0x1800c564b  call    ?zInternalStop@?$ActivityBase@VCortanaSearchTelemetryLogging@@$00$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CortanaSearchTelemetryLogging,1,1,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x1800c5650  call    ?Provider@CortanaSearchTelemetryLogging@@SAPEBU_tlgProvider_t@@XZ; CortanaSearchTelemetryLogging::Provider(void)
0x1800c5655  mov     r9, rax
0x1800c5658  mov     ecx, [rax]
0x1800c565a  cmp     ecx, 5
0x1800c565d  jbe     loc_1800C5850
0x1800c5663  mov     edx, 1
0x1800c5668  mov     rcx, rax
0x1800c566b  call    _tlgKeywordOn
0x1800c5670  test    al, al
0x1800c5672  jz      loc_1800C5850
0x1800c5678  mov     rax, [rdi+30h]
0x1800c567c  lea     rdx, word_180113DF2; int
0x1800c5683  mov     [rbp+var_70], rax
0x1800c5687  mov     rcx, r9; int
0x1800c568a  mov     eax, [rdi+44h]
0x1800c568d  mov     dword ptr [rbp+arg_0], eax
0x1800c5690  mov     eax, [rdi+10h]
0x1800c5693  mov     dword ptr [rbp+arg_8], eax
0x1800c5696  mov     rax, [rdi+78h]
0x1800c569a  mov     [rbp+var_68], rax
0x1800c569e  mov     rax, [rdi+70h]
0x1800c56a2  mov     [rbp+var_60], rax
0x1800c56a6  mov     eax, [rdi+68h]
0x1800c56a9  mov     r8, [rbx+110h]
0x1800c56b0  mov     dword ptr [rbp+arg_10], eax
0x1800c56b3  add     r8, 8; int
0x1800c56b7  mov     rax, [rdi+60h]
0x1800c56bb  mov     [rbp+var_58], rax
0x1800c56bf  mov     rax, [rdi+58h]
0x1800c56c3  mov     [rbp+var_50], rax
0x1800c56c7  mov     eax, [rdi+50h]
0x1800c56ca  mov     dword ptr [rbp+arg_18], eax
0x1800c56cd  mov     rax, [rdi+48h]
0x1800c56d1  mov     [rbp+var_48], rax
0x1800c56d5  mov     eax, [rdi+20h]
0x1800c56d8  mov     dword ptr [rbp+var_80], eax
0x1800c56db  mov     rax, [rdi+18h]
0x1800c56df  mov     [rbp+var_40], rax
0x1800c56e3  mov     eax, [rdi]
0x1800c56e5  mov     dword ptr [rbp+var_80+4], eax
0x1800c56e8  mov     rax, [rdi+80h]
0x1800c56ef  mov     [rbp+var_38], rax
0x1800c56f3  mov     eax, [rdi+40h]
0x1800c56f6  mov     dword ptr [rbp+var_78], eax
0x1800c56f9  mov     rax, [rdi+38h]
0x1800c56fd  mov     [rbp+var_30], rax
0x1800c5701  mov     eax, [rdi+8]
0x1800c5704  mov     dword ptr [rbp+var_78+4], eax
0x1800c5707  lea     rax, [rbp+var_70]
0x1800c570b  mov     [rsp+140h+var_90], rax; __int64
0x1800c5713  lea     rax, [rbp+arg_0]
0x1800c5717  mov     [rsp+140h+var_98], rax; __int64
0x1800c571f  lea     rax, [rbp+arg_8]
0x1800c5723  mov     [rsp+140h+var_A0], rax; __int64
0x1800c572b  lea     rax, [rbp+var_68]
0x1800c572f  mov     [rsp+140h+var_A8], rax; __int64
0x1800c5737  lea     rax, [rbp+var_60]
0x1800c573b  mov     [rsp+140h+var_B0], rax; __int64
0x1800c5743  lea     rax, [rbp+arg_10]
0x1800c5747  mov     [rsp+140h+var_B8], rax; __int64
0x1800c574f  lea     rax, [rbp+var_58]
0x1800c5753  mov     [rsp+140h+var_C0], rax; __int64
0x1800c575b  lea     rax, [rbp+var_50]
0x1800c575f  mov     [rsp+140h+var_C8], rax; __int64
0x1800c5764  lea     rax, [rbp+arg_18]
0x1800c5768  mov     [rsp+140h+var_D0], rax; __int64
0x1800c576d  lea     rax, [rbp+var_48]
0x1800c5771  mov     [rsp+140h+var_D8], rax; __int64
0x1800c5776  lea     rax, [rbp+var_80]
0x1800c577a  mov     [rsp+140h+var_E0], rax; __int64
0x1800c577f  lea     rax, [rbp+var_40]
0x1800c5783  mov     [rsp+140h+var_E8], rax; __int64
0x1800c5788  lea     rax, [rbp+var_80+4]
0x1800c578c  mov     [rsp+140h+var_F0], rax; __int64
0x1800c5791  lea     rax, [rbp+var_38]
0x1800c5795  mov     [rsp+140h+var_F8], rax; __int64
0x1800c579a  lea     rax, [rbp+var_78]
0x1800c579e  mov     [rsp+140h+var_100], rax; __int64
0x1800c57a3  lea     rax, [rbp+var_30]
0x1800c57a7  mov     [rsp+140h+var_108], rax; __int64
0x1800c57ac  lea     rax, [rbp+var_78+4]
0x1800c57b0  mov     [rsp+140h+var_110], rax; __int64
0x1800c57b5  lea     rax, [rbp+var_28]
0x1800c57b9  mov     [rsp+140h+var_118], rax; __int64
0x1800c57be  lea     rax, [rbp+var_20]
0x1800c57c2  mov     [rsp+140h+var_120], rax; __int64
0x1800c57c7  mov     [rbp+var_28], 1000000h
0x1800c57cf  mov     [rbp+var_20], 0
0x1800c57d7  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@_W@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@_W@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800c57dc  jmp     short loc_1800C5850
0x1800c57de  call    ?zInternalStop@?$ActivityBase@VCortanaSearchTelemetryLogging@@$00$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CortanaSearchTelemetryLogging,1,1,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x1800c57e3  call    ?Provider@CortanaSearchTelemetryLogging@@SAPEBU_tlgProvider_t@@XZ; CortanaSearchTelemetryLogging::Provider(void)
0x1800c57e8  mov     rdi, rax
0x1800c57eb  mov     ecx, [rax]
0x1800c57ed  cmp     ecx, 5
0x1800c57f0  jbe     short loc_1800C5850
0x1800c57f2  mov     edx, 1
0x1800c57f7  mov     rcx, rax
0x1800c57fa  call    _tlgKeywordOn
0x1800c57ff  test    al, al
0x1800c5801  jz      short loc_1800C5850
0x1800c5803  call    cs:__imp_GetCurrentThreadId
0x1800c5809  mov     r8, [rbx+110h]
0x1800c5810  lea     rdx, word_180113F66
0x1800c5817  mov     dword ptr [rbp+arg_0], eax
0x1800c581a  mov     rcx, rdi
0x1800c581d  mov     eax, [r8+48h]
0x1800c5821  add     r8, 8
0x1800c5825  mov     dword ptr [rbp+arg_8], eax
0x1800c5828  lea     rax, [rbp+arg_0]
0x1800c582c  mov     [rsp+140h+var_110], rax
0x1800c5831  lea     rax, [rbp+arg_8]
0x1800c5835  mov     [rsp+140h+var_118], rax
0x1800c583a  lea     rax, [rbp+arg_10]
0x1800c583e  mov     [rsp+140h+var_120], rax
0x1800c5843  mov     [rbp+arg_10], 0
0x1800c584b  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800c5850  mov     rcx, rbx
0x1800c5853  add     rsp, 130h
0x1800c585a  pop     rdi
0x1800c585b  pop     rbx
0x1800c585c  pop     rbp
0x1800c585d  jmp     ?IgnoreCurrentThread@?$ActivityBase@VCortanaSearchTelemetryLogging@@$00$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CortanaSearchTelemetryLogging,1,1,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
