# EventWriteCommsErrorPropagateEvent(long,char const * const,ulong)

- ea: `0x1800068a8`
- end: `0x1800068ef`
- name: `?EventWriteCommsErrorPropagateEvent@@YAXJQEBDK@Z`
- size: `71`
- prototype: `void __fastcall(__int64, char *, __int64, __int64)`
- caller_count: `8`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000307c`
- `0x1800044dc`
- `0x180006ad0`
- `0x180006be8`
- `0x180007248`
- `0x180009acc`
- `0x180009bc4`
- `0x18000a2ec`

## callees

- `0x1800012d0`
- `0x1800068a8`

## pseudocode

```c
void __fastcall EventWriteCommsErrorPropagateEvent(__int64 a1, char *a2, __int64 a3, __int64 a4)
{
  int v4; // [rsp+40h] [rbp-18h] BYREF
  char *v5; // [rsp+48h] [rbp-10h] BYREF
  int v6; // [rsp+78h] [rbp+20h] BYREF

  if ( (unsigned int)dword_180013018 > 2 )
  {
    v5 = a2;
    v6 = a3;
    v4 = a1;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      a1,
      (int)byte_180010345,
      a3,
      a4,
      (__int64)&v4,
      &v5,
      (__int64)&v6);
  }
}

```

## disassembly

```asm
0x1800068a8  mov     r11, rsp
0x1800068ab  sub     rsp, 58h
0x1800068af  mov     eax, cs:dword_180013018
0x1800068b5  cmp     eax, 2
0x1800068b8  jbe     short loc_1800068EA
0x1800068ba  lea     rax, [r11+20h]
0x1800068be  mov     [r11-10h], rdx
0x1800068c2  mov     [r11-28h], rax
0x1800068c6  lea     rdx, byte_180010345
0x1800068cd  lea     rax, [r11-10h]
0x1800068d1  mov     [r11+20h], r8d
0x1800068d5  mov     [r11-30h], rax
0x1800068d9  lea     rax, [r11-18h]
0x1800068dd  mov     [r11-38h], rax
0x1800068e1  mov     [rsp+58h+var_18], ecx
0x1800068e5  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800068ea  add     rsp, 58h
0x1800068ee  retn
```
