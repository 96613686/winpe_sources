# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCapacity(unsigned __int64)

- ea: `0x180045fe4`
- end: `0x180046113`
- name: `?_EnsureCapacity@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJ_K@Z`
- size: `303`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18003eaac`
- `0x180046158`

## callees

- `0x180045e44`
- `0x180045fe4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x1800460e5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x1800460e5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180046080`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180046080`

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
0x180045fe4  mov     [rsp+arg_0], rbx
0x180045fe9  mov     [rsp+arg_10], rbp
0x180045fee  push    rsi
0x180045fef  push    rdi
0x180045ff0  push    r14
0x180045ff2  sub     rsp, 20h
0x180045ff6  lea     rbp, [rdx+1]
0x180045ffa  mov     rdi, rcx
0x180045ffd  cmp     rbp, rdx
0x180046000  jnb     short loc_18004600C
0x180046002  mov     ebx, 80070216h
0x180046007  jmp     loc_1800460FE
0x18004600c  mov     r9, [rcx+10h]
0x180046010  xor     r14d, r14d
0x180046013  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180046017  cmp     r9, rcx
0x18004601a  jnz     short loc_180046056
0x18004601c  cmp     [rdi+8], rcx
0x180046020  jnz     short loc_18004603F
0x180046022  mov     rax, [rdi]
0x180046025  test    rax, rax
0x180046028  jz      short loc_180046036
0x18004602a  inc     rcx
0x18004602d  cmp     [rax+rcx*2], r14w
0x180046032  jnz     short loc_18004602A
0x180046034  jmp     short loc_180046039
0x180046036  mov     rcx, r14
0x180046039  mov     [rdi+8], rcx
0x18004603d  jmp     short loc_180046043
0x18004603f  mov     rcx, [rdi+8]
0x180046043  mov     rax, [rdi]
0x180046046  inc     rcx
0x180046049  neg     rax
0x18004604c  sbb     r9, r9
0x18004604f  and     r9, rcx
0x180046052  mov     [rdi+10h], r9
0x180046056  test    r9, r9
0x180046059  jnz     short loc_180046098
0x18004605b  lea     r8, [rsp+38h+cb]; unsigned __int64 *
0x180046060  mov     [rsp+38h+cb], r14
0x180046065  lea     edx, [r9+2]; unsigned __int64
0x180046069  mov     rcx, rbp; unsigned __int64
0x18004606c  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180046071  mov     ebx, eax
0x180046073  test    eax, eax
0x180046075  js      loc_1800460FE
0x18004607b  mov     rcx, [rsp+38h+cb]; cb
0x180046080  call    cs:__imp_CoTaskMemAlloc
0x180046086  test    rax, rax
0x180046089  jz      short loc_1800460F9
0x18004608b  mov     [rdi+10h], rbp
0x18004608f  mov     [rdi], rax
0x180046092  mov     [rax], r14w
0x180046096  jmp     short loc_1800460FE
0x180046098  mov     ebx, r14d
0x18004609b  cmp     rbp, r9
0x18004609e  jbe     short loc_1800460FE
0x1800460a0  lea     r8, [rsp+38h+cb]; unsigned __int64 *
0x1800460a5  mov     [rsp+38h+cb], r14
0x1800460aa  mov     edx, 2; unsigned __int64
0x1800460af  mov     rcx, r9; unsigned __int64
0x1800460b2  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x1800460b7  mov     ebx, eax
0x1800460b9  test    eax, eax
0x1800460bb  js      short loc_1800460FE
0x1800460bd  mov     rsi, [rsp+38h+cb]
0x1800460c2  mov     rax, rsi
0x1800460c5  sub     rax, r9
0x1800460c8  cmp     rax, 800h
0x1800460ce  jbe     short loc_1800460D7
0x1800460d0  lea     rsi, [r9+800h]
0x1800460d7  mov     rcx, [rdi]; pv
0x1800460da  cmp     rbp, rsi
0x1800460dd  cmova   rsi, rbp
0x1800460e1  lea     rdx, [rsi+rsi]; cb
0x1800460e5  call    cs:__imp_CoTaskMemRealloc
0x1800460eb  test    rax, rax
0x1800460ee  jz      short loc_1800460F9
0x1800460f0  mov     [rdi+10h], rsi
0x1800460f4  mov     [rdi], rax
0x1800460f7  jmp     short loc_1800460FE
0x1800460f9  mov     ebx, 8007000Eh
0x1800460fe  mov     rbp, [rsp+38h+arg_10]
0x180046103  mov     eax, ebx
0x180046105  mov     rbx, [rsp+38h+arg_0]
0x18004610a  add     rsp, 20h
0x18004610e  pop     r14
0x180046110  pop     rdi
0x180046111  pop     rsi
0x180046112  retn
```
