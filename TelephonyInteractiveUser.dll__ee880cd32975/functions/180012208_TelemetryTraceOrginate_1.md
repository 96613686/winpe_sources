# TelemetryTraceOrginate_1

- ea: `0x180012208`
- end: `0x180012292`
- name: `TelemetryTraceOrginate_1`
- size: `138`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180011e68`

## callees

- `0x180001008`
- `0x180012208`

## string_xrefs

- `0x180012246`: `onecoreuap\net\phone\telephonyinteractiveuser\lib\incomingcalltoast.cpp`

## pseudocode

```c
__int64 __fastcall TelemetryTraceOrginate_1(int a1, __int64 a2, int a3)
{
  __int64 result; // rax
  const char *v4; // [rsp+40h] [rbp-18h] BYREF
  __int64 v5; // [rsp+48h] [rbp-10h] BYREF
  __int64 v6; // [rsp+68h] [rbp+10h] BYREF
  int v7; // [rsp+78h] [rbp+20h] BYREF

  v6 = a2;
  result = (unsigned int)dword_180025038;
  if ( (unsigned int)dword_180025038 > 2 )
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
                 (unsigned int)word_180020F42,
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
0x180012208  mov     r11, rsp
0x18001220b  mov     [r11+10h], rdx
0x18001220f  sub     rsp, 58h
0x180012213  mov     eax, cs:dword_180025038
0x180012219  cmp     eax, 2
0x18001221c  jbe     short loc_18001228D
0x18001221e  mov     rdx, cs:qword_180025050
0x180012225  mov     r9, 200000000000h
0x18001222f  mov     rax, cs:qword_180025048
0x180012236  test    r9, rax
0x180012239  jz      short loc_18001228D
0x18001223b  mov     rax, rdx
0x18001223e  and     rax, r9
0x180012241  cmp     rax, rdx
0x180012244  jnz     short loc_18001228D
0x180012246  lea     rax, aOnecoreuapNetP; "onecoreuap\\net\\phone\\telephonyintera"...
0x18001224d  mov     [r11+10h], r8d
0x180012251  mov     [r11-18h], rax
0x180012255  lea     rdx, word_180020F42
0x18001225c  lea     rax, [r11+10h]
0x180012260  mov     [rsp+58h+arg_18], ecx
0x180012264  mov     [r11-20h], rax
0x180012268  lea     rax, [r11-18h]
0x18001226c  mov     [r11-28h], rax
0x180012270  lea     rax, [r11+20h]
0x180012274  mov     [r11-30h], rax
0x180012278  lea     rax, [r11-10h]
0x18001227c  mov     [r11-38h], rax
0x180012280  mov     qword ptr [r11-10h], 800h
0x180012288  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18001228d  add     rsp, 58h
0x180012291  retn
```
