# TelemetryTracePropagate_2

- ea: `0x180015f74`
- end: `0x180015ffe`
- name: `TelemetryTracePropagate_2`
- size: `138`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180015f64`

## callees

- `0x180001008`
- `0x180015f74`

## string_xrefs

- `0x180015fb2`: `onecoreuap\net\phone\telephonyinteractiveuser\lib\incomingcalltoastfeedback.cpp`

## pseudocode

```c
__int64 __fastcall TelemetryTracePropagate_2(int a1, __int64 a2, int a3)
{
  __int64 result; // rax
  const char *v4; // [rsp+40h] [rbp-18h] BYREF
  __int64 v5; // [rsp+48h] [rbp-10h] BYREF
  __int64 v6; // [rsp+68h] [rbp+10h] BYREF
  int v7; // [rsp+78h] [rbp+20h] BYREF

  v6 = a2;
  result = (unsigned int)dword_180025038;
  if ( (unsigned int)dword_180025038 > 3 )
  {
    result = qword_180025048;
    if ( (qword_180025048 & 0x200000000000LL) != 0 )
    {
      result = qword_180025050 & 0x200000000000LL;
      if ( (qword_180025050 & 0x200000000000LL) == qword_180025050 )
      {
        LODWORD(v6) = a3;
        v4 = "onecoreuap\\net\\phone\\telephonyinteractiveuser\\lib\\incomingcalltoastfeedback.cpp";
        v7 = a1;
        v5 = 2048;
        return _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
                 a1,
                 (unsigned int)word_180021202,
                 a3,
                 0,
                 (__int64)&v5,
                 (__int64)&v7,
                 (__int64)&v4,
                 (__int64)&v6);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180015f74  mov     r11, rsp
0x180015f77  mov     [r11+10h], rdx
0x180015f7b  sub     rsp, 58h
0x180015f7f  mov     eax, cs:dword_180025038
0x180015f85  cmp     eax, 3
0x180015f88  jbe     short loc_180015FF9
0x180015f8a  mov     rdx, cs:qword_180025050
0x180015f91  mov     r9, 200000000000h
0x180015f9b  mov     rax, cs:qword_180025048
0x180015fa2  test    r9, rax
0x180015fa5  jz      short loc_180015FF9
0x180015fa7  mov     rax, rdx
0x180015faa  and     rax, r9
0x180015fad  cmp     rax, rdx
0x180015fb0  jnz     short loc_180015FF9
0x180015fb2  lea     rax, aOnecoreuapNetP_0; "onecoreuap\\net\\phone\\telephonyintera"...
0x180015fb9  mov     [r11+10h], r8d
0x180015fbd  mov     [r11-18h], rax
0x180015fc1  lea     rdx, word_180021202
0x180015fc8  lea     rax, [r11+10h]
0x180015fcc  mov     [rsp+58h+arg_18], ecx
0x180015fd0  mov     [r11-20h], rax
0x180015fd4  lea     rax, [r11-18h]
0x180015fd8  mov     [r11-28h], rax
0x180015fdc  lea     rax, [r11+20h]
0x180015fe0  mov     [r11-30h], rax
0x180015fe4  lea     rax, [r11-10h]
0x180015fe8  mov     [r11-38h], rax
0x180015fec  mov     qword ptr [r11-10h], 800h
0x180015ff4  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180015ff9  add     rsp, 58h
0x180015ffd  retn
```
