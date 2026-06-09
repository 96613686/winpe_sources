# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCapacity(unsigned __int64)

- ea: `0x18001397c`
- end: `0x180013a71`
- name: `?_EnsureCapacity@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJ_K@Z`
- size: `245`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180013db4`
- `0x1800435c8`
- `0x1800447b4`

## callees

- `0x180011724`
- `0x18001397c`
- `0x180013a78`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180013a4d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180013a4d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800139ea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800139ea`

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
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCount();
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
0x18001397c  push    rbx
0x18001397e  push    rbp
0x18001397f  push    rsi
0x180013980  push    rdi
0x180013981  sub     rsp, 28h
0x180013985  lea     rbp, [rdx+1]
0x180013989  mov     rdi, rcx
0x18001398c  cmp     rbp, rdx
0x18001398f  jnb     short loc_18001399B
0x180013991  mov     ebx, 80070216h
0x180013996  jmp     loc_180013A66
0x18001399b  mov     r9, [rcx+10h]
0x18001399f  cmp     r9, 0FFFFFFFFFFFFFFFFh
0x1800139a3  jnz     short loc_1800139C0
0x1800139a5  call    ?_EnsureCount@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCount(void)
0x1800139aa  cmp     qword ptr [rcx], 0
0x1800139ae  jz      short loc_1800139B9
0x1800139b0  mov     r9, [rcx+8]
0x1800139b4  inc     r9
0x1800139b7  jmp     short loc_1800139BC
0x1800139b9  xor     r9d, r9d
0x1800139bc  mov     [rcx+10h], r9
0x1800139c0  test    r9, r9
0x1800139c3  jnz     short loc_180013A03
0x1800139c5  lea     r8, [rsp+48h+cb]; unsigned __int64 *
0x1800139ca  mov     [rsp+48h+cb], r9
0x1800139cf  lea     edx, [r9+2]; unsigned __int64
0x1800139d3  mov     rcx, rbp; unsigned __int64
0x1800139d6  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x1800139db  mov     ebx, eax
0x1800139dd  test    eax, eax
0x1800139df  js      loc_180013A66
0x1800139e5  mov     rcx, [rsp+48h+cb]; cb
0x1800139ea  call    cs:__imp_CoTaskMemAlloc
0x1800139f0  test    rax, rax
0x1800139f3  jz      short loc_180013A61
0x1800139f5  xor     ecx, ecx
0x1800139f7  mov     [rdi+10h], rbp
0x1800139fb  mov     [rdi], rax
0x1800139fe  mov     [rax], cx
0x180013a01  jmp     short loc_180013A66
0x180013a03  xor     ebx, ebx
0x180013a05  cmp     rbp, r9
0x180013a08  jbe     short loc_180013A66
0x180013a0a  lea     r8, [rsp+48h+cb]; unsigned __int64 *
0x180013a0f  mov     [rsp+48h+cb], rbx
0x180013a14  lea     edx, [rbx+2]; unsigned __int64
0x180013a17  mov     rcx, r9; unsigned __int64
0x180013a1a  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180013a1f  mov     ebx, eax
0x180013a21  test    eax, eax
0x180013a23  js      short loc_180013A66
0x180013a25  mov     rsi, [rsp+48h+cb]
0x180013a2a  mov     rax, rsi
0x180013a2d  sub     rax, r9
0x180013a30  cmp     rax, 800h
0x180013a36  jbe     short loc_180013A3F
0x180013a38  lea     rsi, [r9+800h]
0x180013a3f  mov     rcx, [rdi]; pv
0x180013a42  cmp     rbp, rsi
0x180013a45  cmova   rsi, rbp
0x180013a49  lea     rdx, [rsi+rsi]; cb
0x180013a4d  call    cs:__imp_CoTaskMemRealloc
0x180013a53  test    rax, rax
0x180013a56  jz      short loc_180013A61
0x180013a58  mov     [rdi+10h], rsi
0x180013a5c  mov     [rdi], rax
0x180013a5f  jmp     short loc_180013A66
0x180013a61  mov     ebx, 8007000Eh
0x180013a66  mov     eax, ebx
0x180013a68  add     rsp, 28h
0x180013a6c  pop     rdi
0x180013a6d  pop     rsi
0x180013a6e  pop     rbp
0x180013a6f  pop     rbx
0x180013a70  retn
```
