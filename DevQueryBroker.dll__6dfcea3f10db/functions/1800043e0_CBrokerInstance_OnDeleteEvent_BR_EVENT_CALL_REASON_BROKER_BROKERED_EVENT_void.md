# CBrokerInstance::OnDeleteEvent(_BR_EVENT_CALL_REASON,_BROKER *,_BROKERED_EVENT *,void *)

- ea: `0x1800043e0`
- end: `0x1800043f8`
- name: `?OnDeleteEvent@CBrokerInstance@@CAKW4_BR_EVENT_CALL_REASON@@PEAU_BROKER@@PEAU_BROKERED_EVENT@@PEAX@Z`
- size: `24`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, struct _BrokeredQueryContext *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180002a68`
- `0x18000314c`

## pseudocode

```c
__int64 __fastcall CBrokerInstance::OnDeleteEvent(__int64 a1, __int64 a2, __int64 a3, struct _BrokeredQueryContext *a4)
{
  CActiveQueries::RemoveBrokeredQueryContext(a4);
  CheckIdleStop();
  return 0;
}

```

## disassembly

```asm
0x1800043e0  sub     rsp, 28h
0x1800043e4  mov     rcx, r9; struct _BrokeredQueryContext *
0x1800043e7  call    ?RemoveBrokeredQueryContext@CActiveQueries@@SAXPEAU_BrokeredQueryContext@@@Z; CActiveQueries::RemoveBrokeredQueryContext(_BrokeredQueryContext *)
0x1800043ec  call    ?CheckIdleStop@@YAXXZ; CheckIdleStop(void)
0x1800043f1  xor     eax, eax
0x1800043f3  add     rsp, 28h
0x1800043f7  retn
```
