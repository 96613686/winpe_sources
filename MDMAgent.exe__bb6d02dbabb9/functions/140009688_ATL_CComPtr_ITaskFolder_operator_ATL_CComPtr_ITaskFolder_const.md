# ATL::CComPtr<ITaskFolder>::operator=(ATL::CComPtr<ITaskFolder> const &)

- ea: `0x140009688`
- end: `0x1400096dc`
- name: `??4?$CComPtr@UITaskFolder@@@ATL@@QEAAPEAUITaskFolder@@AEBV01@@Z`
- size: `84`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x14000a51c`

## callees

- `0x140009688`
- `0x14001a010`

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
0x140009688  mov     [rsp+arg_0], rbx
0x14000968d  push    rdi
0x14000968e  sub     rsp, 20h
0x140009692  mov     rbx, [rdx]
0x140009695  mov     rdi, rcx
0x140009698  cmp     [rcx], rbx
0x14000969b  jz      short loc_1400096CD
0x14000969d  test    rbx, rbx
0x1400096a0  jz      short loc_1400096B1
0x1400096a2  mov     rax, [rbx]
0x1400096a5  mov     rcx, rbx
0x1400096a8  mov     rax, [rax+8]
0x1400096ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400096b1  mov     rcx, [rdi]
0x1400096b4  test    rcx, rcx
0x1400096b7  jz      short loc_1400096C5
0x1400096b9  mov     rdx, [rcx]
0x1400096bc  mov     rax, [rdx+10h]
0x1400096c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400096c5  mov     [rdi], rbx
0x1400096c8  mov     rax, rbx
0x1400096cb  jmp     short loc_1400096D0
0x1400096cd  mov     rax, [rcx]
0x1400096d0  mov     rbx, [rsp+28h+arg_0]
0x1400096d5  add     rsp, 20h
0x1400096d9  pop     rdi
0x1400096da  retn
```
