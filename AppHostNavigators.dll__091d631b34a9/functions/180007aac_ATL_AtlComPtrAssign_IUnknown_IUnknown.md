# ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)

- ea: `0x180007aac`
- end: `0x180007afe`
- name: `?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z`
- size: `82`
- prototype: `struct IUnknown *__fastcall(struct IUnknown **, struct IUnknown *)`
- caller_count: `12`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800080f0`
- `0x1800087a0`
- `0x1800087f0`
- `0x18000a104`
- `0x18000b860`
- `0x18000bc0c`
- `0x18000c230`
- `0x18000dcb0`
- `0x18000de58`
- `0x18000ee94`
- `0x180010b64`
- `0x180010d64`

## callees

- `0x180007aac`
- `0x180014010`

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
0x180007aac  mov     [rsp+arg_0], rbx
0x180007ab1  push    rdi
0x180007ab2  sub     rsp, 20h
0x180007ab6  mov     rbx, rdx
0x180007ab9  mov     rdi, rcx
0x180007abc  test    rcx, rcx
0x180007abf  jnz     short loc_180007AC5
0x180007ac1  xor     eax, eax
0x180007ac3  jmp     short loc_180007AF3
0x180007ac5  test    rbx, rbx
0x180007ac8  jz      short loc_180007AD9
0x180007aca  mov     rax, [rdx]
0x180007acd  mov     rcx, rbx
0x180007ad0  mov     rax, [rax+8]
0x180007ad4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ad9  mov     rcx, [rdi]
0x180007adc  test    rcx, rcx
0x180007adf  jz      short loc_180007AED
0x180007ae1  mov     rax, [rcx]
0x180007ae4  mov     rax, [rax+10h]
0x180007ae8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007aed  mov     [rdi], rbx
0x180007af0  mov     rax, rbx
0x180007af3  mov     rbx, [rsp+28h+arg_0]
0x180007af8  add     rsp, 20h
0x180007afc  pop     rdi
0x180007afd  retn
```
