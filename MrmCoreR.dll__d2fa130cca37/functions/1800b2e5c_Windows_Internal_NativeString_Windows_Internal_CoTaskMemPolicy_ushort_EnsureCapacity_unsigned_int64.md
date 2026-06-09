# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCapacity(unsigned __int64)

- ea: `0x1800b2e5c`
- end: `0x1800b2f8b`
- name: `?_EnsureCapacity@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJ_K@Z`
- size: `303`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800af3a0`

## callees

- `0x1800614b4`
- `0x1800b2e5c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800b2ef8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800b2ef8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x1800b2f5d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x1800b2f5d`

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
0x1800b2e5c  mov     [rsp+arg_0], rbx
0x1800b2e61  mov     [rsp+arg_10], rbp
0x1800b2e66  push    rsi
0x1800b2e67  push    rdi
0x1800b2e68  push    r14
0x1800b2e6a  sub     rsp, 20h
0x1800b2e6e  lea     rbp, [rdx+1]
0x1800b2e72  mov     rdi, rcx
0x1800b2e75  cmp     rbp, rdx
0x1800b2e78  jnb     short loc_1800B2E84
0x1800b2e7a  mov     ebx, 80070216h
0x1800b2e7f  jmp     loc_1800B2F76
0x1800b2e84  mov     r9, [rcx+10h]
0x1800b2e88  xor     r14d, r14d
0x1800b2e8b  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800b2e8f  cmp     r9, rcx
0x1800b2e92  jnz     short loc_1800B2ECE
0x1800b2e94  cmp     [rdi+8], rcx
0x1800b2e98  jnz     short loc_1800B2EB7
0x1800b2e9a  mov     rax, [rdi]
0x1800b2e9d  test    rax, rax
0x1800b2ea0  jz      short loc_1800B2EAE
0x1800b2ea2  inc     rcx
0x1800b2ea5  cmp     [rax+rcx*2], r14w
0x1800b2eaa  jnz     short loc_1800B2EA2
0x1800b2eac  jmp     short loc_1800B2EB1
0x1800b2eae  mov     rcx, r14
0x1800b2eb1  mov     [rdi+8], rcx
0x1800b2eb5  jmp     short loc_1800B2EBB
0x1800b2eb7  mov     rcx, [rdi+8]
0x1800b2ebb  mov     rax, [rdi]
0x1800b2ebe  inc     rcx
0x1800b2ec1  neg     rax
0x1800b2ec4  sbb     r9, r9
0x1800b2ec7  and     r9, rcx
0x1800b2eca  mov     [rdi+10h], r9
0x1800b2ece  test    r9, r9
0x1800b2ed1  jnz     short loc_1800B2F10
0x1800b2ed3  lea     r8, [rsp+38h+cb]; unsigned __int64 *
0x1800b2ed8  mov     [rsp+38h+cb], r14
0x1800b2edd  lea     edx, [r9+2]; unsigned __int64
0x1800b2ee1  mov     rcx, rbp; unsigned __int64
0x1800b2ee4  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x1800b2ee9  mov     ebx, eax
0x1800b2eeb  test    eax, eax
0x1800b2eed  js      loc_1800B2F76
0x1800b2ef3  mov     rcx, [rsp+38h+cb]; cb
0x1800b2ef8  call    cs:__imp_CoTaskMemAlloc
0x1800b2efe  test    rax, rax
0x1800b2f01  jz      short loc_1800B2F71
0x1800b2f03  mov     [rdi+10h], rbp
0x1800b2f07  mov     [rdi], rax
0x1800b2f0a  mov     [rax], r14w
0x1800b2f0e  jmp     short loc_1800B2F76
0x1800b2f10  mov     ebx, r14d
0x1800b2f13  cmp     rbp, r9
0x1800b2f16  jbe     short loc_1800B2F76
0x1800b2f18  lea     r8, [rsp+38h+cb]; unsigned __int64 *
0x1800b2f1d  mov     [rsp+38h+cb], r14
0x1800b2f22  mov     edx, 2; unsigned __int64
0x1800b2f27  mov     rcx, r9; unsigned __int64
0x1800b2f2a  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x1800b2f2f  mov     ebx, eax
0x1800b2f31  test    eax, eax
0x1800b2f33  js      short loc_1800B2F76
0x1800b2f35  mov     rsi, [rsp+38h+cb]
0x1800b2f3a  mov     rax, rsi
0x1800b2f3d  sub     rax, r9
0x1800b2f40  cmp     rax, 800h
0x1800b2f46  jbe     short loc_1800B2F4F
0x1800b2f48  lea     rsi, [r9+800h]
0x1800b2f4f  mov     rcx, [rdi]; pv
0x1800b2f52  cmp     rbp, rsi
0x1800b2f55  cmova   rsi, rbp
0x1800b2f59  lea     rdx, [rsi+rsi]; cb
0x1800b2f5d  call    cs:__imp_CoTaskMemRealloc
0x1800b2f63  test    rax, rax
0x1800b2f66  jz      short loc_1800B2F71
0x1800b2f68  mov     [rdi+10h], rsi
0x1800b2f6c  mov     [rdi], rax
0x1800b2f6f  jmp     short loc_1800B2F76
0x1800b2f71  mov     ebx, 8007000Eh
0x1800b2f76  mov     rbp, [rsp+38h+arg_10]
0x1800b2f7b  mov     eax, ebx
0x1800b2f7d  mov     rbx, [rsp+38h+arg_0]
0x1800b2f82  add     rsp, 20h
0x1800b2f86  pop     r14
0x1800b2f88  pop     rdi
0x1800b2f89  pop     rsi
0x1800b2f8a  retn
```
