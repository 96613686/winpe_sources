# CBcdWmiWrapper::GetNamespace(void)

- ea: `0x18000b9c0`
- end: `0x18000b9c5`
- name: `?GetNamespace@CBcdWmiWrapper@@IEAAPEAUIWbemServices@@XZ`
- size: `5`
- prototype: `struct IWbemServices *__fastcall(CBcdWmiWrapper *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task`

## pseudocode

```c
struct IWbemServices *__fastcall CBcdWmiWrapper::GetNamespace(CBcdWmiWrapper *this)
{
  return (struct IWbemServices *)*((_QWORD *)this + 2);
}

```

## disassembly

```asm
0x18000b9c0  mov     rax, [rcx+10h]
0x18000b9c4  retn
```
