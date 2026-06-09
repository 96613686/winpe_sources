# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCapacity(unsigned __int64)

- ea: `0x1400407b0`
- end: `0x1400408a5`
- name: `?_EnsureCapacity@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJ_K@Z`
- size: `245`
- prototype: ``
- caller_count: `6`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x14003ec3c`
- `0x14006aebc`
- `0x14006b244`
- `0x14006bd10`
- `0x14006c3b8`
- `0x14006c730`

## callees

- `0x140040020`
- `0x1400407b0`
- `0x1400408ac`

## import_xrefs

- `ole32!CoTaskMemRealloc` at `0x140040881`
- `ole32!CoTaskMemRealloc` at `0x140040881`
- `ole32!CoTaskMemAlloc` at `0x14004081e`
- `ole32!CoTaskMemAlloc` at `0x14004081e`

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
0x1400407b0  push    rbx
0x1400407b2  push    rbp
0x1400407b3  push    rsi
0x1400407b4  push    rdi
0x1400407b5  sub     rsp, 28h
0x1400407b9  lea     rbp, [rdx+1]
0x1400407bd  mov     rdi, rcx
0x1400407c0  cmp     rbp, rdx
0x1400407c3  jnb     short loc_1400407CF
0x1400407c5  mov     ebx, 80070216h
0x1400407ca  jmp     loc_14004089A
0x1400407cf  mov     r9, [rcx+10h]
0x1400407d3  cmp     r9, 0FFFFFFFFFFFFFFFFh
0x1400407d7  jnz     short loc_1400407F4
0x1400407d9  call    ?_EnsureCount@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCount(void)
0x1400407de  cmp     qword ptr [rcx], 0
0x1400407e2  jz      short loc_1400407ED
0x1400407e4  mov     r9, [rcx+8]
0x1400407e8  inc     r9
0x1400407eb  jmp     short loc_1400407F0
0x1400407ed  xor     r9d, r9d
0x1400407f0  mov     [rcx+10h], r9
0x1400407f4  test    r9, r9
0x1400407f7  jnz     short loc_140040837
0x1400407f9  lea     r8, [rsp+48h+cb]; unsigned __int64 *
0x1400407fe  mov     [rsp+48h+cb], r9
0x140040803  lea     edx, [r9+2]; unsigned __int64
0x140040807  mov     rcx, rbp; unsigned __int64
0x14004080a  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x14004080f  mov     ebx, eax
0x140040811  test    eax, eax
0x140040813  js      loc_14004089A
0x140040819  mov     rcx, [rsp+48h+cb]; cb
0x14004081e  call    cs:__imp_CoTaskMemAlloc
0x140040824  test    rax, rax
0x140040827  jz      short loc_140040895
0x140040829  xor     ecx, ecx
0x14004082b  mov     [rdi+10h], rbp
0x14004082f  mov     [rdi], rax
0x140040832  mov     [rax], cx
0x140040835  jmp     short loc_14004089A
0x140040837  xor     ebx, ebx
0x140040839  cmp     rbp, r9
0x14004083c  jbe     short loc_14004089A
0x14004083e  lea     r8, [rsp+48h+cb]; unsigned __int64 *
0x140040843  mov     [rsp+48h+cb], rbx
0x140040848  lea     edx, [rbx+2]; unsigned __int64
0x14004084b  mov     rcx, r9; unsigned __int64
0x14004084e  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x140040853  mov     ebx, eax
0x140040855  test    eax, eax
0x140040857  js      short loc_14004089A
0x140040859  mov     rsi, [rsp+48h+cb]
0x14004085e  mov     rax, rsi
0x140040861  sub     rax, r9
0x140040864  cmp     rax, 800h
0x14004086a  jbe     short loc_140040873
0x14004086c  lea     rsi, [r9+800h]
0x140040873  mov     rcx, [rdi]; pv
0x140040876  cmp     rbp, rsi
0x140040879  cmova   rsi, rbp
0x14004087d  lea     rdx, [rsi+rsi]; cb
0x140040881  call    cs:__imp_CoTaskMemRealloc
0x140040887  test    rax, rax
0x14004088a  jz      short loc_140040895
0x14004088c  mov     [rdi+10h], rsi
0x140040890  mov     [rdi], rax
0x140040893  jmp     short loc_14004089A
0x140040895  mov     ebx, 8007000Eh
0x14004089a  mov     eax, ebx
0x14004089c  add     rsp, 28h
0x1400408a0  pop     rdi
0x1400408a1  pop     rsi
0x1400408a2  pop     rbp
0x1400408a3  pop     rbx
0x1400408a4  retn
```
