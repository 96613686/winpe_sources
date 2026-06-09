# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCapacity(unsigned __int64)

- ea: `0x18002231c`
- end: `0x180022411`
- name: `?_EnsureCapacity@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJ_K@Z`
- size: `245`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `7`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180021830`
- `0x180022848`
- `0x180022bfc`
- `0x180023838`
- `0x18003106c`
- `0x1800314dc`
- `0x18003e178`

## callees

- `0x18001ff6c`
- `0x18002231c`
- `0x180022418`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002238a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002238a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x1800223ed`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x1800223ed`

## pseudocode

```c
__int64 __fastcall Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCapacity(
        __int64 a1,
        unsigned __int64 a2)
{
  unsigned __int64 v2; // rbp
  int v4; // ebx
  unsigned __int64 v5; // r9
  _QWORD *v6; // rcx
  _WORD *v7; // rax
  __int64 v8; // r9
  SIZE_T v9; // rsi
  LPVOID v10; // rax
  SIZE_T cb; // [rsp+58h] [rbp+10h] BYREF

  v2 = a2 + 1;
  if ( a2 + 1 < a2 )
    return (unsigned int)-2147024362;
  v5 = *(_QWORD *)(a1 + 16);
  if ( v5 == -1 )
  {
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCount(a1);
    if ( *v6 )
      v5 = v6[1] + 1LL;
    else
      v5 = 0;
    v6[2] = v5;
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
0x18002231c  push    rbx
0x18002231e  push    rbp
0x18002231f  push    rsi
0x180022320  push    rdi
0x180022321  sub     rsp, 28h
0x180022325  lea     rbp, [rdx+1]
0x180022329  mov     rdi, rcx
0x18002232c  cmp     rbp, rdx
0x18002232f  jnb     short loc_18002233B
0x180022331  mov     ebx, 80070216h
0x180022336  jmp     loc_180022406
0x18002233b  mov     r9, [rcx+10h]
0x18002233f  cmp     r9, 0FFFFFFFFFFFFFFFFh
0x180022343  jnz     short loc_180022360
0x180022345  call    ?_EnsureCount@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCount(void)
0x18002234a  cmp     qword ptr [rcx], 0
0x18002234e  jz      short loc_180022359
0x180022350  mov     r9, [rcx+8]
0x180022354  inc     r9
0x180022357  jmp     short loc_18002235C
0x180022359  xor     r9d, r9d
0x18002235c  mov     [rcx+10h], r9
0x180022360  test    r9, r9
0x180022363  jnz     short loc_1800223A3
0x180022365  lea     r8, [rsp+48h+cb]; unsigned __int64 *
0x18002236a  mov     [rsp+48h+cb], r9
0x18002236f  lea     edx, [r9+2]; unsigned __int64
0x180022373  mov     rcx, rbp; unsigned __int64
0x180022376  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18002237b  mov     ebx, eax
0x18002237d  test    eax, eax
0x18002237f  js      loc_180022406
0x180022385  mov     rcx, [rsp+48h+cb]; cb
0x18002238a  call    cs:__imp_CoTaskMemAlloc
0x180022390  test    rax, rax
0x180022393  jz      short loc_180022401
0x180022395  xor     ecx, ecx
0x180022397  mov     [rdi+10h], rbp
0x18002239b  mov     [rdi], rax
0x18002239e  mov     [rax], cx
0x1800223a1  jmp     short loc_180022406
0x1800223a3  xor     ebx, ebx
0x1800223a5  cmp     rbp, r9
0x1800223a8  jbe     short loc_180022406
0x1800223aa  lea     r8, [rsp+48h+cb]; unsigned __int64 *
0x1800223af  mov     [rsp+48h+cb], rbx
0x1800223b4  lea     edx, [rbx+2]; unsigned __int64
0x1800223b7  mov     rcx, r9; unsigned __int64
0x1800223ba  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x1800223bf  mov     ebx, eax
0x1800223c1  test    eax, eax
0x1800223c3  js      short loc_180022406
0x1800223c5  mov     rsi, [rsp+48h+cb]
0x1800223ca  mov     rax, rsi
0x1800223cd  sub     rax, r9
0x1800223d0  cmp     rax, 800h
0x1800223d6  jbe     short loc_1800223DF
0x1800223d8  lea     rsi, [r9+800h]
0x1800223df  mov     rcx, [rdi]; pv
0x1800223e2  cmp     rbp, rsi
0x1800223e5  cmova   rsi, rbp
0x1800223e9  lea     rdx, [rsi+rsi]; cb
0x1800223ed  call    cs:__imp_CoTaskMemRealloc
0x1800223f3  test    rax, rax
0x1800223f6  jz      short loc_180022401
0x1800223f8  mov     [rdi+10h], rsi
0x1800223fc  mov     [rdi], rax
0x1800223ff  jmp     short loc_180022406
0x180022401  mov     ebx, 8007000Eh
0x180022406  mov     eax, ebx
0x180022408  add     rsp, 28h
0x18002240c  pop     rdi
0x18002240d  pop     rsi
0x18002240e  pop     rbp
0x18002240f  pop     rbx
0x180022410  retn
```
