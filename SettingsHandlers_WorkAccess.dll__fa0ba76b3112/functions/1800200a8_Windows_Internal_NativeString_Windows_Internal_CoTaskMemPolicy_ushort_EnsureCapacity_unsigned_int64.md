# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCapacity(unsigned __int64)

- ea: `0x1800200a8`
- end: `0x1800201aa`
- name: `?_EnsureCapacity@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJ_K@Z`
- size: `258`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180019d44`
- `0x1800208f8`
- `0x18003b018`

## callees

- `0x18001f81c`
- `0x1800200a8`
- `0x1800201b0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18002017f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18002017f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180020116`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180020116`

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
0x1800200a8  push    rbx
0x1800200aa  push    rbp
0x1800200ab  push    rsi
0x1800200ac  push    rdi
0x1800200ad  sub     rsp, 28h
0x1800200b1  lea     rbp, [rdx+1]
0x1800200b5  mov     rdi, rcx
0x1800200b8  cmp     rbp, rdx
0x1800200bb  jnb     short loc_1800200C7
0x1800200bd  mov     ebx, 80070216h
0x1800200c2  jmp     loc_18002019E
0x1800200c7  mov     r9, [rcx+10h]
0x1800200cb  cmp     r9, 0FFFFFFFFFFFFFFFFh
0x1800200cf  jnz     short loc_1800200EC
0x1800200d1  call    ?_EnsureCount@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCount(void)
0x1800200d6  cmp     qword ptr [rcx], 0
0x1800200da  jz      short loc_1800200E5
0x1800200dc  mov     r9, [rcx+8]
0x1800200e0  inc     r9
0x1800200e3  jmp     short loc_1800200E8
0x1800200e5  xor     r9d, r9d
0x1800200e8  mov     [rcx+10h], r9
0x1800200ec  test    r9, r9
0x1800200ef  jnz     short loc_180020135
0x1800200f1  lea     r8, [rsp+48h+cb]; unsigned __int64 *
0x1800200f6  mov     [rsp+48h+cb], r9
0x1800200fb  lea     edx, [r9+2]; unsigned __int64
0x1800200ff  mov     rcx, rbp; unsigned __int64
0x180020102  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180020107  mov     ebx, eax
0x180020109  test    eax, eax
0x18002010b  js      loc_18002019E
0x180020111  mov     rcx, [rsp+48h+cb]; cb
0x180020116  call    cs:__imp_CoTaskMemAlloc
0x18002011d  nop     dword ptr [rax+rax+00h]
0x180020122  test    rax, rax
0x180020125  jz      short loc_180020199
0x180020127  xor     ecx, ecx
0x180020129  mov     [rdi+10h], rbp
0x18002012d  mov     [rdi], rax
0x180020130  mov     [rax], cx
0x180020133  jmp     short loc_18002019E
0x180020135  xor     ebx, ebx
0x180020137  cmp     rbp, r9
0x18002013a  jbe     short loc_18002019E
0x18002013c  lea     r8, [rsp+48h+cb]; unsigned __int64 *
0x180020141  mov     [rsp+48h+cb], rbx
0x180020146  lea     edx, [rbx+2]; unsigned __int64
0x180020149  mov     rcx, r9; unsigned __int64
0x18002014c  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180020151  mov     ebx, eax
0x180020153  test    eax, eax
0x180020155  js      short loc_18002019E
0x180020157  mov     rsi, [rsp+48h+cb]
0x18002015c  mov     rax, rsi
0x18002015f  sub     rax, r9
0x180020162  cmp     rax, 800h
0x180020168  jbe     short loc_180020171
0x18002016a  lea     rsi, [r9+800h]
0x180020171  mov     rcx, [rdi]; pv
0x180020174  cmp     rbp, rsi
0x180020177  cmova   rsi, rbp
0x18002017b  lea     rdx, [rsi+rsi]; cb
0x18002017f  call    cs:__imp_CoTaskMemRealloc
0x180020186  nop     dword ptr [rax+rax+00h]
0x18002018b  test    rax, rax
0x18002018e  jz      short loc_180020199
0x180020190  mov     [rdi+10h], rsi
0x180020194  mov     [rdi], rax
0x180020197  jmp     short loc_18002019E
0x180020199  mov     ebx, 8007000Eh
0x18002019e  mov     eax, ebx
0x1800201a0  add     rsp, 28h
0x1800201a4  pop     rdi
0x1800201a5  pop     rsi
0x1800201a6  pop     rbp
0x1800201a7  pop     rbx
0x1800201a8  retn
```
