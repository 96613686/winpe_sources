# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCapacity(unsigned __int64)

- ea: `0x1800129e4`
- end: `0x180012b06`
- name: `?_EnsureCapacity@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJ_K@Z`
- size: `290`
- prototype: `__int64 __fastcall(__int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180012b48`

## callees

- `0x180012824`
- `0x1800129e4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180012a78`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180012a78`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180012ad8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180012ad8`

## pseudocode

```c
__int64 __fastcall Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCapacity(
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
    v4 = ULongLongMult(a2 + 1, a2, &cb);
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
    v4 = ULongLongMult(v5, a2, &cb);
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
0x1800129e4  mov     [rsp+arg_0], rbx
0x1800129e9  mov     [rsp+arg_10], rbp
0x1800129ee  push    rsi
0x1800129ef  push    rdi
0x1800129f0  push    r14
0x1800129f2  sub     rsp, 20h
0x1800129f6  lea     rbp, [rdx+1]
0x1800129fa  mov     rdi, rcx
0x1800129fd  cmp     rbp, rdx
0x180012a00  jnb     short loc_180012A0C
0x180012a02  mov     ebx, 80070216h
0x180012a07  jmp     loc_180012AF1
0x180012a0c  mov     r9, [rcx+10h]
0x180012a10  xor     r14d, r14d
0x180012a13  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180012a17  cmp     r9, rcx
0x180012a1a  jnz     short loc_180012A56
0x180012a1c  cmp     [rdi+8], rcx
0x180012a20  jnz     short loc_180012A3F
0x180012a22  mov     rax, [rdi]
0x180012a25  test    rax, rax
0x180012a28  jz      short loc_180012A36
0x180012a2a  inc     rcx
0x180012a2d  cmp     [rax+rcx*2], r14w
0x180012a32  jnz     short loc_180012A2A
0x180012a34  jmp     short loc_180012A39
0x180012a36  mov     rcx, r14
0x180012a39  mov     [rdi+8], rcx
0x180012a3d  jmp     short loc_180012A43
0x180012a3f  mov     rcx, [rdi+8]
0x180012a43  mov     rax, [rdi]
0x180012a46  inc     rcx
0x180012a49  neg     rax
0x180012a4c  sbb     r9, r9
0x180012a4f  and     r9, rcx
0x180012a52  mov     [rdi+10h], r9
0x180012a56  test    r9, r9
0x180012a59  jnz     short loc_180012A90
0x180012a5b  lea     r8, [rsp+38h+cb]; unsigned __int64 *
0x180012a60  mov     [rsp+38h+cb], r14
0x180012a65  mov     rcx, rbp; unsigned __int64
0x180012a68  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180012a6d  mov     ebx, eax
0x180012a6f  test    eax, eax
0x180012a71  js      short loc_180012AF1
0x180012a73  mov     rcx, [rsp+38h+cb]; cb
0x180012a78  call    cs:__imp_CoTaskMemAlloc
0x180012a7e  test    rax, rax
0x180012a81  jz      short loc_180012AEC
0x180012a83  mov     [rdi+10h], rbp
0x180012a87  mov     [rdi], rax
0x180012a8a  mov     [rax], r14w
0x180012a8e  jmp     short loc_180012AF1
0x180012a90  mov     ebx, r14d
0x180012a93  cmp     rbp, r9
0x180012a96  jbe     short loc_180012AF1
0x180012a98  lea     r8, [rsp+38h+cb]; unsigned __int64 *
0x180012a9d  mov     [rsp+38h+cb], r14
0x180012aa2  mov     rcx, r9; unsigned __int64
0x180012aa5  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180012aaa  mov     ebx, eax
0x180012aac  test    eax, eax
0x180012aae  js      short loc_180012AF1
0x180012ab0  mov     rsi, [rsp+38h+cb]
0x180012ab5  mov     rax, rsi
0x180012ab8  sub     rax, r9
0x180012abb  cmp     rax, 800h
0x180012ac1  jbe     short loc_180012ACA
0x180012ac3  lea     rsi, [r9+800h]
0x180012aca  mov     rcx, [rdi]; pv
0x180012acd  cmp     rbp, rsi
0x180012ad0  cmova   rsi, rbp
0x180012ad4  lea     rdx, [rsi+rsi]; cb
0x180012ad8  call    cs:__imp_CoTaskMemRealloc
0x180012ade  test    rax, rax
0x180012ae1  jz      short loc_180012AEC
0x180012ae3  mov     [rdi+10h], rsi
0x180012ae7  mov     [rdi], rax
0x180012aea  jmp     short loc_180012AF1
0x180012aec  mov     ebx, 8007000Eh
0x180012af1  mov     rbp, [rsp+38h+arg_10]
0x180012af6  mov     eax, ebx
0x180012af8  mov     rbx, [rsp+38h+arg_0]
0x180012afd  add     rsp, 20h
0x180012b01  pop     r14
0x180012b03  pop     rdi
0x180012b04  pop     rsi
0x180012b05  retn
```
