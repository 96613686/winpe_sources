# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCapacity(unsigned __int64)

- ea: `0x180016878`
- end: `0x1800169a7`
- name: `?_EnsureCapacity@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJ_K@Z`
- size: `303`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180010770`
- `0x180038f8c`

## callees

- `0x1800166d8`
- `0x180016878`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180016914`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180016914`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180016979`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180016979`

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
0x180016878  mov     [rsp+arg_0], rbx
0x18001687d  mov     [rsp+arg_10], rbp
0x180016882  push    rsi
0x180016883  push    rdi
0x180016884  push    r14
0x180016886  sub     rsp, 20h
0x18001688a  lea     rbp, [rdx+1]
0x18001688e  mov     rdi, rcx
0x180016891  cmp     rbp, rdx
0x180016894  jnb     short loc_1800168A0
0x180016896  mov     ebx, 80070216h
0x18001689b  jmp     loc_180016992
0x1800168a0  mov     r9, [rcx+10h]
0x1800168a4  xor     r14d, r14d
0x1800168a7  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800168ab  cmp     r9, rcx
0x1800168ae  jnz     short loc_1800168EA
0x1800168b0  cmp     [rdi+8], rcx
0x1800168b4  jnz     short loc_1800168D3
0x1800168b6  mov     rax, [rdi]
0x1800168b9  test    rax, rax
0x1800168bc  jz      short loc_1800168CA
0x1800168be  inc     rcx
0x1800168c1  cmp     [rax+rcx*2], r14w
0x1800168c6  jnz     short loc_1800168BE
0x1800168c8  jmp     short loc_1800168CD
0x1800168ca  mov     rcx, r14
0x1800168cd  mov     [rdi+8], rcx
0x1800168d1  jmp     short loc_1800168D7
0x1800168d3  mov     rcx, [rdi+8]
0x1800168d7  mov     rax, [rdi]
0x1800168da  inc     rcx
0x1800168dd  neg     rax
0x1800168e0  sbb     r9, r9
0x1800168e3  and     r9, rcx
0x1800168e6  mov     [rdi+10h], r9
0x1800168ea  test    r9, r9
0x1800168ed  jnz     short loc_18001692C
0x1800168ef  lea     r8, [rsp+38h+cb]; unsigned __int64 *
0x1800168f4  mov     [rsp+38h+cb], r14
0x1800168f9  lea     edx, [r9+2]; unsigned __int64
0x1800168fd  mov     rcx, rbp; unsigned __int64
0x180016900  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180016905  mov     ebx, eax
0x180016907  test    eax, eax
0x180016909  js      loc_180016992
0x18001690f  mov     rcx, [rsp+38h+cb]; cb
0x180016914  call    cs:__imp_CoTaskMemAlloc
0x18001691a  test    rax, rax
0x18001691d  jz      short loc_18001698D
0x18001691f  mov     [rdi+10h], rbp
0x180016923  mov     [rdi], rax
0x180016926  mov     [rax], r14w
0x18001692a  jmp     short loc_180016992
0x18001692c  mov     ebx, r14d
0x18001692f  cmp     rbp, r9
0x180016932  jbe     short loc_180016992
0x180016934  lea     r8, [rsp+38h+cb]; unsigned __int64 *
0x180016939  mov     [rsp+38h+cb], r14
0x18001693e  mov     edx, 2; unsigned __int64
0x180016943  mov     rcx, r9; unsigned __int64
0x180016946  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18001694b  mov     ebx, eax
0x18001694d  test    eax, eax
0x18001694f  js      short loc_180016992
0x180016951  mov     rsi, [rsp+38h+cb]
0x180016956  mov     rax, rsi
0x180016959  sub     rax, r9
0x18001695c  cmp     rax, 800h
0x180016962  jbe     short loc_18001696B
0x180016964  lea     rsi, [r9+800h]
0x18001696b  mov     rcx, [rdi]; pv
0x18001696e  cmp     rbp, rsi
0x180016971  cmova   rsi, rbp
0x180016975  lea     rdx, [rsi+rsi]; cb
0x180016979  call    cs:__imp_CoTaskMemRealloc
0x18001697f  test    rax, rax
0x180016982  jz      short loc_18001698D
0x180016984  mov     [rdi+10h], rsi
0x180016988  mov     [rdi], rax
0x18001698b  jmp     short loc_180016992
0x18001698d  mov     ebx, 8007000Eh
0x180016992  mov     rbp, [rsp+38h+arg_10]
0x180016997  mov     eax, ebx
0x180016999  mov     rbx, [rsp+38h+arg_0]
0x18001699e  add     rsp, 20h
0x1800169a2  pop     r14
0x1800169a4  pop     rdi
0x1800169a5  pop     rsi
0x1800169a6  retn
```
