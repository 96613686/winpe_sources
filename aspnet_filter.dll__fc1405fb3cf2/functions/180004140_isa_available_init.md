# __isa_available_init

- ea: `0x180004140`
- end: `0x1800042e1`
- name: `__isa_available_init`
- size: `417`
- prototype: `int __cdecl()`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180003aa4`
- `0x180003bd4`

## callees

- `0x180004140`

## pseudocode

```c
int __cdecl _isa_available_init()
{
  int v5; // r11d
  int v6; // r10d
  int v7; // esi
  int v9; // r9d
  int v14; // edi
  int v15; // eax
  unsigned __int64 v16; // rax
  __int64 v17; // rcx
  int v18; // r8d
  int v23; // eax
  char v25; // [rsp+20h] [rbp+8h]

  _RAX = 0;
  __asm { cpuid }
  v5 = 0;
  v6 = _RDX;
  v7 = _RAX;
  _RAX = 1;
  v9 = _RCX ^ 0x6C65746E | _RBX ^ 0x756E6547;
  __asm { cpuid }
  v14 = _RCX;
  if ( !(v6 ^ 0x49656E69 | v9)
    && ((_memcpy_nt_iters = -1, v15 = _RAX & 0xFFF3FF0, v15 == 67264)
     || v15 == 132704
     || v15 == 132720
     || (v16 = (unsigned int)(v15 - 198224), (unsigned int)v16 <= 0x20) && (v17 = 0x100010001LL, _bittest64(&v17, v16))) )
  {
    v18 = _favor | 1;
    _favor |= 1u;
  }
  else
  {
    v18 = _favor;
  }
  _RAX = 7;
  if ( v7 >= 7 )
  {
    __asm { cpuid }
    v5 = _RBX;
    if ( (_RBX & 0x200) != 0 )
      _favor = v18 | 2;
  }
  _isa_available = 1;
  _isa_enabled = 2;
  if ( (v14 & 0x100000) != 0 )
  {
    _isa_available = 2;
    _isa_enabled = 6;
    if ( (v14 & 0x8000000) != 0 && (v14 & 0x10000000) != 0 )
    {
      __asm { xgetbv }
      v25 = _RAX;
      if ( (_RAX & 6) == 6 )
      {
        v23 = _isa_enabled | 8;
        _isa_available = 3;
        _isa_enabled |= 8u;
        if ( (v5 & 0x20) != 0 )
        {
          _isa_available = 5;
          _isa_enabled = v23 | 0x20;
          if ( (v5 & 0xD0030000) == 0xD0030000 && (v25 & 0xE0) == 0xE0 )
          {
            _isa_enabled |= 0x40u;
            _isa_available = 6;
          }
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180004140  mov     [rsp+arg_8], rbx
0x180004145  mov     [rsp+arg_10], rsi
0x18000414a  push    rdi
0x18000414b  sub     rsp, 10h
0x18000414f  xor     eax, eax
0x180004151  xor     ecx, ecx
0x180004153  cpuid
0x180004155  mov     r8d, ecx
0x180004158  xor     r11d, r11d
0x18000415b  mov     r9d, ebx
0x18000415e  xor     r8d, 6C65746Eh
0x180004165  xor     r9d, 756E6547h
0x18000416c  mov     r10d, edx
0x18000416f  mov     esi, eax
0x180004171  xor     ecx, ecx
0x180004173  lea     eax, [r11+1]
0x180004177  or      r9d, r8d
0x18000417a  cpuid
0x18000417c  xor     r10d, 49656E69h
0x180004183  mov     [rsp+18h+var_18], eax
0x180004186  or      r9d, r10d
0x180004189  mov     [rsp+18h+var_14], ebx
0x18000418d  mov     edi, ecx
0x18000418f  mov     [rsp+18h+var_10], ecx
0x180004193  mov     [rsp+18h+var_C], edx
0x180004197  jnz     short loc_1800041E9
0x180004199  or      cs:__memcpy_nt_iters, 0FFFFFFFFFFFFFFFFh
0x1800041a1  and     eax, 0FFF3FF0h
0x1800041a6  cmp     eax, 106C0h
0x1800041ab  jz      short loc_1800041D5
0x1800041ad  cmp     eax, 20660h
0x1800041b2  jz      short loc_1800041D5
0x1800041b4  cmp     eax, 20670h
0x1800041b9  jz      short loc_1800041D5
0x1800041bb  add     eax, 0FFFCF9B0h
0x1800041c0  cmp     eax, 20h ; ' '
0x1800041c3  ja      short loc_1800041E9
0x1800041c5  mov     rcx, 100010001h
0x1800041cf  bt      rcx, rax
0x1800041d3  jnb     short loc_1800041E9
0x1800041d5  mov     r8d, cs:__favor
0x1800041dc  or      r8d, 1
0x1800041e0  mov     cs:__favor, r8d
0x1800041e7  jmp     short loc_1800041F0
0x1800041e9  mov     r8d, cs:__favor
0x1800041f0  mov     eax, 7
0x1800041f5  lea     r9d, [rax-5]
0x1800041f9  cmp     esi, eax
0x1800041fb  jl      short loc_180004223
0x1800041fd  xor     ecx, ecx
0x1800041ff  cpuid
0x180004201  mov     [rsp+18h+var_18], eax
0x180004204  mov     r11d, ebx
0x180004207  mov     [rsp+18h+var_14], ebx
0x18000420b  mov     [rsp+18h+var_10], ecx
0x18000420f  mov     [rsp+18h+var_C], edx
0x180004213  bt      ebx, 9
0x180004217  jnb     short loc_180004223
0x180004219  or      r8d, r9d
0x18000421c  mov     cs:__favor, r8d
0x180004223  mov     cs:__isa_available, 1
0x18000422d  mov     cs:__isa_enabled, r9d
0x180004234  bt      edi, 14h
0x180004238  jnb     loc_1800042CF
0x18000423e  mov     cs:__isa_available, r9d
0x180004245  mov     ebx, 6
0x18000424a  mov     cs:__isa_enabled, ebx
0x180004250  bt      edi, 1Bh
0x180004254  jnb     short loc_1800042CF
0x180004256  bt      edi, 1Ch
0x18000425a  jnb     short loc_1800042CF
0x18000425c  xor     ecx, ecx
0x18000425e  xgetbv
0x180004261  shl     rdx, 20h
0x180004265  or      rdx, rax
0x180004268  mov     [rsp+18h+arg_0], rdx
0x18000426d  mov     rax, [rsp+18h+arg_0]
0x180004272  and     al, bl
0x180004274  cmp     al, bl
0x180004276  jnz     short loc_1800042CF
0x180004278  mov     eax, cs:__isa_enabled
0x18000427e  or      eax, 8
0x180004281  mov     cs:__isa_available, 3
0x18000428b  mov     cs:__isa_enabled, eax
0x180004291  test    r11b, 20h
0x180004295  jz      short loc_1800042CF
0x180004297  or      eax, 20h
0x18000429a  mov     cs:__isa_available, 5
0x1800042a4  mov     cs:__isa_enabled, eax
0x1800042aa  mov     eax, 0D0030000h
0x1800042af  and     r11d, eax
0x1800042b2  cmp     r11d, eax
0x1800042b5  jnz     short loc_1800042CF
0x1800042b7  mov     rax, [rsp+18h+arg_0]
0x1800042bc  and     al, 0E0h
0x1800042be  cmp     al, 0E0h
0x1800042c0  jnz     short loc_1800042CF
0x1800042c2  or      cs:__isa_enabled, 40h
0x1800042c9  mov     cs:__isa_available, ebx
0x1800042cf  mov     rbx, [rsp+18h+arg_8]
0x1800042d4  xor     eax, eax
0x1800042d6  mov     rsi, [rsp+18h+arg_10]
0x1800042db  add     rsp, 10h
0x1800042df  pop     rdi
0x1800042e0  retn
```
