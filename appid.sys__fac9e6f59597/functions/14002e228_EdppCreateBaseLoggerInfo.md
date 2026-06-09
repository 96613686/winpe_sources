# EdppCreateBaseLoggerInfo

- ea: `0x14002e228`
- end: `0x14002e2d5`
- name: `EdppCreateBaseLoggerInfo`
- size: `173`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned __int16, __int64 *, unsigned int *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14002e45c`
- `0x14002e9d8`

## callees

- `0x14002e228`
- `0x14002e90c`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14002e28a`
- `ntoskrnl!ExAllocatePool2` at `0x14002e28a`

## pseudocode

```c
__int64 __fastcall EdppCreateBaseLoggerInfo(__int64 a1, __int64 a2, unsigned __int16 a3, __int64 *a4, unsigned int *a5)
{
  __int64 v9; // rax
  unsigned int v10; // ebx
  __int64 Pool2; // rax
  __int64 v12; // rdi
  __int64 result; // rax

  *a4 = 0;
  *a5 = 0;
  v9 = -1;
  do
    ++v9;
  while ( *(_WORD *)(a2 + 2 * v9) );
  v10 = ((unsigned __int16)(2 * (v9 + 1)) + a3 + 183) & 0xFFFFFFF8;
  Pool2 = ExAllocatePool2(256, v10, 1097884741);
  v12 = Pool2;
  if ( !Pool2 )
    return 3221225495LL;
  EdppSetLoggerInfoBaseParameters(a1, a2, a3, Pool2, v10);
  result = 0;
  *a4 = v12;
  *a5 = v10;
  return result;
}

```

## disassembly

```asm
0x14002e228  push    rbx
0x14002e22a  push    rbp
0x14002e22b  push    rsi
0x14002e22c  push    rdi
0x14002e22d  push    r12
0x14002e22f  push    r13
0x14002e231  push    r14
0x14002e233  push    r15
0x14002e235  sub     rsp, 38h
0x14002e239  mov     r15, [rsp+78h+arg_20]
0x14002e241  xor     r13d, r13d
0x14002e244  movzx   ebp, r8w
0x14002e248  mov     r12, rcx
0x14002e24b  mov     r14, r9
0x14002e24e  mov     [r9], r13
0x14002e251  mov     rsi, rdx
0x14002e254  mov     ecx, ebp
0x14002e256  mov     [r15], r13d
0x14002e259  or      rax, 0FFFFFFFFFFFFFFFFh
0x14002e25d  inc     rax
0x14002e260  cmp     [rdx+rax*2], r13w
0x14002e265  jnz     short loc_14002E25D
0x14002e267  add     ecx, 0B7h
0x14002e26d  inc     ax
0x14002e270  add     ax, ax
0x14002e273  mov     r8d, 41706445h
0x14002e279  movzx   eax, ax
0x14002e27c  add     ecx, eax
0x14002e27e  and     ecx, 0FFFFFFF8h
0x14002e281  mov     ebx, ecx
0x14002e283  mov     edx, ecx
0x14002e285  mov     ecx, 100h
0x14002e28a  call    cs:__imp_ExAllocatePool2
0x14002e291  nop     dword ptr [rax+rax+00h]
0x14002e296  mov     rdi, rax
0x14002e299  test    rax, rax
0x14002e29c  jnz     short loc_14002E2A5
0x14002e29e  mov     eax, 0C0000017h
0x14002e2a3  jmp     short loc_14002E2C3
0x14002e2a5  mov     r9, rdi
0x14002e2a8  mov     [rsp+78h+var_58], ebx
0x14002e2ac  movzx   r8d, bp
0x14002e2b0  mov     rdx, rsi
0x14002e2b3  mov     rcx, r12
0x14002e2b6  call    EdppSetLoggerInfoBaseParameters
0x14002e2bb  xor     eax, eax
0x14002e2bd  mov     [r14], rdi
0x14002e2c0  mov     [r15], ebx
0x14002e2c3  add     rsp, 38h
0x14002e2c7  pop     r15
0x14002e2c9  pop     r14
0x14002e2cb  pop     r13
0x14002e2cd  pop     r12
0x14002e2cf  pop     rdi
0x14002e2d0  pop     rsi
0x14002e2d1  pop     rbp
0x14002e2d2  pop     rbx
0x14002e2d3  retn
```
