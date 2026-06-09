# wil::TraceLoggingProvider::ReportTraceLoggingFailure(wil::FailureInfo const &)

- ea: `0x180005f6c`
- end: `0x1800060cc`
- name: `?ReportTraceLoggingFailure@TraceLoggingProvider@wil@@IEAAXAEBUFailureInfo@2@@Z`
- size: `352`
- prototype: `void __fastcall(wil::TraceLoggingProvider *this, const struct wil::FailureInfo *, __int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180004570`
- `0x1800059a0`

## callees

- `0x1800012bc`
- `0x180005f6c`

## pseudocode

```c
void __fastcall wil::TraceLoggingProvider::ReportTraceLoggingFailure(
        wil::TraceLoggingProvider *this,
        const struct wil::FailureInfo *a2,
        __int64 a3,
        __int64 a4)
{
  _DWORD *v4; // rcx
  int v5; // [rsp+B8h] [rbp-80h] BYREF
  int v6; // [rsp+BCh] [rbp-7Ch] BYREF
  int v7; // [rsp+C0h] [rbp-78h] BYREF
  int v8; // [rsp+C4h] [rbp-74h] BYREF
  int v9; // [rsp+C8h] [rbp-70h] BYREF
  const unsigned __int16 *v10; // [rsp+D0h] [rbp-68h] BYREF
  int *v11; // [rsp+D8h] [rbp-60h] BYREF
  const unsigned __int16 *v12; // [rsp+E0h] [rbp-58h] BYREF
  int *v13; // [rsp+E8h] [rbp-50h] BYREF
  const unsigned __int16 *v14; // [rsp+F0h] [rbp-48h] BYREF
  const unsigned __int16 *v15; // [rsp+F8h] [rbp-40h] BYREF
  int *v16; // [rsp+100h] [rbp-38h] BYREF
  const unsigned __int16 *v17; // [rsp+108h] [rbp-30h] BYREF
  const unsigned __int16 *v18; // [rsp+110h] [rbp-28h] BYREF
  __int64 v19; // [rsp+118h] [rbp-20h] BYREF
  int v20; // [rsp+138h] [rbp+0h] BYREF
  int v21; // [rsp+148h] [rbp+10h] BYREF
  int v22; // [rsp+150h] [rbp+18h] BYREF

  v4 = (_DWORD *)*((_QWORD *)this + 1);
  if ( *v4 > 2u )
  {
    v10 = (const unsigned __int16 *)*((_QWORD *)a2 + 6);
    v20 = *((_DWORD *)a2 + 17);
    v21 = *((_DWORD *)a2 + 4);
    v11 = (int *)*((_QWORD *)a2 + 15);
    v12 = (const unsigned __int16 *)*((_QWORD *)a2 + 14);
    v22 = *((_DWORD *)a2 + 26);
    v13 = (int *)*((_QWORD *)a2 + 12);
    v14 = (const unsigned __int16 *)*((_QWORD *)a2 + 11);
    v5 = *((_DWORD *)a2 + 20);
    v15 = (const unsigned __int16 *)*((_QWORD *)a2 + 9);
    v6 = *((_DWORD *)a2 + 8);
    v16 = (int *)*((_QWORD *)a2 + 3);
    v7 = *(_DWORD *)a2;
    v17 = (const unsigned __int16 *)*((_QWORD *)a2 + 16);
    v8 = *((_DWORD *)a2 + 16);
    v18 = (const unsigned __int16 *)*((_QWORD *)a2 + 7);
    v9 = *((_DWORD *)a2 + 2);
    v19 = 0x1000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      (__int64)v4,
      (__int64)byte_180011A79,
      a3,
      a4,
      (__int64)&v19,
      (__int64)&v9,
      &v18,
      (__int64)&v8,
      &v17,
      (__int64)&v7,
      &v16,
      (__int64)&v6,
      &v15,
      (__int64)&v5,
      &v14,
      &v13,
      (__int64)&v22,
      &v12,
      &v11,
      (__int64)&v21,
      (__int64)&v20,
      &v10);
  }
}

```

## disassembly

```asm
0x180005f6c  mov     r11, rsp
0x180005f6f  push    rbp
0x180005f70  lea     rbp, [r11+8]
0x180005f74  sub     rsp, 120h
0x180005f7b  mov     rcx, [rcx+8]
0x180005f7f  mov     eax, [rcx]
0x180005f81  cmp     eax, 2
0x180005f84  jbe     loc_1800060C3
0x180005f8a  mov     rax, [rdx+30h]
0x180005f8e  mov     [rbp-10h+var_58], rax
0x180005f92  mov     eax, [rdx+44h]
0x180005f95  mov     [rbp-10h+arg_0], eax
0x180005f98  mov     eax, [rdx+10h]
0x180005f9b  mov     [rbp-10h+arg_10], eax
0x180005f9e  mov     rax, [rdx+78h]
0x180005fa2  mov     [rbp-10h+var_50], rax
0x180005fa6  mov     rax, [rdx+70h]
0x180005faa  mov     [rbp-10h+var_48], rax
0x180005fae  mov     eax, [rdx+68h]
0x180005fb1  mov     [rbp-10h+arg_18], eax
0x180005fb4  mov     rax, [rdx+60h]
0x180005fb8  mov     [rbp-10h+var_40], rax
0x180005fbc  mov     rax, [rdx+58h]
0x180005fc0  mov     [rbp-10h+var_38], rax
0x180005fc4  mov     eax, [rdx+50h]
0x180005fc7  mov     [rbp-10h+var_70], eax
0x180005fca  mov     rax, [rdx+48h]
0x180005fce  mov     [rbp-10h+var_30], rax
0x180005fd2  mov     eax, [rdx+20h]
0x180005fd5  mov     [rbp-10h+var_6C], eax
0x180005fd8  mov     rax, [rdx+18h]
0x180005fdc  mov     [rbp-10h+var_28], rax
0x180005fe0  mov     eax, [rdx]
0x180005fe2  mov     [rbp-10h+var_68], eax
0x180005fe5  mov     rax, [rdx+80h]
0x180005fec  mov     [rbp-10h+var_20], rax
0x180005ff0  mov     eax, [rdx+40h]
0x180005ff3  mov     [rbp-10h+var_64], eax
0x180005ff6  mov     rax, [rdx+38h]
0x180005ffa  mov     [rbp-10h+var_18], rax
0x180005ffe  mov     eax, [rdx+8]
0x180006001  lea     rdx, byte_180011A79
0x180006008  mov     [rbp-10h+var_60], eax
0x18000600b  lea     rax, [rbp-10h+var_58]
0x18000600f  mov     [r11-80h], rax
0x180006013  lea     rax, [rbp-10h+arg_0]
0x180006017  mov     [r11-88h], rax
0x18000601e  lea     rax, [rbp-10h+arg_10]
0x180006022  mov     [r11-90h], rax
0x180006029  lea     rax, [rbp-10h+var_50]
0x18000602d  mov     [r11-98h], rax
0x180006034  lea     rax, [rbp-10h+var_48]
0x180006038  mov     [r11-0A0h], rax
0x18000603f  lea     rax, [rbp-10h+arg_18]
0x180006043  mov     [r11-0A8h], rax
0x18000604a  lea     rax, [rbp-10h+var_40]
0x18000604e  mov     [rsp+78h], rax
0x180006053  lea     rax, [rbp-10h+var_38]
0x180006057  mov     [rsp+120h+var_B0], rax
0x18000605c  lea     rax, [rbp-10h+var_70]
0x180006060  mov     [rsp+120h+var_B8], rax
0x180006065  lea     rax, [rbp-10h+var_30]
0x180006069  mov     [rsp+120h+var_C0], rax
0x18000606e  lea     rax, [rbp-10h+var_6C]
0x180006072  mov     [rsp+120h+var_C8], rax
0x180006077  lea     rax, [rbp-10h+var_28]
0x18000607b  mov     [rsp+120h+var_D0], rax
0x180006080  lea     rax, [rbp-10h+var_68]
0x180006084  mov     [rsp+120h+var_D8], rax
0x180006089  lea     rax, [rbp-10h+var_20]
0x18000608d  mov     [rsp+120h+var_E0], rax
0x180006092  lea     rax, [rbp-10h+var_64]
0x180006096  mov     [rsp+120h+var_E8], rax
0x18000609b  lea     rax, [rbp-10h+var_18]
0x18000609f  mov     [rsp+120h+var_F0], rax
0x1800060a4  lea     rax, [rbp-10h+var_60]
0x1800060a8  mov     [rsp+120h+var_F8], rax
0x1800060ad  lea     rax, [rbp-10h+var_10]
0x1800060b1  mov     [rsp+120h+var_100], rax
0x1800060b6  mov     [rbp-10h+var_10], 1000000h
0x1800060be  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800060c3  add     rsp, 120h
0x1800060ca  pop     rbp
0x1800060cb  retn
```
