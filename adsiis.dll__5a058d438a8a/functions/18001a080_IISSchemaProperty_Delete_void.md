# IISSchemaProperty::Delete(void *)

- ea: `0x18001a080`
- end: `0x18001a093`
- name: `?Delete@IISSchemaProperty@@SAXPEAX@Z`
- size: `19`
- prototype: `void __fastcall(void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x180019cb4`
- `0x18001a080`

## pseudocode

```c
void __fastcall IISSchemaProperty::Delete(IISSchemaProperty *a1, unsigned int a2)
{
  if ( a1 )
    IISSchemaProperty::`scalar deleting destructor'(a1, a2);
}

```

## disassembly

```asm
0x18001a080  sub     rsp, 28h
0x18001a084  test    rcx, rcx
0x18001a087  jz      short loc_18001A08E
0x18001a089  call    ??_GIISSchemaProperty@@QEAAPEAXI@Z; IISSchemaProperty::`scalar deleting destructor'(uint)
0x18001a08e  add     rsp, 28h
0x18001a092  retn
```
