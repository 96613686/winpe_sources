# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCapacity(unsigned __int64)

- ea: `0x140017c28`
- end: `0x140017d57`
- name: `?_EnsureCapacity@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJ_K@Z`
- size: `303`
- prototype: `__int64 __fastcall(__int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140017de4`

## callees

- `0x140017200`
- `0x140017c28`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140017cc4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140017cc4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x140017d29`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x140017d29`

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
0x140017c28  mov     [rsp+arg_0], rbx
0x140017c2d  mov     [rsp+arg_10], rbp
0x140017c32  push    rsi
0x140017c33  push    rdi
0x140017c34  push    r14
0x140017c36  sub     rsp, 20h
0x140017c3a  lea     rbp, [rdx+1]
0x140017c3e  mov     rdi, rcx
0x140017c41  cmp     rbp, rdx
0x140017c44  jnb     short loc_140017C50
0x140017c46  mov     ebx, 80070216h
0x140017c4b  jmp     loc_140017D42
0x140017c50  mov     r9, [rcx+10h]
0x140017c54  xor     r14d, r14d
0x140017c57  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140017c5b  cmp     r9, rcx
0x140017c5e  jnz     short loc_140017C9A
0x140017c60  cmp     [rdi+8], rcx
0x140017c64  jnz     short loc_140017C83
0x140017c66  mov     rax, [rdi]
0x140017c69  test    rax, rax
0x140017c6c  jz      short loc_140017C7A
0x140017c6e  inc     rcx
0x140017c71  cmp     [rax+rcx*2], r14w
0x140017c76  jnz     short loc_140017C6E
0x140017c78  jmp     short loc_140017C7D
0x140017c7a  mov     rcx, r14
0x140017c7d  mov     [rdi+8], rcx
0x140017c81  jmp     short loc_140017C87
0x140017c83  mov     rcx, [rdi+8]
0x140017c87  mov     rax, [rdi]
0x140017c8a  inc     rcx
0x140017c8d  neg     rax
0x140017c90  sbb     r9, r9
0x140017c93  and     r9, rcx
0x140017c96  mov     [rdi+10h], r9
0x140017c9a  test    r9, r9
0x140017c9d  jnz     short loc_140017CDC
0x140017c9f  lea     r8, [rsp+38h+cb]; unsigned __int64 *
0x140017ca4  mov     [rsp+38h+cb], r14
0x140017ca9  lea     edx, [r9+2]; unsigned __int64
0x140017cad  mov     rcx, rbp; unsigned __int64
0x140017cb0  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x140017cb5  mov     ebx, eax
0x140017cb7  test    eax, eax
0x140017cb9  js      loc_140017D42
0x140017cbf  mov     rcx, [rsp+38h+cb]; cb
0x140017cc4  call    cs:__imp_CoTaskMemAlloc
0x140017cca  test    rax, rax
0x140017ccd  jz      short loc_140017D3D
0x140017ccf  mov     [rdi+10h], rbp
0x140017cd3  mov     [rdi], rax
0x140017cd6  mov     [rax], r14w
0x140017cda  jmp     short loc_140017D42
0x140017cdc  mov     ebx, r14d
0x140017cdf  cmp     rbp, r9
0x140017ce2  jbe     short loc_140017D42
0x140017ce4  lea     r8, [rsp+38h+cb]; unsigned __int64 *
0x140017ce9  mov     [rsp+38h+cb], r14
0x140017cee  mov     edx, 2; unsigned __int64
0x140017cf3  mov     rcx, r9; unsigned __int64
0x140017cf6  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x140017cfb  mov     ebx, eax
0x140017cfd  test    eax, eax
0x140017cff  js      short loc_140017D42
0x140017d01  mov     rsi, [rsp+38h+cb]
0x140017d06  mov     rax, rsi
0x140017d09  sub     rax, r9
0x140017d0c  cmp     rax, 800h
0x140017d12  jbe     short loc_140017D1B
0x140017d14  lea     rsi, [r9+800h]
0x140017d1b  mov     rcx, [rdi]; pv
0x140017d1e  cmp     rbp, rsi
0x140017d21  cmova   rsi, rbp
0x140017d25  lea     rdx, [rsi+rsi]; cb
0x140017d29  call    cs:__imp_CoTaskMemRealloc
0x140017d2f  test    rax, rax
0x140017d32  jz      short loc_140017D3D
0x140017d34  mov     [rdi+10h], rsi
0x140017d38  mov     [rdi], rax
0x140017d3b  jmp     short loc_140017D42
0x140017d3d  mov     ebx, 8007000Eh
0x140017d42  mov     rbp, [rsp+38h+arg_10]
0x140017d47  mov     eax, ebx
0x140017d49  mov     rbx, [rsp+38h+arg_0]
0x140017d4e  add     rsp, 20h
0x140017d52  pop     r14
0x140017d54  pop     rdi
0x140017d55  pop     rsi
0x140017d56  retn
```
