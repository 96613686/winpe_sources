# KappxParsePackageFullNameFromToken

- ea: `0x140036d20`
- end: `0x140036e77`
- name: `KappxParsePackageFullNameFromToken`
- size: `343`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x14001f010`

## callees

- `0x140006c40`
- `0x14002de18`
- `0x14002de9c`
- `0x14002df74`
- `0x140036d20`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140036e43`
- `ntoskrnl!ExFreePoolWithTag` at `0x140036e43`
- `ntoskrnl!ExAllocatePool2` at `0x140036d40`
- `ntoskrnl!ExAllocatePool2` at `0x140036d40`

## pseudocode

```c
__int64 __fastcall KappxParsePackageFullNameFromToken(unsigned __int16 *a1)
{
  WCHAR *Pool2; // rax
  WCHAR *v3; // rdi
  unsigned int v5; // r14d
  WCHAR *v6; // r15
  unsigned __int16 v7; // r13
  unsigned int i; // r12d
  unsigned __int16 v9; // ax
  __int64 v10; // rbx
  int v11; // eax

  Pool2 = (WCHAR *)ExAllocatePool2(256, *a1, 1483763777);
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
      goto LABEL_18;
    v9 = KappxSafeSearch(v6, v7, 95);
    v10 = v9;
    if ( v9 == v7 && i != 4 )
    {
      v5 = -2147483643;
LABEL_18:
      ExFreePoolWithTag(v3, 0x58707041u);
      return v5;
    }
    if ( i )
    {
      if ( i == 1 )
      {
        v11 = KappxParseVersion(v6);
        goto LABEL_15;
      }
      if ( i == 2 )
      {
        v5 = 0;
        goto LABEL_16;
      }
      if ( i - 3 > 1 )
        break;
    }
    v11 = KappxParseString(v6);
LABEL_15:
    v5 = v11;
    if ( v11 < 0 )
      goto LABEL_18;
LABEL_16:
    v6 += v10 + 1;
    v7 += -1 - v10;
  }
  return 0xFFFFFFFFLL;
}

```

## disassembly

```asm
0x140036d20  push    rbx
0x140036d22  push    rbp
0x140036d23  push    rsi
0x140036d24  push    rdi
0x140036d25  sub     rsp, 28h
0x140036d29  mov     rbp, rdx
0x140036d2c  mov     rsi, r8
0x140036d2f  movzx   edx, word ptr [rcx]
0x140036d32  mov     rbx, rcx
0x140036d35  mov     ecx, 100h
0x140036d3a  mov     r8d, 58707041h
0x140036d40  call    cs:__imp_ExAllocatePool2
0x140036d47  nop     dword ptr [rax+rax+00h]
0x140036d4c  mov     rdi, rax
0x140036d4f  test    rax, rax
0x140036d52  jnz     short loc_140036D63
0x140036d54  mov     eax, 0C0000017h
0x140036d59  add     rsp, 28h
0x140036d5d  pop     rdi
0x140036d5e  pop     rsi
0x140036d5f  pop     rbp
0x140036d60  pop     rbx
0x140036d61  retn
0x140036d63  movzx   r8d, word ptr [rbx]; Size
0x140036d67  mov     rcx, rdi; void *
0x140036d6a  mov     rdx, [rbx+8]; Src
0x140036d6e  mov     [rsp+48h+arg_0], r12
0x140036d73  mov     [rsp+48h+arg_8], r13
0x140036d78  mov     [rsp+48h+arg_10], r14
0x140036d7d  xor     r14d, r14d
0x140036d80  mov     [rsp+48h+var_28], r15
0x140036d85  call    memmove
0x140036d8a  movzx   r13d, word ptr [rbx]
0x140036d8e  mov     r15, rdi
0x140036d91  shr     r13w, 1
0x140036d95  xor     r12d, r12d
0x140036d98  cmp     r12d, 5
0x140036d9c  jnb     loc_140036E3B
0x140036da2  mov     r8d, 5Fh ; '_'
0x140036da8  movzx   edx, r13w
0x140036dac  mov     rcx, r15
0x140036daf  call    KappxSafeSearch
0x140036db4  movzx   ebx, ax
0x140036db7  cmp     bx, r13w
0x140036dbb  jnz     short loc_140036DC3
0x140036dbd  cmp     r12d, 4
0x140036dc1  jnz     short loc_140036E35
0x140036dc3  mov     ecx, r12d
0x140036dc6  test    r12d, r12d
0x140036dc9  jz      short loc_140036E04
0x140036dcb  sub     ecx, 1
0x140036dce  jz      short loc_140036DF2
0x140036dd0  sub     ecx, 1
0x140036dd3  jz      short loc_140036DED
0x140036dd5  sub     ecx, 1
0x140036dd8  jz      short loc_140036DE8
0x140036dda  cmp     ecx, 1
0x140036ddd  jnz     loc_140036E70
0x140036de3  mov     r8, rsi
0x140036de6  jmp     short loc_140036E07
0x140036de8  xor     r8d, r8d
0x140036deb  jmp     short loc_140036E07
0x140036ded  xor     r14d, r14d
0x140036df0  jmp     short loc_140036E19
0x140036df2  mov     r8, [rsp+48h+arg_28]
0x140036df7  movzx   edx, bx
0x140036dfa  mov     rcx, r15; SourceString
0x140036dfd  call    KappxParseVersion
0x140036e02  jmp     short loc_140036E12
0x140036e04  mov     r8, rbp
0x140036e07  movzx   edx, bx
0x140036e0a  mov     rcx, r15; Src
0x140036e0d  call    KappxParseString
0x140036e12  mov     r14d, eax
0x140036e15  test    eax, eax
0x140036e17  js      short loc_140036E3B
0x140036e19  mov     eax, 0FFFFh
0x140036e1e  lea     r15, [r15+rbx*2]
0x140036e22  sub     ax, bx
0x140036e25  add     r15, 2
0x140036e29  add     r13w, ax
0x140036e2d  inc     r12d
0x140036e30  jmp     loc_140036D98
0x140036e35  mov     r14d, 80000005h
0x140036e3b  mov     edx, 58707041h; Tag
0x140036e40  mov     rcx, rdi; P
0x140036e43  call    cs:__imp_ExFreePoolWithTag
0x140036e4a  nop     dword ptr [rax+rax+00h]
0x140036e4f  mov     eax, r14d
0x140036e52  mov     r14, [rsp+48h+arg_10]
0x140036e57  mov     r13, [rsp+48h+arg_8]
0x140036e5c  mov     r12, [rsp+48h+arg_0]
0x140036e61  mov     r15, [rsp+48h+var_28]
0x140036e66  add     rsp, 28h
0x140036e6a  pop     rdi
0x140036e6b  pop     rsi
0x140036e6c  pop     rbp
0x140036e6d  pop     rbx
0x140036e6e  retn
0x140036e70  mov     eax, 0FFFFFFFFh
0x140036e75  jmp     short loc_140036E52
```
