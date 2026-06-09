# VsmmNumapNodeObjectTeardown

- ea: `0x14009eafc`
- end: `0x14009eb7c`
- name: `VsmmNumapNodeObjectTeardown`
- size: `128`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x14009df58`
- `0x14009e994`

## callees

- `0x14009baac`
- `0x14009e158`
- `0x14009eafc`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14009eb1e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14009eb1e`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x14009eb4f`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x14009eb4f`

## pseudocode

```c
__int64 __fastcall VsmmNumapNodeObjectTeardown(__int64 a1)
{
  int v2; // edi
  void *v3; // rcx

  v2 = 0;
  v3 = *(void **)(a1 + 16);
  if ( v3 )
  {
    ExFreePoolWithTag(v3, 0x6D4D6456u);
    *(_QWORD *)(a1 + 16) = 0;
    *(_WORD *)(a1 + 24) = 0;
  }
  VsmmNumapBackingTeardown(a1);
  do
    ExDeleteLookasideListEx((PLOOKASIDE_LIST_EX)(a1 + 224 + 96LL * v2++));
  while ( v2 != 2 );
  return VidStatisticsDataTeardown((PFAST_MUTEX)(a1 + 72));
}

```

## disassembly

```asm
0x14009eafc  mov     [rsp+arg_0], rbx
0x14009eb01  mov     [rsp+arg_8], rsi
0x14009eb06  push    rdi
0x14009eb07  sub     rsp, 20h
0x14009eb0b  mov     rbx, rcx
0x14009eb0e  xor     edi, edi
0x14009eb10  mov     rcx, [rcx+10h]; P
0x14009eb14  test    rcx, rcx
0x14009eb17  jz      short loc_14009EB32
0x14009eb19  mov     edx, 6D4D6456h; Tag
0x14009eb1e  call    cs:__imp_ExFreePoolWithTag
0x14009eb25  nop     dword ptr [rax+rax+00h]
0x14009eb2a  mov     [rbx+10h], rdi
0x14009eb2e  mov     [rbx+18h], di
0x14009eb32  mov     rcx, rbx
0x14009eb35  call    VsmmNumapBackingTeardown
0x14009eb3a  lea     rsi, [rbx+0E0h]
0x14009eb41  movsxd  rax, edi
0x14009eb44  lea     rcx, [rax+rax*2]
0x14009eb48  shl     rcx, 5
0x14009eb4c  add     rcx, rsi; Lookaside
0x14009eb4f  call    cs:__imp_ExDeleteLookasideListEx
0x14009eb56  nop     dword ptr [rax+rax+00h]
0x14009eb5b  inc     edi
0x14009eb5d  cmp     edi, 2
0x14009eb60  jnz     short loc_14009EB41
0x14009eb62  lea     rcx, [rbx+48h]; FastMutex
0x14009eb66  call    VidStatisticsDataTeardown
0x14009eb6b  mov     rbx, [rsp+28h+arg_0]
0x14009eb70  mov     rsi, [rsp+28h+arg_8]
0x14009eb75  add     rsp, 20h
0x14009eb79  pop     rdi
0x14009eb7a  retn
```
