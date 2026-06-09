# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCapacity(unsigned __int64)

- ea: `0x18001974c`
- end: `0x18001986e`
- name: `?_EnsureCapacity@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJ_K@Z`
- size: `290`
- prototype: `__int64 __fastcall(__int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180014a7c`
- `0x18001a50c`

## callees

- `0x1800194d0`
- `0x18001974c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180019840`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180019840`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800197e0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800197e0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x18001974c  mov     [rsp+arg_0], rbx
0x180019751  mov     [rsp+arg_10], rbp
0x180019756  push    rsi
0x180019757  push    rdi
0x180019758  push    r14
0x18001975a  sub     rsp, 20h
0x18001975e  lea     rbp, [rdx+1]
0x180019762  mov     rdi, rcx
0x180019765  cmp     rbp, rdx
0x180019768  jnb     short loc_180019774
0x18001976a  mov     ebx, 80070216h
0x18001976f  jmp     loc_180019859
0x180019774  mov     r9, [rcx+10h]
0x180019778  xor     r14d, r14d
0x18001977b  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18001977f  cmp     r9, rcx
0x180019782  jnz     short loc_1800197BE
0x180019784  cmp     [rdi+8], rcx
0x180019788  jnz     short loc_1800197A7
0x18001978a  mov     rax, [rdi]
0x18001978d  test    rax, rax
0x180019790  jz      short loc_18001979E
0x180019792  inc     rcx
0x180019795  cmp     [rax+rcx*2], r14w
0x18001979a  jnz     short loc_180019792
0x18001979c  jmp     short loc_1800197A1
0x18001979e  mov     rcx, r14
0x1800197a1  mov     [rdi+8], rcx
0x1800197a5  jmp     short loc_1800197AB
0x1800197a7  mov     rcx, [rdi+8]
0x1800197ab  mov     rax, [rdi]
0x1800197ae  inc     rcx
0x1800197b1  neg     rax
0x1800197b4  sbb     r9, r9
0x1800197b7  and     r9, rcx
0x1800197ba  mov     [rdi+10h], r9
0x1800197be  test    r9, r9
0x1800197c1  jnz     short loc_1800197F8
0x1800197c3  lea     r8, [rsp+38h+cb]; unsigned __int64 *
0x1800197c8  mov     [rsp+38h+cb], r14
0x1800197cd  mov     rcx, rbp; unsigned __int64
0x1800197d0  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x1800197d5  mov     ebx, eax
0x1800197d7  test    eax, eax
0x1800197d9  js      short loc_180019859
0x1800197db  mov     rcx, [rsp+38h+cb]; cb
0x1800197e0  call    cs:__imp_CoTaskMemAlloc
0x1800197e6  test    rax, rax
0x1800197e9  jz      short loc_180019854
0x1800197eb  mov     [rdi+10h], rbp
0x1800197ef  mov     [rdi], rax
0x1800197f2  mov     [rax], r14w
0x1800197f6  jmp     short loc_180019859
0x1800197f8  mov     ebx, r14d
0x1800197fb  cmp     rbp, r9
0x1800197fe  jbe     short loc_180019859
0x180019800  lea     r8, [rsp+38h+cb]; unsigned __int64 *
0x180019805  mov     [rsp+38h+cb], r14
0x18001980a  mov     rcx, r9; unsigned __int64
0x18001980d  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180019812  mov     ebx, eax
0x180019814  test    eax, eax
0x180019816  js      short loc_180019859
0x180019818  mov     rsi, [rsp+38h+cb]
0x18001981d  mov     rax, rsi
0x180019820  sub     rax, r9
0x180019823  cmp     rax, 800h
0x180019829  jbe     short loc_180019832
0x18001982b  lea     rsi, [r9+800h]
0x180019832  mov     rcx, [rdi]; pv
0x180019835  cmp     rbp, rsi
0x180019838  cmova   rsi, rbp
0x18001983c  lea     rdx, [rsi+rsi]; cb
0x180019840  call    cs:__imp_CoTaskMemRealloc
0x180019846  test    rax, rax
0x180019849  jz      short loc_180019854
0x18001984b  mov     [rdi+10h], rsi
0x18001984f  mov     [rdi], rax
0x180019852  jmp     short loc_180019859
0x180019854  mov     ebx, 8007000Eh
0x180019859  mov     rbp, [rsp+38h+arg_10]
0x18001985e  mov     eax, ebx
0x180019860  mov     rbx, [rsp+38h+arg_0]
0x180019865  add     rsp, 20h
0x180019869  pop     r14
0x18001986b  pop     rdi
0x18001986c  pop     rsi
0x18001986d  retn
```
