# TelemetryTraceOrginate

- ea: `0x180005130`
- end: `0x1800051ba`
- name: `TelemetryTraceOrginate`
- size: `138`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180004d8c`

## callees

- `0x180001008`
- `0x180005130`

## string_xrefs

- `0x18000516e`: `onecoreuap\net\phone\telephonyinteractiveuser\lib\serviceuitoast.cpp`

## pseudocode

```c
__int64 __fastcall TelemetryTraceOrginate(int a1, __int64 a2, int a3)
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
        v4 = "onecoreuap\\net\\phone\\telephonyinteractiveuser\\lib\\serviceuitoast.cpp";
        v7 = a1;
        v5 = 2048;
        return _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
                 a1,
                 (unsigned int)&word_1800205BE,
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
0x180005130  mov     r11, rsp
0x180005133  mov     [r11+10h], rdx
0x180005137  sub     rsp, 58h
0x18000513b  mov     eax, cs:dword_180025038
0x180005141  cmp     eax, 2
0x180005144  jbe     short loc_1800051B5
0x180005146  mov     rdx, cs:qword_180025050
0x18000514d  mov     r9, 200000000000h
0x180005157  mov     rax, cs:qword_180025048
0x18000515e  test    r9, rax
0x180005161  jz      short loc_1800051B5
0x180005163  mov     rax, rdx
0x180005166  and     rax, r9
0x180005169  cmp     rax, rdx
0x18000516c  jnz     short loc_1800051B5
0x18000516e  lea     rax, aOnecoreuapNetP_1; "onecoreuap\\net\\phone\\telephonyintera"...
0x180005175  mov     [r11+10h], r8d
0x180005179  mov     [r11-18h], rax
0x18000517d  lea     rdx, word_1800205BE
0x180005184  lea     rax, [r11+10h]
0x180005188  mov     [rsp+58h+arg_18], ecx
0x18000518c  mov     [r11-20h], rax
0x180005190  lea     rax, [r11-18h]
0x180005194  mov     [r11-28h], rax
0x180005198  lea     rax, [r11+20h]
0x18000519c  mov     [r11-30h], rax
0x1800051a0  lea     rax, [r11-10h]
0x1800051a4  mov     [r11-38h], rax
0x1800051a8  mov     qword ptr [r11-10h], 800h
0x1800051b0  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800051b5  add     rsp, 58h
0x1800051b9  retn
```
