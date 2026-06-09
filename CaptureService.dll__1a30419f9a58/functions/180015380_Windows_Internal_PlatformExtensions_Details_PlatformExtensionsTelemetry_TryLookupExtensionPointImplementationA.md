# Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryLookupExtensionPointImplementationAcid::Stop(ushort const *)

- ea: `0x180015380`
- end: `0x1800155d3`
- name: `?Stop@TryLookupExtensionPointImplementationAcid@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@QEAAXPEBG@Z`
- size: `595`
- prototype: `void __fastcall(Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryLookupExtensionPointImplementationAcid *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180017520`

## callees

- `0x180001484`
- `0x180001b14`
- `0x18000254c`
- `0x180011f74`
- `0x180013130`
- `0x180015380`
- `0x1800189ac`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180015563`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180015563`

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
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // r9
  __int64 v11; // r8
  const struct _tlgProvider_t *v12; // rax
  __int64 v13; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v15; // r8
  __int64 v16; // r9
  int v17; // [rsp+B0h] [rbp-80h] BYREF
  int v18; // [rsp+B4h] [rbp-7Ch] BYREF
  int v19; // [rsp+B8h] [rbp-78h] BYREF
  __int64 v20; // [rsp+C0h] [rbp-70h] BYREF
  __int64 *v21; // [rsp+C8h] [rbp-68h] BYREF
  __int64 *v22; // [rsp+D0h] [rbp-60h] BYREF
  const unsigned __int16 *v23; // [rsp+D8h] [rbp-58h] BYREF
  __int64 *v24; // [rsp+E0h] [rbp-50h] BYREF
  const unsigned __int16 *v25; // [rsp+E8h] [rbp-48h] BYREF
  const unsigned __int16 *v26; // [rsp+F0h] [rbp-40h] BYREF
  __int64 *v27; // [rsp+F8h] [rbp-38h] BYREF
  const unsigned __int16 *v28; // [rsp+100h] [rbp-30h] BYREF
  const unsigned __int16 *v29; // [rsp+108h] [rbp-28h] BYREF
  __int64 v30[4]; // [rsp+110h] [rbp-20h] BYREF
  DWORD v31; // [rsp+140h] [rbp+10h] BYREF
  int v32; // [rsp+150h] [rbp+20h] BYREF
  __int64 *v33; // [rsp+158h] [rbp+28h] BYREF

  v2 = *((_QWORD *)this + 34);
  v5 = *(_DWORD *)(v2 + 72);
  if ( v5 < 0 && (v6 = (int *)(v2 + 80), v5 == v6[2]) && v6 )
  {
    wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v7 = Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider();
    v10 = (__int64)v7;
    if ( *(_DWORD *)v7 > 5u && (unsigned __int8)tlgKeywordOn(v7, 0x200000000000LL, v9, v7) )
    {
      v11 = *((_QWORD *)this + 34);
      v22 = (__int64 *)*((_QWORD *)v6 + 15);
      v23 = (const unsigned __int16 *)*((_QWORD *)v6 + 14);
      v31 = v6[26];
      v24 = (__int64 *)*((_QWORD *)v6 + 12);
      v25 = (const unsigned __int16 *)*((_QWORD *)v6 + 11);
      v32 = v6[20];
      v26 = (const unsigned __int16 *)*((_QWORD *)v6 + 9);
      LODWORD(v33) = v6[8];
      v27 = (__int64 *)*((_QWORD *)v6 + 3);
      v17 = *v6;
      v28 = (const unsigned __int16 *)*((_QWORD *)v6 + 16);
      v18 = v6[16];
      v29 = (const unsigned __int16 *)*((_QWORD *)v6 + 7);
      v19 = v6[2];
      v21 = (__int64 *)a2;
      v30[0] = 0x1000000;
      v20 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        v10,
        (__int64)byte_180029013,
        v11 + 8,
        v10,
        (__int64)&v20,
        (__int64)v30,
        (__int64)&v19,
        &v29,
        (__int64)&v18,
        &v28,
        (__int64)&v17,
        &v27,
        (__int64)&v33,
        &v26,
        (__int64)&v32,
        &v25,
        &v24,
        (__int64)&v31,
        &v23,
        &v22,
        &v21);
    }
  }
  else
  {
    wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v12 = Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider();
    v13 = (__int64)v12;
    if ( *(_DWORD *)v12 > 5u && (unsigned __int8)tlgKeywordOn(v12, 0x200000000000LL, v9, v10) )
    {
      v33 = (__int64 *)a2;
      CurrentThreadId = GetCurrentThreadId();
      v15 = *((_QWORD *)this + 34);
      v31 = CurrentThreadId;
      v32 = *(_DWORD *)(v15 + 72);
      v20 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
        v13,
        (__int64)&unk_180029168,
        v15 + 8,
        v16,
        (__int64)&v20,
        (__int64)&v32,
        (__int64)&v31,
        &v33);
    }
  }
  wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
    this,
    v8,
    v9,
    v10);
}

```

## disassembly

```asm
0x180015380  mov     [rsp-8+arg_8], rbx
0x180015385  push    rbp
0x180015386  push    rsi
0x180015387  push    rdi
0x180015388  lea     rbp, [rsp+10h]
0x18001538d  sub     rsp, 120h
0x180015394  mov     rdi, [rcx+110h]
0x18001539b  mov     rsi, rdx
0x18001539e  mov     rbx, rcx
0x1800153a1  mov     eax, [rdi+48h]
0x1800153a4  test    eax, eax
0x1800153a6  jns     loc_180015535
0x1800153ac  add     rdi, 50h ; 'P'
0x1800153b0  cmp     eax, [rdi+8]
0x1800153b3  jnz     loc_180015535
0x1800153b9  test    rdi, rdi
0x1800153bc  jz      loc_180015535
0x1800153c2  call    ?zInternalStop@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x1800153c7  call    ?Provider@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider(void)
0x1800153cc  mov     r9, rax
0x1800153cf  mov     ecx, [rax]
0x1800153d1  cmp     ecx, 5
0x1800153d4  jbe     loc_1800155B9
0x1800153da  mov     rdx, 200000000000h
0x1800153e4  mov     rcx, rax
0x1800153e7  call    _tlgKeywordOn
0x1800153ec  test    al, al
0x1800153ee  jz      loc_1800155B9
0x1800153f4  mov     rax, [rdi+78h]
0x1800153f8  lea     rdx, byte_180029013
0x1800153ff  mov     r8, [rbx+110h]
0x180015406  mov     rcx, r9
0x180015409  mov     [rbp+var_60], rax
0x18001540d  add     r8, 8
0x180015411  mov     rax, [rdi+70h]
0x180015415  mov     [rbp+var_58], rax
0x180015419  mov     eax, [rdi+68h]
0x18001541c  mov     [rbp+arg_0], eax
0x18001541f  mov     rax, [rdi+60h]
0x180015423  mov     [rbp+var_50], rax
0x180015427  mov     rax, [rdi+58h]
0x18001542b  mov     [rbp+var_48], rax
0x18001542f  mov     eax, [rdi+50h]
0x180015432  mov     [rbp+arg_10], eax
0x180015435  mov     rax, [rdi+48h]
0x180015439  mov     [rbp+var_40], rax
0x18001543d  mov     eax, [rdi+20h]
0x180015440  mov     dword ptr [rbp+arg_18], eax
0x180015443  mov     rax, [rdi+18h]
0x180015447  mov     [rbp+var_38], rax
0x18001544b  mov     eax, [rdi]
0x18001544d  mov     [rbp+var_80], eax
0x180015450  mov     rax, [rdi+80h]
0x180015457  mov     [rbp+var_30], rax
0x18001545b  mov     eax, [rdi+40h]
0x18001545e  mov     [rbp+var_7C], eax
0x180015461  mov     rax, [rdi+38h]
0x180015465  mov     [rbp+var_28], rax
0x180015469  mov     eax, [rdi+8]
0x18001546c  mov     [rbp+var_78], eax
0x18001546f  lea     rax, [rbp+var_68]
0x180015473  mov     [rsp+130h+var_90], rax
0x18001547b  lea     rax, [rbp+var_60]
0x18001547f  mov     [rsp+130h+var_98], rax
0x180015487  lea     rax, [rbp+var_58]
0x18001548b  mov     [rsp+130h+var_A0], rax
0x180015493  lea     rax, [rbp+arg_0]
0x180015497  mov     [rsp+130h+var_A8], rax
0x18001549f  lea     rax, [rbp+var_50]
0x1800154a3  mov     [rsp+130h+var_B0], rax
0x1800154ab  lea     rax, [rbp+var_48]
0x1800154af  mov     [rsp+130h+var_B8], rax
0x1800154b4  lea     rax, [rbp+arg_10]
0x1800154b8  mov     [rsp+130h+var_C0], rax
0x1800154bd  lea     rax, [rbp+var_40]
0x1800154c1  mov     [rsp+130h+var_C8], rax
0x1800154c6  lea     rax, [rbp+arg_18]
0x1800154ca  mov     [rsp+130h+var_D0], rax
0x1800154cf  lea     rax, [rbp+var_38]
0x1800154d3  mov     [rsp+130h+var_D8], rax
0x1800154d8  lea     rax, [rbp+var_80]
0x1800154dc  mov     [rsp+130h+var_E0], rax
0x1800154e1  lea     rax, [rbp+var_30]
0x1800154e5  mov     [rsp+130h+var_E8], rax
0x1800154ea  lea     rax, [rbp+var_7C]
0x1800154ee  mov     [rsp+130h+var_F0], rax
0x1800154f3  lea     rax, [rbp+var_28]
0x1800154f7  mov     [rsp+130h+var_F8], rax
0x1800154fc  lea     rax, [rbp+var_78]
0x180015500  mov     [rsp+130h+var_100], rax
0x180015505  lea     rax, [rbp+var_20]
0x180015509  mov     [rsp+130h+var_108], rax
0x18001550e  lea     rax, [rbp+var_70]
0x180015512  mov     [rsp+130h+var_110], rax
0x180015517  mov     [rbp+var_68], rsi
0x18001551b  mov     [rbp+var_20], 1000000h
0x180015523  mov     [rbp+var_70], 0
0x18001552b  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@454564566@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x180015530  jmp     loc_1800155B9
0x180015535  call    ?zInternalStop@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18001553a  call    ?Provider@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider(void)
0x18001553f  mov     rdi, rax
0x180015542  mov     ecx, [rax]
0x180015544  cmp     ecx, 5
0x180015547  jbe     short loc_1800155B9
0x180015549  mov     rdx, 200000000000h
0x180015553  mov     rcx, rax
0x180015556  call    _tlgKeywordOn
0x18001555b  test    al, al
0x18001555d  jz      short loc_1800155B9
0x18001555f  mov     [rbp+arg_18], rsi
0x180015563  call    cs:__imp_GetCurrentThreadId
0x180015569  mov     r8, [rbx+110h]
0x180015570  lea     rdx, unk_180029168
0x180015577  mov     [rbp+arg_0], eax
0x18001557a  mov     rcx, rdi
0x18001557d  mov     eax, [r8+48h]
0x180015581  add     r8, 8
0x180015585  mov     [rbp+arg_10], eax
0x180015588  lea     rax, [rbp+arg_18]
0x18001558c  mov     [rsp+130h+var_F8], rax
0x180015591  lea     rax, [rbp+arg_0]
0x180015595  mov     [rsp+130h+var_100], rax
0x18001559a  lea     rax, [rbp+arg_10]
0x18001559e  mov     [rsp+130h+var_108], rax
0x1800155a3  lea     rax, [rbp+var_70]
0x1800155a7  mov     [rsp+130h+var_110], rax
0x1800155ac  mov     [rbp+var_70], 0
0x1800155b4  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x1800155b9  mov     rcx, rbx
0x1800155bc  mov     rbx, [rsp+130h+arg_8]
0x1800155c4  add     rsp, 120h
0x1800155cb  pop     rdi
0x1800155cc  pop     rsi
0x1800155cd  pop     rbp
0x1800155ce  jmp     ?IgnoreCurrentThread@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
