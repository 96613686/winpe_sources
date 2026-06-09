# Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::StopActivity(void)

- ea: `0x1800380f0`
- end: `0x180038316`
- name: `?StopActivity@TryActivateContractExtension@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@MEAAXXZ`
- size: `550`
- prototype: `void __fastcall(Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x18000c7d0`
- `0x18000cb30`
- `0x180010c48`
- `0x180010f8c`
- `0x180018d70`
- `0x1800357d8`
- `0x1800380f0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800382b4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800382b4`

## pseudocode

```c
void __fastcall Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::StopActivity(
        Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension *this)
{
  int *v1; // rax
  int v3; // ecx
  int *v4; // rdi
  const struct _tlgProvider_t *v5; // rax
  __int64 v6; // r9
  const unsigned __int16 *v7; // rax
  const wchar_t *v8; // rcx
  __int64 v9; // r8
  const struct _tlgProvider_t *v10; // rax
  __int64 v11; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v13; // r8
  int v14; // eax
  __int64 v15; // r9
  int v16; // [rsp+A0h] [rbp-19h] BYREF
  int v17; // [rsp+A4h] [rbp-15h] BYREF
  const wchar_t *v18; // [rsp+A8h] [rbp-11h] BYREF
  const unsigned __int16 *v19; // [rsp+B0h] [rbp-9h] BYREF
  const wchar_t *v20; // [rsp+B8h] [rbp-1h] BYREF
  const unsigned __int16 *v21; // [rsp+C0h] [rbp+7h] BYREF
  const unsigned __int16 *v22; // [rsp+C8h] [rbp+Fh] BYREF
  const wchar_t *v23; // [rsp+D0h] [rbp+17h] BYREF
  const unsigned __int16 *v24; // [rsp+D8h] [rbp+1Fh] BYREF
  const unsigned __int16 *v25; // [rsp+E0h] [rbp+27h] BYREF
  __int64 v26; // [rsp+E8h] [rbp+2Fh] BYREF
  _QWORD v27[4]; // [rsp+F0h] [rbp+37h] BYREF
  DWORD v28; // [rsp+120h] [rbp+67h] BYREF
  int v29; // [rsp+128h] [rbp+6Fh] BYREF
  __int64 v30; // [rsp+130h] [rbp+77h] BYREF
  int v31; // [rsp+138h] [rbp+7Fh] BYREF

  v1 = (int *)*((_QWORD *)this + 34);
  v3 = v1[18];
  if ( v3 >= 0 || v3 != v1[22] || (v4 = v1 + 20, v1 == (int *)-80LL) )
  {
    wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(this);
    v10 = Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider();
    v11 = (__int64)v10;
    if ( *(_DWORD *)v10 > 5u && (unsigned __int8)tlgKeywordOn(v10, 0x400000000000LL) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v13 = *((_QWORD *)this + 34);
      v28 = CurrentThreadId;
      v14 = *(_DWORD *)(v13 + 72);
      v30 = 0;
      v29 = v14;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v11,
        byte_18005290E,
        (const GUID *)(v13 + 8),
        v15,
        (__int64)&v30,
        (__int64)&v29,
        (__int64)&v28);
    }
  }
  else
  {
    wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(this);
    v5 = Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider();
    if ( *(_DWORD *)v5 > 5u && (unsigned __int8)tlgKeywordOn(v5, 0x400000000000LL) )
    {
      v7 = (const unsigned __int16 *)*((_QWORD *)v4 + 14);
      v8 = (const wchar_t *)*((_QWORD *)v4 + 15);
      v9 = *((_QWORD *)this + 34);
      v27[0] = 0;
      v19 = v7;
      v28 = v4[26];
      v20 = (const wchar_t *)*((_QWORD *)v4 + 12);
      v21 = (const unsigned __int16 *)*((_QWORD *)v4 + 11);
      v29 = v4[20];
      v22 = (const unsigned __int16 *)*((_QWORD *)v4 + 9);
      LODWORD(v30) = v4[8];
      v23 = (const wchar_t *)*((_QWORD *)v4 + 3);
      v31 = *v4;
      v24 = (const unsigned __int16 *)*((_QWORD *)v4 + 16);
      v16 = v4[16];
      v25 = (const unsigned __int16 *)*((_QWORD *)v4 + 7);
      v17 = v4[2];
      v18 = v8;
      v26 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        v6,
        byte_180053028,
        (const GUID *)(v9 + 8),
        v6,
        (__int64)v27,
        (__int64)&v26,
        (__int64)&v17,
        &v25,
        (__int64)&v16,
        &v24,
        (__int64)&v31,
        &v23,
        (__int64)&v30,
        &v22,
        (__int64)&v29,
        &v21,
        &v20,
        (__int64)&v28,
        &v19,
        &v18);
    }
  }
  wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x1800380f0  push    rbp
0x1800380f2  push    rbx
0x1800380f3  push    rdi
0x1800380f4  lea     rbp, [rsp-47h]
0x1800380f9  sub     rsp, 100h
0x180038100  mov     rax, [rcx+110h]
0x180038107  mov     rbx, rcx
0x18003810a  mov     ecx, [rax+48h]
0x18003810d  test    ecx, ecx
0x18003810f  jns     loc_180038289
0x180038115  cmp     ecx, [rax+58h]
0x180038118  jnz     loc_180038289
0x18003811e  lea     rdi, [rax+50h]
0x180038122  test    rdi, rdi
0x180038125  jz      loc_180038289
0x18003812b  mov     rcx, rbx
0x18003812e  call    ?zInternalStop@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180038133  call    ?Provider@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider(void)
0x180038138  mov     r9, rax
0x18003813b  cmp     dword ptr [rax], 5
0x18003813e  jbe     loc_180038304
0x180038144  mov     rdx, 400000000000h
0x18003814e  mov     rcx, rax
0x180038151  call    _tlgKeywordOn
0x180038156  test    al, al
0x180038158  jz      loc_180038304
0x18003815e  mov     rax, [rdi+70h]
0x180038162  lea     rdx, byte_180053028
0x180038169  mov     rcx, [rdi+78h]
0x18003816d  mov     r8, [rbx+110h]
0x180038174  and     [rbp+57h+var_20], 0
0x180038179  add     r8, 8
0x18003817d  mov     [rbp+57h+var_60], rax
0x180038181  mov     eax, [rdi+68h]
0x180038184  mov     [rbp+57h+arg_0], eax
0x180038187  mov     rax, [rdi+60h]
0x18003818b  mov     [rbp+57h+var_58], rax
0x18003818f  mov     rax, [rdi+58h]
0x180038193  mov     [rbp+57h+var_50], rax
0x180038197  mov     eax, [rdi+50h]
0x18003819a  mov     [rbp+57h+arg_8], eax
0x18003819d  mov     rax, [rdi+48h]
0x1800381a1  mov     [rbp+57h+var_48], rax
0x1800381a5  mov     eax, [rdi+20h]
0x1800381a8  mov     dword ptr [rbp+57h+arg_10], eax
0x1800381ab  mov     rax, [rdi+18h]
0x1800381af  mov     [rbp+57h+var_40], rax
0x1800381b3  mov     eax, [rdi]
0x1800381b5  mov     [rbp+57h+arg_18], eax
0x1800381b8  mov     rax, [rdi+80h]
0x1800381bf  mov     [rbp+57h+var_38], rax
0x1800381c3  mov     eax, [rdi+40h]
0x1800381c6  mov     [rbp+57h+var_70], eax
0x1800381c9  mov     rax, [rdi+38h]
0x1800381cd  mov     [rbp+57h+var_30], rax
0x1800381d1  mov     eax, [rdi+8]
0x1800381d4  mov     [rbp+57h+var_6C], eax
0x1800381d7  lea     rax, [rbp+57h+var_68]
0x1800381db  mov     [rsp+110h+var_78], rax
0x1800381e3  lea     rax, [rbp+57h+var_60]
0x1800381e7  mov     [rsp+110h+var_80], rax
0x1800381ef  lea     rax, [rbp+57h+arg_0]
0x1800381f3  mov     [rsp+110h+var_88], rax
0x1800381fb  lea     rax, [rbp+57h+var_58]
0x1800381ff  mov     [rsp+110h+var_90], rax
0x180038207  lea     rax, [rbp+57h+var_50]
0x18003820b  mov     [rsp+110h+var_98], rax
0x180038210  lea     rax, [rbp+57h+arg_8]
0x180038214  mov     [rsp+110h+var_A0], rax
0x180038219  lea     rax, [rbp+57h+var_48]
0x18003821d  mov     [rsp+110h+var_A8], rax
0x180038222  lea     rax, [rbp+57h+arg_10]
0x180038226  mov     [rsp+110h+var_B0], rax
0x18003822b  lea     rax, [rbp+57h+var_40]
0x18003822f  mov     [rsp+110h+var_B8], rax
0x180038234  lea     rax, [rbp+57h+arg_18]
0x180038238  mov     [rsp+110h+var_C0], rax
0x18003823d  lea     rax, [rbp+57h+var_38]
0x180038241  mov     [rsp+110h+var_C8], rax
0x180038246  lea     rax, [rbp+57h+var_70]
0x18003824a  mov     [rsp+110h+var_D0], rax
0x18003824f  lea     rax, [rbp+57h+var_30]
0x180038253  mov     [rsp+110h+var_D8], rax
0x180038258  lea     rax, [rbp+57h+var_6C]
0x18003825c  mov     [rsp+110h+var_E0], rax
0x180038261  lea     rax, [rbp+57h+var_28]
0x180038265  mov     [rsp+110h+var_E8], rax
0x18003826a  lea     rax, [rbp+57h+var_20]
0x18003826e  mov     [rbp+57h+var_68], rcx
0x180038272  mov     rcx, r9
0x180038275  mov     [rsp+110h+var_F0], rax
0x18003827a  mov     [rbp+57h+var_28], 1000000h
0x180038282  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180038287  jmp     short loc_180038304
0x180038289  mov     rcx, rbx
0x18003828c  call    ?zInternalStop@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180038291  call    ?Provider@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider(void)
0x180038296  mov     rdi, rax
0x180038299  cmp     dword ptr [rax], 5
0x18003829c  jbe     short loc_180038304
0x18003829e  mov     rdx, 400000000000h
0x1800382a8  mov     rcx, rax
0x1800382ab  call    _tlgKeywordOn
0x1800382b0  test    al, al
0x1800382b2  jz      short loc_180038304
0x1800382b4  call    cs:__imp_GetCurrentThreadId
0x1800382bb  nop     dword ptr [rax+rax+00h]
0x1800382c0  mov     r8, [rbx+110h]
0x1800382c7  lea     rdx, byte_18005290E
0x1800382ce  mov     [rbp+57h+arg_0], eax
0x1800382d1  mov     rcx, rdi
0x1800382d4  mov     eax, [r8+48h]
0x1800382d8  add     r8, 8
0x1800382dc  and     [rbp+57h+arg_10], 0
0x1800382e1  mov     [rbp+57h+arg_8], eax
0x1800382e4  lea     rax, [rbp+57h+arg_0]
0x1800382e8  mov     [rsp+110h+var_E0], rax
0x1800382ed  lea     rax, [rbp+57h+arg_8]
0x1800382f1  mov     [rsp+110h+var_E8], rax
0x1800382f6  lea     rax, [rbp+57h+arg_10]
0x1800382fa  mov     [rsp+110h+var_F0], rax
0x1800382ff  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180038304  mov     rcx, rbx
0x180038307  add     rsp, 100h
0x18003830e  pop     rdi
0x18003830f  pop     rbx
0x180038310  pop     rbp
0x180038311  jmp     ?IgnoreCurrentThread@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
