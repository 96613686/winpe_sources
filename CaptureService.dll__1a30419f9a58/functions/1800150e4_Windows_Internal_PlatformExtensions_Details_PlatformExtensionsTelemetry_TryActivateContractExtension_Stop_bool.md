# Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::Stop(bool,bool,ushort const *)

- ea: `0x1800150e4`
- end: `0x180015379`
- name: `?Stop@TryActivateContractExtension@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@QEAAX_N0PEBG@Z`
- size: `661`
- prototype: `void __fastcall(Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension *__hidden this, bool, bool, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180015d0c`

## callees

- `0x180001770`
- `0x180001bd4`
- `0x18000254c`
- `0x180011f74`
- `0x180013130`
- `0x1800150e4`
- `0x1800189ac`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800152fa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800152fa`

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
  __int64 *v29; // [rsp+E8h] [rbp-58h] BYREF
  __int64 *v30; // [rsp+F0h] [rbp-50h] BYREF
  __int64 *v31; // [rsp+F8h] [rbp-48h] BYREF
  const unsigned __int16 *v32; // [rsp+100h] [rbp-40h] BYREF
  __int64 *v33; // [rsp+108h] [rbp-38h] BYREF
  const unsigned __int16 *v34; // [rsp+110h] [rbp-30h] BYREF
  const unsigned __int16 *v35; // [rsp+118h] [rbp-28h] BYREF
  __int64 *v36; // [rsp+120h] [rbp-20h] BYREF
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
      v31 = (__int64 *)*((_QWORD *)v10 + 15);
      v32 = (const unsigned __int16 *)*((_QWORD *)v10 + 14);
      v15 = *((_QWORD *)this + 34);
      v24 = v10[26];
      v33 = (__int64 *)*((_QWORD *)v10 + 12);
      v34 = (const unsigned __int16 *)*((_QWORD *)v10 + 11);
      v25 = v10[20];
      v35 = (const unsigned __int16 *)*((_QWORD *)v10 + 9);
      v26 = v10[8];
      v36 = (__int64 *)*((_QWORD *)v10 + 3);
      v27 = *v10;
      v37 = (const unsigned __int16 *)*((_QWORD *)v10 + 16);
      v22 = v10[16];
      v38 = (const unsigned __int16 *)*((_QWORD *)v10 + 7);
      v23 = v10[2];
      v30 = (__int64 *)a4;
      v39 = a3;
      v21[0] = a2;
      v28 = 0x1000000;
      v29 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapSz<unsigned short>>(
        v14,
        (__int64)&word_1800291E6,
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
      v29 = (__int64 *)a4;
      v39 = a3;
      v21[0] = a2;
      CurrentThreadId = GetCurrentThreadId();
      v19 = *((_QWORD *)this + 34);
      v23 = CurrentThreadId;
      v22 = *(_DWORD *)(v19 + 72);
      v28 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapSz<unsigned short>>(
        v17,
        (__int64)word_18002935A,
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
  wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
    this,
    v12,
    v13,
    v14);
}

```

## disassembly

```asm
0x1800150e4  push    rbp
0x1800150e6  push    rbx
0x1800150e7  push    rsi
0x1800150e8  push    rdi
0x1800150e9  push    r14
0x1800150eb  push    r15
0x1800150ed  lea     rbp, [rsp-8]
0x1800150f2  sub     rsp, 148h
0x1800150f9  mov     rdi, [rcx+110h]
0x180015100  mov     rsi, r9
0x180015103  mov     r14b, r8b
0x180015106  mov     r15b, dl
0x180015109  mov     rbx, rcx
0x18001510c  mov     eax, [rdi+48h]
0x18001510f  test    eax, eax
0x180015111  jns     loc_1800152C0
0x180015117  add     rdi, 50h ; 'P'
0x18001511b  cmp     eax, [rdi+8]
0x18001511e  jnz     loc_1800152C0
0x180015124  test    rdi, rdi
0x180015127  jz      loc_1800152C0
0x18001512d  call    ?zInternalStop@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180015132  call    ?Provider@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider(void)
0x180015137  mov     r9, rax
0x18001513a  mov     ecx, [rax]
0x18001513c  cmp     ecx, 5
0x18001513f  jbe     loc_180015362
0x180015145  mov     rdx, 400000000000h
0x18001514f  mov     rcx, rax
0x180015152  call    _tlgKeywordOn
0x180015157  test    al, al
0x180015159  jz      loc_180015362
0x18001515f  mov     rax, [rdi+78h]
0x180015163  lea     rdx, word_1800291E6
0x18001516a  mov     [rbp+30h+var_78], rax
0x18001516e  mov     rcx, r9
0x180015171  mov     rax, [rdi+70h]
0x180015175  mov     [rbp+30h+var_70], rax
0x180015179  mov     eax, [rdi+68h]
0x18001517c  mov     r8, [rbx+110h]
0x180015183  mov     [rbp+30h+var_A4], eax
0x180015186  add     r8, 8
0x18001518a  mov     rax, [rdi+60h]
0x18001518e  mov     [rbp+30h+var_68], rax
0x180015192  mov     rax, [rdi+58h]
0x180015196  mov     [rbp+30h+var_60], rax
0x18001519a  mov     eax, [rdi+50h]
0x18001519d  mov     [rbp+30h+var_A0], eax
0x1800151a0  mov     rax, [rdi+48h]
0x1800151a4  mov     [rbp+30h+var_58], rax
0x1800151a8  mov     eax, [rdi+20h]
0x1800151ab  mov     [rbp+30h+var_9C], eax
0x1800151ae  mov     rax, [rdi+18h]
0x1800151b2  mov     [rbp+30h+var_50], rax
0x1800151b6  mov     eax, [rdi]
0x1800151b8  mov     [rbp+30h+var_98], eax
0x1800151bb  mov     rax, [rdi+80h]
0x1800151c2  mov     [rbp+30h+var_48], rax
0x1800151c6  mov     eax, [rdi+40h]
0x1800151c9  mov     [rbp+30h+var_AC], eax
0x1800151cc  mov     rax, [rdi+38h]
0x1800151d0  mov     [rbp+30h+var_40], rax
0x1800151d4  mov     eax, [rdi+8]
0x1800151d7  mov     [rbp+30h+var_A8], eax
0x1800151da  lea     rax, [rbp+30h+var_80]
0x1800151de  mov     [rsp+170h+var_C0], rax
0x1800151e6  lea     rax, [rbp+30h+arg_0]
0x1800151ea  mov     [rsp+170h+var_C8], rax
0x1800151f2  lea     rax, [rbp+30h+var_B0]
0x1800151f6  mov     [rsp+170h+var_D0], rax
0x1800151fe  lea     rax, [rbp+30h+var_78]
0x180015202  mov     [rsp+170h+var_D8], rax
0x18001520a  lea     rax, [rbp+30h+var_70]
0x18001520e  mov     [rsp+170h+var_E0], rax
0x180015216  lea     rax, [rbp+30h+var_A4]
0x18001521a  mov     [rsp+170h+var_E8], rax
0x180015222  lea     rax, [rbp+30h+var_68]
0x180015226  mov     [rsp+170h+var_F0], rax
0x18001522e  lea     rax, [rbp+30h+var_60]
0x180015232  mov     [rsp+170h+var_F8], rax
0x180015237  lea     rax, [rbp+30h+var_A0]
0x18001523b  mov     [rsp+170h+var_100], rax
0x180015240  lea     rax, [rbp+30h+var_58]
0x180015244  mov     [rsp+170h+var_108], rax
0x180015249  lea     rax, [rbp+30h+var_9C]
0x18001524d  mov     [rsp+170h+var_110], rax
0x180015252  lea     rax, [rbp+30h+var_50]
0x180015256  mov     [rsp+170h+var_118], rax
0x18001525b  lea     rax, [rbp+30h+var_98]
0x18001525f  mov     [rsp+170h+var_120], rax
0x180015264  lea     rax, [rbp+30h+var_48]
0x180015268  mov     [rsp+170h+var_128], rax
0x18001526d  lea     rax, [rbp+30h+var_AC]
0x180015271  mov     [rsp+170h+var_130], rax
0x180015276  lea     rax, [rbp+30h+var_40]
0x18001527a  mov     [rsp+170h+var_138], rax
0x18001527f  lea     rax, [rbp+30h+var_A8]
0x180015283  mov     [rsp+170h+var_140], rax
0x180015288  lea     rax, [rbp+30h+var_90]
0x18001528c  mov     [rsp+170h+var_148], rax
0x180015291  lea     rax, [rbp+30h+var_88]
0x180015295  mov     [rsp+170h+var_150], rax
0x18001529a  mov     [rbp+30h+var_80], rsi
0x18001529e  mov     [rbp+30h+arg_0], r14b
0x1800152a2  mov     [rbp+30h+var_B0], r15b
0x1800152a6  mov     [rbp+30h+var_90], 1000000h
0x1800152ae  mov     [rbp+30h+var_88], 0
0x1800152b6  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U?$_tlgWrapperByVal@$00@@U5@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456AEBU?$_tlgWrapperByVal@$00@@76@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapSz<ushort> const &)
0x1800152bb  jmp     loc_180015362
0x1800152c0  call    ?zInternalStop@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x1800152c5  call    ?Provider@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider(void)
0x1800152ca  mov     rdi, rax
0x1800152cd  mov     ecx, [rax]
0x1800152cf  cmp     ecx, 5
0x1800152d2  jbe     loc_180015362
0x1800152d8  mov     rdx, 400000000000h
0x1800152e2  mov     rcx, rax
0x1800152e5  call    _tlgKeywordOn
0x1800152ea  test    al, al
0x1800152ec  jz      short loc_180015362
0x1800152ee  mov     [rbp+30h+var_88], rsi
0x1800152f2  mov     [rbp+30h+arg_0], r14b
0x1800152f6  mov     [rbp+30h+var_B0], r15b
0x1800152fa  call    cs:__imp_GetCurrentThreadId
0x180015300  mov     r8, [rbx+110h]
0x180015307  lea     rdx, word_18002935A
0x18001530e  mov     [rbp+30h+var_A8], eax
0x180015311  mov     rcx, rdi
0x180015314  mov     eax, [r8+48h]
0x180015318  add     r8, 8
0x18001531c  mov     [rbp+30h+var_AC], eax
0x18001531f  lea     rax, [rbp+30h+var_88]
0x180015323  mov     [rsp+170h+var_128], rax
0x180015328  lea     rax, [rbp+30h+arg_0]
0x18001532c  mov     [rsp+170h+var_130], rax
0x180015331  lea     rax, [rbp+30h+var_B0]
0x180015335  mov     [rsp+170h+var_138], rax
0x18001533a  lea     rax, [rbp+30h+var_A8]
0x18001533e  mov     [rsp+170h+var_140], rax
0x180015343  lea     rax, [rbp+30h+var_AC]
0x180015347  mov     [rsp+170h+var_148], rax
0x18001534c  lea     rax, [rbp+30h+var_90]
0x180015350  mov     [rsp+170h+var_150], rax
0x180015355  mov     [rbp+30h+var_90], 0
0x18001535d  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapperByVal@$00@@U3@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapperByVal@$00@@5AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapSz<ushort> const &)
0x180015362  mov     rcx, rbx
0x180015365  add     rsp, 148h
0x18001536c  pop     r15
0x18001536e  pop     r14
0x180015370  pop     rdi
0x180015371  pop     rsi
0x180015372  pop     rbx
0x180015373  pop     rbp
0x180015374  jmp     ?IgnoreCurrentThread@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
