# DirectXDatabaseUpdaterTelemetry::GetSettingsPayloadActivity::StopActivity(void)

- ea: `0x14000c2a0`
- end: `0x14000c4c2`
- name: `?StopActivity@GetSettingsPayloadActivity@DirectXDatabaseUpdaterTelemetry@@MEAAXXZ`
- size: `546`
- prototype: `void __fastcall(DirectXDatabaseUpdaterTelemetry::GetSettingsPayloadActivity *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, installer_update`

## callees

- `0x140001010`
- `0x1400018ec`
- `0x1400022ec`
- `0x1400082c0`
- `0x14000946c`
- `0x14000c2a0`
- `0x14000efa8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000c462`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000c462`

## pseudocode

```c
void __fastcall DirectXDatabaseUpdaterTelemetry::GetSettingsPayloadActivity::StopActivity(
        DirectXDatabaseUpdaterTelemetry::GetSettingsPayloadActivity *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  const struct _tlgProvider_t *v5; // rax
  __int64 v6; // rdx
  __int64 v7; // r8
  const struct _tlgProvider_t *v8; // r9
  __int64 v9; // rcx
  __int64 v10; // r8
  const struct _tlgProvider_t *v11; // rax
  int v12; // edi
  DWORD CurrentThreadId; // eax
  __int64 v14; // r8
  int v15; // r9d
  int v16; // [rsp+A0h] [rbp-19h] BYREF
  int v17; // [rsp+A4h] [rbp-15h] BYREF
  __int64 v18; // [rsp+A8h] [rbp-11h] BYREF
  __int64 v19; // [rsp+B0h] [rbp-9h] BYREF
  __int64 v20; // [rsp+B8h] [rbp-1h] BYREF
  __int64 v21; // [rsp+C0h] [rbp+7h] BYREF
  __int64 v22; // [rsp+C8h] [rbp+Fh] BYREF
  __int64 v23; // [rsp+D0h] [rbp+17h] BYREF
  __int64 v24; // [rsp+D8h] [rbp+1Fh] BYREF
  __int64 v25; // [rsp+E0h] [rbp+27h] BYREF
  __int64 v26; // [rsp+E8h] [rbp+2Fh] BYREF
  __int64 v27[4]; // [rsp+F0h] [rbp+37h] BYREF
  DWORD v28; // [rsp+120h] [rbp+67h] BYREF
  int v29; // [rsp+128h] [rbp+6Fh] BYREF
  __int64 v30; // [rsp+130h] [rbp+77h] BYREF
  int v31; // [rsp+138h] [rbp+7Fh] BYREF

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = (int *)(v1 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v5 = DirectXDatabaseUpdaterLogging::Provider();
    v8 = v5;
    if ( *(_DWORD *)v5 > 5u && (unsigned __int8)tlgKeywordOn(v5, 0x400000000000LL) )
    {
      v9 = *((_QWORD *)v4 + 15);
      v10 = *((_QWORD *)this + 34);
      v19 = *((_QWORD *)v4 + 14);
      v28 = v4[26];
      v20 = *((_QWORD *)v4 + 12);
      v21 = *((_QWORD *)v4 + 11);
      v29 = v4[20];
      v22 = *((_QWORD *)v4 + 9);
      LODWORD(v30) = v4[8];
      v23 = *((_QWORD *)v4 + 3);
      v31 = *v4;
      v24 = *((_QWORD *)v4 + 16);
      v16 = v4[16];
      v25 = *((_QWORD *)v4 + 7);
      v17 = v4[2];
      v26 = 0x1000000;
      v27[0] = 0x1000000;
      v18 = v9;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        (_DWORD)v8,
        (unsigned int)&unk_14001DEE8,
        v10 + 8,
        (_DWORD)v8,
        (__int64)v27,
        (__int64)&v26,
        (__int64)&v17,
        (__int64)&v25,
        (__int64)&v16,
        (__int64)&v24,
        (__int64)&v31,
        (__int64)&v23,
        (__int64)&v30,
        (__int64)&v22,
        (__int64)&v29,
        (__int64)&v21,
        (__int64)&v20,
        (__int64)&v28,
        (__int64)&v19,
        (__int64)&v18);
    }
  }
  else
  {
    wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v11 = DirectXDatabaseUpdaterLogging::Provider();
    v12 = (int)v11;
    if ( *(_DWORD *)v11 > 5u && (unsigned __int8)tlgKeywordOn(v11, 0x400000000000LL) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v14 = *((_QWORD *)this + 34);
      v28 = CurrentThreadId;
      v29 = *(_DWORD *)(v14 + 72);
      v30 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v12,
        (unsigned int)byte_14001EC35,
        v14 + 8,
        v15,
        (__int64)&v30,
        (__int64)&v29,
        (__int64)&v28);
    }
  }
  wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
    this,
    v6,
    v7,
    v8);
}

```

## disassembly

```asm
0x14000c2a0  push    rbp
0x14000c2a2  push    rbx
0x14000c2a3  push    rdi
0x14000c2a4  lea     rbp, [rsp-47h]
0x14000c2a9  sub     rsp, 100h
0x14000c2b0  mov     rdi, [rcx+110h]
0x14000c2b7  mov     rbx, rcx
0x14000c2ba  mov     eax, [rdi+48h]
0x14000c2bd  test    eax, eax
0x14000c2bf  jns     loc_14000C438
0x14000c2c5  add     rdi, 50h ; 'P'
0x14000c2c9  cmp     eax, [rdi+8]
0x14000c2cc  jnz     loc_14000C438
0x14000c2d2  test    rdi, rdi
0x14000c2d5  jz      loc_14000C438
0x14000c2db  call    ?zInternalStop@?$ActivityBase@VDirectXDatabaseUpdaterLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x14000c2e0  call    ?Provider@DirectXDatabaseUpdaterLogging@@SAPEBU_tlgProvider_t@@XZ; DirectXDatabaseUpdaterLogging::Provider(void)
0x14000c2e5  mov     r9, rax
0x14000c2e8  mov     ecx, [rax]
0x14000c2ea  cmp     ecx, 5
0x14000c2ed  jbe     loc_14000C4B0
0x14000c2f3  mov     rdx, 400000000000h
0x14000c2fd  mov     rcx, rax
0x14000c300  call    _tlgKeywordOn
0x14000c305  test    al, al
0x14000c307  jz      loc_14000C4B0
0x14000c30d  mov     rax, [rdi+70h]
0x14000c311  lea     rdx, unk_14001DEE8
0x14000c318  mov     rcx, [rdi+78h]
0x14000c31c  mov     r8, [rbx+110h]
0x14000c323  mov     [rbp+57h+var_60], rax
0x14000c327  add     r8, 8
0x14000c32b  mov     eax, [rdi+68h]
0x14000c32e  mov     [rbp+57h+arg_0], eax
0x14000c331  mov     rax, [rdi+60h]
0x14000c335  mov     [rbp+57h+var_58], rax
0x14000c339  mov     rax, [rdi+58h]
0x14000c33d  mov     [rbp+57h+var_50], rax
0x14000c341  mov     eax, [rdi+50h]
0x14000c344  mov     [rbp+57h+arg_8], eax
0x14000c347  mov     rax, [rdi+48h]
0x14000c34b  mov     [rbp+57h+var_48], rax
0x14000c34f  mov     eax, [rdi+20h]
0x14000c352  mov     dword ptr [rbp+57h+arg_10], eax
0x14000c355  mov     rax, [rdi+18h]
0x14000c359  mov     [rbp+57h+var_40], rax
0x14000c35d  mov     eax, [rdi]
0x14000c35f  mov     [rbp+57h+arg_18], eax
0x14000c362  mov     rax, [rdi+80h]
0x14000c369  mov     [rbp+57h+var_38], rax
0x14000c36d  mov     eax, [rdi+40h]
0x14000c370  mov     [rbp+57h+var_70], eax
0x14000c373  mov     rax, [rdi+38h]
0x14000c377  mov     [rbp+57h+var_30], rax
0x14000c37b  mov     eax, [rdi+8]
0x14000c37e  mov     [rbp+57h+var_6C], eax
0x14000c381  mov     eax, 1000000h
0x14000c386  mov     [rbp+57h+var_28], rax
0x14000c38a  mov     [rbp+57h+var_20], rax
0x14000c38e  lea     rax, [rbp+57h+var_68]
0x14000c392  mov     [rsp+110h+var_78], rax
0x14000c39a  lea     rax, [rbp+57h+var_60]
0x14000c39e  mov     [rsp+110h+var_80], rax
0x14000c3a6  lea     rax, [rbp+57h+arg_0]
0x14000c3aa  mov     [rsp+110h+var_88], rax
0x14000c3b2  lea     rax, [rbp+57h+var_58]
0x14000c3b6  mov     [rsp+110h+var_90], rax
0x14000c3be  lea     rax, [rbp+57h+var_50]
0x14000c3c2  mov     [rsp+110h+var_98], rax
0x14000c3c7  lea     rax, [rbp+57h+arg_8]
0x14000c3cb  mov     [rsp+110h+var_A0], rax
0x14000c3d0  lea     rax, [rbp+57h+var_48]
0x14000c3d4  mov     [rsp+110h+var_A8], rax
0x14000c3d9  lea     rax, [rbp+57h+arg_10]
0x14000c3dd  mov     [rsp+110h+var_B0], rax
0x14000c3e2  lea     rax, [rbp+57h+var_40]
0x14000c3e6  mov     [rsp+110h+var_B8], rax
0x14000c3eb  lea     rax, [rbp+57h+arg_18]
0x14000c3ef  mov     [rsp+110h+var_C0], rax
0x14000c3f4  lea     rax, [rbp+57h+var_38]
0x14000c3f8  mov     [rsp+110h+var_C8], rax
0x14000c3fd  lea     rax, [rbp+57h+var_70]
0x14000c401  mov     [rsp+110h+var_D0], rax
0x14000c406  lea     rax, [rbp+57h+var_30]
0x14000c40a  mov     [rsp+110h+var_D8], rax
0x14000c40f  lea     rax, [rbp+57h+var_6C]
0x14000c413  mov     [rsp+110h+var_E0], rax
0x14000c418  lea     rax, [rbp+57h+var_28]
0x14000c41c  mov     [rsp+110h+var_E8], rax
0x14000c421  lea     rax, [rbp+57h+var_20]
0x14000c425  mov     [rbp+57h+var_68], rcx
0x14000c429  mov     rcx, r9
0x14000c42c  mov     [rsp+110h+var_F0], rax
0x14000c431  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x14000c436  jmp     short loc_14000C4B0
0x14000c438  call    ?zInternalStop@?$ActivityBase@VDirectXDatabaseUpdaterLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x14000c43d  call    ?Provider@DirectXDatabaseUpdaterLogging@@SAPEBU_tlgProvider_t@@XZ; DirectXDatabaseUpdaterLogging::Provider(void)
0x14000c442  mov     rdi, rax
0x14000c445  mov     ecx, [rax]
0x14000c447  cmp     ecx, 5
0x14000c44a  jbe     short loc_14000C4B0
0x14000c44c  mov     rdx, 400000000000h
0x14000c456  mov     rcx, rax
0x14000c459  call    _tlgKeywordOn
0x14000c45e  test    al, al
0x14000c460  jz      short loc_14000C4B0
0x14000c462  call    cs:__imp_GetCurrentThreadId
0x14000c468  mov     r8, [rbx+110h]
0x14000c46f  lea     rdx, byte_14001EC35
0x14000c476  mov     [rbp+57h+arg_0], eax
0x14000c479  mov     rcx, rdi
0x14000c47c  mov     eax, [r8+48h]
0x14000c480  add     r8, 8
0x14000c484  mov     [rbp+57h+arg_8], eax
0x14000c487  mov     eax, 1000000h
0x14000c48c  mov     [rbp+57h+arg_10], rax
0x14000c490  lea     rax, [rbp+57h+arg_0]
0x14000c494  mov     [rsp+110h+var_E0], rax
0x14000c499  lea     rax, [rbp+57h+arg_8]
0x14000c49d  mov     [rsp+110h+var_E8], rax
0x14000c4a2  lea     rax, [rbp+57h+arg_10]
0x14000c4a6  mov     [rsp+110h+var_F0], rax
0x14000c4ab  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14000c4b0  mov     rcx, rbx
0x14000c4b3  add     rsp, 100h
0x14000c4ba  pop     rdi
0x14000c4bb  pop     rbx
0x14000c4bc  pop     rbp
0x14000c4bd  jmp     ?IgnoreCurrentThread@?$ActivityBase@VDirectXDatabaseUpdaterLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
