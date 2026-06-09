# LUATelemetry::AppXSyncActivity::StopActivity(void)

- ea: `0x180041210`
- end: `0x180041438`
- name: `?StopActivity@AppXSyncActivity@LUATelemetry@@MEAAXXZ`
- size: `552`
- prototype: `void __fastcall(LUATelemetry::AppXSyncActivity *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x18000c7d0`
- `0x18000cb30`
- `0x180010f8c`
- `0x180018d70`
- `0x18001fd6c`
- `0x18001fd94`
- `0x180041210`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800413d3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800413d3`

## pseudocode

```c
void __fastcall LUATelemetry::AppXSyncActivity::StopActivity(LUATelemetry::AppXSyncActivity *this)
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
        byte_18005390A,
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
        byte_1800537E2,
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
0x180041210  push    rbp
0x180041212  push    rbx
0x180041213  push    rdi
0x180041214  lea     rbp, [rsp-47h]
0x180041219  sub     rsp, 100h
0x180041220  mov     rax, [rcx+110h]
0x180041227  mov     rbx, rcx
0x18004122a  mov     ecx, [rax+48h]
0x18004122d  test    ecx, ecx
0x18004122f  jns     loc_1800413A7
0x180041235  cmp     ecx, [rax+58h]
0x180041238  jnz     loc_1800413A7
0x18004123e  lea     rdi, [rax+50h]
0x180041242  test    rdi, rdi
0x180041245  jz      loc_1800413A7
0x18004124b  mov     rcx, rbx
0x18004124e  call    ?zInternalStop@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180041253  call    ?Instance@LUATelemetry@@KAPEAV1@XZ; LUATelemetry::Instance(void)
0x180041258  mov     rcx, [rax+8]
0x18004125c  cmp     dword ptr [rcx], 5
0x18004125f  jbe     loc_180041426
0x180041265  mov     rdx, 400000000000h
0x18004126f  call    _tlgKeywordOn
0x180041274  test    al, al
0x180041276  jz      loc_180041426
0x18004127c  mov     rax, [rdi+78h]
0x180041280  lea     rdx, byte_1800537E2
0x180041287  mov     r8, [rbx+110h]
0x18004128e  mov     [rbp+57h+var_68], rax
0x180041292  add     r8, 8
0x180041296  mov     rax, [rdi+70h]
0x18004129a  mov     [rbp+57h+var_60], rax
0x18004129e  mov     eax, [rdi+68h]
0x1800412a1  mov     [rbp+57h+arg_0], eax
0x1800412a4  mov     rax, [rdi+60h]
0x1800412a8  mov     [rbp+57h+var_58], rax
0x1800412ac  mov     rax, [rdi+58h]
0x1800412b0  mov     [rbp+57h+var_50], rax
0x1800412b4  mov     eax, [rdi+50h]
0x1800412b7  mov     [rbp+57h+arg_8], eax
0x1800412ba  mov     rax, [rdi+48h]
0x1800412be  mov     [rbp+57h+var_48], rax
0x1800412c2  mov     eax, [rdi+20h]
0x1800412c5  mov     dword ptr [rbp+57h+arg_10], eax
0x1800412c8  mov     rax, [rdi+18h]
0x1800412cc  mov     [rbp+57h+var_40], rax
0x1800412d0  mov     eax, [rdi]
0x1800412d2  mov     [rbp+57h+arg_18], eax
0x1800412d5  mov     rax, [rdi+80h]
0x1800412dc  mov     [rbp+57h+var_38], rax
0x1800412e0  mov     eax, [rdi+40h]
0x1800412e3  mov     [rbp+57h+var_70], eax
0x1800412e6  mov     rax, [rdi+38h]
0x1800412ea  mov     [rbp+57h+var_30], rax
0x1800412ee  mov     eax, [rdi+8]
0x1800412f1  mov     [rbp+57h+var_6C], eax
0x1800412f4  lea     rax, [rbp+57h+var_68]
0x1800412f8  mov     [rsp+110h+var_78], rax
0x180041300  lea     rax, [rbp+57h+var_60]
0x180041304  mov     [rsp+110h+var_80], rax
0x18004130c  lea     rax, [rbp+57h+arg_0]
0x180041310  mov     [rsp+110h+var_88], rax
0x180041318  lea     rax, [rbp+57h+var_58]
0x18004131c  mov     [rsp+110h+var_90], rax
0x180041324  lea     rax, [rbp+57h+var_50]
0x180041328  mov     [rsp+110h+var_98], rax
0x18004132d  lea     rax, [rbp+57h+arg_8]
0x180041331  mov     [rsp+110h+var_A0], rax
0x180041336  lea     rax, [rbp+57h+var_48]
0x18004133a  mov     [rsp+110h+var_A8], rax
0x18004133f  lea     rax, [rbp+57h+arg_10]
0x180041343  mov     [rsp+110h+var_B0], rax
0x180041348  lea     rax, [rbp+57h+var_40]
0x18004134c  mov     [rsp+110h+var_B8], rax
0x180041351  lea     rax, [rbp+57h+arg_18]
0x180041355  mov     [rsp+110h+var_C0], rax
0x18004135a  lea     rax, [rbp+57h+var_38]
0x18004135e  mov     [rsp+110h+var_C8], rax
0x180041363  lea     rax, [rbp+57h+var_70]
0x180041367  mov     [rsp+110h+var_D0], rax
0x18004136c  lea     rax, [rbp+57h+var_30]
0x180041370  mov     [rsp+110h+var_D8], rax
0x180041375  lea     rax, [rbp+57h+var_6C]
0x180041379  mov     [rsp+110h+var_E0], rax
0x18004137e  lea     rax, [rbp+57h+var_28]
0x180041382  mov     [rsp+110h+var_E8], rax
0x180041387  lea     rax, [rbp+57h+var_20]
0x18004138b  mov     [rsp+110h+var_F0], rax
0x180041390  mov     [rbp+57h+var_28], 1000000h
0x180041398  mov     [rbp+57h+var_20], 3000000h
0x1800413a0  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x1800413a5  jmp     short loc_180041426
0x1800413a7  mov     rcx, rbx
0x1800413aa  call    ?zInternalStop@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x1800413af  call    ?Instance@LUATelemetry@@KAPEAV1@XZ; LUATelemetry::Instance(void)
0x1800413b4  mov     rdi, [rax+8]
0x1800413b8  cmp     dword ptr [rdi], 5
0x1800413bb  jbe     short loc_180041426
0x1800413bd  mov     rdx, 400000000000h
0x1800413c7  mov     rcx, rdi
0x1800413ca  call    _tlgKeywordOn
0x1800413cf  test    al, al
0x1800413d1  jz      short loc_180041426
0x1800413d3  call    cs:__imp_GetCurrentThreadId
0x1800413da  nop     dword ptr [rax+rax+00h]
0x1800413df  mov     r8, [rbx+110h]
0x1800413e6  lea     rdx, byte_18005390A
0x1800413ed  mov     [rbp+57h+arg_0], eax
0x1800413f0  mov     rcx, rdi
0x1800413f3  mov     eax, [r8+48h]
0x1800413f7  add     r8, 8
0x1800413fb  mov     [rbp+57h+arg_8], eax
0x1800413fe  lea     rax, [rbp+57h+arg_0]
0x180041402  mov     [rsp+110h+var_E0], rax
0x180041407  lea     rax, [rbp+57h+arg_8]
0x18004140b  mov     [rsp+110h+var_E8], rax
0x180041410  lea     rax, [rbp+57h+arg_10]
0x180041414  mov     [rsp+110h+var_F0], rax
0x180041419  mov     [rbp+57h+arg_10], 3000000h
0x180041421  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180041426  mov     rcx, rbx
0x180041429  add     rsp, 100h
0x180041430  pop     rdi
0x180041431  pop     rbx
0x180041432  pop     rbp
0x180041433  jmp     ?IgnoreCurrentThread@?$ActivityBase@VLUATelemetry@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
