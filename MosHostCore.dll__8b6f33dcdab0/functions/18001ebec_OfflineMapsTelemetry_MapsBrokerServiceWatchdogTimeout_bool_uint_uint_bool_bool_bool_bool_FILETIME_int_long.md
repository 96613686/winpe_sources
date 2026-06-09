# OfflineMapsTelemetry::MapsBrokerServiceWatchdogTimeout_(bool,uint,uint,bool,bool,bool,bool,_FILETIME,int,long)

- ea: `0x18001ebec`
- end: `0x18001ed1f`
- name: `?MapsBrokerServiceWatchdogTimeout_@OfflineMapsTelemetry@@QEAAX_NII0000U_FILETIME@@HJ@Z`
- size: `307`
- prototype: `void __fastcall(OfflineMapsTelemetry *this, unsigned __int8, int, int, bool, bool, bool, bool, struct _FILETIME, int, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001ef14`

## callees

- `0x18000186c`
- `0x180002c5c`
- `0x180009e6c`
- `0x18001ebec`

## pseudocode

```c
void __fastcall OfflineMapsTelemetry::MapsBrokerServiceWatchdogTimeout_(
        OfflineMapsTelemetry *this,
        unsigned __int8 a2,
        int a3,
        int a4,
        bool a5,
        bool a6,
        bool a7,
        bool a8,
        struct _FILETIME a9,
        int a10,
        int a11)
{
  int v12; // esi
  const struct _tlgProvider_t *v15; // rax
  __int64 v16; // r8
  __int64 v17; // r9
  __int64 v18; // r11
  int v19; // [rsp+90h] [rbp-49h] BYREF
  int v20; // [rsp+94h] [rbp-45h] BYREF
  BOOL v21; // [rsp+98h] [rbp-41h] BYREF
  BOOL v22; // [rsp+9Ch] [rbp-3Dh] BYREF
  BOOL v23; // [rsp+A0h] [rbp-39h] BYREF
  BOOL v24; // [rsp+A4h] [rbp-35h] BYREF
  int v25; // [rsp+A8h] [rbp-31h] BYREF
  int v26; // [rsp+ACh] [rbp-2Dh] BYREF
  int v27; // [rsp+B0h] [rbp-29h] BYREF
  __int64 v28; // [rsp+B8h] [rbp-21h] BYREF
  struct _FILETIME v29; // [rsp+C0h] [rbp-19h] BYREF
  __int64 v30; // [rsp+C8h] [rbp-11h] BYREF
  __int64 v31[6]; // [rsp+D0h] [rbp-9h] BYREF

  v12 = a2;
  v15 = OfflineMapsTraceLogging::Provider();
  if ( *(_DWORD *)v15 > 5u )
  {
    if ( (unsigned __int8)tlgKeywordOn(v15, 0x400000000000LL) )
    {
      v29 = a9;
      v20 = a10;
      v21 = a8;
      v22 = a7;
      v23 = a6;
      v24 = a5;
      v30 = (__int64)this + 24;
      v31[0] = (__int64)this + 24;
      v19 = a11;
      v28 = 0x2000000;
      v25 = a4;
      v26 = a3;
      v27 = v12;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        v18,
        (__int64)byte_18002DDC3,
        v16,
        v17,
        (__int64)&v27,
        (__int64)&v26,
        (__int64)&v25,
        v31,
        &v30,
        (__int64)&v24,
        (__int64)&v23,
        (__int64)&v22,
        (__int64)&v21,
        (__int64)&v20,
        (__int64)&v29,
        (__int64)&v19,
        (__int64)&v28);
    }
  }
}

```

## disassembly

```asm
0x18001ebec  push    rbp
0x18001ebee  push    rbx
0x18001ebef  push    rsi
0x18001ebf0  push    rdi
0x18001ebf1  push    r14
0x18001ebf3  lea     rbp, [rsp-7]
0x18001ebf8  sub     rsp, 0E0h
0x18001ebff  mov     ebx, r9d
0x18001ec02  movzx   esi, dl
0x18001ec05  mov     edi, r8d
0x18001ec08  mov     r14, rcx
0x18001ec0b  call    ?Provider@OfflineMapsTraceLogging@@SAPEBU_tlgProvider_t@@XZ; OfflineMapsTraceLogging::Provider(void)
0x18001ec10  mov     r11, rax
0x18001ec13  mov     r10d, [rax]
0x18001ec16  cmp     r10d, 5
0x18001ec1a  jbe     loc_18001ED11
0x18001ec20  mov     rdx, 400000000000h
0x18001ec2a  mov     rcx, rax
0x18001ec2d  call    _tlgKeywordOn
0x18001ec32  test    al, al
0x18001ec34  jz      loc_18001ED11
0x18001ec3a  mov     rax, qword ptr [rbp+27h+arg_40.dwLowDateTime]
0x18001ec3e  lea     rdx, byte_18002DDC3
0x18001ec45  mov     ecx, [rbp+27h+arg_50]
0x18001ec4b  mov     [rbp+27h+var_40], rax
0x18001ec4f  mov     eax, [rbp+27h+arg_48]
0x18001ec52  mov     [rbp+27h+var_6C], eax
0x18001ec55  movzx   eax, [rbp+27h+arg_38]
0x18001ec59  mov     [rbp+27h+var_68], eax
0x18001ec5c  movzx   eax, [rbp+27h+arg_30]
0x18001ec60  mov     [rbp+27h+var_64], eax
0x18001ec63  movzx   eax, [rbp+27h+arg_28]
0x18001ec67  mov     [rbp+27h+var_60], eax
0x18001ec6a  movzx   eax, [rbp+27h+arg_20]
0x18001ec6e  mov     [rbp+27h+var_5C], eax
0x18001ec71  lea     rax, [r14+18h]
0x18001ec75  mov     [rbp+27h+var_38], rax
0x18001ec79  mov     [rbp+27h+var_30], rax
0x18001ec7d  lea     rax, [rbp+27h+var_48]
0x18001ec81  mov     [rsp+100h+var_80], rax
0x18001ec89  lea     rax, [rbp+27h+var_70]
0x18001ec8d  mov     [rsp+100h+var_88], rax
0x18001ec92  lea     rax, [rbp+27h+var_40]
0x18001ec96  mov     [rsp+100h+var_90], rax
0x18001ec9b  lea     rax, [rbp+27h+var_6C]
0x18001ec9f  mov     [rsp+100h+var_98], rax
0x18001eca4  lea     rax, [rbp+27h+var_68]
0x18001eca8  mov     [rsp+100h+var_A0], rax
0x18001ecad  lea     rax, [rbp+27h+var_64]
0x18001ecb1  mov     [rsp+100h+var_A8], rax
0x18001ecb6  lea     rax, [rbp+27h+var_60]
0x18001ecba  mov     [rsp+100h+var_B0], rax
0x18001ecbf  lea     rax, [rbp+27h+var_5C]
0x18001ecc3  mov     [rsp+100h+var_B8], rax
0x18001ecc8  lea     rax, [rbp+27h+var_38]
0x18001eccc  mov     [rsp+100h+var_C0], rax
0x18001ecd1  lea     rax, [rbp+27h+var_30]
0x18001ecd5  mov     [rsp+100h+var_C8], rax
0x18001ecda  lea     rax, [rbp+27h+var_58]
0x18001ecde  mov     [rsp+100h+var_D0], rax
0x18001ece3  lea     rax, [rbp+27h+var_54]
0x18001ece7  mov     [rsp+100h+var_D8], rax
0x18001ecec  lea     rax, [rbp+27h+var_50]
0x18001ecf0  mov     [rbp+27h+var_70], ecx
0x18001ecf3  mov     rcx, r11
0x18001ecf6  mov     [rsp+100h+var_E0], rax
0x18001ecfb  mov     [rbp+27h+var_48], 2000000h
0x18001ed03  mov     [rbp+27h+var_58], ebx
0x18001ed06  mov     [rbp+27h+var_54], edi
0x18001ed09  mov     [rbp+27h+var_50], esi
0x18001ed0c  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U?$_tlgWrapperByRef@$0BA@@@U2@U1@U1@U1@U1@U1@U?$_tlgWrapperByVal@$07@@U1@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@33AEBU?$_tlgWrapperByRef@$0BA@@@433333AEBU?$_tlgWrapperByVal@$07@@35@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x18001ed11  add     rsp, 0E0h
0x18001ed18  pop     r14
0x18001ed1a  pop     rdi
0x18001ed1b  pop     rsi
0x18001ed1c  pop     rbx
0x18001ed1d  pop     rbp
0x18001ed1e  retn
```
