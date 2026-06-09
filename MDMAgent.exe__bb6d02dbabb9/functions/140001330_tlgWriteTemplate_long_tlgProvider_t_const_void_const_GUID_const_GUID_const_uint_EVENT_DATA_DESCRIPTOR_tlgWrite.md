# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)

- ea: `0x140001330`
- end: `0x140001370`
- name: `??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z`
- size: `64`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14001310c`

## callees

- `0x140001f60`
- `0x1400029c0`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        __int64 a1,
        unsigned __int8 *a2,
        const GUID *a3)
{
  struct _EVENT_DATA_DESCRIPTOR v4; // [rsp+30h] [rbp-38h] BYREF

  return tlgWriteTransfer_EventWriteTransfer(a1, a2, a3, 0, 2u, &v4);
}

```

## disassembly

```asm
0x140001330  sub     rsp, 68h
0x140001334  mov     rax, cs:__security_cookie
0x14000133b  xor     rax, rsp
0x14000133e  mov     [rsp+68h+var_18], rax
0x140001343  lea     rax, [rsp+68h+var_38]
0x140001348  xor     r9d, r9d
0x14000134b  mov     [rsp+68h+var_40], rax
0x140001350  mov     [rsp+68h+var_48], 2
0x140001358  call    _tlgWriteTransfer_EventWriteTransfer
0x14000135d  mov     rcx, [rsp+68h+var_18]
0x140001362  xor     rcx, rsp; StackCookie
0x140001365  call    __security_check_cookie
0x14000136a  add     rsp, 68h
0x14000136e  retn
```
