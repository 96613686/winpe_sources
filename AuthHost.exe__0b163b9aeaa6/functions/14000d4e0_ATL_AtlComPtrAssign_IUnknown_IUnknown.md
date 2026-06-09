# ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)

- ea: `0x14000d4e0`
- end: `0x14000d532`
- name: `?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z`
- size: `82`
- prototype: `struct IUnknown *__fastcall(struct IUnknown **, struct IUnknown *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000e2e0`

## callees

- `0x14000d4e0`
- `0x140014010`

## pseudocode

```c
struct IUnknown *__fastcall ATL::AtlComPtrAssign(struct IUnknown **a1, struct IUnknown *a2)
{
  if ( !a1 )
    return 0;
  if ( a2 )
    ((void (__fastcall *)(struct IUnknown *))a2->lpVtbl->AddRef)(a2);
  if ( *a1 )
    ((void (__fastcall *)(_QWORD))(*a1)->lpVtbl->Release)(*a1);
  *a1 = a2;
  return a2;
}

```

## disassembly

```asm
0x14000d4e0  mov     [rsp+arg_0], rbx
0x14000d4e5  push    rdi
0x14000d4e6  sub     rsp, 20h
0x14000d4ea  mov     rbx, rdx
0x14000d4ed  mov     rdi, rcx
0x14000d4f0  test    rcx, rcx
0x14000d4f3  jnz     short loc_14000D4F9
0x14000d4f5  xor     eax, eax
0x14000d4f7  jmp     short loc_14000D527
0x14000d4f9  test    rbx, rbx
0x14000d4fc  jz      short loc_14000D50D
0x14000d4fe  mov     rax, [rdx]
0x14000d501  mov     rcx, rbx
0x14000d504  mov     rax, [rax+8]
0x14000d508  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d50d  mov     rcx, [rdi]
0x14000d510  test    rcx, rcx
0x14000d513  jz      short loc_14000D521
0x14000d515  mov     rax, [rcx]
0x14000d518  mov     rax, [rax+10h]
0x14000d51c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d521  mov     [rdi], rbx
0x14000d524  mov     rax, rbx
0x14000d527  mov     rbx, [rsp+28h+arg_0]
0x14000d52c  add     rsp, 20h
0x14000d530  pop     rdi
0x14000d531  retn
```
