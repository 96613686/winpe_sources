# PowerAndBatteryTelemetry::EnergySaverOverrideQuickAction::StopActivity(void)

- ea: `0x180044410`
- end: `0x180044634`
- name: `?StopActivity@EnergySaverOverrideQuickAction@PowerAndBatteryTelemetry@@MEAAXXZ`
- size: `548`
- prototype: `void __fastcall(PowerAndBatteryTelemetry::EnergySaverOverrideQuickAction *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x180001188`
- `0x1800014ac`
- `0x180001c3c`
- `0x180022e60`
- `0x180025840`
- `0x18002c874`
- `0x180044410`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800445d5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800445d5`

## pseudocode

```c
void __fastcall PowerAndBatteryTelemetry::EnergySaverOverrideQuickAction::StopActivity(
        PowerAndBatteryTelemetry::EnergySaverOverrideQuickAction *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  const struct _tlgProvider_t *v5; // rax
  __int64 v6; // r8
  __int64 v7; // r9
  const WCHAR *v8; // rcx
  __int64 v9; // r8
  const struct _tlgProvider_t *v10; // rax
  __int64 v11; // r8
  __int64 v12; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v14; // r8
  __int64 v15; // r9
  int v16; // [rsp+A0h] [rbp-19h] BYREF
  int v17; // [rsp+A4h] [rbp-15h] BYREF
  const WCHAR *v18; // [rsp+A8h] [rbp-11h] BYREF
  const unsigned __int16 *v19; // [rsp+B0h] [rbp-9h] BYREF
  const WCHAR *v20; // [rsp+B8h] [rbp-1h] BYREF
  const unsigned __int16 *v21; // [rsp+C0h] [rbp+7h] BYREF
  const unsigned __int16 *v22; // [rsp+C8h] [rbp+Fh] BYREF
  const WCHAR *v23; // [rsp+D0h] [rbp+17h] BYREF
  const unsigned __int16 *v24; // [rsp+D8h] [rbp+1Fh] BYREF
  const unsigned __int16 *v25; // [rsp+E0h] [rbp+27h] BYREF
  __int64 v26; // [rsp+E8h] [rbp+2Fh] BYREF
  _QWORD v27[4]; // [rsp+F0h] [rbp+37h] BYREF
  DWORD v28; // [rsp+120h] [rbp+67h] BYREF
  int v29; // [rsp+128h] [rbp+6Fh] BYREF
  __int64 v30; // [rsp+130h] [rbp+77h] BYREF
  int v31; // [rsp+138h] [rbp+7Fh] BYREF

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = (int *)(v1 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<PowerAndBatteryLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v5 = PowerAndBatteryLoggingProvider::Provider();
    if ( *(_DWORD *)v5 > 5u && (unsigned __int8)tlgKeywordOn(v5, 0x400000000000LL, v6) )
    {
      v8 = (const WCHAR *)*((_QWORD *)v4 + 15);
      v9 = *((_QWORD *)this + 34);
      v19 = (const unsigned __int16 *)*((_QWORD *)v4 + 14);
      v28 = v4[26];
      v20 = (const WCHAR *)*((_QWORD *)v4 + 12);
      v21 = (const unsigned __int16 *)*((_QWORD *)v4 + 11);
      v29 = v4[20];
      v22 = (const unsigned __int16 *)*((_QWORD *)v4 + 9);
      LODWORD(v30) = v4[8];
      v23 = (const WCHAR *)*((_QWORD *)v4 + 3);
      v31 = *v4;
      v24 = (const unsigned __int16 *)*((_QWORD *)v4 + 16);
      v16 = v4[16];
      v25 = (const unsigned __int16 *)*((_QWORD *)v4 + 7);
      v17 = v4[2];
      v18 = v8;
      v26 = 0x1000000;
      v27[0] = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        v7,
        (__int64)&dword_18005AFD4,
        v9 + 8,
        v7,
        (__int64)v27,
        (__int64)&v26,
        (__int64)&v17,
        &v25,
        (__int64)&v16,
        &v24,
        (__int64)&v31,
        &v23,
        (__int64)&v30,
        &v22,
        (__int64)&v29,
        &v21,
        &v20,
        (__int64)&v28,
        &v19,
        &v18);
    }
  }
  else
  {
    wil::ActivityBase<PowerAndBatteryLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v10 = PowerAndBatteryLoggingProvider::Provider();
    v12 = (__int64)v10;
    if ( *(_DWORD *)v10 > 5u && (unsigned __int8)tlgKeywordOn(v10, 0x400000000000LL, v11) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v14 = *((_QWORD *)this + 34);
      v28 = CurrentThreadId;
      v29 = *(_DWORD *)(v14 + 72);
      v30 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v12,
        (__int64)word_18005B10A,
        v14 + 8,
        v15,
        (__int64)&v30,
        (__int64)&v29,
        (__int64)&v28);
    }
  }
  wil::ActivityBase<PowerAndBatteryLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(this);
}

```

## disassembly

```asm
0x180044410  push    rbp
0x180044412  push    rbx
0x180044413  push    rdi
0x180044414  lea     rbp, [rsp-47h]
0x180044419  sub     rsp, 100h
0x180044420  mov     rdi, [rcx+110h]
0x180044427  mov     rbx, rcx
0x18004442a  mov     eax, [rdi+48h]
0x18004442d  test    eax, eax
0x18004442f  jns     loc_1800445AB
0x180044435  add     rdi, 50h ; 'P'
0x180044439  cmp     eax, [rdi+8]
0x18004443c  jnz     loc_1800445AB
0x180044442  test    rdi, rdi
0x180044445  jz      loc_1800445AB
0x18004444b  call    ?zInternalStop@?$ActivityBase@VPowerAndBatteryLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<PowerAndBatteryLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180044450  call    ?Provider@PowerAndBatteryLoggingProvider@@SAPEBU_tlgProvider_t@@XZ; PowerAndBatteryLoggingProvider::Provider(void)
0x180044455  mov     r9, rax
0x180044458  mov     ecx, [rax]
0x18004445a  cmp     ecx, 5
0x18004445d  jbe     loc_180044622
0x180044463  mov     rdx, 400000000000h
0x18004446d  mov     rcx, rax
0x180044470  call    _tlgKeywordOn
0x180044475  test    al, al
0x180044477  jz      loc_180044622
0x18004447d  mov     rax, [rdi+70h]
0x180044481  lea     rdx, dword_18005AFD4
0x180044488  mov     rcx, [rdi+78h]
0x18004448c  mov     r8, [rbx+110h]
0x180044493  mov     [rbp+57h+var_60], rax
0x180044497  add     r8, 8
0x18004449b  mov     eax, [rdi+68h]
0x18004449e  mov     [rbp+57h+arg_0], eax
0x1800444a1  mov     rax, [rdi+60h]
0x1800444a5  mov     [rbp+57h+var_58], rax
0x1800444a9  mov     rax, [rdi+58h]
0x1800444ad  mov     [rbp+57h+var_50], rax
0x1800444b1  mov     eax, [rdi+50h]
0x1800444b4  mov     [rbp+57h+arg_8], eax
0x1800444b7  mov     rax, [rdi+48h]
0x1800444bb  mov     [rbp+57h+var_48], rax
0x1800444bf  mov     eax, [rdi+20h]
0x1800444c2  mov     dword ptr [rbp+57h+arg_10], eax
0x1800444c5  mov     rax, [rdi+18h]
0x1800444c9  mov     [rbp+57h+var_40], rax
0x1800444cd  mov     eax, [rdi]
0x1800444cf  mov     [rbp+57h+arg_18], eax
0x1800444d2  mov     rax, [rdi+80h]
0x1800444d9  mov     [rbp+57h+var_38], rax
0x1800444dd  mov     eax, [rdi+40h]
0x1800444e0  mov     [rbp+57h+var_70], eax
0x1800444e3  mov     rax, [rdi+38h]
0x1800444e7  mov     [rbp+57h+var_30], rax
0x1800444eb  mov     eax, [rdi+8]
0x1800444ee  mov     [rbp+57h+var_6C], eax
0x1800444f1  lea     rax, [rbp+57h+var_68]
0x1800444f5  mov     [rsp+110h+var_78], rax
0x1800444fd  lea     rax, [rbp+57h+var_60]
0x180044501  mov     [rsp+110h+var_80], rax
0x180044509  lea     rax, [rbp+57h+arg_0]
0x18004450d  mov     [rsp+110h+var_88], rax
0x180044515  lea     rax, [rbp+57h+var_58]
0x180044519  mov     [rsp+110h+var_90], rax
0x180044521  lea     rax, [rbp+57h+var_50]
0x180044525  mov     [rsp+110h+var_98], rax
0x18004452a  lea     rax, [rbp+57h+arg_8]
0x18004452e  mov     [rsp+110h+var_A0], rax
0x180044533  lea     rax, [rbp+57h+var_48]
0x180044537  mov     [rsp+110h+var_A8], rax
0x18004453c  lea     rax, [rbp+57h+arg_10]
0x180044540  mov     [rsp+110h+var_B0], rax
0x180044545  lea     rax, [rbp+57h+var_40]
0x180044549  mov     [rsp+110h+var_B8], rax
0x18004454e  lea     rax, [rbp+57h+arg_18]
0x180044552  mov     [rsp+110h+var_C0], rax
0x180044557  lea     rax, [rbp+57h+var_38]
0x18004455b  mov     [rsp+110h+var_C8], rax
0x180044560  lea     rax, [rbp+57h+var_70]
0x180044564  mov     [rsp+110h+var_D0], rax
0x180044569  lea     rax, [rbp+57h+var_30]
0x18004456d  mov     [rsp+110h+var_D8], rax
0x180044572  lea     rax, [rbp+57h+var_6C]
0x180044576  mov     [rsp+110h+var_E0], rax
0x18004457b  lea     rax, [rbp+57h+var_28]
0x18004457f  mov     [rsp+110h+var_E8], rax
0x180044584  lea     rax, [rbp+57h+var_20]
0x180044588  mov     [rbp+57h+var_68], rcx
0x18004458c  mov     rcx, r9
0x18004458f  mov     [rsp+110h+var_F0], rax
0x180044594  mov     [rbp+57h+var_28], 1000000h
0x18004459c  mov     [rbp+57h+var_20], 0
0x1800445a4  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x1800445a9  jmp     short loc_180044622
0x1800445ab  call    ?zInternalStop@?$ActivityBase@VPowerAndBatteryLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<PowerAndBatteryLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x1800445b0  call    ?Provider@PowerAndBatteryLoggingProvider@@SAPEBU_tlgProvider_t@@XZ; PowerAndBatteryLoggingProvider::Provider(void)
0x1800445b5  mov     rdi, rax
0x1800445b8  mov     ecx, [rax]
0x1800445ba  cmp     ecx, 5
0x1800445bd  jbe     short loc_180044622
0x1800445bf  mov     rdx, 400000000000h
0x1800445c9  mov     rcx, rax
0x1800445cc  call    _tlgKeywordOn
0x1800445d1  test    al, al
0x1800445d3  jz      short loc_180044622
0x1800445d5  call    cs:__imp_GetCurrentThreadId
0x1800445db  mov     r8, [rbx+110h]
0x1800445e2  lea     rdx, word_18005B10A
0x1800445e9  mov     [rbp+57h+arg_0], eax
0x1800445ec  mov     rcx, rdi
0x1800445ef  mov     eax, [r8+48h]
0x1800445f3  add     r8, 8
0x1800445f7  mov     [rbp+57h+arg_8], eax
0x1800445fa  lea     rax, [rbp+57h+arg_0]
0x1800445fe  mov     [rsp+110h+var_E0], rax
0x180044603  lea     rax, [rbp+57h+arg_8]
0x180044607  mov     [rsp+110h+var_E8], rax
0x18004460c  lea     rax, [rbp+57h+arg_10]
0x180044610  mov     [rsp+110h+var_F0], rax
0x180044615  mov     [rbp+57h+arg_10], 0
0x18004461d  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180044622  mov     rcx, rbx
0x180044625  add     rsp, 100h
0x18004462c  pop     rdi
0x18004462d  pop     rbx
0x18004462e  pop     rbp
0x18004462f  jmp     ?IgnoreCurrentThread@?$ActivityBase@VPowerAndBatteryLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<PowerAndBatteryLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
