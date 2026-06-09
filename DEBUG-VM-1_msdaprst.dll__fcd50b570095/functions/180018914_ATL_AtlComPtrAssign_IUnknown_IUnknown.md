# ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)

- ea: `0x180018914`
- end: `0x18001895d`
- name: `?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z`
- size: `73`
- prototype: `struct IUnknown *__fastcall(struct IUnknown **, struct IUnknown *)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001ba50`
- `0x18001bccc`
- `0x180021680`

## callees

- `0x180018914`
- `0x180030010`

## pseudocode

```c
struct IUnknown *__fastcall ATL::AtlComPtrAssign(struct IUnknown **a1, struct IUnknown *a2)
{
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
0x180018914  mov     [rsp+arg_0], rbx
0x180018919  push    rdi
0x18001891a  sub     rsp, 20h
0x18001891e  mov     rbx, rdx
0x180018921  mov     rdi, rcx
0x180018924  test    rdx, rdx
0x180018927  jz      short loc_180018938
0x180018929  mov     rax, [rdx]
0x18001892c  mov     rcx, rdx
0x18001892f  mov     rax, [rax+8]
0x180018933  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018938  mov     rcx, [rdi]
0x18001893b  test    rcx, rcx
0x18001893e  jz      short loc_18001894C
0x180018940  mov     rax, [rcx]
0x180018943  mov     rax, [rax+10h]
0x180018947  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001894c  mov     [rdi], rbx
0x18001894f  mov     rax, rbx
0x180018952  mov     rbx, [rsp+28h+arg_0]
0x180018957  add     rsp, 20h
0x18001895b  pop     rdi
0x18001895c  retn
```
