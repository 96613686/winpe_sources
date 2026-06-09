# LUATelemetry::AppXSyncActivity::Stop(int)

- ea: `0x180040d50`
- end: `0x180040fa4`
- name: `?Stop@AppXSyncActivity@LUATelemetry@@QEAAXH@Z`
- size: `596`
- prototype: `void __fastcall(LUATelemetry::AppXSyncActivity *__hidden this, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180040304`

## callees

- `0x180003ddc`
- `0x1800040a4`
- `0x18000cb30`
- `0x180018d70`
- `0x18001fd6c`
- `0x18001fd94`
- `0x180040d50`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180040f2e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180040f2e`

## pseudocode

```c
void __fastcall LUATelemetry::AppXSyncActivity::Stop(LUATelemetry::AppXSyncActivity *this, int a2)
{
  int *v2; // rax
  int v5; // ecx
  int *v6; // rdi
  _DWORD *v7; // rcx
  int v8; // ecx
  int v9; // r9d
  __int64 v10; // r8
  struct LUATelemetry *v11; // rax
  _DWORD *v12; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v14; // r8
  int v15; // r9d
  int v16; // [rsp+B0h] [rbp-80h] BYREF
  int v17; // [rsp+B4h] [rbp-7Ch] BYREF
  int v18; // [rsp+B8h] [rbp-78h] BYREF
  int v19; // [rsp+BCh] [rbp-74h] BYREF
  __int64 v20; // [rsp+C0h] [rbp-70h] BYREF
  __int64 v21; // [rsp+C8h] [rbp-68h] BYREF
  __int64 v22; // [rsp+D0h] [rbp-60h] BYREF
  __int64 v23; // [rsp+D8h] [rbp-58h] BYREF
  __int64 v24; // [rsp+E0h] [rbp-50h] BYREF
  __int64 v25; // [rsp+E8h] [rbp-48h] BYREF
  __int64 v26; // [rsp+F0h] [rbp-40h] BYREF
  __int64 v27; // [rsp+F8h] [rbp-38h] BYREF
  __int64 v28; // [rsp+100h] [rbp-30h] BYREF
  __int64 v29[3]; // [rsp+108h] [rbp-28h] BYREF
  int v30; // [rsp+130h] [rbp+0h] BYREF
  DWORD v31; // [rsp+140h] [rbp+10h] BYREF
  int v32; // [rsp+148h] [rbp+18h] BYREF

  v2 = (int *)*((_QWORD *)this + 34);
  v5 = v2[18];
  if ( v5 >= 0 || v5 != v2[22] || (v6 = v2 + 20, v2 == (int *)-80LL) )
  {
    wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(this);
    v11 = LUATelemetry::Instance();
    v12 = (_DWORD *)*((_QWORD *)v11 + 1);
    if ( *v12 > 5u && (unsigned __int8)tlgKeywordOn(*((_QWORD *)v11 + 1), 0x400000000000LL) )
    {
      v30 = a2;
      CurrentThreadId = GetCurrentThreadId();
      v14 = *((_QWORD *)this + 34);
      v31 = CurrentThreadId;
      v32 = *(_DWORD *)(v14 + 72);
      v20 = 50331648;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (_DWORD)v12,
        (unsigned int)&unk_180053DEE,
        v14 + 8,
        v15,
        (__int64)&v20,
        (__int64)&v32,
        (__int64)&v31,
        (__int64)&v30);
    }
  }
  else
  {
    wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(this);
    v7 = (_DWORD *)*((_QWORD *)LUATelemetry::Instance() + 1);
    if ( *v7 > 5u && (unsigned __int8)tlgKeywordOn(v7, 0x400000000000LL) )
    {
      v10 = *((_QWORD *)this + 34);
      v21 = *((_QWORD *)v6 + 15);
      v22 = *((_QWORD *)v6 + 14);
      v31 = v6[26];
      v23 = *((_QWORD *)v6 + 12);
      v24 = *((_QWORD *)v6 + 11);
      v32 = v6[20];
      v25 = *((_QWORD *)v6 + 9);
      v16 = v6[8];
      v26 = *((_QWORD *)v6 + 3);
      v17 = *v6;
      v27 = *((_QWORD *)v6 + 16);
      v18 = v6[16];
      v28 = *((_QWORD *)v6 + 7);
      v19 = v6[2];
      v30 = a2;
      v29[0] = 0x1000000;
      v20 = 50331648;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        v8,
        (unsigned int)&unk_1800539A7,
        v10 + 8,
        v9,
        (__int64)&v20,
        (__int64)v29,
        (__int64)&v19,
        (__int64)&v28,
        (__int64)&v18,
        (__int64)&v27,
        (__int64)&v17,
        (__int64)&v26,
        (__int64)&v16,
        (__int64)&v25,
        (__int64)&v32,
        (__int64)&v24,
        (__int64)&v23,
        (__int64)&v31,
        (__int64)&v22,
        (__int64)&v21,
        (__int64)&v30);
    }
  }
  wil::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(this);
}

```

## disassembly

```asm
0x180040d50  mov     [rsp-8+arg_8], rbx
0x180040d55  push    rbp
0x180040d56  push    rsi
0x180040d57  push    rdi
0x180040d58  lea     rbp, [rsp+20h]
0x180040d5d  sub     rsp, 110h
0x180040d64  mov     rax, [rcx+110h]
0x180040d6b  mov     rbx, rcx
0x180040d6e  mov     esi, edx
0x180040d70  mov     ecx, [rax+48h]
0x180040d73  test    ecx, ecx
0x180040d75  jns     loc_180040EFF
0x180040d7b  cmp     ecx, [rax+58h]
0x180040d7e  jnz     loc_180040EFF
0x180040d84  lea     rdi, [rax+50h]
0x180040d88  test    rdi, rdi
0x180040d8b  jz      loc_180040EFF
0x180040d91  mov     rcx, rbx
0x180040d94  call    ?zInternalStop@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180040d99  call    ?Instance@LUATelemetry@@KAPEAV1@XZ; LUATelemetry::Instance(void)
0x180040d9e  mov     rcx, [rax+8]
0x180040da2  cmp     dword ptr [rcx], 5
0x180040da5  jbe     loc_180040F8A
0x180040dab  mov     rdx, 400000000000h
0x180040db5  call    _tlgKeywordOn
0x180040dba  test    al, al
0x180040dbc  jz      loc_180040F8A
0x180040dc2  mov     rax, [rdi+78h]
0x180040dc6  lea     rdx, unk_1800539A7
0x180040dcd  mov     r8, [rbx+110h]
0x180040dd4  mov     [rbp-10h+var_58], rax
0x180040dd8  add     r8, 8
0x180040ddc  mov     rax, [rdi+70h]
0x180040de0  mov     [rbp-10h+var_50], rax
0x180040de4  mov     eax, [rdi+68h]
0x180040de7  mov     [rbp-10h+arg_10], eax
0x180040dea  mov     rax, [rdi+60h]
0x180040dee  mov     [rbp-10h+var_48], rax
0x180040df2  mov     rax, [rdi+58h]
0x180040df6  mov     [rbp-10h+var_40], rax
0x180040dfa  mov     eax, [rdi+50h]
0x180040dfd  mov     [rbp-10h+arg_18], eax
0x180040e00  mov     rax, [rdi+48h]
0x180040e04  mov     [rbp-10h+var_38], rax
0x180040e08  mov     eax, [rdi+20h]
0x180040e0b  mov     [rbp-10h+var_70], eax
0x180040e0e  mov     rax, [rdi+18h]
0x180040e12  mov     [rbp-10h+var_30], rax
0x180040e16  mov     eax, [rdi]
0x180040e18  mov     [rbp-10h+var_6C], eax
0x180040e1b  mov     rax, [rdi+80h]
0x180040e22  mov     [rbp-10h+var_28], rax
0x180040e26  mov     eax, [rdi+40h]
0x180040e29  mov     [rbp-10h+var_68], eax
0x180040e2c  mov     rax, [rdi+38h]
0x180040e30  mov     [rbp-10h+var_20], rax
0x180040e34  mov     eax, [rdi+8]
0x180040e37  mov     [rbp-10h+var_64], eax
0x180040e3a  lea     rax, [rbp-10h+arg_0]
0x180040e3e  mov     [rsp+120h+var_80], rax
0x180040e46  lea     rax, [rbp-10h+var_58]
0x180040e4a  mov     [rsp+120h+var_88], rax
0x180040e52  lea     rax, [rbp-10h+var_50]
0x180040e56  mov     [rsp+120h+var_90], rax
0x180040e5e  lea     rax, [rbp-10h+arg_10]
0x180040e62  mov     [rsp+120h+var_98], rax
0x180040e6a  lea     rax, [rbp-10h+var_48]
0x180040e6e  mov     [rsp+120h+var_A0], rax
0x180040e76  lea     rax, [rbp-10h+var_40]
0x180040e7a  mov     [rsp+120h+var_A8], rax
0x180040e7f  lea     rax, [rbp-10h+arg_18]
0x180040e83  mov     [rsp+120h+var_B0], rax
0x180040e88  lea     rax, [rbp-10h+var_38]
0x180040e8c  mov     [rsp+120h+var_B8], rax
0x180040e91  lea     rax, [rbp-10h+var_70]
0x180040e95  mov     [rsp+120h+var_C0], rax
0x180040e9a  lea     rax, [rbp-10h+var_30]
0x180040e9e  mov     [rsp+120h+var_C8], rax
0x180040ea3  lea     rax, [rbp-10h+var_6C]
0x180040ea7  mov     [rsp+120h+var_D0], rax
0x180040eac  lea     rax, [rbp-10h+var_28]
0x180040eb0  mov     [rsp+120h+var_D8], rax
0x180040eb5  lea     rax, [rbp-10h+var_68]
0x180040eb9  mov     [rsp+120h+var_E0], rax
0x180040ebe  lea     rax, [rbp-10h+var_20]
0x180040ec2  mov     [rsp+120h+var_E8], rax
0x180040ec7  lea     rax, [rbp-10h+var_64]
0x180040ecb  mov     [rsp+120h+var_F0], rax
0x180040ed0  lea     rax, [rbp-10h+var_18]
0x180040ed4  mov     [rsp+120h+var_F8], rax
0x180040ed9  lea     rax, [rbp-10h+var_60]
0x180040edd  mov     [rsp+120h+var_100], rax
0x180040ee2  mov     [rbp-10h+arg_0], esi
0x180040ee5  mov     [rbp-10h+var_18], 1000000h
0x180040eed  mov     [rbp-10h+var_60], 3000000h
0x180040ef5  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@454564564@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x180040efa  jmp     loc_180040F8A
0x180040eff  mov     rcx, rbx
0x180040f02  call    ?zInternalStop@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180040f07  call    ?Instance@LUATelemetry@@KAPEAV1@XZ; LUATelemetry::Instance(void)
0x180040f0c  mov     rdi, [rax+8]
0x180040f10  cmp     dword ptr [rdi], 5
0x180040f13  jbe     short loc_180040F8A
0x180040f15  mov     rdx, 400000000000h
0x180040f1f  mov     rcx, rdi
0x180040f22  call    _tlgKeywordOn
0x180040f27  test    al, al
0x180040f29  jz      short loc_180040F8A
0x180040f2b  mov     [rbp-10h+arg_0], esi
0x180040f2e  call    cs:__imp_GetCurrentThreadId
0x180040f35  nop     dword ptr [rax+rax+00h]
0x180040f3a  mov     r8, [rbx+110h]
0x180040f41  lea     rdx, unk_180053DEE
0x180040f48  mov     [rbp-10h+arg_10], eax
0x180040f4b  mov     rcx, rdi
0x180040f4e  mov     eax, [r8+48h]
0x180040f52  add     r8, 8
0x180040f56  mov     [rbp-10h+arg_18], eax
0x180040f59  lea     rax, [rbp-10h+arg_0]
0x180040f5d  mov     [rsp+120h+var_E8], rax
0x180040f62  lea     rax, [rbp-10h+arg_10]
0x180040f66  mov     [rsp+120h+var_F0], rax
0x180040f6b  lea     rax, [rbp-10h+arg_18]
0x180040f6f  mov     [rsp+120h+var_F8], rax
0x180040f74  lea     rax, [rbp-10h+var_60]
0x180040f78  mov     [rsp+120h+var_100], rax
0x180040f7d  mov     [rbp-10h+var_60], 3000000h
0x180040f85  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@44@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180040f8a  mov     rcx, rbx
0x180040f8d  mov     rbx, [rsp+120h+arg_8]
0x180040f95  add     rsp, 110h
0x180040f9c  pop     rdi
0x180040f9d  pop     rsi
0x180040f9e  pop     rbp
0x180040f9f  jmp     ?IgnoreCurrentThread@?$ActivityBase@VLUATelemetry@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
