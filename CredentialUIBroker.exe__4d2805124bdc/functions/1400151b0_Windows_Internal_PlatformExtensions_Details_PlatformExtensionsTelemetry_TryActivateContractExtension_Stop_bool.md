# Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::Stop(bool,bool,ushort const *)

- ea: `0x1400151b0`
- end: `0x140015445`
- name: `?Stop@TryActivateContractExtension@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@QEAAX_N0PEBG@Z`
- size: `661`
- prototype: `void __fastcall(Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension *__hidden this, bool, bool, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140016a54`

## callees

- `0x14000205c`
- `0x140002614`
- `0x140002f8c`
- `0x14000e620`
- `0x140011aa0`
- `0x1400151b0`
- `0x14001c16c`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1400153c6`
- `KERNEL32!GetCurrentThreadId` at `0x1400153c6`

## pseudocode

```c
void __fastcall Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::Stop(
        Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension *this,
        char a2,
        char a3,
        const unsigned __int16 *a4)
{
  __int64 v4; // rdi
  int v9; // eax
  int *v10; // rdi
  const struct _tlgProvider_t *v11; // rax
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // r9
  __int64 v15; // r8
  const struct _tlgProvider_t *v16; // rax
  __int64 v17; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v19; // r8
  __int64 v20; // r9
  _BYTE v21[4]; // [rsp+C0h] [rbp-80h] BYREF
  int v22; // [rsp+C4h] [rbp-7Ch] BYREF
  DWORD v23; // [rsp+C8h] [rbp-78h] BYREF
  int v24; // [rsp+CCh] [rbp-74h] BYREF
  int v25; // [rsp+D0h] [rbp-70h] BYREF
  int v26; // [rsp+D4h] [rbp-6Ch] BYREF
  int v27; // [rsp+D8h] [rbp-68h] BYREF
  __int64 v28; // [rsp+E0h] [rbp-60h] BYREF
  const unsigned __int16 *v29; // [rsp+E8h] [rbp-58h] BYREF
  const unsigned __int16 *v30; // [rsp+F0h] [rbp-50h] BYREF
  const unsigned __int16 *v31; // [rsp+F8h] [rbp-48h] BYREF
  const unsigned __int16 *v32; // [rsp+100h] [rbp-40h] BYREF
  const unsigned __int16 *v33; // [rsp+108h] [rbp-38h] BYREF
  const unsigned __int16 *v34; // [rsp+110h] [rbp-30h] BYREF
  const unsigned __int16 *v35; // [rsp+118h] [rbp-28h] BYREF
  const unsigned __int16 *v36; // [rsp+120h] [rbp-20h] BYREF
  const unsigned __int16 *v37; // [rsp+128h] [rbp-18h] BYREF
  const unsigned __int16 *v38; // [rsp+130h] [rbp-10h] BYREF
  char v39; // [rsp+180h] [rbp+40h] BYREF

  v4 = *((_QWORD *)this + 34);
  v9 = *(_DWORD *)(v4 + 72);
  if ( v9 < 0 && (v10 = (int *)(v4 + 80), v9 == v10[2]) && v10 )
  {
    wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v11 = Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider();
    v14 = (__int64)v11;
    if ( *(_DWORD *)v11 > 5u && (unsigned __int8)tlgKeywordOn(v11, 0x400000000000LL, v13, v11) )
    {
      v31 = (const unsigned __int16 *)*((_QWORD *)v10 + 15);
      v32 = (const unsigned __int16 *)*((_QWORD *)v10 + 14);
      v15 = *((_QWORD *)this + 34);
      v24 = v10[26];
      v33 = (const unsigned __int16 *)*((_QWORD *)v10 + 12);
      v34 = (const unsigned __int16 *)*((_QWORD *)v10 + 11);
      v25 = v10[20];
      v35 = (const unsigned __int16 *)*((_QWORD *)v10 + 9);
      v26 = v10[8];
      v36 = (const unsigned __int16 *)*((_QWORD *)v10 + 3);
      v27 = *v10;
      v37 = (const unsigned __int16 *)*((_QWORD *)v10 + 16);
      v22 = v10[16];
      v38 = (const unsigned __int16 *)*((_QWORD *)v10 + 7);
      v23 = v10[2];
      v30 = a4;
      v39 = a3;
      v21[0] = a2;
      v28 = 0x1000000;
      v29 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapSz<unsigned short>>(
        v14,
        (__int64)byte_1400254D3,
        v15 + 8,
        v14,
        (__int64)&v29,
        (__int64)&v28,
        (__int64)&v23,
        &v38,
        (__int64)&v22,
        &v37,
        (__int64)&v27,
        &v36,
        (__int64)&v26,
        &v35,
        (__int64)&v25,
        &v34,
        &v33,
        (__int64)&v24,
        &v32,
        &v31,
        (__int64)v21,
        (__int64)&v39,
        &v30);
    }
  }
  else
  {
    wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v16 = Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider();
    v17 = (__int64)v16;
    if ( *(_DWORD *)v16 > 5u && (unsigned __int8)tlgKeywordOn(v16, 0x400000000000LL, v13, v14) )
    {
      v29 = a4;
      v39 = a3;
      v21[0] = a2;
      CurrentThreadId = GetCurrentThreadId();
      v19 = *((_QWORD *)this + 34);
      v23 = CurrentThreadId;
      v22 = *(_DWORD *)(v19 + 72);
      v28 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapSz<unsigned short>>(
        v17,
        (__int64)byte_14002487D,
        v19 + 8,
        v20,
        (__int64)&v28,
        (__int64)&v22,
        (__int64)&v23,
        (__int64)v21,
        (__int64)&v39,
        &v29);
    }
  }
  wil::ActivityBase<CredUIBrokerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
    this,
    v12,
    v13,
    v14);
}

```

## disassembly

```asm
0x1400151b0  push    rbp
0x1400151b2  push    rbx
0x1400151b3  push    rsi
0x1400151b4  push    rdi
0x1400151b5  push    r14
0x1400151b7  push    r15
0x1400151b9  lea     rbp, [rsp-8]
0x1400151be  sub     rsp, 148h
0x1400151c5  mov     rdi, [rcx+110h]
0x1400151cc  mov     rsi, r9
0x1400151cf  mov     r14b, r8b
0x1400151d2  mov     r15b, dl
0x1400151d5  mov     rbx, rcx
0x1400151d8  mov     eax, [rdi+48h]
0x1400151db  test    eax, eax
0x1400151dd  jns     loc_14001538C
0x1400151e3  add     rdi, 50h ; 'P'
0x1400151e7  cmp     eax, [rdi+8]
0x1400151ea  jnz     loc_14001538C
0x1400151f0  test    rdi, rdi
0x1400151f3  jz      loc_14001538C
0x1400151f9  call    ?zInternalStop@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x1400151fe  call    ?Provider@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider(void)
0x140015203  mov     r9, rax
0x140015206  mov     ecx, [rax]
0x140015208  cmp     ecx, 5
0x14001520b  jbe     loc_14001542E
0x140015211  mov     rdx, 400000000000h
0x14001521b  mov     rcx, rax
0x14001521e  call    _tlgKeywordOn
0x140015223  test    al, al
0x140015225  jz      loc_14001542E
0x14001522b  mov     rax, [rdi+78h]
0x14001522f  lea     rdx, byte_1400254D3
0x140015236  mov     [rbp+30h+var_78], rax
0x14001523a  mov     rcx, r9
0x14001523d  mov     rax, [rdi+70h]
0x140015241  mov     [rbp+30h+var_70], rax
0x140015245  mov     eax, [rdi+68h]
0x140015248  mov     r8, [rbx+110h]
0x14001524f  mov     [rbp+30h+var_A4], eax
0x140015252  add     r8, 8
0x140015256  mov     rax, [rdi+60h]
0x14001525a  mov     [rbp+30h+var_68], rax
0x14001525e  mov     rax, [rdi+58h]
0x140015262  mov     [rbp+30h+var_60], rax
0x140015266  mov     eax, [rdi+50h]
0x140015269  mov     [rbp+30h+var_A0], eax
0x14001526c  mov     rax, [rdi+48h]
0x140015270  mov     [rbp+30h+var_58], rax
0x140015274  mov     eax, [rdi+20h]
0x140015277  mov     [rbp+30h+var_9C], eax
0x14001527a  mov     rax, [rdi+18h]
0x14001527e  mov     [rbp+30h+var_50], rax
0x140015282  mov     eax, [rdi]
0x140015284  mov     [rbp+30h+var_98], eax
0x140015287  mov     rax, [rdi+80h]
0x14001528e  mov     [rbp+30h+var_48], rax
0x140015292  mov     eax, [rdi+40h]
0x140015295  mov     [rbp+30h+var_AC], eax
0x140015298  mov     rax, [rdi+38h]
0x14001529c  mov     [rbp+30h+var_40], rax
0x1400152a0  mov     eax, [rdi+8]
0x1400152a3  mov     [rbp+30h+var_A8], eax
0x1400152a6  lea     rax, [rbp+30h+var_80]
0x1400152aa  mov     [rsp+170h+var_C0], rax
0x1400152b2  lea     rax, [rbp+30h+arg_0]
0x1400152b6  mov     [rsp+170h+var_C8], rax
0x1400152be  lea     rax, [rbp+30h+var_B0]
0x1400152c2  mov     [rsp+170h+var_D0], rax
0x1400152ca  lea     rax, [rbp+30h+var_78]
0x1400152ce  mov     [rsp+170h+var_D8], rax
0x1400152d6  lea     rax, [rbp+30h+var_70]
0x1400152da  mov     [rsp+170h+var_E0], rax
0x1400152e2  lea     rax, [rbp+30h+var_A4]
0x1400152e6  mov     [rsp+170h+var_E8], rax
0x1400152ee  lea     rax, [rbp+30h+var_68]
0x1400152f2  mov     [rsp+170h+var_F0], rax
0x1400152fa  lea     rax, [rbp+30h+var_60]
0x1400152fe  mov     [rsp+170h+var_F8], rax
0x140015303  lea     rax, [rbp+30h+var_A0]
0x140015307  mov     [rsp+170h+var_100], rax
0x14001530c  lea     rax, [rbp+30h+var_58]
0x140015310  mov     [rsp+170h+var_108], rax
0x140015315  lea     rax, [rbp+30h+var_9C]
0x140015319  mov     [rsp+170h+var_110], rax
0x14001531e  lea     rax, [rbp+30h+var_50]
0x140015322  mov     [rsp+170h+var_118], rax
0x140015327  lea     rax, [rbp+30h+var_98]
0x14001532b  mov     [rsp+170h+var_120], rax
0x140015330  lea     rax, [rbp+30h+var_48]
0x140015334  mov     [rsp+170h+var_128], rax
0x140015339  lea     rax, [rbp+30h+var_AC]
0x14001533d  mov     [rsp+170h+var_130], rax
0x140015342  lea     rax, [rbp+30h+var_40]
0x140015346  mov     [rsp+170h+var_138], rax
0x14001534b  lea     rax, [rbp+30h+var_A8]
0x14001534f  mov     [rsp+170h+var_140], rax
0x140015354  lea     rax, [rbp+30h+var_90]
0x140015358  mov     [rsp+170h+var_148], rax
0x14001535d  lea     rax, [rbp+30h+var_88]
0x140015361  mov     [rsp+170h+var_150], rax
0x140015366  mov     [rbp+30h+var_80], rsi
0x14001536a  mov     [rbp+30h+arg_0], r14b
0x14001536e  mov     [rbp+30h+var_B0], r15b
0x140015372  mov     [rbp+30h+var_90], 1000000h
0x14001537a  mov     [rbp+30h+var_88], 0
0x140015382  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U?$_tlgWrapperByVal@$00@@U5@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456AEBU?$_tlgWrapperByVal@$00@@76@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapSz<ushort> const &)
0x140015387  jmp     loc_14001542E
0x14001538c  call    ?zInternalStop@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x140015391  call    ?Provider@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider(void)
0x140015396  mov     rdi, rax
0x140015399  mov     ecx, [rax]
0x14001539b  cmp     ecx, 5
0x14001539e  jbe     loc_14001542E
0x1400153a4  mov     rdx, 400000000000h
0x1400153ae  mov     rcx, rax
0x1400153b1  call    _tlgKeywordOn
0x1400153b6  test    al, al
0x1400153b8  jz      short loc_14001542E
0x1400153ba  mov     [rbp+30h+var_88], rsi
0x1400153be  mov     [rbp+30h+arg_0], r14b
0x1400153c2  mov     [rbp+30h+var_B0], r15b
0x1400153c6  call    cs:__imp_GetCurrentThreadId
0x1400153cc  mov     r8, [rbx+110h]
0x1400153d3  lea     rdx, byte_14002487D
0x1400153da  mov     [rbp+30h+var_A8], eax
0x1400153dd  mov     rcx, rdi
0x1400153e0  mov     eax, [r8+48h]
0x1400153e4  add     r8, 8
0x1400153e8  mov     [rbp+30h+var_AC], eax
0x1400153eb  lea     rax, [rbp+30h+var_88]
0x1400153ef  mov     [rsp+170h+var_128], rax
0x1400153f4  lea     rax, [rbp+30h+arg_0]
0x1400153f8  mov     [rsp+170h+var_130], rax
0x1400153fd  lea     rax, [rbp+30h+var_B0]
0x140015401  mov     [rsp+170h+var_138], rax
0x140015406  lea     rax, [rbp+30h+var_A8]
0x14001540a  mov     [rsp+170h+var_140], rax
0x14001540f  lea     rax, [rbp+30h+var_AC]
0x140015413  mov     [rsp+170h+var_148], rax
0x140015418  lea     rax, [rbp+30h+var_90]
0x14001541c  mov     [rsp+170h+var_150], rax
0x140015421  mov     [rbp+30h+var_90], 0
0x140015429  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapperByVal@$00@@U3@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapperByVal@$00@@5AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapSz<ushort> const &)
0x14001542e  mov     rcx, rbx
0x140015431  add     rsp, 148h
0x140015438  pop     r15
0x14001543a  pop     r14
0x14001543c  pop     rdi
0x14001543d  pop     rsi
0x14001543e  pop     rbx
0x14001543f  pop     rbp
0x140015440  jmp     ?IgnoreCurrentThread@?$ActivityBase@VCredUIBrokerLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CredUIBrokerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
