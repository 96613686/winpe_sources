# WiFiCloudStoreTelemetry::CdsTriggeredWlanSync::Stop(WiFiCloudStoreTelemetryResult)

- ea: `0x1800112e4`
- end: `0x180011557`
- name: `?Stop@CdsTriggeredWlanSync@WiFiCloudStoreTelemetry@@QEAAXW4WiFiCloudStoreTelemetryResult@@@Z`
- size: `627`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180011210`

## callees

- `0x180001af4`
- `0x1800112e4`
- `0x180019e40`
- `0x18001c898`
- `0x18001cd90`
- `0x18001edd4`
- `0x1800202bc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800114de`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800114de`

## pseudocode

```c
__int64 __fastcall WiFiCloudStoreTelemetry::CdsTriggeredWlanSync::Stop(__int64 a1, int a2)
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
        (__int64)&word_180046086,
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
        (unsigned __int8 *)byte_1800461CB,
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
0x1800112e4  mov     [rsp-8+arg_8], rbx
0x1800112e9  push    rbp
0x1800112ea  push    rsi
0x1800112eb  push    rdi
0x1800112ec  lea     rbp, [rsp+10h]
0x1800112f1  sub     rsp, 120h
0x1800112f8  mov     rdi, [rcx+110h]
0x1800112ff  mov     esi, edx
0x180011301  mov     rbx, rcx
0x180011304  mov     eax, [rdi+48h]
0x180011307  test    eax, eax
0x180011309  jns     loc_1800114AA
0x18001130f  add     rdi, 50h ; 'P'
0x180011313  cmp     eax, [rdi+8]
0x180011316  jnz     loc_1800114AA
0x18001131c  test    rdi, rdi
0x18001131f  jz      loc_1800114AA
0x180011325  call    ?zInternalStop@?$ActivityBase@VWiFiCloudStoreTelemetry@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WiFiCloudStoreTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18001132a  call    ?Provider@WiFiCloudStoreTelemetry@@SAPEBU_tlgProvider_t@@XZ; WiFiCloudStoreTelemetry::Provider(void)
0x18001132f  mov     r9, rax
0x180011332  mov     ecx, [rax]
0x180011334  cmp     ecx, 5
0x180011337  jbe     loc_18001153D
0x18001133d  mov     rdx, 400000000000h
0x180011347  mov     rcx, rax
0x18001134a  call    _tlgKeywordOn
0x18001134f  test    al, al
0x180011351  jz      loc_18001153D
0x180011357  mov     rax, [rdi+78h]
0x18001135b  lea     rdx, word_180046086
0x180011362  mov     [rbp+var_60], rax
0x180011366  cmp     esi, 1
0x180011369  mov     rax, [rdi+70h]
0x18001136d  mov     rcx, r9
0x180011370  mov     r8, [rbx+110h]
0x180011377  setnz   [rbp+arg_0]
0x18001137b  mov     [rbp+var_58], rax
0x18001137f  add     r8, 8
0x180011383  mov     eax, [rdi+68h]
0x180011386  mov     [rbp+arg_18], eax
0x180011389  mov     rax, [rdi+60h]
0x18001138d  mov     [rbp+var_50], rax
0x180011391  mov     rax, [rdi+58h]
0x180011395  mov     [rbp+var_48], rax
0x180011399  mov     eax, [rdi+50h]
0x18001139c  mov     [rbp+var_7C], eax
0x18001139f  mov     rax, [rdi+48h]
0x1800113a3  mov     [rbp+var_40], rax
0x1800113a7  mov     eax, [rdi+20h]
0x1800113aa  mov     [rbp+var_78], eax
0x1800113ad  mov     rax, [rdi+18h]
0x1800113b1  mov     [rbp+var_38], rax
0x1800113b5  mov     eax, [rdi]
0x1800113b7  mov     [rbp+var_74], eax
0x1800113ba  mov     rax, [rdi+80h]
0x1800113c1  mov     [rbp+var_30], rax
0x1800113c5  mov     eax, [rdi+40h]
0x1800113c8  mov     [rbp+var_70], eax
0x1800113cb  mov     rax, [rdi+38h]
0x1800113cf  mov     [rbp+var_28], rax
0x1800113d3  mov     eax, [rdi+8]
0x1800113d6  mov     [rbp+var_80], eax
0x1800113d9  lea     rax, [rbp+arg_10]
0x1800113dd  mov     [rsp+130h+var_88], rax
0x1800113e5  lea     rax, [rbp+arg_0]
0x1800113e9  mov     [rsp+130h+var_90], rax
0x1800113f1  lea     rax, [rbp+var_60]
0x1800113f5  mov     [rsp+130h+var_98], rax
0x1800113fd  lea     rax, [rbp+var_58]
0x180011401  mov     [rsp+130h+var_A0], rax
0x180011409  lea     rax, [rbp+arg_18]
0x18001140d  mov     [rsp+130h+var_A8], rax
0x180011415  lea     rax, [rbp+var_50]
0x180011419  mov     [rsp+130h+var_B0], rax
0x180011421  lea     rax, [rbp+var_48]
0x180011425  mov     [rsp+130h+var_B8], rax
0x18001142a  lea     rax, [rbp+var_7C]
0x18001142e  mov     [rsp+130h+var_C0], rax
0x180011433  lea     rax, [rbp+var_40]
0x180011437  mov     [rsp+130h+var_C8], rax
0x18001143c  lea     rax, [rbp+var_78]
0x180011440  mov     [rsp+130h+var_D0], rax
0x180011445  lea     rax, [rbp+var_38]
0x180011449  mov     [rsp+130h+var_D8], rax
0x18001144e  lea     rax, [rbp+var_74]
0x180011452  mov     [rsp+130h+var_E0], rax
0x180011457  lea     rax, [rbp+var_30]
0x18001145b  mov     [rsp+130h+var_E8], rax
0x180011460  lea     rax, [rbp+var_70]
0x180011464  mov     [rsp+130h+var_F0], rax
0x180011469  lea     rax, [rbp+var_28]
0x18001146d  mov     [rsp+130h+var_F8], rax
0x180011472  lea     rax, [rbp+var_80]
0x180011476  mov     [rsp+130h+var_100], rax
0x18001147b  lea     rax, [rbp+var_20]
0x18001147f  mov     [rsp+130h+var_108], rax
0x180011484  lea     rax, [rbp+var_68]
0x180011488  mov     [rsp+130h+var_110], rax
0x18001148d  mov     [rbp+arg_10], esi
0x180011490  mov     [rbp+var_20], 1000000h
0x180011498  mov     [rbp+var_68], 0
0x1800114a0  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U?$_tlgWrapperByVal@$00@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456AEBU?$_tlgWrapperByVal@$00@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<4> const &)
0x1800114a5  jmp     loc_18001153D
0x1800114aa  call    ?zInternalStop@?$ActivityBase@VWiFiCloudStoreTelemetry@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WiFiCloudStoreTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x1800114af  call    ?Provider@WiFiCloudStoreTelemetry@@SAPEBU_tlgProvider_t@@XZ; WiFiCloudStoreTelemetry::Provider(void)
0x1800114b4  mov     rdi, rax
0x1800114b7  mov     ecx, [rax]
0x1800114b9  cmp     ecx, 5
0x1800114bc  jbe     short loc_18001153D
0x1800114be  mov     rdx, 400000000000h
0x1800114c8  mov     rcx, rax
0x1800114cb  call    _tlgKeywordOn
0x1800114d0  test    al, al
0x1800114d2  jz      short loc_18001153D
0x1800114d4  cmp     esi, 1
0x1800114d7  mov     [rbp+arg_10], esi
0x1800114da  setnz   [rbp+arg_0]
0x1800114de  call    cs:__imp_GetCurrentThreadId
0x1800114e4  mov     r8, [rbx+110h]
0x1800114eb  lea     rdx, byte_1800461CB
0x1800114f2  mov     [rbp+arg_18], eax
0x1800114f5  mov     rcx, rdi
0x1800114f8  mov     eax, [r8+48h]
0x1800114fc  add     r8, 8
0x180011500  mov     [rbp+var_80], eax
0x180011503  lea     rax, [rbp+arg_10]
0x180011507  mov     [rsp+130h+var_F0], rax
0x18001150c  lea     rax, [rbp+arg_0]
0x180011510  mov     [rsp+130h+var_F8], rax
0x180011515  lea     rax, [rbp+arg_18]
0x180011519  mov     [rsp+130h+var_100], rax
0x18001151e  lea     rax, [rbp+var_80]
0x180011522  mov     [rsp+130h+var_108], rax
0x180011527  lea     rax, [rbp+var_68]
0x18001152b  mov     [rsp+130h+var_110], rax
0x180011530  mov     [rbp+var_68], 0
0x180011538  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapperByVal@$00@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapperByVal@$00@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<4> const &)
0x18001153d  mov     rcx, rbx
0x180011540  mov     rbx, [rsp+130h+arg_8]
0x180011548  add     rsp, 120h
0x18001154f  pop     rdi
0x180011550  pop     rsi
0x180011551  pop     rbp
0x180011552  jmp     ?IgnoreCurrentThread@?$ActivityBase@VWiFiCloudStoreTelemetry@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WiFiCloudStoreTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
