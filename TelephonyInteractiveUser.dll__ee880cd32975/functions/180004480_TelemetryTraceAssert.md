# TelemetryTraceAssert

- ea: `0x180004480`
- end: `0x18000451a`
- name: `TelemetryTraceAssert`
- size: `154`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003e48`

## callees

- `0x180001008`
- `0x180004480`

## string_xrefs

- `0x1800044c6`: `onecoreuap\net\phone\telephonyinteractiveuser\dll\com_dll.cpp`

## pseudocode

```c
__int64 __fastcall TelemetryTraceAssert(int a1, const char *a2, int a3, int a4)
{
  __int64 result; // rax
  int v5; // [rsp+50h] [rbp+8h] BYREF
  const char *v6; // [rsp+58h] [rbp+10h] BYREF
  int v7; // [rsp+60h] [rbp+18h] BYREF
  __int64 v8; // [rsp+68h] [rbp+20h] BYREF

  v7 = a3;
  v6 = a2;
  v5 = a1;
  result = (unsigned int)dword_180025038;
  if ( (unsigned int)dword_180025038 > 2 )
  {
    result = qword_180025048;
    if ( (qword_180025048 & 0x200000000000LL) != 0 )
    {
      result = qword_180025050 & 0x200000000000LL;
      if ( (qword_180025050 & 0x200000000000LL) == qword_180025050 )
      {
        v7 = 51;
        v6 = "onecoreuap\\net\\phone\\telephonyinteractiveuser\\dll\\com_dll.cpp";
        v5 = -2147418113;
        v8 = 2048;
        return _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
                 qword_180025050,
                 (unsigned int)byte_1800204D1,
                 a3,
                 a4,
                 (__int64)&v8,
                 (__int64)&v5,
                 (__int64)&v6,
                 (__int64)&v7);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180004480  mov     r11, rsp
0x180004483  mov     [r11+18h], r8d
0x180004487  mov     [r11+10h], rdx
0x18000448b  mov     [rsp+arg_0], ecx
0x18000448f  sub     rsp, 48h
0x180004493  mov     eax, cs:dword_180025038
0x180004499  cmp     eax, 2
0x18000449c  jbe     short loc_180004515
0x18000449e  mov     rcx, cs:qword_180025050
0x1800044a5  mov     rdx, 200000000000h
0x1800044af  mov     rax, cs:qword_180025048
0x1800044b6  test    rdx, rax
0x1800044b9  jz      short loc_180004515
0x1800044bb  mov     rax, rcx
0x1800044be  and     rax, rdx
0x1800044c1  cmp     rax, rcx
0x1800044c4  jnz     short loc_180004515
0x1800044c6  lea     rax, aOnecoreuapNetP_2; "onecoreuap\\net\\phone\\telephonyintera"...
0x1800044cd  mov     [rsp+48h+arg_10], 33h ; '3'
0x1800044d5  mov     [r11+10h], rax
0x1800044d9  lea     rdx, byte_1800204D1
0x1800044e0  lea     rax, [r11+18h]
0x1800044e4  mov     [rsp+48h+arg_0], 8000FFFFh
0x1800044ec  mov     [r11-10h], rax
0x1800044f0  lea     rax, [r11+10h]
0x1800044f4  mov     [r11-18h], rax
0x1800044f8  lea     rax, [r11+8]
0x1800044fc  mov     [r11-20h], rax
0x180004500  lea     rax, [r11+20h]
0x180004504  mov     [r11-28h], rax
0x180004508  mov     qword ptr [r11+20h], 800h
0x180004510  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180004515  add     rsp, 48h
0x180004519  retn
```
