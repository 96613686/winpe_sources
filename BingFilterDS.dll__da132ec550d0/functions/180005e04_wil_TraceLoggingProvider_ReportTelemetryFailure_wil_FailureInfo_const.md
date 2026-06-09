# wil::TraceLoggingProvider::ReportTelemetryFailure(wil::FailureInfo const &)

- ea: `0x180005e04`
- end: `0x180005f63`
- name: `?ReportTelemetryFailure@TraceLoggingProvider@wil@@IEAAXAEBUFailureInfo@2@@Z`
- size: `351`
- prototype: `void __fastcall(wil::TraceLoggingProvider *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180004570`
- `0x1800059a0`

## callees

- `0x180001008`
- `0x180005e04`

## pseudocode

```c
void __fastcall wil::TraceLoggingProvider::ReportTelemetryFailure(
        wil::TraceLoggingProvider *this,
        const struct wil::FailureInfo *a2)
{
  __int64 v2; // rcx
  __int64 v3; // r8
  int v4; // [rsp+A8h] [rbp-9h] BYREF
  int v5; // [rsp+ACh] [rbp-5h] BYREF
  int v6; // [rsp+B0h] [rbp-1h] BYREF
  int *v7; // [rsp+B8h] [rbp+7h] BYREF
  const unsigned __int16 *v8; // [rsp+C0h] [rbp+Fh] BYREF
  int *v9; // [rsp+C8h] [rbp+17h] BYREF
  const unsigned __int16 *v10; // [rsp+D0h] [rbp+1Fh] BYREF
  const unsigned __int16 *v11; // [rsp+D8h] [rbp+27h] BYREF
  int *v12; // [rsp+E0h] [rbp+2Fh] BYREF
  const unsigned __int16 *v13; // [rsp+E8h] [rbp+37h] BYREF
  const unsigned __int16 *v14; // [rsp+F0h] [rbp+3Fh] BYREF
  __int64 v15; // [rsp+F8h] [rbp+47h] BYREF
  __int64 v16; // [rsp+100h] [rbp+4Fh] BYREF
  int v17; // [rsp+118h] [rbp+67h] BYREF
  int v18; // [rsp+128h] [rbp+77h] BYREF
  int v19; // [rsp+130h] [rbp+7Fh] BYREF

  v2 = *((_QWORD *)this + 1);
  if ( *(_DWORD *)v2 > 2u )
  {
    v3 = *(_QWORD *)(v2 + 24);
    if ( (*(_QWORD *)(v2 + 16) & 0x200000000000LL) != 0 && (v3 & 0x200000000000LL) == v3 )
    {
      v7 = (int *)*((_QWORD *)a2 + 15);
      v8 = (const unsigned __int16 *)*((_QWORD *)a2 + 14);
      v17 = *((_DWORD *)a2 + 26);
      v9 = (int *)*((_QWORD *)a2 + 12);
      v10 = (const unsigned __int16 *)*((_QWORD *)a2 + 11);
      v18 = *((_DWORD *)a2 + 20);
      v11 = (const unsigned __int16 *)*((_QWORD *)a2 + 9);
      v19 = *((_DWORD *)a2 + 8);
      v12 = (int *)*((_QWORD *)a2 + 3);
      v4 = *(_DWORD *)a2;
      v13 = (const unsigned __int16 *)*((_QWORD *)a2 + 16);
      v5 = *((_DWORD *)a2 + 16);
      v14 = (const unsigned __int16 *)*((_QWORD *)a2 + 7);
      v6 = *((_DWORD *)a2 + 2);
      v15 = 0x1000000;
      v16 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        v2,
        (__int64)&byte_180011BAF,
        v3,
        0x200000000000LL,
        (__int64)&v16,
        (__int64)&v15,
        (__int64)&v6,
        &v14,
        (__int64)&v5,
        &v13,
        (__int64)&v4,
        &v12,
        (__int64)&v19,
        &v11,
        (__int64)&v18,
        &v10,
        &v9,
        (__int64)&v17,
        &v8,
        &v7);
    }
  }
}

```

## disassembly

```asm
0x180005e04  mov     r11, rsp
0x180005e07  push    rbp
0x180005e08  lea     rbp, [r11-5Fh]
0x180005e0c  sub     rsp, 100h
0x180005e13  mov     rcx, [rcx+8]
0x180005e17  mov     eax, [rcx]
0x180005e19  cmp     eax, 2
0x180005e1c  jbe     loc_180005F5A
0x180005e22  mov     r8, [rcx+18h]
0x180005e26  mov     r9, 200000000000h
0x180005e30  mov     rax, [rcx+10h]
0x180005e34  test    r9, rax
0x180005e37  jz      loc_180005F5A
0x180005e3d  mov     rax, r8
0x180005e40  and     rax, r9
0x180005e43  cmp     rax, r8
0x180005e46  jnz     loc_180005F5A
0x180005e4c  mov     rax, [rdx+78h]
0x180005e50  mov     [rbp+57h+var_50], rax
0x180005e54  mov     rax, [rdx+70h]
0x180005e58  mov     [rbp+57h+var_48], rax
0x180005e5c  mov     eax, [rdx+68h]
0x180005e5f  mov     [rbp+57h+arg_0], eax
0x180005e62  mov     rax, [rdx+60h]
0x180005e66  mov     [rbp+57h+var_40], rax
0x180005e6a  mov     rax, [rdx+58h]
0x180005e6e  mov     [rbp+57h+var_38], rax
0x180005e72  mov     eax, [rdx+50h]
0x180005e75  mov     [rbp+57h+arg_10], eax
0x180005e78  mov     rax, [rdx+48h]
0x180005e7c  mov     [rbp+57h+var_30], rax
0x180005e80  mov     eax, [rdx+20h]
0x180005e83  mov     [rbp+57h+arg_18], eax
0x180005e86  mov     rax, [rdx+18h]
0x180005e8a  mov     [rbp+57h+var_28], rax
0x180005e8e  mov     eax, [rdx]
0x180005e90  mov     [rbp+57h+var_60], eax
0x180005e93  mov     rax, [rdx+80h]
0x180005e9a  mov     [rbp+57h+var_20], rax
0x180005e9e  mov     eax, [rdx+40h]
0x180005ea1  mov     [rbp+57h+var_5C], eax
0x180005ea4  mov     rax, [rdx+38h]
0x180005ea8  mov     [rbp+57h+var_18], rax
0x180005eac  mov     eax, [rdx+8]
0x180005eaf  lea     rdx, byte_180011BAF
0x180005eb6  mov     [rbp+57h+var_58], eax
0x180005eb9  mov     eax, 1000000h
0x180005ebe  mov     [rbp+57h+var_10], rax
0x180005ec2  mov     [rbp+57h+var_8], rax
0x180005ec6  lea     rax, [rbp+57h+var_50]
0x180005eca  mov     [r11-70h], rax
0x180005ece  lea     rax, [rbp+57h+var_48]
0x180005ed2  mov     [r11-78h], rax
0x180005ed6  lea     rax, [rbp+57h+arg_0]
0x180005eda  mov     [r11-80h], rax
0x180005ede  lea     rax, [rbp+57h+var_40]
0x180005ee2  mov     [r11-88h], rax
0x180005ee9  lea     rax, [rbp+57h+var_38]
0x180005eed  mov     [rsp+78h], rax
0x180005ef2  lea     rax, [rbp+57h+arg_10]
0x180005ef6  mov     [rsp+100h+var_90], rax
0x180005efb  lea     rax, [rbp+57h+var_30]
0x180005eff  mov     [rsp+100h+var_98], rax
0x180005f04  lea     rax, [rbp+57h+arg_18]
0x180005f08  mov     [rsp+100h+var_A0], rax
0x180005f0d  lea     rax, [rbp+57h+var_28]
0x180005f11  mov     [rsp+100h+var_A8], rax
0x180005f16  lea     rax, [rbp+57h+var_60]
0x180005f1a  mov     [rsp+100h+var_B0], rax
0x180005f1f  lea     rax, [rbp+57h+var_20]
0x180005f23  mov     [rsp+100h+var_B8], rax
0x180005f28  lea     rax, [rbp+57h+var_5C]
0x180005f2c  mov     [rsp+100h+var_C0], rax
0x180005f31  lea     rax, [rbp+57h+var_18]
0x180005f35  mov     [rsp+100h+var_C8], rax
0x180005f3a  lea     rax, [rbp+57h+var_58]
0x180005f3e  mov     [rsp+100h+var_D0], rax
0x180005f43  lea     rax, [rbp+57h+var_10]
0x180005f47  mov     [rsp+100h+var_D8], rax
0x180005f4c  lea     rax, [rbp+57h+var_8]
0x180005f50  mov     [rsp+100h+var_E0], rax
0x180005f55  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180005f5a  add     rsp, 100h
0x180005f61  pop     rbp
0x180005f62  retn
```
