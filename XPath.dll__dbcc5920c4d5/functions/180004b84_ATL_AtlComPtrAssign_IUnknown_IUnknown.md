# ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)

- ea: `0x180004b84`
- end: `0x180004bd6`
- name: `?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z`
- size: `82`
- prototype: `struct IUnknown *__fastcall(struct IUnknown **, struct IUnknown *)`
- caller_count: `25`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180004aac`
- `0x180004c30`
- `0x180004d24`
- `0x180005068`
- `0x180005124`
- `0x180005a3c`
- `0x180005b60`
- `0x180005c7c`
- `0x180006de0`
- `0x180006e90`
- `0x180006f40`
- `0x180006ff0`
- `0x180007110`
- `0x1800071b4`
- `0x180007258`
- `0x1800080b8`
- `0x180008c24`
- `0x1800094f4`
- `0x180009890`
- `0x180009d84`
- `0x18000a094`
- `0x18000d7a0`
- `0x18000d850`
- `0x18000e5ac`
- `0x18000e5e0`

## callees

- `0x180004b84`
- `0x180012010`

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
0x180004b84  mov     [rsp+arg_0], rbx
0x180004b89  push    rdi
0x180004b8a  sub     rsp, 20h
0x180004b8e  mov     rbx, rdx
0x180004b91  mov     rdi, rcx
0x180004b94  test    rcx, rcx
0x180004b97  jnz     short loc_180004B9D
0x180004b99  xor     eax, eax
0x180004b9b  jmp     short loc_180004BCB
0x180004b9d  test    rbx, rbx
0x180004ba0  jz      short loc_180004BB1
0x180004ba2  mov     rax, [rdx]
0x180004ba5  mov     rcx, rbx
0x180004ba8  mov     rax, [rax+8]
0x180004bac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004bb1  mov     rcx, [rdi]
0x180004bb4  test    rcx, rcx
0x180004bb7  jz      short loc_180004BC5
0x180004bb9  mov     rax, [rcx]
0x180004bbc  mov     rax, [rax+10h]
0x180004bc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004bc5  mov     [rdi], rbx
0x180004bc8  mov     rax, rbx
0x180004bcb  mov     rbx, [rsp+28h+arg_0]
0x180004bd0  add     rsp, 20h
0x180004bd4  pop     rdi
0x180004bd5  retn
```
