# OfflineMapsTelemetry::OfflineUpdateComplete_(_FILETIME,unsigned __int64,bool,uint,uint,int)

- ea: `0x18001a748`
- end: `0x18001a84a`
- name: `?OfflineUpdateComplete_@OfflineMapsTelemetry@@QEAAXU_FILETIME@@_K_NIIH@Z`
- size: `258`
- prototype: `void __fastcall(OfflineMapsTelemetry *__hidden this, struct _FILETIME, unsigned __int64, bool, unsigned int, unsigned int, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180017220`

## callees

- `0x18000186c`
- `0x180002a68`
- `0x180009e6c`
- `0x18001a748`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001a774`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001a774`

## pseudocode

```c
void __fastcall OfflineMapsTelemetry::OfflineUpdateComplete_(
        OfflineMapsTelemetry *this,
        struct _FILETIME a2,
        __int64 a3,
        unsigned __int8 a4,
        unsigned int a5,
        unsigned int a6,
        int a7)
{
  int v8; // edi
  const struct _tlgProvider_t *v11; // rax
  __int64 v12; // r8
  __int64 v13; // r9
  __int64 v14; // r10
  int v15; // [rsp+70h] [rbp-21h] BYREF
  unsigned int v16; // [rsp+74h] [rbp-1Dh] BYREF
  unsigned int v17; // [rsp+78h] [rbp-19h] BYREF
  int v18; // [rsp+7Ch] [rbp-15h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+80h] [rbp-11h] BYREF
  __int64 v20; // [rsp+88h] [rbp-9h] BYREF
  struct _FILETIME v21; // [rsp+90h] [rbp-1h] BYREF
  __int64 v22; // [rsp+98h] [rbp+7h] BYREF
  __int64 v23; // [rsp+A0h] [rbp+Fh] BYREF
  struct _FILETIME v24; // [rsp+A8h] [rbp+17h] BYREF

  v8 = a4;
  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v11 = OfflineMapsTraceLogging::Provider();
  if ( *(_DWORD *)v11 > 5u )
  {
    if ( (unsigned __int8)tlgKeywordOn(v11, 0x400000000000LL) )
    {
      v15 = a7;
      v22 = (__int64)this + 24;
      v16 = a6;
      v17 = a5;
      v21 = SystemTimeAsFileTime;
      v20 = 0x2000000;
      v18 = v8;
      v23 = a3;
      v24 = a2;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
        v14,
        (__int64)byte_18002CE19,
        v12,
        v13,
        (__int64)&v24,
        (__int64)&v23,
        (__int64)&v18,
        (__int64)&v17,
        (__int64)&v16,
        &v22,
        (__int64)&v15,
        (__int64)&v21,
        (__int64)&v20);
    }
  }
}

```

## disassembly

```asm
0x18001a748  push    rbp
0x18001a74a  push    rbx
0x18001a74b  push    rsi
0x18001a74c  push    rdi
0x18001a74d  push    r14
0x18001a74f  lea     rbp, [rsp-1Fh]
0x18001a754  sub     rsp, 0B0h
0x18001a75b  mov     r14, rcx
0x18001a75e  movzx   edi, r9b
0x18001a762  lea     rcx, [rbp+3Fh+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18001a766  mov     qword ptr [rbp+3Fh+SystemTimeAsFileTime.dwLowDateTime], 0
0x18001a76e  mov     rsi, r8
0x18001a771  mov     rbx, rdx
0x18001a774  call    cs:__imp_GetSystemTimeAsFileTime
0x18001a77a  call    ?Provider@OfflineMapsTraceLogging@@SAPEBU_tlgProvider_t@@XZ; OfflineMapsTraceLogging::Provider(void)
0x18001a77f  mov     r10, rax
0x18001a782  mov     edx, [rax]
0x18001a784  cmp     edx, 5
0x18001a787  jbe     loc_18001A83C
0x18001a78d  mov     rdx, 400000000000h
0x18001a797  mov     rcx, rax
0x18001a79a  call    _tlgKeywordOn
0x18001a79f  test    al, al
0x18001a7a1  jz      loc_18001A83C
0x18001a7a7  mov     rcx, qword ptr [rbp+3Fh+SystemTimeAsFileTime.dwLowDateTime]
0x18001a7ab  lea     rdx, byte_18002CE19
0x18001a7b2  mov     eax, [rbp+3Fh+arg_30]
0x18001a7b5  mov     [rbp+3Fh+var_60], eax
0x18001a7b8  lea     rax, [r14+18h]
0x18001a7bc  mov     [rbp+3Fh+var_38], rax
0x18001a7c0  mov     eax, [rbp+3Fh+arg_28]
0x18001a7c3  mov     [rbp+3Fh+var_5C], eax
0x18001a7c6  mov     eax, [rbp+3Fh+arg_20]
0x18001a7c9  mov     [rbp+3Fh+var_58], eax
0x18001a7cc  lea     rax, [rbp+3Fh+var_48]
0x18001a7d0  mov     [rsp+0D0h+var_70], rax
0x18001a7d5  lea     rax, [rbp+3Fh+var_40]
0x18001a7d9  mov     [rsp+0D0h+var_78], rax
0x18001a7de  lea     rax, [rbp+3Fh+var_60]
0x18001a7e2  mov     [rsp+0D0h+var_80], rax
0x18001a7e7  lea     rax, [rbp+3Fh+var_38]
0x18001a7eb  mov     [rsp+0D0h+var_88], rax
0x18001a7f0  lea     rax, [rbp+3Fh+var_5C]
0x18001a7f4  mov     [rsp+0D0h+var_90], rax
0x18001a7f9  lea     rax, [rbp+3Fh+var_58]
0x18001a7fd  mov     [rsp+0D0h+var_98], rax
0x18001a802  lea     rax, [rbp+3Fh+var_54]
0x18001a806  mov     [rsp+0D0h+var_A0], rax
0x18001a80b  lea     rax, [rbp+3Fh+var_30]
0x18001a80f  mov     [rsp+0D0h+var_A8], rax
0x18001a814  lea     rax, [rbp+3Fh+var_28]
0x18001a818  mov     [rbp+3Fh+var_40], rcx
0x18001a81c  mov     rcx, r10
0x18001a81f  mov     [rsp+0D0h+var_B0], rax
0x18001a824  mov     [rbp+3Fh+var_48], 2000000h
0x18001a82c  mov     [rbp+3Fh+var_54], edi
0x18001a82f  mov     [rbp+3Fh+var_30], rsi
0x18001a833  mov     [rbp+3Fh+var_28], rbx
0x18001a837  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U2@U2@U?$_tlgWrapperByRef@$0BA@@@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@44AEBU?$_tlgWrapperByRef@$0BA@@@433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)
0x18001a83c  add     rsp, 0B0h
0x18001a843  pop     r14
0x18001a845  pop     rdi
0x18001a846  pop     rsi
0x18001a847  pop     rbx
0x18001a848  pop     rbp
0x18001a849  retn
```
