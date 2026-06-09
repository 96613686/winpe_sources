# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)

- ea: `0x180002c84`
- end: `0x180002d2d`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z`
- size: `169`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x1800115ac`
- `0x1800117d0`
- `0x1800179c0`

## callees

- `0x180001c98`
- `0x1800023a0`
- `0x1800036a0`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        __int64 a1,
        unsigned __int8 *a2,
        const GUID *a3,
        const GUID *a4,
        __int64 a5,
        __int64 a6,
        __int64 a7)
{
  struct _EVENT_DATA_DESCRIPTOR v8; // [rsp+40h] [rbp-68h] BYREF
  _BYTE v9[48]; // [rsp+60h] [rbp-48h] BYREF

  _tlgDataDescInit<_tlgIndexSequence<3,0,1,2>>::Fill<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
    v9,
    a5,
    a6,
    a7);
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, a3, a4, 5u, &v8);
}

```

## disassembly

```asm
0x180002c84  mov     [rsp+arg_18], r9
0x180002c89  mov     [rsp+arg_10], r8
0x180002c8e  mov     [rsp+arg_8], rdx
0x180002c93  mov     [rsp+arg_0], rcx
0x180002c98  sub     rsp, 0A8h
0x180002c9f  mov     rax, cs:__security_cookie
0x180002ca6  xor     rax, rsp
0x180002ca9  mov     [rsp+0A8h+var_18], rax
0x180002cb1  mov     [rsp+0A8h+var_78], 5
0x180002cb9  lea     rax, [rsp+0A8h+var_48]
0x180002cbe  mov     r9, [rsp+0A8h+arg_30]
0x180002cc6  mov     r8, [rsp+0A8h+arg_28]
0x180002cce  mov     rdx, [rsp+0A8h+arg_20]
0x180002cd6  mov     rcx, rax
0x180002cd9  call    ??$Fill@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgDataDescInit@U?$_tlgIndexSequence@$02$0A@$00$01@@@@SAXPEAU_EVENT_DATA_DESCRIPTOR@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@2@Z
0x180002cde  lea     rax, [rsp+0A8h+var_68]
0x180002ce3  mov     [rsp+0A8h+var_80], rax
0x180002ce8  mov     [rsp+0A8h+var_88], 5
0x180002cf0  mov     r9, [rsp+0A8h+arg_18]
0x180002cf8  mov     r8, [rsp+0A8h+arg_10]
0x180002d00  mov     rdx, [rsp+0A8h+arg_8]
0x180002d08  mov     rcx, [rsp+0A8h+arg_0]
0x180002d10  call    _tlgWriteTransfer_EventWriteTransfer
0x180002d15  mov     rcx, [rsp+0A8h+var_18]
0x180002d1d  xor     rcx, rsp; StackCookie
0x180002d20  call    __security_check_cookie
0x180002d25  add     rsp, 0A8h
0x180002d2c  retn
```
