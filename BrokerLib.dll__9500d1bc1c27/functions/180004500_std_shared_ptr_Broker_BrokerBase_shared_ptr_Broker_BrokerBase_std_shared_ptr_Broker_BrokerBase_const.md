# std::shared_ptr<Broker::BrokerBase>::shared_ptr<Broker::BrokerBase>(std::shared_ptr<Broker::BrokerBase> const &)

- ea: `0x180004500`
- end: `0x180004528`
- name: `??0?$shared_ptr@VBrokerBase@Broker@@@std@@QEAA@AEBV01@@Z`
- size: `40`
- prototype: ``
- caller_count: `19`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800012cc`
- `0x180003a60`
- `0x180003db0`
- `0x180004140`
- `0x180004700`
- `0x1800050d0`
- `0x18000a18c`
- `0x18000c970`
- `0x18000efc4`
- `0x180011b9c`
- `0x180014558`
- `0x180014d90`
- `0x1800171e4`
- `0x1800178fc`
- `0x180018004`
- `0x1800183bc`
- `0x1800186a8`
- `0x1800192fc`
- `0x18001d73f`

## callees

- `0x180004500`

## pseudocode

```c
_QWORD *__fastcall std::shared_ptr<Broker::BrokerBase>::shared_ptr<Broker::BrokerBase>(_QWORD *a1, _QWORD *a2)
{
  __int64 v2; // rax

  *a1 = 0;
  a1[1] = 0;
  v2 = a2[1];
  if ( v2 )
    _InterlockedIncrement((volatile signed __int32 *)(v2 + 8));
  *a1 = *a2;
  a1[1] = a2[1];
  return a1;
}

```

## disassembly

```asm
0x180004500  xor     eax, eax
0x180004502  mov     [rcx], rax
0x180004505  mov     [rcx+8], rax
0x180004509  mov     rax, [rdx+8]
0x18000450d  test    rax, rax
0x180004510  jz      short loc_180004516
0x180004512  lock inc dword ptr [rax+8]
0x180004516  mov     rax, [rdx]
0x180004519  mov     [rcx], rax
0x18000451c  mov     rax, [rdx+8]
0x180004520  mov     [rcx+8], rax
0x180004524  mov     rax, rcx
0x180004527  retn
```
