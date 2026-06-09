# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCapacity(unsigned __int64)

- ea: `0x1800198b8`
- end: `0x1800199ad`
- name: `?_EnsureCapacity@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJ_K@Z`
- size: `245`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180016400`
- `0x180019b90`
- `0x18001d790`

## callees

- `0x180019590`
- `0x1800198b8`
- `0x1800199b4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180019989`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180019989`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180019926`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180019926`

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
0x1800198b8  push    rbx
0x1800198ba  push    rbp
0x1800198bb  push    rsi
0x1800198bc  push    rdi
0x1800198bd  sub     rsp, 28h
0x1800198c1  lea     rbp, [rdx+1]
0x1800198c5  mov     rdi, rcx
0x1800198c8  cmp     rbp, rdx
0x1800198cb  jnb     short loc_1800198D7
0x1800198cd  mov     ebx, 80070216h
0x1800198d2  jmp     loc_1800199A2
0x1800198d7  mov     r9, [rcx+10h]
0x1800198db  cmp     r9, 0FFFFFFFFFFFFFFFFh
0x1800198df  jnz     short loc_1800198FC
0x1800198e1  call    ?_EnsureCount@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCount(void)
0x1800198e6  cmp     qword ptr [rcx], 0
0x1800198ea  jz      short loc_1800198F5
0x1800198ec  mov     r9, [rcx+8]
0x1800198f0  inc     r9
0x1800198f3  jmp     short loc_1800198F8
0x1800198f5  xor     r9d, r9d
0x1800198f8  mov     [rcx+10h], r9
0x1800198fc  test    r9, r9
0x1800198ff  jnz     short loc_18001993F
0x180019901  lea     r8, [rsp+48h+cb]; unsigned __int64 *
0x180019906  mov     [rsp+48h+cb], r9
0x18001990b  lea     edx, [r9+2]; unsigned __int64
0x18001990f  mov     rcx, rbp; unsigned __int64
0x180019912  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180019917  mov     ebx, eax
0x180019919  test    eax, eax
0x18001991b  js      loc_1800199A2
0x180019921  mov     rcx, [rsp+48h+cb]; cb
0x180019926  call    cs:__imp_CoTaskMemAlloc
0x18001992c  test    rax, rax
0x18001992f  jz      short loc_18001999D
0x180019931  xor     ecx, ecx
0x180019933  mov     [rdi+10h], rbp
0x180019937  mov     [rdi], rax
0x18001993a  mov     [rax], cx
0x18001993d  jmp     short loc_1800199A2
0x18001993f  xor     ebx, ebx
0x180019941  cmp     rbp, r9
0x180019944  jbe     short loc_1800199A2
0x180019946  lea     r8, [rsp+48h+cb]; unsigned __int64 *
0x18001994b  mov     [rsp+48h+cb], rbx
0x180019950  lea     edx, [rbx+2]; unsigned __int64
0x180019953  mov     rcx, r9; unsigned __int64
0x180019956  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18001995b  mov     ebx, eax
0x18001995d  test    eax, eax
0x18001995f  js      short loc_1800199A2
0x180019961  mov     rsi, [rsp+48h+cb]
0x180019966  mov     rax, rsi
0x180019969  sub     rax, r9
0x18001996c  cmp     rax, 800h
0x180019972  jbe     short loc_18001997B
0x180019974  lea     rsi, [r9+800h]
0x18001997b  mov     rcx, [rdi]; pv
0x18001997e  cmp     rbp, rsi
0x180019981  cmova   rsi, rbp
0x180019985  lea     rdx, [rsi+rsi]; cb
0x180019989  call    cs:__imp_CoTaskMemRealloc
0x18001998f  test    rax, rax
0x180019992  jz      short loc_18001999D
0x180019994  mov     [rdi+10h], rsi
0x180019998  mov     [rdi], rax
0x18001999b  jmp     short loc_1800199A2
0x18001999d  mov     ebx, 8007000Eh
0x1800199a2  mov     eax, ebx
0x1800199a4  add     rsp, 28h
0x1800199a8  pop     rdi
0x1800199a9  pop     rsi
0x1800199aa  pop     rbp
0x1800199ab  pop     rbx
0x1800199ac  retn
```
