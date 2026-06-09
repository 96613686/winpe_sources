# OfflineMapsTelemetry::OfflineUpdateFailed_(_FILETIME,unsigned __int64,bool,uint,uint,int,long)

- ea: `0x18001aa80`
- end: `0x18001ab91`
- name: `?OfflineUpdateFailed_@OfflineMapsTelemetry@@QEAAXU_FILETIME@@_K_NIIHJ@Z`
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
- `0x18001aa80`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001aaac`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001aaac`

## pseudocode

```c
void __fastcall OfflineMapsTelemetry::OfflineUpdateFailed_(
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
        (__int64)byte_18002CB51,
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
0x18001aa80  push    rbp
0x18001aa82  push    rbx
0x18001aa83  push    rsi
0x18001aa84  push    rdi
0x18001aa85  push    r14
0x18001aa87  lea     rbp, [rsp-17h]
0x18001aa8c  sub     rsp, 0C0h
0x18001aa93  mov     r14, rcx
0x18001aa96  movzx   edi, r9b
0x18001aa9a  lea     rcx, [rbp+37h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18001aa9e  mov     qword ptr [rbp+37h+SystemTimeAsFileTime.dwLowDateTime], 0
0x18001aaa6  mov     rsi, r8
0x18001aaa9  mov     rbx, rdx
0x18001aaac  call    cs:__imp_GetSystemTimeAsFileTime
0x18001aab2  call    ?Provider@OfflineMapsTraceLogging@@SAPEBU_tlgProvider_t@@XZ; OfflineMapsTraceLogging::Provider(void)
0x18001aab7  mov     r10, rax
0x18001aaba  mov     edx, [rax]
0x18001aabc  cmp     edx, 5
0x18001aabf  jbe     loc_18001AB83
0x18001aac5  mov     rdx, 400000000000h
0x18001aacf  mov     rcx, rax
0x18001aad2  call    _tlgKeywordOn
0x18001aad7  test    al, al
0x18001aad9  jz      loc_18001AB83
0x18001aadf  mov     rax, qword ptr [rbp+37h+SystemTimeAsFileTime.dwLowDateTime]
0x18001aae3  lea     rdx, byte_18002CB51
0x18001aaea  mov     ecx, [rbp+37h+arg_38]
0x18001aaed  mov     [rbp+37h+var_48], rax
0x18001aaf1  mov     eax, [rbp+37h+arg_30]
0x18001aaf4  mov     [rbp+37h+var_6C], eax
0x18001aaf7  lea     rax, [r14+18h]
0x18001aafb  mov     [rbp+37h+var_40], rax
0x18001aaff  mov     eax, [rbp+37h+arg_28]
0x18001ab02  mov     [rbp+37h+var_68], eax
0x18001ab05  mov     eax, [rbp+37h+arg_20]
0x18001ab08  mov     [rbp+37h+var_64], eax
0x18001ab0b  lea     rax, [rbp+37h+var_50]
0x18001ab0f  mov     [rsp+0E0h+var_78], rax
0x18001ab14  lea     rax, [rbp+37h+var_70]
0x18001ab18  mov     [rsp+0E0h+var_80], rax
0x18001ab1d  lea     rax, [rbp+37h+var_48]
0x18001ab21  mov     [rsp+0E0h+var_88], rax
0x18001ab26  lea     rax, [rbp+37h+var_6C]
0x18001ab2a  mov     [rsp+0E0h+var_90], rax
0x18001ab2f  lea     rax, [rbp+37h+var_40]
0x18001ab33  mov     [rsp+0E0h+var_98], rax
0x18001ab38  lea     rax, [rbp+37h+var_68]
0x18001ab3c  mov     [rsp+0E0h+var_A0], rax
0x18001ab41  lea     rax, [rbp+37h+var_64]
0x18001ab45  mov     [rsp+0E0h+var_A8], rax
0x18001ab4a  lea     rax, [rbp+37h+var_60]
0x18001ab4e  mov     [rsp+0E0h+var_B0], rax
0x18001ab53  lea     rax, [rbp+37h+var_38]
0x18001ab57  mov     [rsp+0E0h+var_B8], rax
0x18001ab5c  lea     rax, [rbp+37h+var_30]
0x18001ab60  mov     [rbp+37h+var_70], ecx
0x18001ab63  mov     rcx, r10
0x18001ab66  mov     [rsp+0E0h+var_C0], rax
0x18001ab6b  mov     [rbp+37h+var_50], 2000000h
0x18001ab73  mov     [rbp+37h+var_60], edi
0x18001ab76  mov     [rbp+37h+var_38], rsi
0x18001ab7a  mov     [rbp+37h+var_30], rbx
0x18001ab7e  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U2@U2@U?$_tlgWrapperByRef@$0BA@@@U2@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@44AEBU?$_tlgWrapperByRef@$0BA@@@4343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x18001ab83  add     rsp, 0C0h
0x18001ab8a  pop     r14
0x18001ab8c  pop     rdi
0x18001ab8d  pop     rsi
0x18001ab8e  pop     rbx
0x18001ab8f  pop     rbp
0x18001ab90  retn
```
