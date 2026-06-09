# Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingsTelemetry::AgentActivationSettingManagerInitialize::StopActivity(void)

- ea: `0x140023200`
- end: `0x14002342f`
- name: `?StopActivity@AgentActivationSettingManagerInitialize@AgentActivationSettingsTelemetry@Settings@Windows@VoiceAgentServices@Microsoft@@MEAAXXZ`
- size: `559`
- prototype: `void __fastcall(Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingsTelemetry::AgentActivationSettingManagerInitialize *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1400017dc`
- `0x140001b28`
- `0x14000c224`
- `0x140011588`
- `0x140022d54`
- `0x140023200`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400233cd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400233cd`

## pseudocode

```c
void __fastcall Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingsTelemetry::AgentActivationSettingManagerInitialize::StopActivity(
        Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingsTelemetry::AgentActivationSettingManagerInitialize *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  const struct _tlgProvider_t *v5; // rax
  __int64 v6; // rcx
  __int64 v7; // r8
  const struct _tlgProvider_t *v8; // rax
  int v9; // edi
  DWORD CurrentThreadId; // eax
  __int64 v11; // r8
  int v12; // [rsp+C0h] [rbp-80h] BYREF
  int v13; // [rsp+C4h] [rbp-7Ch] BYREF
  int v14; // [rsp+C8h] [rbp-78h] BYREF
  int v15; // [rsp+CCh] [rbp-74h] BYREF
  __int64 v16; // [rsp+D0h] [rbp-70h] BYREF
  __int64 v17; // [rsp+D8h] [rbp-68h] BYREF
  __int64 v18; // [rsp+E0h] [rbp-60h] BYREF
  __int64 v19; // [rsp+E8h] [rbp-58h] BYREF
  __int64 v20; // [rsp+F0h] [rbp-50h] BYREF
  __int64 v21; // [rsp+F8h] [rbp-48h] BYREF
  __int64 v22; // [rsp+100h] [rbp-40h] BYREF
  __int64 v23; // [rsp+108h] [rbp-38h] BYREF
  __int64 v24; // [rsp+110h] [rbp-30h] BYREF
  __int64 v25; // [rsp+118h] [rbp-28h] BYREF
  _QWORD v26[4]; // [rsp+120h] [rbp-20h] BYREF
  DWORD v27; // [rsp+150h] [rbp+10h] BYREF
  int v28; // [rsp+158h] [rbp+18h] BYREF
  __int64 v29; // [rsp+160h] [rbp+20h] BYREF
  int v30; // [rsp+168h] [rbp+28h] BYREF

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = (int *)(v1 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<FlightDataRecorderActivityClass,0,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v5 = Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingsProvider::Provider();
    if ( *(_DWORD *)v5 > 5u )
    {
      v6 = *((_QWORD *)v4 + 6);
      v18 = *((_QWORD *)v4 + 14);
      v7 = *((_QWORD *)this + 34);
      LODWORD(v29) = v4[26];
      v19 = *((_QWORD *)v4 + 12);
      v20 = *((_QWORD *)v4 + 11);
      v30 = v4[20];
      v21 = *((_QWORD *)v4 + 9);
      v12 = v4[8];
      v22 = *((_QWORD *)v4 + 3);
      v13 = *v4;
      v23 = *((_QWORD *)v4 + 16);
      v14 = v4[16];
      v24 = *((_QWORD *)v4 + 7);
      v15 = v4[2];
      v16 = v6;
      v27 = v4[17];
      v28 = v4[4];
      v17 = *((_QWORD *)v4 + 15);
      v25 = 0x1000000;
      v26[0] = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (_DWORD)v5,
        (unsigned int)&word_140043B26,
        v7 + 8,
        (_DWORD)v5,
        (__int64)v26,
        (__int64)&v25,
        (__int64)&v15,
        (__int64)&v24,
        (__int64)&v14,
        (__int64)&v23,
        (__int64)&v13,
        (__int64)&v22,
        (__int64)&v12,
        (__int64)&v21,
        (__int64)&v30,
        (__int64)&v20,
        (__int64)&v19,
        (__int64)&v29,
        (__int64)&v18,
        (__int64)&v17,
        (__int64)&v28,
        (__int64)&v27,
        (__int64)&v16);
    }
  }
  else
  {
    wil::ActivityBase<FlightDataRecorderActivityClass,0,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v8 = Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingsProvider::Provider();
    v9 = (int)v8;
    if ( *(_DWORD *)v8 > 5u )
    {
      CurrentThreadId = GetCurrentThreadId();
      v11 = *((_QWORD *)this + 34);
      v27 = CurrentThreadId;
      v28 = *(_DWORD *)(v11 + 72);
      v29 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v9,
        (unsigned int)&unk_140043C88,
        v11 + 8,
        0,
        (__int64)&v29,
        (__int64)&v28,
        (__int64)&v27);
    }
  }
  wil::ActivityBase<FlightDataRecorderActivityClass,0,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(this);
}

```

## disassembly

```asm
0x140023200  push    rbp
0x140023202  push    rbx
0x140023203  push    rdi
0x140023204  lea     rbp, [rsp+10h]
0x140023209  sub     rsp, 130h
0x140023210  mov     rdi, [rcx+110h]
0x140023217  mov     rbx, rcx
0x14002321a  mov     eax, [rdi+48h]
0x14002321d  test    eax, eax
0x14002321f  jns     loc_1400233B9
0x140023225  add     rdi, 50h ; 'P'
0x140023229  cmp     eax, [rdi+8]
0x14002322c  jnz     loc_1400233B9
0x140023232  test    rdi, rdi
0x140023235  jz      loc_1400233B9
0x14002323b  call    ?zInternalStop@?$ActivityBase@VFlightDataRecorderActivityClass@@$0A@$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<FlightDataRecorderActivityClass,0,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x140023240  call    ?Provider@AgentActivationSettingsProvider@Settings@Windows@VoiceAgentServices@Microsoft@@SAPEBU_tlgProvider_t@@XZ; Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingsProvider::Provider(void)
0x140023245  mov     r9, rax
0x140023248  mov     ecx, [rax]
0x14002324a  cmp     ecx, 5
0x14002324d  jbe     loc_14002341D
0x140023253  mov     rax, [rdi+70h]
0x140023257  lea     rdx, word_140043B26
0x14002325e  mov     rcx, [rdi+30h]
0x140023262  mov     [rbp+var_60], rax
0x140023266  mov     eax, [rdi+68h]
0x140023269  mov     r8, [rbx+110h]
0x140023270  mov     dword ptr [rbp+arg_10], eax
0x140023273  add     r8, 8
0x140023277  mov     rax, [rdi+60h]
0x14002327b  mov     [rbp+var_58], rax
0x14002327f  mov     rax, [rdi+58h]
0x140023283  mov     [rbp+var_50], rax
0x140023287  mov     eax, [rdi+50h]
0x14002328a  mov     [rbp+arg_18], eax
0x14002328d  mov     rax, [rdi+48h]
0x140023291  mov     [rbp+var_48], rax
0x140023295  mov     eax, [rdi+20h]
0x140023298  mov     [rbp+var_80], eax
0x14002329b  mov     rax, [rdi+18h]
0x14002329f  mov     [rbp+var_40], rax
0x1400232a3  mov     eax, [rdi]
0x1400232a5  mov     [rbp+var_7C], eax
0x1400232a8  mov     rax, [rdi+80h]
0x1400232af  mov     [rbp+var_38], rax
0x1400232b3  mov     eax, [rdi+40h]
0x1400232b6  mov     [rbp+var_78], eax
0x1400232b9  mov     rax, [rdi+38h]
0x1400232bd  mov     [rbp+var_30], rax
0x1400232c1  mov     eax, [rdi+8]
0x1400232c4  mov     [rbp+var_74], eax
0x1400232c7  lea     rax, [rbp+var_70]
0x1400232cb  mov     [rsp+140h+var_90], rax
0x1400232d3  lea     rax, [rbp+arg_0]
0x1400232d7  mov     [rsp+140h+var_98], rax
0x1400232df  lea     rax, [rbp+arg_8]
0x1400232e3  mov     [rsp+140h+var_A0], rax
0x1400232eb  lea     rax, [rbp+var_68]
0x1400232ef  mov     [rsp+140h+var_A8], rax
0x1400232f7  lea     rax, [rbp+var_60]
0x1400232fb  mov     [rsp+140h+var_B0], rax
0x140023303  lea     rax, [rbp+arg_10]
0x140023307  mov     [rsp+140h+var_B8], rax
0x14002330f  lea     rax, [rbp+var_58]
0x140023313  mov     [rsp+140h+var_C0], rax
0x14002331b  lea     rax, [rbp+var_50]
0x14002331f  mov     [rsp+140h+var_C8], rax
0x140023324  lea     rax, [rbp+arg_18]
0x140023328  mov     [rsp+140h+var_D0], rax
0x14002332d  lea     rax, [rbp+var_48]
0x140023331  mov     [rsp+140h+var_D8], rax
0x140023336  lea     rax, [rbp+var_80]
0x14002333a  mov     [rsp+140h+var_E0], rax
0x14002333f  lea     rax, [rbp+var_40]
0x140023343  mov     [rsp+140h+var_E8], rax
0x140023348  lea     rax, [rbp+var_7C]
0x14002334c  mov     [rsp+140h+var_F0], rax
0x140023351  lea     rax, [rbp+var_38]
0x140023355  mov     [rsp+140h+var_F8], rax
0x14002335a  lea     rax, [rbp+var_78]
0x14002335e  mov     [rsp+140h+var_100], rax
0x140023363  lea     rax, [rbp+var_30]
0x140023367  mov     [rsp+140h+var_108], rax
0x14002336c  lea     rax, [rbp+var_74]
0x140023370  mov     [rbp+var_70], rcx
0x140023374  mov     ecx, [rdi+44h]
0x140023377  mov     [rsp+140h+var_110], rax
0x14002337c  lea     rax, [rbp+var_28]
0x140023380  mov     [rbp+arg_0], ecx
0x140023383  mov     ecx, [rdi+10h]
0x140023386  mov     [rbp+arg_8], ecx
0x140023389  mov     rcx, [rdi+78h]
0x14002338d  mov     [rsp+140h+var_118], rax
0x140023392  lea     rax, [rbp+var_20]
0x140023396  mov     [rbp+var_68], rcx
0x14002339a  mov     rcx, r9
0x14002339d  mov     [rsp+140h+var_120], rax
0x1400233a2  mov     [rbp+var_28], 1000000h
0x1400233aa  mov     [rbp+var_20], 0
0x1400233b2  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1400233b7  jmp     short loc_14002341D
0x1400233b9  call    ?zInternalStop@?$ActivityBase@VFlightDataRecorderActivityClass@@$0A@$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<FlightDataRecorderActivityClass,0,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x1400233be  call    ?Provider@AgentActivationSettingsProvider@Settings@Windows@VoiceAgentServices@Microsoft@@SAPEBU_tlgProvider_t@@XZ; Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingsProvider::Provider(void)
0x1400233c3  mov     rdi, rax
0x1400233c6  mov     ecx, [rax]
0x1400233c8  cmp     ecx, 5
0x1400233cb  jbe     short loc_14002341D
0x1400233cd  call    cs:__imp_GetCurrentThreadId
0x1400233d3  mov     r8, [rbx+110h]
0x1400233da  lea     rdx, unk_140043C88
0x1400233e1  mov     [rbp+arg_0], eax
0x1400233e4  xor     r9d, r9d
0x1400233e7  lea     rax, [rbp+arg_0]
0x1400233eb  mov     [rsp+140h+var_110], rax
0x1400233f0  lea     rax, [rbp+arg_8]
0x1400233f4  mov     ecx, [r8+48h]
0x1400233f8  add     r8, 8
0x1400233fc  mov     [rsp+140h+var_118], rax
0x140023401  lea     rax, [rbp+arg_10]
0x140023405  mov     [rbp+arg_8], ecx
0x140023408  mov     rcx, rdi
0x14002340b  mov     [rsp+140h+var_120], rax
0x140023410  mov     [rbp+arg_10], 0
0x140023418  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14002341d  mov     rcx, rbx
0x140023420  add     rsp, 130h
0x140023427  pop     rdi
0x140023428  pop     rbx
0x140023429  pop     rbp
0x14002342a  jmp     ?IgnoreCurrentThread@?$ActivityBase@VFlightDataRecorderActivityClass@@$0A@$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<FlightDataRecorderActivityClass,0,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
