# FwppCommonShutdown

- ea: `0x18001bfb8`
- end: `0x18001c075`
- name: `FwppCommonShutdown`
- size: `189`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000faf0`
- `0x18001bdd0`

## callees

- `0x180008480`
- `0x18001bfb8`
- `0x18001f5d8`
- `0x1800208c0`

## import_xrefs

- `ntoskrnl!KeQueryMaximumProcessorCountEx` at `0x18001bfcf`
- `ntoskrnl!KeQueryMaximumProcessorCountEx` at `0x18001bfe6`
- `ntoskrnl!KeQueryMaximumProcessorCountEx` at `0x18001bfcf`
- `ntoskrnl!KeQueryMaximumProcessorCountEx` at `0x18001bfe6`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x18001c009`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x18001c028`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x18001c03b`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x18001c04e`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x18001c009`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x18001c028`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x18001c03b`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x18001c04e`

## pseudocode

```c
void *FwppCommonShutdown()
{
  ULONG i; // ebx
  __int64 v1; // rcx

  if ( gPerProcessorContext )
  {
    for ( i = 0; i < KeQueryMaximumProcessorCountEx(0xFFFFu); ++i )
      ;
    WfpNamedPoolFree(v1, (PVOID *)&gPerProcessorContext);
  }
  ExDeleteNPagedLookasideList(&Lookaside);
  WfpObjectManagerClose(&unk_180048680);
  ExDeleteNPagedLookasideList(&stru_180048580);
  ExDeleteNPagedLookasideList(&stru_180048500);
  ExDeleteNPagedLookasideList(&gFwpNblInfo);
  return memset(&gFwpNblInfo, 0, 0x2C0u);
}

```

## disassembly

```asm
0x18001bfb8  push    rbx
0x18001bfba  sub     rsp, 20h
0x18001bfbe  cmp     cs:gPerProcessorContext, 0
0x18001bfc6  jz      short loc_18001C002
0x18001bfc8  mov     ecx, 0FFFFh; GroupNumber
0x18001bfcd  xor     ebx, ebx
0x18001bfcf  call    cs:__imp_KeQueryMaximumProcessorCountEx
0x18001bfd6  nop     dword ptr [rax+rax+00h]
0x18001bfdb  test    eax, eax
0x18001bfdd  jz      short loc_18001BFF6
0x18001bfdf  mov     ecx, 0FFFFh; GroupNumber
0x18001bfe4  inc     ebx
0x18001bfe6  call    cs:__imp_KeQueryMaximumProcessorCountEx
0x18001bfed  nop     dword ptr [rax+rax+00h]
0x18001bff2  cmp     ebx, eax
0x18001bff4  jb      short loc_18001BFDF
0x18001bff6  lea     rdx, gPerProcessorContext
0x18001bffd  call    WfpNamedPoolFree
0x18001c002  lea     rcx, Lookaside; Lookaside
0x18001c009  call    cs:__imp_ExDeleteNPagedLookasideList
0x18001c010  nop     dword ptr [rax+rax+00h]
0x18001c015  lea     rcx, unk_180048680; void *
0x18001c01c  call    WfpObjectManagerClose
0x18001c021  lea     rcx, stru_180048580; Lookaside
0x18001c028  call    cs:__imp_ExDeleteNPagedLookasideList
0x18001c02f  nop     dword ptr [rax+rax+00h]
0x18001c034  lea     rcx, stru_180048500; Lookaside
0x18001c03b  call    cs:__imp_ExDeleteNPagedLookasideList
0x18001c042  nop     dword ptr [rax+rax+00h]
0x18001c047  lea     rcx, gFwpNblInfo; Lookaside
0x18001c04e  call    cs:__imp_ExDeleteNPagedLookasideList
0x18001c055  nop     dword ptr [rax+rax+00h]
0x18001c05a  xor     edx, edx; Val
0x18001c05c  lea     rcx, gFwpNblInfo; void *
0x18001c063  mov     r8d, 2C0h; Size
0x18001c069  call    memset
0x18001c06e  add     rsp, 20h
0x18001c072  pop     rbx
0x18001c073  retn
```
