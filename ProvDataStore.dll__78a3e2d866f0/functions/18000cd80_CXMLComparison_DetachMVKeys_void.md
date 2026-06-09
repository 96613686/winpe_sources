# CXMLComparison::DetachMVKeys(void)

- ea: `0x18000cd80`
- end: `0x18000cd8d`
- name: `?DetachMVKeys@CXMLComparison@@UEAAPEAPEAUIMVKey@@XZ`
- size: `13`
- prototype: `struct IMVKey **__fastcall(CXMLComparison *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## pseudocode

```c
struct IMVKey **__fastcall CXMLComparison::DetachMVKeys(CXMLComparison *this)
{
  struct IMVKey **result; // rax

  result = (struct IMVKey **)*((_QWORD *)this + 12);
  *((_QWORD *)this + 12) = 0;
  return result;
}

```

## disassembly

```asm
0x18000cd80  mov     rax, [rcx+60h]
0x18000cd84  mov     qword ptr [rcx+60h], 0
0x18000cd8c  retn
```
