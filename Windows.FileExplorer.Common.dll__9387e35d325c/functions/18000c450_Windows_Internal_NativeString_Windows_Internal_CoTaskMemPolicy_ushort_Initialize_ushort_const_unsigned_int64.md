# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)

- ea: `0x18000c450`
- end: `0x18000c660`
- name: `?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z`
- size: `528`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `10`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000c188`
- `0x18000d188`
- `0x180016fe8`
- `0x1800180d0`
- `0x18001882c`
- `0x180023ea0`
- `0x180041860`
- `0x180041960`
- `0x1800430a0`
- `0x180046a18`

## callees

- `0x18000c450`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000c4d5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000c4d5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c59a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c59a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18000c5ed`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18000c5ed`

## pseudocode

```c
__int64 __fastcall Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
        __int64 a1,
        _WORD *a2,
        unsigned __int64 a3)
{
  _WORD *v3; // rbx
  __int64 v5; // rax
  unsigned __int64 v6; // rbp
  unsigned __int64 v7; // rdi
  unsigned __int64 v8; // rcx
  _WORD *v9; // rax
  int v10; // r8d
  _WORD *v11; // rdx
  unsigned __int64 v12; // rcx
  _WORD *v13; // rax
  __int64 result; // rax
  void *v15; // rcx
  unsigned __int64 v16; // rsi
  LPVOID v17; // rax

  v3 = a2;
  if ( a2 )
  {
    v5 = -1;
    v6 = -1;
    do
      ++v6;
    while ( a2[v6] );
    if ( a3 == -1 )
    {
      a3 = v6;
    }
    else if ( a3 < v6 )
    {
      v6 = a3;
    }
    v7 = a3 + 1;
    if ( a3 + 1 < a3 )
      return 2147942934LL;
    v8 = *(_QWORD *)(a1 + 16);
    if ( v8 == -1 )
    {
      if ( *(_QWORD *)(a1 + 8) == -1 )
      {
        if ( *(_QWORD *)a1 )
        {
          do
            ++v5;
          while ( *(_WORD *)(*(_QWORD *)a1 + 2 * v5) );
        }
        else
        {
          v5 = 0;
        }
        *(_QWORD *)(a1 + 8) = v5;
      }
      else
      {
        v5 = *(_QWORD *)(a1 + 8);
      }
      v8 = v5 + 1;
      if ( !*(_QWORD *)a1 )
        v8 = 0;
      *(_QWORD *)(a1 + 16) = v8;
    }
    if ( v8 )
    {
      v10 = 0;
      if ( v7 <= v8 )
        goto LABEL_13;
      v16 = 2 * v8;
      if ( is_mul_ok(v8, 2u) )
      {
        if ( v8 > 0x800 )
          v16 = v8 + 2048;
        if ( v7 > v16 )
          v16 = v7;
        v17 = CoTaskMemRealloc(*(LPVOID *)a1, 2 * v16);
        if ( !v17 )
          return 2147942414LL;
        *(_QWORD *)(a1 + 16) = v16;
        v10 = 0;
        *(_QWORD *)a1 = v17;
        goto LABEL_14;
      }
    }
    else if ( is_mul_ok(v7, 2u) )
    {
      v9 = CoTaskMemAlloc(2 * v7);
      if ( v9 )
      {
        *(_QWORD *)(a1 + 16) = v7;
        v10 = 0;
        *(_QWORD *)a1 = v9;
        *v9 = 0;
        goto LABEL_14;
      }
      v10 = -2147024882;
LABEL_13:
      if ( v10 < 0 )
        return (unsigned int)v10;
LABEL_14:
      if ( v7 )
      {
        v11 = *(_WORD **)a1;
        if ( v7 > 0x7FFFFFFF || v6 > 0x7FFFFFFE )
        {
          *v11 = 0;
        }
        else
        {
          v12 = v6;
          do
          {
            if ( !v12 )
              break;
            if ( !*v3 )
              break;
            *v11++ = *v3++;
            --v12;
            --v7;
          }
          while ( v7 );
          v13 = v11 - 1;
          if ( v7 )
            v13 = v11;
          *v13 = 0;
        }
      }
      *(_QWORD *)(a1 + 8) = v6;
      return (unsigned int)v10;
    }
    return 2147942934LL;
  }
  v15 = *(void **)a1;
  if ( v15 )
  {
    CoTaskMemFree(v15);
    *(_QWORD *)a1 = 0;
  }
  *(_QWORD *)(a1 + 8) = 0;
  result = 0;
  *(_QWORD *)(a1 + 16) = 0;
  return result;
}

```

## disassembly

```asm
0x18000c450  push    rbx
0x18000c452  push    r14
0x18000c454  push    r15
0x18000c456  sub     rsp, 20h
0x18000c45a  mov     rbx, rdx
0x18000c45d  mov     r14, rcx
0x18000c460  test    rdx, rdx
0x18000c463  jz      loc_18000C58F
0x18000c469  mov     [rsp+38h+arg_0], rbp
0x18000c46e  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000c475  mov     rbp, rax
0x18000c478  mov     [rsp+38h+arg_18], rdi
0x18000c47d  nop     dword ptr [rax]
0x18000c480  inc     rbp
0x18000c483  cmp     word ptr [rdx+rbp*2], 0
0x18000c488  jnz     short loc_18000C480
0x18000c48a  cmp     r8, rax
0x18000c48d  jnz     loc_18000C57E
0x18000c493  mov     r8, rbp
0x18000c496  lea     rdi, [r8+1]
0x18000c49a  cmp     rdi, r8
0x18000c49d  jb      loc_18000C570
0x18000c4a3  mov     rcx, [rcx+10h]
0x18000c4a7  xor     r15d, r15d
0x18000c4aa  cmp     rcx, rax
0x18000c4ad  jz      loc_18000C61A
0x18000c4b3  mov     [rsp+38h+arg_10], rsi
0x18000c4b8  test    rcx, rcx
0x18000c4bb  jnz     loc_18000C5B8
0x18000c4c1  mov     eax, 2
0x18000c4c6  mul     rdi
0x18000c4c9  test    rdx, rdx
0x18000c4cc  jnz     loc_18000C577
0x18000c4d2  mov     rcx, rax; cb
0x18000c4d5  call    cs:__imp_CoTaskMemAlloc
0x18000c4db  test    rax, rax
0x18000c4de  jz      short loc_18000C4F0
0x18000c4e0  mov     [r14+10h], rdi
0x18000c4e4  mov     r8d, r15d
0x18000c4e7  mov     [r14], rax
0x18000c4ea  mov     [rax], r15w
0x18000c4ee  jmp     short loc_18000C4FB
0x18000c4f0  mov     r8d, 8007000Eh
0x18000c4f6  test    r8d, r8d
0x18000c4f9  js      short loc_18000C554
0x18000c4fb  test    rdi, rdi
0x18000c4fe  jz      short loc_18000C550
0x18000c500  mov     rdx, [r14]
0x18000c503  cmp     rdi, 7FFFFFFFh
0x18000c50a  ja      loc_18000C657
0x18000c510  cmp     rbp, 7FFFFFFEh
0x18000c517  ja      loc_18000C657
0x18000c51d  mov     rcx, rbp
0x18000c520  test    rcx, rcx
0x18000c523  jz      short loc_18000C541
0x18000c525  movzx   eax, word ptr [rbx]
0x18000c528  test    ax, ax
0x18000c52b  jz      short loc_18000C541
0x18000c52d  mov     [rdx], ax
0x18000c530  add     rbx, 2
0x18000c534  add     rdx, 2
0x18000c538  dec     rcx
0x18000c53b  sub     rdi, 1
0x18000c53f  jnz     short loc_18000C520
0x18000c541  test    rdi, rdi
0x18000c544  lea     rax, [rdx-2]
0x18000c548  cmovnz  rax, rdx
0x18000c54c  mov     [rax], r15w
0x18000c550  mov     [r14+8], rbp
0x18000c554  mov     eax, r8d
0x18000c557  mov     rsi, [rsp+38h+arg_10]
0x18000c55c  mov     rbp, [rsp+38h+arg_0]
0x18000c561  mov     rdi, [rsp+38h+arg_18]
0x18000c566  add     rsp, 20h
0x18000c56a  pop     r15
0x18000c56c  pop     r14
0x18000c56e  pop     rbx
0x18000c56f  retn
0x18000c570  mov     eax, 80070216h
0x18000c575  jmp     short loc_18000C55C
0x18000c577  mov     eax, 80070216h
0x18000c57c  jmp     short loc_18000C557
0x18000c57e  cmp     r8, rbp
0x18000c581  jnb     loc_18000C496
0x18000c587  mov     rbp, r8
0x18000c58a  jmp     loc_18000C496
0x18000c58f  mov     rcx, [rcx]; pv
0x18000c592  xor     r15d, r15d
0x18000c595  test    rcx, rcx
0x18000c598  jz      short loc_18000C5A3
0x18000c59a  call    cs:__imp_CoTaskMemFree
0x18000c5a0  mov     [r14], r15
0x18000c5a3  mov     [r14+8], r15
0x18000c5a7  mov     eax, r15d
0x18000c5aa  mov     [r14+10h], r15
0x18000c5ae  add     rsp, 20h
0x18000c5b2  pop     r15
0x18000c5b4  pop     r14
0x18000c5b6  pop     rbx
0x18000c5b7  retn
0x18000c5b8  mov     r8d, r15d
0x18000c5bb  cmp     rdi, rcx
0x18000c5be  jbe     loc_18000C4F6
0x18000c5c4  mov     eax, 2
0x18000c5c9  mul     rcx
0x18000c5cc  mov     rsi, rax
0x18000c5cf  test    rdx, rdx
0x18000c5d2  jnz     short loc_18000C577
0x18000c5d4  sub     rax, rcx
0x18000c5d7  cmp     rax, 800h
0x18000c5dd  ja      short loc_18000C602
0x18000c5df  mov     rcx, [r14]; pv
0x18000c5e2  cmp     rdi, rsi
0x18000c5e5  cmova   rsi, rdi
0x18000c5e9  lea     rdx, [rsi+rsi]; cb
0x18000c5ed  call    cs:__imp_CoTaskMemRealloc
0x18000c5f3  test    rax, rax
0x18000c5f6  jnz     short loc_18000C60B
0x18000c5f8  mov     eax, 8007000Eh
0x18000c5fd  jmp     loc_18000C557
0x18000c602  lea     rsi, [rcx+800h]
0x18000c609  jmp     short loc_18000C5DF
0x18000c60b  mov     [r14+10h], rsi
0x18000c60f  mov     r8d, r15d
0x18000c612  mov     [r14], rax
0x18000c615  jmp     loc_18000C4FB
0x18000c61a  mov     rcx, [r14+8]
0x18000c61e  cmp     rcx, rax
0x18000c621  jnz     short loc_18000C640
0x18000c623  mov     rcx, [r14]
0x18000c626  test    rcx, rcx
0x18000c629  jnz     short loc_18000C630
0x18000c62b  mov     rax, r15
0x18000c62e  jmp     short loc_18000C63A
0x18000c630  inc     rax
0x18000c633  cmp     [rcx+rax*2], r15w
0x18000c638  jnz     short loc_18000C630
0x18000c63a  mov     [r14+8], rax
0x18000c63e  jmp     short loc_18000C643
0x18000c640  mov     rax, rcx
0x18000c643  cmp     [r14], r15
0x18000c646  lea     rcx, [rax+1]
0x18000c64a  cmovz   rcx, r15
0x18000c64e  mov     [r14+10h], rcx
0x18000c652  jmp     loc_18000C4B3
0x18000c657  mov     [rdx], r15w
0x18000c65b  jmp     loc_18000C550
```
