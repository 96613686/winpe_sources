# _tlgWriteActivityAutoStop<35184372088832,5>(_tlgProvider_t const *,_GUID const *)

- ea: `0x1400091b0`
- end: `0x1400091e8`
- name: `??$_tlgWriteActivityAutoStop@$0CAAAAAAAAAAA@$04@@YAXPEBU_tlgProvider_t@@PEBU_GUID@@@Z`
- size: `56`
- prototype: `__int64 __fastcall(unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1400092d4`

## callees

- `0x140001008`
- `0x140001248`
- `0x1400091b0`

## pseudocode

```c
__int64 __fastcall _tlgWriteActivityAutoStop<35184372088832,5>(unsigned int *a1)
{
  __int64 result; // rax
  __int64 v2; // rcx
  __int64 v3; // r10

  result = *a1;
  if ( (unsigned int)result > 5 )
  {
    result = tlgKeywordOn(a1, 0x200000000000LL);
    if ( (_BYTE)result )
      return _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
               v2,
               byte_14000E9C5,
               v3,
               0);
  }
  return result;
}

```

## disassembly

```asm
0x1400091b0  sub     rsp, 28h
0x1400091b4  mov     eax, [rcx]
0x1400091b6  mov     r10, rdx
0x1400091b9  cmp     eax, 5
0x1400091bc  jbe     short loc_1400091E3
0x1400091be  mov     rdx, 200000000000h
0x1400091c8  call    _tlgKeywordOn
0x1400091cd  test    al, al
0x1400091cf  jz      short loc_1400091E3
0x1400091d1  xor     r9d, r9d
0x1400091d4  lea     rdx, byte_14000E9C5
0x1400091db  mov     r8, r10
0x1400091de  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1400091e3  add     rsp, 28h
0x1400091e7  retn
```
