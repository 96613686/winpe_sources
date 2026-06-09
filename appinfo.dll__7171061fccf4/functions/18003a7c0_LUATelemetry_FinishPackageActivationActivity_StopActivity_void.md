# LUATelemetry::FinishPackageActivationActivity::StopActivity(void)

- ea: `0x18003a7c0`
- end: `0x18003a9e4`
- name: `?StopActivity@FinishPackageActivationActivity@LUATelemetry@@MEAAXXZ`
- size: `548`
- prototype: `void __fastcall(LUATelemetry::FinishPackageActivationActivity *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x18000be18`
- `0x18000f168`
- `0x180010658`
- `0x180011fd0`
- `0x18001b03c`
- `0x18001b23c`
- `0x18003a7c0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003a985`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003a985`

## pseudocode

```c
void __fastcall LUATelemetry::FinishPackageActivationActivity::StopActivity(
        LUATelemetry::FinishPackageActivationActivity *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  const struct _tlgProvider_t *v5; // rax
  __int64 v6; // r9
  const wchar_t *v7; // rcx
  __int64 v8; // r8
  const struct _tlgProvider_t *v9; // rax
  __int64 v10; // rdi
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
  _QWORD v25[4]; // [rsp+F0h] [rbp+37h] BYREF
  DWORD v26; // [rsp+120h] [rbp+67h] BYREF
  int v27; // [rsp+128h] [rbp+6Fh] BYREF
  __int64 v28; // [rsp+130h] [rbp+77h] BYREF
  int v29; // [rsp+138h] [rbp+7Fh] BYREF

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = (int *)(v1 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v5 = LUATelemetry::Provider();
    if ( *(_DWORD *)v5 > 5u && (unsigned __int8)tlgKeywordOn(v5, 0x200000000000LL) )
    {
      v7 = (const wchar_t *)*((_QWORD *)v4 + 15);
      v8 = *((_QWORD *)this + 34);
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
      v16 = v7;
      v24 = 0x1000000;
      v25[0] = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        v6,
        (unsigned __int8 *)byte_1800565DD,
        (const GUID *)(v8 + 8),
        v6,
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
  else
  {
    wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v9 = LUATelemetry::Provider();
    v10 = (__int64)v9;
    if ( *(_DWORD *)v9 > 5u && (unsigned __int8)tlgKeywordOn(v9, 0x200000000000LL) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v12 = *((_QWORD *)this + 34);
      v26 = CurrentThreadId;
      v27 = *(_DWORD *)(v12 + 72);
      v28 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v10,
        (unsigned __int8 *)&word_180054E56,
        (const GUID *)(v12 + 8),
        v13,
        (__int64)&v28,
        (__int64)&v27,
        (__int64)&v26);
    }
  }
  wil::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(this);
}

```

## disassembly

```asm
0x18003a7c0  push    rbp
0x18003a7c2  push    rbx
0x18003a7c3  push    rdi
0x18003a7c4  lea     rbp, [rsp-47h]
0x18003a7c9  sub     rsp, 100h
0x18003a7d0  mov     rdi, [rcx+110h]
0x18003a7d7  mov     rbx, rcx
0x18003a7da  mov     eax, [rdi+48h]
0x18003a7dd  test    eax, eax
0x18003a7df  jns     loc_18003A95B
0x18003a7e5  add     rdi, 50h ; 'P'
0x18003a7e9  cmp     eax, [rdi+8]
0x18003a7ec  jnz     loc_18003A95B
0x18003a7f2  test    rdi, rdi
0x18003a7f5  jz      loc_18003A95B
0x18003a7fb  call    ?zInternalStop@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18003a800  call    ?Provider@LUATelemetry@@SAPEBU_tlgProvider_t@@XZ; LUATelemetry::Provider(void)
0x18003a805  mov     r9, rax
0x18003a808  mov     ecx, [rax]
0x18003a80a  cmp     ecx, 5
0x18003a80d  jbe     loc_18003A9D2
0x18003a813  mov     rdx, 200000000000h
0x18003a81d  mov     rcx, rax
0x18003a820  call    _tlgKeywordOn
0x18003a825  test    al, al
0x18003a827  jz      loc_18003A9D2
0x18003a82d  mov     rax, [rdi+70h]
0x18003a831  lea     rdx, byte_1800565DD
0x18003a838  mov     rcx, [rdi+78h]
0x18003a83c  mov     r8, [rbx+110h]
0x18003a843  mov     [rbp+57h+var_60], rax
0x18003a847  add     r8, 8
0x18003a84b  mov     eax, [rdi+68h]
0x18003a84e  mov     [rbp+57h+arg_0], eax
0x18003a851  mov     rax, [rdi+60h]
0x18003a855  mov     [rbp+57h+var_58], rax
0x18003a859  mov     rax, [rdi+58h]
0x18003a85d  mov     [rbp+57h+var_50], rax
0x18003a861  mov     eax, [rdi+50h]
0x18003a864  mov     [rbp+57h+arg_8], eax
0x18003a867  mov     rax, [rdi+48h]
0x18003a86b  mov     [rbp+57h+var_48], rax
0x18003a86f  mov     eax, [rdi+20h]
0x18003a872  mov     dword ptr [rbp+57h+arg_10], eax
0x18003a875  mov     rax, [rdi+18h]
0x18003a879  mov     [rbp+57h+var_40], rax
0x18003a87d  mov     eax, [rdi]
0x18003a87f  mov     [rbp+57h+arg_18], eax
0x18003a882  mov     rax, [rdi+80h]
0x18003a889  mov     [rbp+57h+var_38], rax
0x18003a88d  mov     eax, [rdi+40h]
0x18003a890  mov     [rbp+57h+var_70], eax
0x18003a893  mov     rax, [rdi+38h]
0x18003a897  mov     [rbp+57h+var_30], rax
0x18003a89b  mov     eax, [rdi+8]
0x18003a89e  mov     [rbp+57h+var_6C], eax
0x18003a8a1  lea     rax, [rbp+57h+var_68]
0x18003a8a5  mov     [rsp+110h+var_78], rax
0x18003a8ad  lea     rax, [rbp+57h+var_60]
0x18003a8b1  mov     [rsp+110h+var_80], rax
0x18003a8b9  lea     rax, [rbp+57h+arg_0]
0x18003a8bd  mov     [rsp+110h+var_88], rax
0x18003a8c5  lea     rax, [rbp+57h+var_58]
0x18003a8c9  mov     [rsp+110h+var_90], rax
0x18003a8d1  lea     rax, [rbp+57h+var_50]
0x18003a8d5  mov     [rsp+110h+var_98], rax
0x18003a8da  lea     rax, [rbp+57h+arg_8]
0x18003a8de  mov     [rsp+110h+var_A0], rax
0x18003a8e3  lea     rax, [rbp+57h+var_48]
0x18003a8e7  mov     [rsp+110h+var_A8], rax
0x18003a8ec  lea     rax, [rbp+57h+arg_10]
0x18003a8f0  mov     [rsp+110h+var_B0], rax
0x18003a8f5  lea     rax, [rbp+57h+var_40]
0x18003a8f9  mov     [rsp+110h+var_B8], rax
0x18003a8fe  lea     rax, [rbp+57h+arg_18]
0x18003a902  mov     [rsp+110h+var_C0], rax
0x18003a907  lea     rax, [rbp+57h+var_38]
0x18003a90b  mov     [rsp+110h+var_C8], rax
0x18003a910  lea     rax, [rbp+57h+var_70]
0x18003a914  mov     [rsp+110h+var_D0], rax
0x18003a919  lea     rax, [rbp+57h+var_30]
0x18003a91d  mov     [rsp+110h+var_D8], rax
0x18003a922  lea     rax, [rbp+57h+var_6C]
0x18003a926  mov     [rsp+110h+var_E0], rax
0x18003a92b  lea     rax, [rbp+57h+var_28]
0x18003a92f  mov     [rsp+110h+var_E8], rax
0x18003a934  lea     rax, [rbp+57h+var_20]
0x18003a938  mov     [rbp+57h+var_68], rcx
0x18003a93c  mov     rcx, r9
0x18003a93f  mov     [rsp+110h+var_F0], rax
0x18003a944  mov     [rbp+57h+var_28], 1000000h
0x18003a94c  mov     [rbp+57h+var_20], 0
0x18003a954  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18003a959  jmp     short loc_18003A9D2
0x18003a95b  call    ?zInternalStop@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18003a960  call    ?Provider@LUATelemetry@@SAPEBU_tlgProvider_t@@XZ; LUATelemetry::Provider(void)
0x18003a965  mov     rdi, rax
0x18003a968  mov     ecx, [rax]
0x18003a96a  cmp     ecx, 5
0x18003a96d  jbe     short loc_18003A9D2
0x18003a96f  mov     rdx, 200000000000h
0x18003a979  mov     rcx, rax
0x18003a97c  call    _tlgKeywordOn
0x18003a981  test    al, al
0x18003a983  jz      short loc_18003A9D2
0x18003a985  call    cs:__imp_GetCurrentThreadId
0x18003a98b  mov     r8, [rbx+110h]
0x18003a992  lea     rdx, word_180054E56
0x18003a999  mov     [rbp+57h+arg_0], eax
0x18003a99c  mov     rcx, rdi
0x18003a99f  mov     eax, [r8+48h]
0x18003a9a3  add     r8, 8
0x18003a9a7  mov     [rbp+57h+arg_8], eax
0x18003a9aa  lea     rax, [rbp+57h+arg_0]
0x18003a9ae  mov     [rsp+110h+var_E0], rax
0x18003a9b3  lea     rax, [rbp+57h+arg_8]
0x18003a9b7  mov     [rsp+110h+var_E8], rax
0x18003a9bc  lea     rax, [rbp+57h+arg_10]
0x18003a9c0  mov     [rsp+110h+var_F0], rax
0x18003a9c5  mov     [rbp+57h+arg_10], 0
0x18003a9cd  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18003a9d2  mov     rcx, rbx
0x18003a9d5  add     rsp, 100h
0x18003a9dc  pop     rdi
0x18003a9dd  pop     rbx
0x18003a9de  pop     rbp
0x18003a9df  jmp     ?IgnoreCurrentThread@?$ActivityBase@VLUATelemetry@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
