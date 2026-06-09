# Comms::DeserializeObject(Comms::Deserializer &,Comms::detail::NullType &)

- ea: `0x180003170`
- end: `0x180003173`
- name: `?DeserializeObject@Comms@@YA_NAEAVDeserializer@1@AEAVNullType@detail@1@@Z`
- size: `3`
- prototype: `char __fastcall(Comms *this, struct Comms::Deserializer *, struct Comms::detail::NullType *)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## pseudocode

```c
char __fastcall Comms::DeserializeObject(
        Comms *this,
        struct Comms::Deserializer *a2,
        struct Comms::detail::NullType *a3)
{
  return 1;
}

```

## disassembly

```asm
0x180003170  mov     al, 1; bool Comms::DeserializeObject(class Comms::Deserializer &, class Comms::detail::NullType &)
0x180003172  retn
```
