# _dynamic_initializer_for__ILicenseService_NDR64__table__

- ea: `0x180001050`
- end: `0x180001090`
- name: `_dynamic_initializer_for__ILicenseService_NDR64__table__`
- size: `64`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## import_xrefs

- `RPCRT4!NdrServerCallAll` at `0x180001050`

## pseudocode

```c
void (__stdcall *dynamic_initializer_for__ILicenseService_NDR64__table__())(PRPC_MESSAGE pRpcMsg)
{
  void (__stdcall *result)(PRPC_MESSAGE); // rax

  result = NdrServerCallAll;
  qword_180021AB0 = (__int64)NdrServerCallAll;
  qword_180021AB8 = (__int64)NdrServerCallAll;
  qword_180021AC0 = (__int64)NdrServerCallAll;
  qword_180021AC8 = (__int64)NdrServerCallAll;
  qword_180021AD0 = (__int64)NdrServerCallAll;
  qword_180021AD8 = (__int64)NdrServerCallAll;
  qword_180021AE0 = (__int64)NdrServerCallAll;
  qword_180021AE8 = (__int64)NdrServerCallAll;
  return result;
}

```

## disassembly

```asm
0x180001050  mov     rax, cs:__imp_NdrServerCallAll
0x180001057  mov     cs:qword_180021AB0, rax
0x18000105e  mov     cs:qword_180021AB8, rax
0x180001065  mov     cs:qword_180021AC0, rax
0x18000106c  mov     cs:qword_180021AC8, rax
0x180001073  mov     cs:qword_180021AD0, rax
0x18000107a  mov     cs:qword_180021AD8, rax
0x180001081  mov     cs:qword_180021AE0, rax
0x180001088  mov     cs:qword_180021AE8, rax
0x18000108f  retn
```
