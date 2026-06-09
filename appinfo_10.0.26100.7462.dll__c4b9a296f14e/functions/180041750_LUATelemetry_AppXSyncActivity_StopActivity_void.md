# LUATelemetry::AppXSyncActivity::StopActivity(void)

- ea: `0x180041750`
- end: `0x180041978`
- name: `?StopActivity@AppXSyncActivity@LUATelemetry@@MEAAXXZ`
- size: `552`
- prototype: `void __fastcall(LUATelemetry::AppXSyncActivity *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x18000c7d0`
- `0x18000cb30`
- `0x180010f8c`
- `0x180018d70`
- `0x18001fd6c`
- `0x18001fd94`
- `0x180041750`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180041913`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180041913`

## pseudocode

```c
void __fastcall LUATelemetry::AppXSyncActivity::StopActivity(LUATelemetry::AppXSyncActivity *this)
{
  int *v1; // rax
  int v3; // ecx
  int *v4; // rdi
  __int64 v5; // rdx
  _DWORD *v6; // rcx
  __int64 v7; // r8
  __int64 v8; // r9
  __int64 v9; // rcx
  __int64 v10; // r8
  struct LUATelemetry *v11; // rax
  _DWORD *v12; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v14; // r8
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
  __int64 v27[4]; // [rsp+F0h] [rbp+37h] BYREF
  DWORD v28; // [rsp+120h] [rbp+67h] BYREF
  int v29; // [rsp+128h] [rbp+6Fh] BYREF
  __int64 v30; // [rsp+130h] [rbp+77h] BYREF
  int v31; // [rsp+138h] [rbp+7Fh] BYREF

  v1 = (int *)*((_QWORD *)this + 34);
  v3 = v1[18];
  if ( v3 >= 0 || v3 != v1[22] || (v4 = v1 + 20, v1 == (int *)-80LL) )
  {
    wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(this);
    v11 = LUATelemetry::Instance();
    v12 = (_DWORD *)*((_QWORD *)v11 + 1);
    if ( *v12 > 5u && (unsigned __int8)tlgKeywordOn(*((_QWORD *)v11 + 1), 0x400000000000LL) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v14 = *((_QWORD *)this + 34);
      v28 = CurrentThreadId;
      v29 = *(_DWORD *)(v14 + 72);
      v30 = 50331648;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (__int64)v12,
        byte_180054922,
        (const GUID *)(v14 + 8),
        v15,
        (__int64)&v30,
        (__int64)&v29,
        (__int64)&v28);
    }
  }
  else
  {
    wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(this);
    v6 = (_DWORD *)*((_QWORD *)LUATelemetry::Instance() + 1);
    if ( *v6 > 5u && (unsigned __int8)tlgKeywordOn(v6, 0x400000000000LL) )
    {
      v10 = *((_QWORD *)this + 34);
      v18 = (const wchar_t *)*((_QWORD *)v4 + 15);
      v19 = (const unsigned __int16 *)*((_QWORD *)v4 + 14);
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
      v26 = 0x1000000;
      v27[0] = 50331648;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        v9,
        byte_1800547FA,
        (const GUID *)(v10 + 8),
        v8,
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
  wil::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
    this,
    v5,
    v7,
    v8);
}

```

## disassembly

```asm
0x180041750  push    rbp
0x180041752  push    rbx
0x180041753  push    rdi
0x180041754  lea     rbp, [rsp-47h]
0x180041759  sub     rsp, 100h
0x180041760  mov     rax, [rcx+110h]
0x180041767  mov     rbx, rcx
0x18004176a  mov     ecx, [rax+48h]
0x18004176d  test    ecx, ecx
0x18004176f  jns     loc_1800418E7
0x180041775  cmp     ecx, [rax+58h]
0x180041778  jnz     loc_1800418E7
0x18004177e  lea     rdi, [rax+50h]
0x180041782  test    rdi, rdi
0x180041785  jz      loc_1800418E7
0x18004178b  mov     rcx, rbx
0x18004178e  call    ?zInternalStop@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180041793  call    ?Instance@LUATelemetry@@KAPEAV1@XZ; LUATelemetry::Instance(void)
0x180041798  mov     rcx, [rax+8]
0x18004179c  cmp     dword ptr [rcx], 5
0x18004179f  jbe     loc_180041966
0x1800417a5  mov     rdx, 400000000000h
0x1800417af  call    _tlgKeywordOn
0x1800417b4  test    al, al
0x1800417b6  jz      loc_180041966
0x1800417bc  mov     rax, [rdi+78h]
0x1800417c0  lea     rdx, byte_1800547FA
0x1800417c7  mov     r8, [rbx+110h]
0x1800417ce  mov     [rbp+57h+var_68], rax
0x1800417d2  add     r8, 8
0x1800417d6  mov     rax, [rdi+70h]
0x1800417da  mov     [rbp+57h+var_60], rax
0x1800417de  mov     eax, [rdi+68h]
0x1800417e1  mov     [rbp+57h+arg_0], eax
0x1800417e4  mov     rax, [rdi+60h]
0x1800417e8  mov     [rbp+57h+var_58], rax
0x1800417ec  mov     rax, [rdi+58h]
0x1800417f0  mov     [rbp+57h+var_50], rax
0x1800417f4  mov     eax, [rdi+50h]
0x1800417f7  mov     [rbp+57h+arg_8], eax
0x1800417fa  mov     rax, [rdi+48h]
0x1800417fe  mov     [rbp+57h+var_48], rax
0x180041802  mov     eax, [rdi+20h]
0x180041805  mov     dword ptr [rbp+57h+arg_10], eax
0x180041808  mov     rax, [rdi+18h]
0x18004180c  mov     [rbp+57h+var_40], rax
0x180041810  mov     eax, [rdi]
0x180041812  mov     [rbp+57h+arg_18], eax
0x180041815  mov     rax, [rdi+80h]
0x18004181c  mov     [rbp+57h+var_38], rax
0x180041820  mov     eax, [rdi+40h]
0x180041823  mov     [rbp+57h+var_70], eax
0x180041826  mov     rax, [rdi+38h]
0x18004182a  mov     [rbp+57h+var_30], rax
0x18004182e  mov     eax, [rdi+8]
0x180041831  mov     [rbp+57h+var_6C], eax
0x180041834  lea     rax, [rbp+57h+var_68]
0x180041838  mov     [rsp+110h+var_78], rax
0x180041840  lea     rax, [rbp+57h+var_60]
0x180041844  mov     [rsp+110h+var_80], rax
0x18004184c  lea     rax, [rbp+57h+arg_0]
0x180041850  mov     [rsp+110h+var_88], rax
0x180041858  lea     rax, [rbp+57h+var_58]
0x18004185c  mov     [rsp+110h+var_90], rax
0x180041864  lea     rax, [rbp+57h+var_50]
0x180041868  mov     [rsp+110h+var_98], rax
0x18004186d  lea     rax, [rbp+57h+arg_8]
0x180041871  mov     [rsp+110h+var_A0], rax
0x180041876  lea     rax, [rbp+57h+var_48]
0x18004187a  mov     [rsp+110h+var_A8], rax
0x18004187f  lea     rax, [rbp+57h+arg_10]
0x180041883  mov     [rsp+110h+var_B0], rax
0x180041888  lea     rax, [rbp+57h+var_40]
0x18004188c  mov     [rsp+110h+var_B8], rax
0x180041891  lea     rax, [rbp+57h+arg_18]
0x180041895  mov     [rsp+110h+var_C0], rax
0x18004189a  lea     rax, [rbp+57h+var_38]
0x18004189e  mov     [rsp+110h+var_C8], rax
0x1800418a3  lea     rax, [rbp+57h+var_70]
0x1800418a7  mov     [rsp+110h+var_D0], rax
0x1800418ac  lea     rax, [rbp+57h+var_30]
0x1800418b0  mov     [rsp+110h+var_D8], rax
0x1800418b5  lea     rax, [rbp+57h+var_6C]
0x1800418b9  mov     [rsp+110h+var_E0], rax
0x1800418be  lea     rax, [rbp+57h+var_28]
0x1800418c2  mov     [rsp+110h+var_E8], rax
0x1800418c7  lea     rax, [rbp+57h+var_20]
0x1800418cb  mov     [rsp+110h+var_F0], rax
0x1800418d0  mov     [rbp+57h+var_28], 1000000h
0x1800418d8  mov     [rbp+57h+var_20], 3000000h
0x1800418e0  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x1800418e5  jmp     short loc_180041966
0x1800418e7  mov     rcx, rbx
0x1800418ea  call    ?zInternalStop@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x1800418ef  call    ?Instance@LUATelemetry@@KAPEAV1@XZ; LUATelemetry::Instance(void)
0x1800418f4  mov     rdi, [rax+8]
0x1800418f8  cmp     dword ptr [rdi], 5
0x1800418fb  jbe     short loc_180041966
0x1800418fd  mov     rdx, 400000000000h
0x180041907  mov     rcx, rdi
0x18004190a  call    _tlgKeywordOn
0x18004190f  test    al, al
0x180041911  jz      short loc_180041966
0x180041913  call    cs:__imp_GetCurrentThreadId
0x18004191a  nop     dword ptr [rax+rax+00h]
0x18004191f  mov     r8, [rbx+110h]
0x180041926  lea     rdx, byte_180054922
0x18004192d  mov     [rbp+57h+arg_0], eax
0x180041930  mov     rcx, rdi
0x180041933  mov     eax, [r8+48h]
0x180041937  add     r8, 8
0x18004193b  mov     [rbp+57h+arg_8], eax
0x18004193e  lea     rax, [rbp+57h+arg_0]
0x180041942  mov     [rsp+110h+var_E0], rax
0x180041947  lea     rax, [rbp+57h+arg_8]
0x18004194b  mov     [rsp+110h+var_E8], rax
0x180041950  lea     rax, [rbp+57h+arg_10]
0x180041954  mov     [rsp+110h+var_F0], rax
0x180041959  mov     [rbp+57h+arg_10], 3000000h
0x180041961  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180041966  mov     rcx, rbx
0x180041969  add     rsp, 100h
0x180041970  pop     rdi
0x180041971  pop     rbx
0x180041972  pop     rbp
0x180041973  jmp     ?IgnoreCurrentThread@?$ActivityBase@VLUATelemetry@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
