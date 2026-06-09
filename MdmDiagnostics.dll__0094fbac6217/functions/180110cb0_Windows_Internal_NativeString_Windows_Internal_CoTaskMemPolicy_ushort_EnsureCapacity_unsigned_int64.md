# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCapacity(unsigned __int64)

- ea: `0x180110cb0`
- end: `0x180110dd2`
- name: `?_EnsureCapacity@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJ_K@Z`
- size: `290`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180105e28`

## callees

- `0x1800f8680`
- `0x180110cb0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180110d44`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180110d44`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180110da4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180110da4`

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
0x180110cb0  mov     [rsp+arg_0], rbx
0x180110cb5  mov     [rsp+arg_10], rbp
0x180110cba  push    rsi
0x180110cbb  push    rdi
0x180110cbc  push    r14
0x180110cbe  sub     rsp, 20h
0x180110cc2  lea     rbp, [rdx+1]
0x180110cc6  mov     rdi, rcx
0x180110cc9  cmp     rbp, rdx
0x180110ccc  jnb     short loc_180110CD8
0x180110cce  mov     ebx, 80070216h
0x180110cd3  jmp     loc_180110DBD
0x180110cd8  mov     r9, [rcx+10h]
0x180110cdc  xor     r14d, r14d
0x180110cdf  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180110ce3  cmp     r9, rcx
0x180110ce6  jnz     short loc_180110D22
0x180110ce8  cmp     [rdi+8], rcx
0x180110cec  jnz     short loc_180110D0B
0x180110cee  mov     rax, [rdi]
0x180110cf1  test    rax, rax
0x180110cf4  jz      short loc_180110D02
0x180110cf6  inc     rcx
0x180110cf9  cmp     [rax+rcx*2], r14w
0x180110cfe  jnz     short loc_180110CF6
0x180110d00  jmp     short loc_180110D05
0x180110d02  mov     rcx, r14
0x180110d05  mov     [rdi+8], rcx
0x180110d09  jmp     short loc_180110D0F
0x180110d0b  mov     rcx, [rdi+8]
0x180110d0f  mov     rax, [rdi]
0x180110d12  inc     rcx
0x180110d15  neg     rax
0x180110d18  sbb     r9, r9
0x180110d1b  and     r9, rcx
0x180110d1e  mov     [rdi+10h], r9
0x180110d22  test    r9, r9
0x180110d25  jnz     short loc_180110D5C
0x180110d27  lea     r8, [rsp+38h+cb]; unsigned __int64 *
0x180110d2c  mov     [rsp+38h+cb], r14
0x180110d31  mov     rcx, rbp; unsigned __int64
0x180110d34  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180110d39  mov     ebx, eax
0x180110d3b  test    eax, eax
0x180110d3d  js      short loc_180110DBD
0x180110d3f  mov     rcx, [rsp+38h+cb]; cb
0x180110d44  call    cs:__imp_CoTaskMemAlloc
0x180110d4a  test    rax, rax
0x180110d4d  jz      short loc_180110DB8
0x180110d4f  mov     [rdi+10h], rbp
0x180110d53  mov     [rdi], rax
0x180110d56  mov     [rax], r14w
0x180110d5a  jmp     short loc_180110DBD
0x180110d5c  mov     ebx, r14d
0x180110d5f  cmp     rbp, r9
0x180110d62  jbe     short loc_180110DBD
0x180110d64  lea     r8, [rsp+38h+cb]; unsigned __int64 *
0x180110d69  mov     [rsp+38h+cb], r14
0x180110d6e  mov     rcx, r9; unsigned __int64
0x180110d71  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180110d76  mov     ebx, eax
0x180110d78  test    eax, eax
0x180110d7a  js      short loc_180110DBD
0x180110d7c  mov     rsi, [rsp+38h+cb]
0x180110d81  mov     rax, rsi
0x180110d84  sub     rax, r9
0x180110d87  cmp     rax, 800h
0x180110d8d  jbe     short loc_180110D96
0x180110d8f  lea     rsi, [r9+800h]
0x180110d96  mov     rcx, [rdi]; pv
0x180110d99  cmp     rbp, rsi
0x180110d9c  cmova   rsi, rbp
0x180110da0  lea     rdx, [rsi+rsi]; cb
0x180110da4  call    cs:__imp_CoTaskMemRealloc
0x180110daa  test    rax, rax
0x180110dad  jz      short loc_180110DB8
0x180110daf  mov     [rdi+10h], rsi
0x180110db3  mov     [rdi], rax
0x180110db6  jmp     short loc_180110DBD
0x180110db8  mov     ebx, 8007000Eh
0x180110dbd  mov     rbp, [rsp+38h+arg_10]
0x180110dc2  mov     eax, ebx
0x180110dc4  mov     rbx, [rsp+38h+arg_0]
0x180110dc9  add     rsp, 20h
0x180110dcd  pop     r14
0x180110dcf  pop     rdi
0x180110dd0  pop     rsi
0x180110dd1  retn
```
