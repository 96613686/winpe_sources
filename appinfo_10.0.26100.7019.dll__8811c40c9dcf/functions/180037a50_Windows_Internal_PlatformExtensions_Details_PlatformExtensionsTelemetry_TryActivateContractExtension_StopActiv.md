# Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::StopActivity(void)

- ea: `0x180037a50`
- end: `0x180037c76`
- name: `?StopActivity@TryActivateContractExtension@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@MEAAXXZ`
- size: `550`
- prototype: `void __fastcall(Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x18000c7d0`
- `0x18000cb30`
- `0x180010b08`
- `0x180010e4c`
- `0x180018ac0`
- `0x180035728`
- `0x180037a50`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180037c14`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180037c14`

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
        byte_18004F38D,
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
        byte_18004FA41,
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
0x180037a50  push    rbp
0x180037a52  push    rbx
0x180037a53  push    rdi
0x180037a54  lea     rbp, [rsp-47h]
0x180037a59  sub     rsp, 100h
0x180037a60  mov     rax, [rcx+110h]
0x180037a67  mov     rbx, rcx
0x180037a6a  mov     ecx, [rax+48h]
0x180037a6d  test    ecx, ecx
0x180037a6f  jns     loc_180037BE9
0x180037a75  cmp     ecx, [rax+58h]
0x180037a78  jnz     loc_180037BE9
0x180037a7e  lea     rdi, [rax+50h]
0x180037a82  test    rdi, rdi
0x180037a85  jz      loc_180037BE9
0x180037a8b  mov     rcx, rbx
0x180037a8e  call    ?zInternalStop@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180037a93  call    ?Provider@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider(void)
0x180037a98  mov     r9, rax
0x180037a9b  cmp     dword ptr [rax], 5
0x180037a9e  jbe     loc_180037C64
0x180037aa4  mov     rdx, 400000000000h
0x180037aae  mov     rcx, rax
0x180037ab1  call    _tlgKeywordOn
0x180037ab6  test    al, al
0x180037ab8  jz      loc_180037C64
0x180037abe  mov     rax, [rdi+70h]
0x180037ac2  lea     rdx, byte_18004FA41
0x180037ac9  mov     rcx, [rdi+78h]
0x180037acd  mov     r8, [rbx+110h]
0x180037ad4  and     [rbp+57h+var_20], 0
0x180037ad9  add     r8, 8
0x180037add  mov     [rbp+57h+var_60], rax
0x180037ae1  mov     eax, [rdi+68h]
0x180037ae4  mov     [rbp+57h+arg_0], eax
0x180037ae7  mov     rax, [rdi+60h]
0x180037aeb  mov     [rbp+57h+var_58], rax
0x180037aef  mov     rax, [rdi+58h]
0x180037af3  mov     [rbp+57h+var_50], rax
0x180037af7  mov     eax, [rdi+50h]
0x180037afa  mov     [rbp+57h+arg_8], eax
0x180037afd  mov     rax, [rdi+48h]
0x180037b01  mov     [rbp+57h+var_48], rax
0x180037b05  mov     eax, [rdi+20h]
0x180037b08  mov     dword ptr [rbp+57h+arg_10], eax
0x180037b0b  mov     rax, [rdi+18h]
0x180037b0f  mov     [rbp+57h+var_40], rax
0x180037b13  mov     eax, [rdi]
0x180037b15  mov     [rbp+57h+arg_18], eax
0x180037b18  mov     rax, [rdi+80h]
0x180037b1f  mov     [rbp+57h+var_38], rax
0x180037b23  mov     eax, [rdi+40h]
0x180037b26  mov     [rbp+57h+var_70], eax
0x180037b29  mov     rax, [rdi+38h]
0x180037b2d  mov     [rbp+57h+var_30], rax
0x180037b31  mov     eax, [rdi+8]
0x180037b34  mov     [rbp+57h+var_6C], eax
0x180037b37  lea     rax, [rbp+57h+var_68]
0x180037b3b  mov     [rsp+110h+var_78], rax
0x180037b43  lea     rax, [rbp+57h+var_60]
0x180037b47  mov     [rsp+110h+var_80], rax
0x180037b4f  lea     rax, [rbp+57h+arg_0]
0x180037b53  mov     [rsp+110h+var_88], rax
0x180037b5b  lea     rax, [rbp+57h+var_58]
0x180037b5f  mov     [rsp+110h+var_90], rax
0x180037b67  lea     rax, [rbp+57h+var_50]
0x180037b6b  mov     [rsp+110h+var_98], rax
0x180037b70  lea     rax, [rbp+57h+arg_8]
0x180037b74  mov     [rsp+110h+var_A0], rax
0x180037b79  lea     rax, [rbp+57h+var_48]
0x180037b7d  mov     [rsp+110h+var_A8], rax
0x180037b82  lea     rax, [rbp+57h+arg_10]
0x180037b86  mov     [rsp+110h+var_B0], rax
0x180037b8b  lea     rax, [rbp+57h+var_40]
0x180037b8f  mov     [rsp+110h+var_B8], rax
0x180037b94  lea     rax, [rbp+57h+arg_18]
0x180037b98  mov     [rsp+110h+var_C0], rax
0x180037b9d  lea     rax, [rbp+57h+var_38]
0x180037ba1  mov     [rsp+110h+var_C8], rax
0x180037ba6  lea     rax, [rbp+57h+var_70]
0x180037baa  mov     [rsp+110h+var_D0], rax
0x180037baf  lea     rax, [rbp+57h+var_30]
0x180037bb3  mov     [rsp+110h+var_D8], rax
0x180037bb8  lea     rax, [rbp+57h+var_6C]
0x180037bbc  mov     [rsp+110h+var_E0], rax
0x180037bc1  lea     rax, [rbp+57h+var_28]
0x180037bc5  mov     [rsp+110h+var_E8], rax
0x180037bca  lea     rax, [rbp+57h+var_20]
0x180037bce  mov     [rbp+57h+var_68], rcx
0x180037bd2  mov     rcx, r9
0x180037bd5  mov     [rsp+110h+var_F0], rax
0x180037bda  mov     [rbp+57h+var_28], 1000000h
0x180037be2  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180037be7  jmp     short loc_180037C64
0x180037be9  mov     rcx, rbx
0x180037bec  call    ?zInternalStop@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180037bf1  call    ?Provider@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider(void)
0x180037bf6  mov     rdi, rax
0x180037bf9  cmp     dword ptr [rax], 5
0x180037bfc  jbe     short loc_180037C64
0x180037bfe  mov     rdx, 400000000000h
0x180037c08  mov     rcx, rax
0x180037c0b  call    _tlgKeywordOn
0x180037c10  test    al, al
0x180037c12  jz      short loc_180037C64
0x180037c14  call    cs:__imp_GetCurrentThreadId
0x180037c1b  nop     dword ptr [rax+rax+00h]
0x180037c20  mov     r8, [rbx+110h]
0x180037c27  lea     rdx, byte_18004F38D
0x180037c2e  mov     [rbp+57h+arg_0], eax
0x180037c31  mov     rcx, rdi
0x180037c34  mov     eax, [r8+48h]
0x180037c38  add     r8, 8
0x180037c3c  and     [rbp+57h+arg_10], 0
0x180037c41  mov     [rbp+57h+arg_8], eax
0x180037c44  lea     rax, [rbp+57h+arg_0]
0x180037c48  mov     [rsp+110h+var_E0], rax
0x180037c4d  lea     rax, [rbp+57h+arg_8]
0x180037c51  mov     [rsp+110h+var_E8], rax
0x180037c56  lea     rax, [rbp+57h+arg_10]
0x180037c5a  mov     [rsp+110h+var_F0], rax
0x180037c5f  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180037c64  mov     rcx, rbx
0x180037c67  add     rsp, 100h
0x180037c6e  pop     rdi
0x180037c6f  pop     rbx
0x180037c70  pop     rbp
0x180037c71  jmp     ?IgnoreCurrentThread@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
