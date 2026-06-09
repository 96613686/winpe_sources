# LUATelemetry::RegistrySyncActivity::Stop(int)

- ea: `0x18003f3dc`
- end: `0x18003f630`
- name: `?Stop@RegistrySyncActivity@LUATelemetry@@QEAAXH@Z`
- size: `596`
- prototype: `void __fastcall(LUATelemetry::RegistrySyncActivity *__hidden this, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callers

- `0x18003eb60`

## callees

- `0x180003ddc`
- `0x1800040a4`
- `0x18000cb30`
- `0x180018ac0`
- `0x180020fe0`
- `0x180021008`
- `0x18003f3dc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003f5ba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003f5ba`

## pseudocode

```c
void __fastcall LUATelemetry::RegistrySyncActivity::Stop(LUATelemetry::RegistrySyncActivity *this, int a2)
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
        (unsigned int)&unk_180051C8D,
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
        (unsigned int)&unk_180051A27,
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
0x18003f3dc  mov     [rsp-8+arg_8], rbx
0x18003f3e1  push    rbp
0x18003f3e2  push    rsi
0x18003f3e3  push    rdi
0x18003f3e4  lea     rbp, [rsp+20h]
0x18003f3e9  sub     rsp, 110h
0x18003f3f0  mov     rax, [rcx+110h]
0x18003f3f7  mov     rbx, rcx
0x18003f3fa  mov     esi, edx
0x18003f3fc  mov     ecx, [rax+48h]
0x18003f3ff  test    ecx, ecx
0x18003f401  jns     loc_18003F58B
0x18003f407  cmp     ecx, [rax+58h]
0x18003f40a  jnz     loc_18003F58B
0x18003f410  lea     rdi, [rax+50h]
0x18003f414  test    rdi, rdi
0x18003f417  jz      loc_18003F58B
0x18003f41d  mov     rcx, rbx
0x18003f420  call    ?zInternalStop@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18003f425  call    ?Instance@LUATelemetry@@KAPEAV1@XZ; LUATelemetry::Instance(void)
0x18003f42a  mov     rcx, [rax+8]
0x18003f42e  cmp     dword ptr [rcx], 5
0x18003f431  jbe     loc_18003F616
0x18003f437  mov     rdx, 400000000000h
0x18003f441  call    _tlgKeywordOn
0x18003f446  test    al, al
0x18003f448  jz      loc_18003F616
0x18003f44e  mov     rax, [rdi+78h]
0x18003f452  lea     rdx, unk_180051A27
0x18003f459  mov     r8, [rbx+110h]
0x18003f460  mov     [rbp-10h+var_58], rax
0x18003f464  add     r8, 8
0x18003f468  mov     rax, [rdi+70h]
0x18003f46c  mov     [rbp-10h+var_50], rax
0x18003f470  mov     eax, [rdi+68h]
0x18003f473  mov     [rbp-10h+arg_10], eax
0x18003f476  mov     rax, [rdi+60h]
0x18003f47a  mov     [rbp-10h+var_48], rax
0x18003f47e  mov     rax, [rdi+58h]
0x18003f482  mov     [rbp-10h+var_40], rax
0x18003f486  mov     eax, [rdi+50h]
0x18003f489  mov     [rbp-10h+arg_18], eax
0x18003f48c  mov     rax, [rdi+48h]
0x18003f490  mov     [rbp-10h+var_38], rax
0x18003f494  mov     eax, [rdi+20h]
0x18003f497  mov     [rbp-10h+var_70], eax
0x18003f49a  mov     rax, [rdi+18h]
0x18003f49e  mov     [rbp-10h+var_30], rax
0x18003f4a2  mov     eax, [rdi]
0x18003f4a4  mov     [rbp-10h+var_6C], eax
0x18003f4a7  mov     rax, [rdi+80h]
0x18003f4ae  mov     [rbp-10h+var_28], rax
0x18003f4b2  mov     eax, [rdi+40h]
0x18003f4b5  mov     [rbp-10h+var_68], eax
0x18003f4b8  mov     rax, [rdi+38h]
0x18003f4bc  mov     [rbp-10h+var_20], rax
0x18003f4c0  mov     eax, [rdi+8]
0x18003f4c3  mov     [rbp-10h+var_64], eax
0x18003f4c6  lea     rax, [rbp-10h+arg_0]
0x18003f4ca  mov     [rsp+120h+var_80], rax
0x18003f4d2  lea     rax, [rbp-10h+var_58]
0x18003f4d6  mov     [rsp+120h+var_88], rax
0x18003f4de  lea     rax, [rbp-10h+var_50]
0x18003f4e2  mov     [rsp+120h+var_90], rax
0x18003f4ea  lea     rax, [rbp-10h+arg_10]
0x18003f4ee  mov     [rsp+120h+var_98], rax
0x18003f4f6  lea     rax, [rbp-10h+var_48]
0x18003f4fa  mov     [rsp+120h+var_A0], rax
0x18003f502  lea     rax, [rbp-10h+var_40]
0x18003f506  mov     [rsp+120h+var_A8], rax
0x18003f50b  lea     rax, [rbp-10h+arg_18]
0x18003f50f  mov     [rsp+120h+var_B0], rax
0x18003f514  lea     rax, [rbp-10h+var_38]
0x18003f518  mov     [rsp+120h+var_B8], rax
0x18003f51d  lea     rax, [rbp-10h+var_70]
0x18003f521  mov     [rsp+120h+var_C0], rax
0x18003f526  lea     rax, [rbp-10h+var_30]
0x18003f52a  mov     [rsp+120h+var_C8], rax
0x18003f52f  lea     rax, [rbp-10h+var_6C]
0x18003f533  mov     [rsp+120h+var_D0], rax
0x18003f538  lea     rax, [rbp-10h+var_28]
0x18003f53c  mov     [rsp+120h+var_D8], rax
0x18003f541  lea     rax, [rbp-10h+var_68]
0x18003f545  mov     [rsp+120h+var_E0], rax
0x18003f54a  lea     rax, [rbp-10h+var_20]
0x18003f54e  mov     [rsp+120h+var_E8], rax
0x18003f553  lea     rax, [rbp-10h+var_64]
0x18003f557  mov     [rsp+120h+var_F0], rax
0x18003f55c  lea     rax, [rbp-10h+var_18]
0x18003f560  mov     [rsp+120h+var_F8], rax
0x18003f565  lea     rax, [rbp-10h+var_60]
0x18003f569  mov     [rsp+120h+var_100], rax
0x18003f56e  mov     [rbp-10h+arg_0], esi
0x18003f571  mov     [rbp-10h+var_18], 1000000h
0x18003f579  mov     [rbp-10h+var_60], 3000000h
0x18003f581  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@454564564@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18003f586  jmp     loc_18003F616
0x18003f58b  mov     rcx, rbx
0x18003f58e  call    ?zInternalStop@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18003f593  call    ?Instance@LUATelemetry@@KAPEAV1@XZ; LUATelemetry::Instance(void)
0x18003f598  mov     rdi, [rax+8]
0x18003f59c  cmp     dword ptr [rdi], 5
0x18003f59f  jbe     short loc_18003F616
0x18003f5a1  mov     rdx, 400000000000h
0x18003f5ab  mov     rcx, rdi
0x18003f5ae  call    _tlgKeywordOn
0x18003f5b3  test    al, al
0x18003f5b5  jz      short loc_18003F616
0x18003f5b7  mov     [rbp-10h+arg_0], esi
0x18003f5ba  call    cs:__imp_GetCurrentThreadId
0x18003f5c1  nop     dword ptr [rax+rax+00h]
0x18003f5c6  mov     r8, [rbx+110h]
0x18003f5cd  lea     rdx, unk_180051C8D
0x18003f5d4  mov     [rbp-10h+arg_10], eax
0x18003f5d7  mov     rcx, rdi
0x18003f5da  mov     eax, [r8+48h]
0x18003f5de  add     r8, 8
0x18003f5e2  mov     [rbp-10h+arg_18], eax
0x18003f5e5  lea     rax, [rbp-10h+arg_0]
0x18003f5e9  mov     [rsp+120h+var_E8], rax
0x18003f5ee  lea     rax, [rbp-10h+arg_10]
0x18003f5f2  mov     [rsp+120h+var_F0], rax
0x18003f5f7  lea     rax, [rbp-10h+arg_18]
0x18003f5fb  mov     [rsp+120h+var_F8], rax
0x18003f600  lea     rax, [rbp-10h+var_60]
0x18003f604  mov     [rsp+120h+var_100], rax
0x18003f609  mov     [rbp-10h+var_60], 3000000h
0x18003f611  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@44@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18003f616  mov     rcx, rbx
0x18003f619  mov     rbx, [rsp+120h+arg_8]
0x18003f621  add     rsp, 110h
0x18003f628  pop     rdi
0x18003f629  pop     rsi
0x18003f62a  pop     rbp
0x18003f62b  jmp     ?IgnoreCurrentThread@?$ActivityBase@VLUATelemetry@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
