# NetioUnInitializeFlowsManager

- ea: `0x1400742d0`
- end: `0x140074327`
- name: `NetioUnInitializeFlowsManager`
- size: `87`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1400426c8`
- `0x1400742d0`

## import_xrefs

- `ntoskrnl!RtlDeleteHashTable` at `0x140074304`
- `ntoskrnl!RtlDeleteHashTable` at `0x140074314`
- `ntoskrnl!RtlDeleteHashTable` at `0x140074304`
- `ntoskrnl!RtlDeleteHashTable` at `0x140074314`

## pseudocode

```c
void __fastcall NetioUnInitializeFlowsManager(__int64 a1)
{
  struct _RTL_DYNAMIC_HASH_TABLE *v2; // rcx

  PplDestroyLookasideList(*(PVOID *)(a1 + 1896), 0x6636764Eu);
  PplDestroyLookasideList(*(PVOID *)(a1 + 1888), 0x6634764Eu);
  v2 = *(struct _RTL_DYNAMIC_HASH_TABLE **)(a1 + 80);
  if ( v2 )
    RtlDeleteHashTable(v2);
  RtlDeleteHashTable((PRTL_DYNAMIC_HASH_TABLE)(a1 + 16));
}

```

## disassembly

```asm
0x1400742d0  push    rbx
0x1400742d2  sub     rsp, 20h
0x1400742d6  mov     rbx, rcx
0x1400742d9  mov     edx, 6636764Eh; Tag
0x1400742de  mov     rcx, [rcx+768h]; P
0x1400742e5  call    PplDestroyLookasideList
0x1400742ea  mov     rcx, [rbx+760h]; P
0x1400742f1  mov     edx, 6634764Eh; Tag
0x1400742f6  call    PplDestroyLookasideList
0x1400742fb  mov     rcx, [rbx+50h]; HashTable
0x1400742ff  test    rcx, rcx
0x140074302  jz      short loc_140074310
0x140074304  call    cs:__imp_RtlDeleteHashTable
0x14007430b  nop     dword ptr [rax+rax+00h]
0x140074310  lea     rcx, [rbx+10h]; HashTable
0x140074314  call    cs:__imp_RtlDeleteHashTable
0x14007431b  nop     dword ptr [rax+rax+00h]
0x140074320  add     rsp, 20h
0x140074324  pop     rbx
0x140074325  retn
```
