# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCapacity(unsigned __int64)

- ea: `0x1800379a0`
- end: `0x180037ac2`
- name: `?_EnsureCapacity@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJ_K@Z`
- size: `290`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180032854`
- `0x180037f98`

## callees

- `0x1800375e4`
- `0x1800379a0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180037a94`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180037a94`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180037a34`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180037a34`

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
0x1800379a0  mov     [rsp+arg_0], rbx
0x1800379a5  mov     [rsp+arg_10], rbp
0x1800379aa  push    rsi
0x1800379ab  push    rdi
0x1800379ac  push    r14
0x1800379ae  sub     rsp, 20h
0x1800379b2  lea     rbp, [rdx+1]
0x1800379b6  mov     rdi, rcx
0x1800379b9  cmp     rbp, rdx
0x1800379bc  jnb     short loc_1800379C8
0x1800379be  mov     ebx, 80070216h
0x1800379c3  jmp     loc_180037AAD
0x1800379c8  mov     r9, [rcx+10h]
0x1800379cc  xor     r14d, r14d
0x1800379cf  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800379d3  cmp     r9, rcx
0x1800379d6  jnz     short loc_180037A12
0x1800379d8  cmp     [rdi+8], rcx
0x1800379dc  jnz     short loc_1800379FB
0x1800379de  mov     rax, [rdi]
0x1800379e1  test    rax, rax
0x1800379e4  jz      short loc_1800379F2
0x1800379e6  inc     rcx
0x1800379e9  cmp     [rax+rcx*2], r14w
0x1800379ee  jnz     short loc_1800379E6
0x1800379f0  jmp     short loc_1800379F5
0x1800379f2  mov     rcx, r14
0x1800379f5  mov     [rdi+8], rcx
0x1800379f9  jmp     short loc_1800379FF
0x1800379fb  mov     rcx, [rdi+8]
0x1800379ff  mov     rax, [rdi]
0x180037a02  inc     rcx
0x180037a05  neg     rax
0x180037a08  sbb     r9, r9
0x180037a0b  and     r9, rcx
0x180037a0e  mov     [rdi+10h], r9
0x180037a12  test    r9, r9
0x180037a15  jnz     short loc_180037A4C
0x180037a17  lea     r8, [rsp+38h+cb]; unsigned __int64 *
0x180037a1c  mov     [rsp+38h+cb], r14
0x180037a21  mov     rcx, rbp; unsigned __int64
0x180037a24  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180037a29  mov     ebx, eax
0x180037a2b  test    eax, eax
0x180037a2d  js      short loc_180037AAD
0x180037a2f  mov     rcx, [rsp+38h+cb]; cb
0x180037a34  call    cs:__imp_CoTaskMemAlloc
0x180037a3a  test    rax, rax
0x180037a3d  jz      short loc_180037AA8
0x180037a3f  mov     [rdi+10h], rbp
0x180037a43  mov     [rdi], rax
0x180037a46  mov     [rax], r14w
0x180037a4a  jmp     short loc_180037AAD
0x180037a4c  mov     ebx, r14d
0x180037a4f  cmp     rbp, r9
0x180037a52  jbe     short loc_180037AAD
0x180037a54  lea     r8, [rsp+38h+cb]; unsigned __int64 *
0x180037a59  mov     [rsp+38h+cb], r14
0x180037a5e  mov     rcx, r9; unsigned __int64
0x180037a61  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180037a66  mov     ebx, eax
0x180037a68  test    eax, eax
0x180037a6a  js      short loc_180037AAD
0x180037a6c  mov     rsi, [rsp+38h+cb]
0x180037a71  mov     rax, rsi
0x180037a74  sub     rax, r9
0x180037a77  cmp     rax, 800h
0x180037a7d  jbe     short loc_180037A86
0x180037a7f  lea     rsi, [r9+800h]
0x180037a86  mov     rcx, [rdi]; pv
0x180037a89  cmp     rbp, rsi
0x180037a8c  cmova   rsi, rbp
0x180037a90  lea     rdx, [rsi+rsi]; cb
0x180037a94  call    cs:__imp_CoTaskMemRealloc
0x180037a9a  test    rax, rax
0x180037a9d  jz      short loc_180037AA8
0x180037a9f  mov     [rdi+10h], rsi
0x180037aa3  mov     [rdi], rax
0x180037aa6  jmp     short loc_180037AAD
0x180037aa8  mov     ebx, 8007000Eh
0x180037aad  mov     rbp, [rsp+38h+arg_10]
0x180037ab2  mov     eax, ebx
0x180037ab4  mov     rbx, [rsp+38h+arg_0]
0x180037ab9  add     rsp, 20h
0x180037abd  pop     r14
0x180037abf  pop     rdi
0x180037ac0  pop     rsi
0x180037ac1  retn
```
