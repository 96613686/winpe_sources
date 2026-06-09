# CommonUtil::ISecurityAttributes::~ISecurityAttributes(void)

- ea: `0x180007ef0`
- end: `0x180007efb`
- name: `??1ISecurityAttributes@CommonUtil@@UEAA@XZ`
- size: `11`
- prototype: `void __fastcall(CommonUtil::ISecurityAttributes *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180009a90`

## pseudocode

```c
void __fastcall CommonUtil::ISecurityAttributes::~ISecurityAttributes(CommonUtil::ISecurityAttributes *this)
{
  *(_QWORD *)this = &CommonUtil::CRefObject::`vftable';
}

```

## disassembly

```asm
0x180007ef0  lea     rax, ??_7CRefObject@CommonUtil@@6B@; const CommonUtil::CRefObject::`vftable'
0x180007ef7  mov     [rcx], rax
0x180007efa  retn
```
