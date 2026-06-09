# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCapacity(unsigned __int64)

- ea: `0x180033064`
- end: `0x180033193`
- name: `?_EnsureCapacity@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJ_K@Z`
- size: `303`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180032188`
- `0x18003319c`

## callees

- `0x1800211c4`
- `0x180033064`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180033165`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180033165`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180033100`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180033100`

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
0x180033064  mov     [rsp+arg_0], rbx
0x180033069  mov     [rsp+arg_10], rbp
0x18003306e  push    rsi
0x18003306f  push    rdi
0x180033070  push    r14
0x180033072  sub     rsp, 20h
0x180033076  lea     rbp, [rdx+1]
0x18003307a  mov     rdi, rcx
0x18003307d  cmp     rbp, rdx
0x180033080  jnb     short loc_18003308C
0x180033082  mov     ebx, 80070216h
0x180033087  jmp     loc_18003317E
0x18003308c  mov     r9, [rcx+10h]
0x180033090  xor     r14d, r14d
0x180033093  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180033097  cmp     r9, rcx
0x18003309a  jnz     short loc_1800330D6
0x18003309c  cmp     [rdi+8], rcx
0x1800330a0  jnz     short loc_1800330BF
0x1800330a2  mov     rax, [rdi]
0x1800330a5  test    rax, rax
0x1800330a8  jz      short loc_1800330B6
0x1800330aa  inc     rcx
0x1800330ad  cmp     [rax+rcx*2], r14w
0x1800330b2  jnz     short loc_1800330AA
0x1800330b4  jmp     short loc_1800330B9
0x1800330b6  mov     rcx, r14
0x1800330b9  mov     [rdi+8], rcx
0x1800330bd  jmp     short loc_1800330C3
0x1800330bf  mov     rcx, [rdi+8]
0x1800330c3  mov     rax, [rdi]
0x1800330c6  inc     rcx
0x1800330c9  neg     rax
0x1800330cc  sbb     r9, r9
0x1800330cf  and     r9, rcx
0x1800330d2  mov     [rdi+10h], r9
0x1800330d6  test    r9, r9
0x1800330d9  jnz     short loc_180033118
0x1800330db  lea     r8, [rsp+38h+cb]; unsigned __int64 *
0x1800330e0  mov     [rsp+38h+cb], r14
0x1800330e5  lea     edx, [r9+2]; unsigned __int64
0x1800330e9  mov     rcx, rbp; unsigned __int64
0x1800330ec  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x1800330f1  mov     ebx, eax
0x1800330f3  test    eax, eax
0x1800330f5  js      loc_18003317E
0x1800330fb  mov     rcx, [rsp+38h+cb]; cb
0x180033100  call    cs:__imp_CoTaskMemAlloc
0x180033106  test    rax, rax
0x180033109  jz      short loc_180033179
0x18003310b  mov     [rdi+10h], rbp
0x18003310f  mov     [rdi], rax
0x180033112  mov     [rax], r14w
0x180033116  jmp     short loc_18003317E
0x180033118  mov     ebx, r14d
0x18003311b  cmp     rbp, r9
0x18003311e  jbe     short loc_18003317E
0x180033120  lea     r8, [rsp+38h+cb]; unsigned __int64 *
0x180033125  mov     [rsp+38h+cb], r14
0x18003312a  mov     edx, 2; unsigned __int64
0x18003312f  mov     rcx, r9; unsigned __int64
0x180033132  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180033137  mov     ebx, eax
0x180033139  test    eax, eax
0x18003313b  js      short loc_18003317E
0x18003313d  mov     rsi, [rsp+38h+cb]
0x180033142  mov     rax, rsi
0x180033145  sub     rax, r9
0x180033148  cmp     rax, 800h
0x18003314e  jbe     short loc_180033157
0x180033150  lea     rsi, [r9+800h]
0x180033157  mov     rcx, [rdi]; pv
0x18003315a  cmp     rbp, rsi
0x18003315d  cmova   rsi, rbp
0x180033161  lea     rdx, [rsi+rsi]; cb
0x180033165  call    cs:__imp_CoTaskMemRealloc
0x18003316b  test    rax, rax
0x18003316e  jz      short loc_180033179
0x180033170  mov     [rdi+10h], rsi
0x180033174  mov     [rdi], rax
0x180033177  jmp     short loc_18003317E
0x180033179  mov     ebx, 8007000Eh
0x18003317e  mov     rbp, [rsp+38h+arg_10]
0x180033183  mov     eax, ebx
0x180033185  mov     rbx, [rsp+38h+arg_0]
0x18003318a  add     rsp, 20h
0x18003318e  pop     r14
0x180033190  pop     rdi
0x180033191  pop     rsi
0x180033192  retn
```
