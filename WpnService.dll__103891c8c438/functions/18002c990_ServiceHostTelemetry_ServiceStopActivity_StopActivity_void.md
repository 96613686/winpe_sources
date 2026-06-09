# ServiceHostTelemetry::ServiceStopActivity::StopActivity(void)

- ea: `0x18002c990`
- end: `0x18002cbb5`
- name: `?StopActivity@ServiceStopActivity@ServiceHostTelemetry@@MEAAXXZ`
- size: `549`
- prototype: `void __fastcall(ServiceHostTelemetry::ServiceStopActivity *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task`

## callees

- `0x180001e64`
- `0x18000f270`
- `0x18000f2f0`
- `0x180016b74`
- `0x1800172bc`
- `0x180018430`
- `0x18002c990`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002cb52`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002cb52`

## pseudocode

```c
void __fastcall ServiceHostTelemetry::ServiceStopActivity::StopActivity(
        ServiceHostTelemetry::ServiceStopActivity *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  const struct _tlgProvider_t *v5; // rax
  __int64 v6; // r8
  __int64 v7; // r9
  __int64 v8; // rcx
  __int64 v9; // r8
  const struct _tlgProvider_t *v10; // rax
  __int64 v11; // r8
  __int64 v12; // r9
  __int64 v13; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v15; // r8
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
    wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v5 = ServiceHostLogging::Provider();
    if ( *(_DWORD *)v5 > 5u && (unsigned __int8)tlgKeywordOn(v5, 0x400000000000LL, v6, v5) )
    {
      v8 = *((_QWORD *)v4 + 15);
      v9 = *((_QWORD *)this + 34);
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
      v18 = v8;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        v7,
        (__int64)&byte_18003D30F,
        v9 + 8,
        v7,
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
  else
  {
    wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v10 = ServiceHostLogging::Provider();
    v13 = (__int64)v10;
    if ( *(_DWORD *)v10 > 5u && (unsigned __int8)tlgKeywordOn(v10, 0x400000000000LL, v11, v12) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v15 = *((_QWORD *)this + 34);
      v28 = CurrentThreadId;
      v29 = *(_DWORD *)(v15 + 72);
      v30 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v13,
        (unsigned __int8 *)byte_18003D2BB,
        (const GUID *)(v15 + 8),
        0,
        (__int64)&v30,
        (__int64)&v29,
        (__int64)&v28);
    }
  }
  wil::ActivityBase<WnsCPTracelogger,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x18002c990  push    rbp
0x18002c992  push    rbx
0x18002c993  push    rdi
0x18002c994  lea     rbp, [rsp-47h]
0x18002c999  sub     rsp, 100h
0x18002c9a0  mov     rdi, [rcx+110h]
0x18002c9a7  mov     rbx, rcx
0x18002c9aa  mov     eax, [rdi+48h]
0x18002c9ad  test    eax, eax
0x18002c9af  jns     loc_18002CB28
0x18002c9b5  add     rdi, 50h ; 'P'
0x18002c9b9  cmp     eax, [rdi+8]
0x18002c9bc  jnz     loc_18002CB28
0x18002c9c2  test    rdi, rdi
0x18002c9c5  jz      loc_18002CB28
0x18002c9cb  call    ?zInternalStop@?$ActivityBase@VServiceHostLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18002c9d0  call    ?Provider@ServiceHostLogging@@SAPEBU_tlgProvider_t@@XZ; ServiceHostLogging::Provider(void)
0x18002c9d5  mov     r9, rax
0x18002c9d8  mov     ecx, [rax]
0x18002c9da  cmp     ecx, 5
0x18002c9dd  jbe     loc_18002CBA3
0x18002c9e3  mov     rdx, 400000000000h
0x18002c9ed  mov     rcx, rax
0x18002c9f0  call    _tlgKeywordOn
0x18002c9f5  test    al, al
0x18002c9f7  jz      loc_18002CBA3
0x18002c9fd  mov     rax, [rdi+70h]
0x18002ca01  lea     rdx, byte_18003D30F
0x18002ca08  mov     rcx, [rdi+78h]
0x18002ca0c  mov     r8, [rbx+110h]
0x18002ca13  mov     [rbp+57h+var_60], rax
0x18002ca17  add     r8, 8
0x18002ca1b  mov     eax, [rdi+68h]
0x18002ca1e  mov     [rbp+57h+arg_0], eax
0x18002ca21  mov     rax, [rdi+60h]
0x18002ca25  mov     [rbp+57h+var_58], rax
0x18002ca29  mov     rax, [rdi+58h]
0x18002ca2d  mov     [rbp+57h+var_50], rax
0x18002ca31  mov     eax, [rdi+50h]
0x18002ca34  mov     [rbp+57h+arg_8], eax
0x18002ca37  mov     rax, [rdi+48h]
0x18002ca3b  mov     [rbp+57h+var_48], rax
0x18002ca3f  mov     eax, [rdi+20h]
0x18002ca42  mov     dword ptr [rbp+57h+arg_10], eax
0x18002ca45  mov     rax, [rdi+18h]
0x18002ca49  mov     [rbp+57h+var_40], rax
0x18002ca4d  mov     eax, [rdi]
0x18002ca4f  mov     [rbp+57h+arg_18], eax
0x18002ca52  mov     rax, [rdi+80h]
0x18002ca59  mov     [rbp+57h+var_38], rax
0x18002ca5d  mov     eax, [rdi+40h]
0x18002ca60  mov     [rbp+57h+var_70], eax
0x18002ca63  mov     rax, [rdi+38h]
0x18002ca67  mov     [rbp+57h+var_30], rax
0x18002ca6b  mov     eax, [rdi+8]
0x18002ca6e  mov     [rbp+57h+var_6C], eax
0x18002ca71  mov     eax, 1000000h
0x18002ca76  mov     [rbp+57h+var_28], rax
0x18002ca7a  mov     [rbp+57h+var_20], rax
0x18002ca7e  lea     rax, [rbp+57h+var_68]
0x18002ca82  mov     [rsp+110h+var_78], rax
0x18002ca8a  lea     rax, [rbp+57h+var_60]
0x18002ca8e  mov     [rsp+110h+var_80], rax
0x18002ca96  lea     rax, [rbp+57h+arg_0]
0x18002ca9a  mov     [rsp+110h+var_88], rax
0x18002caa2  lea     rax, [rbp+57h+var_58]
0x18002caa6  mov     [rsp+110h+var_90], rax
0x18002caae  lea     rax, [rbp+57h+var_50]
0x18002cab2  mov     [rsp+110h+var_98], rax
0x18002cab7  lea     rax, [rbp+57h+arg_8]
0x18002cabb  mov     [rsp+110h+var_A0], rax
0x18002cac0  lea     rax, [rbp+57h+var_48]
0x18002cac4  mov     [rsp+110h+var_A8], rax
0x18002cac9  lea     rax, [rbp+57h+arg_10]
0x18002cacd  mov     [rsp+110h+var_B0], rax
0x18002cad2  lea     rax, [rbp+57h+var_40]
0x18002cad6  mov     [rsp+110h+var_B8], rax
0x18002cadb  lea     rax, [rbp+57h+arg_18]
0x18002cadf  mov     [rsp+110h+var_C0], rax
0x18002cae4  lea     rax, [rbp+57h+var_38]
0x18002cae8  mov     [rsp+110h+var_C8], rax
0x18002caed  lea     rax, [rbp+57h+var_70]
0x18002caf1  mov     [rsp+110h+var_D0], rax
0x18002caf6  lea     rax, [rbp+57h+var_30]
0x18002cafa  mov     [rsp+110h+var_D8], rax
0x18002caff  lea     rax, [rbp+57h+var_6C]
0x18002cb03  mov     [rsp+110h+var_E0], rax
0x18002cb08  lea     rax, [rbp+57h+var_28]
0x18002cb0c  mov     [rsp+110h+var_E8], rax
0x18002cb11  lea     rax, [rbp+57h+var_20]
0x18002cb15  mov     [rbp+57h+var_68], rcx
0x18002cb19  mov     rcx, r9
0x18002cb1c  mov     [rsp+110h+var_F0], rax
0x18002cb21  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18002cb26  jmp     short loc_18002CBA3
0x18002cb28  call    ?zInternalStop@?$ActivityBase@VServiceHostLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18002cb2d  call    ?Provider@ServiceHostLogging@@SAPEBU_tlgProvider_t@@XZ; ServiceHostLogging::Provider(void)
0x18002cb32  mov     rdi, rax
0x18002cb35  mov     ecx, [rax]
0x18002cb37  cmp     ecx, 5
0x18002cb3a  jbe     short loc_18002CBA3
0x18002cb3c  mov     rdx, 400000000000h
0x18002cb46  mov     rcx, rax
0x18002cb49  call    _tlgKeywordOn
0x18002cb4e  test    al, al
0x18002cb50  jz      short loc_18002CBA3
0x18002cb52  call    cs:__imp_GetCurrentThreadId
0x18002cb58  mov     r8, [rbx+110h]
0x18002cb5f  lea     rdx, byte_18003D2BB
0x18002cb66  mov     [rbp+57h+arg_0], eax
0x18002cb69  xor     r9d, r9d
0x18002cb6c  mov     rcx, rdi
0x18002cb6f  mov     eax, [r8+48h]
0x18002cb73  add     r8, 8
0x18002cb77  mov     [rbp+57h+arg_8], eax
0x18002cb7a  mov     eax, 1000000h
0x18002cb7f  mov     [rbp+57h+arg_10], rax
0x18002cb83  lea     rax, [rbp+57h+arg_0]
0x18002cb87  mov     [rsp+110h+var_E0], rax
0x18002cb8c  lea     rax, [rbp+57h+arg_8]
0x18002cb90  mov     [rsp+110h+var_E8], rax
0x18002cb95  lea     rax, [rbp+57h+arg_10]
0x18002cb99  mov     [rsp+110h+var_F0], rax
0x18002cb9e  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18002cba3  mov     rcx, rbx
0x18002cba6  add     rsp, 100h
0x18002cbad  pop     rdi
0x18002cbae  pop     rbx
0x18002cbaf  pop     rbp
0x18002cbb0  jmp     ?IgnoreCurrentThread@?$ActivityBase@VWnsCPTracelogger@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WnsCPTracelogger,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
