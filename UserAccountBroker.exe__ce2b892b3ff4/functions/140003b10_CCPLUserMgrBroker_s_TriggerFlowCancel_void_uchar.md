# CCPLUserMgrBroker::_s_TriggerFlowCancel(void *,uchar)

- ea: `0x140003b10`
- end: `0x140003b28`
- name: `?_s_TriggerFlowCancel@CCPLUserMgrBroker@@CAXPEAXE@Z`
- size: `24`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140003b10`

## import_xrefs

- `KERNEL32!SetEvent` at `0x140003b1d`
- `KERNEL32!SetEvent` at `0x140003b1d`

## pseudocode

```c
void __fastcall CCPLUserMgrBroker::_s_TriggerFlowCancel(_QWORD *a1)
{
  void *v1; // rcx

  v1 = (void *)a1[4];
  if ( v1 )
    SetEvent(v1);
}

```

## disassembly

```asm
0x140003b10  sub     rsp, 28h
0x140003b14  mov     rcx, [rcx+20h]; hEvent
0x140003b18  test    rcx, rcx
0x140003b1b  jz      short loc_140003B23
0x140003b1d  call    cs:__imp_SetEvent
0x140003b23  add     rsp, 28h
0x140003b27  retn
```
