# __cpu_features_init

- ea: `0x140001980`
- end: `0x140001a19`
- name: `__cpu_features_init`
- size: `153`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140001d00`

## callees

- `0x140001980`

## pseudocode

```c
__int64 _cpu_features_init()
{
  int v5; // r9d
  char v11; // r8
  char v17; // cl

  _RAX = 0;
  __asm { cpuid }
  v5 = _RAX;
  _RAX = 1;
  __asm { cpuid }
  v11 = (_RCX & 0x100000) != 0 ? 8 : 0;
  if ( (_RCX & 0x100000) != 0 && (_RCX & 0x8000000) != 0 && (_RCX & 0x10000000) != 0 )
    __asm { xgetbv }
  _RAX = 7;
  if ( v5 >= 7 )
  {
    __asm { cpuid }
    v17 = v11 | 2;
    if ( (_RBX & 0x200) == 0 )
      v17 = v11;
    v11 = v17;
    if ( (_RBX & 0x20) != 0 && (v17 & 4) != 0 )
      v11 = v17 | 0x10;
  }
  _isa_info = v11 | 1;
  return 0;
}

```

## disassembly

```asm
0x140001980  push    rbx
0x140001982  sub     rsp, 10h
0x140001986  xor     eax, eax
0x140001988  xor     ecx, ecx
0x14000198a  cpuid
0x14000198c  mov     r9d, eax
0x14000198f  xor     ecx, ecx
0x140001991  mov     eax, 1
0x140001996  cpuid
0x140001998  mov     edx, ecx
0x14000199a  and     edx, 100000h
0x1400019a0  mov     eax, edx
0x1400019a2  neg     eax
0x1400019a4  sbb     r8b, r8b
0x1400019a7  and     r8b, 8
0x1400019ab  test    edx, edx
0x1400019ad  jz      short loc_1400019D3
0x1400019af  bt      ecx, 1Bh
0x1400019b3  jnb     short loc_1400019D3
0x1400019b5  bt      ecx, 1Ch
0x1400019b9  jnb     short loc_1400019D3
0x1400019bb  xor     ecx, ecx
0x1400019bd  xgetbv
0x1400019c0  shl     rdx, 20h
0x1400019c4  or      rdx, rax
0x1400019c7  and     dl, 6
0x1400019ca  cmp     dl, 6
0x1400019cd  jnz     short loc_1400019D3
0x1400019cf  or      r8b, 4
0x1400019d3  mov     eax, 7
0x1400019d8  cmp     r9d, eax
0x1400019db  jl      short loc_140001A05
0x1400019dd  xor     ecx, ecx
0x1400019df  cpuid
0x1400019e1  mov     al, r8b
0x1400019e4  or      al, 2
0x1400019e6  movzx   ecx, al
0x1400019e9  bt      ebx, 9
0x1400019ed  movzx   eax, r8b
0x1400019f1  cmovnb  ecx, eax
0x1400019f4  mov     r8b, cl
0x1400019f7  test    bl, 20h
0x1400019fa  jz      short loc_140001A05
0x1400019fc  test    cl, 4
0x1400019ff  jz      short loc_140001A05
0x140001a01  or      r8b, 10h
0x140001a05  or      r8b, 1
0x140001a09  mov     cs:__isa_info, r8b
0x140001a10  xor     eax, eax
0x140001a12  add     rsp, 10h
0x140001a16  pop     rbx
0x140001a17  retn
```
