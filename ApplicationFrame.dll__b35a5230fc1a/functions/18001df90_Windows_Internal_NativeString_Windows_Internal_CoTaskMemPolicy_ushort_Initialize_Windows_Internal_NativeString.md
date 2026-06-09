# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::Initialize(Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> const &)

- ea: `0x18001df90`
- end: `0x18001e1af`
- name: `?Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJAEBV123@@Z`
- size: `543`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001dee0`
- `0x180060560`

## callees

- `0x18001df90`
- `0x18001e260`
- `0x18002e020`
- `0x1800532a8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18001e18e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18001e18e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001e03c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001e03c`

## pseudocode

```c
__int64 __fastcall Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::Initialize(
        __int64 a1,
        _QWORD *a2)
{
  unsigned __int64 v2; // rax
  unsigned __int64 v3; // rdi
  _WORD *v5; // rbx
  unsigned __int64 v6; // rsi
  unsigned __int64 v7; // r9
  _WORD *v8; // rax
  int v9; // r12d
  _WORD *v10; // rdx
  unsigned __int64 v11; // rax
  _WORD *v12; // rax
  _QWORD *v14; // rcx
  __int64 v15; // r9
  unsigned __int64 v16; // r14
  LPVOID v17; // rax
  unsigned __int64 v18; // [rsp+58h] [rbp+10h] BYREF

  v2 = a2[1];
  v3 = -1;
  if ( v2 == -1 )
  {
    if ( *a2 )
    {
      v2 = -1;
      do
        ++v2;
      while ( *(_WORD *)(*a2 + 2 * v2) );
      v5 = (_WORD *)*a2;
      goto LABEL_7;
    }
LABEL_36:
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(a1);
    return 0;
  }
  v5 = (_WORD *)*a2;
  if ( !*a2 )
    goto LABEL_36;
  do
LABEL_7:
    ++v3;
  while ( v5[v3] );
  if ( v2 == -1 )
  {
    v2 = v3;
  }
  else if ( v2 < v3 )
  {
    v3 = v2;
  }
  v6 = v2 + 1;
  if ( v2 + 1 < v2 )
    return 2147942934LL;
  v7 = *(_QWORD *)(a1 + 16);
  if ( v7 == -1 )
  {
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCount(a1);
    if ( *v14 )
      v7 = v14[1] + 1LL;
    else
      v7 = 0;
    v14[2] = v7;
  }
  if ( v7 )
  {
    v9 = 0;
    if ( v6 > v7 )
    {
      v18 = 0;
      v9 = ULongLongMult(v7, 2u, &v18);
      if ( v9 >= 0 )
      {
        v16 = v18;
        if ( v18 - v15 > 0x800 )
          v16 = v15 + 2048;
        if ( v6 > v16 )
          v16 = v6;
        v17 = CoTaskMemRealloc(*(LPVOID *)a1, 2 * v16);
        if ( !v17 )
          return 2147942414LL;
        *(_QWORD *)(a1 + 16) = v16;
        *(_QWORD *)a1 = v17;
        goto LABEL_19;
      }
    }
  }
  else
  {
    if ( !is_mul_ok(v6, 2u) )
      return 2147942934LL;
    v8 = CoTaskMemAlloc(2 * v6);
    if ( v8 )
    {
      *(_QWORD *)(a1 + 16) = v6;
      v9 = 0;
      *(_QWORD *)a1 = v8;
      *v8 = 0;
LABEL_19:
      if ( v6 )
      {
        v10 = *(_WORD **)a1;
        if ( v3 > 0x7FFFFFFE || v6 > 0x7FFFFFFF )
        {
          *v10 = 0;
        }
        else
        {
          v11 = v3;
          do
          {
            if ( !v11 )
              break;
            if ( !*v5 )
              break;
            *v10++ = *v5++;
            --v11;
            --v6;
          }
          while ( v6 );
          v12 = v10 - 1;
          if ( v6 )
            v12 = v10;
          *v12 = 0;
        }
      }
      *(_QWORD *)(a1 + 8) = v3;
      return (unsigned int)v9;
    }
    v9 = -2147024882;
  }
  if ( v9 >= 0 )
    goto LABEL_19;
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18001df90  push    rbx
0x18001df92  push    rbp
0x18001df93  push    rdi
0x18001df94  push    r15
0x18001df96  sub     rsp, 28h
0x18001df9a  mov     rax, [rdx+8]
0x18001df9e  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x18001dfa5  mov     r15, rcx
0x18001dfa8  cmp     rax, rdi
0x18001dfab  jnz     short loc_18001DFD0
0x18001dfad  mov     r8, [rdx]
0x18001dfb0  test    r8, r8
0x18001dfb3  jz      loc_18001E10D
0x18001dfb9  mov     rax, rdi
0x18001dfbc  nop     dword ptr [rax+00h]
0x18001dfc0  inc     rax
0x18001dfc3  cmp     word ptr [r8+rax*2], 0
0x18001dfc9  jnz     short loc_18001DFC0
0x18001dfcb  mov     rbx, r8
0x18001dfce  jmp     short loc_18001DFDC
0x18001dfd0  mov     rbx, [rdx]
0x18001dfd3  test    rbx, rbx
0x18001dfd6  jz      loc_18001E10D
0x18001dfdc  mov     [rsp+48h+arg_0], rsi
0x18001dfe1  inc     rdi
0x18001dfe4  cmp     word ptr [rbx+rdi*2], 0
0x18001dfe9  jnz     short loc_18001DFE1
0x18001dfeb  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001dfef  jz      loc_18001E0FA
0x18001dff5  cmp     rax, rdi
0x18001dff8  cmovb   rdi, rax
0x18001dffc  lea     rsi, [rax+1]
0x18001e000  cmp     rsi, rax
0x18001e003  jb      loc_18001E0DF
0x18001e009  mov     r9, [rcx+10h]
0x18001e00d  xor     ebp, ebp
0x18001e00f  cmp     r9, 0FFFFFFFFFFFFFFFFh
0x18001e013  jz      loc_18001E125
0x18001e019  mov     [rsp+48h+arg_10], r12
0x18001e01e  mov     [rsp+48h+var_28], r14
0x18001e023  test    r9, r9
0x18001e026  jnz     short loc_18001E05A
0x18001e028  mov     eax, 2
0x18001e02d  mul     rsi
0x18001e030  test    rdx, rdx
0x18001e033  jnz     loc_18001E0F3
0x18001e039  mov     rcx, rax; cb
0x18001e03c  call    cs:__imp_CoTaskMemAlloc
0x18001e042  test    rax, rax
0x18001e045  jz      loc_18001E102
0x18001e04b  mov     [r15+10h], rsi
0x18001e04f  mov     r12d, ebp
0x18001e052  mov     [r15], rax
0x18001e055  mov     [rax], bp
0x18001e058  jmp     short loc_18001E06B
0x18001e05a  mov     r12d, ebp
0x18001e05d  cmp     rsi, r9
0x18001e060  ja      loc_18001E144
0x18001e066  test    r12d, r12d
0x18001e069  js      short loc_18001E0C3
0x18001e06b  test    rsi, rsi
0x18001e06e  jz      short loc_18001E0BF
0x18001e070  mov     rdx, [r15]
0x18001e073  cmp     rdi, 7FFFFFFEh
0x18001e07a  ja      loc_18001E120
0x18001e080  cmp     rsi, 7FFFFFFFh
0x18001e087  ja      loc_18001E120
0x18001e08d  mov     rax, rdi
0x18001e090  test    rax, rax
0x18001e093  jz      short loc_18001E0B1
0x18001e095  movzx   ecx, word ptr [rbx]
0x18001e098  test    cx, cx
0x18001e09b  jz      short loc_18001E0B1
0x18001e09d  mov     [rdx], cx
0x18001e0a0  add     rbx, 2
0x18001e0a4  add     rdx, 2
0x18001e0a8  dec     rax
0x18001e0ab  sub     rsi, 1
0x18001e0af  jnz     short loc_18001E090
0x18001e0b1  test    rsi, rsi
0x18001e0b4  lea     rax, [rdx-2]
0x18001e0b8  cmovnz  rax, rdx
0x18001e0bc  mov     [rax], bp
0x18001e0bf  mov     [r15+8], rdi
0x18001e0c3  mov     eax, r12d
0x18001e0c6  mov     r12, [rsp+48h+arg_10]
0x18001e0cb  mov     r14, [rsp+48h+var_28]
0x18001e0d0  mov     rsi, [rsp+48h+arg_0]
0x18001e0d5  add     rsp, 28h
0x18001e0d9  pop     r15
0x18001e0db  pop     rdi
0x18001e0dc  pop     rbp
0x18001e0dd  pop     rbx
0x18001e0de  retn
0x18001e0df  mov     rsi, [rsp+48h+arg_0]
0x18001e0e4  mov     eax, 80070216h
0x18001e0e9  add     rsp, 28h
0x18001e0ed  pop     r15
0x18001e0ef  pop     rdi
0x18001e0f0  pop     rbp
0x18001e0f1  pop     rbx
0x18001e0f2  retn
0x18001e0f3  mov     eax, 80070216h
0x18001e0f8  jmp     short loc_18001E0C6
0x18001e0fa  mov     rax, rdi
0x18001e0fd  jmp     loc_18001DFFC
0x18001e102  mov     r12d, 8007000Eh
0x18001e108  jmp     loc_18001E066
0x18001e10d  xor     ebp, ebp
0x18001e10f  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18001e114  mov     eax, ebp
0x18001e116  add     rsp, 28h
0x18001e11a  pop     r15
0x18001e11c  pop     rdi
0x18001e11d  pop     rbp
0x18001e11e  pop     rbx
0x18001e11f  retn
0x18001e120  mov     [rdx], bp
0x18001e123  jmp     short loc_18001E0BF
0x18001e125  call    ?_EnsureCount@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCount(void)
0x18001e12a  cmp     [rcx], rbp
0x18001e12d  jz      short loc_18001E138
0x18001e12f  mov     r9, [rcx+8]
0x18001e133  inc     r9
0x18001e136  jmp     short loc_18001E13B
0x18001e138  mov     r9, rbp
0x18001e13b  mov     [rcx+10h], r9
0x18001e13f  jmp     loc_18001E019
0x18001e144  lea     r8, [rsp+48h+arg_8]; unsigned __int64 *
0x18001e149  mov     [rsp+48h+arg_8], rbp
0x18001e14e  mov     edx, 2; unsigned __int64
0x18001e153  mov     rcx, r9; unsigned __int64
0x18001e156  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18001e15b  mov     r12d, eax
0x18001e15e  test    eax, eax
0x18001e160  js      loc_18001E066
0x18001e166  mov     r14, [rsp+48h+arg_8]
0x18001e16b  mov     rax, r14
0x18001e16e  sub     rax, r9
0x18001e171  cmp     rax, 800h
0x18001e177  jbe     short loc_18001E180
0x18001e179  lea     r14, [r9+800h]
0x18001e180  mov     rcx, [r15]; pv
0x18001e183  cmp     rsi, r14
0x18001e186  cmova   r14, rsi
0x18001e18a  lea     rdx, [r14+r14]; cb
0x18001e18e  call    cs:__imp_CoTaskMemRealloc
0x18001e194  test    rax, rax
0x18001e197  jz      short loc_18001E1A5
0x18001e199  mov     [r15+10h], r14
0x18001e19d  mov     [r15], rax
0x18001e1a0  jmp     loc_18001E06B
0x18001e1a5  mov     eax, 8007000Eh
0x18001e1aa  jmp     loc_18001E0C6
```
