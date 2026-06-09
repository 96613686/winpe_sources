# CredUXTelemetry::AcceptCredentialsOrCancelActivity::StopActivity(void)

- ea: `0x1400156b0`
- end: `0x1400158d4`
- name: `?StopActivity@AcceptCredentialsOrCancelActivity@CredUXTelemetry@@MEAAXXZ`
- size: `548`
- prototype: `void __fastcall(CredUXTelemetry::AcceptCredentialsOrCancelActivity *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14000177c`
- `0x1400023e0`
- `0x140002f8c`
- `0x14000e620`
- `0x140011a60`
- `0x1400156b0`
- `0x14001c16c`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140015875`
- `KERNEL32!GetCurrentThreadId` at `0x140015875`

## pseudocode

```c
void __fastcall CredUXTelemetry::AcceptCredentialsOrCancelActivity::StopActivity(
        CredUXTelemetry::AcceptCredentialsOrCancelActivity *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  const struct _tlgProvider_t *v5; // rax
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // r9
  const unsigned __int16 *v9; // rcx
  __int64 v10; // r8
  const struct _tlgProvider_t *v11; // rax
  __int64 v12; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v14; // r8
  __int64 v15; // r9
  int v16; // [rsp+A0h] [rbp-19h] BYREF
  int v17; // [rsp+A4h] [rbp-15h] BYREF
  const unsigned __int16 *v18; // [rsp+A8h] [rbp-11h] BYREF
  const unsigned __int16 *v19; // [rsp+B0h] [rbp-9h] BYREF
  const unsigned __int16 *v20; // [rsp+B8h] [rbp-1h] BYREF
  const unsigned __int16 *v21; // [rsp+C0h] [rbp+7h] BYREF
  const unsigned __int16 *v22; // [rsp+C8h] [rbp+Fh] BYREF
  const unsigned __int16 *v23; // [rsp+D0h] [rbp+17h] BYREF
  const unsigned __int16 *v24; // [rsp+D8h] [rbp+1Fh] BYREF
  const unsigned __int16 *v25; // [rsp+E0h] [rbp+27h] BYREF
  __int64 v26; // [rsp+E8h] [rbp+2Fh] BYREF
  __int64 v27[4]; // [rsp+F0h] [rbp+37h] BYREF
  DWORD v28; // [rsp+120h] [rbp+67h] BYREF
  int v29; // [rsp+128h] [rbp+6Fh] BYREF
  __int64 v30; // [rsp+130h] [rbp+77h] BYREF
  int v31; // [rsp+138h] [rbp+7Fh] BYREF

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = (int *)(v1 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v5 = CredUXLogging::Provider();
    v8 = (__int64)v5;
    if ( *(_DWORD *)v5 > 5u && (unsigned __int8)tlgKeywordOn(v5, 0x200000000000LL, v7, v5) )
    {
      v9 = (const unsigned __int16 *)*((_QWORD *)v4 + 15);
      v10 = *((_QWORD *)this + 34);
      v19 = (const unsigned __int16 *)*((_QWORD *)v4 + 14);
      v28 = v4[26];
      v20 = (const unsigned __int16 *)*((_QWORD *)v4 + 12);
      v21 = (const unsigned __int16 *)*((_QWORD *)v4 + 11);
      v29 = v4[20];
      v22 = (const unsigned __int16 *)*((_QWORD *)v4 + 9);
      LODWORD(v30) = v4[8];
      v23 = (const unsigned __int16 *)*((_QWORD *)v4 + 3);
      v31 = *v4;
      v24 = (const unsigned __int16 *)*((_QWORD *)v4 + 16);
      v16 = v4[16];
      v25 = (const unsigned __int16 *)*((_QWORD *)v4 + 7);
      v17 = v4[2];
      v18 = v9;
      v26 = 0x1000000;
      v27[0] = 50331648;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        v8,
        (__int64)&word_140026246,
        v10 + 8,
        v8,
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
    wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v11 = CredUXLogging::Provider();
    v12 = (__int64)v11;
    if ( *(_DWORD *)v11 > 5u && (unsigned __int8)tlgKeywordOn(v11, 0x200000000000LL, v7, v8) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v14 = *((_QWORD *)this + 34);
      v28 = CurrentThreadId;
      v29 = *(_DWORD *)(v14 + 72);
      v30 = 50331648;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v12,
        (__int64)byte_14002514D,
        v14 + 8,
        v15,
        (__int64)&v30,
        (__int64)&v29,
        (__int64)&v28);
    }
  }
  wil::ActivityBase<CredUIBrokerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
    this,
    v6,
    v7,
    v8);
}

```

## disassembly

```asm
0x1400156b0  push    rbp
0x1400156b2  push    rbx
0x1400156b3  push    rdi
0x1400156b4  lea     rbp, [rsp-47h]
0x1400156b9  sub     rsp, 100h
0x1400156c0  mov     rdi, [rcx+110h]
0x1400156c7  mov     rbx, rcx
0x1400156ca  mov     eax, [rdi+48h]
0x1400156cd  test    eax, eax
0x1400156cf  jns     loc_14001584B
0x1400156d5  add     rdi, 50h ; 'P'
0x1400156d9  cmp     eax, [rdi+8]
0x1400156dc  jnz     loc_14001584B
0x1400156e2  test    rdi, rdi
0x1400156e5  jz      loc_14001584B
0x1400156eb  call    ?zInternalStop@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x1400156f0  call    ?Provider@CredUXLogging@@SAPEBU_tlgProvider_t@@XZ; CredUXLogging::Provider(void)
0x1400156f5  mov     r9, rax
0x1400156f8  mov     ecx, [rax]
0x1400156fa  cmp     ecx, 5
0x1400156fd  jbe     loc_1400158C2
0x140015703  mov     rdx, 200000000000h
0x14001570d  mov     rcx, rax
0x140015710  call    _tlgKeywordOn
0x140015715  test    al, al
0x140015717  jz      loc_1400158C2
0x14001571d  mov     rax, [rdi+70h]
0x140015721  lea     rdx, word_140026246
0x140015728  mov     rcx, [rdi+78h]
0x14001572c  mov     r8, [rbx+110h]
0x140015733  mov     [rbp+57h+var_60], rax
0x140015737  add     r8, 8
0x14001573b  mov     eax, [rdi+68h]
0x14001573e  mov     [rbp+57h+arg_0], eax
0x140015741  mov     rax, [rdi+60h]
0x140015745  mov     [rbp+57h+var_58], rax
0x140015749  mov     rax, [rdi+58h]
0x14001574d  mov     [rbp+57h+var_50], rax
0x140015751  mov     eax, [rdi+50h]
0x140015754  mov     [rbp+57h+arg_8], eax
0x140015757  mov     rax, [rdi+48h]
0x14001575b  mov     [rbp+57h+var_48], rax
0x14001575f  mov     eax, [rdi+20h]
0x140015762  mov     dword ptr [rbp+57h+arg_10], eax
0x140015765  mov     rax, [rdi+18h]
0x140015769  mov     [rbp+57h+var_40], rax
0x14001576d  mov     eax, [rdi]
0x14001576f  mov     [rbp+57h+arg_18], eax
0x140015772  mov     rax, [rdi+80h]
0x140015779  mov     [rbp+57h+var_38], rax
0x14001577d  mov     eax, [rdi+40h]
0x140015780  mov     [rbp+57h+var_70], eax
0x140015783  mov     rax, [rdi+38h]
0x140015787  mov     [rbp+57h+var_30], rax
0x14001578b  mov     eax, [rdi+8]
0x14001578e  mov     [rbp+57h+var_6C], eax
0x140015791  lea     rax, [rbp+57h+var_68]
0x140015795  mov     [rsp+110h+var_78], rax
0x14001579d  lea     rax, [rbp+57h+var_60]
0x1400157a1  mov     [rsp+110h+var_80], rax
0x1400157a9  lea     rax, [rbp+57h+arg_0]
0x1400157ad  mov     [rsp+110h+var_88], rax
0x1400157b5  lea     rax, [rbp+57h+var_58]
0x1400157b9  mov     [rsp+110h+var_90], rax
0x1400157c1  lea     rax, [rbp+57h+var_50]
0x1400157c5  mov     [rsp+110h+var_98], rax
0x1400157ca  lea     rax, [rbp+57h+arg_8]
0x1400157ce  mov     [rsp+110h+var_A0], rax
0x1400157d3  lea     rax, [rbp+57h+var_48]
0x1400157d7  mov     [rsp+110h+var_A8], rax
0x1400157dc  lea     rax, [rbp+57h+arg_10]
0x1400157e0  mov     [rsp+110h+var_B0], rax
0x1400157e5  lea     rax, [rbp+57h+var_40]
0x1400157e9  mov     [rsp+110h+var_B8], rax
0x1400157ee  lea     rax, [rbp+57h+arg_18]
0x1400157f2  mov     [rsp+110h+var_C0], rax
0x1400157f7  lea     rax, [rbp+57h+var_38]
0x1400157fb  mov     [rsp+110h+var_C8], rax
0x140015800  lea     rax, [rbp+57h+var_70]
0x140015804  mov     [rsp+110h+var_D0], rax
0x140015809  lea     rax, [rbp+57h+var_30]
0x14001580d  mov     [rsp+110h+var_D8], rax
0x140015812  lea     rax, [rbp+57h+var_6C]
0x140015816  mov     [rsp+110h+var_E0], rax
0x14001581b  lea     rax, [rbp+57h+var_28]
0x14001581f  mov     [rsp+110h+var_E8], rax
0x140015824  lea     rax, [rbp+57h+var_20]
0x140015828  mov     [rbp+57h+var_68], rcx
0x14001582c  mov     rcx, r9
0x14001582f  mov     [rsp+110h+var_F0], rax
0x140015834  mov     [rbp+57h+var_28], 1000000h
0x14001583c  mov     [rbp+57h+var_20], 3000000h
0x140015844  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x140015849  jmp     short loc_1400158C2
0x14001584b  call    ?zInternalStop@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x140015850  call    ?Provider@CredUXLogging@@SAPEBU_tlgProvider_t@@XZ; CredUXLogging::Provider(void)
0x140015855  mov     rdi, rax
0x140015858  mov     ecx, [rax]
0x14001585a  cmp     ecx, 5
0x14001585d  jbe     short loc_1400158C2
0x14001585f  mov     rdx, 200000000000h
0x140015869  mov     rcx, rax
0x14001586c  call    _tlgKeywordOn
0x140015871  test    al, al
0x140015873  jz      short loc_1400158C2
0x140015875  call    cs:__imp_GetCurrentThreadId
0x14001587b  mov     r8, [rbx+110h]
0x140015882  lea     rdx, byte_14002514D
0x140015889  mov     [rbp+57h+arg_0], eax
0x14001588c  mov     rcx, rdi
0x14001588f  mov     eax, [r8+48h]
0x140015893  add     r8, 8
0x140015897  mov     [rbp+57h+arg_8], eax
0x14001589a  lea     rax, [rbp+57h+arg_0]
0x14001589e  mov     [rsp+110h+var_E0], rax
0x1400158a3  lea     rax, [rbp+57h+arg_8]
0x1400158a7  mov     [rsp+110h+var_E8], rax
0x1400158ac  lea     rax, [rbp+57h+arg_10]
0x1400158b0  mov     [rsp+110h+var_F0], rax
0x1400158b5  mov     [rbp+57h+arg_10], 3000000h
0x1400158bd  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1400158c2  mov     rcx, rbx
0x1400158c5  add     rsp, 100h
0x1400158cc  pop     rdi
0x1400158cd  pop     rbx
0x1400158ce  pop     rbp
0x1400158cf  jmp     ?IgnoreCurrentThread@?$ActivityBase@VCredUIBrokerLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CredUIBrokerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
