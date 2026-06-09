# DirectXDatabaseUpdaterTelemetry::WriteLastRunData::StopActivity(void)

- ea: `0x14000c930`
- end: `0x14000cb52`
- name: `?StopActivity@WriteLastRunData@DirectXDatabaseUpdaterTelemetry@@MEAAXXZ`
- size: `546`
- prototype: `void __fastcall(DirectXDatabaseUpdaterTelemetry::WriteLastRunData *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update`

## callees

- `0x140001010`
- `0x1400018ec`
- `0x1400022ec`
- `0x1400082c0`
- `0x14000946c`
- `0x14000c930`
- `0x14000efa8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000caf2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000caf2`

## pseudocode

```c
void __fastcall DirectXDatabaseUpdaterTelemetry::WriteLastRunData::StopActivity(
        DirectXDatabaseUpdaterTelemetry::WriteLastRunData *this)
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
        (unsigned int)byte_14001E483,
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
        (unsigned int)byte_14001E979,
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
0x14000c930  push    rbp
0x14000c932  push    rbx
0x14000c933  push    rdi
0x14000c934  lea     rbp, [rsp-47h]
0x14000c939  sub     rsp, 100h
0x14000c940  mov     rdi, [rcx+110h]
0x14000c947  mov     rbx, rcx
0x14000c94a  mov     eax, [rdi+48h]
0x14000c94d  test    eax, eax
0x14000c94f  jns     loc_14000CAC8
0x14000c955  add     rdi, 50h ; 'P'
0x14000c959  cmp     eax, [rdi+8]
0x14000c95c  jnz     loc_14000CAC8
0x14000c962  test    rdi, rdi
0x14000c965  jz      loc_14000CAC8
0x14000c96b  call    ?zInternalStop@?$ActivityBase@VDirectXDatabaseUpdaterLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x14000c970  call    ?Provider@DirectXDatabaseUpdaterLogging@@SAPEBU_tlgProvider_t@@XZ; DirectXDatabaseUpdaterLogging::Provider(void)
0x14000c975  mov     r9, rax
0x14000c978  mov     ecx, [rax]
0x14000c97a  cmp     ecx, 5
0x14000c97d  jbe     loc_14000CB40
0x14000c983  mov     rdx, 400000000000h
0x14000c98d  mov     rcx, rax
0x14000c990  call    _tlgKeywordOn
0x14000c995  test    al, al
0x14000c997  jz      loc_14000CB40
0x14000c99d  mov     rax, [rdi+70h]
0x14000c9a1  lea     rdx, byte_14001E483
0x14000c9a8  mov     rcx, [rdi+78h]
0x14000c9ac  mov     r8, [rbx+110h]
0x14000c9b3  mov     [rbp+57h+var_60], rax
0x14000c9b7  add     r8, 8
0x14000c9bb  mov     eax, [rdi+68h]
0x14000c9be  mov     [rbp+57h+arg_0], eax
0x14000c9c1  mov     rax, [rdi+60h]
0x14000c9c5  mov     [rbp+57h+var_58], rax
0x14000c9c9  mov     rax, [rdi+58h]
0x14000c9cd  mov     [rbp+57h+var_50], rax
0x14000c9d1  mov     eax, [rdi+50h]
0x14000c9d4  mov     [rbp+57h+arg_8], eax
0x14000c9d7  mov     rax, [rdi+48h]
0x14000c9db  mov     [rbp+57h+var_48], rax
0x14000c9df  mov     eax, [rdi+20h]
0x14000c9e2  mov     dword ptr [rbp+57h+arg_10], eax
0x14000c9e5  mov     rax, [rdi+18h]
0x14000c9e9  mov     [rbp+57h+var_40], rax
0x14000c9ed  mov     eax, [rdi]
0x14000c9ef  mov     [rbp+57h+arg_18], eax
0x14000c9f2  mov     rax, [rdi+80h]
0x14000c9f9  mov     [rbp+57h+var_38], rax
0x14000c9fd  mov     eax, [rdi+40h]
0x14000ca00  mov     [rbp+57h+var_70], eax
0x14000ca03  mov     rax, [rdi+38h]
0x14000ca07  mov     [rbp+57h+var_30], rax
0x14000ca0b  mov     eax, [rdi+8]
0x14000ca0e  mov     [rbp+57h+var_6C], eax
0x14000ca11  mov     eax, 1000000h
0x14000ca16  mov     [rbp+57h+var_28], rax
0x14000ca1a  mov     [rbp+57h+var_20], rax
0x14000ca1e  lea     rax, [rbp+57h+var_68]
0x14000ca22  mov     [rsp+110h+var_78], rax
0x14000ca2a  lea     rax, [rbp+57h+var_60]
0x14000ca2e  mov     [rsp+110h+var_80], rax
0x14000ca36  lea     rax, [rbp+57h+arg_0]
0x14000ca3a  mov     [rsp+110h+var_88], rax
0x14000ca42  lea     rax, [rbp+57h+var_58]
0x14000ca46  mov     [rsp+110h+var_90], rax
0x14000ca4e  lea     rax, [rbp+57h+var_50]
0x14000ca52  mov     [rsp+110h+var_98], rax
0x14000ca57  lea     rax, [rbp+57h+arg_8]
0x14000ca5b  mov     [rsp+110h+var_A0], rax
0x14000ca60  lea     rax, [rbp+57h+var_48]
0x14000ca64  mov     [rsp+110h+var_A8], rax
0x14000ca69  lea     rax, [rbp+57h+arg_10]
0x14000ca6d  mov     [rsp+110h+var_B0], rax
0x14000ca72  lea     rax, [rbp+57h+var_40]
0x14000ca76  mov     [rsp+110h+var_B8], rax
0x14000ca7b  lea     rax, [rbp+57h+arg_18]
0x14000ca7f  mov     [rsp+110h+var_C0], rax
0x14000ca84  lea     rax, [rbp+57h+var_38]
0x14000ca88  mov     [rsp+110h+var_C8], rax
0x14000ca8d  lea     rax, [rbp+57h+var_70]
0x14000ca91  mov     [rsp+110h+var_D0], rax
0x14000ca96  lea     rax, [rbp+57h+var_30]
0x14000ca9a  mov     [rsp+110h+var_D8], rax
0x14000ca9f  lea     rax, [rbp+57h+var_6C]
0x14000caa3  mov     [rsp+110h+var_E0], rax
0x14000caa8  lea     rax, [rbp+57h+var_28]
0x14000caac  mov     [rsp+110h+var_E8], rax
0x14000cab1  lea     rax, [rbp+57h+var_20]
0x14000cab5  mov     [rbp+57h+var_68], rcx
0x14000cab9  mov     rcx, r9
0x14000cabc  mov     [rsp+110h+var_F0], rax
0x14000cac1  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x14000cac6  jmp     short loc_14000CB40
0x14000cac8  call    ?zInternalStop@?$ActivityBase@VDirectXDatabaseUpdaterLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x14000cacd  call    ?Provider@DirectXDatabaseUpdaterLogging@@SAPEBU_tlgProvider_t@@XZ; DirectXDatabaseUpdaterLogging::Provider(void)
0x14000cad2  mov     rdi, rax
0x14000cad5  mov     ecx, [rax]
0x14000cad7  cmp     ecx, 5
0x14000cada  jbe     short loc_14000CB40
0x14000cadc  mov     rdx, 400000000000h
0x14000cae6  mov     rcx, rax
0x14000cae9  call    _tlgKeywordOn
0x14000caee  test    al, al
0x14000caf0  jz      short loc_14000CB40
0x14000caf2  call    cs:__imp_GetCurrentThreadId
0x14000caf8  mov     r8, [rbx+110h]
0x14000caff  lea     rdx, byte_14001E979
0x14000cb06  mov     [rbp+57h+arg_0], eax
0x14000cb09  mov     rcx, rdi
0x14000cb0c  mov     eax, [r8+48h]
0x14000cb10  add     r8, 8
0x14000cb14  mov     [rbp+57h+arg_8], eax
0x14000cb17  mov     eax, 1000000h
0x14000cb1c  mov     [rbp+57h+arg_10], rax
0x14000cb20  lea     rax, [rbp+57h+arg_0]
0x14000cb24  mov     [rsp+110h+var_E0], rax
0x14000cb29  lea     rax, [rbp+57h+arg_8]
0x14000cb2d  mov     [rsp+110h+var_E8], rax
0x14000cb32  lea     rax, [rbp+57h+arg_10]
0x14000cb36  mov     [rsp+110h+var_F0], rax
0x14000cb3b  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14000cb40  mov     rcx, rbx
0x14000cb43  add     rsp, 100h
0x14000cb4a  pop     rdi
0x14000cb4b  pop     rbx
0x14000cb4c  pop     rbp
0x14000cb4d  jmp     ?IgnoreCurrentThread@?$ActivityBase@VDirectXDatabaseUpdaterLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
