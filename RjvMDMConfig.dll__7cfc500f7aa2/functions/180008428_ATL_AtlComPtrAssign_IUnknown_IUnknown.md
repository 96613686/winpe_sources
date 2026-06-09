# ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)

- ea: `0x180008428`
- end: `0x18000847b`
- name: `?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z`
- size: `83`
- prototype: `struct IUnknown *__fastcall(struct IUnknown **, struct IUnknown *)`
- caller_count: `7`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180008bd4`
- `0x180015e1c`
- `0x1800163f4`
- `0x180017ed8`
- `0x1800198f0`
- `0x180019a90`
- `0x180019dd0`

## callees

- `0x180008428`
- `0x18001e010`

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
0x180008428  mov     [rsp+arg_0], rbx
0x18000842d  push    rdi
0x18000842e  sub     rsp, 20h
0x180008432  mov     rbx, rdx
0x180008435  mov     rdi, rcx
0x180008438  test    rcx, rcx
0x18000843b  jnz     short loc_180008441
0x18000843d  xor     eax, eax
0x18000843f  jmp     short loc_18000846F
0x180008441  test    rbx, rbx
0x180008444  jz      short loc_180008455
0x180008446  mov     rax, [rdx]
0x180008449  mov     rcx, rbx
0x18000844c  mov     rax, [rax+8]
0x180008450  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008455  mov     rcx, [rdi]
0x180008458  test    rcx, rcx
0x18000845b  jz      short loc_180008469
0x18000845d  mov     rax, [rcx]
0x180008460  mov     rax, [rax+10h]
0x180008464  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008469  mov     [rdi], rbx
0x18000846c  mov     rax, rbx
0x18000846f  mov     rbx, [rsp+28h+arg_0]
0x180008474  add     rsp, 20h
0x180008478  pop     rdi
0x180008479  retn
```
