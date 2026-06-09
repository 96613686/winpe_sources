# DirectXDatabaseUpdaterTelemetry::CreateDbDownloadJobActivity::StopActivity(void)

- ea: `0x14000be40`
- end: `0x14000c062`
- name: `?StopActivity@CreateDbDownloadJobActivity@DirectXDatabaseUpdaterTelemetry@@MEAAXXZ`
- size: `546`
- prototype: `void __fastcall(DirectXDatabaseUpdaterTelemetry::CreateDbDownloadJobActivity *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update`

## callees

- `0x140001010`
- `0x1400018ec`
- `0x1400022ec`
- `0x1400082c0`
- `0x14000946c`
- `0x14000be40`
- `0x14000efa8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000c002`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000c002`

## pseudocode

```c
void __fastcall DirectXDatabaseUpdaterTelemetry::CreateDbDownloadJobActivity::StopActivity(
        DirectXDatabaseUpdaterTelemetry::CreateDbDownloadJobActivity *this)
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
        (unsigned int)word_14001E01A,
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
        (unsigned int)byte_14001E5AB,
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
0x14000be40  push    rbp
0x14000be42  push    rbx
0x14000be43  push    rdi
0x14000be44  lea     rbp, [rsp-47h]
0x14000be49  sub     rsp, 100h
0x14000be50  mov     rdi, [rcx+110h]
0x14000be57  mov     rbx, rcx
0x14000be5a  mov     eax, [rdi+48h]
0x14000be5d  test    eax, eax
0x14000be5f  jns     loc_14000BFD8
0x14000be65  add     rdi, 50h ; 'P'
0x14000be69  cmp     eax, [rdi+8]
0x14000be6c  jnz     loc_14000BFD8
0x14000be72  test    rdi, rdi
0x14000be75  jz      loc_14000BFD8
0x14000be7b  call    ?zInternalStop@?$ActivityBase@VDirectXDatabaseUpdaterLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x14000be80  call    ?Provider@DirectXDatabaseUpdaterLogging@@SAPEBU_tlgProvider_t@@XZ; DirectXDatabaseUpdaterLogging::Provider(void)
0x14000be85  mov     r9, rax
0x14000be88  mov     ecx, [rax]
0x14000be8a  cmp     ecx, 5
0x14000be8d  jbe     loc_14000C050
0x14000be93  mov     rdx, 400000000000h
0x14000be9d  mov     rcx, rax
0x14000bea0  call    _tlgKeywordOn
0x14000bea5  test    al, al
0x14000bea7  jz      loc_14000C050
0x14000bead  mov     rax, [rdi+70h]
0x14000beb1  lea     rdx, word_14001E01A
0x14000beb8  mov     rcx, [rdi+78h]
0x14000bebc  mov     r8, [rbx+110h]
0x14000bec3  mov     [rbp+57h+var_60], rax
0x14000bec7  add     r8, 8
0x14000becb  mov     eax, [rdi+68h]
0x14000bece  mov     [rbp+57h+arg_0], eax
0x14000bed1  mov     rax, [rdi+60h]
0x14000bed5  mov     [rbp+57h+var_58], rax
0x14000bed9  mov     rax, [rdi+58h]
0x14000bedd  mov     [rbp+57h+var_50], rax
0x14000bee1  mov     eax, [rdi+50h]
0x14000bee4  mov     [rbp+57h+arg_8], eax
0x14000bee7  mov     rax, [rdi+48h]
0x14000beeb  mov     [rbp+57h+var_48], rax
0x14000beef  mov     eax, [rdi+20h]
0x14000bef2  mov     dword ptr [rbp+57h+arg_10], eax
0x14000bef5  mov     rax, [rdi+18h]
0x14000bef9  mov     [rbp+57h+var_40], rax
0x14000befd  mov     eax, [rdi]
0x14000beff  mov     [rbp+57h+arg_18], eax
0x14000bf02  mov     rax, [rdi+80h]
0x14000bf09  mov     [rbp+57h+var_38], rax
0x14000bf0d  mov     eax, [rdi+40h]
0x14000bf10  mov     [rbp+57h+var_70], eax
0x14000bf13  mov     rax, [rdi+38h]
0x14000bf17  mov     [rbp+57h+var_30], rax
0x14000bf1b  mov     eax, [rdi+8]
0x14000bf1e  mov     [rbp+57h+var_6C], eax
0x14000bf21  mov     eax, 1000000h
0x14000bf26  mov     [rbp+57h+var_28], rax
0x14000bf2a  mov     [rbp+57h+var_20], rax
0x14000bf2e  lea     rax, [rbp+57h+var_68]
0x14000bf32  mov     [rsp+110h+var_78], rax
0x14000bf3a  lea     rax, [rbp+57h+var_60]
0x14000bf3e  mov     [rsp+110h+var_80], rax
0x14000bf46  lea     rax, [rbp+57h+arg_0]
0x14000bf4a  mov     [rsp+110h+var_88], rax
0x14000bf52  lea     rax, [rbp+57h+var_58]
0x14000bf56  mov     [rsp+110h+var_90], rax
0x14000bf5e  lea     rax, [rbp+57h+var_50]
0x14000bf62  mov     [rsp+110h+var_98], rax
0x14000bf67  lea     rax, [rbp+57h+arg_8]
0x14000bf6b  mov     [rsp+110h+var_A0], rax
0x14000bf70  lea     rax, [rbp+57h+var_48]
0x14000bf74  mov     [rsp+110h+var_A8], rax
0x14000bf79  lea     rax, [rbp+57h+arg_10]
0x14000bf7d  mov     [rsp+110h+var_B0], rax
0x14000bf82  lea     rax, [rbp+57h+var_40]
0x14000bf86  mov     [rsp+110h+var_B8], rax
0x14000bf8b  lea     rax, [rbp+57h+arg_18]
0x14000bf8f  mov     [rsp+110h+var_C0], rax
0x14000bf94  lea     rax, [rbp+57h+var_38]
0x14000bf98  mov     [rsp+110h+var_C8], rax
0x14000bf9d  lea     rax, [rbp+57h+var_70]
0x14000bfa1  mov     [rsp+110h+var_D0], rax
0x14000bfa6  lea     rax, [rbp+57h+var_30]
0x14000bfaa  mov     [rsp+110h+var_D8], rax
0x14000bfaf  lea     rax, [rbp+57h+var_6C]
0x14000bfb3  mov     [rsp+110h+var_E0], rax
0x14000bfb8  lea     rax, [rbp+57h+var_28]
0x14000bfbc  mov     [rsp+110h+var_E8], rax
0x14000bfc1  lea     rax, [rbp+57h+var_20]
0x14000bfc5  mov     [rbp+57h+var_68], rcx
0x14000bfc9  mov     rcx, r9
0x14000bfcc  mov     [rsp+110h+var_F0], rax
0x14000bfd1  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x14000bfd6  jmp     short loc_14000C050
0x14000bfd8  call    ?zInternalStop@?$ActivityBase@VDirectXDatabaseUpdaterLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x14000bfdd  call    ?Provider@DirectXDatabaseUpdaterLogging@@SAPEBU_tlgProvider_t@@XZ; DirectXDatabaseUpdaterLogging::Provider(void)
0x14000bfe2  mov     rdi, rax
0x14000bfe5  mov     ecx, [rax]
0x14000bfe7  cmp     ecx, 5
0x14000bfea  jbe     short loc_14000C050
0x14000bfec  mov     rdx, 400000000000h
0x14000bff6  mov     rcx, rax
0x14000bff9  call    _tlgKeywordOn
0x14000bffe  test    al, al
0x14000c000  jz      short loc_14000C050
0x14000c002  call    cs:__imp_GetCurrentThreadId
0x14000c008  mov     r8, [rbx+110h]
0x14000c00f  lea     rdx, byte_14001E5AB
0x14000c016  mov     [rbp+57h+arg_0], eax
0x14000c019  mov     rcx, rdi
0x14000c01c  mov     eax, [r8+48h]
0x14000c020  add     r8, 8
0x14000c024  mov     [rbp+57h+arg_8], eax
0x14000c027  mov     eax, 1000000h
0x14000c02c  mov     [rbp+57h+arg_10], rax
0x14000c030  lea     rax, [rbp+57h+arg_0]
0x14000c034  mov     [rsp+110h+var_E0], rax
0x14000c039  lea     rax, [rbp+57h+arg_8]
0x14000c03d  mov     [rsp+110h+var_E8], rax
0x14000c042  lea     rax, [rbp+57h+arg_10]
0x14000c046  mov     [rsp+110h+var_F0], rax
0x14000c04b  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14000c050  mov     rcx, rbx
0x14000c053  add     rsp, 100h
0x14000c05a  pop     rdi
0x14000c05b  pop     rbx
0x14000c05c  pop     rbp
0x14000c05d  jmp     ?IgnoreCurrentThread@?$ActivityBase@VDirectXDatabaseUpdaterLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
