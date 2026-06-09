# VfsCleanupStreamContext

- ea: `0x140001ce0`
- end: `0x140001d65`
- name: `VfsCleanupStreamContext`
- size: `133`
- prototype: `void __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140001ce0`

## import_xrefs

- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x140001d1a`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x140001d1a`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x140001d09`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x140001d09`
- `ntoskrnl!ExDeleteResourceLite` at `0x140001d39`
- `ntoskrnl!ExDeleteResourceLite` at `0x140001d39`
- `ntoskrnl!ExFreePoolWithTag` at `0x140001d4d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140001d4d`

## pseudocode

```c
void __fastcall VfsCleanupStreamContext(__int64 a1)
{
  struct _ERESOURCE *v2; // rbx
  struct _RTL_AVL_TABLE *i; // rbx
  PVOID v4; // rax

  v2 = *(struct _ERESOURCE **)(a1 + 8);
  if ( (*(_DWORD *)(a1 + 4) & 1) != 0 )
  {
    if ( !v2 )
      return;
    for ( i = (struct _RTL_AVL_TABLE *)(a1 + 16); ; RtlDeleteElementGenericTableAvl(i, v4) )
    {
      v4 = RtlEnumerateGenericTableAvl(i, 1u);
      if ( !v4 )
        break;
    }
    v2 = *(struct _ERESOURCE **)(a1 + 8);
  }
  else if ( !v2 )
  {
    return;
  }
  ExDeleteResourceLite(v2);
  ExFreePoolWithTag(v2, 0x72454656u);
}

```

## disassembly

```asm
0x140001ce0  mov     [rsp+arg_0], rbx
0x140001ce5  push    rdi
0x140001ce6  sub     rsp, 20h
0x140001cea  mov     eax, [rcx+4]
0x140001ced  mov     rdi, rcx
0x140001cf0  mov     rbx, [rcx+8]
0x140001cf4  test    al, 1
0x140001cf6  jz      short loc_140001D31
0x140001cf8  test    rbx, rbx
0x140001cfb  jz      short loc_140001D59
0x140001cfd  lea     rbx, [rcx+10h]
0x140001d01  jmp     short loc_140001D15
0x140001d03  mov     rdx, rax; Buffer
0x140001d06  mov     rcx, rbx; Table
0x140001d09  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x140001d10  nop     dword ptr [rax+rax+00h]
0x140001d15  mov     dl, 1; Restart
0x140001d17  mov     rcx, rbx; Table
0x140001d1a  call    cs:__imp_RtlEnumerateGenericTableAvl
0x140001d21  nop     dword ptr [rax+rax+00h]
0x140001d26  test    rax, rax
0x140001d29  jnz     short loc_140001D03
0x140001d2b  mov     rbx, [rdi+8]
0x140001d2f  jmp     short loc_140001D36
0x140001d31  test    rbx, rbx
0x140001d34  jz      short loc_140001D59
0x140001d36  mov     rcx, rbx; Resource
0x140001d39  call    cs:__imp_ExDeleteResourceLite
0x140001d40  nop     dword ptr [rax+rax+00h]
0x140001d45  mov     edx, 72454656h; Tag
0x140001d4a  mov     rcx, rbx; P
0x140001d4d  call    cs:__imp_ExFreePoolWithTag
0x140001d54  nop     dword ptr [rax+rax+00h]
0x140001d59  mov     rbx, [rsp+28h+arg_0]
0x140001d5e  add     rsp, 20h
0x140001d62  pop     rdi
0x140001d63  retn
```
