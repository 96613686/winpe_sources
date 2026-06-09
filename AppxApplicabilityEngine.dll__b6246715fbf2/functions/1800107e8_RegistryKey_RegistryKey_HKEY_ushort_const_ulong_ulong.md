# RegistryKey::RegistryKey(HKEY__ *,ushort const *,ulong,ulong)

- ea: `0x1800107e8`
- end: `0x180010811`
- name: `??0RegistryKey@@QEAA@PEAUHKEY__@@PEBGKK@Z`
- size: `41`
- prototype: `RegistryKey *__fastcall(RegistryKey *this, HKEY, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180010754`
- `0x180020320`
- `0x1800207f0`

## callees

- `0x180020220`

## pseudocode

```c
RegistryKey *__fastcall RegistryKey::RegistryKey(RegistryKey *this, HKEY a2, const unsigned __int16 *a3)
{
  unsigned int v5; // [rsp+20h] [rbp-18h]
  unsigned int v6; // [rsp+28h] [rbp-10h]

  RegistryKey::RegistryKey(this, 0, a2, a3, v5, v6);
  *(_QWORD *)this = &RegistryKey::`vftable';
  return this;
}

```

## disassembly

```asm
0x1800107e8  push    rbx
0x1800107ea  sub     rsp, 30h
0x1800107ee  mov     r9, r8; unsigned __int16 *
0x1800107f1  mov     rbx, rcx
0x1800107f4  mov     r8, rdx; hKey
0x1800107f7  xor     edx, edx; void *
0x1800107f9  call    ??0RegistryKey@@QEAA@PEAXPEAUHKEY__@@PEBGKK@Z; RegistryKey::RegistryKey(void *,HKEY__ *,ushort const *,ulong,ulong)
0x1800107fe  lea     rax, ??_7RegistryKey@@6B@; const RegistryKey::`vftable'
0x180010805  mov     [rbx], rax
0x180010808  mov     rax, rbx
0x18001080b  add     rsp, 30h
0x18001080f  pop     rbx
0x180010810  retn
```
