# Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryLookupExtensionPointImplementationAcid::Stop(ushort const *)

- ea: `0x18003a334`
- end: `0x18003a587`
- name: `?Stop@TryLookupExtensionPointImplementationAcid@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@QEAAXPEBG@Z`
- size: `595`
- prototype: `void __fastcall(Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryLookupExtensionPointImplementationAcid *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x18003b818`

## callees

- `0x1800024e4`
- `0x180003144`
- `0x18000f168`
- `0x180011fd0`
- `0x18001b03c`
- `0x1800384dc`
- `0x18003a334`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003a517`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003a517`

## pseudocode

```c
void __fastcall Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryLookupExtensionPointImplementationAcid::Stop(
        Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryLookupExtensionPointImplementationAcid *this,
        const unsigned __int16 *a2)
{
  __int64 v2; // rdi
  int v5; // eax
  int *v6; // rdi
  const struct _tlgProvider_t *v7; // rax
  __int64 v8; // r9
  __int64 v9; // r8
  const struct _tlgProvider_t *v10; // rax
  __int64 v11; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v13; // r8
  __int64 v14; // r9
  int v15; // [rsp+B0h] [rbp-80h] BYREF
  int v16; // [rsp+B4h] [rbp-7Ch] BYREF
  int v17; // [rsp+B8h] [rbp-78h] BYREF
  __int64 v18; // [rsp+C0h] [rbp-70h] BYREF
  const wchar_t *v19; // [rsp+C8h] [rbp-68h] BYREF
  const wchar_t *v20; // [rsp+D0h] [rbp-60h] BYREF
  const unsigned __int16 *v21; // [rsp+D8h] [rbp-58h] BYREF
  const wchar_t *v22; // [rsp+E0h] [rbp-50h] BYREF
  const unsigned __int16 *v23; // [rsp+E8h] [rbp-48h] BYREF
  const unsigned __int16 *v24; // [rsp+F0h] [rbp-40h] BYREF
  const wchar_t *v25; // [rsp+F8h] [rbp-38h] BYREF
  const unsigned __int16 *v26; // [rsp+100h] [rbp-30h] BYREF
  const unsigned __int16 *v27; // [rsp+108h] [rbp-28h] BYREF
  __int64 v28[4]; // [rsp+110h] [rbp-20h] BYREF
  DWORD v29; // [rsp+140h] [rbp+10h] BYREF
  int v30; // [rsp+150h] [rbp+20h] BYREF
  const wchar_t *v31; // [rsp+158h] [rbp+28h] BYREF

  v2 = *((_QWORD *)this + 34);
  v5 = *(_DWORD *)(v2 + 72);
  if ( v5 < 0 && (v6 = (int *)(v2 + 80), v5 == v6[2]) && v6 )
  {
    wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v7 = Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider();
    if ( *(_DWORD *)v7 > 5u && (unsigned __int8)tlgKeywordOn(v7, 0x200000000000LL) )
    {
      v9 = *((_QWORD *)this + 34);
      v20 = (const wchar_t *)*((_QWORD *)v6 + 15);
      v21 = (const unsigned __int16 *)*((_QWORD *)v6 + 14);
      v29 = v6[26];
      v22 = (const wchar_t *)*((_QWORD *)v6 + 12);
      v23 = (const unsigned __int16 *)*((_QWORD *)v6 + 11);
      v30 = v6[20];
      v24 = (const unsigned __int16 *)*((_QWORD *)v6 + 9);
      LODWORD(v31) = v6[8];
      v25 = (const wchar_t *)*((_QWORD *)v6 + 3);
      v15 = *v6;
      v26 = (const unsigned __int16 *)*((_QWORD *)v6 + 16);
      v16 = v6[16];
      v27 = (const unsigned __int16 *)*((_QWORD *)v6 + 7);
      v17 = v6[2];
      v19 = a2;
      v28[0] = 0x1000000;
      v18 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        v8,
        (__int64)word_180055FCA,
        v9 + 8,
        v8,
        (__int64)&v18,
        (__int64)v28,
        (__int64)&v17,
        &v27,
        (__int64)&v16,
        &v26,
        (__int64)&v15,
        &v25,
        (__int64)&v31,
        &v24,
        (__int64)&v30,
        &v23,
        &v22,
        (__int64)&v29,
        &v21,
        &v20,
        &v19);
    }
  }
  else
  {
    wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v10 = Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider();
    v11 = (__int64)v10;
    if ( *(_DWORD *)v10 > 5u && (unsigned __int8)tlgKeywordOn(v10, 0x200000000000LL) )
    {
      v31 = a2;
      CurrentThreadId = GetCurrentThreadId();
      v13 = *((_QWORD *)this + 34);
      v29 = CurrentThreadId;
      v30 = *(_DWORD *)(v13 + 72);
      v18 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
        v11,
        (__int64)&unk_180055B10,
        v13 + 8,
        v14,
        (__int64)&v18,
        (__int64)&v30,
        (__int64)&v29,
        &v31);
    }
  }
  wil::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(this);
}

```

## disassembly

```asm
0x18003a334  mov     [rsp-8+arg_8], rbx
0x18003a339  push    rbp
0x18003a33a  push    rsi
0x18003a33b  push    rdi
0x18003a33c  lea     rbp, [rsp+10h]
0x18003a341  sub     rsp, 120h
0x18003a348  mov     rdi, [rcx+110h]
0x18003a34f  mov     rsi, rdx
0x18003a352  mov     rbx, rcx
0x18003a355  mov     eax, [rdi+48h]
0x18003a358  test    eax, eax
0x18003a35a  jns     loc_18003A4E9
0x18003a360  add     rdi, 50h ; 'P'
0x18003a364  cmp     eax, [rdi+8]
0x18003a367  jnz     loc_18003A4E9
0x18003a36d  test    rdi, rdi
0x18003a370  jz      loc_18003A4E9
0x18003a376  call    ?zInternalStop@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18003a37b  call    ?Provider@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider(void)
0x18003a380  mov     r9, rax
0x18003a383  mov     ecx, [rax]
0x18003a385  cmp     ecx, 5
0x18003a388  jbe     loc_18003A56D
0x18003a38e  mov     rdx, 200000000000h
0x18003a398  mov     rcx, rax
0x18003a39b  call    _tlgKeywordOn
0x18003a3a0  test    al, al
0x18003a3a2  jz      loc_18003A56D
0x18003a3a8  mov     rax, [rdi+78h]
0x18003a3ac  lea     rdx, word_180055FCA
0x18003a3b3  mov     r8, [rbx+110h]
0x18003a3ba  mov     rcx, r9
0x18003a3bd  mov     [rbp+var_60], rax
0x18003a3c1  add     r8, 8
0x18003a3c5  mov     rax, [rdi+70h]
0x18003a3c9  mov     [rbp+var_58], rax
0x18003a3cd  mov     eax, [rdi+68h]
0x18003a3d0  mov     [rbp+arg_0], eax
0x18003a3d3  mov     rax, [rdi+60h]
0x18003a3d7  mov     [rbp+var_50], rax
0x18003a3db  mov     rax, [rdi+58h]
0x18003a3df  mov     [rbp+var_48], rax
0x18003a3e3  mov     eax, [rdi+50h]
0x18003a3e6  mov     [rbp+arg_10], eax
0x18003a3e9  mov     rax, [rdi+48h]
0x18003a3ed  mov     [rbp+var_40], rax
0x18003a3f1  mov     eax, [rdi+20h]
0x18003a3f4  mov     dword ptr [rbp+arg_18], eax
0x18003a3f7  mov     rax, [rdi+18h]
0x18003a3fb  mov     [rbp+var_38], rax
0x18003a3ff  mov     eax, [rdi]
0x18003a401  mov     [rbp+var_80], eax
0x18003a404  mov     rax, [rdi+80h]
0x18003a40b  mov     [rbp+var_30], rax
0x18003a40f  mov     eax, [rdi+40h]
0x18003a412  mov     [rbp+var_7C], eax
0x18003a415  mov     rax, [rdi+38h]
0x18003a419  mov     [rbp+var_28], rax
0x18003a41d  mov     eax, [rdi+8]
0x18003a420  mov     [rbp+var_78], eax
0x18003a423  lea     rax, [rbp+var_68]
0x18003a427  mov     [rsp+130h+var_90], rax
0x18003a42f  lea     rax, [rbp+var_60]
0x18003a433  mov     [rsp+130h+var_98], rax
0x18003a43b  lea     rax, [rbp+var_58]
0x18003a43f  mov     [rsp+130h+var_A0], rax
0x18003a447  lea     rax, [rbp+arg_0]
0x18003a44b  mov     [rsp+130h+var_A8], rax
0x18003a453  lea     rax, [rbp+var_50]
0x18003a457  mov     [rsp+130h+var_B0], rax
0x18003a45f  lea     rax, [rbp+var_48]
0x18003a463  mov     [rsp+130h+var_B8], rax
0x18003a468  lea     rax, [rbp+arg_10]
0x18003a46c  mov     [rsp+130h+var_C0], rax
0x18003a471  lea     rax, [rbp+var_40]
0x18003a475  mov     [rsp+130h+var_C8], rax
0x18003a47a  lea     rax, [rbp+arg_18]
0x18003a47e  mov     [rsp+130h+var_D0], rax
0x18003a483  lea     rax, [rbp+var_38]
0x18003a487  mov     [rsp+130h+var_D8], rax
0x18003a48c  lea     rax, [rbp+var_80]
0x18003a490  mov     [rsp+130h+var_E0], rax
0x18003a495  lea     rax, [rbp+var_30]
0x18003a499  mov     [rsp+130h+var_E8], rax
0x18003a49e  lea     rax, [rbp+var_7C]
0x18003a4a2  mov     [rsp+130h+var_F0], rax
0x18003a4a7  lea     rax, [rbp+var_28]
0x18003a4ab  mov     [rsp+130h+var_F8], rax
0x18003a4b0  lea     rax, [rbp+var_78]
0x18003a4b4  mov     [rsp+130h+var_100], rax
0x18003a4b9  lea     rax, [rbp+var_20]
0x18003a4bd  mov     [rsp+130h+var_108], rax
0x18003a4c2  lea     rax, [rbp+var_70]
0x18003a4c6  mov     [rsp+130h+var_110], rax
0x18003a4cb  mov     [rbp+var_68], rsi
0x18003a4cf  mov     [rbp+var_20], 1000000h
0x18003a4d7  mov     [rbp+var_70], 0
0x18003a4df  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@454564566@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18003a4e4  jmp     loc_18003A56D
0x18003a4e9  call    ?zInternalStop@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18003a4ee  call    ?Provider@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider(void)
0x18003a4f3  mov     rdi, rax
0x18003a4f6  mov     ecx, [rax]
0x18003a4f8  cmp     ecx, 5
0x18003a4fb  jbe     short loc_18003A56D
0x18003a4fd  mov     rdx, 200000000000h
0x18003a507  mov     rcx, rax
0x18003a50a  call    _tlgKeywordOn
0x18003a50f  test    al, al
0x18003a511  jz      short loc_18003A56D
0x18003a513  mov     [rbp+arg_18], rsi
0x18003a517  call    cs:__imp_GetCurrentThreadId
0x18003a51d  mov     r8, [rbx+110h]
0x18003a524  lea     rdx, unk_180055B10
0x18003a52b  mov     [rbp+arg_0], eax
0x18003a52e  mov     rcx, rdi
0x18003a531  mov     eax, [r8+48h]
0x18003a535  add     r8, 8
0x18003a539  mov     [rbp+arg_10], eax
0x18003a53c  lea     rax, [rbp+arg_18]
0x18003a540  mov     [rsp+130h+var_F8], rax
0x18003a545  lea     rax, [rbp+arg_0]
0x18003a549  mov     [rsp+130h+var_100], rax
0x18003a54e  lea     rax, [rbp+arg_10]
0x18003a552  mov     [rsp+130h+var_108], rax
0x18003a557  lea     rax, [rbp+var_70]
0x18003a55b  mov     [rsp+130h+var_110], rax
0x18003a560  mov     [rbp+var_70], 0
0x18003a568  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x18003a56d  mov     rcx, rbx
0x18003a570  mov     rbx, [rsp+130h+arg_8]
0x18003a578  add     rsp, 120h
0x18003a57f  pop     rdi
0x18003a580  pop     rsi
0x18003a581  pop     rbp
0x18003a582  jmp     ?IgnoreCurrentThread@?$ActivityBase@VLUATelemetry@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
