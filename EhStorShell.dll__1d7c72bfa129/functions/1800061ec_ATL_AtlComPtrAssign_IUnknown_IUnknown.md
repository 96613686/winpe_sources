# ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)

- ea: `0x1800061ec`
- end: `0x18000623e`
- name: `?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z`
- size: `82`
- prototype: `struct IUnknown *__fastcall(struct IUnknown **, struct IUnknown *)`
- caller_count: `6`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002610`
- `0x180004260`
- `0x180004560`
- `0x180005d58`
- `0x180005dc0`
- `0x18000b250`

## callees

- `0x1800061ec`
- `0x18000c010`

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
0x1800061ec  mov     [rsp+arg_0], rbx
0x1800061f1  push    rdi
0x1800061f2  sub     rsp, 20h
0x1800061f6  mov     rbx, rdx
0x1800061f9  mov     rdi, rcx
0x1800061fc  test    rcx, rcx
0x1800061ff  jnz     short loc_180006205
0x180006201  xor     eax, eax
0x180006203  jmp     short loc_180006233
0x180006205  test    rbx, rbx
0x180006208  jz      short loc_180006219
0x18000620a  mov     rax, [rdx]
0x18000620d  mov     rcx, rbx
0x180006210  mov     rax, [rax+8]
0x180006214  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006219  mov     rcx, [rdi]
0x18000621c  test    rcx, rcx
0x18000621f  jz      short loc_18000622D
0x180006221  mov     rax, [rcx]
0x180006224  mov     rax, [rax+10h]
0x180006228  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000622d  mov     [rdi], rbx
0x180006230  mov     rax, rbx
0x180006233  mov     rbx, [rsp+28h+arg_0]
0x180006238  add     rsp, 20h
0x18000623c  pop     rdi
0x18000623d  retn
```
