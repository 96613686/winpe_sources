# ConstraintIndexTelemetry::SettingsFilterCacheManager_FilterDeviceItems::StopActivity(void)

- ea: `0x1800c5150`
- end: `0x1800c53a2`
- name: `?StopActivity@SettingsFilterCacheManager_FilterDeviceItems@ConstraintIndexTelemetry@@MEAAXXZ`
- size: `594`
- prototype: `void __fastcall(ConstraintIndexTelemetry::SettingsFilterCacheManager_FilterDeviceItems *__hidden this)`
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
- `0x1800c5150`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800c5343`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800c5343`

## pseudocode

```c
void __fastcall ConstraintIndexTelemetry::SettingsFilterCacheManager_FilterDeviceItems::StopActivity(
        ConstraintIndexTelemetry::SettingsFilterCacheManager_FilterDeviceItems *this)
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
        (int)&byte_18011461D,
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
        (unsigned int)&unk_1801145B0,
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
0x1800c5150  push    rbp
0x1800c5152  push    rbx
0x1800c5153  push    rdi
0x1800c5154  lea     rbp, [rsp+10h]
0x1800c5159  sub     rsp, 130h
0x1800c5160  mov     rdi, [rcx+110h]
0x1800c5167  mov     rbx, rcx
0x1800c516a  mov     eax, [rdi+48h]
0x1800c516d  test    eax, eax
0x1800c516f  jns     loc_1800C531E
0x1800c5175  add     rdi, 50h ; 'P'
0x1800c5179  cmp     eax, [rdi+8]
0x1800c517c  jnz     loc_1800C531E
0x1800c5182  test    rdi, rdi
0x1800c5185  jz      loc_1800C531E
0x1800c518b  call    ?zInternalStop@?$ActivityBase@VCortanaSearchTelemetryLogging@@$00$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CortanaSearchTelemetryLogging,1,1,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x1800c5190  call    ?Provider@CortanaSearchTelemetryLogging@@SAPEBU_tlgProvider_t@@XZ; CortanaSearchTelemetryLogging::Provider(void)
0x1800c5195  mov     r9, rax
0x1800c5198  mov     ecx, [rax]
0x1800c519a  cmp     ecx, 5
0x1800c519d  jbe     loc_1800C5390
0x1800c51a3  mov     edx, 1
0x1800c51a8  mov     rcx, rax
0x1800c51ab  call    _tlgKeywordOn
0x1800c51b0  test    al, al
0x1800c51b2  jz      loc_1800C5390
0x1800c51b8  mov     rax, [rdi+30h]
0x1800c51bc  lea     rdx, byte_18011461D; int
0x1800c51c3  mov     [rbp+var_70], rax
0x1800c51c7  mov     rcx, r9; int
0x1800c51ca  mov     eax, [rdi+44h]
0x1800c51cd  mov     dword ptr [rbp+arg_0], eax
0x1800c51d0  mov     eax, [rdi+10h]
0x1800c51d3  mov     dword ptr [rbp+arg_8], eax
0x1800c51d6  mov     rax, [rdi+78h]
0x1800c51da  mov     [rbp+var_68], rax
0x1800c51de  mov     rax, [rdi+70h]
0x1800c51e2  mov     [rbp+var_60], rax
0x1800c51e6  mov     eax, [rdi+68h]
0x1800c51e9  mov     r8, [rbx+110h]
0x1800c51f0  mov     dword ptr [rbp+arg_10], eax
0x1800c51f3  add     r8, 8; int
0x1800c51f7  mov     rax, [rdi+60h]
0x1800c51fb  mov     [rbp+var_58], rax
0x1800c51ff  mov     rax, [rdi+58h]
0x1800c5203  mov     [rbp+var_50], rax
0x1800c5207  mov     eax, [rdi+50h]
0x1800c520a  mov     dword ptr [rbp+arg_18], eax
0x1800c520d  mov     rax, [rdi+48h]
0x1800c5211  mov     [rbp+var_48], rax
0x1800c5215  mov     eax, [rdi+20h]
0x1800c5218  mov     dword ptr [rbp+var_80], eax
0x1800c521b  mov     rax, [rdi+18h]
0x1800c521f  mov     [rbp+var_40], rax
0x1800c5223  mov     eax, [rdi]
0x1800c5225  mov     dword ptr [rbp+var_80+4], eax
0x1800c5228  mov     rax, [rdi+80h]
0x1800c522f  mov     [rbp+var_38], rax
0x1800c5233  mov     eax, [rdi+40h]
0x1800c5236  mov     dword ptr [rbp+var_78], eax
0x1800c5239  mov     rax, [rdi+38h]
0x1800c523d  mov     [rbp+var_30], rax
0x1800c5241  mov     eax, [rdi+8]
0x1800c5244  mov     dword ptr [rbp+var_78+4], eax
0x1800c5247  lea     rax, [rbp+var_70]
0x1800c524b  mov     [rsp+140h+var_90], rax; __int64
0x1800c5253  lea     rax, [rbp+arg_0]
0x1800c5257  mov     [rsp+140h+var_98], rax; __int64
0x1800c525f  lea     rax, [rbp+arg_8]
0x1800c5263  mov     [rsp+140h+var_A0], rax; __int64
0x1800c526b  lea     rax, [rbp+var_68]
0x1800c526f  mov     [rsp+140h+var_A8], rax; __int64
0x1800c5277  lea     rax, [rbp+var_60]
0x1800c527b  mov     [rsp+140h+var_B0], rax; __int64
0x1800c5283  lea     rax, [rbp+arg_10]
0x1800c5287  mov     [rsp+140h+var_B8], rax; __int64
0x1800c528f  lea     rax, [rbp+var_58]
0x1800c5293  mov     [rsp+140h+var_C0], rax; __int64
0x1800c529b  lea     rax, [rbp+var_50]
0x1800c529f  mov     [rsp+140h+var_C8], rax; __int64
0x1800c52a4  lea     rax, [rbp+arg_18]
0x1800c52a8  mov     [rsp+140h+var_D0], rax; __int64
0x1800c52ad  lea     rax, [rbp+var_48]
0x1800c52b1  mov     [rsp+140h+var_D8], rax; __int64
0x1800c52b6  lea     rax, [rbp+var_80]
0x1800c52ba  mov     [rsp+140h+var_E0], rax; __int64
0x1800c52bf  lea     rax, [rbp+var_40]
0x1800c52c3  mov     [rsp+140h+var_E8], rax; __int64
0x1800c52c8  lea     rax, [rbp+var_80+4]
0x1800c52cc  mov     [rsp+140h+var_F0], rax; __int64
0x1800c52d1  lea     rax, [rbp+var_38]
0x1800c52d5  mov     [rsp+140h+var_F8], rax; __int64
0x1800c52da  lea     rax, [rbp+var_78]
0x1800c52de  mov     [rsp+140h+var_100], rax; __int64
0x1800c52e3  lea     rax, [rbp+var_30]
0x1800c52e7  mov     [rsp+140h+var_108], rax; __int64
0x1800c52ec  lea     rax, [rbp+var_78+4]
0x1800c52f0  mov     [rsp+140h+var_110], rax; __int64
0x1800c52f5  lea     rax, [rbp+var_28]
0x1800c52f9  mov     [rsp+140h+var_118], rax; __int64
0x1800c52fe  lea     rax, [rbp+var_20]
0x1800c5302  mov     [rsp+140h+var_120], rax; __int64
0x1800c5307  mov     [rbp+var_28], 1000000h
0x1800c530f  mov     [rbp+var_20], 0
0x1800c5317  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@_W@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@_W@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800c531c  jmp     short loc_1800C5390
0x1800c531e  call    ?zInternalStop@?$ActivityBase@VCortanaSearchTelemetryLogging@@$00$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CortanaSearchTelemetryLogging,1,1,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x1800c5323  call    ?Provider@CortanaSearchTelemetryLogging@@SAPEBU_tlgProvider_t@@XZ; CortanaSearchTelemetryLogging::Provider(void)
0x1800c5328  mov     rdi, rax
0x1800c532b  mov     ecx, [rax]
0x1800c532d  cmp     ecx, 5
0x1800c5330  jbe     short loc_1800C5390
0x1800c5332  mov     edx, 1
0x1800c5337  mov     rcx, rax
0x1800c533a  call    _tlgKeywordOn
0x1800c533f  test    al, al
0x1800c5341  jz      short loc_1800C5390
0x1800c5343  call    cs:__imp_GetCurrentThreadId
0x1800c5349  mov     r8, [rbx+110h]
0x1800c5350  lea     rdx, unk_1801145B0
0x1800c5357  mov     dword ptr [rbp+arg_0], eax
0x1800c535a  mov     rcx, rdi
0x1800c535d  mov     eax, [r8+48h]
0x1800c5361  add     r8, 8
0x1800c5365  mov     dword ptr [rbp+arg_8], eax
0x1800c5368  lea     rax, [rbp+arg_0]
0x1800c536c  mov     [rsp+140h+var_110], rax
0x1800c5371  lea     rax, [rbp+arg_8]
0x1800c5375  mov     [rsp+140h+var_118], rax
0x1800c537a  lea     rax, [rbp+arg_10]
0x1800c537e  mov     [rsp+140h+var_120], rax
0x1800c5383  mov     [rbp+arg_10], 0
0x1800c538b  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800c5390  mov     rcx, rbx
0x1800c5393  add     rsp, 130h
0x1800c539a  pop     rdi
0x1800c539b  pop     rbx
0x1800c539c  pop     rbp
0x1800c539d  jmp     ?IgnoreCurrentThread@?$ActivityBase@VCortanaSearchTelemetryLogging@@$00$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CortanaSearchTelemetryLogging,1,1,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
