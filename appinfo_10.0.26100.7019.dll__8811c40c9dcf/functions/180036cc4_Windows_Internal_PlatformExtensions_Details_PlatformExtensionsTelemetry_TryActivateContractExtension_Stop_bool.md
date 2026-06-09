# Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::Stop(bool,bool,ushort const *)

- ea: `0x180036cc4`
- end: `0x180036f6b`
- name: `?Stop@TryActivateContractExtension@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@QEAAX_N0PEBG@Z`
- size: `679`
- prototype: `void __fastcall(Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension *__hidden this, bool, bool, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x1800380c0`

## callees

- `0x180002ec0`
- `0x18000329c`
- `0x18000cb30`
- `0x180010b08`
- `0x180018ac0`
- `0x180035728`
- `0x180036cc4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180036edc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180036edc`

## pseudocode

```c
void __fastcall Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::Stop(
        Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension *this,
        char a2,
        char a3,
        const unsigned __int16 *a4)
{
  int *v4; // rax
  int v9; // ecx
  int *v10; // rdi
  const struct _tlgProvider_t *v11; // rcx
  int v12; // ecx
  int v13; // r9d
  __int64 v14; // r8
  __int64 v15; // rax
  const struct _tlgProvider_t *v16; // rax
  int v17; // edi
  DWORD CurrentThreadId; // eax
  __int64 v19; // r8
  int v20; // eax
  int v21; // r9d
  _BYTE v22[4]; // [rsp+C0h] [rbp-80h] BYREF
  int v23; // [rsp+C4h] [rbp-7Ch] BYREF
  DWORD v24; // [rsp+C8h] [rbp-78h] BYREF
  int v25; // [rsp+CCh] [rbp-74h] BYREF
  int v26; // [rsp+D0h] [rbp-70h] BYREF
  int v27; // [rsp+D4h] [rbp-6Ch] BYREF
  int v28; // [rsp+D8h] [rbp-68h] BYREF
  __int64 v29; // [rsp+E0h] [rbp-60h] BYREF
  const unsigned __int16 *v30; // [rsp+E8h] [rbp-58h] BYREF
  const unsigned __int16 *v31; // [rsp+F0h] [rbp-50h] BYREF
  __int64 v32; // [rsp+F8h] [rbp-48h] BYREF
  __int64 v33; // [rsp+100h] [rbp-40h] BYREF
  __int64 v34; // [rsp+108h] [rbp-38h] BYREF
  __int64 v35; // [rsp+110h] [rbp-30h] BYREF
  __int64 v36; // [rsp+118h] [rbp-28h] BYREF
  __int64 v37; // [rsp+120h] [rbp-20h] BYREF
  __int64 v38; // [rsp+128h] [rbp-18h] BYREF
  __int64 v39; // [rsp+130h] [rbp-10h] BYREF
  char v40; // [rsp+160h] [rbp+20h] BYREF

  v4 = (int *)*((_QWORD *)this + 34);
  v9 = v4[18];
  if ( v9 >= 0 || v9 != v4[22] || (v10 = v4 + 20, v4 == (int *)-80LL) )
  {
    wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(this);
    v16 = Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider();
    v17 = (int)v16;
    if ( *(_DWORD *)v16 > 5u && (unsigned __int8)tlgKeywordOn(v16, 0x400000000000LL) )
    {
      v30 = a4;
      v40 = a3;
      v22[0] = a2;
      CurrentThreadId = GetCurrentThreadId();
      v19 = *((_QWORD *)this + 34);
      v24 = CurrentThreadId;
      v20 = *(_DWORD *)(v19 + 72);
      v29 = 0;
      v23 = v20;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapSz<unsigned short>>(
        v17,
        (unsigned int)&unk_180050305,
        v19 + 8,
        v21,
        (__int64)&v29,
        (__int64)&v23,
        (__int64)&v24,
        (__int64)v22,
        (__int64)&v40,
        (__int64)&v30);
    }
  }
  else
  {
    wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(this);
    v11 = Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider();
    if ( *(_DWORD *)v11 > 5u && (unsigned __int8)tlgKeywordOn(v11, 0x400000000000LL) )
    {
      v32 = *((_QWORD *)v10 + 15);
      v33 = *((_QWORD *)v10 + 14);
      v14 = *((_QWORD *)this + 34);
      v25 = v10[26];
      v15 = *((_QWORD *)v10 + 12);
      v30 = 0;
      v34 = v15;
      v35 = *((_QWORD *)v10 + 11);
      v26 = v10[20];
      v36 = *((_QWORD *)v10 + 9);
      v27 = v10[8];
      v37 = *((_QWORD *)v10 + 3);
      v28 = *v10;
      v38 = *((_QWORD *)v10 + 16);
      v23 = v10[16];
      v39 = *((_QWORD *)v10 + 7);
      v24 = v10[2];
      v31 = a4;
      v40 = a3;
      v22[0] = a2;
      v29 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapSz<unsigned short>>(
        v12,
        (unsigned int)&unk_1800510C6,
        v14 + 8,
        v13,
        (__int64)&v30,
        (__int64)&v29,
        (__int64)&v24,
        (__int64)&v39,
        (__int64)&v23,
        (__int64)&v38,
        (__int64)&v28,
        (__int64)&v37,
        (__int64)&v27,
        (__int64)&v36,
        (__int64)&v26,
        (__int64)&v35,
        (__int64)&v34,
        (__int64)&v25,
        (__int64)&v33,
        (__int64)&v32,
        (__int64)v22,
        (__int64)&v40,
        (__int64)&v31);
    }
  }
  wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x180036cc4  mov     [rsp-18h+arg_8], rbx
0x180036cc9  mov     [rsp-18h+arg_10], rsi
0x180036cce  mov     [rsp-18h+arg_18], rdi
0x180036cd3  push    rbp
0x180036cd4  push    r14
0x180036cd6  push    r15
0x180036cd8  mov     rbp, rsp
0x180036cdb  sub     rsp, 140h
0x180036ce2  mov     rax, [rcx+110h]
0x180036ce9  mov     rbx, rcx
0x180036cec  mov     rsi, r9
0x180036cef  mov     r14b, r8b
0x180036cf2  mov     r15b, dl
0x180036cf5  mov     ecx, [rax+48h]
0x180036cf8  test    ecx, ecx
0x180036cfa  jns     loc_180036EA1
0x180036d00  cmp     ecx, [rax+58h]
0x180036d03  jnz     loc_180036EA1
0x180036d09  lea     rdi, [rax+50h]
0x180036d0d  test    rdi, rdi
0x180036d10  jz      loc_180036EA1
0x180036d16  mov     rcx, rbx
0x180036d19  call    ?zInternalStop@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180036d1e  call    ?Provider@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider(void)
0x180036d23  mov     rcx, rax
0x180036d26  cmp     dword ptr [rax], 5
0x180036d29  jbe     loc_180036F47
0x180036d2f  mov     rdx, 400000000000h
0x180036d39  call    _tlgKeywordOn
0x180036d3e  test    al, al
0x180036d40  jz      loc_180036F47
0x180036d46  mov     rax, [rdi+78h]
0x180036d4a  lea     rdx, unk_1800510C6
0x180036d51  mov     [rbp+var_48], rax
0x180036d55  mov     rax, [rdi+70h]
0x180036d59  mov     [rbp+var_40], rax
0x180036d5d  mov     eax, [rdi+68h]
0x180036d60  mov     r8, [rbx+110h]
0x180036d67  mov     [rbp+var_74], eax
0x180036d6a  add     r8, 8
0x180036d6e  mov     rax, [rdi+60h]
0x180036d72  and     [rbp+var_58], 0
0x180036d77  mov     [rbp+var_38], rax
0x180036d7b  mov     rax, [rdi+58h]
0x180036d7f  mov     [rbp+var_30], rax
0x180036d83  mov     eax, [rdi+50h]
0x180036d86  mov     [rbp+var_70], eax
0x180036d89  mov     rax, [rdi+48h]
0x180036d8d  mov     [rbp+var_28], rax
0x180036d91  mov     eax, [rdi+20h]
0x180036d94  mov     [rbp+var_6C], eax
0x180036d97  mov     rax, [rdi+18h]
0x180036d9b  mov     [rbp+var_20], rax
0x180036d9f  mov     eax, [rdi]
0x180036da1  mov     [rbp+var_68], eax
0x180036da4  mov     rax, [rdi+80h]
0x180036dab  mov     [rbp+var_18], rax
0x180036daf  mov     eax, [rdi+40h]
0x180036db2  mov     [rbp+var_7C], eax
0x180036db5  mov     rax, [rdi+38h]
0x180036db9  mov     [rbp+var_10], rax
0x180036dbd  mov     eax, [rdi+8]
0x180036dc0  mov     [rbp+var_78], eax
0x180036dc3  lea     rax, [rbp+var_50]
0x180036dc7  mov     [rsp+140h+var_90], rax
0x180036dcf  lea     rax, [rbp+arg_0]
0x180036dd3  mov     [rsp+140h+var_98], rax
0x180036ddb  lea     rax, [rbp+var_80]
0x180036ddf  mov     [rsp+140h+var_A0], rax
0x180036de7  lea     rax, [rbp+var_48]
0x180036deb  mov     [rsp+140h+var_A8], rax
0x180036df3  lea     rax, [rbp+var_40]
0x180036df7  mov     [rsp+140h+var_B0], rax
0x180036dff  lea     rax, [rbp+var_74]
0x180036e03  mov     [rsp+140h+var_B8], rax
0x180036e0b  lea     rax, [rbp+var_38]
0x180036e0f  mov     [rsp+140h+var_C0], rax
0x180036e17  lea     rax, [rbp+var_30]
0x180036e1b  mov     [rsp+140h+var_C8], rax
0x180036e20  lea     rax, [rbp+var_70]
0x180036e24  mov     [rsp+140h+var_D0], rax
0x180036e29  lea     rax, [rbp+var_28]
0x180036e2d  mov     [rsp+140h+var_D8], rax
0x180036e32  lea     rax, [rbp+var_6C]
0x180036e36  mov     [rsp+140h+var_E0], rax
0x180036e3b  lea     rax, [rbp+var_20]
0x180036e3f  mov     [rsp+140h+var_E8], rax
0x180036e44  lea     rax, [rbp+var_68]
0x180036e48  mov     [rsp+140h+var_F0], rax
0x180036e4d  lea     rax, [rbp+var_18]
0x180036e51  mov     [rsp+140h+var_F8], rax
0x180036e56  lea     rax, [rbp+var_7C]
0x180036e5a  mov     [rsp+140h+var_100], rax
0x180036e5f  lea     rax, [rbp+var_10]
0x180036e63  mov     [rsp+140h+var_108], rax
0x180036e68  lea     rax, [rbp+var_78]
0x180036e6c  mov     [rsp+140h+var_110], rax
0x180036e71  lea     rax, [rbp+var_60]
0x180036e75  mov     [rsp+140h+var_118], rax
0x180036e7a  lea     rax, [rbp+var_58]
0x180036e7e  mov     [rsp+140h+var_120], rax
0x180036e83  mov     [rbp+var_50], rsi
0x180036e87  mov     [rbp+arg_0], r14b
0x180036e8b  mov     [rbp+var_80], r15b
0x180036e8f  mov     [rbp+var_60], 1000000h
0x180036e97  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U?$_tlgWrapperByVal@$00@@U5@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456AEBU?$_tlgWrapperByVal@$00@@76@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapSz<ushort> const &)
0x180036e9c  jmp     loc_180036F47
0x180036ea1  mov     rcx, rbx
0x180036ea4  call    ?zInternalStop@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180036ea9  call    ?Provider@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider(void)
0x180036eae  mov     rdi, rax
0x180036eb1  cmp     dword ptr [rax], 5
0x180036eb4  jbe     loc_180036F47
0x180036eba  mov     rdx, 400000000000h
0x180036ec4  mov     rcx, rax
0x180036ec7  call    _tlgKeywordOn
0x180036ecc  test    al, al
0x180036ece  jz      short loc_180036F47
0x180036ed0  mov     [rbp+var_58], rsi
0x180036ed4  mov     [rbp+arg_0], r14b
0x180036ed8  mov     [rbp+var_80], r15b
0x180036edc  call    cs:__imp_GetCurrentThreadId
0x180036ee3  nop     dword ptr [rax+rax+00h]
0x180036ee8  mov     r8, [rbx+110h]
0x180036eef  lea     rdx, unk_180050305
0x180036ef6  mov     [rbp+var_78], eax
0x180036ef9  mov     rcx, rdi
0x180036efc  mov     eax, [r8+48h]
0x180036f00  add     r8, 8
0x180036f04  and     [rbp+var_60], 0
0x180036f09  mov     [rbp+var_7C], eax
0x180036f0c  lea     rax, [rbp+var_58]
0x180036f10  mov     [rsp+140h+var_F8], rax
0x180036f15  lea     rax, [rbp+arg_0]
0x180036f19  mov     [rsp+140h+var_100], rax
0x180036f1e  lea     rax, [rbp+var_80]
0x180036f22  mov     [rsp+140h+var_108], rax
0x180036f27  lea     rax, [rbp+var_78]
0x180036f2b  mov     [rsp+140h+var_110], rax
0x180036f30  lea     rax, [rbp+var_7C]
0x180036f34  mov     [rsp+140h+var_118], rax
0x180036f39  lea     rax, [rbp+var_60]
0x180036f3d  mov     [rsp+140h+var_120], rax
0x180036f42  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapperByVal@$00@@U3@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapperByVal@$00@@5AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapSz<ushort> const &)
0x180036f47  mov     rcx, rbx
0x180036f4a  lea     r11, [rsp+140h+var_s0]
0x180036f52  mov     rbx, [r11+28h]
0x180036f56  mov     rsi, [r11+30h]
0x180036f5a  mov     rdi, [r11+38h]
0x180036f5e  mov     rsp, r11
0x180036f61  pop     r15
0x180036f63  pop     r14
0x180036f65  pop     rbp
0x180036f66  jmp     ?IgnoreCurrentThread@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
