# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<wchar_t>>::_EnsureCapacity(unsigned __int64)

- ea: `0x180070df4`
- end: `0x180070f23`
- name: `?_EnsureCapacity@?$NativeString@V?$CoTaskMemPolicy@_W@Internal@Windows@@@Internal@Windows@@AEAAJ_K@Z`
- size: `303`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18006f004`
- `0x180076184`

## callees

- `0x180011724`
- `0x180070df4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180070ef5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180070ef5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180070e90`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180070e90`

## pseudocode

```c
__int64 __fastcall Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<wchar_t>>::_EnsureCapacity(
        __int64 a1,
        unsigned __int64 a2)
{
  unsigned __int64 v2; // rbp
  int v4; // ebx
  unsigned __int64 v5; // r9
  __int64 v6; // rcx
  _WORD *v7; // rax
  __int64 v8; // r9
  SIZE_T v9; // rsi
  LPVOID v10; // rax
  SIZE_T cb; // [rsp+48h] [rbp+10h] BYREF

  v2 = a2 + 1;
  if ( a2 + 1 < a2 )
    return (unsigned int)-2147024362;
  v5 = *(_QWORD *)(a1 + 16);
  v6 = -1;
  if ( v5 == -1 )
  {
    if ( *(_QWORD *)(a1 + 8) == -1 )
    {
      if ( *(_QWORD *)a1 )
      {
        do
          ++v6;
        while ( *(_WORD *)(*(_QWORD *)a1 + 2 * v6) );
      }
      else
      {
        v6 = 0;
      }
      *(_QWORD *)(a1 + 8) = v6;
    }
    else
    {
      v6 = *(_QWORD *)(a1 + 8);
    }
    v5 = (v6 + 1) & -(__int64)(*(_QWORD *)a1 != 0);
    *(_QWORD *)(a1 + 16) = v5;
  }
  if ( !v5 )
  {
    cb = 0;
    v4 = ULongLongMult(v2, 2u, &cb);
    if ( v4 < 0 )
      return (unsigned int)v4;
    v7 = CoTaskMemAlloc(cb);
    if ( v7 )
    {
      *(_QWORD *)(a1 + 16) = v2;
      *(_QWORD *)a1 = v7;
      *v7 = 0;
      return (unsigned int)v4;
    }
    return (unsigned int)-2147024882;
  }
  v4 = 0;
  if ( v2 > v5 )
  {
    cb = 0;
    v4 = ULongLongMult(v5, 2u, &cb);
    if ( v4 >= 0 )
    {
      v9 = cb;
      if ( cb - v8 > 0x800 )
        v9 = v8 + 2048;
      if ( v2 > v9 )
        v9 = v2;
      v10 = CoTaskMemRealloc(*(LPVOID *)a1, 2 * v9);
      if ( v10 )
      {
        *(_QWORD *)(a1 + 16) = v9;
        *(_QWORD *)a1 = v10;
        return (unsigned int)v4;
      }
      return (unsigned int)-2147024882;
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180070df4  mov     [rsp+arg_0], rbx
0x180070df9  mov     [rsp+arg_10], rbp
0x180070dfe  push    rsi
0x180070dff  push    rdi
0x180070e00  push    r14
0x180070e02  sub     rsp, 20h
0x180070e06  lea     rbp, [rdx+1]
0x180070e0a  mov     rdi, rcx
0x180070e0d  cmp     rbp, rdx
0x180070e10  jnb     short loc_180070E1C
0x180070e12  mov     ebx, 80070216h
0x180070e17  jmp     loc_180070F0E
0x180070e1c  mov     r9, [rcx+10h]
0x180070e20  xor     r14d, r14d
0x180070e23  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180070e27  cmp     r9, rcx
0x180070e2a  jnz     short loc_180070E66
0x180070e2c  cmp     [rdi+8], rcx
0x180070e30  jnz     short loc_180070E4F
0x180070e32  mov     rax, [rdi]
0x180070e35  test    rax, rax
0x180070e38  jz      short loc_180070E46
0x180070e3a  inc     rcx
0x180070e3d  cmp     [rax+rcx*2], r14w
0x180070e42  jnz     short loc_180070E3A
0x180070e44  jmp     short loc_180070E49
0x180070e46  mov     rcx, r14
0x180070e49  mov     [rdi+8], rcx
0x180070e4d  jmp     short loc_180070E53
0x180070e4f  mov     rcx, [rdi+8]
0x180070e53  mov     rax, [rdi]
0x180070e56  inc     rcx
0x180070e59  neg     rax
0x180070e5c  sbb     r9, r9
0x180070e5f  and     r9, rcx
0x180070e62  mov     [rdi+10h], r9
0x180070e66  test    r9, r9
0x180070e69  jnz     short loc_180070EA8
0x180070e6b  lea     r8, [rsp+38h+cb]; unsigned __int64 *
0x180070e70  mov     [rsp+38h+cb], r14
0x180070e75  lea     edx, [r9+2]; unsigned __int64
0x180070e79  mov     rcx, rbp; unsigned __int64
0x180070e7c  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180070e81  mov     ebx, eax
0x180070e83  test    eax, eax
0x180070e85  js      loc_180070F0E
0x180070e8b  mov     rcx, [rsp+38h+cb]; cb
0x180070e90  call    cs:__imp_CoTaskMemAlloc
0x180070e96  test    rax, rax
0x180070e99  jz      short loc_180070F09
0x180070e9b  mov     [rdi+10h], rbp
0x180070e9f  mov     [rdi], rax
0x180070ea2  mov     [rax], r14w
0x180070ea6  jmp     short loc_180070F0E
0x180070ea8  mov     ebx, r14d
0x180070eab  cmp     rbp, r9
0x180070eae  jbe     short loc_180070F0E
0x180070eb0  lea     r8, [rsp+38h+cb]; unsigned __int64 *
0x180070eb5  mov     [rsp+38h+cb], r14
0x180070eba  mov     edx, 2; unsigned __int64
0x180070ebf  mov     rcx, r9; unsigned __int64
0x180070ec2  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180070ec7  mov     ebx, eax
0x180070ec9  test    eax, eax
0x180070ecb  js      short loc_180070F0E
0x180070ecd  mov     rsi, [rsp+38h+cb]
0x180070ed2  mov     rax, rsi
0x180070ed5  sub     rax, r9
0x180070ed8  cmp     rax, 800h
0x180070ede  jbe     short loc_180070EE7
0x180070ee0  lea     rsi, [r9+800h]
0x180070ee7  mov     rcx, [rdi]; pv
0x180070eea  cmp     rbp, rsi
0x180070eed  cmova   rsi, rbp
0x180070ef1  lea     rdx, [rsi+rsi]; cb
0x180070ef5  call    cs:__imp_CoTaskMemRealloc
0x180070efb  test    rax, rax
0x180070efe  jz      short loc_180070F09
0x180070f00  mov     [rdi+10h], rsi
0x180070f04  mov     [rdi], rax
0x180070f07  jmp     short loc_180070F0E
0x180070f09  mov     ebx, 8007000Eh
0x180070f0e  mov     rbp, [rsp+38h+arg_10]
0x180070f13  mov     eax, ebx
0x180070f15  mov     rbx, [rsp+38h+arg_0]
0x180070f1a  add     rsp, 20h
0x180070f1e  pop     r14
0x180070f20  pop     rdi
0x180070f21  pop     rsi
0x180070f22  retn
```
