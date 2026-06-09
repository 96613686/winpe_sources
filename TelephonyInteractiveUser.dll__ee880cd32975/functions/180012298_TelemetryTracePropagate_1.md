# TelemetryTracePropagate_1

- ea: `0x180012298`
- end: `0x180012322`
- name: `TelemetryTracePropagate_1`
- size: `138`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180011e68`

## callees

- `0x180001008`
- `0x180012298`

## string_xrefs

- `0x1800122d6`: `onecoreuap\net\phone\telephonyinteractiveuser\lib\incomingcalltoast.cpp`

## pseudocode

```c
__int64 __fastcall TelemetryTracePropagate_1(int a1, __int64 a2, int a3)
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
        v4 = "onecoreuap\\net\\phone\\telephonyinteractiveuser\\lib\\incomingcalltoast.cpp";
        v7 = a1;
        v5 = 2048;
        return _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
                 a1,
                 (unsigned int)byte_180020EF1,
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
0x180012298  mov     r11, rsp
0x18001229b  mov     [r11+10h], rdx
0x18001229f  sub     rsp, 58h
0x1800122a3  mov     eax, cs:dword_180025038
0x1800122a9  cmp     eax, 3
0x1800122ac  jbe     short loc_18001231D
0x1800122ae  mov     rdx, cs:qword_180025050
0x1800122b5  mov     r9, 200000000000h
0x1800122bf  mov     rax, cs:qword_180025048
0x1800122c6  test    r9, rax
0x1800122c9  jz      short loc_18001231D
0x1800122cb  mov     rax, rdx
0x1800122ce  and     rax, r9
0x1800122d1  cmp     rax, rdx
0x1800122d4  jnz     short loc_18001231D
0x1800122d6  lea     rax, aOnecoreuapNetP; "onecoreuap\\net\\phone\\telephonyintera"...
0x1800122dd  mov     [r11+10h], r8d
0x1800122e1  mov     [r11-18h], rax
0x1800122e5  lea     rdx, byte_180020EF1
0x1800122ec  lea     rax, [r11+10h]
0x1800122f0  mov     [rsp+58h+arg_18], ecx
0x1800122f4  mov     [r11-20h], rax
0x1800122f8  lea     rax, [r11-18h]
0x1800122fc  mov     [r11-28h], rax
0x180012300  lea     rax, [r11+20h]
0x180012304  mov     [r11-30h], rax
0x180012308  lea     rax, [r11-10h]
0x18001230c  mov     [r11-38h], rax
0x180012310  mov     qword ptr [r11-10h], 800h
0x180012318  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18001231d  add     rsp, 58h
0x180012321  retn
```
