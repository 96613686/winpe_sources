# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)

- ea: `0x180002d34`
- end: `0x180002df7`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@@Z`
- size: `195`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001097c`

## callees

- `0x180001c98`
- `0x18000244c`
- `0x1800036a0`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        __int64 a1,
        unsigned __int8 *a2,
        const GUID *a3,
        const GUID *a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9)
{
  struct _EVENT_DATA_DESCRIPTOR v10; // [rsp+40h] [rbp-88h] BYREF
  char v11; // [rsp+60h] [rbp-68h] BYREF

  _tlgDataDescInit<_tlgIndexSequence<5,0,1,2,3,4>>::Fill<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
    (unsigned int)&v11,
    a5,
    a6,
    a7,
    a8,
    a9);
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, a3, a4, 7u, &v10);
}

```

## disassembly

```asm
0x180002d34  mov     [rsp+arg_18], r9
0x180002d39  mov     [rsp+arg_10], r8
0x180002d3e  mov     [rsp+arg_8], rdx
0x180002d43  mov     [rsp+arg_0], rcx
0x180002d48  sub     rsp, 0C8h
0x180002d4f  mov     rax, cs:__security_cookie
0x180002d56  xor     rax, rsp
0x180002d59  mov     [rsp+0C8h+var_18], rax
0x180002d61  mov     [rsp+0C8h+var_98], 7
0x180002d69  lea     rax, [rsp+0C8h+var_68]
0x180002d6e  mov     rcx, [rsp+0C8h+arg_40]
0x180002d76  mov     [rsp+0C8h+var_A0], rcx
0x180002d7b  mov     rcx, [rsp+0C8h+arg_38]
0x180002d83  mov     [rsp+0C8h+var_A8], rcx
0x180002d88  mov     r9, [rsp+0C8h+arg_30]
0x180002d90  mov     r8, [rsp+0C8h+arg_28]
0x180002d98  mov     rdx, [rsp+0C8h+arg_20]
0x180002da0  mov     rcx, rax
0x180002da3  call    ??$Fill@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@@?$_tlgDataDescInit@U?$_tlgIndexSequence@$04$0A@$00$01$02$03@@@@SAXPEAU_EVENT_DATA_DESCRIPTOR@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@@Z
0x180002da8  lea     rax, [rsp+0C8h+var_88]
0x180002dad  mov     [rsp+0C8h+var_A0], rax
0x180002db2  mov     dword ptr [rsp+0C8h+var_A8], 7
0x180002dba  mov     r9, [rsp+0C8h+arg_18]
0x180002dc2  mov     r8, [rsp+0C8h+arg_10]
0x180002dca  mov     rdx, [rsp+0C8h+arg_8]
0x180002dd2  mov     rcx, [rsp+0C8h+arg_0]
0x180002dda  call    _tlgWriteTransfer_EventWriteTransfer
0x180002ddf  mov     rcx, [rsp+0C8h+var_18]
0x180002de7  xor     rcx, rsp; StackCookie
0x180002dea  call    __security_check_cookie
0x180002def  add     rsp, 0C8h
0x180002df6  retn
```
