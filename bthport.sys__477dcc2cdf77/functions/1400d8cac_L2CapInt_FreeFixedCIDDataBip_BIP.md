# L2CapInt_FreeFixedCIDDataBip(_BIP *)

- ea: `0x1400d8cac`
- end: `0x1400d8d00`
- name: `?L2CapInt_FreeFixedCIDDataBip@@YAXPEAU_BIP@@@Z`
- size: `84`
- prototype: `void __fastcall(PVOID P)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x1400d8900`
- `0x1400d8b50`

## callees

- `0x1400d8cac`

## import_xrefs

- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400d8cda`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400d8cda`
- `ntoskrnl!IoFreeMdl` at `0x1400d8cbe`
- `ntoskrnl!IoFreeMdl` at `0x1400d8cbe`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d8ced`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d8ced`

## pseudocode

```c
void __fastcall L2CapInt_FreeFixedCIDDataBip(_QWORD *P)
{
  struct _MDL *v2; // rcx

  v2 = (struct _MDL *)P[14];
  if ( v2 )
    IoFreeMdl(v2);
  if ( *((int *)P + 9) >= 0 )
    ExFreePoolWithTag(P, 0);
  else
    ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(*P + 112LL), P);
}

```

## disassembly

```asm
0x1400d8cac  push    rbx
0x1400d8cae  sub     rsp, 20h
0x1400d8cb2  mov     rbx, rcx
0x1400d8cb5  mov     rcx, [rcx+70h]; Mdl
0x1400d8cb9  test    rcx, rcx
0x1400d8cbc  jz      short loc_1400D8CCA
0x1400d8cbe  call    cs:__imp_IoFreeMdl
0x1400d8cc5  nop     dword ptr [rax+rax+00h]
0x1400d8cca  cmp     dword ptr [rbx+24h], 0
0x1400d8cce  jge     short loc_1400D8CE8
0x1400d8cd0  mov     rcx, [rbx]
0x1400d8cd3  mov     rdx, rbx; Entry
0x1400d8cd6  add     rcx, 70h ; 'p'; Lookaside
0x1400d8cda  call    cs:__imp_ExFreeToLookasideListEx
0x1400d8ce1  nop     dword ptr [rax+rax+00h]
0x1400d8ce6  jmp     short loc_1400D8CF9
0x1400d8ce8  xor     edx, edx; Tag
0x1400d8cea  mov     rcx, rbx; P
0x1400d8ced  call    cs:__imp_ExFreePoolWithTag
0x1400d8cf4  nop     dword ptr [rax+rax+00h]
0x1400d8cf9  add     rsp, 20h
0x1400d8cfd  pop     rbx
0x1400d8cfe  retn
```
