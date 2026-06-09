# WMASACreateInstance

- ea: `0x180081f70`
- end: `0x180081fc4`
- name: `WMASACreateInstance`
- size: `84`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18000abfc`
- `0x180080b9c`
- `0x180081f70`
- `0x180085010`

## pseudocode

```c
__int64 __fastcall WMASACreateInstance(__int64 a1, struct IUnknown *a2)
{
  CDMOSA *v4; // rax
  int *v5; // r8
  CDMOSA *v6; // rax

  v4 = (CDMOSA *)operator new(0x2C8u);
  v6 = CDMOSA::CDMOSA(v4, a2, v5);
  if ( v6 )
    return (**(__int64 (__fastcall ***)(CDMOSA *, GUID *, __int64))v6)(v6, &IID_IUnknown, a1);
  else
    return 2147942414LL;
}

```

## disassembly

```asm
0x180081f70  mov     [rsp+arg_0], rbx
0x180081f75  push    rdi
0x180081f76  sub     rsp, 20h
0x180081f7a  mov     rdi, rcx
0x180081f7d  mov     rbx, rdx
0x180081f80  mov     ecx, 2C8h; Size
0x180081f85  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180081f8a  mov     rdx, rbx; struct IUnknown *
0x180081f8d  mov     rcx, rax; this
0x180081f90  call    ??0CDMOSA@@QEAA@PEAUIUnknown@@PEAJ@Z; CDMOSA::CDMOSA(IUnknown *,long *)
0x180081f95  mov     rcx, rax
0x180081f98  test    rax, rax
0x180081f9b  jnz     short loc_180081FA4
0x180081f9d  mov     eax, 8007000Eh
0x180081fa2  jmp     short loc_180081FB9
0x180081fa4  mov     rax, [rax]
0x180081fa7  lea     rdx, IID_IUnknown
0x180081fae  mov     r8, rdi
0x180081fb1  mov     rax, [rax]
0x180081fb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081fb9  mov     rbx, [rsp+28h+arg_0]
0x180081fbe  add     rsp, 20h
0x180081fc2  pop     rdi
0x180081fc3  retn
```
