# KappxParsePackageFullNameFromToken

- ea: `0x14001ecc8`
- end: `0x14001edc9`
- name: `KappxParsePackageFullNameFromToken`
- size: `257`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14000748c`

## callees

- `0x140013840`
- `0x14001ecc8`
- `0x14001edd0`
- `0x14001ee54`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14001eda6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001eda6`
- `ntoskrnl!ExAllocatePool2` at `0x14001eceb`
- `ntoskrnl!ExAllocatePool2` at `0x14001eceb`

## pseudocode

```c
__int64 __fastcall KappxParsePackageFullNameFromToken(unsigned __int16 *a1)
{
  char *Pool2; // rax
  char *v3; // r15
  int v5; // ebx
  char *v6; // r14
  unsigned __int16 v7; // bp
  unsigned int i; // esi
  unsigned __int16 v9; // ax
  __int64 v10; // rdi

  Pool2 = (char *)ExAllocatePool2(256, *a1, 1483763777);
  v3 = Pool2;
  if ( !Pool2 )
    return 3221225495LL;
  v5 = 0;
  memmove(Pool2, *((const void **)a1 + 1), *a1);
  v6 = v3;
  v7 = *a1 >> 1;
  for ( i = 0; ; ++i )
  {
    if ( i >= 5 )
      goto LABEL_16;
    v9 = KappxSafeSearch(v6, v7, 95);
    v10 = v9;
    if ( v9 == v7 && i != 4 )
    {
      v5 = -2147483643;
LABEL_16:
      ExFreePoolWithTag(v3, 0x58707041u);
      return (unsigned int)v5;
    }
    if ( i )
    {
      if ( i == 1 || i == 2 )
      {
        v5 = 0;
        goto LABEL_14;
      }
      if ( i - 3 > 1 )
        break;
    }
    v5 = KappxParseString(v6);
    if ( v5 < 0 )
      goto LABEL_16;
LABEL_14:
    v6 += 2 * v10 + 2;
    v7 += -1 - v10;
  }
  return 0xFFFFFFFFLL;
}

```

## disassembly

```asm
0x14001ecc8  push    rbx
0x14001ecca  push    rbp
0x14001eccb  push    rsi
0x14001eccc  push    rdi
0x14001eccd  push    r12
0x14001eccf  push    r14
0x14001ecd1  push    r15
0x14001ecd3  sub     rsp, 20h
0x14001ecd7  movzx   edx, word ptr [rcx]
0x14001ecda  mov     r12, r8
0x14001ecdd  mov     rbp, rcx
0x14001ece0  mov     r8d, 58707041h
0x14001ece6  mov     ecx, 100h
0x14001eceb  call    cs:__imp_ExAllocatePool2
0x14001ecf2  nop     dword ptr [rax+rax+00h]
0x14001ecf7  mov     r15, rax
0x14001ecfa  test    rax, rax
0x14001ecfd  jnz     short loc_14001ED09
0x14001ecff  mov     eax, 0C0000017h
0x14001ed04  jmp     loc_14001EDB4
0x14001ed09  movzx   r8d, word ptr [rbp+0]; Size
0x14001ed0e  mov     rcx, r15; void *
0x14001ed11  mov     rdx, [rbp+8]; Src
0x14001ed15  xor     ebx, ebx
0x14001ed17  call    memmove
0x14001ed1c  movzx   ebp, word ptr [rbp+0]
0x14001ed20  mov     r14, r15
0x14001ed23  shr     bp, 1
0x14001ed26  xor     esi, esi
0x14001ed28  cmp     esi, 5
0x14001ed2b  jnb     short loc_14001ED9E
0x14001ed2d  mov     r8d, 5Fh ; '_'
0x14001ed33  movzx   edx, bp
0x14001ed36  mov     rcx, r14
0x14001ed39  call    KappxSafeSearch
0x14001ed3e  movzx   edi, ax
0x14001ed41  cmp     di, bp
0x14001ed44  jnz     short loc_14001ED4B
0x14001ed46  cmp     esi, 4
0x14001ed49  jnz     short loc_14001ED99
0x14001ed4b  mov     ecx, esi
0x14001ed4d  test    esi, esi
0x14001ed4f  jz      short loc_14001ED6E
0x14001ed51  sub     ecx, 1
0x14001ed54  jz      short loc_14001ED6A
0x14001ed56  sub     ecx, 1
0x14001ed59  jz      short loc_14001ED6A
0x14001ed5b  sub     ecx, 1
0x14001ed5e  jz      short loc_14001ED6E
0x14001ed60  cmp     ecx, 1
0x14001ed63  jnz     short loc_14001EDC4
0x14001ed65  mov     r8, r12
0x14001ed68  jmp     short loc_14001ED71
0x14001ed6a  xor     ebx, ebx
0x14001ed6c  jmp     short loc_14001ED82
0x14001ed6e  xor     r8d, r8d
0x14001ed71  movzx   edx, di
0x14001ed74  mov     rcx, r14; Src
0x14001ed77  call    KappxParseString
0x14001ed7c  mov     ebx, eax
0x14001ed7e  test    eax, eax
0x14001ed80  js      short loc_14001ED9E
0x14001ed82  mov     eax, 0FFFFh
0x14001ed87  lea     r14, [r14+rdi*2]
0x14001ed8b  sub     ax, di
0x14001ed8e  add     r14, 2
0x14001ed92  add     bp, ax
0x14001ed95  inc     esi
0x14001ed97  jmp     short loc_14001ED28
0x14001ed99  mov     ebx, 80000005h
0x14001ed9e  mov     edx, 58707041h; Tag
0x14001eda3  mov     rcx, r15; P
0x14001eda6  call    cs:__imp_ExFreePoolWithTag
0x14001edad  nop     dword ptr [rax+rax+00h]
0x14001edb2  mov     eax, ebx
0x14001edb4  add     rsp, 20h
0x14001edb8  pop     r15
0x14001edba  pop     r14
0x14001edbc  pop     r12
0x14001edbe  pop     rdi
0x14001edbf  pop     rsi
0x14001edc0  pop     rbp
0x14001edc1  pop     rbx
0x14001edc2  retn
0x14001edc4  or      eax, 0FFFFFFFFh
0x14001edc7  jmp     short loc_14001EDB4
```
