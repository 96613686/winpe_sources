# PowerAndBatteryTelemetry::SetEnergySaverThreshold::StopActivity(void)

- ea: `0x180029750`
- end: `0x180029974`
- name: `?StopActivity@SetEnergySaverThreshold@PowerAndBatteryTelemetry@@MEAAXXZ`
- size: `548`
- prototype: `void __fastcall(PowerAndBatteryTelemetry::SetEnergySaverThreshold *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x180001188`
- `0x1800014ac`
- `0x180001c3c`
- `0x180022e60`
- `0x180025840`
- `0x180029750`
- `0x18002c874`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180029915`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180029915`

## pseudocode

```c
void __fastcall PowerAndBatteryTelemetry::SetEnergySaverThreshold::StopActivity(
        PowerAndBatteryTelemetry::SetEnergySaverThreshold *this)
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
        (__int64)word_18005A812,
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
        (__int64)byte_18005A941,
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
0x180029750  push    rbp
0x180029752  push    rbx
0x180029753  push    rdi
0x180029754  lea     rbp, [rsp-47h]
0x180029759  sub     rsp, 100h
0x180029760  mov     rdi, [rcx+110h]
0x180029767  mov     rbx, rcx
0x18002976a  mov     eax, [rdi+48h]
0x18002976d  test    eax, eax
0x18002976f  jns     loc_1800298EB
0x180029775  add     rdi, 50h ; 'P'
0x180029779  cmp     eax, [rdi+8]
0x18002977c  jnz     loc_1800298EB
0x180029782  test    rdi, rdi
0x180029785  jz      loc_1800298EB
0x18002978b  call    ?zInternalStop@?$ActivityBase@VPowerAndBatteryLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<PowerAndBatteryLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180029790  call    ?Provider@PowerAndBatteryLoggingProvider@@SAPEBU_tlgProvider_t@@XZ; PowerAndBatteryLoggingProvider::Provider(void)
0x180029795  mov     r9, rax
0x180029798  mov     ecx, [rax]
0x18002979a  cmp     ecx, 5
0x18002979d  jbe     loc_180029962
0x1800297a3  mov     rdx, 400000000000h
0x1800297ad  mov     rcx, rax
0x1800297b0  call    _tlgKeywordOn
0x1800297b5  test    al, al
0x1800297b7  jz      loc_180029962
0x1800297bd  mov     rax, [rdi+70h]
0x1800297c1  lea     rdx, word_18005A812
0x1800297c8  mov     rcx, [rdi+78h]
0x1800297cc  mov     r8, [rbx+110h]
0x1800297d3  mov     [rbp+57h+var_60], rax
0x1800297d7  add     r8, 8
0x1800297db  mov     eax, [rdi+68h]
0x1800297de  mov     [rbp+57h+arg_0], eax
0x1800297e1  mov     rax, [rdi+60h]
0x1800297e5  mov     [rbp+57h+var_58], rax
0x1800297e9  mov     rax, [rdi+58h]
0x1800297ed  mov     [rbp+57h+var_50], rax
0x1800297f1  mov     eax, [rdi+50h]
0x1800297f4  mov     [rbp+57h+arg_8], eax
0x1800297f7  mov     rax, [rdi+48h]
0x1800297fb  mov     [rbp+57h+var_48], rax
0x1800297ff  mov     eax, [rdi+20h]
0x180029802  mov     dword ptr [rbp+57h+arg_10], eax
0x180029805  mov     rax, [rdi+18h]
0x180029809  mov     [rbp+57h+var_40], rax
0x18002980d  mov     eax, [rdi]
0x18002980f  mov     [rbp+57h+arg_18], eax
0x180029812  mov     rax, [rdi+80h]
0x180029819  mov     [rbp+57h+var_38], rax
0x18002981d  mov     eax, [rdi+40h]
0x180029820  mov     [rbp+57h+var_70], eax
0x180029823  mov     rax, [rdi+38h]
0x180029827  mov     [rbp+57h+var_30], rax
0x18002982b  mov     eax, [rdi+8]
0x18002982e  mov     [rbp+57h+var_6C], eax
0x180029831  lea     rax, [rbp+57h+var_68]
0x180029835  mov     [rsp+110h+var_78], rax
0x18002983d  lea     rax, [rbp+57h+var_60]
0x180029841  mov     [rsp+110h+var_80], rax
0x180029849  lea     rax, [rbp+57h+arg_0]
0x18002984d  mov     [rsp+110h+var_88], rax
0x180029855  lea     rax, [rbp+57h+var_58]
0x180029859  mov     [rsp+110h+var_90], rax
0x180029861  lea     rax, [rbp+57h+var_50]
0x180029865  mov     [rsp+110h+var_98], rax
0x18002986a  lea     rax, [rbp+57h+arg_8]
0x18002986e  mov     [rsp+110h+var_A0], rax
0x180029873  lea     rax, [rbp+57h+var_48]
0x180029877  mov     [rsp+110h+var_A8], rax
0x18002987c  lea     rax, [rbp+57h+arg_10]
0x180029880  mov     [rsp+110h+var_B0], rax
0x180029885  lea     rax, [rbp+57h+var_40]
0x180029889  mov     [rsp+110h+var_B8], rax
0x18002988e  lea     rax, [rbp+57h+arg_18]
0x180029892  mov     [rsp+110h+var_C0], rax
0x180029897  lea     rax, [rbp+57h+var_38]
0x18002989b  mov     [rsp+110h+var_C8], rax
0x1800298a0  lea     rax, [rbp+57h+var_70]
0x1800298a4  mov     [rsp+110h+var_D0], rax
0x1800298a9  lea     rax, [rbp+57h+var_30]
0x1800298ad  mov     [rsp+110h+var_D8], rax
0x1800298b2  lea     rax, [rbp+57h+var_6C]
0x1800298b6  mov     [rsp+110h+var_E0], rax
0x1800298bb  lea     rax, [rbp+57h+var_28]
0x1800298bf  mov     [rsp+110h+var_E8], rax
0x1800298c4  lea     rax, [rbp+57h+var_20]
0x1800298c8  mov     [rbp+57h+var_68], rcx
0x1800298cc  mov     rcx, r9
0x1800298cf  mov     [rsp+110h+var_F0], rax
0x1800298d4  mov     [rbp+57h+var_28], 1000000h
0x1800298dc  mov     [rbp+57h+var_20], 0
0x1800298e4  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x1800298e9  jmp     short loc_180029962
0x1800298eb  call    ?zInternalStop@?$ActivityBase@VPowerAndBatteryLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<PowerAndBatteryLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x1800298f0  call    ?Provider@PowerAndBatteryLoggingProvider@@SAPEBU_tlgProvider_t@@XZ; PowerAndBatteryLoggingProvider::Provider(void)
0x1800298f5  mov     rdi, rax
0x1800298f8  mov     ecx, [rax]
0x1800298fa  cmp     ecx, 5
0x1800298fd  jbe     short loc_180029962
0x1800298ff  mov     rdx, 400000000000h
0x180029909  mov     rcx, rax
0x18002990c  call    _tlgKeywordOn
0x180029911  test    al, al
0x180029913  jz      short loc_180029962
0x180029915  call    cs:__imp_GetCurrentThreadId
0x18002991b  mov     r8, [rbx+110h]
0x180029922  lea     rdx, byte_18005A941
0x180029929  mov     [rbp+57h+arg_0], eax
0x18002992c  mov     rcx, rdi
0x18002992f  mov     eax, [r8+48h]
0x180029933  add     r8, 8
0x180029937  mov     [rbp+57h+arg_8], eax
0x18002993a  lea     rax, [rbp+57h+arg_0]
0x18002993e  mov     [rsp+110h+var_E0], rax
0x180029943  lea     rax, [rbp+57h+arg_8]
0x180029947  mov     [rsp+110h+var_E8], rax
0x18002994c  lea     rax, [rbp+57h+arg_10]
0x180029950  mov     [rsp+110h+var_F0], rax
0x180029955  mov     [rbp+57h+arg_10], 0
0x18002995d  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180029962  mov     rcx, rbx
0x180029965  add     rsp, 100h
0x18002996c  pop     rdi
0x18002996d  pop     rbx
0x18002996e  pop     rbp
0x18002996f  jmp     ?IgnoreCurrentThread@?$ActivityBase@VPowerAndBatteryLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<PowerAndBatteryLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
