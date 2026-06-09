# MitigationTelemetryClass::OneSettingsHandlerInitialize::Stop(ulong)

- ea: `0x180056350`
- end: `0x180056583`
- name: `?Stop@OneSettingsHandlerInitialize@MitigationTelemetryClass@@QEAAXK@Z`
- size: `563`
- prototype: `void __fastcall(MitigationTelemetryClass::OneSettingsHandlerInitialize *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callers

- `0x1800552a0`

## callees

- `0x1800012b8`
- `0x1800019bc`
- `0x180001bec`
- `0x18001786c`
- `0x18001e13c`
- `0x1800246bc`
- `0x180056350`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180056522`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180056522`

## pseudocode

```c
void __fastcall MitigationTelemetryClass::OneSettingsHandlerInitialize::Stop(
        MitigationTelemetryClass::OneSettingsHandlerInitialize *this,
        DWORD a2)
{
  __int64 v3; // rdi
  int v4; // eax
  int *v5; // rdi
  const struct _tlgProvider_t *v6; // rax
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // r9
  const WCHAR *v10; // rcx
  __int64 v11; // r8
  const struct _tlgProvider_t *v12; // rax
  __int64 v13; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v15; // r8
  __int64 v16; // r9
  int v17; // [rsp+A0h] [rbp-19h] BYREF
  int v18; // [rsp+A4h] [rbp-15h] BYREF
  const WCHAR *v19; // [rsp+A8h] [rbp-11h] BYREF
  const char *v20; // [rsp+B0h] [rbp-9h] BYREF
  const WCHAR *v21; // [rsp+B8h] [rbp-1h] BYREF
  const char *v22; // [rsp+C0h] [rbp+7h] BYREF
  const char *v23; // [rsp+C8h] [rbp+Fh] BYREF
  const WCHAR *v24; // [rsp+D0h] [rbp+17h] BYREF
  const char *v25; // [rsp+D8h] [rbp+1Fh] BYREF
  const char *v26; // [rsp+E0h] [rbp+27h] BYREF
  __int64 v27; // [rsp+E8h] [rbp+2Fh] BYREF
  __int64 v28[4]; // [rsp+F0h] [rbp+37h] BYREF
  int v29; // [rsp+120h] [rbp+67h] BYREF
  DWORD v30; // [rsp+128h] [rbp+6Fh] BYREF
  __int64 v31; // [rsp+130h] [rbp+77h] BYREF
  int v32; // [rsp+138h] [rbp+7Fh] BYREF

  v30 = a2;
  if ( *((_BYTE *)this + 336) )
  {
    v3 = *((_QWORD *)this + 34);
    v4 = *(_DWORD *)(v3 + 72);
    if ( v4 < 0 && (v5 = (int *)(v3 + 80), v4 == v5[2]) && v5 )
    {
      wil::ActivityBase<MitigationTelemetryClass,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
      v6 = MitigationTelemetryClass::Provider();
      v9 = (__int64)v6;
      if ( *(_DWORD *)v6 > 5u )
      {
        if ( (unsigned __int8)tlgKeywordOn(v6, 0x400000000000LL) )
        {
          v10 = (const WCHAR *)*((_QWORD *)v5 + 15);
          v11 = *((_QWORD *)this + 34);
          v20 = (const char *)*((_QWORD *)v5 + 14);
          v30 = v5[26];
          v21 = (const WCHAR *)*((_QWORD *)v5 + 12);
          v22 = (const char *)*((_QWORD *)v5 + 11);
          v29 = v5[20];
          v23 = (const char *)*((_QWORD *)v5 + 9);
          LODWORD(v31) = v5[8];
          v24 = (const WCHAR *)*((_QWORD *)v5 + 3);
          v32 = *v5;
          v25 = (const char *)*((_QWORD *)v5 + 16);
          v17 = v5[16];
          v26 = (const char *)*((_QWORD *)v5 + 7);
          v18 = v5[2];
          v27 = 0x1000000;
          v28[0] = 0x1000000;
          v19 = v10;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
            v9,
            (__int64)&unk_180070658,
            v11 + 8,
            v9,
            (__int64)v28,
            (__int64)&v27,
            (__int64)&v18,
            &v26,
            (__int64)&v17,
            &v25,
            (__int64)&v32,
            &v24,
            (__int64)&v31,
            &v23,
            (__int64)&v29,
            &v22,
            &v21,
            (__int64)&v30,
            &v20,
            &v19);
        }
      }
    }
    else
    {
      wil::ActivityBase<MitigationTelemetryClass,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
      v12 = MitigationTelemetryClass::Provider();
      v13 = (__int64)v12;
      if ( *(_DWORD *)v12 > 5u && (unsigned __int8)tlgKeywordOn(v12, 0x400000000000LL) )
      {
        CurrentThreadId = GetCurrentThreadId();
        v15 = *((_QWORD *)this + 34);
        v30 = CurrentThreadId;
        v29 = *(_DWORD *)(v15 + 72);
        v31 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v13,
          (__int64)byte_1800705FB,
          v15 + 8,
          v16,
          (__int64)&v31,
          (__int64)&v29,
          (__int64)&v30);
      }
    }
    wil::ActivityBase<MitigationTelemetryClass,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
      this,
      v7,
      v8,
      v9);
  }
}

```

## disassembly

```asm
0x180056350  mov     [rsp-8+arg_8], edx
0x180056354  push    rbp
0x180056355  push    rbx
0x180056356  push    rdi
0x180056357  lea     rbp, [rsp-47h]
0x18005635c  sub     rsp, 100h
0x180056363  cmp     byte ptr [rcx+150h], 0
0x18005636a  mov     rbx, rcx
0x18005636d  jz      loc_180056578
0x180056373  mov     rdi, [rcx+110h]
0x18005637a  mov     eax, [rdi+48h]
0x18005637d  test    eax, eax
0x18005637f  jns     loc_1800564F8
0x180056385  add     rdi, 50h ; 'P'
0x180056389  cmp     eax, [rdi+8]
0x18005638c  jnz     loc_1800564F8
0x180056392  test    rdi, rdi
0x180056395  jz      loc_1800564F8
0x18005639b  call    ?zInternalStop@?$ActivityBase@VMitigationTelemetryClass@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<MitigationTelemetryClass,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x1800563a0  call    ?Provider@MitigationTelemetryClass@@SAPEBU_tlgProvider_t@@XZ; MitigationTelemetryClass::Provider(void)
0x1800563a5  mov     r9, rax
0x1800563a8  mov     ecx, [rax]
0x1800563aa  cmp     ecx, 5
0x1800563ad  jbe     loc_180056570
0x1800563b3  mov     rdx, 400000000000h
0x1800563bd  mov     rcx, rax
0x1800563c0  call    _tlgKeywordOn
0x1800563c5  test    al, al
0x1800563c7  jz      loc_180056570
0x1800563cd  mov     rax, [rdi+70h]
0x1800563d1  lea     rdx, unk_180070658
0x1800563d8  mov     rcx, [rdi+78h]
0x1800563dc  mov     r8, [rbx+110h]
0x1800563e3  mov     [rbp+57h+var_60], rax
0x1800563e7  add     r8, 8
0x1800563eb  mov     eax, [rdi+68h]
0x1800563ee  mov     [rbp+57h+arg_8], eax
0x1800563f1  mov     rax, [rdi+60h]
0x1800563f5  mov     [rbp+57h+var_58], rax
0x1800563f9  mov     rax, [rdi+58h]
0x1800563fd  mov     [rbp+57h+var_50], rax
0x180056401  mov     eax, [rdi+50h]
0x180056404  mov     [rbp+57h+arg_0], eax
0x180056407  mov     rax, [rdi+48h]
0x18005640b  mov     [rbp+57h+var_48], rax
0x18005640f  mov     eax, [rdi+20h]
0x180056412  mov     dword ptr [rbp+57h+arg_10], eax
0x180056415  mov     rax, [rdi+18h]
0x180056419  mov     [rbp+57h+var_40], rax
0x18005641d  mov     eax, [rdi]
0x18005641f  mov     [rbp+57h+arg_18], eax
0x180056422  mov     rax, [rdi+80h]
0x180056429  mov     [rbp+57h+var_38], rax
0x18005642d  mov     eax, [rdi+40h]
0x180056430  mov     [rbp+57h+var_70], eax
0x180056433  mov     rax, [rdi+38h]
0x180056437  mov     [rbp+57h+var_30], rax
0x18005643b  mov     eax, [rdi+8]
0x18005643e  mov     [rbp+57h+var_6C], eax
0x180056441  mov     eax, 1000000h
0x180056446  mov     [rbp+57h+var_28], rax
0x18005644a  mov     [rbp+57h+var_20], rax
0x18005644e  lea     rax, [rbp+57h+var_68]
0x180056452  mov     [rsp+110h+var_78], rax
0x18005645a  lea     rax, [rbp+57h+var_60]
0x18005645e  mov     [rsp+110h+var_80], rax
0x180056466  lea     rax, [rbp+57h+arg_8]
0x18005646a  mov     [rsp+110h+var_88], rax
0x180056472  lea     rax, [rbp+57h+var_58]
0x180056476  mov     [rsp+110h+var_90], rax
0x18005647e  lea     rax, [rbp+57h+var_50]
0x180056482  mov     [rsp+110h+var_98], rax
0x180056487  lea     rax, [rbp+57h+arg_0]
0x18005648b  mov     [rsp+110h+var_A0], rax
0x180056490  lea     rax, [rbp+57h+var_48]
0x180056494  mov     [rsp+110h+var_A8], rax
0x180056499  lea     rax, [rbp+57h+arg_10]
0x18005649d  mov     [rsp+110h+var_B0], rax
0x1800564a2  lea     rax, [rbp+57h+var_40]
0x1800564a6  mov     [rsp+110h+var_B8], rax
0x1800564ab  lea     rax, [rbp+57h+arg_18]
0x1800564af  mov     [rsp+110h+var_C0], rax
0x1800564b4  lea     rax, [rbp+57h+var_38]
0x1800564b8  mov     [rsp+110h+var_C8], rax
0x1800564bd  lea     rax, [rbp+57h+var_70]
0x1800564c1  mov     [rsp+110h+var_D0], rax
0x1800564c6  lea     rax, [rbp+57h+var_30]
0x1800564ca  mov     [rsp+110h+var_D8], rax
0x1800564cf  lea     rax, [rbp+57h+var_6C]
0x1800564d3  mov     [rsp+110h+var_E0], rax
0x1800564d8  lea     rax, [rbp+57h+var_28]
0x1800564dc  mov     [rsp+110h+var_E8], rax
0x1800564e1  lea     rax, [rbp+57h+var_20]
0x1800564e5  mov     [rbp+57h+var_68], rcx
0x1800564e9  mov     rcx, r9
0x1800564ec  mov     [rsp+110h+var_F0], rax
0x1800564f1  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x1800564f6  jmp     short loc_180056570
0x1800564f8  call    ?zInternalStop@?$ActivityBase@VMitigationTelemetryClass@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<MitigationTelemetryClass,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x1800564fd  call    ?Provider@MitigationTelemetryClass@@SAPEBU_tlgProvider_t@@XZ; MitigationTelemetryClass::Provider(void)
0x180056502  mov     rdi, rax
0x180056505  mov     ecx, [rax]
0x180056507  cmp     ecx, 5
0x18005650a  jbe     short loc_180056570
0x18005650c  mov     rdx, 400000000000h
0x180056516  mov     rcx, rax
0x180056519  call    _tlgKeywordOn
0x18005651e  test    al, al
0x180056520  jz      short loc_180056570
0x180056522  call    cs:__imp_GetCurrentThreadId
0x180056528  mov     r8, [rbx+110h]
0x18005652f  lea     rdx, byte_1800705FB
0x180056536  mov     [rbp+57h+arg_8], eax
0x180056539  mov     rcx, rdi
0x18005653c  mov     eax, [r8+48h]
0x180056540  add     r8, 8
0x180056544  mov     [rbp+57h+arg_0], eax
0x180056547  mov     eax, 1000000h
0x18005654c  mov     [rbp+57h+arg_10], rax
0x180056550  lea     rax, [rbp+57h+arg_8]
0x180056554  mov     [rsp+110h+var_E0], rax
0x180056559  lea     rax, [rbp+57h+arg_0]
0x18005655d  mov     [rsp+110h+var_E8], rax
0x180056562  lea     rax, [rbp+57h+arg_10]
0x180056566  mov     [rsp+110h+var_F0], rax
0x18005656b  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180056570  mov     rcx, rbx
0x180056573  call    ?IgnoreCurrentThread@?$ActivityBase@VMitigationTelemetryClass@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<MitigationTelemetryClass,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
0x180056578  add     rsp, 100h
0x18005657f  pop     rdi
0x180056580  pop     rbx
0x180056581  pop     rbp
0x180056582  retn
```
