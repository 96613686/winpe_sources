# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCapacity(unsigned __int64)

- ea: `0x18003ba54`
- end: `0x18003bb3e`
- name: `?_EnsureCapacity@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJ_K@Z`
- size: `234`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800371a8`
- `0x180042820`
- `0x180042f84`

## callees

- `0x18003b788`
- `0x18003ba54`
- `0x18003bb44`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18003bb1a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18003bb1a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003baba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003baba`

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
    v4 = ULongLongMult(v2, a2, &cb);
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
0x18003ba54  push    rbx
0x18003ba56  push    rbp
0x18003ba57  push    rsi
0x18003ba58  push    rdi
0x18003ba59  sub     rsp, 28h
0x18003ba5d  lea     rbp, [rdx+1]
0x18003ba61  mov     rdi, rcx
0x18003ba64  cmp     rbp, rdx
0x18003ba67  jnb     short loc_18003BA73
0x18003ba69  mov     ebx, 80070216h
0x18003ba6e  jmp     loc_18003BB33
0x18003ba73  mov     r9, [rcx+10h]
0x18003ba77  cmp     r9, 0FFFFFFFFFFFFFFFFh
0x18003ba7b  jnz     short loc_18003BA98
0x18003ba7d  call    ?_EnsureCount@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCount(void)
0x18003ba82  cmp     qword ptr [rcx], 0
0x18003ba86  jz      short loc_18003BA91
0x18003ba88  mov     r9, [rcx+8]
0x18003ba8c  inc     r9
0x18003ba8f  jmp     short loc_18003BA94
0x18003ba91  xor     r9d, r9d
0x18003ba94  mov     [rcx+10h], r9
0x18003ba98  test    r9, r9
0x18003ba9b  jnz     short loc_18003BAD3
0x18003ba9d  lea     r8, [rsp+48h+cb]; unsigned __int64 *
0x18003baa2  mov     [rsp+48h+cb], r9
0x18003baa7  mov     rcx, rbp; unsigned __int64
0x18003baaa  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18003baaf  mov     ebx, eax
0x18003bab1  test    eax, eax
0x18003bab3  js      short loc_18003BB33
0x18003bab5  mov     rcx, [rsp+48h+cb]; cb
0x18003baba  call    cs:__imp_CoTaskMemAlloc
0x18003bac0  test    rax, rax
0x18003bac3  jz      short loc_18003BB2E
0x18003bac5  xor     ecx, ecx
0x18003bac7  mov     [rdi+10h], rbp
0x18003bacb  mov     [rdi], rax
0x18003bace  mov     [rax], cx
0x18003bad1  jmp     short loc_18003BB33
0x18003bad3  xor     ebx, ebx
0x18003bad5  cmp     rbp, r9
0x18003bad8  jbe     short loc_18003BB33
0x18003bada  lea     r8, [rsp+48h+cb]; unsigned __int64 *
0x18003badf  mov     [rsp+48h+cb], rbx
0x18003bae4  mov     rcx, r9; unsigned __int64
0x18003bae7  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18003baec  mov     ebx, eax
0x18003baee  test    eax, eax
0x18003baf0  js      short loc_18003BB33
0x18003baf2  mov     rsi, [rsp+48h+cb]
0x18003baf7  mov     rax, rsi
0x18003bafa  sub     rax, r9
0x18003bafd  cmp     rax, 800h
0x18003bb03  jbe     short loc_18003BB0C
0x18003bb05  lea     rsi, [r9+800h]
0x18003bb0c  mov     rcx, [rdi]; pv
0x18003bb0f  cmp     rbp, rsi
0x18003bb12  cmova   rsi, rbp
0x18003bb16  lea     rdx, [rsi+rsi]; cb
0x18003bb1a  call    cs:__imp_CoTaskMemRealloc
0x18003bb20  test    rax, rax
0x18003bb23  jz      short loc_18003BB2E
0x18003bb25  mov     [rdi+10h], rsi
0x18003bb29  mov     [rdi], rax
0x18003bb2c  jmp     short loc_18003BB33
0x18003bb2e  mov     ebx, 8007000Eh
0x18003bb33  mov     eax, ebx
0x18003bb35  add     rsp, 28h
0x18003bb39  pop     rdi
0x18003bb3a  pop     rsi
0x18003bb3b  pop     rbp
0x18003bb3c  pop     rbx
0x18003bb3d  retn
```
