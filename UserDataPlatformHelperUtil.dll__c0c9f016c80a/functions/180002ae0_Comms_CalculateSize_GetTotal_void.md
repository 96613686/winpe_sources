# Comms::CalculateSize::GetTotal(void)

- ea: `0x180002ae0`
- end: `0x180002ae5`
- name: `?GetTotal@CalculateSize@Comms@@QEBA_KXZ`
- size: `5`
- prototype: `unsigned __int64 __fastcall(Comms::CalculateSize *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
unsigned __int64 __fastcall Comms::CalculateSize::GetTotal(Comms::CalculateSize *this)
{
  return *((_QWORD *)this + 1);
}

```

## disassembly

```asm
0x180002ae0  mov     rax, [rcx+8]
0x180002ae4  retn
```
