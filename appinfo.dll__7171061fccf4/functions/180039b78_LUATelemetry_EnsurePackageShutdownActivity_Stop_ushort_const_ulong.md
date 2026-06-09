# LUATelemetry::EnsurePackageShutdownActivity::Stop(ushort const *,ulong)

- ea: `0x180039b78`
- end: `0x180039df4`
- name: `?Stop@EnsurePackageShutdownActivity@LUATelemetry@@QEAAXPEBGK@Z`
- size: `636`
- prototype: `void __fastcall(LUATelemetry::EnsurePackageShutdownActivity *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180031724`

## callees

- `0x1800027d0`
- `0x18000f168`
- `0x180010110`
- `0x180011fd0`
- `0x18001b03c`
- `0x18001b23c`
- `0x180039b78`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180039d76`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180039d76`

## pseudocode

```c
void __fastcall LUATelemetry::EnsurePackageShutdownActivity::Stop(
        LUATelemetry::EnsurePackageShutdownActivity *this,
        const unsigned __int16 *a2,
        int a3)
{
  __int64 v3; // rdi
  int v7; // eax
  int *v8; // rdi
  const struct _tlgProvider_t *v9; // rax
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
  int v20; // [rsp+BCh] [rbp-74h] BYREF
  int v21; // [rsp+C0h] [rbp-70h] BYREF
  __int64 v22; // [rsp+C8h] [rbp-68h] BYREF
  const wchar_t *v23; // [rsp+D0h] [rbp-60h] BYREF
  const wchar_t *v24; // [rsp+D8h] [rbp-58h] BYREF
  const wchar_t *v25; // [rsp+E0h] [rbp-50h] BYREF
  const unsigned __int16 *v26; // [rsp+E8h] [rbp-48h] BYREF
  const wchar_t *v27; // [rsp+F0h] [rbp-40h] BYREF
  const unsigned __int16 *v28; // [rsp+F8h] [rbp-38h] BYREF
  const unsigned __int16 *v29; // [rsp+100h] [rbp-30h] BYREF
  const wchar_t *v30; // [rsp+108h] [rbp-28h] BYREF
  const unsigned __int16 *v31; // [rsp+110h] [rbp-20h] BYREF
  const unsigned __int16 *v32; // [rsp+118h] [rbp-18h] BYREF
  int v33; // [rsp+140h] [rbp+10h] BYREF
  DWORD v34; // [rsp+158h] [rbp+28h] BYREF

  v3 = *((_QWORD *)this + 34);
  v7 = *(_DWORD *)(v3 + 72);
  if ( v7 < 0 && (v8 = (int *)(v3 + 80), v7 == v8[2]) && v8 )
  {
    wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v9 = LUATelemetry::Provider();
    if ( *(_DWORD *)v9 > 5u && (unsigned __int8)tlgKeywordOn(v9, 0x200000000000LL) )
    {
      v25 = (const wchar_t *)*((_QWORD *)v8 + 15);
      v11 = *((_QWORD *)this + 34);
      v26 = (const unsigned __int16 *)*((_QWORD *)v8 + 14);
      v34 = v8[26];
      v27 = (const wchar_t *)*((_QWORD *)v8 + 12);
      v28 = (const unsigned __int16 *)*((_QWORD *)v8 + 11);
      v18 = v8[20];
      v29 = (const unsigned __int16 *)*((_QWORD *)v8 + 9);
      v19 = v8[8];
      v30 = (const wchar_t *)*((_QWORD *)v8 + 3);
      v20 = *v8;
      v31 = (const unsigned __int16 *)*((_QWORD *)v8 + 16);
      v21 = v8[16];
      v32 = (const unsigned __int16 *)*((_QWORD *)v8 + 7);
      v17 = v8[2];
      v33 = a3;
      v24 = a2;
      v22 = 0x1000000;
      v23 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        v10,
        (__int64)&unk_1800555D0,
        v11 + 8,
        v10,
        (__int64)&v23,
        (__int64)&v22,
        (__int64)&v17,
        &v32,
        (__int64)&v21,
        &v31,
        (__int64)&v20,
        &v30,
        (__int64)&v19,
        &v29,
        (__int64)&v18,
        &v28,
        &v27,
        (__int64)&v34,
        &v26,
        &v25,
        &v24,
        (__int64)&v33);
    }
  }
  else
  {
    wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v12 = LUATelemetry::Provider();
    v13 = (__int64)v12;
    if ( *(_DWORD *)v12 > 5u && (unsigned __int8)tlgKeywordOn(v12, 0x200000000000LL) )
    {
      v33 = a3;
      v23 = a2;
      CurrentThreadId = GetCurrentThreadId();
      v15 = *((_QWORD *)this + 34);
      v34 = CurrentThreadId;
      v17 = *(_DWORD *)(v15 + 72);
      v22 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        v13,
        (unsigned __int8 *)&unk_180054DD8,
        (const GUID *)(v15 + 8),
        v16,
        (__int64)&v22,
        (__int64)&v17,
        (__int64)&v34,
        &v23,
        (__int64)&v33);
    }
  }
  wil::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(this);
}

```

## disassembly

```asm
0x180039b78  mov     [rsp-8+arg_8], rbx
0x180039b7d  mov     [rsp-8+arg_10], rsi
0x180039b82  push    rbp
0x180039b83  push    rdi
0x180039b84  push    r14
0x180039b86  lea     rbp, [rsp+10h]
0x180039b8b  sub     rsp, 120h
0x180039b92  mov     rdi, [rcx+110h]
0x180039b99  mov     esi, r8d
0x180039b9c  mov     r14, rdx
0x180039b9f  mov     rbx, rcx
0x180039ba2  mov     eax, [rdi+48h]
0x180039ba5  test    eax, eax
0x180039ba7  jns     loc_180039D45
0x180039bad  add     rdi, 50h ; 'P'
0x180039bb1  cmp     eax, [rdi+8]
0x180039bb4  jnz     loc_180039D45
0x180039bba  test    rdi, rdi
0x180039bbd  jz      loc_180039D45
0x180039bc3  call    ?zInternalStop@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180039bc8  call    ?Provider@LUATelemetry@@SAPEBU_tlgProvider_t@@XZ; LUATelemetry::Provider(void)
0x180039bcd  mov     r9, rax
0x180039bd0  mov     ecx, [rax]
0x180039bd2  cmp     ecx, 5
0x180039bd5  jbe     loc_180039DD5
0x180039bdb  mov     rdx, 200000000000h
0x180039be5  mov     rcx, rax
0x180039be8  call    _tlgKeywordOn
0x180039bed  test    al, al
0x180039bef  jz      loc_180039DD5
0x180039bf5  mov     rax, [rdi+78h]
0x180039bf9  lea     rdx, unk_1800555D0
0x180039c00  mov     [rbp+var_50], rax
0x180039c04  mov     rcx, r9
0x180039c07  mov     rax, [rdi+70h]
0x180039c0b  mov     r8, [rbx+110h]
0x180039c12  mov     [rbp+var_48], rax
0x180039c16  add     r8, 8
0x180039c1a  mov     eax, [rdi+68h]
0x180039c1d  mov     [rbp+arg_18], eax
0x180039c20  mov     rax, [rdi+60h]
0x180039c24  mov     [rbp+var_40], rax
0x180039c28  mov     rax, [rdi+58h]
0x180039c2c  mov     [rbp+var_38], rax
0x180039c30  mov     eax, [rdi+50h]
0x180039c33  mov     [rbp+var_7C], eax
0x180039c36  mov     rax, [rdi+48h]
0x180039c3a  mov     [rbp+var_30], rax
0x180039c3e  mov     eax, [rdi+20h]
0x180039c41  mov     [rbp+var_78], eax
0x180039c44  mov     rax, [rdi+18h]
0x180039c48  mov     [rbp+var_28], rax
0x180039c4c  mov     eax, [rdi]
0x180039c4e  mov     [rbp+var_74], eax
0x180039c51  mov     rax, [rdi+80h]
0x180039c58  mov     [rbp+var_20], rax
0x180039c5c  mov     eax, [rdi+40h]
0x180039c5f  mov     [rbp+var_70], eax
0x180039c62  mov     rax, [rdi+38h]
0x180039c66  mov     [rbp+var_18], rax
0x180039c6a  mov     eax, [rdi+8]
0x180039c6d  mov     [rbp+var_80], eax
0x180039c70  lea     rax, [rbp+arg_0]
0x180039c74  mov     [rsp+130h+var_88], rax
0x180039c7c  lea     rax, [rbp+var_58]
0x180039c80  mov     [rsp+130h+var_90], rax
0x180039c88  lea     rax, [rbp+var_50]
0x180039c8c  mov     [rsp+130h+var_98], rax
0x180039c94  lea     rax, [rbp+var_48]
0x180039c98  mov     [rsp+130h+var_A0], rax
0x180039ca0  lea     rax, [rbp+arg_18]
0x180039ca4  mov     [rsp+130h+var_A8], rax
0x180039cac  lea     rax, [rbp+var_40]
0x180039cb0  mov     [rsp+130h+var_B0], rax
0x180039cb8  lea     rax, [rbp+var_38]
0x180039cbc  mov     [rsp+130h+var_B8], rax
0x180039cc1  lea     rax, [rbp+var_7C]
0x180039cc5  mov     [rsp+130h+var_C0], rax
0x180039cca  lea     rax, [rbp+var_30]
0x180039cce  mov     [rsp+130h+var_C8], rax
0x180039cd3  lea     rax, [rbp+var_78]
0x180039cd7  mov     [rsp+130h+var_D0], rax
0x180039cdc  lea     rax, [rbp+var_28]
0x180039ce0  mov     [rsp+130h+var_D8], rax
0x180039ce5  lea     rax, [rbp+var_74]
0x180039ce9  mov     [rsp+130h+var_E0], rax
0x180039cee  lea     rax, [rbp+var_20]
0x180039cf2  mov     [rsp+130h+var_E8], rax
0x180039cf7  lea     rax, [rbp+var_70]
0x180039cfb  mov     [rsp+130h+var_F0], rax
0x180039d00  lea     rax, [rbp+var_18]
0x180039d04  mov     [rsp+130h+var_F8], rax
0x180039d09  lea     rax, [rbp+var_80]
0x180039d0d  mov     [rsp+130h+var_100], rax
0x180039d12  lea     rax, [rbp+var_68]
0x180039d16  mov     [rsp+130h+var_108], rax
0x180039d1b  lea     rax, [rbp+var_60]
0x180039d1f  mov     [rsp+130h+var_110], rax
0x180039d24  mov     [rbp+arg_0], esi
0x180039d27  mov     [rbp+var_58], r14
0x180039d2b  mov     [rbp+var_68], 1000000h
0x180039d33  mov     [rbp+var_60], 0
0x180039d3b  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U4@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@4545645664@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x180039d40  jmp     loc_180039DD5
0x180039d45  call    ?zInternalStop@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180039d4a  call    ?Provider@LUATelemetry@@SAPEBU_tlgProvider_t@@XZ; LUATelemetry::Provider(void)
0x180039d4f  mov     rdi, rax
0x180039d52  mov     ecx, [rax]
0x180039d54  cmp     ecx, 5
0x180039d57  jbe     short loc_180039DD5
0x180039d59  mov     rdx, 200000000000h
0x180039d63  mov     rcx, rax
0x180039d66  call    _tlgKeywordOn
0x180039d6b  test    al, al
0x180039d6d  jz      short loc_180039DD5
0x180039d6f  mov     [rbp+arg_0], esi
0x180039d72  mov     [rbp+var_60], r14
0x180039d76  call    cs:__imp_GetCurrentThreadId
0x180039d7c  mov     r8, [rbx+110h]
0x180039d83  lea     rdx, unk_180054DD8
0x180039d8a  mov     [rbp+arg_18], eax
0x180039d8d  mov     rcx, rdi
0x180039d90  mov     eax, [r8+48h]
0x180039d94  add     r8, 8
0x180039d98  mov     [rbp+var_80], eax
0x180039d9b  lea     rax, [rbp+arg_0]
0x180039d9f  mov     [rsp+130h+var_F0], rax
0x180039da4  lea     rax, [rbp+var_60]
0x180039da8  mov     [rsp+130h+var_F8], rax
0x180039dad  lea     rax, [rbp+arg_18]
0x180039db1  mov     [rsp+130h+var_100], rax
0x180039db6  lea     rax, [rbp+var_80]
0x180039dba  mov     [rsp+130h+var_108], rax
0x180039dbf  lea     rax, [rbp+var_68]
0x180039dc3  mov     [rsp+130h+var_110], rax
0x180039dc8  mov     [rbp+var_68], 0
0x180039dd0  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapSz@G@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapSz@G@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x180039dd5  mov     rcx, rbx
0x180039dd8  lea     r11, [rsp+130h+var_10]
0x180039de0  mov     rbx, [r11+28h]
0x180039de4  mov     rsi, [r11+30h]
0x180039de8  mov     rsp, r11
0x180039deb  pop     r14
0x180039ded  pop     rdi
0x180039dee  pop     rbp
0x180039def  jmp     ?IgnoreCurrentThread@?$ActivityBase@VLUATelemetry@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
