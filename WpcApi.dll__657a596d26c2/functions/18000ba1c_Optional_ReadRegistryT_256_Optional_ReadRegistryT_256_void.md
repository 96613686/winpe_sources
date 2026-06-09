# Optional<ReadRegistryT<256>>::~Optional<ReadRegistryT<256>>(void)

- ea: `0x18000ba1c`
- end: `0x18000ba58`
- name: `??1?$Optional@V?$ReadRegistryT@$0BAA@@@@@QEAA@XZ`
- size: `60`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `6`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800184e8`
- `0x1800296d8`
- `0x180029c05`
- `0x180029d80`
- `0x180029fae`
- `0x18002ac0a`

## callees

- `0x18000ba1c`
- `0x18002c010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Optional<ReadRegistryT<256>>::~Optional<ReadRegistryT<256>>(__int64 a1)
{
  __int64 v1; // r8
  __int64 (__fastcall ***v3)(_QWORD, _QWORD); // rcx
  __int64 result; // rax

  v1 = *(_QWORD *)(a1 + 48);
  if ( v1 )
  {
    v3 = (__int64 (__fastcall ***)(_QWORD, _QWORD))(v1 + 16 + *(int *)(*(_QWORD *)(v1 + 16) + 4LL));
    result = (**v3)(v3, 0);
    *(_QWORD *)(a1 + 48) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000ba1c  push    rbx
0x18000ba1e  sub     rsp, 20h
0x18000ba22  mov     r8, [rcx+30h]
0x18000ba26  mov     rbx, rcx
0x18000ba29  test    r8, r8
0x18000ba2c  jz      short loc_18000BA52
0x18000ba2e  mov     rax, [r8+10h]
0x18000ba32  xor     edx, edx
0x18000ba34  add     r8, 10h
0x18000ba38  movsxd  rcx, dword ptr [rax+4]
0x18000ba3c  add     rcx, r8
0x18000ba3f  mov     rax, [rcx]
0x18000ba42  mov     rax, [rax]
0x18000ba45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ba4a  mov     qword ptr [rbx+30h], 0
0x18000ba52  add     rsp, 20h
0x18000ba56  pop     rbx
0x18000ba57  retn
```
