# std::unique_ptr<CodeIntegrity::Management::SiPolicyView const,std::default_delete<CodeIntegrity::Management::SiPolicyView const>>::~unique_ptr<CodeIntegrity::Management::SiPolicyView const,std::default_delete<CodeIntegrity::Management::SiPolicyView const>>(void)

- ea: `0x1800052c0`
- end: `0x1800052db`
- name: `??1?$unique_ptr@$$CBVSiPolicyView@Management@CodeIntegrity@@U?$default_delete@$$CBVSiPolicyView@Management@CodeIntegrity@@@std@@@std@@QEAA@XZ`
- size: `27`
- prototype: `void *__fastcall(CodeIntegrity::Management::SiPolicyView **)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180008fb0`
- `0x180009420`
- `0x1800096e0`

## callees

- `0x1800052c0`
- `0x18000589c`

## pseudocode

```c
void *__fastcall std::unique_ptr<CodeIntegrity::Management::SiPolicyView const>::~unique_ptr<CodeIntegrity::Management::SiPolicyView const>(
        CodeIntegrity::Management::SiPolicyView **a1)
{
  CodeIntegrity::Management::SiPolicyView *v1; // rcx
  void *result; // rax

  v1 = *a1;
  if ( v1 )
    return CodeIntegrity::Management::SiPolicyView::`scalar deleting destructor'(v1, 1u);
  return result;
}

```

## disassembly

```asm
0x1800052c0  sub     rsp, 28h
0x1800052c4  mov     rcx, [rcx]; this
0x1800052c7  test    rcx, rcx
0x1800052ca  jz      short loc_1800052D6
0x1800052cc  mov     edx, 1; unsigned int
0x1800052d1  call    ??_GSiPolicyView@Management@CodeIntegrity@@QEAAPEAXI@Z; CodeIntegrity::Management::SiPolicyView::`scalar deleting destructor'(uint)
0x1800052d6  add     rsp, 28h
0x1800052da  retn
```
