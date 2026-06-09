# __isa_available_init

- ea: `0x180001ce8`
- end: `0x180001e89`
- name: `__isa_available_init`
- size: `417`
- prototype: `int __cdecl()`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180001690`
- `0x1800017c0`

## callees

- `0x180001ce8`

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
0x180001ce8  mov     [rsp+arg_8], rbx
0x180001ced  mov     [rsp+arg_10], rsi
0x180001cf2  push    rdi
0x180001cf3  sub     rsp, 10h
0x180001cf7  xor     eax, eax
0x180001cf9  xor     ecx, ecx
0x180001cfb  cpuid
0x180001cfd  mov     r8d, ecx
0x180001d00  xor     r11d, r11d
0x180001d03  mov     r9d, ebx
0x180001d06  xor     r8d, 6C65746Eh
0x180001d0d  xor     r9d, 756E6547h
0x180001d14  mov     r10d, edx
0x180001d17  mov     esi, eax
0x180001d19  xor     ecx, ecx
0x180001d1b  lea     eax, [r11+1]
0x180001d1f  or      r9d, r8d
0x180001d22  cpuid
0x180001d24  xor     r10d, 49656E69h
0x180001d2b  mov     [rsp+18h+var_18], eax
0x180001d2e  or      r9d, r10d
0x180001d31  mov     [rsp+18h+var_14], ebx
0x180001d35  mov     edi, ecx
0x180001d37  mov     [rsp+18h+var_10], ecx
0x180001d3b  mov     [rsp+18h+var_C], edx
0x180001d3f  jnz     short loc_180001D91
0x180001d41  or      cs:__memcpy_nt_iters, 0FFFFFFFFFFFFFFFFh
0x180001d49  and     eax, 0FFF3FF0h
0x180001d4e  cmp     eax, 106C0h
0x180001d53  jz      short loc_180001D7D
0x180001d55  cmp     eax, 20660h
0x180001d5a  jz      short loc_180001D7D
0x180001d5c  cmp     eax, 20670h
0x180001d61  jz      short loc_180001D7D
0x180001d63  add     eax, 0FFFCF9B0h
0x180001d68  cmp     eax, 20h ; ' '
0x180001d6b  ja      short loc_180001D91
0x180001d6d  mov     rcx, 100010001h
0x180001d77  bt      rcx, rax
0x180001d7b  jnb     short loc_180001D91
0x180001d7d  mov     r8d, cs:__favor
0x180001d84  or      r8d, 1
0x180001d88  mov     cs:__favor, r8d
0x180001d8f  jmp     short loc_180001D98
0x180001d91  mov     r8d, cs:__favor
0x180001d98  mov     eax, 7
0x180001d9d  lea     r9d, [rax-5]
0x180001da1  cmp     esi, eax
0x180001da3  jl      short loc_180001DCB
0x180001da5  xor     ecx, ecx
0x180001da7  cpuid
0x180001da9  mov     [rsp+18h+var_18], eax
0x180001dac  mov     r11d, ebx
0x180001daf  mov     [rsp+18h+var_14], ebx
0x180001db3  mov     [rsp+18h+var_10], ecx
0x180001db7  mov     [rsp+18h+var_C], edx
0x180001dbb  bt      ebx, 9
0x180001dbf  jnb     short loc_180001DCB
0x180001dc1  or      r8d, r9d
0x180001dc4  mov     cs:__favor, r8d
0x180001dcb  mov     cs:__isa_available, 1
0x180001dd5  mov     cs:__isa_enabled, r9d
0x180001ddc  bt      edi, 14h
0x180001de0  jnb     loc_180001E77
0x180001de6  mov     cs:__isa_available, r9d
0x180001ded  mov     ebx, 6
0x180001df2  mov     cs:__isa_enabled, ebx
0x180001df8  bt      edi, 1Bh
0x180001dfc  jnb     short loc_180001E77
0x180001dfe  bt      edi, 1Ch
0x180001e02  jnb     short loc_180001E77
0x180001e04  xor     ecx, ecx
0x180001e06  xgetbv
0x180001e09  shl     rdx, 20h
0x180001e0d  or      rdx, rax
0x180001e10  mov     [rsp+18h+arg_0], rdx
0x180001e15  mov     rax, [rsp+18h+arg_0]
0x180001e1a  and     al, bl
0x180001e1c  cmp     al, bl
0x180001e1e  jnz     short loc_180001E77
0x180001e20  mov     eax, cs:__isa_enabled
0x180001e26  or      eax, 8
0x180001e29  mov     cs:__isa_available, 3
0x180001e33  mov     cs:__isa_enabled, eax
0x180001e39  test    r11b, 20h
0x180001e3d  jz      short loc_180001E77
0x180001e3f  or      eax, 20h
0x180001e42  mov     cs:__isa_available, 5
0x180001e4c  mov     cs:__isa_enabled, eax
0x180001e52  mov     eax, 0D0030000h
0x180001e57  and     r11d, eax
0x180001e5a  cmp     r11d, eax
0x180001e5d  jnz     short loc_180001E77
0x180001e5f  mov     rax, [rsp+18h+arg_0]
0x180001e64  and     al, 0E0h
0x180001e66  cmp     al, 0E0h
0x180001e68  jnz     short loc_180001E77
0x180001e6a  or      cs:__isa_enabled, 40h
0x180001e71  mov     cs:__isa_available, ebx
0x180001e77  mov     rbx, [rsp+18h+arg_8]
0x180001e7c  xor     eax, eax
0x180001e7e  mov     rsi, [rsp+18h+arg_10]
0x180001e83  add     rsp, 10h
0x180001e87  pop     rdi
0x180001e88  retn
```
