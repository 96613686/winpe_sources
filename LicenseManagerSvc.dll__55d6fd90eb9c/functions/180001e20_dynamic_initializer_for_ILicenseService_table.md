# _dynamic_initializer_for__ILicenseService_table__

- ea: `0x180001e20`
- end: `0x180001e60`
- name: `_dynamic_initializer_for__ILicenseService_table__`
- size: `64`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## import_xrefs

- `RPCRT4!NdrServerCall2` at `0x180001e20`

## pseudocode

```c
void (__stdcall *dynamic_initializer_for__ILicenseService_table__())(PRPC_MESSAGE pRpcMsg)
{
  void (__stdcall *result)(PRPC_MESSAGE); // rax

  result = NdrServerCall2;
  qword_180021A60 = (__int64)NdrServerCall2;
  qword_180021A68 = (__int64)NdrServerCall2;
  qword_180021A70 = (__int64)NdrServerCall2;
  qword_180021A78 = (__int64)NdrServerCall2;
  qword_180021A80 = (__int64)NdrServerCall2;
  qword_180021A88 = (__int64)NdrServerCall2;
  qword_180021A90 = (__int64)NdrServerCall2;
  qword_180021A98 = (__int64)NdrServerCall2;
  return result;
}

```

## disassembly

```asm
0x180001e20  mov     rax, cs:__imp_NdrServerCall2
0x180001e27  mov     cs:qword_180021A60, rax
0x180001e2e  mov     cs:qword_180021A68, rax
0x180001e35  mov     cs:qword_180021A70, rax
0x180001e3c  mov     cs:qword_180021A78, rax
0x180001e43  mov     cs:qword_180021A80, rax
0x180001e4a  mov     cs:qword_180021A88, rax
0x180001e51  mov     cs:qword_180021A90, rax
0x180001e58  mov     cs:qword_180021A98, rax
0x180001e5f  retn
```
