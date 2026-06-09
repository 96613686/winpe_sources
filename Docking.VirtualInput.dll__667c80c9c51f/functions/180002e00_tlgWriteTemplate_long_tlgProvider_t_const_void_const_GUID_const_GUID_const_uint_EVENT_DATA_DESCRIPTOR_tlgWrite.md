# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)

- ea: `0x180002e00`
- end: `0x180002f4e`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z`
- size: `334`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000f350`
- `0x18001097c`

## callees

- `0x180001c98`
- `0x180002560`
- `0x1800036a0`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
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
        __int64 a19)
{
  struct _EVENT_DATA_DESCRIPTOR v20; // [rsp+90h] [rbp-128h] BYREF
  _BYTE v21[240]; // [rsp+B0h] [rbp-108h] BYREF

  _tlgDataDescInit<_tlgIndexSequence<15,0,1,2,3,4,5,6,7,8,9,10,11,12,13,14>>::Fill<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
    (__int64)v21,
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
    a19);
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, a3, a4, 0x11u, &v20);
}

```

## disassembly

```asm
0x180002e00  mov     [rsp+arg_18], r9
0x180002e05  mov     [rsp+arg_10], r8
0x180002e0a  mov     [rsp+arg_8], rdx
0x180002e0f  mov     [rsp+arg_0], rcx
0x180002e14  sub     rsp, 1B8h
0x180002e1b  mov     rax, cs:__security_cookie
0x180002e22  xor     rax, rsp
0x180002e25  mov     [rsp+1B8h+var_18], rax
0x180002e2d  mov     [rsp+1B8h+var_138], 11h
0x180002e38  lea     rax, [rsp+1B8h+var_108]
0x180002e40  mov     rcx, [rsp+1B8h+arg_90]
0x180002e48  mov     [rsp+1B8h+var_140], rcx
0x180002e4d  mov     rcx, [rsp+1B8h+arg_88]
0x180002e55  mov     [rsp+1B8h+var_148], rcx
0x180002e5a  mov     rcx, [rsp+1B8h+arg_80]
0x180002e62  mov     [rsp+1B8h+var_150], rcx
0x180002e67  mov     rcx, [rsp+1B8h+arg_78]
0x180002e6f  mov     [rsp+1B8h+var_158], rcx
0x180002e74  mov     rcx, [rsp+1B8h+arg_70]
0x180002e7c  mov     [rsp+1B8h+var_160], rcx
0x180002e81  mov     rcx, [rsp+1B8h+arg_68]
0x180002e89  mov     [rsp+1B8h+var_168], rcx
0x180002e8e  mov     rcx, [rsp+1B8h+arg_60]
0x180002e96  mov     [rsp+1B8h+var_170], rcx
0x180002e9b  mov     rcx, [rsp+1B8h+arg_58]
0x180002ea3  mov     [rsp+1B8h+var_178], rcx
0x180002ea8  mov     rcx, [rsp+1B8h+arg_50]
0x180002eb0  mov     [rsp+1B8h+var_180], rcx
0x180002eb5  mov     rcx, [rsp+1B8h+arg_48]
0x180002ebd  mov     [rsp+1B8h+var_188], rcx
0x180002ec2  mov     rcx, [rsp+1B8h+arg_40]
0x180002eca  mov     [rsp+1B8h+var_190], rcx
0x180002ecf  mov     rcx, [rsp+1B8h+arg_38]
0x180002ed7  mov     [rsp+1B8h+var_198], rcx
0x180002edc  mov     r9, [rsp+1B8h+arg_30]
0x180002ee4  mov     r8, [rsp+1B8h+arg_28]
0x180002eec  mov     rdx, [rsp+1B8h+arg_20]
0x180002ef4  mov     rcx, rax
0x180002ef7  call    ??$Fill@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgDataDescInit@U?$_tlgIndexSequence@$0P@$0A@$00$01$02$03$04$05$06$07$08$09$0L@$0M@$0N@$0O@@@@@SAXPEAU_EVENT_DATA_DESCRIPTOR@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@232AEBU?$_tlgWrapSz@G@@23234234@Z
0x180002efc  lea     rax, [rsp+1B8h+var_128]
0x180002f04  mov     [rsp+1B8h+var_190], rax
0x180002f09  mov     dword ptr [rsp+1B8h+var_198], 11h
0x180002f11  mov     r9, [rsp+1B8h+arg_18]
0x180002f19  mov     r8, [rsp+1B8h+arg_10]
0x180002f21  mov     rdx, [rsp+1B8h+arg_8]
0x180002f29  mov     rcx, [rsp+1B8h+arg_0]
0x180002f31  call    _tlgWriteTransfer_EventWriteTransfer
0x180002f36  mov     rcx, [rsp+1B8h+var_18]
0x180002f3e  xor     rcx, rsp; StackCookie
0x180002f41  call    __security_check_cookie
0x180002f46  add     rsp, 1B8h
0x180002f4d  retn
```
