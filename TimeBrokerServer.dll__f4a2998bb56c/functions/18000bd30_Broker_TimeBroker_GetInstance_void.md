# Broker::TimeBroker::GetInstance(void)

- ea: `0x18000bd30`
- end: `0x18000bd62`
- name: `?GetInstance@TimeBroker@Broker@@SA?AV?$shared_ptr@VTimeBroker@Broker@@@std@@XZ`
- size: `50`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `12`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000ef50`
- `0x180010e88`
- `0x1800118e0`
- `0x180011c20`
- `0x180013b40`
- `0x180014750`
- `0x1800147b0`
- `0x1800148a0`
- `0x180014900`
- `0x180014970`
- `0x1800149d0`
- `0x1800159b0`

## callees

- `0x18000bd30`

## pseudocode

```c
_QWORD *__fastcall Broker::TimeBroker::GetInstance(_QWORD *a1)
{
  __int64 v1; // rdx
  _QWORD *result; // rax

  v1 = (__int64)*(&Broker::TimeBroker::Instance + 1);
  *a1 = 0;
  a1[1] = 0;
  if ( v1 )
  {
    _InterlockedIncrement((volatile signed __int32 *)(v1 + 8));
    v1 = (__int64)*(&Broker::TimeBroker::Instance + 1);
  }
  *a1 = Broker::TimeBroker::Instance;
  result = a1;
  a1[1] = v1;
  return result;
}

```

## disassembly

```asm
0x18000bd30  mov     rdx, qword ptr cs:?Instance@TimeBroker@Broker@@0V?$shared_ptr@VTimeBroker@Broker@@@std@@A+8; std::shared_ptr<Broker::TimeBroker> Broker::TimeBroker::Instance
0x18000bd37  xor     eax, eax
0x18000bd39  mov     [rcx], rax
0x18000bd3c  mov     [rcx+8], rax
0x18000bd40  test    rdx, rdx
0x18000bd43  jz      short loc_18000BD50
0x18000bd45  lock inc dword ptr [rdx+8]
0x18000bd49  mov     rdx, qword ptr cs:?Instance@TimeBroker@Broker@@0V?$shared_ptr@VTimeBroker@Broker@@@std@@A+8; std::shared_ptr<Broker::TimeBroker> Broker::TimeBroker::Instance
0x18000bd50  mov     rax, qword ptr cs:?Instance@TimeBroker@Broker@@0V?$shared_ptr@VTimeBroker@Broker@@@std@@A; std::shared_ptr<Broker::TimeBroker> Broker::TimeBroker::Instance
0x18000bd57  mov     [rcx], rax
0x18000bd5a  mov     rax, rcx
0x18000bd5d  mov     [rcx+8], rdx
0x18000bd61  retn
```
