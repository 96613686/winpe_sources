# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)

- ea: `0x140001008`
- end: `0x140001044`
- name: `??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z`
- size: `60`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1400091b0`
- `0x1400091f0`

## callees

- `0x14000126c`
- `0x1400096d0`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        __int64 a1,
        __int64 a2)
{
  return tlgWriteTransfer_EventWriteTransfer(a1, a2);
}

```

## disassembly

```asm
0x140001008  sub     rsp, 68h
0x14000100c  mov     rax, cs:__security_cookie
0x140001013  xor     rax, rsp
0x140001016  mov     [rsp+68h+var_18], rax
0x14000101b  lea     rax, [rsp+68h+var_38]
0x140001020  mov     [rsp+68h+var_40], rax
0x140001025  mov     [rsp+68h+var_48], 2
0x14000102d  call    _tlgWriteTransfer_EventWriteTransfer
0x140001032  mov     rcx, [rsp+68h+var_18]
0x140001037  xor     rcx, rsp; StackCookie
0x14000103a  call    __security_check_cookie
0x14000103f  add     rsp, 68h
0x140001043  retn
```
