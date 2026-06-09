# CVssWriter::OnBackupShutdown(_GUID)

- ea: `0x1800074b0`
- end: `0x1800074b3`
- name: `?OnBackupShutdown@CVssWriter@@UEAA_NU_GUID@@@Z`
- size: `3`
- prototype: `bool __fastcall(CVssWriter *__hidden this, struct _GUID *__struct_ptr)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
char __fastcall CVssWriter::OnBackupShutdown(CVssWriter *this, struct _GUID *a2)
{
  return 1;
}

```

## disassembly

```asm
0x1800074b0  mov     al, 1
0x1800074b2  retn
```
