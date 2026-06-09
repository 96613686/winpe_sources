# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCapacity(unsigned __int64)

- ea: `0x180024794`
- end: `0x1800248b6`
- name: `?_EnsureCapacity@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJ_K@Z`
- size: `290`
- prototype: `__int64 __fastcall(__int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800248f8`

## callees

- `0x180024764`
- `0x180024794`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180024828`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180024828`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180024888`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180024888`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
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
0x180024794  mov     [rsp+arg_0], rbx
0x180024799  mov     [rsp+arg_10], rbp
0x18002479e  push    rsi
0x18002479f  push    rdi
0x1800247a0  push    r14
0x1800247a2  sub     rsp, 20h
0x1800247a6  lea     rbp, [rdx+1]
0x1800247aa  mov     rdi, rcx
0x1800247ad  cmp     rbp, rdx
0x1800247b0  jnb     short loc_1800247BC
0x1800247b2  mov     ebx, 80070216h
0x1800247b7  jmp     loc_1800248A1
0x1800247bc  mov     r9, [rcx+10h]
0x1800247c0  xor     r14d, r14d
0x1800247c3  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800247c7  cmp     r9, rcx
0x1800247ca  jnz     short loc_180024806
0x1800247cc  cmp     [rdi+8], rcx
0x1800247d0  jnz     short loc_1800247EF
0x1800247d2  mov     rax, [rdi]
0x1800247d5  test    rax, rax
0x1800247d8  jz      short loc_1800247E6
0x1800247da  inc     rcx
0x1800247dd  cmp     [rax+rcx*2], r14w
0x1800247e2  jnz     short loc_1800247DA
0x1800247e4  jmp     short loc_1800247E9
0x1800247e6  mov     rcx, r14
0x1800247e9  mov     [rdi+8], rcx
0x1800247ed  jmp     short loc_1800247F3
0x1800247ef  mov     rcx, [rdi+8]
0x1800247f3  mov     rax, [rdi]
0x1800247f6  inc     rcx
0x1800247f9  neg     rax
0x1800247fc  sbb     r9, r9
0x1800247ff  and     r9, rcx
0x180024802  mov     [rdi+10h], r9
0x180024806  test    r9, r9
0x180024809  jnz     short loc_180024840
0x18002480b  lea     r8, [rsp+38h+cb]; unsigned __int64 *
0x180024810  mov     [rsp+38h+cb], r14
0x180024815  mov     rcx, rbp; unsigned __int64
0x180024818  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18002481d  mov     ebx, eax
0x18002481f  test    eax, eax
0x180024821  js      short loc_1800248A1
0x180024823  mov     rcx, [rsp+38h+cb]; cb
0x180024828  call    cs:__imp_CoTaskMemAlloc
0x18002482e  test    rax, rax
0x180024831  jz      short loc_18002489C
0x180024833  mov     [rdi+10h], rbp
0x180024837  mov     [rdi], rax
0x18002483a  mov     [rax], r14w
0x18002483e  jmp     short loc_1800248A1
0x180024840  mov     ebx, r14d
0x180024843  cmp     rbp, r9
0x180024846  jbe     short loc_1800248A1
0x180024848  lea     r8, [rsp+38h+cb]; unsigned __int64 *
0x18002484d  mov     [rsp+38h+cb], r14
0x180024852  mov     rcx, r9; unsigned __int64
0x180024855  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18002485a  mov     ebx, eax
0x18002485c  test    eax, eax
0x18002485e  js      short loc_1800248A1
0x180024860  mov     rsi, [rsp+38h+cb]
0x180024865  mov     rax, rsi
0x180024868  sub     rax, r9
0x18002486b  cmp     rax, 800h
0x180024871  jbe     short loc_18002487A
0x180024873  lea     rsi, [r9+800h]
0x18002487a  mov     rcx, [rdi]; pv
0x18002487d  cmp     rbp, rsi
0x180024880  cmova   rsi, rbp
0x180024884  lea     rdx, [rsi+rsi]; cb
0x180024888  call    cs:__imp_CoTaskMemRealloc
0x18002488e  test    rax, rax
0x180024891  jz      short loc_18002489C
0x180024893  mov     [rdi+10h], rsi
0x180024897  mov     [rdi], rax
0x18002489a  jmp     short loc_1800248A1
0x18002489c  mov     ebx, 8007000Eh
0x1800248a1  mov     rbp, [rsp+38h+arg_10]
0x1800248a6  mov     eax, ebx
0x1800248a8  mov     rbx, [rsp+38h+arg_0]
0x1800248ad  add     rsp, 20h
0x1800248b1  pop     r14
0x1800248b3  pop     rdi
0x1800248b4  pop     rsi
0x1800248b5  retn
```
