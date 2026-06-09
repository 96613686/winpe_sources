# LKRhash::CLKRLinearHashTable_Iterator::operator=(LKRhash::CLKRLinearHashTable_Iterator const &)

- ea: `0x180003090`
- end: `0x180003126`
- name: `??4CLKRLinearHashTable_Iterator@LKRhash@@QEAAAEAV01@AEBV01@@Z`
- size: `150`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180004524`
- `0x180009b98`

## callees

- `0x180003090`
- `0x18000b010`

## pseudocode

```c
__int64 __fastcall LKRhash::CLKRLinearHashTable_Iterator::operator=(__int64 a1, __int64 a2)
{
  if ( *(_QWORD *)a2 && *(_WORD *)(a2 + 20) != 0xFFFF )
    (*(void (__fastcall **)(_QWORD, __int64))(*(_QWORD *)a2 + 56LL))(
      *(_QWORD *)(*(_QWORD *)(a2 + 8) + 8LL * *(__int16 *)(a2 + 20) + 24),
      1);
  if ( *(_QWORD *)a1 && *(_WORD *)(a1 + 20) != 0xFFFF )
    (*(void (__fastcall **)(_QWORD, __int64))(*(_QWORD *)a1 + 56LL))(
      *(_QWORD *)(*(_QWORD *)(a1 + 8) + 8LL * *(__int16 *)(a1 + 20) + 24),
      0xFFFFFFFFLL);
  *(_QWORD *)a1 = *(_QWORD *)a2;
  *(_QWORD *)(a1 + 8) = *(_QWORD *)(a2 + 8);
  *(_DWORD *)(a1 + 16) = *(_DWORD *)(a2 + 16);
  *(_WORD *)(a1 + 20) = *(_WORD *)(a2 + 20);
  return a1;
}

```

## disassembly

```asm
0x180003090  mov     [rsp+arg_0], rbx
0x180003095  mov     [rsp+arg_8], rsi
0x18000309a  push    rdi
0x18000309b  sub     rsp, 20h
0x18000309f  mov     r8, [rdx]
0x1800030a2  or      esi, 0FFFFFFFFh
0x1800030a5  mov     rdi, rdx
0x1800030a8  mov     rbx, rcx
0x1800030ab  test    r8, r8
0x1800030ae  jz      short loc_1800030D0
0x1800030b0  cmp     [rdx+14h], si
0x1800030b4  jz      short loc_1800030D0
0x1800030b6  movsx   rax, word ptr [rdx+14h]
0x1800030bb  mov     rcx, [rdx+8]
0x1800030bf  lea     edx, [rsi+2]
0x1800030c2  mov     rcx, [rcx+rax*8+18h]
0x1800030c7  mov     rax, [r8+38h]
0x1800030cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030d0  mov     r8, [rbx]
0x1800030d3  test    r8, r8
0x1800030d6  jz      short loc_1800030F7
0x1800030d8  cmp     [rbx+14h], si
0x1800030dc  jz      short loc_1800030F7
0x1800030de  movsx   rax, word ptr [rbx+14h]
0x1800030e3  mov     edx, esi
0x1800030e5  mov     rcx, [rbx+8]
0x1800030e9  mov     rcx, [rcx+rax*8+18h]
0x1800030ee  mov     rax, [r8+38h]
0x1800030f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030f7  mov     rax, [rdi]
0x1800030fa  mov     rsi, [rsp+28h+arg_8]
0x1800030ff  mov     [rbx], rax
0x180003102  mov     rax, [rdi+8]
0x180003106  mov     [rbx+8], rax
0x18000310a  mov     eax, [rdi+10h]
0x18000310d  mov     [rbx+10h], eax
0x180003110  movzx   eax, word ptr [rdi+14h]
0x180003114  mov     [rbx+14h], ax
0x180003118  mov     rax, rbx
0x18000311b  mov     rbx, [rsp+28h+arg_0]
0x180003120  add     rsp, 20h
0x180003124  pop     rdi
0x180003125  retn
```
