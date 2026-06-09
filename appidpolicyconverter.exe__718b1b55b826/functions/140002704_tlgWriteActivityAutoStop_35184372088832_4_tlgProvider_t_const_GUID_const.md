# _tlgWriteActivityAutoStop<35184372088832,4>(_tlgProvider_t const *,_GUID const *)

- ea: `0x140002704`
- end: `0x140002735`
- name: `??$_tlgWriteActivityAutoStop@$0CAAAAAAAAAAA@$03@@YAXPEBU_tlgProvider_t@@PEBU_GUID@@@Z`
- size: `49`
- prototype: `__int64 __fastcall(unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000273c`

## callees

- `0x140001008`
- `0x1400013b8`
- `0x140002704`

## pseudocode

```c
__int64 __fastcall _tlgWriteActivityAutoStop<35184372088832,4>(unsigned int *a1)
{
  __int64 result; // rax
  __int64 v2; // r8
  __int64 v3; // r10

  result = *a1;
  if ( (unsigned int)result > 4 )
  {
    result = tlgKeywordOn(a1);
    if ( (_BYTE)result )
      return _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
               v3,
               byte_14001A639,
               v2,
               0);
  }
  return result;
}

```

## disassembly

```asm
0x140002704  sub     rsp, 28h
0x140002708  mov     eax, [rcx]
0x14000270a  mov     r8, rdx
0x14000270d  mov     r10, rcx
0x140002710  cmp     eax, 4
0x140002713  jbe     short loc_140002730
0x140002715  call    _tlgKeywordOn
0x14000271a  test    al, al
0x14000271c  jz      short loc_140002730
0x14000271e  xor     r9d, r9d
0x140002721  lea     rdx, byte_14001A639
0x140002728  mov     rcx, r10
0x14000272b  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x140002730  add     rsp, 28h
0x140002734  retn
```
