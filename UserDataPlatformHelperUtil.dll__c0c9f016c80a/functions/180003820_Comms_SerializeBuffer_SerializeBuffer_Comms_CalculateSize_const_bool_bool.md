# Comms::SerializeBuffer::SerializeBuffer(Comms::CalculateSize const &,bool,bool)

- ea: `0x180003820`
- end: `0x180003852`
- name: `??0SerializeBuffer@Comms@@QEAA@AEBVCalculateSize@1@_N1@Z`
- size: `50`
- prototype: `Comms::SerializeBuffer *__fastcall(Comms::SerializeBuffer *this, const struct Comms::CalculateSize *, char, char)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
Comms::SerializeBuffer *__fastcall Comms::SerializeBuffer::SerializeBuffer(
        Comms::SerializeBuffer *this,
        const struct Comms::CalculateSize *a2,
        char a3,
        char a4)
{
  Comms::SerializeBuffer *result; // rax

  *(_QWORD *)this = &Comms::SerializeBuffer::`vftable';
  *((_QWORD *)this + 1) = *((_QWORD *)a2 + 1);
  *((_QWORD *)this + 3) = -1;
  *((_QWORD *)this + 4) = -1;
  *((_QWORD *)this + 5) = -1;
  result = this;
  *((_BYTE *)this + 16) = a3;
  *((_BYTE *)this + 17) = a4;
  *((_BYTE *)this + 48) = 0;
  return result;
}

```

## disassembly

```asm
0x180003820  lea     rax, ??_7SerializeBuffer@Comms@@6B@; const Comms::SerializeBuffer::`vftable'
0x180003827  mov     [rcx], rax
0x18000382a  mov     rax, [rdx+8]
0x18000382e  mov     [rcx+8], rax
0x180003832  or      rax, 0FFFFFFFFFFFFFFFFh
0x180003836  mov     [rcx+18h], rax
0x18000383a  mov     [rcx+20h], rax
0x18000383e  mov     [rcx+28h], rax
0x180003842  mov     rax, rcx
0x180003845  mov     [rcx+10h], r8b
0x180003849  mov     [rcx+11h], r9b
0x18000384d  mov     byte ptr [rcx+30h], 0
0x180003851  retn
```
