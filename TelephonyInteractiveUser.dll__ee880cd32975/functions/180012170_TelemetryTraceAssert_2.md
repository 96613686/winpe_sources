# TelemetryTraceAssert_2

- ea: `0x180012170`
- end: `0x180012202`
- name: `TelemetryTraceAssert_2`
- size: `146`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180011e5c`

## callees

- `0x180001008`
- `0x180012170`

## string_xrefs

- `0x1800121b2`: `onecoreuap\net\phone\telephonyinteractiveuser\lib\incomingcalltoast.cpp`

## pseudocode

```c
__int64 __fastcall TelemetryTraceAssert_2(int a1, __int64 a2, int a3, int a4)
{
  __int64 result; // rax
  __int64 v5[3]; // [rsp+40h] [rbp-18h] BYREF
  int v6; // [rsp+60h] [rbp+8h] BYREF
  __int64 v7; // [rsp+68h] [rbp+10h] BYREF
  const char *v8; // [rsp+78h] [rbp+20h] BYREF

  v7 = a2;
  v6 = a1;
  result = (unsigned int)dword_180025038;
  if ( (unsigned int)dword_180025038 > 2 )
  {
    result = qword_180025048;
    if ( (qword_180025048 & 0x200000000000LL) != 0 )
    {
      result = qword_180025050 & 0x200000000000LL;
      if ( (qword_180025050 & 0x200000000000LL) == qword_180025050 )
      {
        v6 = a3;
        v8 = "onecoreuap\\net\\phone\\telephonyinteractiveuser\\lib\\incomingcalltoast.cpp";
        LODWORD(v7) = -2147418113;
        v5[0] = 2048;
        return _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
                 qword_180025050,
                 (unsigned int)byte_180020EA3,
                 a3,
                 a4,
                 (__int64)v5,
                 (__int64)&v7,
                 (__int64)&v8,
                 (__int64)&v6);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180012170  mov     r11, rsp
0x180012173  mov     [r11+10h], rdx
0x180012177  mov     [rsp+arg_0], ecx
0x18001217b  sub     rsp, 58h
0x18001217f  mov     eax, cs:dword_180025038
0x180012185  cmp     eax, 2
0x180012188  jbe     short loc_1800121FD
0x18001218a  mov     rcx, cs:qword_180025050
0x180012191  mov     rdx, 200000000000h
0x18001219b  mov     rax, cs:qword_180025048
0x1800121a2  test    rdx, rax
0x1800121a5  jz      short loc_1800121FD
0x1800121a7  mov     rax, rcx
0x1800121aa  and     rax, rdx
0x1800121ad  cmp     rax, rcx
0x1800121b0  jnz     short loc_1800121FD
0x1800121b2  lea     rax, aOnecoreuapNetP; "onecoreuap\\net\\phone\\telephonyintera"...
0x1800121b9  mov     [r11+8], r8d
0x1800121bd  mov     [r11+20h], rax
0x1800121c1  lea     rdx, byte_180020EA3
0x1800121c8  lea     rax, [r11+8]
0x1800121cc  mov     dword ptr [rsp+58h+arg_8], 8000FFFFh
0x1800121d4  mov     [r11-20h], rax
0x1800121d8  lea     rax, [r11+20h]
0x1800121dc  mov     [r11-28h], rax
0x1800121e0  lea     rax, [r11+10h]
0x1800121e4  mov     [r11-30h], rax
0x1800121e8  lea     rax, [r11-18h]
0x1800121ec  mov     [r11-38h], rax
0x1800121f0  mov     qword ptr [r11-18h], 800h
0x1800121f8  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800121fd  add     rsp, 58h
0x180012201  retn
```
