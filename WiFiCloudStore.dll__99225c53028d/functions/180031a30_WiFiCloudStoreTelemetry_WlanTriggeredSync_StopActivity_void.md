# WiFiCloudStoreTelemetry::WlanTriggeredSync::StopActivity(void)

- ea: `0x180031a30`
- end: `0x180031c54`
- name: `?StopActivity@WlanTriggeredSync@WiFiCloudStoreTelemetry@@MEAAXXZ`
- size: `548`
- prototype: `void __fastcall(WiFiCloudStoreTelemetry::WlanTriggeredSync *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x1800013fc`
- `0x180001dc8`
- `0x180019e40`
- `0x18001c898`
- `0x18001edd4`
- `0x1800202bc`
- `0x180031a30`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180031bf5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180031bf5`

## pseudocode

```c
void __fastcall WiFiCloudStoreTelemetry::WlanTriggeredSync::StopActivity(
        WiFiCloudStoreTelemetry::WlanTriggeredSync *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  const struct _tlgProvider_t *v5; // rax
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // r9
  __int64 v9; // rcx
  __int64 v10; // r8
  const struct _tlgProvider_t *v11; // rax
  __int64 v12; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v14; // r8
  int v15; // [rsp+A0h] [rbp-19h] BYREF
  int v16; // [rsp+A4h] [rbp-15h] BYREF
  __int64 v17; // [rsp+A8h] [rbp-11h] BYREF
  __int64 v18; // [rsp+B0h] [rbp-9h] BYREF
  __int64 v19; // [rsp+B8h] [rbp-1h] BYREF
  __int64 v20; // [rsp+C0h] [rbp+7h] BYREF
  __int64 v21; // [rsp+C8h] [rbp+Fh] BYREF
  __int64 v22; // [rsp+D0h] [rbp+17h] BYREF
  __int64 v23; // [rsp+D8h] [rbp+1Fh] BYREF
  __int64 v24; // [rsp+E0h] [rbp+27h] BYREF
  __int64 v25; // [rsp+E8h] [rbp+2Fh] BYREF
  _QWORD v26[4]; // [rsp+F0h] [rbp+37h] BYREF
  DWORD v27; // [rsp+120h] [rbp+67h] BYREF
  int v28; // [rsp+128h] [rbp+6Fh] BYREF
  __int64 v29; // [rsp+130h] [rbp+77h] BYREF
  int v30; // [rsp+138h] [rbp+7Fh] BYREF

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = (int *)(v1 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<WiFiCloudStoreTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v5 = WiFiCloudStoreTelemetry::Provider();
    v8 = (__int64)v5;
    if ( *(_DWORD *)v5 > 5u && (unsigned __int8)tlgKeywordOn(v5, 0x400000000000LL) )
    {
      v9 = *((_QWORD *)v4 + 15);
      v10 = *((_QWORD *)this + 34);
      v18 = *((_QWORD *)v4 + 14);
      v27 = v4[26];
      v19 = *((_QWORD *)v4 + 12);
      v20 = *((_QWORD *)v4 + 11);
      v28 = v4[20];
      v21 = *((_QWORD *)v4 + 9);
      LODWORD(v29) = v4[8];
      v22 = *((_QWORD *)v4 + 3);
      v30 = *v4;
      v23 = *((_QWORD *)v4 + 16);
      v15 = v4[16];
      v24 = *((_QWORD *)v4 + 7);
      v16 = v4[2];
      v17 = v9;
      v25 = 0x1000000;
      v26[0] = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        v8,
        (__int64)byte_1800468F3,
        v10 + 8,
        v8,
        (__int64)v26,
        (__int64)&v25,
        (__int64)&v16,
        &v24,
        (__int64)&v15,
        &v23,
        (__int64)&v30,
        &v22,
        (__int64)&v29,
        &v21,
        (__int64)&v28,
        &v20,
        &v19,
        (__int64)&v27,
        &v18,
        &v17);
    }
  }
  else
  {
    wil::ActivityBase<WiFiCloudStoreTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v11 = WiFiCloudStoreTelemetry::Provider();
    v12 = (__int64)v11;
    if ( *(_DWORD *)v11 > 5u && (unsigned __int8)tlgKeywordOn(v11, 0x400000000000LL) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v14 = *((_QWORD *)this + 34);
      v27 = CurrentThreadId;
      v28 = *(_DWORD *)(v14 + 72);
      v29 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v12,
        (__int64)&dword_180046A1C,
        v14 + 8);
    }
  }
  wil::ActivityBase<WiFiCloudStoreTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
    this,
    v6,
    v7,
    v8);
}

```

## disassembly

```asm
0x180031a30  push    rbp
0x180031a32  push    rbx
0x180031a33  push    rdi
0x180031a34  lea     rbp, [rsp-47h]
0x180031a39  sub     rsp, 100h
0x180031a40  mov     rdi, [rcx+110h]
0x180031a47  mov     rbx, rcx
0x180031a4a  mov     eax, [rdi+48h]
0x180031a4d  test    eax, eax
0x180031a4f  jns     loc_180031BCB
0x180031a55  add     rdi, 50h ; 'P'
0x180031a59  cmp     eax, [rdi+8]
0x180031a5c  jnz     loc_180031BCB
0x180031a62  test    rdi, rdi
0x180031a65  jz      loc_180031BCB
0x180031a6b  call    ?zInternalStop@?$ActivityBase@VWiFiCloudStoreTelemetry@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WiFiCloudStoreTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180031a70  call    ?Provider@WiFiCloudStoreTelemetry@@SAPEBU_tlgProvider_t@@XZ; WiFiCloudStoreTelemetry::Provider(void)
0x180031a75  mov     r9, rax
0x180031a78  mov     ecx, [rax]
0x180031a7a  cmp     ecx, 5
0x180031a7d  jbe     loc_180031C42
0x180031a83  mov     rdx, 400000000000h
0x180031a8d  mov     rcx, rax
0x180031a90  call    _tlgKeywordOn
0x180031a95  test    al, al
0x180031a97  jz      loc_180031C42
0x180031a9d  mov     rax, [rdi+70h]
0x180031aa1  lea     rdx, byte_1800468F3
0x180031aa8  mov     rcx, [rdi+78h]
0x180031aac  mov     r8, [rbx+110h]
0x180031ab3  mov     [rbp+57h+var_60], rax
0x180031ab7  add     r8, 8
0x180031abb  mov     eax, [rdi+68h]
0x180031abe  mov     [rbp+57h+arg_0], eax
0x180031ac1  mov     rax, [rdi+60h]
0x180031ac5  mov     [rbp+57h+var_58], rax
0x180031ac9  mov     rax, [rdi+58h]
0x180031acd  mov     [rbp+57h+var_50], rax
0x180031ad1  mov     eax, [rdi+50h]
0x180031ad4  mov     [rbp+57h+arg_8], eax
0x180031ad7  mov     rax, [rdi+48h]
0x180031adb  mov     [rbp+57h+var_48], rax
0x180031adf  mov     eax, [rdi+20h]
0x180031ae2  mov     dword ptr [rbp+57h+arg_10], eax
0x180031ae5  mov     rax, [rdi+18h]
0x180031ae9  mov     [rbp+57h+var_40], rax
0x180031aed  mov     eax, [rdi]
0x180031aef  mov     [rbp+57h+arg_18], eax
0x180031af2  mov     rax, [rdi+80h]
0x180031af9  mov     [rbp+57h+var_38], rax
0x180031afd  mov     eax, [rdi+40h]
0x180031b00  mov     [rbp+57h+var_70], eax
0x180031b03  mov     rax, [rdi+38h]
0x180031b07  mov     [rbp+57h+var_30], rax
0x180031b0b  mov     eax, [rdi+8]
0x180031b0e  mov     [rbp+57h+var_6C], eax
0x180031b11  lea     rax, [rbp+57h+var_68]
0x180031b15  mov     [rsp+110h+var_78], rax
0x180031b1d  lea     rax, [rbp+57h+var_60]
0x180031b21  mov     [rsp+110h+var_80], rax
0x180031b29  lea     rax, [rbp+57h+arg_0]
0x180031b2d  mov     [rsp+110h+var_88], rax
0x180031b35  lea     rax, [rbp+57h+var_58]
0x180031b39  mov     [rsp+110h+var_90], rax
0x180031b41  lea     rax, [rbp+57h+var_50]
0x180031b45  mov     [rsp+110h+var_98], rax
0x180031b4a  lea     rax, [rbp+57h+arg_8]
0x180031b4e  mov     [rsp+110h+var_A0], rax
0x180031b53  lea     rax, [rbp+57h+var_48]
0x180031b57  mov     [rsp+110h+var_A8], rax
0x180031b5c  lea     rax, [rbp+57h+arg_10]
0x180031b60  mov     [rsp+110h+var_B0], rax
0x180031b65  lea     rax, [rbp+57h+var_40]
0x180031b69  mov     [rsp+110h+var_B8], rax
0x180031b6e  lea     rax, [rbp+57h+arg_18]
0x180031b72  mov     [rsp+110h+var_C0], rax
0x180031b77  lea     rax, [rbp+57h+var_38]
0x180031b7b  mov     [rsp+110h+var_C8], rax
0x180031b80  lea     rax, [rbp+57h+var_70]
0x180031b84  mov     [rsp+110h+var_D0], rax
0x180031b89  lea     rax, [rbp+57h+var_30]
0x180031b8d  mov     [rsp+110h+var_D8], rax
0x180031b92  lea     rax, [rbp+57h+var_6C]
0x180031b96  mov     [rsp+110h+var_E0], rax
0x180031b9b  lea     rax, [rbp+57h+var_28]
0x180031b9f  mov     [rsp+110h+var_E8], rax
0x180031ba4  lea     rax, [rbp+57h+var_20]
0x180031ba8  mov     [rbp+57h+var_68], rcx
0x180031bac  mov     rcx, r9
0x180031baf  mov     [rsp+110h+var_F0], rax
0x180031bb4  mov     [rbp+57h+var_28], 1000000h
0x180031bbc  mov     [rbp+57h+var_20], 0
0x180031bc4  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180031bc9  jmp     short loc_180031C42
0x180031bcb  call    ?zInternalStop@?$ActivityBase@VWiFiCloudStoreTelemetry@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WiFiCloudStoreTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180031bd0  call    ?Provider@WiFiCloudStoreTelemetry@@SAPEBU_tlgProvider_t@@XZ; WiFiCloudStoreTelemetry::Provider(void)
0x180031bd5  mov     rdi, rax
0x180031bd8  mov     ecx, [rax]
0x180031bda  cmp     ecx, 5
0x180031bdd  jbe     short loc_180031C42
0x180031bdf  mov     rdx, 400000000000h
0x180031be9  mov     rcx, rax
0x180031bec  call    _tlgKeywordOn
0x180031bf1  test    al, al
0x180031bf3  jz      short loc_180031C42
0x180031bf5  call    cs:__imp_GetCurrentThreadId
0x180031bfb  mov     r8, [rbx+110h]
0x180031c02  lea     rdx, dword_180046A1C
0x180031c09  mov     [rbp+57h+arg_0], eax
0x180031c0c  mov     rcx, rdi
0x180031c0f  mov     eax, [r8+48h]
0x180031c13  add     r8, 8
0x180031c17  mov     [rbp+57h+arg_8], eax
0x180031c1a  lea     rax, [rbp+57h+arg_0]
0x180031c1e  mov     [rsp+110h+var_E0], rax
0x180031c23  lea     rax, [rbp+57h+arg_8]
0x180031c27  mov     [rsp+110h+var_E8], rax
0x180031c2c  lea     rax, [rbp+57h+arg_10]
0x180031c30  mov     [rsp+110h+var_F0], rax
0x180031c35  mov     [rbp+57h+arg_10], 0
0x180031c3d  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180031c42  mov     rcx, rbx
0x180031c45  add     rsp, 100h
0x180031c4c  pop     rdi
0x180031c4d  pop     rbx
0x180031c4e  pop     rbp
0x180031c4f  jmp     ?IgnoreCurrentThread@?$ActivityBase@VWiFiCloudStoreTelemetry@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WiFiCloudStoreTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
