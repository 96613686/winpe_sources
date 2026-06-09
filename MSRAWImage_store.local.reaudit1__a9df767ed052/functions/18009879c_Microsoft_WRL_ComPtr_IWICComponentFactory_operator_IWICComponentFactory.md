# Microsoft::WRL::ComPtr<IWICComponentFactory>::operator=(IWICComponentFactory *)

- ea: `0x18009879c`
- end: `0x1800987f6`
- name: `??4?$ComPtr@UIWICComponentFactory@@@WRL@Microsoft@@QEAAAEAV012@PEAUIWICComponentFactory@@@Z`
- size: `90`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18009d37c`
- `0x18009d58c`

## callees

- `0x18009879c`
- `0x1800b4010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 *__fastcall Microsoft::WRL::ComPtr<IWICComponentFactory>::operator=(__int64 *a1, __int64 a2)
{
  __int64 v4; // rcx

  if ( *a1 != a2 )
  {
    if ( a2 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)a2 + 8LL))(a2);
    v4 = *a1;
    *a1 = a2;
    if ( v4 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  }
  return a1;
}

```

## disassembly

```asm
0x18009879c  push    rdi
0x18009879e  sub     rsp, 30h
0x1800987a2  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x1800987ab  mov     [rsp+38h+arg_0], rbx
0x1800987b0  mov     rbx, rdx
0x1800987b3  mov     rdi, rcx
0x1800987b6  cmp     [rcx], rdx
0x1800987b9  jz      short loc_1800987E7
0x1800987bb  test    rdx, rdx
0x1800987be  jz      short loc_1800987D0
0x1800987c0  mov     rax, [rdx]
0x1800987c3  mov     rcx, rdx
0x1800987c6  mov     rax, [rax+8]
0x1800987ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800987cf  nop
0x1800987d0  mov     rcx, [rdi]
0x1800987d3  mov     [rdi], rbx
0x1800987d6  test    rcx, rcx
0x1800987d9  jz      short loc_1800987E7
0x1800987db  mov     rax, [rcx]
0x1800987de  mov     rax, [rax+10h]
0x1800987e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800987e7  mov     rax, rdi
0x1800987ea  mov     rbx, [rsp+38h+arg_0]
0x1800987ef  add     rsp, 30h
0x1800987f3  pop     rdi
0x1800987f4  retn
```
