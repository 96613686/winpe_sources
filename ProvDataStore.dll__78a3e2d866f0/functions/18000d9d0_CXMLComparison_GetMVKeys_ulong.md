# CXMLComparison::GetMVKeys(ulong *)

- ea: `0x18000d9d0`
- end: `0x18000d9da`
- name: `?GetMVKeys@CXMLComparison@@UEBAPEAPEAUIMVKey@@PEAK@Z`
- size: `10`
- prototype: `struct IMVKey **__fastcall(CXMLComparison *__hidden this, unsigned int *)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## pseudocode

```c
struct IMVKey **__fastcall CXMLComparison::GetMVKeys(CXMLComparison *this, unsigned int *a2)
{
  *a2 = *((_DWORD *)this + 26);
  return (struct IMVKey **)*((_QWORD *)this + 12);
}

```

## disassembly

```asm
0x18000d9d0  mov     eax, [rcx+68h]
0x18000d9d3  mov     [rdx], eax
0x18000d9d5  mov     rax, [rcx+60h]
0x18000d9d9  retn
```
