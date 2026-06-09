# configExtension

- ea: `0x180079f58`
- end: `0x18007a11f`
- name: `configExtension`
- size: `455`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x18004afa0`

## callees

- `0x18000e9b0`
- `0x1800110c0`
- `0x180012264`
- `0x180079f58`
- `0x18007a128`
- `0x1800960c0`

## pseudocode

```c
__int64 __fastcall configExtension(__int64 a1, int *a2, __int64 a3)
{
  unsigned int v3; // ebx
  char v6; // r15
  int v7; // r12d
  int v8; // ebp
  int v9; // r13d
  int v10; // esi
  __int64 v11; // r8
  int v12; // ecx
  __int64 (__fastcall *v13)(_QWORD, int *, _QWORD, __int64, _DWORD, int, int); // rax
  __int64 result; // rax
  __int64 v15; // rdx
  int i; // esi
  __int64 (__fastcall *v17)(_QWORD, _QWORD, _QWORD, __int64, _DWORD, _DWORD, int); // rax
  int v18; // [rsp+40h] [rbp-48h]
  unsigned int v19; // [rsp+90h] [rbp+8h]
  int v20; // [rsp+A8h] [rbp+20h]

  v3 = 0;
  v6 = 0;
  v7 = -1;
  v8 = 0;
  v9 = escapedValue_0(a2, 2, 4, 8) + 1;
  while ( v8 < v9 )
  {
    CDKsyncCache_0(a2);
    v20 = a2[2];
    v10 = escapedValue_0(a2, 4, 8, 16);
    v19 = escapedValue_0(a2, 4, 8, 16);
    CDKsyncCache_0(a2);
    v12 = v19;
    v18 = a2[2];
    if ( v18 < (int)(8 * v19) )
      return 257;
    if ( v10 )
    {
      if ( v10 == 2 )
      {
        if ( (v6 & 4) != 0 )
          return 1025;
        v13 = *(__int64 (__fastcall **)(_QWORD, int *, _QWORD, __int64, _DWORD, int, int))(a3 + 112);
        if ( v13 )
        {
          result = v13(*(_QWORD *)(a3 + 120), a2, v19, 1, 0, v20, 42);
          v3 = result;
          if ( (_DWORD)result )
            return result;
          v7 = v8;
        }
        v6 |= 4u;
      }
    }
    else
    {
      for ( i = 0; i < v12; ++i )
      {
        if ( (unsigned int)CDKreadBits(a2, 8, v11) != 165 )
          return 1025;
        v12 = v19;
      }
    }
    CDKsyncCache_0(a2);
    v15 = 8 * v19 + a2[2] - v18;
    if ( (int)v15 < 0 )
      return 1025;
    CDKpushFor(a2, v15);
    ++v8;
  }
  if ( v7 != -1 )
    return v3;
  v17 = *(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64, _DWORD, _DWORD, int))(a3 + 112);
  if ( !v17 )
    return v3;
  result = v17(*(_QWORD *)(a3 + 120), 0, 0, 1, 0, 0, 42);
  v3 = result;
  if ( !(_DWORD)result )
    return v3;
  return result;
}

```

## disassembly

```asm
0x180079f58  mov     [rsp+arg_8], rbx
0x180079f5d  mov     [rsp+arg_0], rcx
0x180079f62  push    rbp
0x180079f63  push    rsi
0x180079f64  push    rdi
0x180079f65  push    r12
0x180079f67  push    r13
0x180079f69  push    r14
0x180079f6b  push    r15
0x180079f6d  sub     rsp, 50h
0x180079f71  xor     ebx, ebx
0x180079f73  mov     rdi, rdx
0x180079f76  mov     r14, r8
0x180079f79  mov     rcx, rdi
0x180079f7c  xor     r15d, r15d
0x180079f7f  or      r12d, 0FFFFFFFFh
0x180079f83  lea     edx, [rbx+2]
0x180079f86  lea     r9d, [rbx+8]
0x180079f8a  lea     r8d, [rbx+4]
0x180079f8e  call    escapedValue_0
0x180079f93  xor     ebp, ebp
0x180079f95  lea     r13d, [rax+1]
0x180079f99  cmp     ebp, r13d
0x180079f9c  jge     loc_18007A0C3
0x180079fa2  mov     rcx, rdi
0x180079fa5  call    CDKsyncCache_0
0x180079faa  mov     eax, [rdi+8]
0x180079fad  mov     edx, 4
0x180079fb2  mov     rcx, rdi
0x180079fb5  mov     [rsp+88h+arg_18], eax
0x180079fbc  lea     r9d, [rdx+0Ch]
0x180079fc0  lea     r8d, [rdx+4]
0x180079fc4  call    escapedValue_0
0x180079fc9  mov     edx, 4
0x180079fce  mov     rcx, rdi
0x180079fd1  mov     esi, eax
0x180079fd3  lea     r9d, [rdx+0Ch]
0x180079fd7  lea     r8d, [rdx+4]
0x180079fdb  call    escapedValue_0
0x180079fe0  mov     rcx, rdi
0x180079fe3  mov     dword ptr [rsp+88h+arg_0], eax
0x180079fea  call    CDKsyncCache_0
0x180079fef  mov     eax, [rdi+8]
0x180079ff2  mov     ecx, dword ptr [rsp+88h+arg_0]
0x180079ff9  mov     [rsp+88h+var_48], eax
0x180079ffd  lea     edx, ds:0[rcx*8]
0x18007a004  mov     [rsp+88h+var_44], edx
0x18007a008  cmp     eax, edx
0x18007a00a  jl      loc_18007A0BC
0x18007a010  test    esi, esi
0x18007a012  jz      short loc_18007A090
0x18007a014  cmp     esi, 2
0x18007a017  jnz     short loc_18007A06C
0x18007a019  test    r15b, 4
0x18007a01d  jnz     loc_18007A0B5
0x18007a023  mov     rax, [r14+70h]
0x18007a027  test    rax, rax
0x18007a02a  jz      short loc_18007A068
0x18007a02c  mov     edx, [rsp+88h+arg_18]
0x18007a033  lea     r9d, [rsi-1]
0x18007a037  mov     [rsp+88h+var_58], 2Ah ; '*'
0x18007a03f  mov     r8d, ecx
0x18007a042  mov     rcx, [r14+78h]
0x18007a046  mov     [rsp+88h+var_60], edx
0x18007a04a  mov     rdx, rdi
0x18007a04d  mov     [rsp+88h+var_68], 0
0x18007a055  call    cs:__guard_dispatch_icall_fptr
0x18007a05b  mov     ebx, eax
0x18007a05d  test    eax, eax
0x18007a05f  jnz     loc_18007A106
0x18007a065  mov     r12d, ebp
0x18007a068  or      r15d, 4
0x18007a06c  mov     rcx, rdi
0x18007a06f  call    CDKsyncCache_0
0x18007a074  mov     edx, [rdi+8]
0x18007a077  sub     edx, [rsp+88h+var_48]
0x18007a07b  add     edx, [rsp+88h+var_44]
0x18007a07f  js      short loc_18007A0B5
0x18007a081  mov     rcx, rdi
0x18007a084  call    CDKpushFor
0x18007a089  inc     ebp
0x18007a08b  jmp     loc_180079F99
0x18007a090  xor     esi, esi
0x18007a092  cmp     esi, ecx
0x18007a094  jge     short loc_18007A06C
0x18007a096  mov     edx, 8
0x18007a09b  mov     rcx, rdi
0x18007a09e  call    CDKreadBits
0x18007a0a3  cmp     eax, 0A5h
0x18007a0a8  jnz     short loc_18007A0B5
0x18007a0aa  mov     ecx, dword ptr [rsp+88h+arg_0]
0x18007a0b1  inc     esi
0x18007a0b3  jmp     short loc_18007A092
0x18007a0b5  mov     eax, 401h
0x18007a0ba  jmp     short loc_18007A106
0x18007a0bc  mov     eax, 101h
0x18007a0c1  jmp     short loc_18007A106
0x18007a0c3  cmp     r12d, 0FFFFFFFFh
0x18007a0c7  jnz     short loc_18007A104
0x18007a0c9  mov     rax, [r14+70h]
0x18007a0cd  test    rax, rax
0x18007a0d0  jz      short loc_18007A104
0x18007a0d2  mov     rcx, [r14+78h]
0x18007a0d6  lea     r9d, [r12+2]
0x18007a0db  mov     [rsp+88h+var_58], 2Ah ; '*'
0x18007a0e3  xor     r8d, r8d
0x18007a0e6  mov     [rsp+88h+var_60], 0
0x18007a0ee  xor     edx, edx
0x18007a0f0  mov     [rsp+88h+var_68], 0
0x18007a0f8  call    cs:__guard_dispatch_icall_fptr
0x18007a0fe  mov     ebx, eax
0x18007a100  test    eax, eax
0x18007a102  jnz     short loc_18007A106
0x18007a104  mov     eax, ebx
0x18007a106  mov     rbx, [rsp+88h+arg_8]
0x18007a10e  add     rsp, 50h
0x18007a112  pop     r15
0x18007a114  pop     r14
0x18007a116  pop     r13
0x18007a118  pop     r12
0x18007a11a  pop     rdi
0x18007a11b  pop     rsi
0x18007a11c  pop     rbp
0x18007a11d  retn
```
