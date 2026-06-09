# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCapacity(unsigned __int64)

- ea: `0x180033868`
- end: `0x180033952`
- name: `?_EnsureCapacity@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJ_K@Z`
- size: `234`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800337e4`
- `0x180049100`

## callees

- `0x18001ffd0`
- `0x180033868`
- `0x1800490d0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800338c5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800338c5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18003392e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18003392e`

## pseudocode

```c
__int64 __fastcall Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCapacity(
        __int64 a1,
        unsigned __int64 a2,
        __int64 a3)
{
  unsigned __int64 v3; // rbp
  unsigned int v5; // ebx
  unsigned __int64 v6; // r9
  _QWORD *v7; // rcx
  _WORD *v8; // rax
  __int64 v9; // r9
  unsigned __int64 v10; // rsi
  LPVOID v11; // rax
  unsigned __int64 v13; // [rsp+58h] [rbp+10h] BYREF

  v3 = a2 + 1;
  if ( a2 + 1 < a2 )
    return (unsigned int)-2147024362;
  v6 = *(_QWORD *)(a1 + 16);
  if ( v6 == -1 )
  {
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCount(a1, a2, a3, -1);
    if ( *v7 )
      v6 = v7[1] + 1LL;
    else
      v6 = 0;
    v7[2] = v6;
  }
  if ( !v6 )
  {
    v13 = 0;
    if ( !is_mul_ok(v3, 2u) )
      return (unsigned int)-2147024362;
    v8 = CoTaskMemAlloc(2 * v3);
    if ( v8 )
    {
      *(_QWORD *)a1 = v8;
      v5 = 0;
      *(_QWORD *)(a1 + 16) = v3;
      *v8 = 0;
      return v5;
    }
    return (unsigned int)-2147024882;
  }
  v5 = 0;
  if ( v3 > v6 )
  {
    v13 = 0;
    v5 = ULongLongMult(v6, 2u, &v13);
    if ( (v5 & 0x80000000) == 0 )
    {
      v10 = v13;
      if ( v13 - v9 > 0x800 )
        v10 = v9 + 2048;
      if ( v3 > v10 )
        v10 = v3;
      v11 = CoTaskMemRealloc(*(LPVOID *)a1, 2 * v10);
      if ( v11 )
      {
        *(_QWORD *)(a1 + 16) = v10;
        *(_QWORD *)a1 = v11;
        return v5;
      }
      return (unsigned int)-2147024882;
    }
  }
  return v5;
}

```

## disassembly

```asm
0x180033868  push    rbx
0x18003386a  push    rbp
0x18003386b  push    rsi
0x18003386c  push    rdi
0x18003386d  sub     rsp, 28h
0x180033871  lea     rbp, [rdx+1]
0x180033875  mov     rdi, rcx
0x180033878  cmp     rbp, rdx
0x18003387b  jnb     short loc_180033887
0x18003387d  mov     ebx, 80070216h
0x180033882  jmp     loc_180033947
0x180033887  mov     r9, [rcx+10h]
0x18003388b  cmp     r9, 0FFFFFFFFFFFFFFFFh
0x18003388f  jnz     short loc_1800338AC
0x180033891  call    ?_EnsureCount@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCount(void)
0x180033896  cmp     qword ptr [rcx], 0
0x18003389a  jz      short loc_1800338A5
0x18003389c  mov     r9, [rcx+8]
0x1800338a0  inc     r9
0x1800338a3  jmp     short loc_1800338A8
0x1800338a5  xor     r9d, r9d
0x1800338a8  mov     [rcx+10h], r9
0x1800338ac  test    r9, r9
0x1800338af  jnz     short loc_1800338E3
0x1800338b1  lea     eax, [r9+2]
0x1800338b5  mov     [rsp+48h+arg_8], r9
0x1800338ba  mul     rbp
0x1800338bd  test    rdx, rdx
0x1800338c0  jnz     short loc_18003387D
0x1800338c2  mov     rcx, rax; cb
0x1800338c5  call    cs:__imp_CoTaskMemAlloc
0x1800338cb  mov     rcx, rax
0x1800338ce  test    rax, rax
0x1800338d1  jz      short loc_180033942
0x1800338d3  mov     [rdi], rax
0x1800338d6  xor     ebx, ebx
0x1800338d8  xor     eax, eax
0x1800338da  mov     [rdi+10h], rbp
0x1800338de  mov     [rcx], ax
0x1800338e1  jmp     short loc_180033947
0x1800338e3  xor     ebx, ebx
0x1800338e5  cmp     rbp, r9
0x1800338e8  jbe     short loc_180033947
0x1800338ea  lea     r8, [rsp+48h+arg_8]; unsigned __int64 *
0x1800338ef  mov     [rsp+48h+arg_8], rbx
0x1800338f4  lea     edx, [rbx+2]; unsigned __int64
0x1800338f7  mov     rcx, r9; unsigned __int64
0x1800338fa  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x1800338ff  mov     ebx, eax
0x180033901  test    eax, eax
0x180033903  js      short loc_180033947
0x180033905  mov     rsi, [rsp+48h+arg_8]
0x18003390a  mov     rcx, rsi
0x18003390d  sub     rcx, r9
0x180033910  cmp     rcx, 800h
0x180033917  jbe     short loc_180033920
0x180033919  lea     rsi, [r9+800h]
0x180033920  mov     rcx, [rdi]; pv
0x180033923  cmp     rbp, rsi
0x180033926  cmova   rsi, rbp
0x18003392a  lea     rdx, [rsi+rsi]; cb
0x18003392e  call    cs:__imp_CoTaskMemRealloc
0x180033934  test    rax, rax
0x180033937  jz      short loc_180033942
0x180033939  mov     [rdi+10h], rsi
0x18003393d  mov     [rdi], rax
0x180033940  jmp     short loc_180033947
0x180033942  mov     ebx, 8007000Eh
0x180033947  mov     eax, ebx
0x180033949  add     rsp, 28h
0x18003394d  pop     rdi
0x18003394e  pop     rsi
0x18003394f  pop     rbp
0x180033950  pop     rbx
0x180033951  retn
```
