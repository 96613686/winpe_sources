# RegistryT<256>::`vector deleting destructor'(uint)

- ea: `0x180025884`
- end: `0x1800258fd`
- name: `??_E?$RegistryT@$0BAA@@@UEAAPEAXI@Z`
- size: `121`
- prototype: `_QWORD *__fastcall(_QWORD *, char)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callers

- `0x180025730`

## callees

- `0x1800036e4`
- `0x180025884`
- `0x18002c010`

## pseudocode

```c
_QWORD *__fastcall RegistryT<256>::`vector deleting destructor'(_QWORD *a1, char a2)
{
  volatile signed __int32 *v2; // rbx

  v2 = (volatile signed __int32 *)*(a1 - 3);
  if ( v2 )
  {
    if ( _InterlockedExchangeAdd(v2 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v2)(v2);
      if ( _InterlockedExchangeAdd(v2 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v2 + 8LL))(v2);
    }
  }
  *a1 = &IConstHierarchicalStorage::`vftable';
  if ( (a2 & 1) != 0 )
    operator delete(a1 - 6);
  return a1 - 6;
}

```

## disassembly

```asm
0x180025884  push    rbx
0x180025886  push    rbp
0x180025887  push    rsi
0x180025888  push    rdi
0x180025889  sub     rsp, 28h
0x18002588d  mov     rbx, [rcx-18h]
0x180025891  mov     ebp, edx
0x180025893  mov     rsi, rcx
0x180025896  test    rbx, rbx
0x180025899  jz      short loc_1800258D2
0x18002589b  or      eax, 0FFFFFFFFh
0x18002589e  lock xadd [rbx+8], eax
0x1800258a3  cmp     eax, 1
0x1800258a6  jnz     short loc_1800258D2
0x1800258a8  mov     rax, [rbx]
0x1800258ab  mov     rcx, rbx
0x1800258ae  mov     rax, [rax]
0x1800258b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800258b6  or      eax, 0FFFFFFFFh
0x1800258b9  lock xadd [rbx+0Ch], eax
0x1800258be  cmp     eax, 1
0x1800258c1  jnz     short loc_1800258D2
0x1800258c3  mov     rax, [rbx]
0x1800258c6  mov     rcx, rbx
0x1800258c9  mov     rax, [rax+8]
0x1800258cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800258d2  lea     rax, ??_7IConstHierarchicalStorage@@6B@; const IConstHierarchicalStorage::`vftable'
0x1800258d9  mov     [rsi], rax
0x1800258dc  test    bpl, 1
0x1800258e0  jz      short loc_1800258F0
0x1800258e2  mov     edx, 38h ; '8'
0x1800258e7  lea     rcx, [rsi-30h]; Block
0x1800258eb  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800258f0  lea     rax, [rsi-30h]
0x1800258f4  add     rsp, 28h
0x1800258f8  pop     rdi
0x1800258f9  pop     rsi
0x1800258fa  pop     rbp
0x1800258fb  pop     rbx
0x1800258fc  retn
```
