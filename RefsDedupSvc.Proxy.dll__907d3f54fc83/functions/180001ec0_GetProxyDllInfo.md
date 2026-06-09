# GetProxyDllInfo

- ea: `0x180001ec0`
- end: `0x180001ed5`
- name: `GetProxyDllInfo`
- size: `21`
- prototype: `GUID *__fastcall(_QWORD *, GUID **)`
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## pseudocode

```c
GUID *__fastcall GetProxyDllInfo(_QWORD *a1, GUID **a2)
{
  GUID *result; // rax

  *a1 = &aProxyFileList;
  result = &CLSID_PSFactoryBuffer;
  *a2 = &CLSID_PSFactoryBuffer;
  return result;
}

```

## disassembly

```asm
0x180001ec0  lea     rax, aProxyFileList
0x180001ec7  mov     [rcx], rax
0x180001eca  lea     rax, CLSID_PSFactoryBuffer
0x180001ed1  mov     [rdx], rax
0x180001ed4  retn
```
