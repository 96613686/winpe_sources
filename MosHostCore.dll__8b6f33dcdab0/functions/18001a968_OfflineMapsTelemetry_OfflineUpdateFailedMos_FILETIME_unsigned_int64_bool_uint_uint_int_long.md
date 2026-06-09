# OfflineMapsTelemetry::OfflineUpdateFailedMos_(_FILETIME,unsigned __int64,bool,uint,uint,int,long)

- ea: `0x18001a968`
- end: `0x18001aa79`
- name: `?OfflineUpdateFailedMos_@OfflineMapsTelemetry@@QEAAXU_FILETIME@@_K_NIIHJ@Z`
- size: `273`
- prototype: `void __fastcall(OfflineMapsTelemetry *__hidden this, struct _FILETIME, unsigned __int64, bool, unsigned int, unsigned int, int, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x180017220`

## callees

- `0x18000186c`
- `0x180002b58`
- `0x180009e6c`
- `0x18001a968`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001a994`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001a994`

## pseudocode

```c
void __fastcall OfflineMapsTelemetry::OfflineUpdateFailedMos_(
        OfflineMapsTelemetry *this,
        struct _FILETIME a2,
        __int64 a3,
        unsigned __int8 a4,
        unsigned int a5,
        unsigned int a6,
        int a7,
        int a8)
{
  int v9; // edi
  const struct _tlgProvider_t *v12; // rax
  __int64 v13; // r8
  __int64 v14; // r9
  __int64 v15; // r10
  int v16; // [rsp+70h] [rbp-39h] BYREF
  int v17; // [rsp+74h] [rbp-35h] BYREF
  unsigned int v18; // [rsp+78h] [rbp-31h] BYREF
  unsigned int v19; // [rsp+7Ch] [rbp-2Dh] BYREF
  int v20; // [rsp+80h] [rbp-29h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+88h] [rbp-21h] BYREF
  __int64 v22; // [rsp+90h] [rbp-19h] BYREF
  struct _FILETIME v23; // [rsp+98h] [rbp-11h] BYREF
  __int64 v24; // [rsp+A0h] [rbp-9h] BYREF
  __int64 v25; // [rsp+A8h] [rbp-1h] BYREF
  struct _FILETIME v26; // [rsp+B0h] [rbp+7h] BYREF

  v9 = a4;
  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v12 = OfflineMapsTraceLogging::Provider();
  if ( *(_DWORD *)v12 > 5u )
  {
    if ( (unsigned __int8)tlgKeywordOn(v12, 0x400000000000LL) )
    {
      v23 = SystemTimeAsFileTime;
      v17 = a7;
      v24 = (__int64)this + 24;
      v18 = a6;
      v19 = a5;
      v16 = a8;
      v22 = 0x2000000;
      v20 = v9;
      v25 = a3;
      v26 = a2;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        v15,
        (__int64)byte_18002CD2B,
        v13,
        v14,
        (__int64)&v26,
        (__int64)&v25,
        (__int64)&v20,
        (__int64)&v19,
        (__int64)&v18,
        &v24,
        (__int64)&v17,
        (__int64)&v23,
        (__int64)&v16,
        (__int64)&v22);
    }
  }
}

```

## disassembly

```asm
0x18001a968  push    rbp
0x18001a96a  push    rbx
0x18001a96b  push    rsi
0x18001a96c  push    rdi
0x18001a96d  push    r14
0x18001a96f  lea     rbp, [rsp-17h]
0x18001a974  sub     rsp, 0C0h
0x18001a97b  mov     r14, rcx
0x18001a97e  movzx   edi, r9b
0x18001a982  lea     rcx, [rbp+37h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18001a986  mov     qword ptr [rbp+37h+SystemTimeAsFileTime.dwLowDateTime], 0
0x18001a98e  mov     rsi, r8
0x18001a991  mov     rbx, rdx
0x18001a994  call    cs:__imp_GetSystemTimeAsFileTime
0x18001a99a  call    ?Provider@OfflineMapsTraceLogging@@SAPEBU_tlgProvider_t@@XZ; OfflineMapsTraceLogging::Provider(void)
0x18001a99f  mov     r10, rax
0x18001a9a2  mov     edx, [rax]
0x18001a9a4  cmp     edx, 5
0x18001a9a7  jbe     loc_18001AA6B
0x18001a9ad  mov     rdx, 400000000000h
0x18001a9b7  mov     rcx, rax
0x18001a9ba  call    _tlgKeywordOn
0x18001a9bf  test    al, al
0x18001a9c1  jz      loc_18001AA6B
0x18001a9c7  mov     rax, qword ptr [rbp+37h+SystemTimeAsFileTime.dwLowDateTime]
0x18001a9cb  lea     rdx, byte_18002CD2B
0x18001a9d2  mov     ecx, [rbp+37h+arg_38]
0x18001a9d5  mov     [rbp+37h+var_48], rax
0x18001a9d9  mov     eax, [rbp+37h+arg_30]
0x18001a9dc  mov     [rbp+37h+var_6C], eax
0x18001a9df  lea     rax, [r14+18h]
0x18001a9e3  mov     [rbp+37h+var_40], rax
0x18001a9e7  mov     eax, [rbp+37h+arg_28]
0x18001a9ea  mov     [rbp+37h+var_68], eax
0x18001a9ed  mov     eax, [rbp+37h+arg_20]
0x18001a9f0  mov     [rbp+37h+var_64], eax
0x18001a9f3  lea     rax, [rbp+37h+var_50]
0x18001a9f7  mov     [rsp+0E0h+var_78], rax
0x18001a9fc  lea     rax, [rbp+37h+var_70]
0x18001aa00  mov     [rsp+0E0h+var_80], rax
0x18001aa05  lea     rax, [rbp+37h+var_48]
0x18001aa09  mov     [rsp+0E0h+var_88], rax
0x18001aa0e  lea     rax, [rbp+37h+var_6C]
0x18001aa12  mov     [rsp+0E0h+var_90], rax
0x18001aa17  lea     rax, [rbp+37h+var_40]
0x18001aa1b  mov     [rsp+0E0h+var_98], rax
0x18001aa20  lea     rax, [rbp+37h+var_68]
0x18001aa24  mov     [rsp+0E0h+var_A0], rax
0x18001aa29  lea     rax, [rbp+37h+var_64]
0x18001aa2d  mov     [rsp+0E0h+var_A8], rax
0x18001aa32  lea     rax, [rbp+37h+var_60]
0x18001aa36  mov     [rsp+0E0h+var_B0], rax
0x18001aa3b  lea     rax, [rbp+37h+var_38]
0x18001aa3f  mov     [rsp+0E0h+var_B8], rax
0x18001aa44  lea     rax, [rbp+37h+var_30]
0x18001aa48  mov     [rbp+37h+var_70], ecx
0x18001aa4b  mov     rcx, r10
0x18001aa4e  mov     [rsp+0E0h+var_C0], rax
0x18001aa53  mov     [rbp+37h+var_50], 2000000h
0x18001aa5b  mov     [rbp+37h+var_60], edi
0x18001aa5e  mov     [rbp+37h+var_38], rsi
0x18001aa62  mov     [rbp+37h+var_30], rbx
0x18001aa66  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U2@U2@U?$_tlgWrapperByRef@$0BA@@@U2@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@44AEBU?$_tlgWrapperByRef@$0BA@@@4343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x18001aa6b  add     rsp, 0C0h
0x18001aa72  pop     r14
0x18001aa74  pop     rdi
0x18001aa75  pop     rsi
0x18001aa76  pop     rbx
0x18001aa77  pop     rbp
0x18001aa78  retn
```
