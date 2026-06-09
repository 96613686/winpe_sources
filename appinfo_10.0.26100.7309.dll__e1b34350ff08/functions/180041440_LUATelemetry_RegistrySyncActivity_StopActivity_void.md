# LUATelemetry::RegistrySyncActivity::StopActivity(void)

- ea: `0x180041440`
- end: `0x180041668`
- name: `?StopActivity@RegistrySyncActivity@LUATelemetry@@MEAAXXZ`
- size: `552`
- prototype: `void __fastcall(LUATelemetry::RegistrySyncActivity *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callees

- `0x18000c7d0`
- `0x18000cb30`
- `0x180010f8c`
- `0x180018d70`
- `0x18001fd6c`
- `0x18001fd94`
- `0x180041440`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180041603`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180041603`

## pseudocode

```c
void __fastcall LUATelemetry::RegistrySyncActivity::StopActivity(LUATelemetry::RegistrySyncActivity *this)
{
  int *v1; // rax
  int v3; // ecx
  int *v4; // rdi
  _DWORD *v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // r9
  __int64 v8; // r8
  struct LUATelemetry *v9; // rax
  _DWORD *v10; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v12; // r8
  __int64 v13; // r9
  int v14; // [rsp+A0h] [rbp-19h] BYREF
  int v15; // [rsp+A4h] [rbp-15h] BYREF
  const wchar_t *v16; // [rsp+A8h] [rbp-11h] BYREF
  const unsigned __int16 *v17; // [rsp+B0h] [rbp-9h] BYREF
  const wchar_t *v18; // [rsp+B8h] [rbp-1h] BYREF
  const unsigned __int16 *v19; // [rsp+C0h] [rbp+7h] BYREF
  const unsigned __int16 *v20; // [rsp+C8h] [rbp+Fh] BYREF
  const wchar_t *v21; // [rsp+D0h] [rbp+17h] BYREF
  const unsigned __int16 *v22; // [rsp+D8h] [rbp+1Fh] BYREF
  const unsigned __int16 *v23; // [rsp+E0h] [rbp+27h] BYREF
  __int64 v24; // [rsp+E8h] [rbp+2Fh] BYREF
  __int64 v25[4]; // [rsp+F0h] [rbp+37h] BYREF
  DWORD v26; // [rsp+120h] [rbp+67h] BYREF
  int v27; // [rsp+128h] [rbp+6Fh] BYREF
  __int64 v28; // [rsp+130h] [rbp+77h] BYREF
  int v29; // [rsp+138h] [rbp+7Fh] BYREF

  v1 = (int *)*((_QWORD *)this + 34);
  v3 = v1[18];
  if ( v3 >= 0 || v3 != v1[22] || (v4 = v1 + 20, v1 == (int *)-80LL) )
  {
    wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(this);
    v9 = LUATelemetry::Instance();
    v10 = (_DWORD *)*((_QWORD *)v9 + 1);
    if ( *v10 > 5u && (unsigned __int8)tlgKeywordOn(*((_QWORD *)v9 + 1), 0x400000000000LL) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v12 = *((_QWORD *)this + 34);
      v26 = CurrentThreadId;
      v27 = *(_DWORD *)(v12 + 72);
      v28 = 50331648;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (__int64)v10,
        byte_18005378D,
        (const GUID *)(v12 + 8),
        v13,
        (__int64)&v28,
        (__int64)&v27,
        (__int64)&v26);
    }
  }
  else
  {
    wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(this);
    v5 = (_DWORD *)*((_QWORD *)LUATelemetry::Instance() + 1);
    if ( *v5 > 5u && (unsigned __int8)tlgKeywordOn(v5, 0x400000000000LL) )
    {
      v8 = *((_QWORD *)this + 34);
      v16 = (const wchar_t *)*((_QWORD *)v4 + 15);
      v17 = (const unsigned __int16 *)*((_QWORD *)v4 + 14);
      v26 = v4[26];
      v18 = (const wchar_t *)*((_QWORD *)v4 + 12);
      v19 = (const unsigned __int16 *)*((_QWORD *)v4 + 11);
      v27 = v4[20];
      v20 = (const unsigned __int16 *)*((_QWORD *)v4 + 9);
      LODWORD(v28) = v4[8];
      v21 = (const wchar_t *)*((_QWORD *)v4 + 3);
      v29 = *v4;
      v22 = (const unsigned __int16 *)*((_QWORD *)v4 + 16);
      v14 = v4[16];
      v23 = (const unsigned __int16 *)*((_QWORD *)v4 + 7);
      v15 = v4[2];
      v24 = 0x1000000;
      v25[0] = 50331648;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        v6,
        byte_180053C5F,
        (const GUID *)(v8 + 8),
        v7,
        (__int64)v25,
        (__int64)&v24,
        (__int64)&v15,
        &v23,
        (__int64)&v14,
        &v22,
        (__int64)&v29,
        &v21,
        (__int64)&v28,
        &v20,
        (__int64)&v27,
        &v19,
        &v18,
        (__int64)&v26,
        &v17,
        &v16);
    }
  }
  wil::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(this);
}

```

## disassembly

```asm
0x180041440  push    rbp
0x180041442  push    rbx
0x180041443  push    rdi
0x180041444  lea     rbp, [rsp-47h]
0x180041449  sub     rsp, 100h
0x180041450  mov     rax, [rcx+110h]
0x180041457  mov     rbx, rcx
0x18004145a  mov     ecx, [rax+48h]
0x18004145d  test    ecx, ecx
0x18004145f  jns     loc_1800415D7
0x180041465  cmp     ecx, [rax+58h]
0x180041468  jnz     loc_1800415D7
0x18004146e  lea     rdi, [rax+50h]
0x180041472  test    rdi, rdi
0x180041475  jz      loc_1800415D7
0x18004147b  mov     rcx, rbx
0x18004147e  call    ?zInternalStop@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180041483  call    ?Instance@LUATelemetry@@KAPEAV1@XZ; LUATelemetry::Instance(void)
0x180041488  mov     rcx, [rax+8]
0x18004148c  cmp     dword ptr [rcx], 5
0x18004148f  jbe     loc_180041656
0x180041495  mov     rdx, 400000000000h
0x18004149f  call    _tlgKeywordOn
0x1800414a4  test    al, al
0x1800414a6  jz      loc_180041656
0x1800414ac  mov     rax, [rdi+78h]
0x1800414b0  lea     rdx, byte_180053C5F
0x1800414b7  mov     r8, [rbx+110h]
0x1800414be  mov     [rbp+57h+var_68], rax
0x1800414c2  add     r8, 8
0x1800414c6  mov     rax, [rdi+70h]
0x1800414ca  mov     [rbp+57h+var_60], rax
0x1800414ce  mov     eax, [rdi+68h]
0x1800414d1  mov     [rbp+57h+arg_0], eax
0x1800414d4  mov     rax, [rdi+60h]
0x1800414d8  mov     [rbp+57h+var_58], rax
0x1800414dc  mov     rax, [rdi+58h]
0x1800414e0  mov     [rbp+57h+var_50], rax
0x1800414e4  mov     eax, [rdi+50h]
0x1800414e7  mov     [rbp+57h+arg_8], eax
0x1800414ea  mov     rax, [rdi+48h]
0x1800414ee  mov     [rbp+57h+var_48], rax
0x1800414f2  mov     eax, [rdi+20h]
0x1800414f5  mov     dword ptr [rbp+57h+arg_10], eax
0x1800414f8  mov     rax, [rdi+18h]
0x1800414fc  mov     [rbp+57h+var_40], rax
0x180041500  mov     eax, [rdi]
0x180041502  mov     [rbp+57h+arg_18], eax
0x180041505  mov     rax, [rdi+80h]
0x18004150c  mov     [rbp+57h+var_38], rax
0x180041510  mov     eax, [rdi+40h]
0x180041513  mov     [rbp+57h+var_70], eax
0x180041516  mov     rax, [rdi+38h]
0x18004151a  mov     [rbp+57h+var_30], rax
0x18004151e  mov     eax, [rdi+8]
0x180041521  mov     [rbp+57h+var_6C], eax
0x180041524  lea     rax, [rbp+57h+var_68]
0x180041528  mov     [rsp+110h+var_78], rax
0x180041530  lea     rax, [rbp+57h+var_60]
0x180041534  mov     [rsp+110h+var_80], rax
0x18004153c  lea     rax, [rbp+57h+arg_0]
0x180041540  mov     [rsp+110h+var_88], rax
0x180041548  lea     rax, [rbp+57h+var_58]
0x18004154c  mov     [rsp+110h+var_90], rax
0x180041554  lea     rax, [rbp+57h+var_50]
0x180041558  mov     [rsp+110h+var_98], rax
0x18004155d  lea     rax, [rbp+57h+arg_8]
0x180041561  mov     [rsp+110h+var_A0], rax
0x180041566  lea     rax, [rbp+57h+var_48]
0x18004156a  mov     [rsp+110h+var_A8], rax
0x18004156f  lea     rax, [rbp+57h+arg_10]
0x180041573  mov     [rsp+110h+var_B0], rax
0x180041578  lea     rax, [rbp+57h+var_40]
0x18004157c  mov     [rsp+110h+var_B8], rax
0x180041581  lea     rax, [rbp+57h+arg_18]
0x180041585  mov     [rsp+110h+var_C0], rax
0x18004158a  lea     rax, [rbp+57h+var_38]
0x18004158e  mov     [rsp+110h+var_C8], rax
0x180041593  lea     rax, [rbp+57h+var_70]
0x180041597  mov     [rsp+110h+var_D0], rax
0x18004159c  lea     rax, [rbp+57h+var_30]
0x1800415a0  mov     [rsp+110h+var_D8], rax
0x1800415a5  lea     rax, [rbp+57h+var_6C]
0x1800415a9  mov     [rsp+110h+var_E0], rax
0x1800415ae  lea     rax, [rbp+57h+var_28]
0x1800415b2  mov     [rsp+110h+var_E8], rax
0x1800415b7  lea     rax, [rbp+57h+var_20]
0x1800415bb  mov     [rsp+110h+var_F0], rax
0x1800415c0  mov     [rbp+57h+var_28], 1000000h
0x1800415c8  mov     [rbp+57h+var_20], 3000000h
0x1800415d0  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x1800415d5  jmp     short loc_180041656
0x1800415d7  mov     rcx, rbx
0x1800415da  call    ?zInternalStop@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x1800415df  call    ?Instance@LUATelemetry@@KAPEAV1@XZ; LUATelemetry::Instance(void)
0x1800415e4  mov     rdi, [rax+8]
0x1800415e8  cmp     dword ptr [rdi], 5
0x1800415eb  jbe     short loc_180041656
0x1800415ed  mov     rdx, 400000000000h
0x1800415f7  mov     rcx, rdi
0x1800415fa  call    _tlgKeywordOn
0x1800415ff  test    al, al
0x180041601  jz      short loc_180041656
0x180041603  call    cs:__imp_GetCurrentThreadId
0x18004160a  nop     dword ptr [rax+rax+00h]
0x18004160f  mov     r8, [rbx+110h]
0x180041616  lea     rdx, byte_18005378D
0x18004161d  mov     [rbp+57h+arg_0], eax
0x180041620  mov     rcx, rdi
0x180041623  mov     eax, [r8+48h]
0x180041627  add     r8, 8
0x18004162b  mov     [rbp+57h+arg_8], eax
0x18004162e  lea     rax, [rbp+57h+arg_0]
0x180041632  mov     [rsp+110h+var_E0], rax
0x180041637  lea     rax, [rbp+57h+arg_8]
0x18004163b  mov     [rsp+110h+var_E8], rax
0x180041640  lea     rax, [rbp+57h+arg_10]
0x180041644  mov     [rsp+110h+var_F0], rax
0x180041649  mov     [rbp+57h+arg_10], 3000000h
0x180041651  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180041656  mov     rcx, rbx
0x180041659  add     rsp, 100h
0x180041660  pop     rdi
0x180041661  pop     rbx
0x180041662  pop     rbp
0x180041663  jmp     ?IgnoreCurrentThread@?$ActivityBase@VLUATelemetry@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
