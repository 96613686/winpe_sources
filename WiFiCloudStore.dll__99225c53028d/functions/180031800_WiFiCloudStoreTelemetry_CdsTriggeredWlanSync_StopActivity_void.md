# WiFiCloudStoreTelemetry::CdsTriggeredWlanSync::StopActivity(void)

- ea: `0x180031800`
- end: `0x180031a24`
- name: `?StopActivity@CdsTriggeredWlanSync@WiFiCloudStoreTelemetry@@MEAAXXZ`
- size: `548`
- prototype: `void __fastcall(WiFiCloudStoreTelemetry::CdsTriggeredWlanSync *__hidden this)`
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
- `0x180031800`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800319c5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800319c5`

## pseudocode

```c
void __fastcall WiFiCloudStoreTelemetry::CdsTriggeredWlanSync::StopActivity(
        WiFiCloudStoreTelemetry::CdsTriggeredWlanSync *this)
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
        (__int64)byte_180046525,
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
        (__int64)byte_180046651,
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
0x180031800  push    rbp
0x180031802  push    rbx
0x180031803  push    rdi
0x180031804  lea     rbp, [rsp-47h]
0x180031809  sub     rsp, 100h
0x180031810  mov     rdi, [rcx+110h]
0x180031817  mov     rbx, rcx
0x18003181a  mov     eax, [rdi+48h]
0x18003181d  test    eax, eax
0x18003181f  jns     loc_18003199B
0x180031825  add     rdi, 50h ; 'P'
0x180031829  cmp     eax, [rdi+8]
0x18003182c  jnz     loc_18003199B
0x180031832  test    rdi, rdi
0x180031835  jz      loc_18003199B
0x18003183b  call    ?zInternalStop@?$ActivityBase@VWiFiCloudStoreTelemetry@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WiFiCloudStoreTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180031840  call    ?Provider@WiFiCloudStoreTelemetry@@SAPEBU_tlgProvider_t@@XZ; WiFiCloudStoreTelemetry::Provider(void)
0x180031845  mov     r9, rax
0x180031848  mov     ecx, [rax]
0x18003184a  cmp     ecx, 5
0x18003184d  jbe     loc_180031A12
0x180031853  mov     rdx, 400000000000h
0x18003185d  mov     rcx, rax
0x180031860  call    _tlgKeywordOn
0x180031865  test    al, al
0x180031867  jz      loc_180031A12
0x18003186d  mov     rax, [rdi+70h]
0x180031871  lea     rdx, byte_180046525
0x180031878  mov     rcx, [rdi+78h]
0x18003187c  mov     r8, [rbx+110h]
0x180031883  mov     [rbp+57h+var_60], rax
0x180031887  add     r8, 8
0x18003188b  mov     eax, [rdi+68h]
0x18003188e  mov     [rbp+57h+arg_0], eax
0x180031891  mov     rax, [rdi+60h]
0x180031895  mov     [rbp+57h+var_58], rax
0x180031899  mov     rax, [rdi+58h]
0x18003189d  mov     [rbp+57h+var_50], rax
0x1800318a1  mov     eax, [rdi+50h]
0x1800318a4  mov     [rbp+57h+arg_8], eax
0x1800318a7  mov     rax, [rdi+48h]
0x1800318ab  mov     [rbp+57h+var_48], rax
0x1800318af  mov     eax, [rdi+20h]
0x1800318b2  mov     dword ptr [rbp+57h+arg_10], eax
0x1800318b5  mov     rax, [rdi+18h]
0x1800318b9  mov     [rbp+57h+var_40], rax
0x1800318bd  mov     eax, [rdi]
0x1800318bf  mov     [rbp+57h+arg_18], eax
0x1800318c2  mov     rax, [rdi+80h]
0x1800318c9  mov     [rbp+57h+var_38], rax
0x1800318cd  mov     eax, [rdi+40h]
0x1800318d0  mov     [rbp+57h+var_70], eax
0x1800318d3  mov     rax, [rdi+38h]
0x1800318d7  mov     [rbp+57h+var_30], rax
0x1800318db  mov     eax, [rdi+8]
0x1800318de  mov     [rbp+57h+var_6C], eax
0x1800318e1  lea     rax, [rbp+57h+var_68]
0x1800318e5  mov     [rsp+110h+var_78], rax
0x1800318ed  lea     rax, [rbp+57h+var_60]
0x1800318f1  mov     [rsp+110h+var_80], rax
0x1800318f9  lea     rax, [rbp+57h+arg_0]
0x1800318fd  mov     [rsp+110h+var_88], rax
0x180031905  lea     rax, [rbp+57h+var_58]
0x180031909  mov     [rsp+110h+var_90], rax
0x180031911  lea     rax, [rbp+57h+var_50]
0x180031915  mov     [rsp+110h+var_98], rax
0x18003191a  lea     rax, [rbp+57h+arg_8]
0x18003191e  mov     [rsp+110h+var_A0], rax
0x180031923  lea     rax, [rbp+57h+var_48]
0x180031927  mov     [rsp+110h+var_A8], rax
0x18003192c  lea     rax, [rbp+57h+arg_10]
0x180031930  mov     [rsp+110h+var_B0], rax
0x180031935  lea     rax, [rbp+57h+var_40]
0x180031939  mov     [rsp+110h+var_B8], rax
0x18003193e  lea     rax, [rbp+57h+arg_18]
0x180031942  mov     [rsp+110h+var_C0], rax
0x180031947  lea     rax, [rbp+57h+var_38]
0x18003194b  mov     [rsp+110h+var_C8], rax
0x180031950  lea     rax, [rbp+57h+var_70]
0x180031954  mov     [rsp+110h+var_D0], rax
0x180031959  lea     rax, [rbp+57h+var_30]
0x18003195d  mov     [rsp+110h+var_D8], rax
0x180031962  lea     rax, [rbp+57h+var_6C]
0x180031966  mov     [rsp+110h+var_E0], rax
0x18003196b  lea     rax, [rbp+57h+var_28]
0x18003196f  mov     [rsp+110h+var_E8], rax
0x180031974  lea     rax, [rbp+57h+var_20]
0x180031978  mov     [rbp+57h+var_68], rcx
0x18003197c  mov     rcx, r9
0x18003197f  mov     [rsp+110h+var_F0], rax
0x180031984  mov     [rbp+57h+var_28], 1000000h
0x18003198c  mov     [rbp+57h+var_20], 0
0x180031994  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180031999  jmp     short loc_180031A12
0x18003199b  call    ?zInternalStop@?$ActivityBase@VWiFiCloudStoreTelemetry@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WiFiCloudStoreTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x1800319a0  call    ?Provider@WiFiCloudStoreTelemetry@@SAPEBU_tlgProvider_t@@XZ; WiFiCloudStoreTelemetry::Provider(void)
0x1800319a5  mov     rdi, rax
0x1800319a8  mov     ecx, [rax]
0x1800319aa  cmp     ecx, 5
0x1800319ad  jbe     short loc_180031A12
0x1800319af  mov     rdx, 400000000000h
0x1800319b9  mov     rcx, rax
0x1800319bc  call    _tlgKeywordOn
0x1800319c1  test    al, al
0x1800319c3  jz      short loc_180031A12
0x1800319c5  call    cs:__imp_GetCurrentThreadId
0x1800319cb  mov     r8, [rbx+110h]
0x1800319d2  lea     rdx, byte_180046651
0x1800319d9  mov     [rbp+57h+arg_0], eax
0x1800319dc  mov     rcx, rdi
0x1800319df  mov     eax, [r8+48h]
0x1800319e3  add     r8, 8
0x1800319e7  mov     [rbp+57h+arg_8], eax
0x1800319ea  lea     rax, [rbp+57h+arg_0]
0x1800319ee  mov     [rsp+110h+var_E0], rax
0x1800319f3  lea     rax, [rbp+57h+arg_8]
0x1800319f7  mov     [rsp+110h+var_E8], rax
0x1800319fc  lea     rax, [rbp+57h+arg_10]
0x180031a00  mov     [rsp+110h+var_F0], rax
0x180031a05  mov     [rbp+57h+arg_10], 0
0x180031a0d  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180031a12  mov     rcx, rbx
0x180031a15  add     rsp, 100h
0x180031a1c  pop     rdi
0x180031a1d  pop     rbx
0x180031a1e  pop     rbp
0x180031a1f  jmp     ?IgnoreCurrentThread@?$ActivityBase@VWiFiCloudStoreTelemetry@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WiFiCloudStoreTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
