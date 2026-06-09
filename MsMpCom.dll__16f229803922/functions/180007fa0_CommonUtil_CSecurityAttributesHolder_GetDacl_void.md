# CommonUtil::CSecurityAttributesHolder::GetDacl(void)

- ea: `0x180007fa0`
- end: `0x180007fa5`
- name: `?GetDacl@CSecurityAttributesHolder@CommonUtil@@UEBAPEAU_ACL@@XZ`
- size: `5`
- prototype: `struct _ACL *__fastcall(CommonUtil::CSecurityAttributesHolder *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## pseudocode

```c
struct _ACL *__fastcall CommonUtil::CSecurityAttributesHolder::GetDacl(CommonUtil::CSecurityAttributesHolder *this)
{
  return (struct _ACL *)*((_QWORD *)this + 3);
}

```

## disassembly

```asm
0x180007fa0  mov     rax, [rcx+18h]
0x180007fa4  retn
```
