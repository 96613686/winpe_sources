# Comms::CalculateSize::CalculateSize(bool,bool)

- ea: `0x1800037f0`
- end: `0x18000380d`
- name: `??0CalculateSize@Comms@@QEAA@_N0@Z`
- size: `29`
- prototype: `Comms::CalculateSize *__fastcall(Comms::CalculateSize *this, char, char)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
Comms::CalculateSize *__fastcall Comms::CalculateSize::CalculateSize(Comms::CalculateSize *this, char a2, char a3)
{
  Comms::CalculateSize *result; // rax

  *((_QWORD *)this + 1) = 0;
  *(_QWORD *)this = &Comms::CalculateSize::`vftable';
  result = this;
  *((_BYTE *)this + 16) = a2;
  *((_BYTE *)this + 17) = a3;
  return result;
}

```

## disassembly

```asm
0x1800037f0  lea     rax, ??_7CalculateSize@Comms@@6B@; const Comms::CalculateSize::`vftable'
0x1800037f7  mov     qword ptr [rcx+8], 0
0x1800037ff  mov     [rcx], rax
0x180003802  mov     rax, rcx
0x180003805  mov     [rcx+10h], dl
0x180003808  mov     [rcx+11h], r8b
0x18000380c  retn
```
