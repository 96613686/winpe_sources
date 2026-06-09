# LUATelemetry::AppXSyncActivity::StopActivity(void)

- ea: `0x18003f640`
- end: `0x18003f868`
- name: `?StopActivity@AppXSyncActivity@LUATelemetry@@MEAAXXZ`
- size: `552`
- prototype: `void __fastcall(LUATelemetry::AppXSyncActivity *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x18000c7d0`
- `0x18000cb30`
- `0x180010e4c`
- `0x180018ac0`
- `0x180020fe0`
- `0x180021008`
- `0x18003f640`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003f803`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003f803`

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
        byte_18005180C,
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
        byte_1800516E4,
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
0x18003f640  push    rbp
0x18003f642  push    rbx
0x18003f643  push    rdi
0x18003f644  lea     rbp, [rsp-47h]
0x18003f649  sub     rsp, 100h
0x18003f650  mov     rax, [rcx+110h]
0x18003f657  mov     rbx, rcx
0x18003f65a  mov     ecx, [rax+48h]
0x18003f65d  test    ecx, ecx
0x18003f65f  jns     loc_18003F7D7
0x18003f665  cmp     ecx, [rax+58h]
0x18003f668  jnz     loc_18003F7D7
0x18003f66e  lea     rdi, [rax+50h]
0x18003f672  test    rdi, rdi
0x18003f675  jz      loc_18003F7D7
0x18003f67b  mov     rcx, rbx
0x18003f67e  call    ?zInternalStop@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18003f683  call    ?Instance@LUATelemetry@@KAPEAV1@XZ; LUATelemetry::Instance(void)
0x18003f688  mov     rcx, [rax+8]
0x18003f68c  cmp     dword ptr [rcx], 5
0x18003f68f  jbe     loc_18003F856
0x18003f695  mov     rdx, 400000000000h
0x18003f69f  call    _tlgKeywordOn
0x18003f6a4  test    al, al
0x18003f6a6  jz      loc_18003F856
0x18003f6ac  mov     rax, [rdi+78h]
0x18003f6b0  lea     rdx, byte_1800516E4
0x18003f6b7  mov     r8, [rbx+110h]
0x18003f6be  mov     [rbp+57h+var_68], rax
0x18003f6c2  add     r8, 8
0x18003f6c6  mov     rax, [rdi+70h]
0x18003f6ca  mov     [rbp+57h+var_60], rax
0x18003f6ce  mov     eax, [rdi+68h]
0x18003f6d1  mov     [rbp+57h+arg_0], eax
0x18003f6d4  mov     rax, [rdi+60h]
0x18003f6d8  mov     [rbp+57h+var_58], rax
0x18003f6dc  mov     rax, [rdi+58h]
0x18003f6e0  mov     [rbp+57h+var_50], rax
0x18003f6e4  mov     eax, [rdi+50h]
0x18003f6e7  mov     [rbp+57h+arg_8], eax
0x18003f6ea  mov     rax, [rdi+48h]
0x18003f6ee  mov     [rbp+57h+var_48], rax
0x18003f6f2  mov     eax, [rdi+20h]
0x18003f6f5  mov     dword ptr [rbp+57h+arg_10], eax
0x18003f6f8  mov     rax, [rdi+18h]
0x18003f6fc  mov     [rbp+57h+var_40], rax
0x18003f700  mov     eax, [rdi]
0x18003f702  mov     [rbp+57h+arg_18], eax
0x18003f705  mov     rax, [rdi+80h]
0x18003f70c  mov     [rbp+57h+var_38], rax
0x18003f710  mov     eax, [rdi+40h]
0x18003f713  mov     [rbp+57h+var_70], eax
0x18003f716  mov     rax, [rdi+38h]
0x18003f71a  mov     [rbp+57h+var_30], rax
0x18003f71e  mov     eax, [rdi+8]
0x18003f721  mov     [rbp+57h+var_6C], eax
0x18003f724  lea     rax, [rbp+57h+var_68]
0x18003f728  mov     [rsp+110h+var_78], rax
0x18003f730  lea     rax, [rbp+57h+var_60]
0x18003f734  mov     [rsp+110h+var_80], rax
0x18003f73c  lea     rax, [rbp+57h+arg_0]
0x18003f740  mov     [rsp+110h+var_88], rax
0x18003f748  lea     rax, [rbp+57h+var_58]
0x18003f74c  mov     [rsp+110h+var_90], rax
0x18003f754  lea     rax, [rbp+57h+var_50]
0x18003f758  mov     [rsp+110h+var_98], rax
0x18003f75d  lea     rax, [rbp+57h+arg_8]
0x18003f761  mov     [rsp+110h+var_A0], rax
0x18003f766  lea     rax, [rbp+57h+var_48]
0x18003f76a  mov     [rsp+110h+var_A8], rax
0x18003f76f  lea     rax, [rbp+57h+arg_10]
0x18003f773  mov     [rsp+110h+var_B0], rax
0x18003f778  lea     rax, [rbp+57h+var_40]
0x18003f77c  mov     [rsp+110h+var_B8], rax
0x18003f781  lea     rax, [rbp+57h+arg_18]
0x18003f785  mov     [rsp+110h+var_C0], rax
0x18003f78a  lea     rax, [rbp+57h+var_38]
0x18003f78e  mov     [rsp+110h+var_C8], rax
0x18003f793  lea     rax, [rbp+57h+var_70]
0x18003f797  mov     [rsp+110h+var_D0], rax
0x18003f79c  lea     rax, [rbp+57h+var_30]
0x18003f7a0  mov     [rsp+110h+var_D8], rax
0x18003f7a5  lea     rax, [rbp+57h+var_6C]
0x18003f7a9  mov     [rsp+110h+var_E0], rax
0x18003f7ae  lea     rax, [rbp+57h+var_28]
0x18003f7b2  mov     [rsp+110h+var_E8], rax
0x18003f7b7  lea     rax, [rbp+57h+var_20]
0x18003f7bb  mov     [rsp+110h+var_F0], rax
0x18003f7c0  mov     [rbp+57h+var_28], 1000000h
0x18003f7c8  mov     [rbp+57h+var_20], 3000000h
0x18003f7d0  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18003f7d5  jmp     short loc_18003F856
0x18003f7d7  mov     rcx, rbx
0x18003f7da  call    ?zInternalStop@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18003f7df  call    ?Instance@LUATelemetry@@KAPEAV1@XZ; LUATelemetry::Instance(void)
0x18003f7e4  mov     rdi, [rax+8]
0x18003f7e8  cmp     dword ptr [rdi], 5
0x18003f7eb  jbe     short loc_18003F856
0x18003f7ed  mov     rdx, 400000000000h
0x18003f7f7  mov     rcx, rdi
0x18003f7fa  call    _tlgKeywordOn
0x18003f7ff  test    al, al
0x18003f801  jz      short loc_18003F856
0x18003f803  call    cs:__imp_GetCurrentThreadId
0x18003f80a  nop     dword ptr [rax+rax+00h]
0x18003f80f  mov     r8, [rbx+110h]
0x18003f816  lea     rdx, byte_18005180C
0x18003f81d  mov     [rbp+57h+arg_0], eax
0x18003f820  mov     rcx, rdi
0x18003f823  mov     eax, [r8+48h]
0x18003f827  add     r8, 8
0x18003f82b  mov     [rbp+57h+arg_8], eax
0x18003f82e  lea     rax, [rbp+57h+arg_0]
0x18003f832  mov     [rsp+110h+var_E0], rax
0x18003f837  lea     rax, [rbp+57h+arg_8]
0x18003f83b  mov     [rsp+110h+var_E8], rax
0x18003f840  lea     rax, [rbp+57h+arg_10]
0x18003f844  mov     [rsp+110h+var_F0], rax
0x18003f849  mov     [rbp+57h+arg_10], 3000000h
0x18003f851  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18003f856  mov     rcx, rbx
0x18003f859  add     rsp, 100h
0x18003f860  pop     rdi
0x18003f861  pop     rbx
0x18003f862  pop     rbp
0x18003f863  jmp     ?IgnoreCurrentThread@?$ActivityBase@VLUATelemetry@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
