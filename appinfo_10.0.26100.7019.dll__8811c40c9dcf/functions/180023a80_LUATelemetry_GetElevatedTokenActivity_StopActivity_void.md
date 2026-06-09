# LUATelemetry::GetElevatedTokenActivity::StopActivity(void)

- ea: `0x180023a80`
- end: `0x180023ca8`
- name: `?StopActivity@GetElevatedTokenActivity@LUATelemetry@@MEAAXXZ`
- size: `552`
- prototype: `void __fastcall(LUATelemetry::GetElevatedTokenActivity *__hidden this)`
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
- `0x180023a80`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180023c43`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180023c43`

## pseudocode

```c
void __fastcall LUATelemetry::GetElevatedTokenActivity::StopActivity(LUATelemetry::GetElevatedTokenActivity *this)
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
        byte_18004ECA7,
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
        byte_18004E68F,
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
0x180023a80  push    rbp
0x180023a82  push    rbx
0x180023a83  push    rdi
0x180023a84  lea     rbp, [rsp-47h]
0x180023a89  sub     rsp, 100h
0x180023a90  mov     rax, [rcx+110h]
0x180023a97  mov     rbx, rcx
0x180023a9a  mov     ecx, [rax+48h]
0x180023a9d  test    ecx, ecx
0x180023a9f  jns     loc_180023C17
0x180023aa5  cmp     ecx, [rax+58h]
0x180023aa8  jnz     loc_180023C17
0x180023aae  lea     rdi, [rax+50h]
0x180023ab2  test    rdi, rdi
0x180023ab5  jz      loc_180023C17
0x180023abb  mov     rcx, rbx
0x180023abe  call    ?zInternalStop@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180023ac3  call    ?Instance@LUATelemetry@@KAPEAV1@XZ; LUATelemetry::Instance(void)
0x180023ac8  mov     rcx, [rax+8]
0x180023acc  cmp     dword ptr [rcx], 5
0x180023acf  jbe     loc_180023C96
0x180023ad5  mov     rdx, 400000000000h
0x180023adf  call    _tlgKeywordOn
0x180023ae4  test    al, al
0x180023ae6  jz      loc_180023C96
0x180023aec  mov     rax, [rdi+78h]
0x180023af0  lea     rdx, byte_18004E68F
0x180023af7  mov     r8, [rbx+110h]
0x180023afe  mov     [rbp+57h+var_68], rax
0x180023b02  add     r8, 8
0x180023b06  mov     rax, [rdi+70h]
0x180023b0a  mov     [rbp+57h+var_60], rax
0x180023b0e  mov     eax, [rdi+68h]
0x180023b11  mov     [rbp+57h+arg_0], eax
0x180023b14  mov     rax, [rdi+60h]
0x180023b18  mov     [rbp+57h+var_58], rax
0x180023b1c  mov     rax, [rdi+58h]
0x180023b20  mov     [rbp+57h+var_50], rax
0x180023b24  mov     eax, [rdi+50h]
0x180023b27  mov     [rbp+57h+arg_8], eax
0x180023b2a  mov     rax, [rdi+48h]
0x180023b2e  mov     [rbp+57h+var_48], rax
0x180023b32  mov     eax, [rdi+20h]
0x180023b35  mov     dword ptr [rbp+57h+arg_10], eax
0x180023b38  mov     rax, [rdi+18h]
0x180023b3c  mov     [rbp+57h+var_40], rax
0x180023b40  mov     eax, [rdi]
0x180023b42  mov     [rbp+57h+arg_18], eax
0x180023b45  mov     rax, [rdi+80h]
0x180023b4c  mov     [rbp+57h+var_38], rax
0x180023b50  mov     eax, [rdi+40h]
0x180023b53  mov     [rbp+57h+var_70], eax
0x180023b56  mov     rax, [rdi+38h]
0x180023b5a  mov     [rbp+57h+var_30], rax
0x180023b5e  mov     eax, [rdi+8]
0x180023b61  mov     [rbp+57h+var_6C], eax
0x180023b64  lea     rax, [rbp+57h+var_68]
0x180023b68  mov     [rsp+110h+var_78], rax
0x180023b70  lea     rax, [rbp+57h+var_60]
0x180023b74  mov     [rsp+110h+var_80], rax
0x180023b7c  lea     rax, [rbp+57h+arg_0]
0x180023b80  mov     [rsp+110h+var_88], rax
0x180023b88  lea     rax, [rbp+57h+var_58]
0x180023b8c  mov     [rsp+110h+var_90], rax
0x180023b94  lea     rax, [rbp+57h+var_50]
0x180023b98  mov     [rsp+110h+var_98], rax
0x180023b9d  lea     rax, [rbp+57h+arg_8]
0x180023ba1  mov     [rsp+110h+var_A0], rax
0x180023ba6  lea     rax, [rbp+57h+var_48]
0x180023baa  mov     [rsp+110h+var_A8], rax
0x180023baf  lea     rax, [rbp+57h+arg_10]
0x180023bb3  mov     [rsp+110h+var_B0], rax
0x180023bb8  lea     rax, [rbp+57h+var_40]
0x180023bbc  mov     [rsp+110h+var_B8], rax
0x180023bc1  lea     rax, [rbp+57h+arg_18]
0x180023bc5  mov     [rsp+110h+var_C0], rax
0x180023bca  lea     rax, [rbp+57h+var_38]
0x180023bce  mov     [rsp+110h+var_C8], rax
0x180023bd3  lea     rax, [rbp+57h+var_70]
0x180023bd7  mov     [rsp+110h+var_D0], rax
0x180023bdc  lea     rax, [rbp+57h+var_30]
0x180023be0  mov     [rsp+110h+var_D8], rax
0x180023be5  lea     rax, [rbp+57h+var_6C]
0x180023be9  mov     [rsp+110h+var_E0], rax
0x180023bee  lea     rax, [rbp+57h+var_28]
0x180023bf2  mov     [rsp+110h+var_E8], rax
0x180023bf7  lea     rax, [rbp+57h+var_20]
0x180023bfb  mov     [rsp+110h+var_F0], rax
0x180023c00  mov     [rbp+57h+var_28], 1000000h
0x180023c08  mov     [rbp+57h+var_20], 3000000h
0x180023c10  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180023c15  jmp     short loc_180023C96
0x180023c17  mov     rcx, rbx
0x180023c1a  call    ?zInternalStop@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180023c1f  call    ?Instance@LUATelemetry@@KAPEAV1@XZ; LUATelemetry::Instance(void)
0x180023c24  mov     rdi, [rax+8]
0x180023c28  cmp     dword ptr [rdi], 5
0x180023c2b  jbe     short loc_180023C96
0x180023c2d  mov     rdx, 400000000000h
0x180023c37  mov     rcx, rdi
0x180023c3a  call    _tlgKeywordOn
0x180023c3f  test    al, al
0x180023c41  jz      short loc_180023C96
0x180023c43  call    cs:__imp_GetCurrentThreadId
0x180023c4a  nop     dword ptr [rax+rax+00h]
0x180023c4f  mov     r8, [rbx+110h]
0x180023c56  lea     rdx, byte_18004ECA7
0x180023c5d  mov     [rbp+57h+arg_0], eax
0x180023c60  mov     rcx, rdi
0x180023c63  mov     eax, [r8+48h]
0x180023c67  add     r8, 8
0x180023c6b  mov     [rbp+57h+arg_8], eax
0x180023c6e  lea     rax, [rbp+57h+arg_0]
0x180023c72  mov     [rsp+110h+var_E0], rax
0x180023c77  lea     rax, [rbp+57h+arg_8]
0x180023c7b  mov     [rsp+110h+var_E8], rax
0x180023c80  lea     rax, [rbp+57h+arg_10]
0x180023c84  mov     [rsp+110h+var_F0], rax
0x180023c89  mov     [rbp+57h+arg_10], 3000000h
0x180023c91  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180023c96  mov     rcx, rbx
0x180023c99  add     rsp, 100h
0x180023ca0  pop     rdi
0x180023ca1  pop     rbx
0x180023ca2  pop     rbp
0x180023ca3  jmp     ?IgnoreCurrentThread@?$ActivityBase@VLUATelemetry@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
