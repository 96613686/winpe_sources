# _tlgWriteActivityAutoStop<0,5>(_tlgProvider_t const *,_GUID const *)

- ea: `0x1400127f4`
- end: `0x140012813`
- name: `??$_tlgWriteActivityAutoStop@$0A@$04@@YAXPEBU_tlgProvider_t@@PEBU_GUID@@@Z`
- size: `31`
- prototype: `__int64 __fastcall(unsigned int *, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140012968`

## callees

- `0x14000132c`
- `0x1400127f4`

## pseudocode

```c
__int64 __fastcall _tlgWriteActivityAutoStop<0,5>(unsigned int *a1, __int64 a2)
{
  __int64 result; // rax

  result = *a1;
  if ( (unsigned int)result > 5 )
    return _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
             a1,
             &byte_14001F67F,
             a2);
  return result;
}

```

## disassembly

```asm
0x1400127f4  sub     rsp, 28h
0x1400127f8  mov     eax, [rcx]
0x1400127fa  cmp     eax, 5
0x1400127fd  jbe     short loc_14001280E
0x1400127ff  mov     r8, rdx
0x140012802  lea     rdx, byte_14001F67F
0x140012809  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x14001280e  add     rsp, 28h
0x140012812  retn
```
