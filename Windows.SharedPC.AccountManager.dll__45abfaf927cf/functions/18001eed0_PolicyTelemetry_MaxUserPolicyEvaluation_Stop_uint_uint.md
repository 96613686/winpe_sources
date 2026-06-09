# PolicyTelemetry::MaxUserPolicyEvaluation::Stop(uint,uint)

- ea: `0x18001eed0`
- end: `0x18001f14a`
- name: `?Stop@MaxUserPolicyEvaluation@PolicyTelemetry@@QEAAXII@Z`
- size: `634`
- prototype: `void __fastcall(PolicyTelemetry::MaxUserPolicyEvaluation *__hidden this, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18001eca0`

## callees

- `0x180001b0c`
- `0x180002414`
- `0x1800026ec`
- `0x18000db78`
- `0x18000e00c`
- `0x18000ed9c`
- `0x18001eed0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001f0cb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001f0cb`

## pseudocode

```c
void __fastcall PolicyTelemetry::MaxUserPolicyEvaluation::Stop(
        PolicyTelemetry::MaxUserPolicyEvaluation *this,
        int a2,
        int a3)
{
  __int64 v3; // rdi
  int v7; // eax
  int *v8; // rdi
  const struct _tlgProvider_t *v9; // rax
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // r9
  __int64 v13; // r8
  const struct _tlgProvider_t *v14; // rax
  __int64 v15; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v17; // r8
  __int64 v18; // r9
  int v19; // [rsp+B0h] [rbp-80h] BYREF
  DWORD v20; // [rsp+B4h] [rbp-7Ch] BYREF
  int v21; // [rsp+B8h] [rbp-78h] BYREF
  int v22; // [rsp+BCh] [rbp-74h] BYREF
  int v23; // [rsp+C0h] [rbp-70h] BYREF
  int v24; // [rsp+C4h] [rbp-6Ch] BYREF
  __int64 v25; // [rsp+C8h] [rbp-68h] BYREF
  const WCHAR *v26; // [rsp+D0h] [rbp-60h] BYREF
  const unsigned __int16 *v27; // [rsp+D8h] [rbp-58h] BYREF
  const WCHAR *v28; // [rsp+E0h] [rbp-50h] BYREF
  const unsigned __int16 *v29; // [rsp+E8h] [rbp-48h] BYREF
  const unsigned __int16 *v30; // [rsp+F0h] [rbp-40h] BYREF
  const WCHAR *v31; // [rsp+F8h] [rbp-38h] BYREF
  const unsigned __int16 *v32; // [rsp+100h] [rbp-30h] BYREF
  const unsigned __int16 *v33; // [rsp+108h] [rbp-28h] BYREF
  __int64 v34; // [rsp+110h] [rbp-20h] BYREF
  int v35; // [rsp+140h] [rbp+10h] BYREF
  int v36; // [rsp+158h] [rbp+28h] BYREF

  v3 = *((_QWORD *)this + 34);
  v7 = *(_DWORD *)(v3 + 72);
  if ( v7 < 0 && (v8 = (int *)(v3 + 80), v7 == v8[2]) && v8 )
  {
    wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v9 = SharedPCAccountManagerLogging::Provider();
    v12 = (__int64)v9;
    if ( *(_DWORD *)v9 > 5u && (unsigned __int8)tlgKeywordOn(v9, 0x400000000000LL, v11, v9) )
    {
      v26 = (const WCHAR *)*((_QWORD *)v8 + 15);
      v27 = (const unsigned __int16 *)*((_QWORD *)v8 + 14);
      v13 = *((_QWORD *)this + 34);
      v21 = v8[26];
      v28 = (const WCHAR *)*((_QWORD *)v8 + 12);
      v29 = (const unsigned __int16 *)*((_QWORD *)v8 + 11);
      v22 = v8[20];
      v30 = (const unsigned __int16 *)*((_QWORD *)v8 + 9);
      v23 = v8[8];
      v31 = (const WCHAR *)*((_QWORD *)v8 + 3);
      v24 = *v8;
      v32 = (const unsigned __int16 *)*((_QWORD *)v8 + 16);
      v19 = v8[16];
      v33 = (const unsigned __int16 *)*((_QWORD *)v8 + 7);
      v20 = v8[2];
      v34 = 0x1000000;
      v25 = 0x1000000;
      v35 = a3;
      v36 = a2;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v12,
        (__int64)&unk_18002E540,
        v13 + 8,
        v12,
        (__int64)&v25,
        (__int64)&v34,
        (__int64)&v20,
        &v33,
        (__int64)&v19,
        &v32,
        (__int64)&v24,
        &v31,
        (__int64)&v23,
        &v30,
        (__int64)&v22,
        &v29,
        &v28,
        (__int64)&v21,
        &v27,
        &v26,
        (__int64)&v36,
        (__int64)&v35);
    }
  }
  else
  {
    wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v14 = SharedPCAccountManagerLogging::Provider();
    v15 = (__int64)v14;
    if ( *(_DWORD *)v14 > 5u && (unsigned __int8)tlgKeywordOn(v14, 0x400000000000LL, v11, v12) )
    {
      v35 = a3;
      v36 = a2;
      CurrentThreadId = GetCurrentThreadId();
      v17 = *((_QWORD *)this + 34);
      v20 = CurrentThreadId;
      v19 = *(_DWORD *)(v17 + 72);
      v25 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v15,
        (__int64)&byte_18002E6E7,
        v17 + 8,
        v18,
        (__int64)&v25,
        (__int64)&v19,
        (__int64)&v20,
        (__int64)&v36,
        (__int64)&v35);
    }
  }
  wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
    this,
    v10,
    v11,
    v12);
}

```

## disassembly

```asm
0x18001eed0  mov     [rsp-8+arg_8], rbx
0x18001eed5  mov     [rsp-8+arg_10], rsi
0x18001eeda  push    rbp
0x18001eedb  push    rdi
0x18001eedc  push    r14
0x18001eede  lea     rbp, [rsp+10h]
0x18001eee3  sub     rsp, 120h
0x18001eeea  mov     rdi, [rcx+110h]
0x18001eef1  mov     esi, r8d
0x18001eef4  mov     r14d, edx
0x18001eef7  mov     rbx, rcx
0x18001eefa  mov     eax, [rdi+48h]
0x18001eefd  test    eax, eax
0x18001eeff  jns     loc_18001F09A
0x18001ef05  add     rdi, 50h ; 'P'
0x18001ef09  cmp     eax, [rdi+8]
0x18001ef0c  jnz     loc_18001F09A
0x18001ef12  test    rdi, rdi
0x18001ef15  jz      loc_18001F09A
0x18001ef1b  call    ?zInternalStop@?$ActivityBase@VSharedPCAccountManagerLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18001ef20  call    ?Provider@SharedPCAccountManagerLogging@@SAPEBU_tlgProvider_t@@XZ; SharedPCAccountManagerLogging::Provider(void)
0x18001ef25  mov     r9, rax
0x18001ef28  mov     ecx, [rax]
0x18001ef2a  cmp     ecx, 5
0x18001ef2d  jbe     loc_18001F12B
0x18001ef33  mov     rdx, 400000000000h
0x18001ef3d  mov     rcx, rax
0x18001ef40  call    _tlgKeywordOn
0x18001ef45  test    al, al
0x18001ef47  jz      loc_18001F12B
0x18001ef4d  mov     rax, [rdi+78h]
0x18001ef51  lea     rdx, unk_18002E540
0x18001ef58  mov     [rbp+var_60], rax
0x18001ef5c  mov     rcx, r9
0x18001ef5f  mov     rax, [rdi+70h]
0x18001ef63  mov     [rbp+var_58], rax
0x18001ef67  mov     eax, [rdi+68h]
0x18001ef6a  mov     r8, [rbx+110h]
0x18001ef71  mov     [rbp+var_78], eax
0x18001ef74  add     r8, 8
0x18001ef78  mov     rax, [rdi+60h]
0x18001ef7c  mov     [rbp+var_50], rax
0x18001ef80  mov     rax, [rdi+58h]
0x18001ef84  mov     [rbp+var_48], rax
0x18001ef88  mov     eax, [rdi+50h]
0x18001ef8b  mov     [rbp+var_74], eax
0x18001ef8e  mov     rax, [rdi+48h]
0x18001ef92  mov     [rbp+var_40], rax
0x18001ef96  mov     eax, [rdi+20h]
0x18001ef99  mov     [rbp+var_70], eax
0x18001ef9c  mov     rax, [rdi+18h]
0x18001efa0  mov     [rbp+var_38], rax
0x18001efa4  mov     eax, [rdi]
0x18001efa6  mov     [rbp+var_6C], eax
0x18001efa9  mov     rax, [rdi+80h]
0x18001efb0  mov     [rbp+var_30], rax
0x18001efb4  mov     eax, [rdi+40h]
0x18001efb7  mov     [rbp+var_80], eax
0x18001efba  mov     rax, [rdi+38h]
0x18001efbe  mov     [rbp+var_28], rax
0x18001efc2  mov     eax, [rdi+8]
0x18001efc5  mov     [rbp+var_7C], eax
0x18001efc8  mov     eax, 1000000h
0x18001efcd  mov     [rbp+var_20], rax
0x18001efd1  mov     [rbp+var_68], rax
0x18001efd5  lea     rax, [rbp+arg_0]
0x18001efd9  mov     [rsp+130h+var_88], rax
0x18001efe1  lea     rax, [rbp+arg_18]
0x18001efe5  mov     [rsp+130h+var_90], rax
0x18001efed  lea     rax, [rbp+var_60]
0x18001eff1  mov     [rsp+130h+var_98], rax
0x18001eff9  lea     rax, [rbp+var_58]
0x18001effd  mov     [rsp+130h+var_A0], rax
0x18001f005  lea     rax, [rbp+var_78]
0x18001f009  mov     [rsp+130h+var_A8], rax
0x18001f011  lea     rax, [rbp+var_50]
0x18001f015  mov     [rsp+130h+var_B0], rax
0x18001f01d  lea     rax, [rbp+var_48]
0x18001f021  mov     [rsp+130h+var_B8], rax
0x18001f026  lea     rax, [rbp+var_74]
0x18001f02a  mov     [rsp+130h+var_C0], rax
0x18001f02f  lea     rax, [rbp+var_40]
0x18001f033  mov     [rsp+130h+var_C8], rax
0x18001f038  lea     rax, [rbp+var_70]
0x18001f03c  mov     [rsp+130h+var_D0], rax
0x18001f041  lea     rax, [rbp+var_38]
0x18001f045  mov     [rsp+130h+var_D8], rax
0x18001f04a  lea     rax, [rbp+var_6C]
0x18001f04e  mov     [rsp+130h+var_E0], rax
0x18001f053  lea     rax, [rbp+var_30]
0x18001f057  mov     [rsp+130h+var_E8], rax
0x18001f05c  lea     rax, [rbp+var_80]
0x18001f060  mov     [rsp+130h+var_F0], rax
0x18001f065  lea     rax, [rbp+var_28]
0x18001f069  mov     [rsp+130h+var_F8], rax
0x18001f06e  lea     rax, [rbp+var_7C]
0x18001f072  mov     [rsp+130h+var_100], rax
0x18001f077  lea     rax, [rbp+var_20]
0x18001f07b  mov     [rsp+130h+var_108], rax
0x18001f080  lea     rax, [rbp+var_68]
0x18001f084  mov     [rsp+130h+var_110], rax
0x18001f089  mov     [rbp+arg_0], esi
0x18001f08c  mov     [rbp+arg_18], r14d
0x18001f090  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@4545645644@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001f095  jmp     loc_18001F12B
0x18001f09a  call    ?zInternalStop@?$ActivityBase@VSharedPCAccountManagerLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18001f09f  call    ?Provider@SharedPCAccountManagerLogging@@SAPEBU_tlgProvider_t@@XZ; SharedPCAccountManagerLogging::Provider(void)
0x18001f0a4  mov     rdi, rax
0x18001f0a7  mov     ecx, [rax]
0x18001f0a9  cmp     ecx, 5
0x18001f0ac  jbe     short loc_18001F12B
0x18001f0ae  mov     rdx, 400000000000h
0x18001f0b8  mov     rcx, rax
0x18001f0bb  call    _tlgKeywordOn
0x18001f0c0  test    al, al
0x18001f0c2  jz      short loc_18001F12B
0x18001f0c4  mov     [rbp+arg_0], esi
0x18001f0c7  mov     [rbp+arg_18], r14d
0x18001f0cb  call    cs:__imp_GetCurrentThreadId
0x18001f0d1  mov     r8, [rbx+110h]
0x18001f0d8  lea     rdx, byte_18002E6E7
0x18001f0df  mov     [rbp+var_7C], eax
0x18001f0e2  mov     rcx, rdi
0x18001f0e5  mov     eax, [r8+48h]
0x18001f0e9  add     r8, 8
0x18001f0ed  mov     [rbp+var_80], eax
0x18001f0f0  mov     eax, 1000000h
0x18001f0f5  mov     [rbp+var_68], rax
0x18001f0f9  lea     rax, [rbp+arg_0]
0x18001f0fd  mov     [rsp+130h+var_F0], rax
0x18001f102  lea     rax, [rbp+arg_18]
0x18001f106  mov     [rsp+130h+var_F8], rax
0x18001f10b  lea     rax, [rbp+var_7C]
0x18001f10f  mov     [rsp+130h+var_100], rax
0x18001f114  lea     rax, [rbp+var_80]
0x18001f118  mov     [rsp+130h+var_108], rax
0x18001f11d  lea     rax, [rbp+var_68]
0x18001f121  mov     [rsp+130h+var_110], rax
0x18001f126  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@444@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001f12b  mov     rcx, rbx
0x18001f12e  lea     r11, [rsp+130h+var_10]
0x18001f136  mov     rbx, [r11+28h]
0x18001f13a  mov     rsi, [r11+30h]
0x18001f13e  mov     rsp, r11
0x18001f141  pop     r14
0x18001f143  pop     rdi
0x18001f144  pop     rbp
0x18001f145  jmp     ?IgnoreCurrentThread@?$ActivityBase@VSharedPCAccountManagerLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
