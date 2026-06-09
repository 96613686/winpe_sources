# WiFiCloudStoreTelemetry::WlanTriggeredSync::Stop(WiFiCloudStoreTelemetryResult)

- ea: `0x180013c74`
- end: `0x180013ee7`
- name: `?Stop@WlanTriggeredSync@WiFiCloudStoreTelemetry@@QEAAXW4WiFiCloudStoreTelemetryResult@@@Z`
- size: `627`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180012fb4`
- `0x18001f808`

## callees

- `0x180001af4`
- `0x180013c74`
- `0x180019e40`
- `0x18001c898`
- `0x18001cd90`
- `0x18001edd4`
- `0x1800202bc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013e6e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013e6e`

## pseudocode

```c
__int64 __fastcall WiFiCloudStoreTelemetry::WlanTriggeredSync::Stop(__int64 a1, int a2)
{
  __int64 v2; // rdi
  int v5; // eax
  int *v6; // rdi
  const struct _tlgProvider_t *v7; // rax
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // r9
  __int64 v11; // rax
  __int64 v12; // r8
  const struct _tlgProvider_t *v13; // rax
  __int64 v14; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v16; // r8
  __int64 v17; // r9
  int v19; // [rsp+B0h] [rbp-80h] BYREF
  int v20; // [rsp+B4h] [rbp-7Ch] BYREF
  int v21; // [rsp+B8h] [rbp-78h] BYREF
  int v22; // [rsp+BCh] [rbp-74h] BYREF
  int v23; // [rsp+C0h] [rbp-70h] BYREF
  __int64 v24; // [rsp+C8h] [rbp-68h] BYREF
  __int64 v25; // [rsp+D0h] [rbp-60h] BYREF
  __int64 v26; // [rsp+D8h] [rbp-58h] BYREF
  __int64 v27; // [rsp+E0h] [rbp-50h] BYREF
  __int64 v28; // [rsp+E8h] [rbp-48h] BYREF
  __int64 v29; // [rsp+F0h] [rbp-40h] BYREF
  __int64 v30; // [rsp+F8h] [rbp-38h] BYREF
  __int64 v31; // [rsp+100h] [rbp-30h] BYREF
  __int64 v32; // [rsp+108h] [rbp-28h] BYREF
  __int64 v33[4]; // [rsp+110h] [rbp-20h] BYREF
  bool v34; // [rsp+140h] [rbp+10h] BYREF
  int v35; // [rsp+150h] [rbp+20h] BYREF
  DWORD v36; // [rsp+158h] [rbp+28h] BYREF

  v2 = *(_QWORD *)(a1 + 272);
  v5 = *(_DWORD *)(v2 + 72);
  if ( v5 < 0 && (v6 = (int *)(v2 + 80), v5 == v6[2]) && v6 )
  {
    wil::ActivityBase<WiFiCloudStoreTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v7 = WiFiCloudStoreTelemetry::Provider();
    v10 = (__int64)v7;
    if ( *(_DWORD *)v7 > 5u && (unsigned __int8)tlgKeywordOn(v7, 0x400000000000LL) )
    {
      v25 = *((_QWORD *)v6 + 15);
      v11 = *((_QWORD *)v6 + 14);
      v12 = *(_QWORD *)(a1 + 272);
      v34 = a2 != 1;
      v26 = v11;
      v36 = v6[26];
      v27 = *((_QWORD *)v6 + 12);
      v28 = *((_QWORD *)v6 + 11);
      v20 = v6[20];
      v29 = *((_QWORD *)v6 + 9);
      v21 = v6[8];
      v30 = *((_QWORD *)v6 + 3);
      v22 = *v6;
      v31 = *((_QWORD *)v6 + 16);
      v23 = v6[16];
      v32 = *((_QWORD *)v6 + 7);
      v19 = v6[2];
      v35 = a2;
      v33[0] = 0x1000000;
      v24 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>>(
        v10,
        (__int64)word_180046292,
        v12 + 8,
        v10,
        (__int64)&v24,
        (__int64)v33,
        (__int64)&v19,
        &v32,
        (__int64)&v23,
        &v31,
        (__int64)&v22,
        &v30,
        (__int64)&v21,
        &v29,
        (__int64)&v20,
        &v28,
        &v27,
        (__int64)&v36,
        &v26,
        &v25);
    }
  }
  else
  {
    wil::ActivityBase<WiFiCloudStoreTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v13 = WiFiCloudStoreTelemetry::Provider();
    v14 = (__int64)v13;
    if ( *(_DWORD *)v13 > 5u && (unsigned __int8)tlgKeywordOn(v13, 0x400000000000LL) )
    {
      v35 = a2;
      v34 = a2 != 1;
      CurrentThreadId = GetCurrentThreadId();
      v16 = *(_QWORD *)(a1 + 272);
      v36 = CurrentThreadId;
      v19 = *(_DWORD *)(v16 + 72);
      v24 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>>(
        v14,
        (unsigned __int8 *)&dword_1800463D4,
        (const GUID *)(v16 + 8),
        v17,
        (__int64)&v24,
        (__int64)&v19,
        (__int64)&v36,
        (__int64)&v34,
        (__int64)&v35);
    }
  }
  return wil::ActivityBase<WiFiCloudStoreTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
           a1,
           v8,
           v9,
           v10);
}

```

## disassembly

```asm
0x180013c74  mov     [rsp-8+arg_8], rbx
0x180013c79  push    rbp
0x180013c7a  push    rsi
0x180013c7b  push    rdi
0x180013c7c  lea     rbp, [rsp+10h]
0x180013c81  sub     rsp, 120h
0x180013c88  mov     rdi, [rcx+110h]
0x180013c8f  mov     esi, edx
0x180013c91  mov     rbx, rcx
0x180013c94  mov     eax, [rdi+48h]
0x180013c97  test    eax, eax
0x180013c99  jns     loc_180013E3A
0x180013c9f  add     rdi, 50h ; 'P'
0x180013ca3  cmp     eax, [rdi+8]
0x180013ca6  jnz     loc_180013E3A
0x180013cac  test    rdi, rdi
0x180013caf  jz      loc_180013E3A
0x180013cb5  call    ?zInternalStop@?$ActivityBase@VWiFiCloudStoreTelemetry@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WiFiCloudStoreTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180013cba  call    ?Provider@WiFiCloudStoreTelemetry@@SAPEBU_tlgProvider_t@@XZ; WiFiCloudStoreTelemetry::Provider(void)
0x180013cbf  mov     r9, rax
0x180013cc2  mov     ecx, [rax]
0x180013cc4  cmp     ecx, 5
0x180013cc7  jbe     loc_180013ECD
0x180013ccd  mov     rdx, 400000000000h
0x180013cd7  mov     rcx, rax
0x180013cda  call    _tlgKeywordOn
0x180013cdf  test    al, al
0x180013ce1  jz      loc_180013ECD
0x180013ce7  mov     rax, [rdi+78h]
0x180013ceb  lea     rdx, word_180046292
0x180013cf2  mov     [rbp+var_60], rax
0x180013cf6  cmp     esi, 1
0x180013cf9  mov     rax, [rdi+70h]
0x180013cfd  mov     rcx, r9
0x180013d00  mov     r8, [rbx+110h]
0x180013d07  setnz   [rbp+arg_0]
0x180013d0b  mov     [rbp+var_58], rax
0x180013d0f  add     r8, 8
0x180013d13  mov     eax, [rdi+68h]
0x180013d16  mov     [rbp+arg_18], eax
0x180013d19  mov     rax, [rdi+60h]
0x180013d1d  mov     [rbp+var_50], rax
0x180013d21  mov     rax, [rdi+58h]
0x180013d25  mov     [rbp+var_48], rax
0x180013d29  mov     eax, [rdi+50h]
0x180013d2c  mov     [rbp+var_7C], eax
0x180013d2f  mov     rax, [rdi+48h]
0x180013d33  mov     [rbp+var_40], rax
0x180013d37  mov     eax, [rdi+20h]
0x180013d3a  mov     [rbp+var_78], eax
0x180013d3d  mov     rax, [rdi+18h]
0x180013d41  mov     [rbp+var_38], rax
0x180013d45  mov     eax, [rdi]
0x180013d47  mov     [rbp+var_74], eax
0x180013d4a  mov     rax, [rdi+80h]
0x180013d51  mov     [rbp+var_30], rax
0x180013d55  mov     eax, [rdi+40h]
0x180013d58  mov     [rbp+var_70], eax
0x180013d5b  mov     rax, [rdi+38h]
0x180013d5f  mov     [rbp+var_28], rax
0x180013d63  mov     eax, [rdi+8]
0x180013d66  mov     [rbp+var_80], eax
0x180013d69  lea     rax, [rbp+arg_10]
0x180013d6d  mov     [rsp+130h+var_88], rax
0x180013d75  lea     rax, [rbp+arg_0]
0x180013d79  mov     [rsp+130h+var_90], rax
0x180013d81  lea     rax, [rbp+var_60]
0x180013d85  mov     [rsp+130h+var_98], rax
0x180013d8d  lea     rax, [rbp+var_58]
0x180013d91  mov     [rsp+130h+var_A0], rax
0x180013d99  lea     rax, [rbp+arg_18]
0x180013d9d  mov     [rsp+130h+var_A8], rax
0x180013da5  lea     rax, [rbp+var_50]
0x180013da9  mov     [rsp+130h+var_B0], rax
0x180013db1  lea     rax, [rbp+var_48]
0x180013db5  mov     [rsp+130h+var_B8], rax
0x180013dba  lea     rax, [rbp+var_7C]
0x180013dbe  mov     [rsp+130h+var_C0], rax
0x180013dc3  lea     rax, [rbp+var_40]
0x180013dc7  mov     [rsp+130h+var_C8], rax
0x180013dcc  lea     rax, [rbp+var_78]
0x180013dd0  mov     [rsp+130h+var_D0], rax
0x180013dd5  lea     rax, [rbp+var_38]
0x180013dd9  mov     [rsp+130h+var_D8], rax
0x180013dde  lea     rax, [rbp+var_74]
0x180013de2  mov     [rsp+130h+var_E0], rax
0x180013de7  lea     rax, [rbp+var_30]
0x180013deb  mov     [rsp+130h+var_E8], rax
0x180013df0  lea     rax, [rbp+var_70]
0x180013df4  mov     [rsp+130h+var_F0], rax
0x180013df9  lea     rax, [rbp+var_28]
0x180013dfd  mov     [rsp+130h+var_F8], rax
0x180013e02  lea     rax, [rbp+var_80]
0x180013e06  mov     [rsp+130h+var_100], rax
0x180013e0b  lea     rax, [rbp+var_20]
0x180013e0f  mov     [rsp+130h+var_108], rax
0x180013e14  lea     rax, [rbp+var_68]
0x180013e18  mov     [rsp+130h+var_110], rax
0x180013e1d  mov     [rbp+arg_10], esi
0x180013e20  mov     [rbp+var_20], 1000000h
0x180013e28  mov     [rbp+var_68], 0
0x180013e30  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U?$_tlgWrapperByVal@$00@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456AEBU?$_tlgWrapperByVal@$00@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<4> const &)
0x180013e35  jmp     loc_180013ECD
0x180013e3a  call    ?zInternalStop@?$ActivityBase@VWiFiCloudStoreTelemetry@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WiFiCloudStoreTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180013e3f  call    ?Provider@WiFiCloudStoreTelemetry@@SAPEBU_tlgProvider_t@@XZ; WiFiCloudStoreTelemetry::Provider(void)
0x180013e44  mov     rdi, rax
0x180013e47  mov     ecx, [rax]
0x180013e49  cmp     ecx, 5
0x180013e4c  jbe     short loc_180013ECD
0x180013e4e  mov     rdx, 400000000000h
0x180013e58  mov     rcx, rax
0x180013e5b  call    _tlgKeywordOn
0x180013e60  test    al, al
0x180013e62  jz      short loc_180013ECD
0x180013e64  cmp     esi, 1
0x180013e67  mov     [rbp+arg_10], esi
0x180013e6a  setnz   [rbp+arg_0]
0x180013e6e  call    cs:__imp_GetCurrentThreadId
0x180013e74  mov     r8, [rbx+110h]
0x180013e7b  lea     rdx, dword_1800463D4
0x180013e82  mov     [rbp+arg_18], eax
0x180013e85  mov     rcx, rdi
0x180013e88  mov     eax, [r8+48h]
0x180013e8c  add     r8, 8
0x180013e90  mov     [rbp+var_80], eax
0x180013e93  lea     rax, [rbp+arg_10]
0x180013e97  mov     [rsp+130h+var_F0], rax
0x180013e9c  lea     rax, [rbp+arg_0]
0x180013ea0  mov     [rsp+130h+var_F8], rax
0x180013ea5  lea     rax, [rbp+arg_18]
0x180013ea9  mov     [rsp+130h+var_100], rax
0x180013eae  lea     rax, [rbp+var_80]
0x180013eb2  mov     [rsp+130h+var_108], rax
0x180013eb7  lea     rax, [rbp+var_68]
0x180013ebb  mov     [rsp+130h+var_110], rax
0x180013ec0  mov     [rbp+var_68], 0
0x180013ec8  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapperByVal@$00@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapperByVal@$00@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<4> const &)
0x180013ecd  mov     rcx, rbx
0x180013ed0  mov     rbx, [rsp+130h+arg_8]
0x180013ed8  add     rsp, 120h
0x180013edf  pop     rdi
0x180013ee0  pop     rsi
0x180013ee1  pop     rbp
0x180013ee2  jmp     ?IgnoreCurrentThread@?$ActivityBase@VWiFiCloudStoreTelemetry@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WiFiCloudStoreTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
