# VfsCreateNameNormalizationContext

- ea: `0x140009f94`
- end: `0x14000a082`
- name: `VfsCreateNameNormalizationContext`
- size: `238`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x14000a5a0`

## callees

- `0x140009298`
- `0x140009368`
- `0x140009f94`

## import_xrefs

- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14000a030`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14000a030`

## pseudocode

```c
__int64 __fastcall VfsCreateNameNormalizationContext(__int64 a1, __int64 a2, void *a3, __int64 a4, _QWORD *a5)
{
  unsigned int v5; // edi
  void *v6; // rbx
  _QWORD *v7; // rax
  __int64 v9; // [rsp+60h] [rbp-18h] BYREF

  v5 = 0;
  v6 = (void *)VfsLookupMappingForUserAndPackage(a3, (__int64)&v9);
  v7 = ExAllocateFromPagedLookasideList(&stru_14001F900);
  if ( v7 )
  {
    *v7 = v6;
    v6 = 0;
    *a5 = v7;
  }
  else
  {
    v5 = -1073741670;
  }
  if ( v6 )
    VfsReleaseMappingEntry(v6);
  return v5;
}

```

## disassembly

```asm
0x140009f94  mov     rax, rsp
0x140009f97  mov     [rax+8], rbx
0x140009f9b  mov     [rax+10h], rsi
0x140009f9f  push    rdi
0x140009fa0  sub     rsp, 70h
0x140009fa4  mov     rbx, r9
0x140009fa7  mov     rsi, r8
0x140009faa  xor     edi, edi
0x140009fac  mov     [rax-48h], rdi
0x140009fb0  mov     [rax-24h], edi
0x140009fb3  mov     r11, [rcx+8]
0x140009fb7  mov     [rax-20h], r11
0x140009fbb  mov     [rax-28h], dx
0x140009fbf  mov     [rax-26h], dx
0x140009fc3  mov     [rax-34h], edi
0x140009fc6  movzx   r10d, word ptr [rcx]
0x140009fca  cmp     dx, r10w
0x140009fce  jb      short loc_140009FDC
0x140009fd0  mov     [rax-30h], rdi
0x140009fd4  xor     eax, eax
0x140009fd6  mov     dword ptr [rsp+78h+var_38], eax
0x140009fda  jmp     short loc_140009FF7
0x140009fdc  movzx   eax, dx
0x140009fdf  add     rax, r11
0x140009fe2  mov     qword ptr [rsp+78h+var_38+8], rax
0x140009fe7  sub     r10w, dx
0x140009feb  mov     word ptr [rsp+78h+var_38], r10w
0x140009ff1  mov     word ptr [rsp+78h+var_38+2], r10w
0x140009ff7  movaps  xmm0, [rsp+78h+var_38]
0x140009ffc  movdqa  [rsp+78h+var_38], xmm0
0x14000a002  lea     rax, [rsp+78h+var_18]
0x14000a007  mov     [rsp+78h+var_58], rax; __int64
0x14000a00c  lea     r9, [rsp+78h+var_38]
0x14000a011  lea     r8, [rsp+78h+var_28]
0x14000a016  mov     rdx, rbx
0x14000a019  mov     rcx, rsi; Buffer
0x14000a01c  call    VfsLookupMappingForUserAndPackage
0x14000a021  mov     rbx, rax
0x14000a024  mov     [rsp+78h+var_48], rax
0x14000a029  lea     rcx, stru_14001F900; Lookaside
0x14000a030  call    cs:__imp_ExAllocateFromPagedLookasideList
0x14000a037  nop     dword ptr [rax+rax+00h]
0x14000a03c  mov     rcx, rax
0x14000a03f  test    rax, rax
0x14000a042  jnz     short loc_14000A04B
0x14000a044  mov     edi, 0C000009Ah
0x14000a049  jmp     short loc_14000A060
0x14000a04b  mov     [rax], rbx
0x14000a04e  xor     ebx, ebx
0x14000a050  mov     [rsp+78h+var_48], rbx
0x14000a055  mov     rax, [rsp+78h+arg_20]
0x14000a05d  mov     [rax], rcx
0x14000a060  test    rbx, rbx
0x14000a063  jz      short loc_14000A06D
0x14000a065  mov     rcx, rbx; P
0x14000a068  call    VfsReleaseMappingEntry
0x14000a06d  mov     eax, edi
0x14000a06f  lea     r11, [rsp+78h+var_8]
0x14000a074  mov     rbx, [r11+10h]
0x14000a078  mov     rsi, [r11+18h]
0x14000a07c  mov     rsp, r11
0x14000a07f  pop     rdi
0x14000a080  retn
0x140014e1c  push    rbp
0x140014e1e  sub     rsp, 30h
0x140014e22  mov     rbp, rdx
0x140014e25  mov     rcx, [rbp+30h]; P
0x140014e29  test    rcx, rcx
0x140014e2c  jz      short loc_140014E34
0x140014e2e  call    VfsReleaseMappingEntry
0x140014e33  nop
0x140014e34  add     rsp, 30h
0x140014e38  pop     rbp
0x140014e39  retn
```
