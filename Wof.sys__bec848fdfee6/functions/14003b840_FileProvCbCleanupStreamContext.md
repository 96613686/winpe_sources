# FileProvCbCleanupStreamContext

- ea: `0x14003b840`
- end: `0x14003b89a`
- name: `FileProvCbCleanupStreamContext`
- size: `90`
- prototype: `void __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x14003b840`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14003b854`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003b854`
- `ntoskrnl!ObDereferenceObjectDeferDelete` at `0x14003b871`
- `ntoskrnl!ObDereferenceObjectDeferDelete` at `0x14003b871`

## pseudocode

```c
void __fastcall FileProvCbCleanupStreamContext(__int64 a1)
{
  void *v2; // rcx
  void *v3; // rcx

  v2 = *(void **)(a1 + 32);
  if ( v2 )
  {
    ExFreePoolWithTag(v2, 0);
    *(_QWORD *)(a1 + 32) = 0;
  }
  v3 = *(void **)(a1 + 40);
  if ( v3 )
  {
    ObDereferenceObjectDeferDelete(v3);
    *(_QWORD *)(a1 + 40) = 0;
  }
  *(_DWORD *)a1 = 0;
  *(_QWORD *)(a1 + 24) = 0;
}

```

## disassembly

```asm
0x14003b840  push    rbx
0x14003b842  sub     rsp, 20h
0x14003b846  mov     rbx, rcx
0x14003b849  mov     rcx, [rcx+20h]; P
0x14003b84d  test    rcx, rcx
0x14003b850  jz      short loc_14003B868
0x14003b852  xor     edx, edx; Tag
0x14003b854  call    cs:__imp_ExFreePoolWithTag
0x14003b85b  nop     dword ptr [rax+rax+00h]
0x14003b860  mov     qword ptr [rbx+20h], 0
0x14003b868  mov     rcx, [rbx+28h]; Object
0x14003b86c  test    rcx, rcx
0x14003b86f  jz      short loc_14003B885
0x14003b871  call    cs:__imp_ObDereferenceObjectDeferDelete
0x14003b878  nop     dword ptr [rax+rax+00h]
0x14003b87d  mov     qword ptr [rbx+28h], 0
0x14003b885  mov     dword ptr [rbx], 0
0x14003b88b  mov     qword ptr [rbx+18h], 0
0x14003b893  add     rsp, 20h
0x14003b897  pop     rbx
0x14003b898  retn
```
