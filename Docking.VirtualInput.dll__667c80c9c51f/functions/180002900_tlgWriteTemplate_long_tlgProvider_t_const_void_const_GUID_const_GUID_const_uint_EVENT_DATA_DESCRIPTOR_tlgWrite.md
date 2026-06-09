# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)

- ea: `0x180002900`
- end: `0x180002985`
- name: `??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z`
- size: `133`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000bd7c`

## callees

- `0x180001c98`
- `0x180001d98`
- `0x1800036a0`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        __int64 a1,
        unsigned __int8 *a2,
        const GUID *a3,
        const GUID *a4)
{
  struct _EVENT_DATA_DESCRIPTOR v5; // [rsp+38h] [rbp-40h] BYREF
  _BYTE v6[8]; // [rsp+58h] [rbp-20h] BYREF

  ___Fill___V____tlgDataDescInit_U___tlgIndexSequence__0A__S____SAXPEAU_EVENT_DATA_DESCRIPTOR___Z(v6);
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, a3, a4, 2u, &v5);
}

```

## disassembly

```asm
0x180002900  mov     [rsp+arg_18], r9
0x180002905  mov     [rsp+arg_10], r8
0x18000290a  mov     [rsp+arg_8], rdx
0x18000290f  mov     [rsp+arg_0], rcx
0x180002914  sub     rsp, 78h
0x180002918  mov     rax, cs:__security_cookie
0x18000291f  xor     rax, rsp
0x180002922  mov     [rsp+78h+var_18], rax
0x180002927  mov     [rsp+78h+var_48], 2
0x18000292f  lea     rax, [rsp+78h+var_20]
0x180002934  mov     rcx, rax
0x180002937  call    ??$Fill@$$V@?$_tlgDataDescInit@U?$_tlgIndexSequence@$0A@$S@@@@SAXPEAU_EVENT_DATA_DESCRIPTOR@@@Z
0x18000293c  lea     rax, [rsp+78h+var_40]
0x180002941  mov     [rsp+78h+var_50], rax
0x180002946  mov     [rsp+78h+var_58], 2
0x18000294e  mov     r9, [rsp+78h+arg_18]
0x180002956  mov     r8, [rsp+78h+arg_10]
0x18000295e  mov     rdx, [rsp+78h+arg_8]
0x180002966  mov     rcx, [rsp+78h+arg_0]
0x18000296e  call    _tlgWriteTransfer_EventWriteTransfer
0x180002973  mov     rcx, [rsp+78h+var_18]
0x180002978  xor     rcx, rsp; StackCookie
0x18000297b  call    __security_check_cookie
0x180002980  add     rsp, 78h
0x180002984  retn
```
