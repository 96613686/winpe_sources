# OfflineMapsTelemetry::OfflineMapCheckForUpdatesFailed_(uint,uint,int,int,_FILETIME,unsigned __int64,bool,uint,uint,long)

- ea: `0x180019bf4`
- end: `0x180019d15`
- name: `?OfflineMapCheckForUpdatesFailed_@OfflineMapsTelemetry@@QEAAXIIHHU_FILETIME@@_K_NIIJ@Z`
- size: `289`
- prototype: `void __fastcall(OfflineMapsTelemetry *__hidden this, unsigned int, unsigned int, int, int, struct _FILETIME, unsigned __int64, bool, unsigned int, unsigned int, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x1800117f0`

## callees

- `0x18000186c`
- `0x180001d54`
- `0x180009e6c`
- `0x180019bf4`

## pseudocode

```c
void __fastcall OfflineMapsTelemetry::OfflineMapCheckForUpdatesFailed_(
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
  int v19; // [rsp+80h] [rbp-39h] BYREF
  unsigned int v20; // [rsp+84h] [rbp-35h] BYREF
  unsigned int v21; // [rsp+88h] [rbp-31h] BYREF
  BOOL v22; // [rsp+8Ch] [rbp-2Dh] BYREF
  int v23; // [rsp+90h] [rbp-29h] BYREF
  int v24; // [rsp+94h] [rbp-25h] BYREF
  int v25; // [rsp+98h] [rbp-21h] BYREF
  int v26; // [rsp+9Ch] [rbp-1Dh] BYREF
  __int64 v27; // [rsp+A0h] [rbp-19h] BYREF
  __int64 v28; // [rsp+A8h] [rbp-11h] BYREF
  unsigned __int64 v29; // [rsp+B0h] [rbp-9h] BYREF
  struct _FILETIME v30; // [rsp+B8h] [rbp-1h] BYREF

  v15 = OfflineMapsTraceLogging::Provider();
  if ( *(_DWORD *)v15 > 5u )
  {
    if ( (unsigned __int8)tlgKeywordOn(v15, 0x400000000000LL) )
    {
      v28 = (__int64)this + 24;
      v20 = a10;
      v21 = a9;
      v22 = a8;
      v29 = a7;
      v30 = a6;
      v23 = a5;
      v19 = a11;
      v27 = 0x2000000;
      v24 = a4;
      v25 = a3;
      v26 = a2;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        v18,
        (__int64)&word_18002C7E6,
        v16,
        v17,
        (__int64)&v26,
        (__int64)&v25,
        (__int64)&v24,
        (__int64)&v23,
        (__int64)&v30,
        (__int64)&v29,
        (__int64)&v22,
        (__int64)&v21,
        (__int64)&v20,
        &v28,
        (__int64)&v19,
        (__int64)&v27);
    }
  }
}

```

## disassembly

```asm
0x180019bf4  push    rbp
0x180019bf6  push    rbx
0x180019bf7  push    rsi
0x180019bf8  push    rdi
0x180019bf9  push    r14
0x180019bfb  lea     rbp, [rsp-7]
0x180019c00  sub     rsp, 0C0h
0x180019c07  mov     ebx, r9d
0x180019c0a  mov     edi, r8d
0x180019c0d  mov     esi, edx
0x180019c0f  mov     r14, rcx
0x180019c12  call    ?Provider@OfflineMapsTraceLogging@@SAPEBU_tlgProvider_t@@XZ; OfflineMapsTraceLogging::Provider(void)
0x180019c17  mov     r11, rax
0x180019c1a  mov     r10d, [rax]
0x180019c1d  cmp     r10d, 5
0x180019c21  jbe     loc_180019D07
0x180019c27  mov     rdx, 400000000000h
0x180019c31  mov     rcx, rax
0x180019c34  call    _tlgKeywordOn
0x180019c39  test    al, al
0x180019c3b  jz      loc_180019D07
0x180019c41  mov     ecx, [rbp+27h+arg_50]
0x180019c47  lea     rax, [r14+18h]
0x180019c4b  mov     [rbp+27h+var_38], rax
0x180019c4f  lea     rdx, word_18002C7E6
0x180019c56  mov     eax, [rbp+27h+arg_48]
0x180019c59  mov     [rbp+27h+var_5C], eax
0x180019c5c  mov     eax, [rbp+27h+arg_40]
0x180019c5f  mov     [rbp+27h+var_58], eax
0x180019c62  movzx   eax, [rbp+27h+arg_38]
0x180019c66  mov     [rbp+27h+var_54], eax
0x180019c69  mov     rax, [rbp+27h+arg_30]
0x180019c6d  mov     [rbp+27h+var_30], rax
0x180019c71  mov     rax, qword ptr [rbp+27h+arg_28.dwLowDateTime]
0x180019c75  mov     [rbp+27h+var_28], rax
0x180019c79  mov     eax, [rbp+27h+arg_20]
0x180019c7c  mov     [rbp+27h+var_50], eax
0x180019c7f  lea     rax, [rbp+27h+var_40]
0x180019c83  mov     [rsp+0E0h+var_68], rax
0x180019c88  lea     rax, [rbp+27h+var_60]
0x180019c8c  mov     [rsp+0E0h+var_70], rax
0x180019c91  lea     rax, [rbp+27h+var_38]
0x180019c95  mov     [rsp+0E0h+var_78], rax
0x180019c9a  lea     rax, [rbp+27h+var_5C]
0x180019c9e  mov     [rsp+0E0h+var_80], rax
0x180019ca3  lea     rax, [rbp+27h+var_58]
0x180019ca7  mov     [rsp+0E0h+var_88], rax
0x180019cac  lea     rax, [rbp+27h+var_54]
0x180019cb0  mov     [rsp+0E0h+var_90], rax
0x180019cb5  lea     rax, [rbp+27h+var_30]
0x180019cb9  mov     [rsp+0E0h+var_98], rax
0x180019cbe  lea     rax, [rbp+27h+var_28]
0x180019cc2  mov     [rsp+0E0h+var_A0], rax
0x180019cc7  lea     rax, [rbp+27h+var_50]
0x180019ccb  mov     [rsp+0E0h+var_A8], rax
0x180019cd0  lea     rax, [rbp+27h+var_4C]
0x180019cd4  mov     [rsp+0E0h+var_B0], rax
0x180019cd9  lea     rax, [rbp+27h+var_48]
0x180019cdd  mov     [rsp+0E0h+var_B8], rax
0x180019ce2  lea     rax, [rbp+27h+var_44]
0x180019ce6  mov     [rbp+27h+var_60], ecx
0x180019ce9  mov     rcx, r11
0x180019cec  mov     [rsp+0E0h+var_C0], rax
0x180019cf1  mov     [rbp+27h+var_40], 2000000h
0x180019cf9  mov     [rbp+27h+var_4C], ebx
0x180019cfc  mov     [rbp+27h+var_48], edi
0x180019cff  mov     [rbp+27h+var_44], esi
0x180019d02  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U?$_tlgWrapperByVal@$07@@U2@U1@U1@U1@U?$_tlgWrapperByRef@$0BA@@@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@333AEBU?$_tlgWrapperByVal@$07@@4333AEBU?$_tlgWrapperByRef@$0BA@@@34@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x180019d07  add     rsp, 0C0h
0x180019d0e  pop     r14
0x180019d10  pop     rdi
0x180019d11  pop     rsi
0x180019d12  pop     rbx
0x180019d13  pop     rbp
0x180019d14  retn
```
