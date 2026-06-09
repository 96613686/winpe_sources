# OfflineMapsTelemetry::OfflineDeleteComplete_(uint,uint,int,int,_FILETIME,unsigned __int64,bool,uint,uint)

- ea: `0x180018d68`
- end: `0x180018e77`
- name: `?OfflineDeleteComplete_@OfflineMapsTelemetry@@QEAAXIIHHU_FILETIME@@_K_NII@Z`
- size: `271`
- prototype: `void __fastcall(OfflineMapsTelemetry *__hidden this, unsigned int, unsigned int, int, int, struct _FILETIME, unsigned __int64, bool, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180017220`

## callees

- `0x18000186c`
- `0x180002140`
- `0x180009e6c`
- `0x180018d68`

## pseudocode

```c
void __fastcall OfflineMapsTelemetry::OfflineDeleteComplete_(
        OfflineMapsTelemetry *this,
        int a2,
        int a3,
        int a4,
        int a5,
        struct _FILETIME a6,
        unsigned __int64 a7,
        bool a8,
        unsigned int a9,
        unsigned int a10)
{
  const struct _tlgProvider_t *v14; // rax
  __int64 v15; // r8
  __int64 v16; // r9
  __int64 v17; // r11
  unsigned int v18; // [rsp+80h] [rbp-39h] BYREF
  unsigned int v19; // [rsp+84h] [rbp-35h] BYREF
  BOOL v20; // [rsp+88h] [rbp-31h] BYREF
  int v21; // [rsp+8Ch] [rbp-2Dh] BYREF
  int v22; // [rsp+90h] [rbp-29h] BYREF
  int v23; // [rsp+94h] [rbp-25h] BYREF
  int v24; // [rsp+98h] [rbp-21h] BYREF
  __int64 v25; // [rsp+A0h] [rbp-19h] BYREF
  __int64 v26; // [rsp+A8h] [rbp-11h] BYREF
  unsigned __int64 v27; // [rsp+B0h] [rbp-9h] BYREF
  struct _FILETIME v28; // [rsp+B8h] [rbp-1h] BYREF

  v14 = OfflineMapsTraceLogging::Provider();
  if ( *(_DWORD *)v14 > 5u )
  {
    if ( (unsigned __int8)tlgKeywordOn(v14, 0x400000000000LL) )
    {
      v18 = a10;
      v19 = a9;
      v20 = a8;
      v27 = a7;
      v28 = a6;
      v21 = a5;
      v26 = (__int64)this + 24;
      v25 = 0x2000000;
      v22 = a4;
      v23 = a3;
      v24 = a2;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<8>>(
        v17,
        (__int64)&unk_18002C4A0,
        v15,
        v16,
        (__int64)&v24,
        (__int64)&v23,
        (__int64)&v22,
        (__int64)&v21,
        (__int64)&v28,
        (__int64)&v27,
        (__int64)&v20,
        (__int64)&v19,
        (__int64)&v18,
        &v26,
        (__int64)&v25);
    }
  }
}

```

## disassembly

```asm
0x180018d68  push    rbp
0x180018d6a  push    rbx
0x180018d6b  push    rsi
0x180018d6c  push    rdi
0x180018d6d  push    r14
0x180018d6f  lea     rbp, [rsp-7]
0x180018d74  sub     rsp, 0C0h
0x180018d7b  mov     ebx, r9d
0x180018d7e  mov     edi, r8d
0x180018d81  mov     esi, edx
0x180018d83  mov     r14, rcx
0x180018d86  call    ?Provider@OfflineMapsTraceLogging@@SAPEBU_tlgProvider_t@@XZ; OfflineMapsTraceLogging::Provider(void)
0x180018d8b  mov     r11, rax
0x180018d8e  mov     r10d, [rax]
0x180018d91  cmp     r10d, 5
0x180018d95  jbe     loc_180018E69
0x180018d9b  mov     rdx, 400000000000h
0x180018da5  mov     rcx, rax
0x180018da8  call    _tlgKeywordOn
0x180018dad  test    al, al
0x180018daf  jz      loc_180018E69
0x180018db5  mov     eax, [rbp+27h+arg_48]
0x180018db8  lea     rcx, [r14+18h]
0x180018dbc  mov     [rbp+27h+var_60], eax
0x180018dbf  lea     rdx, unk_18002C4A0
0x180018dc6  mov     eax, [rbp+27h+arg_40]
0x180018dc9  mov     [rbp+27h+var_5C], eax
0x180018dcc  movzx   eax, [rbp+27h+arg_38]
0x180018dd0  mov     [rbp+27h+var_58], eax
0x180018dd3  mov     rax, [rbp+27h+arg_30]
0x180018dd7  mov     [rbp+27h+var_30], rax
0x180018ddb  mov     rax, qword ptr [rbp+27h+arg_28.dwLowDateTime]
0x180018ddf  mov     [rbp+27h+var_28], rax
0x180018de3  mov     eax, [rbp+27h+arg_20]
0x180018de6  mov     [rbp+27h+var_54], eax
0x180018de9  lea     rax, [rbp+27h+var_40]
0x180018ded  mov     [rsp+0E0h+var_70], rax
0x180018df2  lea     rax, [rbp+27h+var_38]
0x180018df6  mov     [rsp+0E0h+var_78], rax
0x180018dfb  lea     rax, [rbp+27h+var_60]
0x180018dff  mov     [rsp+0E0h+var_80], rax
0x180018e04  lea     rax, [rbp+27h+var_5C]
0x180018e08  mov     [rsp+0E0h+var_88], rax
0x180018e0d  lea     rax, [rbp+27h+var_58]
0x180018e11  mov     [rsp+0E0h+var_90], rax
0x180018e16  lea     rax, [rbp+27h+var_30]
0x180018e1a  mov     [rsp+0E0h+var_98], rax
0x180018e1f  lea     rax, [rbp+27h+var_28]
0x180018e23  mov     [rsp+0E0h+var_A0], rax
0x180018e28  lea     rax, [rbp+27h+var_54]
0x180018e2c  mov     [rsp+0E0h+var_A8], rax
0x180018e31  lea     rax, [rbp+27h+var_50]
0x180018e35  mov     [rsp+0E0h+var_B0], rax
0x180018e3a  lea     rax, [rbp+27h+var_4C]
0x180018e3e  mov     [rsp+0E0h+var_B8], rax
0x180018e43  lea     rax, [rbp+27h+var_48]
0x180018e47  mov     [rbp+27h+var_38], rcx
0x180018e4b  mov     rcx, r11
0x180018e4e  mov     [rsp+0E0h+var_C0], rax
0x180018e53  mov     [rbp+27h+var_40], 2000000h
0x180018e5b  mov     [rbp+27h+var_50], ebx
0x180018e5e  mov     [rbp+27h+var_4C], edi
0x180018e61  mov     [rbp+27h+var_48], esi
0x180018e64  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U?$_tlgWrapperByVal@$07@@U2@U1@U1@U1@U?$_tlgWrapperByRef@$0BA@@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@333AEBU?$_tlgWrapperByVal@$07@@4333AEBU?$_tlgWrapperByRef@$0BA@@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<8> const &)
0x180018e69  add     rsp, 0C0h
0x180018e70  pop     r14
0x180018e72  pop     rdi
0x180018e73  pop     rsi
0x180018e74  pop     rbx
0x180018e75  pop     rbp
0x180018e76  retn
```
