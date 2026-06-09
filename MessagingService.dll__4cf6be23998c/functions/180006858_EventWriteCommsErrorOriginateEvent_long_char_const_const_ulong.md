# EventWriteCommsErrorOriginateEvent(long,char const * const,ulong)

- ea: `0x180006858`
- end: `0x18000689f`
- name: `?EventWriteCommsErrorOriginateEvent@@YAXJQEBDK@Z`
- size: `71`
- prototype: `void __fastcall(__int64, char *, __int64, __int64)`
- caller_count: `9`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800044c4`
- `0x1800044dc`
- `0x180006be8`
- `0x180007248`
- `0x180009acc`
- `0x180009ba4`
- `0x180009bc4`
- `0x18000a2cc`
- `0x18000a2ec`

## callees

- `0x1800012d0`
- `0x180006858`

## pseudocode

```c
void __fastcall EventWriteCommsErrorOriginateEvent(__int64 a1, char *a2, __int64 a3, __int64 a4)
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
      (int)qword_180010310,
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
0x180006858  mov     r11, rsp
0x18000685b  sub     rsp, 58h
0x18000685f  mov     eax, cs:dword_180013018
0x180006865  cmp     eax, 2
0x180006868  jbe     short loc_18000689A
0x18000686a  lea     rax, [r11+20h]
0x18000686e  mov     [r11-10h], rdx
0x180006872  mov     [r11-28h], rax
0x180006876  lea     rdx, qword_180010310
0x18000687d  lea     rax, [r11-10h]
0x180006881  mov     [r11+20h], r8d
0x180006885  mov     [r11-30h], rax
0x180006889  lea     rax, [r11-18h]
0x18000688d  mov     [r11-38h], rax
0x180006891  mov     [rsp+58h+var_18], ecx
0x180006895  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18000689a  add     rsp, 58h
0x18000689e  retn
```
