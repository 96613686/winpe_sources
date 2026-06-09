# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCapacity(unsigned __int64)

- ea: `0x180039fcc`
- end: `0x18003a0ee`
- name: `?_EnsureCapacity@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJ_K@Z`
- size: `290`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18003a130`

## callees

- `0x180038914`
- `0x180039fcc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18003a0c0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18003a0c0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003a060`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003a060`

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
0x180039fcc  mov     [rsp+arg_0], rbx
0x180039fd1  mov     [rsp+arg_10], rbp
0x180039fd6  push    rsi
0x180039fd7  push    rdi
0x180039fd8  push    r14
0x180039fda  sub     rsp, 20h
0x180039fde  lea     rbp, [rdx+1]
0x180039fe2  mov     rdi, rcx
0x180039fe5  cmp     rbp, rdx
0x180039fe8  jnb     short loc_180039FF4
0x180039fea  mov     ebx, 80070216h
0x180039fef  jmp     loc_18003A0D9
0x180039ff4  mov     r9, [rcx+10h]
0x180039ff8  xor     r14d, r14d
0x180039ffb  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180039fff  cmp     r9, rcx
0x18003a002  jnz     short loc_18003A03E
0x18003a004  cmp     [rdi+8], rcx
0x18003a008  jnz     short loc_18003A027
0x18003a00a  mov     rax, [rdi]
0x18003a00d  test    rax, rax
0x18003a010  jz      short loc_18003A01E
0x18003a012  inc     rcx
0x18003a015  cmp     [rax+rcx*2], r14w
0x18003a01a  jnz     short loc_18003A012
0x18003a01c  jmp     short loc_18003A021
0x18003a01e  mov     rcx, r14
0x18003a021  mov     [rdi+8], rcx
0x18003a025  jmp     short loc_18003A02B
0x18003a027  mov     rcx, [rdi+8]
0x18003a02b  mov     rax, [rdi]
0x18003a02e  inc     rcx
0x18003a031  neg     rax
0x18003a034  sbb     r9, r9
0x18003a037  and     r9, rcx
0x18003a03a  mov     [rdi+10h], r9
0x18003a03e  test    r9, r9
0x18003a041  jnz     short loc_18003A078
0x18003a043  lea     r8, [rsp+38h+cb]; unsigned __int64 *
0x18003a048  mov     [rsp+38h+cb], r14
0x18003a04d  mov     rcx, rbp; unsigned __int64
0x18003a050  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18003a055  mov     ebx, eax
0x18003a057  test    eax, eax
0x18003a059  js      short loc_18003A0D9
0x18003a05b  mov     rcx, [rsp+38h+cb]; cb
0x18003a060  call    cs:__imp_CoTaskMemAlloc
0x18003a066  test    rax, rax
0x18003a069  jz      short loc_18003A0D4
0x18003a06b  mov     [rdi+10h], rbp
0x18003a06f  mov     [rdi], rax
0x18003a072  mov     [rax], r14w
0x18003a076  jmp     short loc_18003A0D9
0x18003a078  mov     ebx, r14d
0x18003a07b  cmp     rbp, r9
0x18003a07e  jbe     short loc_18003A0D9
0x18003a080  lea     r8, [rsp+38h+cb]; unsigned __int64 *
0x18003a085  mov     [rsp+38h+cb], r14
0x18003a08a  mov     rcx, r9; unsigned __int64
0x18003a08d  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18003a092  mov     ebx, eax
0x18003a094  test    eax, eax
0x18003a096  js      short loc_18003A0D9
0x18003a098  mov     rsi, [rsp+38h+cb]
0x18003a09d  mov     rax, rsi
0x18003a0a0  sub     rax, r9
0x18003a0a3  cmp     rax, 800h
0x18003a0a9  jbe     short loc_18003A0B2
0x18003a0ab  lea     rsi, [r9+800h]
0x18003a0b2  mov     rcx, [rdi]; pv
0x18003a0b5  cmp     rbp, rsi
0x18003a0b8  cmova   rsi, rbp
0x18003a0bc  lea     rdx, [rsi+rsi]; cb
0x18003a0c0  call    cs:__imp_CoTaskMemRealloc
0x18003a0c6  test    rax, rax
0x18003a0c9  jz      short loc_18003A0D4
0x18003a0cb  mov     [rdi+10h], rsi
0x18003a0cf  mov     [rdi], rax
0x18003a0d2  jmp     short loc_18003A0D9
0x18003a0d4  mov     ebx, 8007000Eh
0x18003a0d9  mov     rbp, [rsp+38h+arg_10]
0x18003a0de  mov     eax, ebx
0x18003a0e0  mov     rbx, [rsp+38h+arg_0]
0x18003a0e5  add     rsp, 20h
0x18003a0e9  pop     r14
0x18003a0eb  pop     rdi
0x18003a0ec  pop     rsi
0x18003a0ed  retn
```
