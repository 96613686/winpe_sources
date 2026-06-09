# kernel_std::detail::sp_counted_impl_p<Streaming::StreamFaultWriter>::dispose(void)

- ea: `0x14000d6e0`
- end: `0x14000d70f`
- name: `?dispose@?$sp_counted_impl_p@VStreamFaultWriter@Streaming@@@detail@kernel_std@@UEAAXXZ`
- size: `47`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x14000d6e0`
- `0x14000f1a4`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000d6fc`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d6fc`

## pseudocode

```c
void __fastcall kernel_std::detail::sp_counted_impl_p<Streaming::StreamFaultWriter>::dispose(__int64 a1)
{
  void *v1; // rbx

  v1 = *(void **)(a1 + 16);
  if ( v1 )
  {
    Streaming::StreamFaultWriter::~StreamFaultWriter(*(Streaming::StreamFaultWriter **)(a1 + 16));
    ExFreePoolWithTag(v1, 0);
  }
}

```

## disassembly

```asm
0x14000d6e0  push    rbx
0x14000d6e2  sub     rsp, 20h
0x14000d6e6  mov     rbx, [rcx+10h]
0x14000d6ea  test    rbx, rbx
0x14000d6ed  jz      short loc_14000D708
0x14000d6ef  mov     rcx, rbx; this
0x14000d6f2  call    ??1StreamFaultWriter@Streaming@@QEAA@XZ; Streaming::StreamFaultWriter::~StreamFaultWriter(void)
0x14000d6f7  xor     edx, edx; Tag
0x14000d6f9  mov     rcx, rbx; P
0x14000d6fc  call    cs:__imp_ExFreePoolWithTag
0x14000d703  nop     dword ptr [rax+rax+00h]
0x14000d708  add     rsp, 20h
0x14000d70c  pop     rbx
0x14000d70d  retn
```
