# std::shared_ptr<PCLmWriter::IObject const>::~shared_ptr<PCLmWriter::IObject const>(void)

- ea: `0x18000f6b8`
- end: `0x18000f6cf`
- name: `??1?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@QEAA@XZ`
- size: `23`
- prototype: ``
- caller_count: `52`
- callee_count: `2`
- tags: ``

## callers

- `0x18001d428`
- `0x18001d46f`
- `0x18001d635`
- `0x18001d647`
- `0x18001d6a8`
- `0x18001d6e0`
- `0x18001d7a4`
- `0x18001d7b6`
- `0x18001d7e2`
- `0x18001d88f`
- `0x18001d8b3`
- `0x18001d8c5`
- `0x18001d8d7`
- `0x18001d8e9`
- `0x18001d8fb`
- `0x18001d91f`
- `0x18001d931`
- `0x18001d943`
- `0x18001d967`
- `0x18001d98b`
- `0x18001d99d`
- `0x18001d9af`
- `0x18001d9d3`
- `0x18001d9e5`
- `0x18001da3f`
- `0x18001da51`
- `0x18001da63`
- `0x18001da87`
- `0x18001da99`
- `0x18001daab`
- `0x18001dabd`
- `0x18001daf3`
- `0x18001db05`
- `0x18001db17`
- `0x18001db29`
- `0x18001db4d`
- `0x18001dbcb`
- `0x18001dbdd`
- `0x18001dbef`
- `0x18001dc01`
- `0x18001dc13`
- `0x18001dc42`
- `0x18001de82`
- `0x18001debc`
- `0x18001dee0`
- `0x18001def6`
- `0x18001df0c`
- `0x18001df22`
- `0x18001df38`
- `0x18001dff8`

## callees

- `0x18000f6b8`
- `0x1800101cc`

## pseudocode

```c
void __fastcall std::shared_ptr<PCLmWriter::IObject const>::~shared_ptr<PCLmWriter::IObject const>(__int64 a1)
{
  std::_Ref_count_base *v1; // rcx

  v1 = *(std::_Ref_count_base **)(a1 + 8);
  if ( v1 )
    std::_Ref_count_base::_Decref(v1);
}

```

## disassembly

```asm
0x18000f6b8  sub     rsp, 28h
0x18000f6bc  mov     rcx, [rcx+8]; this
0x18000f6c0  test    rcx, rcx
0x18000f6c3  jz      short loc_18000F6CA
0x18000f6c5  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ
0x18000f6ca  add     rsp, 28h
0x18000f6ce  retn
```
