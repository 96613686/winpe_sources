# RegistryT<256>::`vbase destructor'(void)

- ea: `0x180016888`
- end: `0x1800168eb`
- name: `??_D?$RegistryT@$0BAA@@@QEAAXXZ`
- size: `99`
- prototype: `void **__fastcall(__int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180029c4d`
- `0x180029fe4`

## callees

- `0x180016888`
- `0x18002c010`

## pseudocode

```c
void **__fastcall RegistryT<256>::`vbase destructor'(__int64 a1)
{
  volatile signed __int32 *v1; // rbx
  void **result; // rax

  v1 = *(volatile signed __int32 **)(a1 + 24);
  if ( v1 )
  {
    if ( _InterlockedExchangeAdd(v1 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v1)(v1);
      if ( _InterlockedExchangeAdd(v1 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v1 + 8LL))(v1);
    }
  }
  result = &IConstHierarchicalStorage::`vftable';
  *(_QWORD *)(a1 + 48) = &IConstHierarchicalStorage::`vftable';
  return result;
}

```

## disassembly

```asm
0x180016888  mov     [rsp+arg_0], rbx
0x18001688d  push    rdi
0x18001688e  sub     rsp, 20h
0x180016892  mov     rbx, [rcx+18h]
0x180016896  mov     rdi, rcx
0x180016899  test    rbx, rbx
0x18001689c  jz      short loc_1800168D5
0x18001689e  or      eax, 0FFFFFFFFh
0x1800168a1  lock xadd [rbx+8], eax
0x1800168a6  cmp     eax, 1
0x1800168a9  jnz     short loc_1800168D5
0x1800168ab  mov     rax, [rbx]
0x1800168ae  mov     rcx, rbx
0x1800168b1  mov     rax, [rax]
0x1800168b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800168b9  or      eax, 0FFFFFFFFh
0x1800168bc  lock xadd [rbx+0Ch], eax
0x1800168c1  cmp     eax, 1
0x1800168c4  jnz     short loc_1800168D5
0x1800168c6  mov     rax, [rbx]
0x1800168c9  mov     rcx, rbx
0x1800168cc  mov     rax, [rax+8]
0x1800168d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800168d5  mov     rbx, [rsp+28h+arg_0]
0x1800168da  lea     rax, ??_7IConstHierarchicalStorage@@6B@; const IConstHierarchicalStorage::`vftable'
0x1800168e1  mov     [rdi+30h], rax
0x1800168e5  add     rsp, 20h
0x1800168e9  pop     rdi
0x1800168ea  retn
```
