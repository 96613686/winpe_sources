# AccountManagerUserModelTelemetry::PolicyDrivenAccountDelete::StopActivity(void)

- ea: `0x180018e40`
- end: `0x180019067`
- name: `?StopActivity@PolicyDrivenAccountDelete@AccountManagerUserModelTelemetry@@MEAAXXZ`
- size: `551`
- prototype: `void __fastcall(AccountManagerUserModelTelemetry::PolicyDrivenAccountDelete *__hidden this)`
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
- `0x180018e40`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019005`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019005`

## pseudocode

```c
void __fastcall AccountManagerUserModelTelemetry::PolicyDrivenAccountDelete::StopActivity(
        AccountManagerUserModelTelemetry::PolicyDrivenAccountDelete *this)
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
        (__int64)byte_18002D683,
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
        (__int64)&byte_18002CE1F,
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
0x180018e40  push    rbp
0x180018e42  push    rbx
0x180018e43  push    rdi
0x180018e44  lea     rbp, [rsp-47h]
0x180018e49  sub     rsp, 100h
0x180018e50  mov     rdi, [rcx+110h]
0x180018e57  mov     rbx, rcx
0x180018e5a  mov     eax, [rdi+48h]
0x180018e5d  test    eax, eax
0x180018e5f  jns     loc_180018FDB
0x180018e65  add     rdi, 50h ; 'P'
0x180018e69  cmp     eax, [rdi+8]
0x180018e6c  jnz     loc_180018FDB
0x180018e72  test    rdi, rdi
0x180018e75  jz      loc_180018FDB
0x180018e7b  call    ?zInternalStop@?$ActivityBase@VSharedPCAccountManagerLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180018e80  call    ?Provider@AccountManagerUserModelTelemetry@@SAPEBU_tlgProvider_t@@XZ; AccountManagerUserModelTelemetry::Provider(void)
0x180018e85  mov     r9, rax
0x180018e88  mov     ecx, [rax]
0x180018e8a  cmp     ecx, 5
0x180018e8d  jbe     loc_180019055
0x180018e93  mov     rdx, 200000000000h
0x180018e9d  mov     rcx, rax
0x180018ea0  call    _tlgKeywordOn
0x180018ea5  test    al, al
0x180018ea7  jz      loc_180019055
0x180018ead  mov     rax, [rdi+70h]
0x180018eb1  lea     rdx, byte_18002D683
0x180018eb8  mov     rcx, [rdi+78h]
0x180018ebc  mov     r8, [rbx+110h]
0x180018ec3  mov     [rbp+57h+var_60], rax
0x180018ec7  add     r8, 8
0x180018ecb  mov     eax, [rdi+68h]
0x180018ece  mov     [rbp+57h+arg_0], eax
0x180018ed1  mov     rax, [rdi+60h]
0x180018ed5  mov     [rbp+57h+var_58], rax
0x180018ed9  mov     rax, [rdi+58h]
0x180018edd  mov     [rbp+57h+var_50], rax
0x180018ee1  mov     eax, [rdi+50h]
0x180018ee4  mov     [rbp+57h+arg_8], eax
0x180018ee7  mov     rax, [rdi+48h]
0x180018eeb  mov     [rbp+57h+var_48], rax
0x180018eef  mov     eax, [rdi+20h]
0x180018ef2  mov     dword ptr [rbp+57h+arg_10], eax
0x180018ef5  mov     rax, [rdi+18h]
0x180018ef9  mov     [rbp+57h+var_40], rax
0x180018efd  mov     eax, [rdi]
0x180018eff  mov     [rbp+57h+arg_18], eax
0x180018f02  mov     rax, [rdi+80h]
0x180018f09  mov     [rbp+57h+var_38], rax
0x180018f0d  mov     eax, [rdi+40h]
0x180018f10  mov     [rbp+57h+var_70], eax
0x180018f13  mov     rax, [rdi+38h]
0x180018f17  mov     [rbp+57h+var_30], rax
0x180018f1b  mov     eax, [rdi+8]
0x180018f1e  mov     [rbp+57h+var_6C], eax
0x180018f21  lea     rax, [rbp+57h+var_68]
0x180018f25  mov     [rsp+110h+var_78], rax
0x180018f2d  lea     rax, [rbp+57h+var_60]
0x180018f31  mov     [rsp+110h+var_80], rax
0x180018f39  lea     rax, [rbp+57h+arg_0]
0x180018f3d  mov     [rsp+110h+var_88], rax
0x180018f45  lea     rax, [rbp+57h+var_58]
0x180018f49  mov     [rsp+110h+var_90], rax
0x180018f51  lea     rax, [rbp+57h+var_50]
0x180018f55  mov     [rsp+110h+var_98], rax
0x180018f5a  lea     rax, [rbp+57h+arg_8]
0x180018f5e  mov     [rsp+110h+var_A0], rax
0x180018f63  lea     rax, [rbp+57h+var_48]
0x180018f67  mov     [rsp+110h+var_A8], rax
0x180018f6c  lea     rax, [rbp+57h+arg_10]
0x180018f70  mov     [rsp+110h+var_B0], rax
0x180018f75  lea     rax, [rbp+57h+var_40]
0x180018f79  mov     [rsp+110h+var_B8], rax
0x180018f7e  lea     rax, [rbp+57h+arg_18]
0x180018f82  mov     [rsp+110h+var_C0], rax
0x180018f87  lea     rax, [rbp+57h+var_38]
0x180018f8b  mov     [rsp+110h+var_C8], rax
0x180018f90  lea     rax, [rbp+57h+var_70]
0x180018f94  mov     [rsp+110h+var_D0], rax
0x180018f99  lea     rax, [rbp+57h+var_30]
0x180018f9d  mov     [rsp+110h+var_D8], rax
0x180018fa2  lea     rax, [rbp+57h+var_6C]
0x180018fa6  mov     [rsp+110h+var_E0], rax
0x180018fab  lea     rax, [rbp+57h+var_28]
0x180018faf  mov     [rsp+110h+var_E8], rax
0x180018fb4  lea     rax, [rbp+57h+var_20]
0x180018fb8  mov     [rbp+57h+var_68], rcx
0x180018fbc  mov     rcx, r9
0x180018fbf  mov     [rsp+110h+var_F0], rax
0x180018fc4  mov     [rbp+57h+var_28], 1000000h
0x180018fcc  mov     [rbp+57h+var_20], 0
0x180018fd4  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180018fd9  jmp     short loc_180019055
0x180018fdb  call    ?zInternalStop@?$ActivityBase@VSharedPCAccountManagerLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180018fe0  call    ?Provider@AccountManagerUserModelTelemetry@@SAPEBU_tlgProvider_t@@XZ; AccountManagerUserModelTelemetry::Provider(void)
0x180018fe5  mov     rdi, rax
0x180018fe8  mov     ecx, [rax]
0x180018fea  cmp     ecx, 5
0x180018fed  jbe     short loc_180019055
0x180018fef  mov     rdx, 200000000000h
0x180018ff9  mov     rcx, rax
0x180018ffc  call    _tlgKeywordOn
0x180019001  test    al, al
0x180019003  jz      short loc_180019055
0x180019005  call    cs:__imp_GetCurrentThreadId
0x18001900b  mov     r8, [rbx+110h]
0x180019012  lea     rdx, byte_18002CE1F
0x180019019  mov     [rbp+57h+arg_0], eax
0x18001901c  xor     r9d, r9d
0x18001901f  mov     rcx, rdi
0x180019022  mov     eax, [r8+48h]
0x180019026  add     r8, 8
0x18001902a  mov     [rbp+57h+arg_8], eax
0x18001902d  lea     rax, [rbp+57h+arg_0]
0x180019031  mov     [rsp+110h+var_E0], rax
0x180019036  lea     rax, [rbp+57h+arg_8]
0x18001903a  mov     [rsp+110h+var_E8], rax
0x18001903f  lea     rax, [rbp+57h+arg_10]
0x180019043  mov     [rsp+110h+var_F0], rax
0x180019048  mov     [rbp+57h+arg_10], 0
0x180019050  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180019055  mov     rcx, rbx
0x180019058  add     rsp, 100h
0x18001905f  pop     rdi
0x180019060  pop     rbx
0x180019061  pop     rbp
0x180019062  jmp     ?IgnoreCurrentThread@?$ActivityBase@VSharedPCAccountManagerLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
