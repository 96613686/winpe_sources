# Concurrency::cancellation_token::~cancellation_token(void)

- ea: `0x1800100e8`
- end: `0x18001011f`
- name: `??1cancellation_token@Concurrency@@QEAA@XZ`
- size: `55`
- prototype: `void __fastcall(volatile signed __int32 **this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180017e22`
- `0x180017ee7`

## callees

- `0x1800100e8`
- `0x180019010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall Concurrency::cancellation_token::~cancellation_token(volatile signed __int32 **this)
{
  volatile signed __int32 *v2; // rcx

  v2 = *this;
  if ( v2 && _InterlockedExchangeAdd(v2 + 2, 0xFFFFFFFF) == 1 )
    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v2 + 8LL))(v2);
  *this = 0;
}

```

## disassembly

```asm
0x1800100e8  push    rbx
0x1800100ea  sub     rsp, 20h
0x1800100ee  mov     rbx, rcx
0x1800100f1  mov     rcx, [rcx]
0x1800100f4  test    rcx, rcx
0x1800100f7  jz      short loc_180010112
0x1800100f9  or      eax, 0FFFFFFFFh
0x1800100fc  lock xadd [rcx+8], eax
0x180010101  cmp     eax, 1
0x180010104  jnz     short loc_180010112
0x180010106  mov     rax, [rcx]
0x180010109  mov     rax, [rax+8]
0x18001010d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010112  mov     qword ptr [rbx], 0
0x180010119  add     rsp, 20h
0x18001011d  pop     rbx
0x18001011e  retn
```
