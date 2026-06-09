# _tlgWriteActivityAutoStop<35184372088832,5>(_tlgProvider_t const *,_GUID const *)

- ea: `0x1400097d4`
- end: `0x14000980d`
- name: `??$_tlgWriteActivityAutoStop@$0CAAAAAAAAAAA@$04@@YAXPEBU_tlgProvider_t@@PEBU_GUID@@@Z`
- size: `57`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140009900`

## callees

- `0x140001008`
- `0x140001258`
- `0x1400097d4`

## pseudocode

```c
__int64 __fastcall _tlgWriteActivityAutoStop<35184372088832,5>(unsigned int *a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax
  __int64 v5; // rcx
  __int64 v6; // r10

  result = *a1;
  if ( (unsigned int)result > 5 )
  {
    result = tlgKeywordOn(a1, 0x200000000000LL, a3, a4);
    if ( (_BYTE)result )
      return _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
               v5,
               byte_14000F9C5,
               v6);
  }
  return result;
}

```

## disassembly

```asm
0x1400097d4  sub     rsp, 28h
0x1400097d8  mov     eax, [rcx]
0x1400097da  mov     r10, rdx
0x1400097dd  cmp     eax, 5
0x1400097e0  jbe     short loc_140009807
0x1400097e2  mov     rdx, 200000000000h
0x1400097ec  call    _tlgKeywordOn
0x1400097f1  test    al, al
0x1400097f3  jz      short loc_140009807
0x1400097f5  xor     r9d, r9d
0x1400097f8  lea     rdx, byte_14000F9C5
0x1400097ff  mov     r8, r10
0x140009802  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x140009807  add     rsp, 28h
0x14000980b  retn
```
