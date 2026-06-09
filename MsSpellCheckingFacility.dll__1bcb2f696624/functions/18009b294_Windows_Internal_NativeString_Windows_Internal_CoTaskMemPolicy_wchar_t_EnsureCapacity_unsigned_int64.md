# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<wchar_t>>::_EnsureCapacity(unsigned __int64)

- ea: `0x18009b294`
- end: `0x18009b3c3`
- name: `?_EnsureCapacity@?$NativeString@V?$CoTaskMemPolicy@_W@Internal@Windows@@@Internal@Windows@@AEAAJ_K@Z`
- size: `303`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18005a89c`

## callees

- `0x1800385f8`
- `0x18009b294`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18009b330`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18009b330`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18009b395`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18009b395`

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
0x18009b294  mov     [rsp+arg_0], rbx
0x18009b299  mov     [rsp+arg_10], rbp
0x18009b29e  push    rsi
0x18009b29f  push    rdi
0x18009b2a0  push    r14
0x18009b2a2  sub     rsp, 20h
0x18009b2a6  lea     rbp, [rdx+1]
0x18009b2aa  mov     rdi, rcx
0x18009b2ad  cmp     rbp, rdx
0x18009b2b0  jnb     short loc_18009B2BC
0x18009b2b2  mov     ebx, 80070216h
0x18009b2b7  jmp     loc_18009B3AE
0x18009b2bc  mov     r9, [rcx+10h]
0x18009b2c0  xor     r14d, r14d
0x18009b2c3  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18009b2c7  cmp     r9, rcx
0x18009b2ca  jnz     short loc_18009B306
0x18009b2cc  cmp     [rdi+8], rcx
0x18009b2d0  jnz     short loc_18009B2EF
0x18009b2d2  mov     rax, [rdi]
0x18009b2d5  test    rax, rax
0x18009b2d8  jz      short loc_18009B2E6
0x18009b2da  inc     rcx
0x18009b2dd  cmp     [rax+rcx*2], r14w
0x18009b2e2  jnz     short loc_18009B2DA
0x18009b2e4  jmp     short loc_18009B2E9
0x18009b2e6  mov     rcx, r14
0x18009b2e9  mov     [rdi+8], rcx
0x18009b2ed  jmp     short loc_18009B2F3
0x18009b2ef  mov     rcx, [rdi+8]
0x18009b2f3  mov     rax, [rdi]
0x18009b2f6  inc     rcx
0x18009b2f9  neg     rax
0x18009b2fc  sbb     r9, r9
0x18009b2ff  and     r9, rcx
0x18009b302  mov     [rdi+10h], r9
0x18009b306  test    r9, r9
0x18009b309  jnz     short loc_18009B348
0x18009b30b  lea     r8, [rsp+38h+cb]; unsigned __int64 *
0x18009b310  mov     [rsp+38h+cb], r14
0x18009b315  lea     edx, [r9+2]; unsigned __int64
0x18009b319  mov     rcx, rbp; unsigned __int64
0x18009b31c  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18009b321  mov     ebx, eax
0x18009b323  test    eax, eax
0x18009b325  js      loc_18009B3AE
0x18009b32b  mov     rcx, [rsp+38h+cb]; cb
0x18009b330  call    cs:__imp_CoTaskMemAlloc
0x18009b336  test    rax, rax
0x18009b339  jz      short loc_18009B3A9
0x18009b33b  mov     [rdi+10h], rbp
0x18009b33f  mov     [rdi], rax
0x18009b342  mov     [rax], r14w
0x18009b346  jmp     short loc_18009B3AE
0x18009b348  mov     ebx, r14d
0x18009b34b  cmp     rbp, r9
0x18009b34e  jbe     short loc_18009B3AE
0x18009b350  lea     r8, [rsp+38h+cb]; unsigned __int64 *
0x18009b355  mov     [rsp+38h+cb], r14
0x18009b35a  mov     edx, 2; unsigned __int64
0x18009b35f  mov     rcx, r9; unsigned __int64
0x18009b362  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18009b367  mov     ebx, eax
0x18009b369  test    eax, eax
0x18009b36b  js      short loc_18009B3AE
0x18009b36d  mov     rsi, [rsp+38h+cb]
0x18009b372  mov     rax, rsi
0x18009b375  sub     rax, r9
0x18009b378  cmp     rax, 800h
0x18009b37e  jbe     short loc_18009B387
0x18009b380  lea     rsi, [r9+800h]
0x18009b387  mov     rcx, [rdi]; pv
0x18009b38a  cmp     rbp, rsi
0x18009b38d  cmova   rsi, rbp
0x18009b391  lea     rdx, [rsi+rsi]; cb
0x18009b395  call    cs:__imp_CoTaskMemRealloc
0x18009b39b  test    rax, rax
0x18009b39e  jz      short loc_18009B3A9
0x18009b3a0  mov     [rdi+10h], rsi
0x18009b3a4  mov     [rdi], rax
0x18009b3a7  jmp     short loc_18009B3AE
0x18009b3a9  mov     ebx, 8007000Eh
0x18009b3ae  mov     rbp, [rsp+38h+arg_10]
0x18009b3b3  mov     eax, ebx
0x18009b3b5  mov     rbx, [rsp+38h+arg_0]
0x18009b3ba  add     rsp, 20h
0x18009b3be  pop     r14
0x18009b3c0  pop     rdi
0x18009b3c1  pop     rsi
0x18009b3c2  retn
```
