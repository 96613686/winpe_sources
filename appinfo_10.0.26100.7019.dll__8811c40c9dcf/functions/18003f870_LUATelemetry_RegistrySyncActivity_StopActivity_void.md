# LUATelemetry::RegistrySyncActivity::StopActivity(void)

- ea: `0x18003f870`
- end: `0x18003fa98`
- name: `?StopActivity@RegistrySyncActivity@LUATelemetry@@MEAAXXZ`
- size: `552`
- prototype: `void __fastcall(LUATelemetry::RegistrySyncActivity *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callees

- `0x18000c7d0`
- `0x18000cb30`
- `0x180010e4c`
- `0x180018ac0`
- `0x180020fe0`
- `0x180021008`
- `0x18003f870`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003fa33`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003fa33`

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
        byte_18005168F,
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
        byte_180051B61,
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
0x18003f870  push    rbp
0x18003f872  push    rbx
0x18003f873  push    rdi
0x18003f874  lea     rbp, [rsp-47h]
0x18003f879  sub     rsp, 100h
0x18003f880  mov     rax, [rcx+110h]
0x18003f887  mov     rbx, rcx
0x18003f88a  mov     ecx, [rax+48h]
0x18003f88d  test    ecx, ecx
0x18003f88f  jns     loc_18003FA07
0x18003f895  cmp     ecx, [rax+58h]
0x18003f898  jnz     loc_18003FA07
0x18003f89e  lea     rdi, [rax+50h]
0x18003f8a2  test    rdi, rdi
0x18003f8a5  jz      loc_18003FA07
0x18003f8ab  mov     rcx, rbx
0x18003f8ae  call    ?zInternalStop@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18003f8b3  call    ?Instance@LUATelemetry@@KAPEAV1@XZ; LUATelemetry::Instance(void)
0x18003f8b8  mov     rcx, [rax+8]
0x18003f8bc  cmp     dword ptr [rcx], 5
0x18003f8bf  jbe     loc_18003FA86
0x18003f8c5  mov     rdx, 400000000000h
0x18003f8cf  call    _tlgKeywordOn
0x18003f8d4  test    al, al
0x18003f8d6  jz      loc_18003FA86
0x18003f8dc  mov     rax, [rdi+78h]
0x18003f8e0  lea     rdx, byte_180051B61
0x18003f8e7  mov     r8, [rbx+110h]
0x18003f8ee  mov     [rbp+57h+var_68], rax
0x18003f8f2  add     r8, 8
0x18003f8f6  mov     rax, [rdi+70h]
0x18003f8fa  mov     [rbp+57h+var_60], rax
0x18003f8fe  mov     eax, [rdi+68h]
0x18003f901  mov     [rbp+57h+arg_0], eax
0x18003f904  mov     rax, [rdi+60h]
0x18003f908  mov     [rbp+57h+var_58], rax
0x18003f90c  mov     rax, [rdi+58h]
0x18003f910  mov     [rbp+57h+var_50], rax
0x18003f914  mov     eax, [rdi+50h]
0x18003f917  mov     [rbp+57h+arg_8], eax
0x18003f91a  mov     rax, [rdi+48h]
0x18003f91e  mov     [rbp+57h+var_48], rax
0x18003f922  mov     eax, [rdi+20h]
0x18003f925  mov     dword ptr [rbp+57h+arg_10], eax
0x18003f928  mov     rax, [rdi+18h]
0x18003f92c  mov     [rbp+57h+var_40], rax
0x18003f930  mov     eax, [rdi]
0x18003f932  mov     [rbp+57h+arg_18], eax
0x18003f935  mov     rax, [rdi+80h]
0x18003f93c  mov     [rbp+57h+var_38], rax
0x18003f940  mov     eax, [rdi+40h]
0x18003f943  mov     [rbp+57h+var_70], eax
0x18003f946  mov     rax, [rdi+38h]
0x18003f94a  mov     [rbp+57h+var_30], rax
0x18003f94e  mov     eax, [rdi+8]
0x18003f951  mov     [rbp+57h+var_6C], eax
0x18003f954  lea     rax, [rbp+57h+var_68]
0x18003f958  mov     [rsp+110h+var_78], rax
0x18003f960  lea     rax, [rbp+57h+var_60]
0x18003f964  mov     [rsp+110h+var_80], rax
0x18003f96c  lea     rax, [rbp+57h+arg_0]
0x18003f970  mov     [rsp+110h+var_88], rax
0x18003f978  lea     rax, [rbp+57h+var_58]
0x18003f97c  mov     [rsp+110h+var_90], rax
0x18003f984  lea     rax, [rbp+57h+var_50]
0x18003f988  mov     [rsp+110h+var_98], rax
0x18003f98d  lea     rax, [rbp+57h+arg_8]
0x18003f991  mov     [rsp+110h+var_A0], rax
0x18003f996  lea     rax, [rbp+57h+var_48]
0x18003f99a  mov     [rsp+110h+var_A8], rax
0x18003f99f  lea     rax, [rbp+57h+arg_10]
0x18003f9a3  mov     [rsp+110h+var_B0], rax
0x18003f9a8  lea     rax, [rbp+57h+var_40]
0x18003f9ac  mov     [rsp+110h+var_B8], rax
0x18003f9b1  lea     rax, [rbp+57h+arg_18]
0x18003f9b5  mov     [rsp+110h+var_C0], rax
0x18003f9ba  lea     rax, [rbp+57h+var_38]
0x18003f9be  mov     [rsp+110h+var_C8], rax
0x18003f9c3  lea     rax, [rbp+57h+var_70]
0x18003f9c7  mov     [rsp+110h+var_D0], rax
0x18003f9cc  lea     rax, [rbp+57h+var_30]
0x18003f9d0  mov     [rsp+110h+var_D8], rax
0x18003f9d5  lea     rax, [rbp+57h+var_6C]
0x18003f9d9  mov     [rsp+110h+var_E0], rax
0x18003f9de  lea     rax, [rbp+57h+var_28]
0x18003f9e2  mov     [rsp+110h+var_E8], rax
0x18003f9e7  lea     rax, [rbp+57h+var_20]
0x18003f9eb  mov     [rsp+110h+var_F0], rax
0x18003f9f0  mov     [rbp+57h+var_28], 1000000h
0x18003f9f8  mov     [rbp+57h+var_20], 3000000h
0x18003fa00  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18003fa05  jmp     short loc_18003FA86
0x18003fa07  mov     rcx, rbx
0x18003fa0a  call    ?zInternalStop@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18003fa0f  call    ?Instance@LUATelemetry@@KAPEAV1@XZ; LUATelemetry::Instance(void)
0x18003fa14  mov     rdi, [rax+8]
0x18003fa18  cmp     dword ptr [rdi], 5
0x18003fa1b  jbe     short loc_18003FA86
0x18003fa1d  mov     rdx, 400000000000h
0x18003fa27  mov     rcx, rdi
0x18003fa2a  call    _tlgKeywordOn
0x18003fa2f  test    al, al
0x18003fa31  jz      short loc_18003FA86
0x18003fa33  call    cs:__imp_GetCurrentThreadId
0x18003fa3a  nop     dword ptr [rax+rax+00h]
0x18003fa3f  mov     r8, [rbx+110h]
0x18003fa46  lea     rdx, byte_18005168F
0x18003fa4d  mov     [rbp+57h+arg_0], eax
0x18003fa50  mov     rcx, rdi
0x18003fa53  mov     eax, [r8+48h]
0x18003fa57  add     r8, 8
0x18003fa5b  mov     [rbp+57h+arg_8], eax
0x18003fa5e  lea     rax, [rbp+57h+arg_0]
0x18003fa62  mov     [rsp+110h+var_E0], rax
0x18003fa67  lea     rax, [rbp+57h+arg_8]
0x18003fa6b  mov     [rsp+110h+var_E8], rax
0x18003fa70  lea     rax, [rbp+57h+arg_10]
0x18003fa74  mov     [rsp+110h+var_F0], rax
0x18003fa79  mov     [rbp+57h+arg_10], 3000000h
0x18003fa81  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18003fa86  mov     rcx, rbx
0x18003fa89  add     rsp, 100h
0x18003fa90  pop     rdi
0x18003fa91  pop     rbx
0x18003fa92  pop     rbp
0x18003fa93  jmp     ?IgnoreCurrentThread@?$ActivityBase@VLUATelemetry@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
