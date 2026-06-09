# Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryLookupExtensionPointImplementationAcid::Stop(ushort const *)

- ea: `0x180036f74`
- end: `0x1800371c9`
- name: `?Stop@TryLookupExtensionPointImplementationAcid@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@QEAAXPEBG@Z`
- size: `597`
- prototype: `void __fastcall(Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryLookupExtensionPointImplementationAcid *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x18003840c`

## callees

- `0x180002244`
- `0x1800031d8`
- `0x18000cb30`
- `0x180010b08`
- `0x180018ac0`
- `0x180035728`
- `0x180036f74`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180037156`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180037156`

## pseudocode

```c
void __fastcall Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryLookupExtensionPointImplementationAcid::Stop(
        Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryLookupExtensionPointImplementationAcid *this,
        const unsigned __int16 *a2)
{
  int *v2; // rax
  int v5; // ecx
  int *v6; // rdi
  const struct _tlgProvider_t *v7; // rax
  int v8; // r9d
  __int64 v9; // rax
  __int64 v10; // rcx
  __int64 v11; // r8
  const struct _tlgProvider_t *v12; // rax
  int v13; // edi
  DWORD CurrentThreadId; // eax
  __int64 v15; // r8
  int v16; // eax
  int v17; // r9d
  int v18; // [rsp+B0h] [rbp-80h] BYREF
  int v19; // [rsp+B4h] [rbp-7Ch] BYREF
  int v20; // [rsp+B8h] [rbp-78h] BYREF
  __int64 v21; // [rsp+C0h] [rbp-70h] BYREF
  const unsigned __int16 *v22; // [rsp+C8h] [rbp-68h] BYREF
  __int64 v23; // [rsp+D0h] [rbp-60h] BYREF
  __int64 v24; // [rsp+D8h] [rbp-58h] BYREF
  __int64 v25; // [rsp+E0h] [rbp-50h] BYREF
  __int64 v26; // [rsp+E8h] [rbp-48h] BYREF
  __int64 v27; // [rsp+F0h] [rbp-40h] BYREF
  __int64 v28; // [rsp+F8h] [rbp-38h] BYREF
  __int64 v29; // [rsp+100h] [rbp-30h] BYREF
  __int64 v30; // [rsp+108h] [rbp-28h] BYREF
  __int64 v31[4]; // [rsp+110h] [rbp-20h] BYREF
  DWORD v32; // [rsp+140h] [rbp+10h] BYREF
  int v33; // [rsp+150h] [rbp+20h] BYREF
  const unsigned __int16 *v34; // [rsp+158h] [rbp+28h] BYREF

  v2 = (int *)*((_QWORD *)this + 34);
  v5 = v2[18];
  if ( v5 >= 0 || v5 != v2[22] || (v6 = v2 + 20, v2 == (int *)-80LL) )
  {
    wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(this);
    v12 = Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider();
    v13 = (int)v12;
    if ( *(_DWORD *)v12 > 5u && (unsigned __int8)tlgKeywordOn(v12, 0x200000000000LL) )
    {
      v34 = a2;
      CurrentThreadId = GetCurrentThreadId();
      v15 = *((_QWORD *)this + 34);
      v32 = CurrentThreadId;
      v16 = *(_DWORD *)(v15 + 72);
      v21 = 0;
      v33 = v16;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
        v13,
        (unsigned int)&unk_180050113,
        v15 + 8,
        v17,
        (__int64)&v21,
        (__int64)&v33,
        (__int64)&v32,
        (__int64)&v34);
    }
  }
  else
  {
    wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(this);
    v7 = Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider();
    if ( *(_DWORD *)v7 > 5u && (unsigned __int8)tlgKeywordOn(v7, 0x200000000000LL) )
    {
      v9 = *((_QWORD *)v6 + 14);
      v10 = *((_QWORD *)v6 + 15);
      v11 = *((_QWORD *)this + 34);
      v21 = 0;
      v24 = v9;
      v32 = v6[26];
      v25 = *((_QWORD *)v6 + 12);
      v26 = *((_QWORD *)v6 + 11);
      v33 = v6[20];
      v27 = *((_QWORD *)v6 + 9);
      LODWORD(v34) = v6[8];
      v28 = *((_QWORD *)v6 + 3);
      v18 = *v6;
      v29 = *((_QWORD *)v6 + 16);
      v19 = v6[16];
      v30 = *((_QWORD *)v6 + 7);
      v20 = v6[2];
      v23 = v10;
      v22 = a2;
      v31[0] = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        v8,
        (unsigned int)&unk_1800505CD,
        v11 + 8,
        v8,
        (__int64)&v21,
        (__int64)v31,
        (__int64)&v20,
        (__int64)&v30,
        (__int64)&v19,
        (__int64)&v29,
        (__int64)&v18,
        (__int64)&v28,
        (__int64)&v34,
        (__int64)&v27,
        (__int64)&v33,
        (__int64)&v26,
        (__int64)&v25,
        (__int64)&v32,
        (__int64)&v24,
        (__int64)&v23,
        (__int64)&v22);
    }
  }
  wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x180036f74  mov     [rsp-8+arg_8], rbx
0x180036f79  push    rbp
0x180036f7a  push    rsi
0x180036f7b  push    rdi
0x180036f7c  lea     rbp, [rsp+10h]
0x180036f81  sub     rsp, 120h
0x180036f88  mov     rax, [rcx+110h]
0x180036f8f  mov     rbx, rcx
0x180036f92  mov     rsi, rdx
0x180036f95  mov     ecx, [rax+48h]
0x180036f98  test    ecx, ecx
0x180036f9a  jns     loc_180037127
0x180036fa0  cmp     ecx, [rax+58h]
0x180036fa3  jnz     loc_180037127
0x180036fa9  lea     rdi, [rax+50h]
0x180036fad  test    rdi, rdi
0x180036fb0  jz      loc_180037127
0x180036fb6  mov     rcx, rbx
0x180036fb9  call    ?zInternalStop@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180036fbe  call    ?Provider@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider(void)
0x180036fc3  mov     r9, rax
0x180036fc6  cmp     dword ptr [rax], 5
0x180036fc9  jbe     loc_1800371AF
0x180036fcf  mov     rdx, 200000000000h
0x180036fd9  mov     rcx, rax
0x180036fdc  call    _tlgKeywordOn
0x180036fe1  test    al, al
0x180036fe3  jz      loc_1800371AF
0x180036fe9  mov     rax, [rdi+70h]
0x180036fed  lea     rdx, unk_1800505CD
0x180036ff4  mov     rcx, [rdi+78h]
0x180036ff8  mov     r8, [rbx+110h]
0x180036fff  and     [rbp+var_70], 0
0x180037004  add     r8, 8
0x180037008  mov     [rbp+var_58], rax
0x18003700c  mov     eax, [rdi+68h]
0x18003700f  mov     [rbp+arg_0], eax
0x180037012  mov     rax, [rdi+60h]
0x180037016  mov     [rbp+var_50], rax
0x18003701a  mov     rax, [rdi+58h]
0x18003701e  mov     [rbp+var_48], rax
0x180037022  mov     eax, [rdi+50h]
0x180037025  mov     [rbp+arg_10], eax
0x180037028  mov     rax, [rdi+48h]
0x18003702c  mov     [rbp+var_40], rax
0x180037030  mov     eax, [rdi+20h]
0x180037033  mov     dword ptr [rbp+arg_18], eax
0x180037036  mov     rax, [rdi+18h]
0x18003703a  mov     [rbp+var_38], rax
0x18003703e  mov     eax, [rdi]
0x180037040  mov     [rbp+var_80], eax
0x180037043  mov     rax, [rdi+80h]
0x18003704a  mov     [rbp+var_30], rax
0x18003704e  mov     eax, [rdi+40h]
0x180037051  mov     [rbp+var_7C], eax
0x180037054  mov     rax, [rdi+38h]
0x180037058  mov     [rbp+var_28], rax
0x18003705c  mov     eax, [rdi+8]
0x18003705f  mov     [rbp+var_78], eax
0x180037062  lea     rax, [rbp+var_68]
0x180037066  mov     [rsp+130h+var_90], rax
0x18003706e  lea     rax, [rbp+var_60]
0x180037072  mov     [rsp+130h+var_98], rax
0x18003707a  lea     rax, [rbp+var_58]
0x18003707e  mov     [rsp+130h+var_A0], rax
0x180037086  lea     rax, [rbp+arg_0]
0x18003708a  mov     [rsp+130h+var_A8], rax
0x180037092  lea     rax, [rbp+var_50]
0x180037096  mov     [rsp+130h+var_B0], rax
0x18003709e  lea     rax, [rbp+var_48]
0x1800370a2  mov     [rsp+130h+var_B8], rax
0x1800370a7  lea     rax, [rbp+arg_10]
0x1800370ab  mov     [rsp+130h+var_C0], rax
0x1800370b0  lea     rax, [rbp+var_40]
0x1800370b4  mov     [rsp+130h+var_C8], rax
0x1800370b9  lea     rax, [rbp+arg_18]
0x1800370bd  mov     [rsp+130h+var_D0], rax
0x1800370c2  lea     rax, [rbp+var_38]
0x1800370c6  mov     [rsp+130h+var_D8], rax
0x1800370cb  lea     rax, [rbp+var_80]
0x1800370cf  mov     [rsp+130h+var_E0], rax
0x1800370d4  lea     rax, [rbp+var_30]
0x1800370d8  mov     [rsp+130h+var_E8], rax
0x1800370dd  lea     rax, [rbp+var_7C]
0x1800370e1  mov     [rsp+130h+var_F0], rax
0x1800370e6  lea     rax, [rbp+var_28]
0x1800370ea  mov     [rsp+130h+var_F8], rax
0x1800370ef  lea     rax, [rbp+var_78]
0x1800370f3  mov     [rsp+130h+var_100], rax
0x1800370f8  lea     rax, [rbp+var_20]
0x1800370fc  mov     [rsp+130h+var_108], rax
0x180037101  lea     rax, [rbp+var_70]
0x180037105  mov     [rbp+var_60], rcx
0x180037109  mov     rcx, r9
0x18003710c  mov     [rsp+130h+var_110], rax
0x180037111  mov     [rbp+var_68], rsi
0x180037115  mov     [rbp+var_20], 1000000h
0x18003711d  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@454564566@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x180037122  jmp     loc_1800371AF
0x180037127  mov     rcx, rbx
0x18003712a  call    ?zInternalStop@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18003712f  call    ?Provider@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider(void)
0x180037134  mov     rdi, rax
0x180037137  cmp     dword ptr [rax], 5
0x18003713a  jbe     short loc_1800371AF
0x18003713c  mov     rdx, 200000000000h
0x180037146  mov     rcx, rax
0x180037149  call    _tlgKeywordOn
0x18003714e  test    al, al
0x180037150  jz      short loc_1800371AF
0x180037152  mov     [rbp+arg_18], rsi
0x180037156  call    cs:__imp_GetCurrentThreadId
0x18003715d  nop     dword ptr [rax+rax+00h]
0x180037162  mov     r8, [rbx+110h]
0x180037169  lea     rdx, unk_180050113
0x180037170  mov     [rbp+arg_0], eax
0x180037173  mov     rcx, rdi
0x180037176  mov     eax, [r8+48h]
0x18003717a  add     r8, 8
0x18003717e  and     [rbp+var_70], 0
0x180037183  mov     [rbp+arg_10], eax
0x180037186  lea     rax, [rbp+arg_18]
0x18003718a  mov     [rsp+130h+var_F8], rax
0x18003718f  lea     rax, [rbp+arg_0]
0x180037193  mov     [rsp+130h+var_100], rax
0x180037198  lea     rax, [rbp+arg_10]
0x18003719c  mov     [rsp+130h+var_108], rax
0x1800371a1  lea     rax, [rbp+var_70]
0x1800371a5  mov     [rsp+130h+var_110], rax
0x1800371aa  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x1800371af  mov     rcx, rbx
0x1800371b2  mov     rbx, [rsp+130h+arg_8]
0x1800371ba  add     rsp, 120h
0x1800371c1  pop     rdi
0x1800371c2  pop     rsi
0x1800371c3  pop     rbp
0x1800371c4  jmp     ?IgnoreCurrentThread@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
