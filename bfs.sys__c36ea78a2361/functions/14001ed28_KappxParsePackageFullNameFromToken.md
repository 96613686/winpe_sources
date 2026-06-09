# KappxParsePackageFullNameFromToken

- ea: `0x14001ed28`
- end: `0x14001ee29`
- name: `KappxParsePackageFullNameFromToken`
- size: `257`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14000761c`

## callees

- `0x140013980`
- `0x14001ed28`
- `0x14001ee30`
- `0x14001eeb4`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14001ee06`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001ee06`
- `ntoskrnl!ExAllocatePool2` at `0x14001ed4b`
- `ntoskrnl!ExAllocatePool2` at `0x14001ed4b`

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
0x14001ed28  push    rbx
0x14001ed2a  push    rbp
0x14001ed2b  push    rsi
0x14001ed2c  push    rdi
0x14001ed2d  push    r12
0x14001ed2f  push    r14
0x14001ed31  push    r15
0x14001ed33  sub     rsp, 20h
0x14001ed37  movzx   edx, word ptr [rcx]
0x14001ed3a  mov     r12, r8
0x14001ed3d  mov     rbp, rcx
0x14001ed40  mov     r8d, 58707041h
0x14001ed46  mov     ecx, 100h
0x14001ed4b  call    cs:__imp_ExAllocatePool2
0x14001ed52  nop     dword ptr [rax+rax+00h]
0x14001ed57  mov     r15, rax
0x14001ed5a  test    rax, rax
0x14001ed5d  jnz     short loc_14001ED69
0x14001ed5f  mov     eax, 0C0000017h
0x14001ed64  jmp     loc_14001EE14
0x14001ed69  movzx   r8d, word ptr [rbp+0]; Size
0x14001ed6e  mov     rcx, r15; void *
0x14001ed71  mov     rdx, [rbp+8]; Src
0x14001ed75  xor     ebx, ebx
0x14001ed77  call    memmove
0x14001ed7c  movzx   ebp, word ptr [rbp+0]
0x14001ed80  mov     r14, r15
0x14001ed83  shr     bp, 1
0x14001ed86  xor     esi, esi
0x14001ed88  cmp     esi, 5
0x14001ed8b  jnb     short loc_14001EDFE
0x14001ed8d  mov     r8d, 5Fh ; '_'
0x14001ed93  movzx   edx, bp
0x14001ed96  mov     rcx, r14
0x14001ed99  call    KappxSafeSearch
0x14001ed9e  movzx   edi, ax
0x14001eda1  cmp     di, bp
0x14001eda4  jnz     short loc_14001EDAB
0x14001eda6  cmp     esi, 4
0x14001eda9  jnz     short loc_14001EDF9
0x14001edab  mov     ecx, esi
0x14001edad  test    esi, esi
0x14001edaf  jz      short loc_14001EDCE
0x14001edb1  sub     ecx, 1
0x14001edb4  jz      short loc_14001EDCA
0x14001edb6  sub     ecx, 1
0x14001edb9  jz      short loc_14001EDCA
0x14001edbb  sub     ecx, 1
0x14001edbe  jz      short loc_14001EDCE
0x14001edc0  cmp     ecx, 1
0x14001edc3  jnz     short loc_14001EE24
0x14001edc5  mov     r8, r12
0x14001edc8  jmp     short loc_14001EDD1
0x14001edca  xor     ebx, ebx
0x14001edcc  jmp     short loc_14001EDE2
0x14001edce  xor     r8d, r8d
0x14001edd1  movzx   edx, di
0x14001edd4  mov     rcx, r14; Src
0x14001edd7  call    KappxParseString
0x14001eddc  mov     ebx, eax
0x14001edde  test    eax, eax
0x14001ede0  js      short loc_14001EDFE
0x14001ede2  mov     eax, 0FFFFh
0x14001ede7  lea     r14, [r14+rdi*2]
0x14001edeb  sub     ax, di
0x14001edee  add     r14, 2
0x14001edf2  add     bp, ax
0x14001edf5  inc     esi
0x14001edf7  jmp     short loc_14001ED88
0x14001edf9  mov     ebx, 80000005h
0x14001edfe  mov     edx, 58707041h; Tag
0x14001ee03  mov     rcx, r15; P
0x14001ee06  call    cs:__imp_ExFreePoolWithTag
0x14001ee0d  nop     dword ptr [rax+rax+00h]
0x14001ee12  mov     eax, ebx
0x14001ee14  add     rsp, 20h
0x14001ee18  pop     r15
0x14001ee1a  pop     r14
0x14001ee1c  pop     r12
0x14001ee1e  pop     rdi
0x14001ee1f  pop     rsi
0x14001ee20  pop     rbp
0x14001ee21  pop     rbx
0x14001ee22  retn
0x14001ee24  or      eax, 0FFFFFFFFh
0x14001ee27  jmp     short loc_14001EE14
```
