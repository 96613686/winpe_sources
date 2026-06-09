# DirectXDatabaseUpdaterTelemetry::UninstallDxDbFOD::StopActivity(void)

- ea: `0x14000c4d0`
- end: `0x14000c6f2`
- name: `?StopActivity@UninstallDxDbFOD@DirectXDatabaseUpdaterTelemetry@@MEAAXXZ`
- size: `546`
- prototype: `void __fastcall(DirectXDatabaseUpdaterTelemetry::UninstallDxDbFOD *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update`

## callees

- `0x140001010`
- `0x1400018ec`
- `0x1400022ec`
- `0x1400082c0`
- `0x14000946c`
- `0x14000c4d0`
- `0x14000efa8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000c692`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000c692`

## pseudocode

```c
void __fastcall DirectXDatabaseUpdaterTelemetry::UninstallDxDbFOD::StopActivity(
        DirectXDatabaseUpdaterTelemetry::UninstallDxDbFOD *this)
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
        (unsigned int)&word_14001E2F6,
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
        (unsigned int)&dword_14001EBE4,
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
0x14000c4d0  push    rbp
0x14000c4d2  push    rbx
0x14000c4d3  push    rdi
0x14000c4d4  lea     rbp, [rsp-47h]
0x14000c4d9  sub     rsp, 100h
0x14000c4e0  mov     rdi, [rcx+110h]
0x14000c4e7  mov     rbx, rcx
0x14000c4ea  mov     eax, [rdi+48h]
0x14000c4ed  test    eax, eax
0x14000c4ef  jns     loc_14000C668
0x14000c4f5  add     rdi, 50h ; 'P'
0x14000c4f9  cmp     eax, [rdi+8]
0x14000c4fc  jnz     loc_14000C668
0x14000c502  test    rdi, rdi
0x14000c505  jz      loc_14000C668
0x14000c50b  call    ?zInternalStop@?$ActivityBase@VDirectXDatabaseUpdaterLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x14000c510  call    ?Provider@DirectXDatabaseUpdaterLogging@@SAPEBU_tlgProvider_t@@XZ; DirectXDatabaseUpdaterLogging::Provider(void)
0x14000c515  mov     r9, rax
0x14000c518  mov     ecx, [rax]
0x14000c51a  cmp     ecx, 5
0x14000c51d  jbe     loc_14000C6E0
0x14000c523  mov     rdx, 400000000000h
0x14000c52d  mov     rcx, rax
0x14000c530  call    _tlgKeywordOn
0x14000c535  test    al, al
0x14000c537  jz      loc_14000C6E0
0x14000c53d  mov     rax, [rdi+70h]
0x14000c541  lea     rdx, word_14001E2F6
0x14000c548  mov     rcx, [rdi+78h]
0x14000c54c  mov     r8, [rbx+110h]
0x14000c553  mov     [rbp+57h+var_60], rax
0x14000c557  add     r8, 8
0x14000c55b  mov     eax, [rdi+68h]
0x14000c55e  mov     [rbp+57h+arg_0], eax
0x14000c561  mov     rax, [rdi+60h]
0x14000c565  mov     [rbp+57h+var_58], rax
0x14000c569  mov     rax, [rdi+58h]
0x14000c56d  mov     [rbp+57h+var_50], rax
0x14000c571  mov     eax, [rdi+50h]
0x14000c574  mov     [rbp+57h+arg_8], eax
0x14000c577  mov     rax, [rdi+48h]
0x14000c57b  mov     [rbp+57h+var_48], rax
0x14000c57f  mov     eax, [rdi+20h]
0x14000c582  mov     dword ptr [rbp+57h+arg_10], eax
0x14000c585  mov     rax, [rdi+18h]
0x14000c589  mov     [rbp+57h+var_40], rax
0x14000c58d  mov     eax, [rdi]
0x14000c58f  mov     [rbp+57h+arg_18], eax
0x14000c592  mov     rax, [rdi+80h]
0x14000c599  mov     [rbp+57h+var_38], rax
0x14000c59d  mov     eax, [rdi+40h]
0x14000c5a0  mov     [rbp+57h+var_70], eax
0x14000c5a3  mov     rax, [rdi+38h]
0x14000c5a7  mov     [rbp+57h+var_30], rax
0x14000c5ab  mov     eax, [rdi+8]
0x14000c5ae  mov     [rbp+57h+var_6C], eax
0x14000c5b1  mov     eax, 1000000h
0x14000c5b6  mov     [rbp+57h+var_28], rax
0x14000c5ba  mov     [rbp+57h+var_20], rax
0x14000c5be  lea     rax, [rbp+57h+var_68]
0x14000c5c2  mov     [rsp+110h+var_78], rax
0x14000c5ca  lea     rax, [rbp+57h+var_60]
0x14000c5ce  mov     [rsp+110h+var_80], rax
0x14000c5d6  lea     rax, [rbp+57h+arg_0]
0x14000c5da  mov     [rsp+110h+var_88], rax
0x14000c5e2  lea     rax, [rbp+57h+var_58]
0x14000c5e6  mov     [rsp+110h+var_90], rax
0x14000c5ee  lea     rax, [rbp+57h+var_50]
0x14000c5f2  mov     [rsp+110h+var_98], rax
0x14000c5f7  lea     rax, [rbp+57h+arg_8]
0x14000c5fb  mov     [rsp+110h+var_A0], rax
0x14000c600  lea     rax, [rbp+57h+var_48]
0x14000c604  mov     [rsp+110h+var_A8], rax
0x14000c609  lea     rax, [rbp+57h+arg_10]
0x14000c60d  mov     [rsp+110h+var_B0], rax
0x14000c612  lea     rax, [rbp+57h+var_40]
0x14000c616  mov     [rsp+110h+var_B8], rax
0x14000c61b  lea     rax, [rbp+57h+arg_18]
0x14000c61f  mov     [rsp+110h+var_C0], rax
0x14000c624  lea     rax, [rbp+57h+var_38]
0x14000c628  mov     [rsp+110h+var_C8], rax
0x14000c62d  lea     rax, [rbp+57h+var_70]
0x14000c631  mov     [rsp+110h+var_D0], rax
0x14000c636  lea     rax, [rbp+57h+var_30]
0x14000c63a  mov     [rsp+110h+var_D8], rax
0x14000c63f  lea     rax, [rbp+57h+var_6C]
0x14000c643  mov     [rsp+110h+var_E0], rax
0x14000c648  lea     rax, [rbp+57h+var_28]
0x14000c64c  mov     [rsp+110h+var_E8], rax
0x14000c651  lea     rax, [rbp+57h+var_20]
0x14000c655  mov     [rbp+57h+var_68], rcx
0x14000c659  mov     rcx, r9
0x14000c65c  mov     [rsp+110h+var_F0], rax
0x14000c661  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x14000c666  jmp     short loc_14000C6E0
0x14000c668  call    ?zInternalStop@?$ActivityBase@VDirectXDatabaseUpdaterLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x14000c66d  call    ?Provider@DirectXDatabaseUpdaterLogging@@SAPEBU_tlgProvider_t@@XZ; DirectXDatabaseUpdaterLogging::Provider(void)
0x14000c672  mov     rdi, rax
0x14000c675  mov     ecx, [rax]
0x14000c677  cmp     ecx, 5
0x14000c67a  jbe     short loc_14000C6E0
0x14000c67c  mov     rdx, 400000000000h
0x14000c686  mov     rcx, rax
0x14000c689  call    _tlgKeywordOn
0x14000c68e  test    al, al
0x14000c690  jz      short loc_14000C6E0
0x14000c692  call    cs:__imp_GetCurrentThreadId
0x14000c698  mov     r8, [rbx+110h]
0x14000c69f  lea     rdx, dword_14001EBE4
0x14000c6a6  mov     [rbp+57h+arg_0], eax
0x14000c6a9  mov     rcx, rdi
0x14000c6ac  mov     eax, [r8+48h]
0x14000c6b0  add     r8, 8
0x14000c6b4  mov     [rbp+57h+arg_8], eax
0x14000c6b7  mov     eax, 1000000h
0x14000c6bc  mov     [rbp+57h+arg_10], rax
0x14000c6c0  lea     rax, [rbp+57h+arg_0]
0x14000c6c4  mov     [rsp+110h+var_E0], rax
0x14000c6c9  lea     rax, [rbp+57h+arg_8]
0x14000c6cd  mov     [rsp+110h+var_E8], rax
0x14000c6d2  lea     rax, [rbp+57h+arg_10]
0x14000c6d6  mov     [rsp+110h+var_F0], rax
0x14000c6db  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14000c6e0  mov     rcx, rbx
0x14000c6e3  add     rsp, 100h
0x14000c6ea  pop     rdi
0x14000c6eb  pop     rbx
0x14000c6ec  pop     rbp
0x14000c6ed  jmp     ?IgnoreCurrentThread@?$ActivityBase@VDirectXDatabaseUpdaterLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
