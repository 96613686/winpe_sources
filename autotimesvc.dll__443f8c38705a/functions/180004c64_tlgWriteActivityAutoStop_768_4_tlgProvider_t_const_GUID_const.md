# _tlgWriteActivityAutoStop<768,4>(_tlgProvider_t const *,_GUID const *)

- ea: `0x180004c64`
- end: `0x180004c9a`
- name: `??$_tlgWriteActivityAutoStop@$0DAA@$03@@YAXPEBU_tlgProvider_t@@PEBU_GUID@@@Z`
- size: `54`
- prototype: `__int64 __fastcall(unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180005620`

## callees

- `0x180001010`
- `0x1800012f0`
- `0x180004c64`

## pseudocode

```c
__int64 __fastcall _tlgWriteActivityAutoStop<768,4>(unsigned int *a1)
{
  __int64 result; // rax
  __int64 v2; // r8
  __int64 v3; // r10

  result = *a1;
  if ( (unsigned int)result > 4 )
  {
    result = tlgKeywordOn(a1, 768);
    if ( (_BYTE)result )
      return _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
               v3,
               qword_180016570,
               v2,
               0);
  }
  return result;
}

```

## disassembly

```asm
0x180004c64  sub     rsp, 28h
0x180004c68  mov     eax, [rcx]
0x180004c6a  mov     r8, rdx
0x180004c6d  mov     r10, rcx
0x180004c70  cmp     eax, 4
0x180004c73  jbe     short loc_180004C95
0x180004c75  mov     edx, 300h
0x180004c7a  call    _tlgKeywordOn
0x180004c7f  test    al, al
0x180004c81  jz      short loc_180004C95
0x180004c83  xor     r9d, r9d
0x180004c86  lea     rdx, qword_180016570
0x180004c8d  mov     rcx, r10
0x180004c90  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180004c95  add     rsp, 28h
0x180004c99  retn
```
