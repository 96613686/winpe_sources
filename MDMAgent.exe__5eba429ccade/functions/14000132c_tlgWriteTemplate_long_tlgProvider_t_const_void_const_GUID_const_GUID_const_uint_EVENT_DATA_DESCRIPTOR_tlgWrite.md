# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)

- ea: `0x14000132c`
- end: `0x14000136b`
- name: `??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z`
- size: `63`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400127f4`

## callees

- `0x140001f48`
- `0x140002930`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  _BYTE v4[32]; // [rsp+30h] [rbp-38h] BYREF

  return tlgWriteTransfer_EventWriteTransfer(a1, a2, a3, 0, 2, v4);
}

```

## disassembly

```asm
0x14000132c  sub     rsp, 68h
0x140001330  mov     rax, cs:__security_cookie
0x140001337  xor     rax, rsp
0x14000133a  mov     [rsp+68h+var_18], rax
0x14000133f  lea     rax, [rsp+68h+var_38]
0x140001344  xor     r9d, r9d
0x140001347  mov     [rsp+68h+var_40], rax
0x14000134c  mov     [rsp+68h+var_48], 2
0x140001354  call    _tlgWriteTransfer_EventWriteTransfer
0x140001359  mov     rcx, [rsp+68h+var_18]
0x14000135e  xor     rcx, rsp; StackCookie
0x140001361  call    __security_check_cookie
0x140001366  add     rsp, 68h
0x14000136a  retn
```
