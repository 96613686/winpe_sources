# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCapacity(unsigned __int64)

- ea: `0x180021408`
- end: `0x1800214fd`
- name: `?_EnsureCapacity@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJ_K@Z`
- size: `245`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001f808`
- `0x180052128`
- `0x1800531c0`

## callees

- `0x1800213d8`
- `0x180021408`
- `0x180021504`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180021476`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180021476`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x1800214d9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x1800214d9`

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
0x180021408  push    rbx
0x18002140a  push    rbp
0x18002140b  push    rsi
0x18002140c  push    rdi
0x18002140d  sub     rsp, 28h
0x180021411  lea     rbp, [rdx+1]
0x180021415  mov     rdi, rcx
0x180021418  cmp     rbp, rdx
0x18002141b  jnb     short loc_180021427
0x18002141d  mov     ebx, 80070216h
0x180021422  jmp     loc_1800214F2
0x180021427  mov     r9, [rcx+10h]
0x18002142b  cmp     r9, 0FFFFFFFFFFFFFFFFh
0x18002142f  jnz     short loc_18002144C
0x180021431  call    ?_EnsureCount@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCount(void)
0x180021436  cmp     qword ptr [rcx], 0
0x18002143a  jz      short loc_180021445
0x18002143c  mov     r9, [rcx+8]
0x180021440  inc     r9
0x180021443  jmp     short loc_180021448
0x180021445  xor     r9d, r9d
0x180021448  mov     [rcx+10h], r9
0x18002144c  test    r9, r9
0x18002144f  jnz     short loc_18002148F
0x180021451  lea     r8, [rsp+48h+cb]; unsigned __int64 *
0x180021456  mov     [rsp+48h+cb], r9
0x18002145b  lea     edx, [r9+2]; unsigned __int64
0x18002145f  mov     rcx, rbp; unsigned __int64
0x180021462  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180021467  mov     ebx, eax
0x180021469  test    eax, eax
0x18002146b  js      loc_1800214F2
0x180021471  mov     rcx, [rsp+48h+cb]; cb
0x180021476  call    cs:__imp_CoTaskMemAlloc
0x18002147c  test    rax, rax
0x18002147f  jz      short loc_1800214ED
0x180021481  xor     ecx, ecx
0x180021483  mov     [rdi+10h], rbp
0x180021487  mov     [rdi], rax
0x18002148a  mov     [rax], cx
0x18002148d  jmp     short loc_1800214F2
0x18002148f  xor     ebx, ebx
0x180021491  cmp     rbp, r9
0x180021494  jbe     short loc_1800214F2
0x180021496  lea     r8, [rsp+48h+cb]; unsigned __int64 *
0x18002149b  mov     [rsp+48h+cb], rbx
0x1800214a0  lea     edx, [rbx+2]; unsigned __int64
0x1800214a3  mov     rcx, r9; unsigned __int64
0x1800214a6  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x1800214ab  mov     ebx, eax
0x1800214ad  test    eax, eax
0x1800214af  js      short loc_1800214F2
0x1800214b1  mov     rsi, [rsp+48h+cb]
0x1800214b6  mov     rax, rsi
0x1800214b9  sub     rax, r9
0x1800214bc  cmp     rax, 800h
0x1800214c2  jbe     short loc_1800214CB
0x1800214c4  lea     rsi, [r9+800h]
0x1800214cb  mov     rcx, [rdi]; pv
0x1800214ce  cmp     rbp, rsi
0x1800214d1  cmova   rsi, rbp
0x1800214d5  lea     rdx, [rsi+rsi]; cb
0x1800214d9  call    cs:__imp_CoTaskMemRealloc
0x1800214df  test    rax, rax
0x1800214e2  jz      short loc_1800214ED
0x1800214e4  mov     [rdi+10h], rsi
0x1800214e8  mov     [rdi], rax
0x1800214eb  jmp     short loc_1800214F2
0x1800214ed  mov     ebx, 8007000Eh
0x1800214f2  mov     eax, ebx
0x1800214f4  add     rsp, 28h
0x1800214f8  pop     rdi
0x1800214f9  pop     rsi
0x1800214fa  pop     rbp
0x1800214fb  pop     rbx
0x1800214fc  retn
```
