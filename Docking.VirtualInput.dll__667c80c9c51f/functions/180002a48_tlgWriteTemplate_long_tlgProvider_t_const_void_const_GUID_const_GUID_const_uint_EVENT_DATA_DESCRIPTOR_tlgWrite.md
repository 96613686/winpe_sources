# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)

- ea: `0x180002a48`
- end: `0x180002bd6`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z`
- size: `398`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1800117d0`
- `0x1800179c0`

## callees

- `0x180001c98`
- `0x180001e8c`
- `0x1800036a0`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        __int64 a1,
        unsigned __int8 *a2,
        const GUID *a3,
        const GUID *a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        __int64 a10,
        __int64 a11,
        __int64 a12,
        __int64 a13,
        __int64 a14,
        __int64 a15,
        __int64 a16,
        __int64 a17,
        __int64 a18,
        __int64 a19,
        __int64 a20,
        __int64 a21,
        __int64 a22,
        __int64 a23)
{
  struct _EVENT_DATA_DESCRIPTOR v24; // [rsp+B0h] [rbp-168h] BYREF
  _BYTE v25[304]; // [rsp+D0h] [rbp-148h] BYREF

  _tlgDataDescInit<_tlgIndexSequence<19,0,1,2,3,4,5,6,7,8,9,10,11,12,13,14,15,16,17,18>>::Fill<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
    (__int64)v25,
    a5,
    a6,
    a7,
    a8,
    a9,
    a10,
    a11,
    a12,
    a13,
    a14,
    a15,
    a16,
    a17,
    a18,
    a19,
    a20,
    a21,
    a22,
    a23);
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, a3, a4, 0x15u, &v24);
}

```

## disassembly

```asm
0x180002a48  mov     [rsp+arg_18], r9
0x180002a4d  mov     [rsp+arg_10], r8
0x180002a52  mov     [rsp+arg_8], rdx
0x180002a57  mov     [rsp+arg_0], rcx
0x180002a5c  sub     rsp, 218h
0x180002a63  mov     rax, cs:__security_cookie
0x180002a6a  xor     rax, rsp
0x180002a6d  mov     [rsp+218h+var_18], rax
0x180002a75  mov     [rsp+218h+var_178], 15h
0x180002a80  lea     rax, [rsp+218h+var_148]
0x180002a88  mov     rcx, [rsp+218h+arg_B0]
0x180002a90  mov     [rsp+218h+var_180], rcx
0x180002a98  mov     rcx, [rsp+218h+arg_A8]
0x180002aa0  mov     [rsp+218h+var_188], rcx
0x180002aa8  mov     rcx, [rsp+218h+arg_A0]
0x180002ab0  mov     [rsp+218h+var_190], rcx
0x180002ab8  mov     rcx, [rsp+218h+arg_98]
0x180002ac0  mov     [rsp+218h+var_198], rcx
0x180002ac8  mov     rcx, [rsp+218h+arg_90]
0x180002ad0  mov     [rsp+218h+var_1A0], rcx
0x180002ad5  mov     rcx, [rsp+218h+arg_88]
0x180002add  mov     [rsp+218h+var_1A8], rcx
0x180002ae2  mov     rcx, [rsp+218h+arg_80]
0x180002aea  mov     [rsp+218h+var_1B0], rcx
0x180002aef  mov     rcx, [rsp+218h+arg_78]
0x180002af7  mov     [rsp+218h+var_1B8], rcx
0x180002afc  mov     rcx, [rsp+218h+arg_70]
0x180002b04  mov     [rsp+218h+var_1C0], rcx
0x180002b09  mov     rcx, [rsp+218h+arg_68]
0x180002b11  mov     [rsp+218h+var_1C8], rcx
0x180002b16  mov     rcx, [rsp+218h+arg_60]
0x180002b1e  mov     [rsp+218h+var_1D0], rcx
0x180002b23  mov     rcx, [rsp+218h+arg_58]
0x180002b2b  mov     [rsp+218h+var_1D8], rcx
0x180002b30  mov     rcx, [rsp+218h+arg_50]
0x180002b38  mov     [rsp+218h+var_1E0], rcx
0x180002b3d  mov     rcx, [rsp+218h+arg_48]
0x180002b45  mov     [rsp+218h+var_1E8], rcx
0x180002b4a  mov     rcx, [rsp+218h+arg_40]
0x180002b52  mov     [rsp+218h+var_1F0], rcx
0x180002b57  mov     rcx, [rsp+218h+arg_38]
0x180002b5f  mov     [rsp+218h+var_1F8], rcx
0x180002b64  mov     r9, [rsp+218h+arg_30]
0x180002b6c  mov     r8, [rsp+218h+arg_28]
0x180002b74  mov     rdx, [rsp+218h+arg_20]
0x180002b7c  mov     rcx, rax
0x180002b7f  call    ??$Fill@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgDataDescInit@U?$_tlgIndexSequence@$0BD@$0A@$00$01$02$03$04$05$06$07$08$09$0L@$0M@$0N@$0O@$0P@$0BA@$0BB@$0BC@@@@@SAXPEAU_EVENT_DATA_DESCRIPTOR@@AEBU?$_tlgWrapperByVal@$07@@1AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@232AEBU?$_tlgWrapSz@G@@23234234223@Z
0x180002b84  lea     rax, [rsp+218h+var_168]
0x180002b8c  mov     [rsp+218h+var_1F0], rax
0x180002b91  mov     dword ptr [rsp+218h+var_1F8], 15h
0x180002b99  mov     r9, [rsp+218h+arg_18]
0x180002ba1  mov     r8, [rsp+218h+arg_10]
0x180002ba9  mov     rdx, [rsp+218h+arg_8]
0x180002bb1  mov     rcx, [rsp+218h+arg_0]
0x180002bb9  call    _tlgWriteTransfer_EventWriteTransfer
0x180002bbe  mov     rcx, [rsp+218h+var_18]
0x180002bc6  xor     rcx, rsp; StackCookie
0x180002bc9  call    __security_check_cookie
0x180002bce  add     rsp, 218h
0x180002bd5  retn
```
