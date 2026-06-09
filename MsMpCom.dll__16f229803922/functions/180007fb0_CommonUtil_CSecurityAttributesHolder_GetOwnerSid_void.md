# CommonUtil::CSecurityAttributesHolder::GetOwnerSid(void)

- ea: `0x180007fb0`
- end: `0x180007fb5`
- name: `?GetOwnerSid@CSecurityAttributesHolder@CommonUtil@@UEBAPEAXXZ`
- size: `5`
- prototype: `void *__fastcall(CommonUtil::CSecurityAttributesHolder *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## pseudocode

```c
void *__fastcall CommonUtil::CSecurityAttributesHolder::GetOwnerSid(CommonUtil::CSecurityAttributesHolder *this)
{
  return (void *)*((_QWORD *)this + 4);
}

```

## disassembly

```asm
0x180007fb0  mov     rax, [rcx+20h]
0x180007fb4  retn
```
