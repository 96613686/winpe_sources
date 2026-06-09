# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCapacity(unsigned __int64)

- ea: `0x18002a8bc`
- end: `0x18002a9b1`
- name: `?_EnsureCapacity@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJ_K@Z`
- size: `245`
- prototype: `__int64 __fastcall(__int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001776c`
- `0x18002aed4`

## callees

- `0x18001360c`
- `0x18002a8bc`
- `0x18002a9b8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002a92a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002a92a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18002a98d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18002a98d`

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
0x18002a8bc  push    rbx
0x18002a8be  push    rbp
0x18002a8bf  push    rsi
0x18002a8c0  push    rdi
0x18002a8c1  sub     rsp, 28h
0x18002a8c5  lea     rbp, [rdx+1]
0x18002a8c9  mov     rdi, rcx
0x18002a8cc  cmp     rbp, rdx
0x18002a8cf  jnb     short loc_18002A8DB
0x18002a8d1  mov     ebx, 80070216h
0x18002a8d6  jmp     loc_18002A9A6
0x18002a8db  mov     r9, [rcx+10h]
0x18002a8df  cmp     r9, 0FFFFFFFFFFFFFFFFh
0x18002a8e3  jnz     short loc_18002A900
0x18002a8e5  call    ?_EnsureCount@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCount(void)
0x18002a8ea  cmp     qword ptr [rcx], 0
0x18002a8ee  jz      short loc_18002A8F9
0x18002a8f0  mov     r9, [rcx+8]
0x18002a8f4  inc     r9
0x18002a8f7  jmp     short loc_18002A8FC
0x18002a8f9  xor     r9d, r9d
0x18002a8fc  mov     [rcx+10h], r9
0x18002a900  test    r9, r9
0x18002a903  jnz     short loc_18002A943
0x18002a905  lea     r8, [rsp+48h+cb]; unsigned __int64 *
0x18002a90a  mov     [rsp+48h+cb], r9
0x18002a90f  lea     edx, [r9+2]; unsigned __int64
0x18002a913  mov     rcx, rbp; unsigned __int64
0x18002a916  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18002a91b  mov     ebx, eax
0x18002a91d  test    eax, eax
0x18002a91f  js      loc_18002A9A6
0x18002a925  mov     rcx, [rsp+48h+cb]; cb
0x18002a92a  call    cs:__imp_CoTaskMemAlloc
0x18002a930  test    rax, rax
0x18002a933  jz      short loc_18002A9A1
0x18002a935  xor     ecx, ecx
0x18002a937  mov     [rdi+10h], rbp
0x18002a93b  mov     [rdi], rax
0x18002a93e  mov     [rax], cx
0x18002a941  jmp     short loc_18002A9A6
0x18002a943  xor     ebx, ebx
0x18002a945  cmp     rbp, r9
0x18002a948  jbe     short loc_18002A9A6
0x18002a94a  lea     r8, [rsp+48h+cb]; unsigned __int64 *
0x18002a94f  mov     [rsp+48h+cb], rbx
0x18002a954  lea     edx, [rbx+2]; unsigned __int64
0x18002a957  mov     rcx, r9; unsigned __int64
0x18002a95a  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18002a95f  mov     ebx, eax
0x18002a961  test    eax, eax
0x18002a963  js      short loc_18002A9A6
0x18002a965  mov     rsi, [rsp+48h+cb]
0x18002a96a  mov     rax, rsi
0x18002a96d  sub     rax, r9
0x18002a970  cmp     rax, 800h
0x18002a976  jbe     short loc_18002A97F
0x18002a978  lea     rsi, [r9+800h]
0x18002a97f  mov     rcx, [rdi]; pv
0x18002a982  cmp     rbp, rsi
0x18002a985  cmova   rsi, rbp
0x18002a989  lea     rdx, [rsi+rsi]; cb
0x18002a98d  call    cs:__imp_CoTaskMemRealloc
0x18002a993  test    rax, rax
0x18002a996  jz      short loc_18002A9A1
0x18002a998  mov     [rdi+10h], rsi
0x18002a99c  mov     [rdi], rax
0x18002a99f  jmp     short loc_18002A9A6
0x18002a9a1  mov     ebx, 8007000Eh
0x18002a9a6  mov     eax, ebx
0x18002a9a8  add     rsp, 28h
0x18002a9ac  pop     rdi
0x18002a9ad  pop     rsi
0x18002a9ae  pop     rbp
0x18002a9af  pop     rbx
0x18002a9b0  retn
```
