# std::_Construct_in_place<std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *> *,std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *> * &>(std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *> * &,std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *> * &)

- ea: `0x180004a88`
- end: `0x180004a8f`
- name: `??$_Construct_in_place@PEAU?$_Tree_node@V?$SiPolicyTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@PEAX@std@@AEAPEAU12@@std@@YAXAEAPEAU?$_Tree_node@V?$SiPolicyTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@PEAX@0@0@Z`
- size: `7`
- prototype: `__int64 __fastcall(__int64 *, __int64 *)`
- caller_count: `9`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009c40`
- `0x18000dca4`
- `0x18000e714`
- `0x18000f33c`
- `0x18000f4b8`
- `0x18000fed8`
- `0x18001a094`
- `0x18001a1a4`
- `0x18001ac18`

## pseudocode

```c
__int64 __fastcall std::_Construct_in_place<std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *> *,std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *> * &>(
        __int64 *a1,
        __int64 *a2)
{
  __int64 result; // rax

  result = *a2;
  *a1 = *a2;
  return result;
}

```

## disassembly

```asm
0x180004a88  mov     rax, [rdx]
0x180004a8b  mov     [rcx], rax
0x180004a8e  retn
```
