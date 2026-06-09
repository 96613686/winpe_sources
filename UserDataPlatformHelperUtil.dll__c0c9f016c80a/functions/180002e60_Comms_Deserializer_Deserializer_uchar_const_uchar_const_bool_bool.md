# Comms::Deserializer::Deserializer(uchar const *,uchar const *,bool,bool)

- ea: `0x180002e60`
- end: `0x180002e86`
- name: `??0Deserializer@Comms@@QEAA@PEBE0_N1@Z`
- size: `38`
- prototype: `Comms::Deserializer *__fastcall(Comms::Deserializer *this, const unsigned __int8 *, const unsigned __int8 *, char, bool)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## pseudocode

```c
Comms::Deserializer *__fastcall Comms::Deserializer::Deserializer(
        Comms::Deserializer *this,
        const unsigned __int8 *a2,
        const unsigned __int8 *a3,
        char a4,
        bool a5)
{
  Comms::Deserializer *result; // rax

  *((_BYTE *)this + 17) = a5;
  *((_QWORD *)this + 3) = -1;
  *((_QWORD *)this + 4) = -1;
  *((_QWORD *)this + 5) = -1;
  result = this;
  *(_QWORD *)this = a2;
  *((_QWORD *)this + 1) = a3;
  *((_BYTE *)this + 16) = a4;
  return result;
}

```

## disassembly

```asm
0x180002e60  mov     al, [rsp+arg_20]
0x180002e64  mov     [rcx+11h], al
0x180002e67  or      rax, 0FFFFFFFFFFFFFFFFh
0x180002e6b  mov     [rcx+18h], rax
0x180002e6f  mov     [rcx+20h], rax
0x180002e73  mov     [rcx+28h], rax
0x180002e77  mov     rax, rcx
0x180002e7a  mov     [rcx], rdx
0x180002e7d  mov     [rcx+8], r8
0x180002e81  mov     [rcx+10h], r9b
0x180002e85  retn
```
