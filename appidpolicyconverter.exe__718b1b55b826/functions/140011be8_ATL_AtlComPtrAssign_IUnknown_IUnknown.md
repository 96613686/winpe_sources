# ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)

- ea: `0x140011be8`
- end: `0x140011c3a`
- name: `?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z`
- size: `82`
- prototype: `struct IUnknown *__fastcall(struct IUnknown **, struct IUnknown *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400118bc`
- `0x140011fa0`

## callees

- `0x140011be8`
- `0x140016010`

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
0x140011be8  mov     [rsp+arg_0], rbx
0x140011bed  push    rdi
0x140011bee  sub     rsp, 20h
0x140011bf2  mov     rbx, rdx
0x140011bf5  mov     rdi, rcx
0x140011bf8  test    rcx, rcx
0x140011bfb  jnz     short loc_140011C01
0x140011bfd  xor     eax, eax
0x140011bff  jmp     short loc_140011C2F
0x140011c01  test    rbx, rbx
0x140011c04  jz      short loc_140011C15
0x140011c06  mov     rax, [rdx]
0x140011c09  mov     rcx, rbx
0x140011c0c  mov     rax, [rax+8]
0x140011c10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011c15  mov     rcx, [rdi]
0x140011c18  test    rcx, rcx
0x140011c1b  jz      short loc_140011C29
0x140011c1d  mov     rax, [rcx]
0x140011c20  mov     rax, [rax+10h]
0x140011c24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011c29  mov     [rdi], rbx
0x140011c2c  mov     rax, rbx
0x140011c2f  mov     rbx, [rsp+28h+arg_0]
0x140011c34  add     rsp, 20h
0x140011c38  pop     rdi
0x140011c39  retn
```
