# Comms::DeserializeObject(Comms::Deserializer &,char const * &)

- ea: `0x180003150`
- end: `0x180003155`
- name: `?DeserializeObject@Comms@@YA_NAEAVDeserializer@1@AEAPEBD@Z`
- size: `5`
- prototype: `char __fastcall(size_t **this, struct Comms::Deserializer *, char **)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180002f70`

## pseudocode

```c
// attributes: thunk
char __fastcall Comms::DeserializeObject(size_t **this, struct Comms::Deserializer *a2, char **a3)
{
  return ?DeserializeObject@Comms@@YA_NAEAVDeserializer@1@AEAPEAD@Z(this, a2, a3);
}

```

## disassembly

```asm
0x180003150  jmp     ?DeserializeObject@Comms@@YA_NAEAVDeserializer@1@AEAPEAD@Z; Comms::DeserializeObject(Comms::Deserializer &,char * &)
```
