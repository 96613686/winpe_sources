# CommonUtil::CSecurityAttributesHolder::GetSA(void)

- ea: `0x180007fc0`
- end: `0x180007fc5`
- name: `?GetSA@CSecurityAttributesHolder@CommonUtil@@UEBAPEAU_SECURITY_ATTRIBUTES@@XZ`
- size: `5`
- prototype: `struct _SECURITY_ATTRIBUTES *__fastcall(CommonUtil::CSecurityAttributesHolder *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
struct _SECURITY_ATTRIBUTES *__fastcall CommonUtil::CSecurityAttributesHolder::GetSA(
        CommonUtil::CSecurityAttributesHolder *this)
{
  return (struct _SECURITY_ATTRIBUTES *)((char *)this + 40);
}

```

## disassembly

```asm
0x180007fc0  lea     rax, [rcx+28h]
0x180007fc4  retn
```
