# PowerAndBatteryTelemetry::EnergySaverOverrideAlways::StopActivity(void)

- ea: `0x1800441e0`
- end: `0x180044404`
- name: `?StopActivity@EnergySaverOverrideAlways@PowerAndBatteryTelemetry@@MEAAXXZ`
- size: `548`
- prototype: `void __fastcall(PowerAndBatteryTelemetry::EnergySaverOverrideAlways *__hidden this)`
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
- `0x1800441e0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800443a5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800443a5`

## pseudocode

```c
void __fastcall PowerAndBatteryTelemetry::EnergySaverOverrideAlways::StopActivity(
        PowerAndBatteryTelemetry::EnergySaverOverrideAlways *this)
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
        (__int64)byte_18005B169,
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
        (__int64)word_18005B29A,
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
0x1800441e0  push    rbp
0x1800441e2  push    rbx
0x1800441e3  push    rdi
0x1800441e4  lea     rbp, [rsp-47h]
0x1800441e9  sub     rsp, 100h
0x1800441f0  mov     rdi, [rcx+110h]
0x1800441f7  mov     rbx, rcx
0x1800441fa  mov     eax, [rdi+48h]
0x1800441fd  test    eax, eax
0x1800441ff  jns     loc_18004437B
0x180044205  add     rdi, 50h ; 'P'
0x180044209  cmp     eax, [rdi+8]
0x18004420c  jnz     loc_18004437B
0x180044212  test    rdi, rdi
0x180044215  jz      loc_18004437B
0x18004421b  call    ?zInternalStop@?$ActivityBase@VPowerAndBatteryLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<PowerAndBatteryLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180044220  call    ?Provider@PowerAndBatteryLoggingProvider@@SAPEBU_tlgProvider_t@@XZ; PowerAndBatteryLoggingProvider::Provider(void)
0x180044225  mov     r9, rax
0x180044228  mov     ecx, [rax]
0x18004422a  cmp     ecx, 5
0x18004422d  jbe     loc_1800443F2
0x180044233  mov     rdx, 400000000000h
0x18004423d  mov     rcx, rax
0x180044240  call    _tlgKeywordOn
0x180044245  test    al, al
0x180044247  jz      loc_1800443F2
0x18004424d  mov     rax, [rdi+70h]
0x180044251  lea     rdx, byte_18005B169
0x180044258  mov     rcx, [rdi+78h]
0x18004425c  mov     r8, [rbx+110h]
0x180044263  mov     [rbp+57h+var_60], rax
0x180044267  add     r8, 8
0x18004426b  mov     eax, [rdi+68h]
0x18004426e  mov     [rbp+57h+arg_0], eax
0x180044271  mov     rax, [rdi+60h]
0x180044275  mov     [rbp+57h+var_58], rax
0x180044279  mov     rax, [rdi+58h]
0x18004427d  mov     [rbp+57h+var_50], rax
0x180044281  mov     eax, [rdi+50h]
0x180044284  mov     [rbp+57h+arg_8], eax
0x180044287  mov     rax, [rdi+48h]
0x18004428b  mov     [rbp+57h+var_48], rax
0x18004428f  mov     eax, [rdi+20h]
0x180044292  mov     dword ptr [rbp+57h+arg_10], eax
0x180044295  mov     rax, [rdi+18h]
0x180044299  mov     [rbp+57h+var_40], rax
0x18004429d  mov     eax, [rdi]
0x18004429f  mov     [rbp+57h+arg_18], eax
0x1800442a2  mov     rax, [rdi+80h]
0x1800442a9  mov     [rbp+57h+var_38], rax
0x1800442ad  mov     eax, [rdi+40h]
0x1800442b0  mov     [rbp+57h+var_70], eax
0x1800442b3  mov     rax, [rdi+38h]
0x1800442b7  mov     [rbp+57h+var_30], rax
0x1800442bb  mov     eax, [rdi+8]
0x1800442be  mov     [rbp+57h+var_6C], eax
0x1800442c1  lea     rax, [rbp+57h+var_68]
0x1800442c5  mov     [rsp+110h+var_78], rax
0x1800442cd  lea     rax, [rbp+57h+var_60]
0x1800442d1  mov     [rsp+110h+var_80], rax
0x1800442d9  lea     rax, [rbp+57h+arg_0]
0x1800442dd  mov     [rsp+110h+var_88], rax
0x1800442e5  lea     rax, [rbp+57h+var_58]
0x1800442e9  mov     [rsp+110h+var_90], rax
0x1800442f1  lea     rax, [rbp+57h+var_50]
0x1800442f5  mov     [rsp+110h+var_98], rax
0x1800442fa  lea     rax, [rbp+57h+arg_8]
0x1800442fe  mov     [rsp+110h+var_A0], rax
0x180044303  lea     rax, [rbp+57h+var_48]
0x180044307  mov     [rsp+110h+var_A8], rax
0x18004430c  lea     rax, [rbp+57h+arg_10]
0x180044310  mov     [rsp+110h+var_B0], rax
0x180044315  lea     rax, [rbp+57h+var_40]
0x180044319  mov     [rsp+110h+var_B8], rax
0x18004431e  lea     rax, [rbp+57h+arg_18]
0x180044322  mov     [rsp+110h+var_C0], rax
0x180044327  lea     rax, [rbp+57h+var_38]
0x18004432b  mov     [rsp+110h+var_C8], rax
0x180044330  lea     rax, [rbp+57h+var_70]
0x180044334  mov     [rsp+110h+var_D0], rax
0x180044339  lea     rax, [rbp+57h+var_30]
0x18004433d  mov     [rsp+110h+var_D8], rax
0x180044342  lea     rax, [rbp+57h+var_6C]
0x180044346  mov     [rsp+110h+var_E0], rax
0x18004434b  lea     rax, [rbp+57h+var_28]
0x18004434f  mov     [rsp+110h+var_E8], rax
0x180044354  lea     rax, [rbp+57h+var_20]
0x180044358  mov     [rbp+57h+var_68], rcx
0x18004435c  mov     rcx, r9
0x18004435f  mov     [rsp+110h+var_F0], rax
0x180044364  mov     [rbp+57h+var_28], 1000000h
0x18004436c  mov     [rbp+57h+var_20], 0
0x180044374  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180044379  jmp     short loc_1800443F2
0x18004437b  call    ?zInternalStop@?$ActivityBase@VPowerAndBatteryLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<PowerAndBatteryLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180044380  call    ?Provider@PowerAndBatteryLoggingProvider@@SAPEBU_tlgProvider_t@@XZ; PowerAndBatteryLoggingProvider::Provider(void)
0x180044385  mov     rdi, rax
0x180044388  mov     ecx, [rax]
0x18004438a  cmp     ecx, 5
0x18004438d  jbe     short loc_1800443F2
0x18004438f  mov     rdx, 400000000000h
0x180044399  mov     rcx, rax
0x18004439c  call    _tlgKeywordOn
0x1800443a1  test    al, al
0x1800443a3  jz      short loc_1800443F2
0x1800443a5  call    cs:__imp_GetCurrentThreadId
0x1800443ab  mov     r8, [rbx+110h]
0x1800443b2  lea     rdx, word_18005B29A
0x1800443b9  mov     [rbp+57h+arg_0], eax
0x1800443bc  mov     rcx, rdi
0x1800443bf  mov     eax, [r8+48h]
0x1800443c3  add     r8, 8
0x1800443c7  mov     [rbp+57h+arg_8], eax
0x1800443ca  lea     rax, [rbp+57h+arg_0]
0x1800443ce  mov     [rsp+110h+var_E0], rax
0x1800443d3  lea     rax, [rbp+57h+arg_8]
0x1800443d7  mov     [rsp+110h+var_E8], rax
0x1800443dc  lea     rax, [rbp+57h+arg_10]
0x1800443e0  mov     [rsp+110h+var_F0], rax
0x1800443e5  mov     [rbp+57h+arg_10], 0
0x1800443ed  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800443f2  mov     rcx, rbx
0x1800443f5  add     rsp, 100h
0x1800443fc  pop     rdi
0x1800443fd  pop     rbx
0x1800443fe  pop     rbp
0x1800443ff  jmp     ?IgnoreCurrentThread@?$ActivityBase@VPowerAndBatteryLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<PowerAndBatteryLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
