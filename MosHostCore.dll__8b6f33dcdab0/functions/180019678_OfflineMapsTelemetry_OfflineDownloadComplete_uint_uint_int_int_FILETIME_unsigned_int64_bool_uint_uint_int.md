# OfflineMapsTelemetry::OfflineDownloadComplete_(uint,uint,int,int,_FILETIME,unsigned __int64,bool,uint,uint,int)

- ea: `0x180019678`
- end: `0x1800197bf`
- name: `?OfflineDownloadComplete_@OfflineMapsTelemetry@@QEAAXIIHHU_FILETIME@@_K_NIIH@Z`
- size: `327`
- prototype: `void __fastcall(OfflineMapsTelemetry *__hidden this, unsigned int, unsigned int, int, int, struct _FILETIME, unsigned __int64, bool, unsigned int, unsigned int, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180017220`

## callees

- `0x18000186c`
- `0x180001ff0`
- `0x180009e6c`
- `0x180019678`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800196a2`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800196a2`

## pseudocode

```c
void __fastcall OfflineMapsTelemetry::OfflineDownloadComplete_(
        OfflineMapsTelemetry *this,
        int a2,
        int a3,
        int a4,
        int a5,
        struct _FILETIME a6,
        unsigned __int64 a7,
        bool a8,
        unsigned int a9,
        unsigned int a10,
        int a11)
{
  const struct _tlgProvider_t *v15; // rax
  __int64 v16; // r8
  __int64 v17; // r9
  __int64 v18; // r11
  int v19; // [rsp+90h] [rbp-49h] BYREF
  unsigned int v20; // [rsp+94h] [rbp-45h] BYREF
  unsigned int v21; // [rsp+98h] [rbp-41h] BYREF
  BOOL v22; // [rsp+9Ch] [rbp-3Dh] BYREF
  int v23; // [rsp+A0h] [rbp-39h] BYREF
  int v24; // [rsp+A4h] [rbp-35h] BYREF
  int v25; // [rsp+A8h] [rbp-31h] BYREF
  int v26; // [rsp+ACh] [rbp-2Dh] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+B0h] [rbp-29h] BYREF
  __int64 v28; // [rsp+B8h] [rbp-21h] BYREF
  struct _FILETIME v29; // [rsp+C0h] [rbp-19h] BYREF
  __int64 v30; // [rsp+C8h] [rbp-11h] BYREF
  unsigned __int64 v31; // [rsp+D0h] [rbp-9h] BYREF
  struct _FILETIME v32; // [rsp+D8h] [rbp-1h] BYREF

  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v15 = OfflineMapsTraceLogging::Provider();
  if ( *(_DWORD *)v15 > 5u )
  {
    if ( (unsigned __int8)tlgKeywordOn(v15, 0x400000000000LL) )
    {
      v19 = a11;
      v30 = (__int64)this + 24;
      v20 = a10;
      v21 = a9;
      v22 = a8;
      v31 = a7;
      v32 = a6;
      v23 = a5;
      v29 = SystemTimeAsFileTime;
      v28 = 50331648;
      v24 = a4;
      v25 = a3;
      v26 = a2;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
        v18,
        (__int64)&byte_18002D757,
        v16,
        v17,
        (__int64)&v26,
        (__int64)&v25,
        (__int64)&v24,
        (__int64)&v23,
        (__int64)&v32,
        (__int64)&v31,
        (__int64)&v22,
        (__int64)&v21,
        (__int64)&v20,
        &v30,
        (__int64)&v19,
        (__int64)&v29,
        (__int64)&v28);
    }
  }
}

```

## disassembly

```asm
0x180019678  push    rbp
0x18001967a  push    rbx
0x18001967b  push    rsi
0x18001967c  push    rdi
0x18001967d  push    r14
0x18001967f  lea     rbp, [rsp-7]
0x180019684  sub     rsp, 0E0h
0x18001968b  mov     r14, rcx
0x18001968e  mov     qword ptr [rbp+27h+SystemTimeAsFileTime.dwLowDateTime], 0
0x180019696  lea     rcx, [rbp+27h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18001969a  mov     ebx, r9d
0x18001969d  mov     edi, r8d
0x1800196a0  mov     esi, edx
0x1800196a2  call    cs:__imp_GetSystemTimeAsFileTime
0x1800196a8  call    ?Provider@OfflineMapsTraceLogging@@SAPEBU_tlgProvider_t@@XZ; OfflineMapsTraceLogging::Provider(void)
0x1800196ad  mov     r11, rax
0x1800196b0  mov     r10d, [rax]
0x1800196b3  cmp     r10d, 5
0x1800196b7  jbe     loc_1800197B1
0x1800196bd  mov     rdx, 400000000000h
0x1800196c7  mov     rcx, rax
0x1800196ca  call    _tlgKeywordOn
0x1800196cf  test    al, al
0x1800196d1  jz      loc_1800197B1
0x1800196d7  mov     eax, [rbp+27h+arg_50]
0x1800196dd  lea     rdx, byte_18002D757
0x1800196e4  mov     rcx, qword ptr [rbp+27h+SystemTimeAsFileTime.dwLowDateTime]
0x1800196e8  mov     [rbp+27h+var_70], eax
0x1800196eb  lea     rax, [r14+18h]
0x1800196ef  mov     [rbp+27h+var_38], rax
0x1800196f3  mov     eax, [rbp+27h+arg_48]
0x1800196f6  mov     [rbp+27h+var_6C], eax
0x1800196f9  mov     eax, [rbp+27h+arg_40]
0x1800196fc  mov     [rbp+27h+var_68], eax
0x1800196ff  movzx   eax, [rbp+27h+arg_38]
0x180019703  mov     [rbp+27h+var_64], eax
0x180019706  mov     rax, [rbp+27h+arg_30]
0x18001970a  mov     [rbp+27h+var_30], rax
0x18001970e  mov     rax, qword ptr [rbp+27h+arg_28.dwLowDateTime]
0x180019712  mov     [rbp+27h+var_28], rax
0x180019716  mov     eax, [rbp+27h+arg_20]
0x180019719  mov     [rbp+27h+var_60], eax
0x18001971c  lea     rax, [rbp+27h+var_48]
0x180019720  mov     [rsp+100h+var_80], rax
0x180019728  lea     rax, [rbp+27h+var_40]
0x18001972c  mov     [rsp+100h+var_88], rax
0x180019731  lea     rax, [rbp+27h+var_70]
0x180019735  mov     [rsp+100h+var_90], rax
0x18001973a  lea     rax, [rbp+27h+var_38]
0x18001973e  mov     [rsp+100h+var_98], rax
0x180019743  lea     rax, [rbp+27h+var_6C]
0x180019747  mov     [rsp+100h+var_A0], rax
0x18001974c  lea     rax, [rbp+27h+var_68]
0x180019750  mov     [rsp+100h+var_A8], rax
0x180019755  lea     rax, [rbp+27h+var_64]
0x180019759  mov     [rsp+100h+var_B0], rax
0x18001975e  lea     rax, [rbp+27h+var_30]
0x180019762  mov     [rsp+100h+var_B8], rax
0x180019767  lea     rax, [rbp+27h+var_28]
0x18001976b  mov     [rsp+100h+var_C0], rax
0x180019770  lea     rax, [rbp+27h+var_60]
0x180019774  mov     [rsp+100h+var_C8], rax
0x180019779  lea     rax, [rbp+27h+var_5C]
0x18001977d  mov     [rsp+100h+var_D0], rax
0x180019782  lea     rax, [rbp+27h+var_58]
0x180019786  mov     [rsp+100h+var_D8], rax
0x18001978b  lea     rax, [rbp+27h+var_54]
0x18001978f  mov     [rbp+27h+var_40], rcx
0x180019793  mov     rcx, r11
0x180019796  mov     [rsp+100h+var_E0], rax
0x18001979b  mov     [rbp+27h+var_48], 3000000h
0x1800197a3  mov     [rbp+27h+var_5C], ebx
0x1800197a6  mov     [rbp+27h+var_58], edi
0x1800197a9  mov     [rbp+27h+var_54], esi
0x1800197ac  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U?$_tlgWrapperByVal@$07@@U2@U1@U1@U1@U?$_tlgWrapperByRef@$0BA@@@U1@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@333AEBU?$_tlgWrapperByVal@$07@@4333AEBU?$_tlgWrapperByRef@$0BA@@@344@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)
0x1800197b1  add     rsp, 0E0h
0x1800197b8  pop     r14
0x1800197ba  pop     rdi
0x1800197bb  pop     rsi
0x1800197bc  pop     rbx
0x1800197bd  pop     rbp
0x1800197be  retn
```
