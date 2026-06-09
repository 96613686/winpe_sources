# Comms::DeserializeObject(Comms::Deserializer &,ushort const * &)

- ea: `0x180003160`
- end: `0x180003165`
- name: `?DeserializeObject@Comms@@YA_NAEAVDeserializer@1@AEAPEBG@Z`
- size: `5`
- prototype: `char __fastcall(void ***this, struct Comms::Deserializer *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180003050`

## pseudocode

```c
// attributes: thunk
char __fastcall Comms::DeserializeObject(void ***this, struct Comms::Deserializer *a2, unsigned __int16 **a3)
{
  return ?DeserializeObject@Comms@@YA_NAEAVDeserializer@1@AEAPEAG@Z(this, a2, a3);
}

```

## disassembly

```asm
0x180003160  jmp     ?DeserializeObject@Comms@@YA_NAEAVDeserializer@1@AEAPEAG@Z; Comms::DeserializeObject(Comms::Deserializer &,ushort * &)
```
