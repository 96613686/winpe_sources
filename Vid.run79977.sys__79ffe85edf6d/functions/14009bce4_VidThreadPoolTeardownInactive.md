# VidThreadPoolTeardownInactive

- ea: `0x14009bce4`
- end: `0x14009bd4e`
- name: `VidThreadPoolTeardownInactive`
- size: `106`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1400099d4`
- `0x14000f4e4`

## callees

- `0x14009bce4`

## import_xrefs

- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14009bd0d`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14009bd0d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14009bd22`
- `ntoskrnl!ExFreePoolWithTag` at `0x14009bd22`
- `ntoskrnl!ExQueryDepthSList` at `0x14009bcf5`
- `ntoskrnl!ExQueryDepthSList` at `0x14009bd31`
- `ntoskrnl!ExQueryDepthSList` at `0x14009bcf5`
- `ntoskrnl!ExQueryDepthSList` at `0x14009bd31`

## pseudocode

```c
USHORT __fastcall VidThreadPoolTeardownInactive(union _SLIST_HEADER *a1)
{
  USHORT DepthSList; // di
  union _SLIST_HEADER *v3; // rbx
  PSLIST_ENTRY v4; // rax
  USHORT result; // ax

  DepthSList = ExQueryDepthSList(a1 + 5);
  v3 = a1 + 6;
  while ( 1 )
  {
    result = ExQueryDepthSList(v3);
    if ( DepthSList == result )
      break;
    v4 = ExpInterlockedPopEntrySList(v3);
    ExFreePoolWithTag(&v4[-4], 0x72446456u);
  }
  return result;
}

```

## disassembly

```asm
0x14009bce4  mov     [rsp+arg_0], rbx
0x14009bce9  push    rdi
0x14009bcea  sub     rsp, 20h
0x14009bcee  mov     rbx, rcx
0x14009bcf1  add     rcx, 50h ; 'P'; SListHead
0x14009bcf5  call    cs:__imp_ExQueryDepthSList
0x14009bcfc  nop     dword ptr [rax+rax+00h]
0x14009bd01  movzx   edi, ax
0x14009bd04  add     rbx, 60h ; '`'
0x14009bd08  jmp     short loc_14009BD2E
0x14009bd0a  mov     rcx, rbx; ListHead
0x14009bd0d  call    cs:__imp_ExpInterlockedPopEntrySList
0x14009bd14  nop     dword ptr [rax+rax+00h]
0x14009bd19  mov     edx, 72446456h; Tag
0x14009bd1e  lea     rcx, [rax-40h]; P
0x14009bd22  call    cs:__imp_ExFreePoolWithTag
0x14009bd29  nop     dword ptr [rax+rax+00h]
0x14009bd2e  mov     rcx, rbx; SListHead
0x14009bd31  call    cs:__imp_ExQueryDepthSList
0x14009bd38  nop     dword ptr [rax+rax+00h]
0x14009bd3d  cmp     di, ax
0x14009bd40  jnz     short loc_14009BD0A
0x14009bd42  mov     rbx, [rsp+28h+arg_0]
0x14009bd47  add     rsp, 20h
0x14009bd4b  pop     rdi
0x14009bd4c  retn
```
