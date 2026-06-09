# AccountManagerUserModelTelemetry::PolicyDrivenUserDelete::StopActivity(void)

- ea: `0x1800192a0`
- end: `0x1800194c7`
- name: `?StopActivity@PolicyDrivenUserDelete@AccountManagerUserModelTelemetry@@MEAAXXZ`
- size: `551`
- prototype: `void __fastcall(AccountManagerUserModelTelemetry::PolicyDrivenUserDelete *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config`

## callees

- `0x180001010`
- `0x180001384`
- `0x180001b0c`
- `0x18000db78`
- `0x18000ed9c`
- `0x18001790c`
- `0x1800192a0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019465`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019465`

## pseudocode

```c
void __fastcall AccountManagerUserModelTelemetry::PolicyDrivenUserDelete::StopActivity(
        AccountManagerUserModelTelemetry::PolicyDrivenUserDelete *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  const struct _tlgProvider_t *v5; // rax
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // r9
  const WCHAR *v9; // rcx
  __int64 v10; // r8
  const struct _tlgProvider_t *v11; // rax
  __int64 v12; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v14; // r8
  int v15; // [rsp+A0h] [rbp-19h] BYREF
  int v16; // [rsp+A4h] [rbp-15h] BYREF
  const WCHAR *v17; // [rsp+A8h] [rbp-11h] BYREF
  const unsigned __int16 *v18; // [rsp+B0h] [rbp-9h] BYREF
  const WCHAR *v19; // [rsp+B8h] [rbp-1h] BYREF
  const unsigned __int16 *v20; // [rsp+C0h] [rbp+7h] BYREF
  const unsigned __int16 *v21; // [rsp+C8h] [rbp+Fh] BYREF
  const WCHAR *v22; // [rsp+D0h] [rbp+17h] BYREF
  const unsigned __int16 *v23; // [rsp+D8h] [rbp+1Fh] BYREF
  const unsigned __int16 *v24; // [rsp+E0h] [rbp+27h] BYREF
  __int64 v25; // [rsp+E8h] [rbp+2Fh] BYREF
  _QWORD v26[4]; // [rsp+F0h] [rbp+37h] BYREF
  DWORD v27; // [rsp+120h] [rbp+67h] BYREF
  int v28; // [rsp+128h] [rbp+6Fh] BYREF
  __int64 v29; // [rsp+130h] [rbp+77h] BYREF
  int v30; // [rsp+138h] [rbp+7Fh] BYREF

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = (int *)(v1 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v5 = AccountManagerUserModelTelemetry::Provider();
    v8 = (__int64)v5;
    if ( *(_DWORD *)v5 > 5u && (unsigned __int8)tlgKeywordOn(v5, 0x200000000000LL, v7, v5) )
    {
      v9 = (const WCHAR *)*((_QWORD *)v4 + 15);
      v10 = *((_QWORD *)this + 34);
      v18 = (const unsigned __int16 *)*((_QWORD *)v4 + 14);
      v27 = v4[26];
      v19 = (const WCHAR *)*((_QWORD *)v4 + 12);
      v20 = (const unsigned __int16 *)*((_QWORD *)v4 + 11);
      v28 = v4[20];
      v21 = (const unsigned __int16 *)*((_QWORD *)v4 + 9);
      LODWORD(v29) = v4[8];
      v22 = (const WCHAR *)*((_QWORD *)v4 + 3);
      v30 = *v4;
      v23 = (const unsigned __int16 *)*((_QWORD *)v4 + 16);
      v15 = v4[16];
      v24 = (const unsigned __int16 *)*((_QWORD *)v4 + 7);
      v16 = v4[2];
      v17 = v9;
      v25 = 0x1000000;
      v26[0] = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        v8,
        (__int64)byte_18002D1B1,
        v10 + 8,
        v8,
        (__int64)v26,
        (__int64)&v25,
        (__int64)&v16,
        &v24,
        (__int64)&v15,
        &v23,
        (__int64)&v30,
        &v22,
        (__int64)&v29,
        &v21,
        (__int64)&v28,
        &v20,
        &v19,
        (__int64)&v27,
        &v18,
        &v17);
    }
  }
  else
  {
    wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v11 = AccountManagerUserModelTelemetry::Provider();
    v12 = (__int64)v11;
    if ( *(_DWORD *)v11 > 5u && (unsigned __int8)tlgKeywordOn(v11, 0x200000000000LL, v7, v8) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v14 = *((_QWORD *)this + 34);
      v27 = CurrentThreadId;
      v28 = *(_DWORD *)(v14 + 72);
      v29 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v12,
        (__int64)byte_18002CC2B,
        v14 + 8,
        0,
        (__int64)&v29,
        (__int64)&v28,
        (__int64)&v27);
    }
  }
  wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
    this,
    v6,
    v7,
    v8);
}

```

## disassembly

```asm
0x1800192a0  push    rbp
0x1800192a2  push    rbx
0x1800192a3  push    rdi
0x1800192a4  lea     rbp, [rsp-47h]
0x1800192a9  sub     rsp, 100h
0x1800192b0  mov     rdi, [rcx+110h]
0x1800192b7  mov     rbx, rcx
0x1800192ba  mov     eax, [rdi+48h]
0x1800192bd  test    eax, eax
0x1800192bf  jns     loc_18001943B
0x1800192c5  add     rdi, 50h ; 'P'
0x1800192c9  cmp     eax, [rdi+8]
0x1800192cc  jnz     loc_18001943B
0x1800192d2  test    rdi, rdi
0x1800192d5  jz      loc_18001943B
0x1800192db  call    ?zInternalStop@?$ActivityBase@VSharedPCAccountManagerLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x1800192e0  call    ?Provider@AccountManagerUserModelTelemetry@@SAPEBU_tlgProvider_t@@XZ; AccountManagerUserModelTelemetry::Provider(void)
0x1800192e5  mov     r9, rax
0x1800192e8  mov     ecx, [rax]
0x1800192ea  cmp     ecx, 5
0x1800192ed  jbe     loc_1800194B5
0x1800192f3  mov     rdx, 200000000000h
0x1800192fd  mov     rcx, rax
0x180019300  call    _tlgKeywordOn
0x180019305  test    al, al
0x180019307  jz      loc_1800194B5
0x18001930d  mov     rax, [rdi+70h]
0x180019311  lea     rdx, byte_18002D1B1
0x180019318  mov     rcx, [rdi+78h]
0x18001931c  mov     r8, [rbx+110h]
0x180019323  mov     [rbp+57h+var_60], rax
0x180019327  add     r8, 8
0x18001932b  mov     eax, [rdi+68h]
0x18001932e  mov     [rbp+57h+arg_0], eax
0x180019331  mov     rax, [rdi+60h]
0x180019335  mov     [rbp+57h+var_58], rax
0x180019339  mov     rax, [rdi+58h]
0x18001933d  mov     [rbp+57h+var_50], rax
0x180019341  mov     eax, [rdi+50h]
0x180019344  mov     [rbp+57h+arg_8], eax
0x180019347  mov     rax, [rdi+48h]
0x18001934b  mov     [rbp+57h+var_48], rax
0x18001934f  mov     eax, [rdi+20h]
0x180019352  mov     dword ptr [rbp+57h+arg_10], eax
0x180019355  mov     rax, [rdi+18h]
0x180019359  mov     [rbp+57h+var_40], rax
0x18001935d  mov     eax, [rdi]
0x18001935f  mov     [rbp+57h+arg_18], eax
0x180019362  mov     rax, [rdi+80h]
0x180019369  mov     [rbp+57h+var_38], rax
0x18001936d  mov     eax, [rdi+40h]
0x180019370  mov     [rbp+57h+var_70], eax
0x180019373  mov     rax, [rdi+38h]
0x180019377  mov     [rbp+57h+var_30], rax
0x18001937b  mov     eax, [rdi+8]
0x18001937e  mov     [rbp+57h+var_6C], eax
0x180019381  lea     rax, [rbp+57h+var_68]
0x180019385  mov     [rsp+110h+var_78], rax
0x18001938d  lea     rax, [rbp+57h+var_60]
0x180019391  mov     [rsp+110h+var_80], rax
0x180019399  lea     rax, [rbp+57h+arg_0]
0x18001939d  mov     [rsp+110h+var_88], rax
0x1800193a5  lea     rax, [rbp+57h+var_58]
0x1800193a9  mov     [rsp+110h+var_90], rax
0x1800193b1  lea     rax, [rbp+57h+var_50]
0x1800193b5  mov     [rsp+110h+var_98], rax
0x1800193ba  lea     rax, [rbp+57h+arg_8]
0x1800193be  mov     [rsp+110h+var_A0], rax
0x1800193c3  lea     rax, [rbp+57h+var_48]
0x1800193c7  mov     [rsp+110h+var_A8], rax
0x1800193cc  lea     rax, [rbp+57h+arg_10]
0x1800193d0  mov     [rsp+110h+var_B0], rax
0x1800193d5  lea     rax, [rbp+57h+var_40]
0x1800193d9  mov     [rsp+110h+var_B8], rax
0x1800193de  lea     rax, [rbp+57h+arg_18]
0x1800193e2  mov     [rsp+110h+var_C0], rax
0x1800193e7  lea     rax, [rbp+57h+var_38]
0x1800193eb  mov     [rsp+110h+var_C8], rax
0x1800193f0  lea     rax, [rbp+57h+var_70]
0x1800193f4  mov     [rsp+110h+var_D0], rax
0x1800193f9  lea     rax, [rbp+57h+var_30]
0x1800193fd  mov     [rsp+110h+var_D8], rax
0x180019402  lea     rax, [rbp+57h+var_6C]
0x180019406  mov     [rsp+110h+var_E0], rax
0x18001940b  lea     rax, [rbp+57h+var_28]
0x18001940f  mov     [rsp+110h+var_E8], rax
0x180019414  lea     rax, [rbp+57h+var_20]
0x180019418  mov     [rbp+57h+var_68], rcx
0x18001941c  mov     rcx, r9
0x18001941f  mov     [rsp+110h+var_F0], rax
0x180019424  mov     [rbp+57h+var_28], 1000000h
0x18001942c  mov     [rbp+57h+var_20], 0
0x180019434  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180019439  jmp     short loc_1800194B5
0x18001943b  call    ?zInternalStop@?$ActivityBase@VSharedPCAccountManagerLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180019440  call    ?Provider@AccountManagerUserModelTelemetry@@SAPEBU_tlgProvider_t@@XZ; AccountManagerUserModelTelemetry::Provider(void)
0x180019445  mov     rdi, rax
0x180019448  mov     ecx, [rax]
0x18001944a  cmp     ecx, 5
0x18001944d  jbe     short loc_1800194B5
0x18001944f  mov     rdx, 200000000000h
0x180019459  mov     rcx, rax
0x18001945c  call    _tlgKeywordOn
0x180019461  test    al, al
0x180019463  jz      short loc_1800194B5
0x180019465  call    cs:__imp_GetCurrentThreadId
0x18001946b  mov     r8, [rbx+110h]
0x180019472  lea     rdx, byte_18002CC2B
0x180019479  mov     [rbp+57h+arg_0], eax
0x18001947c  xor     r9d, r9d
0x18001947f  mov     rcx, rdi
0x180019482  mov     eax, [r8+48h]
0x180019486  add     r8, 8
0x18001948a  mov     [rbp+57h+arg_8], eax
0x18001948d  lea     rax, [rbp+57h+arg_0]
0x180019491  mov     [rsp+110h+var_E0], rax
0x180019496  lea     rax, [rbp+57h+arg_8]
0x18001949a  mov     [rsp+110h+var_E8], rax
0x18001949f  lea     rax, [rbp+57h+arg_10]
0x1800194a3  mov     [rsp+110h+var_F0], rax
0x1800194a8  mov     [rbp+57h+arg_10], 0
0x1800194b0  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800194b5  mov     rcx, rbx
0x1800194b8  add     rsp, 100h
0x1800194bf  pop     rdi
0x1800194c0  pop     rbx
0x1800194c1  pop     rbp
0x1800194c2  jmp     ?IgnoreCurrentThread@?$ActivityBase@VSharedPCAccountManagerLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
