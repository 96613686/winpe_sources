# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)

- ea: `0x180002bdc`
- end: `0x180002c7d`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z`
- size: `161`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18001139c`
- `0x180017884`

## callees

- `0x180001c98`
- `0x180002324`
- `0x1800036a0`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
        __int64 a1,
        unsigned __int8 *a2,
        const GUID *a3,
        const GUID *a4,
        __int64 a5,
        __int64 a6)
{
  struct _EVENT_DATA_DESCRIPTOR v7; // [rsp+40h] [rbp-58h] BYREF
  _BYTE v8[32]; // [rsp+60h] [rbp-38h] BYREF

  _tlgDataDescInit<_tlgIndexSequence<2,0,1>>::Fill<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(v8, a5, a6);
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, a3, a4, 4u, &v7);
}

```

## disassembly

```asm
0x180002bdc  mov     [rsp+arg_18], r9
0x180002be1  mov     [rsp+arg_10], r8
0x180002be6  mov     [rsp+arg_8], rdx
0x180002beb  mov     [rsp+arg_0], rcx
0x180002bf0  sub     rsp, 98h
0x180002bf7  mov     rax, cs:__security_cookie
0x180002bfe  xor     rax, rsp
0x180002c01  mov     [rsp+98h+var_18], rax
0x180002c09  mov     [rsp+98h+var_68], 4
0x180002c11  lea     rax, [rsp+98h+var_38]
0x180002c16  mov     r8, [rsp+98h+arg_28]
0x180002c1e  mov     rdx, [rsp+98h+arg_20]
0x180002c26  mov     rcx, rax
0x180002c29  call    ??$Fill@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgDataDescInit@U?$_tlgIndexSequence@$01$0A@$00@@@@SAXPEAU_EVENT_DATA_DESCRIPTOR@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z
0x180002c2e  lea     rax, [rsp+98h+var_58]
0x180002c33  mov     [rsp+98h+var_70], rax
0x180002c38  mov     [rsp+98h+var_78], 4
0x180002c40  mov     r9, [rsp+98h+arg_18]
0x180002c48  mov     r8, [rsp+98h+arg_10]
0x180002c50  mov     rdx, [rsp+98h+arg_8]
0x180002c58  mov     rcx, [rsp+98h+arg_0]
0x180002c60  call    _tlgWriteTransfer_EventWriteTransfer
0x180002c65  mov     rcx, [rsp+98h+var_18]
0x180002c6d  xor     rcx, rsp; StackCookie
0x180002c70  call    __security_check_cookie
0x180002c75  add     rsp, 98h
0x180002c7c  retn
```
