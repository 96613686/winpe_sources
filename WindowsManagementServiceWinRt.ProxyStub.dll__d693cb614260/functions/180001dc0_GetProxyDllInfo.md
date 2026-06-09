# GetProxyDllInfo

- ea: `0x180001dc0`
- end: `0x180001dd5`
- name: `GetProxyDllInfo`
- size: `21`
- prototype: ``
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
0x180001dc0  lea     rax, aProxyFileList
0x180001dc7  mov     [rcx], rax
0x180001dca  lea     rax, CLSID_PSFactoryBuffer
0x180001dd1  mov     [rdx], rax
0x180001dd4  retn
```
