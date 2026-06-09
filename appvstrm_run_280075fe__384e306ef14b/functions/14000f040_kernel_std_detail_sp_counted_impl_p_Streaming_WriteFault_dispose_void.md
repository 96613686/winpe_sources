# kernel_std::detail::sp_counted_impl_p<Streaming::WriteFault>::dispose(void)

- ea: `0x14000f040`
- end: `0x14000f06f`
- name: `?dispose@?$sp_counted_impl_p@VWriteFault@Streaming@@@detail@kernel_std@@UEAAXXZ`
- size: `47`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x14000db20`
- `0x14000f040`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000f05c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f05c`

## pseudocode

```c
void __fastcall kernel_std::detail::sp_counted_impl_p<Streaming::WriteFault>::dispose(__int64 a1)
{
  void *v1; // rbx

  v1 = *(void **)(a1 + 16);
  if ( v1 )
  {
    Streaming::WriteFault::~WriteFault(*(Streaming::WriteFault **)(a1 + 16));
    ExFreePoolWithTag(v1, 0);
  }
}

```

## disassembly

```asm
0x14000f040  push    rbx
0x14000f042  sub     rsp, 20h
0x14000f046  mov     rbx, [rcx+10h]
0x14000f04a  test    rbx, rbx
0x14000f04d  jz      short loc_14000F068
0x14000f04f  mov     rcx, rbx; this
0x14000f052  call    ??1WriteFault@Streaming@@QEAA@XZ; Streaming::WriteFault::~WriteFault(void)
0x14000f057  xor     edx, edx; Tag
0x14000f059  mov     rcx, rbx; P
0x14000f05c  call    cs:__imp_ExFreePoolWithTag
0x14000f063  nop     dword ptr [rax+rax+00h]
0x14000f068  add     rsp, 20h
0x14000f06c  pop     rbx
0x14000f06d  retn
```
