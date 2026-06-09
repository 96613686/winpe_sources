# CommonUtil::CSecurityAttributesHolder::GetSD(void)

- ea: `0x180007fd0`
- end: `0x180007fd5`
- name: `?GetSD@CSecurityAttributesHolder@CommonUtil@@UEBAPEAXXZ`
- size: `5`
- prototype: `void *__fastcall(CommonUtil::CSecurityAttributesHolder *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
void *__fastcall CommonUtil::CSecurityAttributesHolder::GetSD(CommonUtil::CSecurityAttributesHolder *this)
{
  return (void *)*((_QWORD *)this + 2);
}

```

## disassembly

```asm
0x180007fd0  mov     rax, [rcx+10h]
0x180007fd4  retn
```
