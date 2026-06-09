# kernel_std::detail::sp_counted_impl_p<appv::shared::kernel::shared_read_lock>::dispose(void)

- ea: `0x140002740`
- end: `0x140002793`
- name: `?dispose@?$sp_counted_impl_p@Vshared_read_lock@kernel@shared@appv@@@detail@kernel_std@@UEAAXXZ`
- size: `83`
- prototype: `void __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140002740`

## import_xrefs

- `ntoskrnl!ExDeleteResourceLite` at `0x140002758`
- `ntoskrnl!ExDeleteResourceLite` at `0x140002758`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000276f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002780`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000276f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002780`

## pseudocode

```c
void __fastcall kernel_std::detail::sp_counted_impl_p<appv::shared::kernel::shared_read_lock>::dispose(__int64 a1)
{
  _QWORD *v1; // rbx
  struct _ERESOURCE *v2; // rcx
  void *v3; // rcx

  v1 = *(_QWORD **)(a1 + 16);
  if ( v1 )
  {
    v2 = (struct _ERESOURCE *)v1[1];
    if ( v2 )
    {
      ExDeleteResourceLite(v2);
      v3 = (void *)v1[1];
      if ( v3 )
        ExFreePoolWithTag(v3, 0);
    }
    ExFreePoolWithTag(v1, 0);
  }
}

```

## disassembly

```asm
0x140002740  push    rbx
0x140002742  sub     rsp, 20h
0x140002746  mov     rbx, [rcx+10h]
0x14000274a  test    rbx, rbx
0x14000274d  jz      short loc_14000278C
0x14000274f  mov     rcx, [rbx+8]; Resource
0x140002753  test    rcx, rcx
0x140002756  jz      short loc_14000277B
0x140002758  call    cs:__imp_ExDeleteResourceLite
0x14000275f  nop     dword ptr [rax+rax+00h]
0x140002764  mov     rcx, [rbx+8]; P
0x140002768  test    rcx, rcx
0x14000276b  jz      short loc_14000277B
0x14000276d  xor     edx, edx; Tag
0x14000276f  call    cs:__imp_ExFreePoolWithTag
0x140002776  nop     dword ptr [rax+rax+00h]
0x14000277b  xor     edx, edx; Tag
0x14000277d  mov     rcx, rbx; P
0x140002780  call    cs:__imp_ExFreePoolWithTag
0x140002787  nop     dword ptr [rax+rax+00h]
0x14000278c  add     rsp, 20h
0x140002790  pop     rbx
0x140002791  retn
```
