# SvchostPushServiceGlobalsEx(_SVCHOST_GLOBAL_DATA_EX_V1 *)

- ea: `0x180003af0`
- end: `0x180003af8`
- name: `?SvchostPushServiceGlobalsEx@@YAXPEAU_SVCHOST_GLOBAL_DATA_EX_V1@@@Z`
- size: `8`
- prototype: `void __fastcall(struct _SVCHOST_GLOBAL_DATA_EX_V1 *)`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task`

## pseudocode

```c
void __fastcall SvchostPushServiceGlobalsEx(struct _SVCHOST_GLOBAL_DATA_EX_V1 *a1)
{
  qword_18001C300 = (__int64)a1;
}

```

## disassembly

```asm
0x180003af0  mov     cs:qword_18001C300, rcx
0x180003af7  retn
```
