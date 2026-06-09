# Microsoft::WRL::Details::MakeAllocator<CdsToInputTaskHandler>::~MakeAllocator<CdsToInputTaskHandler>(void)

- ea: `0x180008408`
- end: `0x18000841e`
- name: `??1?$MakeAllocator@VCdsToInputTaskHandler@@@Details@WRL@Microsoft@@QEAA@XZ`
- size: `22`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `7`
- callee_count: `2`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x180007f34`
- `0x180007fcc`
- `0x180008064`
- `0x18000816c`
- `0x18000cc28`
- `0x18000cce8`
- `0x18002eca8`

## callees

- `0x180003990`
- `0x180008408`

## pseudocode

```c
void __fastcall Microsoft::WRL::Details::MakeAllocator<CdsToInputTaskHandler>::~MakeAllocator<CdsToInputTaskHandler>(
        void **a1)
{
  void *v1; // rcx

  v1 = *a1;
  if ( v1 )
    operator delete(v1);
}

```

## disassembly

```asm
0x180008408  sub     rsp, 28h
0x18000840c  mov     rcx, [rcx]; Block
0x18000840f  test    rcx, rcx
0x180008412  jz      short loc_180008419
0x180008414  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180008419  add     rsp, 28h
0x18000841d  retn
```
