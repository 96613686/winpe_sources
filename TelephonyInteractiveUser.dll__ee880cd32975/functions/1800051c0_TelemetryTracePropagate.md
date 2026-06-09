# TelemetryTracePropagate

- ea: `0x1800051c0`
- end: `0x18000524a`
- name: `TelemetryTracePropagate`
- size: `138`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180004d8c`

## callees

- `0x180001008`
- `0x1800051c0`

## string_xrefs

- `0x1800051fe`: `onecoreuap\net\phone\telephonyinteractiveuser\lib\serviceuitoast.cpp`

## pseudocode

```c
__int64 __fastcall TelemetryTracePropagate(int a1, __int64 a2, int a3)
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
        v4 = "onecoreuap\\net\\phone\\telephonyinteractiveuser\\lib\\serviceuitoast.cpp";
        v7 = a1;
        v5 = 2048;
        return _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
                 a1,
                 (unsigned int)byte_18002056D,
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
0x1800051c0  mov     r11, rsp
0x1800051c3  mov     [r11+10h], rdx
0x1800051c7  sub     rsp, 58h
0x1800051cb  mov     eax, cs:dword_180025038
0x1800051d1  cmp     eax, 3
0x1800051d4  jbe     short loc_180005245
0x1800051d6  mov     rdx, cs:qword_180025050
0x1800051dd  mov     r9, 200000000000h
0x1800051e7  mov     rax, cs:qword_180025048
0x1800051ee  test    r9, rax
0x1800051f1  jz      short loc_180005245
0x1800051f3  mov     rax, rdx
0x1800051f6  and     rax, r9
0x1800051f9  cmp     rax, rdx
0x1800051fc  jnz     short loc_180005245
0x1800051fe  lea     rax, aOnecoreuapNetP_1; "onecoreuap\\net\\phone\\telephonyintera"...
0x180005205  mov     [r11+10h], r8d
0x180005209  mov     [r11-18h], rax
0x18000520d  lea     rdx, byte_18002056D
0x180005214  lea     rax, [r11+10h]
0x180005218  mov     [rsp+58h+arg_18], ecx
0x18000521c  mov     [r11-20h], rax
0x180005220  lea     rax, [r11-18h]
0x180005224  mov     [r11-28h], rax
0x180005228  lea     rax, [r11+20h]
0x18000522c  mov     [r11-30h], rax
0x180005230  lea     rax, [r11-10h]
0x180005234  mov     [r11-38h], rax
0x180005238  mov     qword ptr [r11-10h], 800h
0x180005240  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180005245  add     rsp, 58h
0x180005249  retn
```
