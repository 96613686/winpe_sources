# ReadRegistryT<256>::`scalar deleting destructor'(uint)

- ea: `0x180025804`
- end: `0x18002587d`
- name: `??_G?$ReadRegistryT@$0BAA@@@UEAAPEAXI@Z`
- size: `121`
- prototype: `_QWORD *__fastcall(_QWORD *, char)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callers

- `0x180025710`

## callees

- `0x1800036e4`
- `0x180025804`
- `0x18002c010`

## pseudocode

```c
_QWORD *__fastcall ReadRegistryT<256>::`scalar deleting destructor'(_QWORD *a1, char a2)
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
    operator delete(a1 - 4);
  return a1 - 4;
}

```

## disassembly

```asm
0x180025804  push    rbx
0x180025806  push    rbp
0x180025807  push    rsi
0x180025808  push    rdi
0x180025809  sub     rsp, 28h
0x18002580d  mov     rbx, [rcx-18h]
0x180025811  mov     ebp, edx
0x180025813  mov     rsi, rcx
0x180025816  test    rbx, rbx
0x180025819  jz      short loc_180025852
0x18002581b  or      eax, 0FFFFFFFFh
0x18002581e  lock xadd [rbx+8], eax
0x180025823  cmp     eax, 1
0x180025826  jnz     short loc_180025852
0x180025828  mov     rax, [rbx]
0x18002582b  mov     rcx, rbx
0x18002582e  mov     rax, [rax]
0x180025831  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025836  or      eax, 0FFFFFFFFh
0x180025839  lock xadd [rbx+0Ch], eax
0x18002583e  cmp     eax, 1
0x180025841  jnz     short loc_180025852
0x180025843  mov     rax, [rbx]
0x180025846  mov     rcx, rbx
0x180025849  mov     rax, [rax+8]
0x18002584d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025852  lea     rax, ??_7IConstHierarchicalStorage@@6B@; const IConstHierarchicalStorage::`vftable'
0x180025859  mov     [rsi], rax
0x18002585c  test    bpl, 1
0x180025860  jz      short loc_180025870
0x180025862  mov     edx, 28h ; '('
0x180025867  lea     rcx, [rsi-20h]; Block
0x18002586b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180025870  lea     rax, [rsi-20h]
0x180025874  add     rsp, 28h
0x180025878  pop     rdi
0x180025879  pop     rsi
0x18002587a  pop     rbp
0x18002587b  pop     rbx
0x18002587c  retn
```
