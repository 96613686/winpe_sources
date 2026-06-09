# _CommonUtil::UtilGetFileSecurity_::_1_::dtor$1

- ea: `0x180009ab4`
- end: `0x180009ac0`
- name: `_CommonUtil::UtilGetFileSecurity_::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180006910`

## pseudocode

```c
__int64 __fastcall CommonUtil::UtilGetFileSecurity_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return CommonUtil::AutoRef<CommonUtil::ISecurityAttributes>::~AutoRef<CommonUtil::ISecurityAttributes>((__int64 *)(a2 + 48));
}

```

## disassembly

```asm
0x180009ab4  lea     rcx, [rdx+30h]
0x180009abb  jmp     ??1?$AutoRef@UISecurityAttributes@CommonUtil@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<CommonUtil::ISecurityAttributes>::~AutoRef<CommonUtil::ISecurityAttributes>(void)
```
