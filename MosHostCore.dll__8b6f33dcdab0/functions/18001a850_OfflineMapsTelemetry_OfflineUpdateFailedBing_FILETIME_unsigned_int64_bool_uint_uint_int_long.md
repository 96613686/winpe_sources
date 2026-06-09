# OfflineMapsTelemetry::OfflineUpdateFailedBing_(_FILETIME,unsigned __int64,bool,uint,uint,int,long)

- ea: `0x18001a850`
- end: `0x18001a961`
- name: `?OfflineUpdateFailedBing_@OfflineMapsTelemetry@@QEAAXU_FILETIME@@_K_NIIHJ@Z`
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
- `0x18001a850`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001a87c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001a87c`

## pseudocode

```c
void __fastcall OfflineMapsTelemetry::OfflineUpdateFailedBing_(
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
        (__int64)&dword_18002CC3C,
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
0x18001a850  push    rbp
0x18001a852  push    rbx
0x18001a853  push    rsi
0x18001a854  push    rdi
0x18001a855  push    r14
0x18001a857  lea     rbp, [rsp-17h]
0x18001a85c  sub     rsp, 0C0h
0x18001a863  mov     r14, rcx
0x18001a866  movzx   edi, r9b
0x18001a86a  lea     rcx, [rbp+37h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18001a86e  mov     qword ptr [rbp+37h+SystemTimeAsFileTime.dwLowDateTime], 0
0x18001a876  mov     rsi, r8
0x18001a879  mov     rbx, rdx
0x18001a87c  call    cs:__imp_GetSystemTimeAsFileTime
0x18001a882  call    ?Provider@OfflineMapsTraceLogging@@SAPEBU_tlgProvider_t@@XZ; OfflineMapsTraceLogging::Provider(void)
0x18001a887  mov     r10, rax
0x18001a88a  mov     edx, [rax]
0x18001a88c  cmp     edx, 5
0x18001a88f  jbe     loc_18001A953
0x18001a895  mov     rdx, 400000000000h
0x18001a89f  mov     rcx, rax
0x18001a8a2  call    _tlgKeywordOn
0x18001a8a7  test    al, al
0x18001a8a9  jz      loc_18001A953
0x18001a8af  mov     rax, qword ptr [rbp+37h+SystemTimeAsFileTime.dwLowDateTime]
0x18001a8b3  lea     rdx, dword_18002CC3C
0x18001a8ba  mov     ecx, [rbp+37h+arg_38]
0x18001a8bd  mov     [rbp+37h+var_48], rax
0x18001a8c1  mov     eax, [rbp+37h+arg_30]
0x18001a8c4  mov     [rbp+37h+var_6C], eax
0x18001a8c7  lea     rax, [r14+18h]
0x18001a8cb  mov     [rbp+37h+var_40], rax
0x18001a8cf  mov     eax, [rbp+37h+arg_28]
0x18001a8d2  mov     [rbp+37h+var_68], eax
0x18001a8d5  mov     eax, [rbp+37h+arg_20]
0x18001a8d8  mov     [rbp+37h+var_64], eax
0x18001a8db  lea     rax, [rbp+37h+var_50]
0x18001a8df  mov     [rsp+0E0h+var_78], rax
0x18001a8e4  lea     rax, [rbp+37h+var_70]
0x18001a8e8  mov     [rsp+0E0h+var_80], rax
0x18001a8ed  lea     rax, [rbp+37h+var_48]
0x18001a8f1  mov     [rsp+0E0h+var_88], rax
0x18001a8f6  lea     rax, [rbp+37h+var_6C]
0x18001a8fa  mov     [rsp+0E0h+var_90], rax
0x18001a8ff  lea     rax, [rbp+37h+var_40]
0x18001a903  mov     [rsp+0E0h+var_98], rax
0x18001a908  lea     rax, [rbp+37h+var_68]
0x18001a90c  mov     [rsp+0E0h+var_A0], rax
0x18001a911  lea     rax, [rbp+37h+var_64]
0x18001a915  mov     [rsp+0E0h+var_A8], rax
0x18001a91a  lea     rax, [rbp+37h+var_60]
0x18001a91e  mov     [rsp+0E0h+var_B0], rax
0x18001a923  lea     rax, [rbp+37h+var_38]
0x18001a927  mov     [rsp+0E0h+var_B8], rax
0x18001a92c  lea     rax, [rbp+37h+var_30]
0x18001a930  mov     [rbp+37h+var_70], ecx
0x18001a933  mov     rcx, r10
0x18001a936  mov     [rsp+0E0h+var_C0], rax
0x18001a93b  mov     [rbp+37h+var_50], 2000000h
0x18001a943  mov     [rbp+37h+var_60], edi
0x18001a946  mov     [rbp+37h+var_38], rsi
0x18001a94a  mov     [rbp+37h+var_30], rbx
0x18001a94e  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U2@U2@U?$_tlgWrapperByRef@$0BA@@@U2@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@44AEBU?$_tlgWrapperByRef@$0BA@@@4343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x18001a953  add     rsp, 0C0h
0x18001a95a  pop     r14
0x18001a95c  pop     rdi
0x18001a95d  pop     rsi
0x18001a95e  pop     rbx
0x18001a95f  pop     rbp
0x18001a960  retn
```
