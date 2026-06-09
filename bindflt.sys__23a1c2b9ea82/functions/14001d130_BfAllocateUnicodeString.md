# BfAllocateUnicodeString

- ea: `0x14001d130`
- end: `0x14001d18b`
- name: `BfAllocateUnicodeString`
- size: `91`
- prototype: ``
- caller_count: `16`
- callee_count: `1`
- tags: ``

## callers

- `0x140001fd0`
- `0x140002d54`
- `0x14000fda0`
- `0x140013864`
- `0x140017360`
- `0x140018b60`
- `0x1400194b0`
- `0x140019c44`
- `0x14001c904`
- `0x14001caf8`
- `0x14001cd84`
- `0x14001d194`
- `0x14001d974`
- `0x140022950`
- `0x140023330`
- `0x140023cd8`

## callees

- `0x14001d130`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14001d15d`
- `ntoskrnl!ExAllocatePool2` at `0x14001d15d`

## pseudocode

```c
__int64 __fastcall BfAllocateUnicodeString(unsigned __int16 a1, __int64 a2, __int64 a3, __int64 a4)
{
  unsigned __int16 v5; // ax
  unsigned __int16 v6; // di
  __int64 Pool2; // rax

  *(_DWORD *)a2 = 0;
  v5 = 1;
  if ( a1 )
    v5 = a1;
  v6 = v5;
  Pool2 = ExAllocatePool2(256, v5, 1953711682, a4);
  *(_QWORD *)(a2 + 8) = Pool2;
  if ( !Pool2 )
    return 3221225626LL;
  *(_WORD *)(a2 + 2) = v6;
  return 0;
}

```

## disassembly

```asm
0x14001d130  mov     [rsp+arg_0], rbx
0x14001d135  push    rdi
0x14001d136  sub     rsp, 20h
0x14001d13a  xor     eax, eax
0x14001d13c  mov     rbx, rdx
0x14001d13f  mov     [rdx], eax
0x14001d141  test    cx, cx
0x14001d144  mov     eax, 1
0x14001d149  mov     r8d, 74734642h
0x14001d14f  cmovnz  ax, cx
0x14001d153  mov     ecx, 100h
0x14001d158  movzx   edi, ax
0x14001d15b  mov     edx, edi
0x14001d15d  call    cs:__imp_ExAllocatePool2
0x14001d164  nop     dword ptr [rax+rax+00h]
0x14001d169  mov     [rbx+8], rax
0x14001d16d  test    rax, rax
0x14001d170  jz      short loc_14001D184
0x14001d172  mov     [rbx+2], di
0x14001d176  xor     eax, eax
0x14001d178  mov     rbx, [rsp+28h+arg_0]
0x14001d17d  add     rsp, 20h
0x14001d181  pop     rdi
0x14001d182  retn
0x14001d184  mov     eax, 0C000009Ah
0x14001d189  jmp     short loc_14001D178
```
