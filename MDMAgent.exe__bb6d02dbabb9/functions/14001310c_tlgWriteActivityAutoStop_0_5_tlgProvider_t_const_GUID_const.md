# _tlgWriteActivityAutoStop<0,5>(_tlgProvider_t const *,_GUID const *)

- ea: `0x14001310c`
- end: `0x14001312c`
- name: `??$_tlgWriteActivityAutoStop@$0A@$04@@YAXPEBU_tlgProvider_t@@PEBU_GUID@@@Z`
- size: `32`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14001328c`

## callees

- `0x140001330`
- `0x14001310c`

## pseudocode

```c
__int64 __fastcall _tlgWriteActivityAutoStop<0,5>(unsigned int *a1, __int64 a2)
{
  __int64 result; // rax

  result = *a1;
  if ( (unsigned int)result > 5 )
    return _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
             a1,
             &byte_14002067F,
             a2);
  return result;
}

```

## disassembly

```asm
0x14001310c  sub     rsp, 28h
0x140013110  mov     eax, [rcx]
0x140013112  cmp     eax, 5
0x140013115  jbe     short loc_140013126
0x140013117  mov     r8, rdx
0x14001311a  lea     rdx, byte_14002067F
0x140013121  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x140013126  add     rsp, 28h
0x14001312a  retn
```
