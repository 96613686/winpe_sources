# Comms::SerializeBuffer::GetBuffer(void)

- ea: `0x180002ad0`
- end: `0x180002ad5`
- name: `?GetBuffer@SerializeBuffer@Comms@@QEBAPEBV?$vector@EV?$allocator@E@utl@@@utl@@XZ`
- size: `5`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
__int64 __fastcall Comms::SerializeBuffer::GetBuffer(__int64 a1)
{
  return a1 + 24;
}

```

## disassembly

```asm
0x180002ad0  lea     rax, [rcx+18h]
0x180002ad4  retn
```
