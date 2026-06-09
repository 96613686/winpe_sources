# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCapacity(unsigned __int64)

- ea: `0x18001f02c`
- end: `0x18001f121`
- name: `?_EnsureCapacity@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJ_K@Z`
- size: `245`
- prototype: `__int64 __fastcall(__int64, unsigned __int64)`
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180012138`
- `0x180024d10`
- `0x180024d70`
- `0x1800479a0`

## callees

- `0x18000f718`
- `0x18001f02c`
- `0x18001f128`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18001f0fd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18001f0fd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001f09a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001f09a`

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
0x18001f02c  push    rbx
0x18001f02e  push    rbp
0x18001f02f  push    rsi
0x18001f030  push    rdi
0x18001f031  sub     rsp, 28h
0x18001f035  lea     rbp, [rdx+1]
0x18001f039  mov     rdi, rcx
0x18001f03c  cmp     rbp, rdx
0x18001f03f  jnb     short loc_18001F04B
0x18001f041  mov     ebx, 80070216h
0x18001f046  jmp     loc_18001F116
0x18001f04b  mov     r9, [rcx+10h]
0x18001f04f  cmp     r9, 0FFFFFFFFFFFFFFFFh
0x18001f053  jnz     short loc_18001F070
0x18001f055  call    ?_EnsureCount@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCount(void)
0x18001f05a  cmp     qword ptr [rcx], 0
0x18001f05e  jz      short loc_18001F069
0x18001f060  mov     r9, [rcx+8]
0x18001f064  inc     r9
0x18001f067  jmp     short loc_18001F06C
0x18001f069  xor     r9d, r9d
0x18001f06c  mov     [rcx+10h], r9
0x18001f070  test    r9, r9
0x18001f073  jnz     short loc_18001F0B3
0x18001f075  lea     r8, [rsp+48h+cb]; unsigned __int64 *
0x18001f07a  mov     [rsp+48h+cb], r9
0x18001f07f  lea     edx, [r9+2]; unsigned __int64
0x18001f083  mov     rcx, rbp; unsigned __int64
0x18001f086  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18001f08b  mov     ebx, eax
0x18001f08d  test    eax, eax
0x18001f08f  js      loc_18001F116
0x18001f095  mov     rcx, [rsp+48h+cb]; cb
0x18001f09a  call    cs:__imp_CoTaskMemAlloc
0x18001f0a0  test    rax, rax
0x18001f0a3  jz      short loc_18001F111
0x18001f0a5  xor     ecx, ecx
0x18001f0a7  mov     [rdi+10h], rbp
0x18001f0ab  mov     [rdi], rax
0x18001f0ae  mov     [rax], cx
0x18001f0b1  jmp     short loc_18001F116
0x18001f0b3  xor     ebx, ebx
0x18001f0b5  cmp     rbp, r9
0x18001f0b8  jbe     short loc_18001F116
0x18001f0ba  lea     r8, [rsp+48h+cb]; unsigned __int64 *
0x18001f0bf  mov     [rsp+48h+cb], rbx
0x18001f0c4  lea     edx, [rbx+2]; unsigned __int64
0x18001f0c7  mov     rcx, r9; unsigned __int64
0x18001f0ca  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18001f0cf  mov     ebx, eax
0x18001f0d1  test    eax, eax
0x18001f0d3  js      short loc_18001F116
0x18001f0d5  mov     rsi, [rsp+48h+cb]
0x18001f0da  mov     rax, rsi
0x18001f0dd  sub     rax, r9
0x18001f0e0  cmp     rax, 800h
0x18001f0e6  jbe     short loc_18001F0EF
0x18001f0e8  lea     rsi, [r9+800h]
0x18001f0ef  mov     rcx, [rdi]; pv
0x18001f0f2  cmp     rbp, rsi
0x18001f0f5  cmova   rsi, rbp
0x18001f0f9  lea     rdx, [rsi+rsi]; cb
0x18001f0fd  call    cs:__imp_CoTaskMemRealloc
0x18001f103  test    rax, rax
0x18001f106  jz      short loc_18001F111
0x18001f108  mov     [rdi+10h], rsi
0x18001f10c  mov     [rdi], rax
0x18001f10f  jmp     short loc_18001F116
0x18001f111  mov     ebx, 8007000Eh
0x18001f116  mov     eax, ebx
0x18001f118  add     rsp, 28h
0x18001f11c  pop     rdi
0x18001f11d  pop     rsi
0x18001f11e  pop     rbp
0x18001f11f  pop     rbx
0x18001f120  retn
```
