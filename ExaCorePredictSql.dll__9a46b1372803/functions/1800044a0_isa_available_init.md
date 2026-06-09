# __isa_available_init

- ea: `0x1800044a0`
- end: `0x180004666`
- name: `__isa_available_init`
- size: `454`
- prototype: `int __cdecl()`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180003ba0`
- `0x180003cd4`

## callees

- `0x1800044a0`

## pseudocode

```c
int __cdecl _isa_available_init()
{
  int v5; // r8d
  int v6; // r11d
  int v7; // edi
  int v8; // r10d
  int v14; // r9d
  int v15; // ecx
  int v16; // eax
  unsigned __int64 v17; // rax
  __int64 v18; // rbx
  int v23; // eax
  char v25; // [rsp+8h] [rbp-18h]

  v25 = 0;
  _RAX = 0;
  _isa_enabled = 2;
  __asm { cpuid }
  _isa_available = 1;
  v5 = _favor;
  v6 = _RCX ^ 0x444D4163 | _RDX ^ 0x69746E65 | _RBX ^ 0x68747541;
  v7 = _RAX;
  v8 = _RBX ^ 0x756E6547 | _RCX ^ 0x6C65746E | _RDX ^ 0x49656E69;
  _RAX = 1;
  __asm { cpuid }
  v14 = _RCX;
  v15 = _RAX;
  if ( !v8 )
  {
    _memcpy_nt_iters = -1;
    v5 = _favor | 4;
    v16 = _RAX & 0xFFF3FF0;
    _favor |= 4u;
    if ( v16 == 67264
      || v16 == 132704
      || v16 == 132720
      || (v17 = (unsigned int)(v16 - 198224), (unsigned int)v17 <= 0x20) && (v18 = 0x100010001LL, _bittest64(&v18, v17)) )
    {
      v5 |= 1u;
      _favor = v5;
    }
  }
  if ( !v6 && (v15 & 0xFF00F00u) >= 0x600F00 )
  {
    v5 |= 4u;
    _favor = v5;
  }
  _RAX = 7;
  if ( v7 >= 7 )
  {
    __asm { cpuid }
    v25 = _RBX;
    if ( (_RBX & 0x200) != 0 )
      _favor = v5 | 2;
  }
  if ( (v14 & 0x100000) != 0 )
  {
    _isa_available = 2;
    _isa_enabled = 6;
    if ( (v14 & 0x8000000) != 0 && (v14 & 0x10000000) != 0 )
    {
      __asm { xgetbv }
      if ( (_RAX & 6) == 6 )
      {
        v23 = _isa_enabled | 8;
        _isa_available = 3;
        _isa_enabled |= 8u;
        if ( (v25 & 0x20) != 0 )
        {
          _isa_available = 5;
          _isa_enabled = v23 | 0x20;
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800044a0  mov     [rsp-8+arg_8], rbx
0x1800044a5  mov     [rsp-8+arg_10], rdi
0x1800044aa  push    rbp
0x1800044ab  mov     rbp, rsp
0x1800044ae  sub     rsp, 20h
0x1800044b2  and     dword ptr [rbp+var_18], 0
0x1800044b6  xor     ecx, ecx
0x1800044b8  xor     eax, eax
0x1800044ba  mov     cs:__isa_enabled, 2
0x1800044c4  cpuid
0x1800044c6  mov     r8d, ecx
0x1800044c9  mov     cs:__isa_available, 1
0x1800044d3  xor     ecx, 444D4163h
0x1800044d9  mov     r9d, edx
0x1800044dc  mov     r10d, edx
0x1800044df  xor     r9d, 69746E65h
0x1800044e6  xor     r10d, 49656E69h
0x1800044ed  xor     r8d, 6C65746Eh
0x1800044f4  or      r10d, r8d
0x1800044f7  mov     r11d, ebx
0x1800044fa  mov     r8d, cs:__favor
0x180004501  xor     r11d, 68747541h
0x180004508  or      r11d, r9d
0x18000450b  mov     edx, ebx
0x18000450d  or      r11d, ecx
0x180004510  xor     edx, 756E6547h
0x180004516  xor     ecx, ecx
0x180004518  mov     edi, eax
0x18000451a  or      r10d, edx
0x18000451d  mov     eax, 1
0x180004522  cpuid
0x180004524  mov     [rbp+var_10], eax
0x180004527  mov     r9d, ecx
0x18000452a  mov     [rbp+var_8], r9d
0x18000452e  mov     ecx, eax
0x180004530  mov     [rbp+var_C], ebx
0x180004533  mov     [rbp+var_4], edx
0x180004536  test    r10d, r10d
0x180004539  jnz     short loc_18000458D
0x18000453b  or      cs:__memcpy_nt_iters, 0FFFFFFFFFFFFFFFFh
0x180004543  or      r8d, 4
0x180004547  and     eax, 0FFF3FF0h
0x18000454c  mov     cs:__favor, r8d
0x180004553  cmp     eax, 106C0h
0x180004558  jz      short loc_180004582
0x18000455a  cmp     eax, 20660h
0x18000455f  jz      short loc_180004582
0x180004561  cmp     eax, 20670h
0x180004566  jz      short loc_180004582
0x180004568  add     eax, 0FFFCF9B0h
0x18000456d  cmp     eax, 20h ; ' '
0x180004570  ja      short loc_18000458D
0x180004572  mov     rbx, 100010001h
0x18000457c  bt      rbx, rax
0x180004580  jnb     short loc_18000458D
0x180004582  or      r8d, 1
0x180004586  mov     cs:__favor, r8d
0x18000458d  test    r11d, r11d
0x180004590  jnz     short loc_1800045AB
0x180004592  and     ecx, 0FF00F00h
0x180004598  cmp     ecx, 600F00h
0x18000459e  jb      short loc_1800045AB
0x1800045a0  or      r8d, 4
0x1800045a4  mov     cs:__favor, r8d
0x1800045ab  mov     eax, 7
0x1800045b0  mov     [rbp+var_20], edx
0x1800045b3  mov     [rbp+var_1C], r9d
0x1800045b7  cmp     edi, eax
0x1800045b9  jl      short loc_1800045DF
0x1800045bb  xor     ecx, ecx
0x1800045bd  cpuid
0x1800045bf  mov     [rbp+var_10], eax
0x1800045c2  mov     [rbp+var_C], ebx
0x1800045c5  mov     [rbp+var_8], ecx
0x1800045c8  mov     [rbp+var_4], edx
0x1800045cb  mov     dword ptr [rbp+var_18], ebx
0x1800045ce  bt      ebx, 9
0x1800045d2  jnb     short loc_1800045DF
0x1800045d4  or      r8d, 2
0x1800045d8  mov     cs:__favor, r8d
0x1800045df  bt      r9d, 14h
0x1800045e4  jnb     short loc_180004654
0x1800045e6  mov     cs:__isa_available, 2
0x1800045f0  mov     cs:__isa_enabled, 6
0x1800045fa  bt      r9d, 1Bh
0x1800045ff  jnb     short loc_180004654
0x180004601  bt      r9d, 1Ch
0x180004606  jnb     short loc_180004654
0x180004608  xor     ecx, ecx
0x18000460a  xgetbv
0x18000460d  shl     rdx, 20h
0x180004611  or      rdx, rax
0x180004614  mov     [rbp+arg_0], rdx
0x180004618  mov     rax, [rbp+arg_0]
0x18000461c  and     al, 6
0x18000461e  cmp     al, 6
0x180004620  jnz     short loc_180004654
0x180004622  mov     eax, cs:__isa_enabled
0x180004628  or      eax, 8
0x18000462b  mov     cs:__isa_available, 3
0x180004635  test    [rbp+var_18], 20h
0x180004639  mov     cs:__isa_enabled, eax
0x18000463f  jz      short loc_180004654
0x180004641  or      eax, 20h
0x180004644  mov     cs:__isa_available, 5
0x18000464e  mov     cs:__isa_enabled, eax
0x180004654  mov     rbx, [rsp+20h+arg_8]
0x180004659  xor     eax, eax
0x18000465b  mov     rdi, [rsp+20h+arg_10]
0x180004660  add     rsp, 20h
0x180004664  pop     rbp
0x180004665  retn
```
