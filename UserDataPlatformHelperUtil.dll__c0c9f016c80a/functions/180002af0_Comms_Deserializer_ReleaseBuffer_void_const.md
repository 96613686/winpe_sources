# Comms::Deserializer::ReleaseBuffer(void const *)

- ea: `0x180002af0`
- end: `0x180002b10`
- name: `?ReleaseBuffer@Deserializer@Comms@@QEAAXPEBX@Z`
- size: `32`
- prototype: `void __fastcall(Comms::Deserializer *__hidden this, const void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180002af0`

## pseudocode

```c
void __fastcall Comms::Deserializer::ReleaseBuffer(Comms::Deserializer *this, const void *a2)
{
  const void **i; // rax

  for ( i = (const void **)*((_QWORD *)this + 3); i != *((const void ***)this + 4); ++i )
  {
    if ( *i == a2 )
    {
      *i = 0;
      return;
    }
  }
}

```

## disassembly

```asm
0x180002af0  mov     rax, [rcx+18h]
0x180002af4  mov     r8, [rcx+20h]
0x180002af8  cmp     rax, r8
0x180002afb  jz      short locret_180002B0F
0x180002afd  cmp     [rax], rdx
0x180002b00  jz      short loc_180002B08
0x180002b02  add     rax, 8
0x180002b06  jmp     short loc_180002AF8
0x180002b08  mov     qword ptr [rax], 0
0x180002b0f  retn
```
