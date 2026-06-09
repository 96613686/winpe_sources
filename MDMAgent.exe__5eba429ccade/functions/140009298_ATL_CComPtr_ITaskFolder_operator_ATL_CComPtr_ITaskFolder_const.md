# ATL::CComPtr<ITaskFolder>::operator=(ATL::CComPtr<ITaskFolder> const &)

- ea: `0x140009298`
- end: `0x1400092eb`
- name: `??4?$CComPtr@UITaskFolder@@@ATL@@QEAAPEAUITaskFolder@@AEBV01@@Z`
- size: `83`
- prototype: `__int64 __fastcall(_QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x14000a0b8`

## callees

- `0x140009298`
- `0x140019010`

## pseudocode

```c
__int64 __fastcall ATL::CComPtr<ITaskFolder>::operator=(_QWORD *a1, _QWORD *a2)
{
  __int64 v2; // rbx

  v2 = *a2;
  if ( *a1 == *a2 )
    return *a1;
  if ( v2 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v2 + 8LL))(*a2);
  if ( *a1 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a1 + 16LL))(*a1);
  *a1 = v2;
  return v2;
}

```

## disassembly

```asm
0x140009298  mov     [rsp+arg_0], rbx
0x14000929d  push    rdi
0x14000929e  sub     rsp, 20h
0x1400092a2  mov     rbx, [rdx]
0x1400092a5  mov     rdi, rcx
0x1400092a8  cmp     [rcx], rbx
0x1400092ab  jz      short loc_1400092DD
0x1400092ad  test    rbx, rbx
0x1400092b0  jz      short loc_1400092C1
0x1400092b2  mov     rax, [rbx]
0x1400092b5  mov     rcx, rbx
0x1400092b8  mov     rax, [rax+8]
0x1400092bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400092c1  mov     rcx, [rdi]
0x1400092c4  test    rcx, rcx
0x1400092c7  jz      short loc_1400092D5
0x1400092c9  mov     rdx, [rcx]
0x1400092cc  mov     rax, [rdx+10h]
0x1400092d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400092d5  mov     [rdi], rbx
0x1400092d8  mov     rax, rbx
0x1400092db  jmp     short loc_1400092E0
0x1400092dd  mov     rax, [rcx]
0x1400092e0  mov     rbx, [rsp+28h+arg_0]
0x1400092e5  add     rsp, 20h
0x1400092e9  pop     rdi
0x1400092ea  retn
```
