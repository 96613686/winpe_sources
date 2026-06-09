# Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::Stop(bool,bool,ushort const *)

- ea: `0x180037364`
- end: `0x18003760b`
- name: `?Stop@TryActivateContractExtension@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@QEAAX_N0PEBG@Z`
- size: `679`
- prototype: `void __fastcall(Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension *__hidden this, bool, bool, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180038760`

## callees

- `0x180002ec0`
- `0x18000329c`
- `0x18000cb30`
- `0x180010c48`
- `0x180018d70`
- `0x1800357d8`
- `0x180037364`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003757c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003757c`

## pseudocode

```c
void __fastcall Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::Stop(
        Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension *this,
        char a2,
        char a3,
        const unsigned __int16 *a4)
{
  int *v4; // rax
  int v9; // ecx
  int *v10; // rdi
  const struct _tlgProvider_t *v11; // rcx
  int v12; // ecx
  int v13; // r9d
  __int64 v14; // r8
  __int64 v15; // rax
  const struct _tlgProvider_t *v16; // rax
  int v17; // edi
  DWORD CurrentThreadId; // eax
  __int64 v19; // r8
  int v20; // eax
  int v21; // r9d
  _BYTE v22[4]; // [rsp+C0h] [rbp-80h] BYREF
  int v23; // [rsp+C4h] [rbp-7Ch] BYREF
  DWORD v24; // [rsp+C8h] [rbp-78h] BYREF
  int v25; // [rsp+CCh] [rbp-74h] BYREF
  int v26; // [rsp+D0h] [rbp-70h] BYREF
  int v27; // [rsp+D4h] [rbp-6Ch] BYREF
  int v28; // [rsp+D8h] [rbp-68h] BYREF
  __int64 v29; // [rsp+E0h] [rbp-60h] BYREF
  const unsigned __int16 *v30; // [rsp+E8h] [rbp-58h] BYREF
  const unsigned __int16 *v31; // [rsp+F0h] [rbp-50h] BYREF
  __int64 v32; // [rsp+F8h] [rbp-48h] BYREF
  __int64 v33; // [rsp+100h] [rbp-40h] BYREF
  __int64 v34; // [rsp+108h] [rbp-38h] BYREF
  __int64 v35; // [rsp+110h] [rbp-30h] BYREF
  __int64 v36; // [rsp+118h] [rbp-28h] BYREF
  __int64 v37; // [rsp+120h] [rbp-20h] BYREF
  __int64 v38; // [rsp+128h] [rbp-18h] BYREF
  __int64 v39; // [rsp+130h] [rbp-10h] BYREF
  char v40; // [rsp+160h] [rbp+20h] BYREF

  v4 = (int *)*((_QWORD *)this + 34);
  v9 = v4[18];
  if ( v9 >= 0 || v9 != v4[22] || (v10 = v4 + 20, v4 == (int *)-80LL) )
  {
    wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(this);
    v16 = Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider();
    v17 = (int)v16;
    if ( *(_DWORD *)v16 > 5u && (unsigned __int8)tlgKeywordOn(v16, 0x400000000000LL) )
    {
      v30 = a4;
      v40 = a3;
      v22[0] = a2;
      CurrentThreadId = GetCurrentThreadId();
      v19 = *((_QWORD *)this + 34);
      v24 = CurrentThreadId;
      v20 = *(_DWORD *)(v19 + 72);
      v29 = 0;
      v23 = v20;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapSz<unsigned short>>(
        v17,
        (unsigned int)&unk_180051620,
        v19 + 8,
        v21,
        (__int64)&v29,
        (__int64)&v23,
        (__int64)&v24,
        (__int64)v22,
        (__int64)&v40,
        (__int64)&v30);
    }
  }
  else
  {
    wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(this);
    v11 = Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider();
    if ( *(_DWORD *)v11 > 5u && (unsigned __int8)tlgKeywordOn(v11, 0x400000000000LL) )
    {
      v32 = *((_QWORD *)v10 + 15);
      v33 = *((_QWORD *)v10 + 14);
      v14 = *((_QWORD *)this + 34);
      v25 = v10[26];
      v15 = *((_QWORD *)v10 + 12);
      v30 = 0;
      v34 = v15;
      v35 = *((_QWORD *)v10 + 11);
      v26 = v10[20];
      v36 = *((_QWORD *)v10 + 9);
      v27 = v10[8];
      v37 = *((_QWORD *)v10 + 3);
      v28 = *v10;
      v38 = *((_QWORD *)v10 + 16);
      v23 = v10[16];
      v39 = *((_QWORD *)v10 + 7);
      v24 = v10[2];
      v31 = a4;
      v40 = a3;
      v22[0] = a2;
      v29 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapSz<unsigned short>>(
        v12,
        (unsigned int)&unk_1800523E1,
        v14 + 8,
        v13,
        (__int64)&v30,
        (__int64)&v29,
        (__int64)&v24,
        (__int64)&v39,
        (__int64)&v23,
        (__int64)&v38,
        (__int64)&v28,
        (__int64)&v37,
        (__int64)&v27,
        (__int64)&v36,
        (__int64)&v26,
        (__int64)&v35,
        (__int64)&v34,
        (__int64)&v25,
        (__int64)&v33,
        (__int64)&v32,
        (__int64)v22,
        (__int64)&v40,
        (__int64)&v31);
    }
  }
  wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x180037364  mov     [rsp-18h+arg_8], rbx
0x180037369  mov     [rsp-18h+arg_10], rsi
0x18003736e  mov     [rsp-18h+arg_18], rdi
0x180037373  push    rbp
0x180037374  push    r14
0x180037376  push    r15
0x180037378  mov     rbp, rsp
0x18003737b  sub     rsp, 140h
0x180037382  mov     rax, [rcx+110h]
0x180037389  mov     rbx, rcx
0x18003738c  mov     rsi, r9
0x18003738f  mov     r14b, r8b
0x180037392  mov     r15b, dl
0x180037395  mov     ecx, [rax+48h]
0x180037398  test    ecx, ecx
0x18003739a  jns     loc_180037541
0x1800373a0  cmp     ecx, [rax+58h]
0x1800373a3  jnz     loc_180037541
0x1800373a9  lea     rdi, [rax+50h]
0x1800373ad  test    rdi, rdi
0x1800373b0  jz      loc_180037541
0x1800373b6  mov     rcx, rbx
0x1800373b9  call    ?zInternalStop@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x1800373be  call    ?Provider@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider(void)
0x1800373c3  mov     rcx, rax
0x1800373c6  cmp     dword ptr [rax], 5
0x1800373c9  jbe     loc_1800375E7
0x1800373cf  mov     rdx, 400000000000h
0x1800373d9  call    _tlgKeywordOn
0x1800373de  test    al, al
0x1800373e0  jz      loc_1800375E7
0x1800373e6  mov     rax, [rdi+78h]
0x1800373ea  lea     rdx, unk_1800523E1
0x1800373f1  mov     [rbp+var_48], rax
0x1800373f5  mov     rax, [rdi+70h]
0x1800373f9  mov     [rbp+var_40], rax
0x1800373fd  mov     eax, [rdi+68h]
0x180037400  mov     r8, [rbx+110h]
0x180037407  mov     [rbp+var_74], eax
0x18003740a  add     r8, 8
0x18003740e  mov     rax, [rdi+60h]
0x180037412  and     [rbp+var_58], 0
0x180037417  mov     [rbp+var_38], rax
0x18003741b  mov     rax, [rdi+58h]
0x18003741f  mov     [rbp+var_30], rax
0x180037423  mov     eax, [rdi+50h]
0x180037426  mov     [rbp+var_70], eax
0x180037429  mov     rax, [rdi+48h]
0x18003742d  mov     [rbp+var_28], rax
0x180037431  mov     eax, [rdi+20h]
0x180037434  mov     [rbp+var_6C], eax
0x180037437  mov     rax, [rdi+18h]
0x18003743b  mov     [rbp+var_20], rax
0x18003743f  mov     eax, [rdi]
0x180037441  mov     [rbp+var_68], eax
0x180037444  mov     rax, [rdi+80h]
0x18003744b  mov     [rbp+var_18], rax
0x18003744f  mov     eax, [rdi+40h]
0x180037452  mov     [rbp+var_7C], eax
0x180037455  mov     rax, [rdi+38h]
0x180037459  mov     [rbp+var_10], rax
0x18003745d  mov     eax, [rdi+8]
0x180037460  mov     [rbp+var_78], eax
0x180037463  lea     rax, [rbp+var_50]
0x180037467  mov     [rsp+140h+var_90], rax
0x18003746f  lea     rax, [rbp+arg_0]
0x180037473  mov     [rsp+140h+var_98], rax
0x18003747b  lea     rax, [rbp+var_80]
0x18003747f  mov     [rsp+140h+var_A0], rax
0x180037487  lea     rax, [rbp+var_48]
0x18003748b  mov     [rsp+140h+var_A8], rax
0x180037493  lea     rax, [rbp+var_40]
0x180037497  mov     [rsp+140h+var_B0], rax
0x18003749f  lea     rax, [rbp+var_74]
0x1800374a3  mov     [rsp+140h+var_B8], rax
0x1800374ab  lea     rax, [rbp+var_38]
0x1800374af  mov     [rsp+140h+var_C0], rax
0x1800374b7  lea     rax, [rbp+var_30]
0x1800374bb  mov     [rsp+140h+var_C8], rax
0x1800374c0  lea     rax, [rbp+var_70]
0x1800374c4  mov     [rsp+140h+var_D0], rax
0x1800374c9  lea     rax, [rbp+var_28]
0x1800374cd  mov     [rsp+140h+var_D8], rax
0x1800374d2  lea     rax, [rbp+var_6C]
0x1800374d6  mov     [rsp+140h+var_E0], rax
0x1800374db  lea     rax, [rbp+var_20]
0x1800374df  mov     [rsp+140h+var_E8], rax
0x1800374e4  lea     rax, [rbp+var_68]
0x1800374e8  mov     [rsp+140h+var_F0], rax
0x1800374ed  lea     rax, [rbp+var_18]
0x1800374f1  mov     [rsp+140h+var_F8], rax
0x1800374f6  lea     rax, [rbp+var_7C]
0x1800374fa  mov     [rsp+140h+var_100], rax
0x1800374ff  lea     rax, [rbp+var_10]
0x180037503  mov     [rsp+140h+var_108], rax
0x180037508  lea     rax, [rbp+var_78]
0x18003750c  mov     [rsp+140h+var_110], rax
0x180037511  lea     rax, [rbp+var_60]
0x180037515  mov     [rsp+140h+var_118], rax
0x18003751a  lea     rax, [rbp+var_58]
0x18003751e  mov     [rsp+140h+var_120], rax
0x180037523  mov     [rbp+var_50], rsi
0x180037527  mov     [rbp+arg_0], r14b
0x18003752b  mov     [rbp+var_80], r15b
0x18003752f  mov     [rbp+var_60], 1000000h
0x180037537  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U?$_tlgWrapperByVal@$00@@U5@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456AEBU?$_tlgWrapperByVal@$00@@76@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapSz<ushort> const &)
0x18003753c  jmp     loc_1800375E7
0x180037541  mov     rcx, rbx
0x180037544  call    ?zInternalStop@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180037549  call    ?Provider@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider(void)
0x18003754e  mov     rdi, rax
0x180037551  cmp     dword ptr [rax], 5
0x180037554  jbe     loc_1800375E7
0x18003755a  mov     rdx, 400000000000h
0x180037564  mov     rcx, rax
0x180037567  call    _tlgKeywordOn
0x18003756c  test    al, al
0x18003756e  jz      short loc_1800375E7
0x180037570  mov     [rbp+var_58], rsi
0x180037574  mov     [rbp+arg_0], r14b
0x180037578  mov     [rbp+var_80], r15b
0x18003757c  call    cs:__imp_GetCurrentThreadId
0x180037583  nop     dword ptr [rax+rax+00h]
0x180037588  mov     r8, [rbx+110h]
0x18003758f  lea     rdx, unk_180051620
0x180037596  mov     [rbp+var_78], eax
0x180037599  mov     rcx, rdi
0x18003759c  mov     eax, [r8+48h]
0x1800375a0  add     r8, 8
0x1800375a4  and     [rbp+var_60], 0
0x1800375a9  mov     [rbp+var_7C], eax
0x1800375ac  lea     rax, [rbp+var_58]
0x1800375b0  mov     [rsp+140h+var_F8], rax
0x1800375b5  lea     rax, [rbp+arg_0]
0x1800375b9  mov     [rsp+140h+var_100], rax
0x1800375be  lea     rax, [rbp+var_80]
0x1800375c2  mov     [rsp+140h+var_108], rax
0x1800375c7  lea     rax, [rbp+var_78]
0x1800375cb  mov     [rsp+140h+var_110], rax
0x1800375d0  lea     rax, [rbp+var_7C]
0x1800375d4  mov     [rsp+140h+var_118], rax
0x1800375d9  lea     rax, [rbp+var_60]
0x1800375dd  mov     [rsp+140h+var_120], rax
0x1800375e2  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapperByVal@$00@@U3@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapperByVal@$00@@5AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapSz<ushort> const &)
0x1800375e7  mov     rcx, rbx
0x1800375ea  lea     r11, [rsp+140h+var_s0]
0x1800375f2  mov     rbx, [r11+28h]
0x1800375f6  mov     rsi, [r11+30h]
0x1800375fa  mov     rdi, [r11+38h]
0x1800375fe  mov     rsp, r11
0x180037601  pop     r15
0x180037603  pop     r14
0x180037605  pop     rbp
0x180037606  jmp     ?IgnoreCurrentThread@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
