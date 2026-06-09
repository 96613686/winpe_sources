# Broker::SebBroker::GetInstance(void)

- ea: `0x180002680`
- end: `0x1800026ca`
- name: `?GetInstance@SebBroker@Broker@@SA?AV?$shared_ptr@VSebBroker@Broker@@@std@@XZ`
- size: `74`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `9`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001ef0`
- `0x1800020c0`
- `0x1800022b0`
- `0x1800029c0`
- `0x1800197fc`
- `0x18001aee0`
- `0x18001e150`
- `0x18001ea70`
- `0x18001eba0`

## callees

- `0x180002680`

## pseudocode

```c
__int64 __fastcall Broker::SebBroker::GetInstance(_QWORD *a1)
{
  __int128 v1; // rax

  *(_QWORD *)&v1 = Broker::SebBroker::Instance;
  if ( Broker::SebBroker::Instance && *(_BYTE *)Broker::SebBroker::Instance )
  {
    *a1 = 0;
    a1[1] = 0;
    *((_QWORD *)&v1 + 1) = *(&Broker::SebBroker::Instance + 1);
    if ( *(&Broker::SebBroker::Instance + 1) )
    {
      _InterlockedIncrement((volatile signed __int32 *)*(&Broker::SebBroker::Instance + 1) + 2);
      v1 = *(_OWORD *)&Broker::SebBroker::Instance;
    }
    *a1 = v1;
  }
  else
  {
    *((_QWORD *)&v1 + 1) = 0;
    *a1 = 0;
  }
  *(_QWORD *)&v1 = a1;
  a1[1] = *((_QWORD *)&v1 + 1);
  return v1;
}

```

## disassembly

```asm
0x180002680  mov     rax, qword ptr cs:?Instance@SebBroker@Broker@@0V?$shared_ptr@VSebBroker@Broker@@@std@@A; std::shared_ptr<Broker::SebBroker> Broker::SebBroker::Instance
0x180002687  test    rax, rax
0x18000268a  jz      short loc_1800026C3
0x18000268c  cmp     byte ptr [rax], 0
0x18000268f  jz      short loc_1800026C3
0x180002691  xor     edx, edx
0x180002693  mov     [rcx], rdx
0x180002696  mov     [rcx+8], rdx
0x18000269a  mov     rdx, qword ptr cs:?Instance@SebBroker@Broker@@0V?$shared_ptr@VSebBroker@Broker@@@std@@A+8; std::shared_ptr<Broker::SebBroker> Broker::SebBroker::Instance
0x1800026a1  test    rdx, rdx
0x1800026a4  jz      short loc_1800026B8
0x1800026a6  lock inc dword ptr [rdx+8]
0x1800026aa  mov     rdx, qword ptr cs:?Instance@SebBroker@Broker@@0V?$shared_ptr@VSebBroker@Broker@@@std@@A+8; std::shared_ptr<Broker::SebBroker> Broker::SebBroker::Instance
0x1800026b1  mov     rax, qword ptr cs:?Instance@SebBroker@Broker@@0V?$shared_ptr@VSebBroker@Broker@@@std@@A; std::shared_ptr<Broker::SebBroker> Broker::SebBroker::Instance
0x1800026b8  mov     [rcx], rax
0x1800026bb  mov     rax, rcx
0x1800026be  mov     [rcx+8], rdx
0x1800026c2  retn
0x1800026c3  xor     edx, edx
0x1800026c5  mov     [rcx], rdx
0x1800026c8  jmp     short loc_1800026BB
```
