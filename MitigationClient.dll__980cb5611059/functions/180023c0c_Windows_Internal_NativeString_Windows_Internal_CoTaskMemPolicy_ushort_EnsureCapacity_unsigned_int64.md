# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCapacity(unsigned __int64)

- ea: `0x180023c0c`
- end: `0x180023d01`
- name: `?_EnsureCapacity@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJ_K@Z`
- size: `245`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180018e5c`
- `0x180023bac`
- `0x1800240b8`

## callees

- `0x180016c30`
- `0x180023c0c`
- `0x180023d08`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180023cdd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180023cdd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180023c7a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180023c7a`

## pseudocode

```c
__int64 __fastcall Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCapacity(
        __int64 a1,
        unsigned __int64 a2,
        __int64 a3)
{
  unsigned __int64 v3; // rbp
  int v5; // ebx
  unsigned __int64 v6; // r9
  _QWORD *v7; // rcx
  _WORD *v8; // rax
  __int64 v9; // r9
  SIZE_T v10; // rsi
  LPVOID v11; // rax
  SIZE_T cb; // [rsp+58h] [rbp+10h] BYREF

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
    cb = 0;
    v5 = ULongLongMult(v3, 2u, &cb);
    if ( v5 < 0 )
      return (unsigned int)v5;
    v8 = CoTaskMemAlloc(cb);
    if ( v8 )
    {
      *(_QWORD *)(a1 + 16) = v3;
      *(_QWORD *)a1 = v8;
      *v8 = 0;
      return (unsigned int)v5;
    }
    return (unsigned int)-2147024882;
  }
  v5 = 0;
  if ( v3 > v6 )
  {
    cb = 0;
    v5 = ULongLongMult(v6, 2u, &cb);
    if ( v5 >= 0 )
    {
      v10 = cb;
      if ( cb - v9 > 0x800 )
        v10 = v9 + 2048;
      if ( v3 > v10 )
        v10 = v3;
      v11 = CoTaskMemRealloc(*(LPVOID *)a1, 2 * v10);
      if ( v11 )
      {
        *(_QWORD *)(a1 + 16) = v10;
        *(_QWORD *)a1 = v11;
        return (unsigned int)v5;
      }
      return (unsigned int)-2147024882;
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180023c0c  push    rbx
0x180023c0e  push    rbp
0x180023c0f  push    rsi
0x180023c10  push    rdi
0x180023c11  sub     rsp, 28h
0x180023c15  lea     rbp, [rdx+1]
0x180023c19  mov     rdi, rcx
0x180023c1c  cmp     rbp, rdx
0x180023c1f  jnb     short loc_180023C2B
0x180023c21  mov     ebx, 80070216h
0x180023c26  jmp     loc_180023CF6
0x180023c2b  mov     r9, [rcx+10h]
0x180023c2f  cmp     r9, 0FFFFFFFFFFFFFFFFh
0x180023c33  jnz     short loc_180023C50
0x180023c35  call    ?_EnsureCount@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCount(void)
0x180023c3a  cmp     qword ptr [rcx], 0
0x180023c3e  jz      short loc_180023C49
0x180023c40  mov     r9, [rcx+8]
0x180023c44  inc     r9
0x180023c47  jmp     short loc_180023C4C
0x180023c49  xor     r9d, r9d
0x180023c4c  mov     [rcx+10h], r9
0x180023c50  test    r9, r9
0x180023c53  jnz     short loc_180023C93
0x180023c55  lea     r8, [rsp+48h+cb]; unsigned __int64 *
0x180023c5a  mov     [rsp+48h+cb], r9
0x180023c5f  lea     edx, [r9+2]; unsigned __int64
0x180023c63  mov     rcx, rbp; unsigned __int64
0x180023c66  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180023c6b  mov     ebx, eax
0x180023c6d  test    eax, eax
0x180023c6f  js      loc_180023CF6
0x180023c75  mov     rcx, [rsp+48h+cb]; cb
0x180023c7a  call    cs:__imp_CoTaskMemAlloc
0x180023c80  test    rax, rax
0x180023c83  jz      short loc_180023CF1
0x180023c85  xor     ecx, ecx
0x180023c87  mov     [rdi+10h], rbp
0x180023c8b  mov     [rdi], rax
0x180023c8e  mov     [rax], cx
0x180023c91  jmp     short loc_180023CF6
0x180023c93  xor     ebx, ebx
0x180023c95  cmp     rbp, r9
0x180023c98  jbe     short loc_180023CF6
0x180023c9a  lea     r8, [rsp+48h+cb]; unsigned __int64 *
0x180023c9f  mov     [rsp+48h+cb], rbx
0x180023ca4  lea     edx, [rbx+2]; unsigned __int64
0x180023ca7  mov     rcx, r9; unsigned __int64
0x180023caa  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180023caf  mov     ebx, eax
0x180023cb1  test    eax, eax
0x180023cb3  js      short loc_180023CF6
0x180023cb5  mov     rsi, [rsp+48h+cb]
0x180023cba  mov     rax, rsi
0x180023cbd  sub     rax, r9
0x180023cc0  cmp     rax, 800h
0x180023cc6  jbe     short loc_180023CCF
0x180023cc8  lea     rsi, [r9+800h]
0x180023ccf  mov     rcx, [rdi]; pv
0x180023cd2  cmp     rbp, rsi
0x180023cd5  cmova   rsi, rbp
0x180023cd9  lea     rdx, [rsi+rsi]; cb
0x180023cdd  call    cs:__imp_CoTaskMemRealloc
0x180023ce3  test    rax, rax
0x180023ce6  jz      short loc_180023CF1
0x180023ce8  mov     [rdi+10h], rsi
0x180023cec  mov     [rdi], rax
0x180023cef  jmp     short loc_180023CF6
0x180023cf1  mov     ebx, 8007000Eh
0x180023cf6  mov     eax, ebx
0x180023cf8  add     rsp, 28h
0x180023cfc  pop     rdi
0x180023cfd  pop     rsi
0x180023cfe  pop     rbp
0x180023cff  pop     rbx
0x180023d00  retn
```
