# LUATelemetry::RegistrySyncActivity::Stop(int)

- ea: `0x1800414ec`
- end: `0x180041740`
- name: `?Stop@RegistrySyncActivity@LUATelemetry@@QEAAXH@Z`
- size: `596`
- prototype: `void __fastcall(LUATelemetry::RegistrySyncActivity *__hidden this, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callers

- `0x180040c70`

## callees

- `0x180003ddc`
- `0x1800040a4`
- `0x18000cb30`
- `0x180018d70`
- `0x18001fd6c`
- `0x18001fd94`
- `0x1800414ec`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800416ca`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800416ca`

## pseudocode

```c
void __fastcall LUATelemetry::RegistrySyncActivity::Stop(LUATelemetry::RegistrySyncActivity *this, int a2)
{
  int *v2; // rax
  int v5; // ecx
  int *v6; // rdi
  __int64 v7; // rdx
  _DWORD *v8; // rcx
  __int64 v9; // r8
  __int64 v10; // r9
  int v11; // ecx
  __int64 v12; // r8
  struct LUATelemetry *v13; // rax
  _DWORD *v14; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v16; // r8
  int v17; // r9d
  int v18; // [rsp+B0h] [rbp-80h] BYREF
  int v19; // [rsp+B4h] [rbp-7Ch] BYREF
  int v20; // [rsp+B8h] [rbp-78h] BYREF
  int v21; // [rsp+BCh] [rbp-74h] BYREF
  __int64 v22; // [rsp+C0h] [rbp-70h] BYREF
  __int64 v23; // [rsp+C8h] [rbp-68h] BYREF
  __int64 v24; // [rsp+D0h] [rbp-60h] BYREF
  __int64 v25; // [rsp+D8h] [rbp-58h] BYREF
  __int64 v26; // [rsp+E0h] [rbp-50h] BYREF
  __int64 v27; // [rsp+E8h] [rbp-48h] BYREF
  __int64 v28; // [rsp+F0h] [rbp-40h] BYREF
  __int64 v29; // [rsp+F8h] [rbp-38h] BYREF
  __int64 v30; // [rsp+100h] [rbp-30h] BYREF
  __int64 v31[3]; // [rsp+108h] [rbp-28h] BYREF
  int v32; // [rsp+130h] [rbp+0h] BYREF
  DWORD v33; // [rsp+140h] [rbp+10h] BYREF
  int v34; // [rsp+148h] [rbp+18h] BYREF

  v2 = (int *)*((_QWORD *)this + 34);
  v5 = v2[18];
  if ( v5 >= 0 || v5 != v2[22] || (v6 = v2 + 20, v2 == (int *)-80LL) )
  {
    wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(this);
    v13 = LUATelemetry::Instance();
    v14 = (_DWORD *)*((_QWORD *)v13 + 1);
    if ( *v14 > 5u && (unsigned __int8)tlgKeywordOn(*((_QWORD *)v13 + 1), 0x400000000000LL) )
    {
      v32 = a2;
      CurrentThreadId = GetCurrentThreadId();
      v16 = *((_QWORD *)this + 34);
      v33 = CurrentThreadId;
      v34 = *(_DWORD *)(v16 + 72);
      v22 = 50331648;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (_DWORD)v14,
        (unsigned int)&unk_180054DA3,
        v16 + 8,
        v17,
        (__int64)&v22,
        (__int64)&v34,
        (__int64)&v33,
        (__int64)&v32);
    }
  }
  else
  {
    wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(this);
    v8 = (_DWORD *)*((_QWORD *)LUATelemetry::Instance() + 1);
    if ( *v8 > 5u && (unsigned __int8)tlgKeywordOn(v8, 0x400000000000LL) )
    {
      v12 = *((_QWORD *)this + 34);
      v23 = *((_QWORD *)v6 + 15);
      v24 = *((_QWORD *)v6 + 14);
      v33 = v6[26];
      v25 = *((_QWORD *)v6 + 12);
      v26 = *((_QWORD *)v6 + 11);
      v34 = v6[20];
      v27 = *((_QWORD *)v6 + 9);
      v18 = v6[8];
      v28 = *((_QWORD *)v6 + 3);
      v19 = *v6;
      v29 = *((_QWORD *)v6 + 16);
      v20 = v6[16];
      v30 = *((_QWORD *)v6 + 7);
      v21 = v6[2];
      v32 = a2;
      v31[0] = 0x1000000;
      v22 = 50331648;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        v11,
        (unsigned int)&unk_180054B3D,
        v12 + 8,
        v10,
        (__int64)&v22,
        (__int64)v31,
        (__int64)&v21,
        (__int64)&v30,
        (__int64)&v20,
        (__int64)&v29,
        (__int64)&v19,
        (__int64)&v28,
        (__int64)&v18,
        (__int64)&v27,
        (__int64)&v34,
        (__int64)&v26,
        (__int64)&v25,
        (__int64)&v33,
        (__int64)&v24,
        (__int64)&v23,
        (__int64)&v32);
    }
  }
  wil::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
    this,
    v7,
    v9,
    v10);
}

```

## disassembly

```asm
0x1800414ec  mov     [rsp-8+arg_8], rbx
0x1800414f1  push    rbp
0x1800414f2  push    rsi
0x1800414f3  push    rdi
0x1800414f4  lea     rbp, [rsp+20h]
0x1800414f9  sub     rsp, 110h
0x180041500  mov     rax, [rcx+110h]
0x180041507  mov     rbx, rcx
0x18004150a  mov     esi, edx
0x18004150c  mov     ecx, [rax+48h]
0x18004150f  test    ecx, ecx
0x180041511  jns     loc_18004169B
0x180041517  cmp     ecx, [rax+58h]
0x18004151a  jnz     loc_18004169B
0x180041520  lea     rdi, [rax+50h]
0x180041524  test    rdi, rdi
0x180041527  jz      loc_18004169B
0x18004152d  mov     rcx, rbx
0x180041530  call    ?zInternalStop@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180041535  call    ?Instance@LUATelemetry@@KAPEAV1@XZ; LUATelemetry::Instance(void)
0x18004153a  mov     rcx, [rax+8]
0x18004153e  cmp     dword ptr [rcx], 5
0x180041541  jbe     loc_180041726
0x180041547  mov     rdx, 400000000000h
0x180041551  call    _tlgKeywordOn
0x180041556  test    al, al
0x180041558  jz      loc_180041726
0x18004155e  mov     rax, [rdi+78h]
0x180041562  lea     rdx, unk_180054B3D
0x180041569  mov     r8, [rbx+110h]
0x180041570  mov     [rbp-10h+var_58], rax
0x180041574  add     r8, 8
0x180041578  mov     rax, [rdi+70h]
0x18004157c  mov     [rbp-10h+var_50], rax
0x180041580  mov     eax, [rdi+68h]
0x180041583  mov     [rbp-10h+arg_10], eax
0x180041586  mov     rax, [rdi+60h]
0x18004158a  mov     [rbp-10h+var_48], rax
0x18004158e  mov     rax, [rdi+58h]
0x180041592  mov     [rbp-10h+var_40], rax
0x180041596  mov     eax, [rdi+50h]
0x180041599  mov     [rbp-10h+arg_18], eax
0x18004159c  mov     rax, [rdi+48h]
0x1800415a0  mov     [rbp-10h+var_38], rax
0x1800415a4  mov     eax, [rdi+20h]
0x1800415a7  mov     [rbp-10h+var_70], eax
0x1800415aa  mov     rax, [rdi+18h]
0x1800415ae  mov     [rbp-10h+var_30], rax
0x1800415b2  mov     eax, [rdi]
0x1800415b4  mov     [rbp-10h+var_6C], eax
0x1800415b7  mov     rax, [rdi+80h]
0x1800415be  mov     [rbp-10h+var_28], rax
0x1800415c2  mov     eax, [rdi+40h]
0x1800415c5  mov     [rbp-10h+var_68], eax
0x1800415c8  mov     rax, [rdi+38h]
0x1800415cc  mov     [rbp-10h+var_20], rax
0x1800415d0  mov     eax, [rdi+8]
0x1800415d3  mov     [rbp-10h+var_64], eax
0x1800415d6  lea     rax, [rbp-10h+arg_0]
0x1800415da  mov     [rsp+120h+var_80], rax
0x1800415e2  lea     rax, [rbp-10h+var_58]
0x1800415e6  mov     [rsp+120h+var_88], rax
0x1800415ee  lea     rax, [rbp-10h+var_50]
0x1800415f2  mov     [rsp+120h+var_90], rax
0x1800415fa  lea     rax, [rbp-10h+arg_10]
0x1800415fe  mov     [rsp+120h+var_98], rax
0x180041606  lea     rax, [rbp-10h+var_48]
0x18004160a  mov     [rsp+120h+var_A0], rax
0x180041612  lea     rax, [rbp-10h+var_40]
0x180041616  mov     [rsp+120h+var_A8], rax
0x18004161b  lea     rax, [rbp-10h+arg_18]
0x18004161f  mov     [rsp+120h+var_B0], rax
0x180041624  lea     rax, [rbp-10h+var_38]
0x180041628  mov     [rsp+120h+var_B8], rax
0x18004162d  lea     rax, [rbp-10h+var_70]
0x180041631  mov     [rsp+120h+var_C0], rax
0x180041636  lea     rax, [rbp-10h+var_30]
0x18004163a  mov     [rsp+120h+var_C8], rax
0x18004163f  lea     rax, [rbp-10h+var_6C]
0x180041643  mov     [rsp+120h+var_D0], rax
0x180041648  lea     rax, [rbp-10h+var_28]
0x18004164c  mov     [rsp+120h+var_D8], rax
0x180041651  lea     rax, [rbp-10h+var_68]
0x180041655  mov     [rsp+120h+var_E0], rax
0x18004165a  lea     rax, [rbp-10h+var_20]
0x18004165e  mov     [rsp+120h+var_E8], rax
0x180041663  lea     rax, [rbp-10h+var_64]
0x180041667  mov     [rsp+120h+var_F0], rax
0x18004166c  lea     rax, [rbp-10h+var_18]
0x180041670  mov     [rsp+120h+var_F8], rax
0x180041675  lea     rax, [rbp-10h+var_60]
0x180041679  mov     [rsp+120h+var_100], rax
0x18004167e  mov     [rbp-10h+arg_0], esi
0x180041681  mov     [rbp-10h+var_18], 1000000h
0x180041689  mov     [rbp-10h+var_60], 3000000h
0x180041691  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@454564564@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x180041696  jmp     loc_180041726
0x18004169b  mov     rcx, rbx
0x18004169e  call    ?zInternalStop@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x1800416a3  call    ?Instance@LUATelemetry@@KAPEAV1@XZ; LUATelemetry::Instance(void)
0x1800416a8  mov     rdi, [rax+8]
0x1800416ac  cmp     dword ptr [rdi], 5
0x1800416af  jbe     short loc_180041726
0x1800416b1  mov     rdx, 400000000000h
0x1800416bb  mov     rcx, rdi
0x1800416be  call    _tlgKeywordOn
0x1800416c3  test    al, al
0x1800416c5  jz      short loc_180041726
0x1800416c7  mov     [rbp-10h+arg_0], esi
0x1800416ca  call    cs:__imp_GetCurrentThreadId
0x1800416d1  nop     dword ptr [rax+rax+00h]
0x1800416d6  mov     r8, [rbx+110h]
0x1800416dd  lea     rdx, unk_180054DA3
0x1800416e4  mov     [rbp-10h+arg_10], eax
0x1800416e7  mov     rcx, rdi
0x1800416ea  mov     eax, [r8+48h]
0x1800416ee  add     r8, 8
0x1800416f2  mov     [rbp-10h+arg_18], eax
0x1800416f5  lea     rax, [rbp-10h+arg_0]
0x1800416f9  mov     [rsp+120h+var_E8], rax
0x1800416fe  lea     rax, [rbp-10h+arg_10]
0x180041702  mov     [rsp+120h+var_F0], rax
0x180041707  lea     rax, [rbp-10h+arg_18]
0x18004170b  mov     [rsp+120h+var_F8], rax
0x180041710  lea     rax, [rbp-10h+var_60]
0x180041714  mov     [rsp+120h+var_100], rax
0x180041719  mov     [rbp-10h+var_60], 3000000h
0x180041721  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@44@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180041726  mov     rcx, rbx
0x180041729  mov     rbx, [rsp+120h+arg_8]
0x180041731  add     rsp, 110h
0x180041738  pop     rdi
0x180041739  pop     rsi
0x18004173a  pop     rbp
0x18004173b  jmp     ?IgnoreCurrentThread@?$ActivityBase@VLUATelemetry@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
