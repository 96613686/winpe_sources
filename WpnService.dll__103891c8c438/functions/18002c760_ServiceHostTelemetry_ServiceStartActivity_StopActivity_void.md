# ServiceHostTelemetry::ServiceStartActivity::StopActivity(void)

- ea: `0x18002c760`
- end: `0x18002c985`
- name: `?StopActivity@ServiceStartActivity@ServiceHostTelemetry@@MEAAXXZ`
- size: `549`
- prototype: `void __fastcall(ServiceHostTelemetry::ServiceStartActivity *__hidden this)`
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
- `0x18002c760`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002c922`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002c922`

## pseudocode

```c
void __fastcall ServiceHostTelemetry::ServiceStartActivity::StopActivity(
        ServiceHostTelemetry::ServiceStartActivity *this)
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
        (__int64)byte_18003D6AD,
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
        (unsigned __int8 *)&unk_18003D658,
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
0x18002c760  push    rbp
0x18002c762  push    rbx
0x18002c763  push    rdi
0x18002c764  lea     rbp, [rsp-47h]
0x18002c769  sub     rsp, 100h
0x18002c770  mov     rdi, [rcx+110h]
0x18002c777  mov     rbx, rcx
0x18002c77a  mov     eax, [rdi+48h]
0x18002c77d  test    eax, eax
0x18002c77f  jns     loc_18002C8F8
0x18002c785  add     rdi, 50h ; 'P'
0x18002c789  cmp     eax, [rdi+8]
0x18002c78c  jnz     loc_18002C8F8
0x18002c792  test    rdi, rdi
0x18002c795  jz      loc_18002C8F8
0x18002c79b  call    ?zInternalStop@?$ActivityBase@VServiceHostLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18002c7a0  call    ?Provider@ServiceHostLogging@@SAPEBU_tlgProvider_t@@XZ; ServiceHostLogging::Provider(void)
0x18002c7a5  mov     r9, rax
0x18002c7a8  mov     ecx, [rax]
0x18002c7aa  cmp     ecx, 5
0x18002c7ad  jbe     loc_18002C973
0x18002c7b3  mov     rdx, 400000000000h
0x18002c7bd  mov     rcx, rax
0x18002c7c0  call    _tlgKeywordOn
0x18002c7c5  test    al, al
0x18002c7c7  jz      loc_18002C973
0x18002c7cd  mov     rax, [rdi+70h]
0x18002c7d1  lea     rdx, byte_18003D6AD
0x18002c7d8  mov     rcx, [rdi+78h]
0x18002c7dc  mov     r8, [rbx+110h]
0x18002c7e3  mov     [rbp+57h+var_60], rax
0x18002c7e7  add     r8, 8
0x18002c7eb  mov     eax, [rdi+68h]
0x18002c7ee  mov     [rbp+57h+arg_0], eax
0x18002c7f1  mov     rax, [rdi+60h]
0x18002c7f5  mov     [rbp+57h+var_58], rax
0x18002c7f9  mov     rax, [rdi+58h]
0x18002c7fd  mov     [rbp+57h+var_50], rax
0x18002c801  mov     eax, [rdi+50h]
0x18002c804  mov     [rbp+57h+arg_8], eax
0x18002c807  mov     rax, [rdi+48h]
0x18002c80b  mov     [rbp+57h+var_48], rax
0x18002c80f  mov     eax, [rdi+20h]
0x18002c812  mov     dword ptr [rbp+57h+arg_10], eax
0x18002c815  mov     rax, [rdi+18h]
0x18002c819  mov     [rbp+57h+var_40], rax
0x18002c81d  mov     eax, [rdi]
0x18002c81f  mov     [rbp+57h+arg_18], eax
0x18002c822  mov     rax, [rdi+80h]
0x18002c829  mov     [rbp+57h+var_38], rax
0x18002c82d  mov     eax, [rdi+40h]
0x18002c830  mov     [rbp+57h+var_70], eax
0x18002c833  mov     rax, [rdi+38h]
0x18002c837  mov     [rbp+57h+var_30], rax
0x18002c83b  mov     eax, [rdi+8]
0x18002c83e  mov     [rbp+57h+var_6C], eax
0x18002c841  mov     eax, 1000000h
0x18002c846  mov     [rbp+57h+var_28], rax
0x18002c84a  mov     [rbp+57h+var_20], rax
0x18002c84e  lea     rax, [rbp+57h+var_68]
0x18002c852  mov     [rsp+110h+var_78], rax
0x18002c85a  lea     rax, [rbp+57h+var_60]
0x18002c85e  mov     [rsp+110h+var_80], rax
0x18002c866  lea     rax, [rbp+57h+arg_0]
0x18002c86a  mov     [rsp+110h+var_88], rax
0x18002c872  lea     rax, [rbp+57h+var_58]
0x18002c876  mov     [rsp+110h+var_90], rax
0x18002c87e  lea     rax, [rbp+57h+var_50]
0x18002c882  mov     [rsp+110h+var_98], rax
0x18002c887  lea     rax, [rbp+57h+arg_8]
0x18002c88b  mov     [rsp+110h+var_A0], rax
0x18002c890  lea     rax, [rbp+57h+var_48]
0x18002c894  mov     [rsp+110h+var_A8], rax
0x18002c899  lea     rax, [rbp+57h+arg_10]
0x18002c89d  mov     [rsp+110h+var_B0], rax
0x18002c8a2  lea     rax, [rbp+57h+var_40]
0x18002c8a6  mov     [rsp+110h+var_B8], rax
0x18002c8ab  lea     rax, [rbp+57h+arg_18]
0x18002c8af  mov     [rsp+110h+var_C0], rax
0x18002c8b4  lea     rax, [rbp+57h+var_38]
0x18002c8b8  mov     [rsp+110h+var_C8], rax
0x18002c8bd  lea     rax, [rbp+57h+var_70]
0x18002c8c1  mov     [rsp+110h+var_D0], rax
0x18002c8c6  lea     rax, [rbp+57h+var_30]
0x18002c8ca  mov     [rsp+110h+var_D8], rax
0x18002c8cf  lea     rax, [rbp+57h+var_6C]
0x18002c8d3  mov     [rsp+110h+var_E0], rax
0x18002c8d8  lea     rax, [rbp+57h+var_28]
0x18002c8dc  mov     [rsp+110h+var_E8], rax
0x18002c8e1  lea     rax, [rbp+57h+var_20]
0x18002c8e5  mov     [rbp+57h+var_68], rcx
0x18002c8e9  mov     rcx, r9
0x18002c8ec  mov     [rsp+110h+var_F0], rax
0x18002c8f1  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18002c8f6  jmp     short loc_18002C973
0x18002c8f8  call    ?zInternalStop@?$ActivityBase@VServiceHostLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18002c8fd  call    ?Provider@ServiceHostLogging@@SAPEBU_tlgProvider_t@@XZ; ServiceHostLogging::Provider(void)
0x18002c902  mov     rdi, rax
0x18002c905  mov     ecx, [rax]
0x18002c907  cmp     ecx, 5
0x18002c90a  jbe     short loc_18002C973
0x18002c90c  mov     rdx, 400000000000h
0x18002c916  mov     rcx, rax
0x18002c919  call    _tlgKeywordOn
0x18002c91e  test    al, al
0x18002c920  jz      short loc_18002C973
0x18002c922  call    cs:__imp_GetCurrentThreadId
0x18002c928  mov     r8, [rbx+110h]
0x18002c92f  lea     rdx, unk_18003D658
0x18002c936  mov     [rbp+57h+arg_0], eax
0x18002c939  xor     r9d, r9d
0x18002c93c  mov     rcx, rdi
0x18002c93f  mov     eax, [r8+48h]
0x18002c943  add     r8, 8
0x18002c947  mov     [rbp+57h+arg_8], eax
0x18002c94a  mov     eax, 1000000h
0x18002c94f  mov     [rbp+57h+arg_10], rax
0x18002c953  lea     rax, [rbp+57h+arg_0]
0x18002c957  mov     [rsp+110h+var_E0], rax
0x18002c95c  lea     rax, [rbp+57h+arg_8]
0x18002c960  mov     [rsp+110h+var_E8], rax
0x18002c965  lea     rax, [rbp+57h+arg_10]
0x18002c969  mov     [rsp+110h+var_F0], rax
0x18002c96e  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18002c973  mov     rcx, rbx
0x18002c976  add     rsp, 100h
0x18002c97d  pop     rdi
0x18002c97e  pop     rbx
0x18002c97f  pop     rbp
0x18002c980  jmp     ?IgnoreCurrentThread@?$ActivityBase@VWnsCPTracelogger@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WnsCPTracelogger,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
