# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCapacity(unsigned __int64)

- ea: `0x18000d294`
- end: `0x18000d393`
- name: `?_EnsureCapacity@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJ_K@Z`
- size: `255`
- prototype: `__int64 __fastcall(__int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000dc80`

## callees

- `0x18000d294`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18000d35f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18000d35f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000d30f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000d30f`

## pseudocode

```c
__int64 __fastcall Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCapacity(
        __int64 a1,
        unsigned __int64 a2)
{
  unsigned __int64 v2; // rdi
  unsigned __int64 v4; // r8
  __int64 v5; // rcx
  _WORD *v6; // rax
  unsigned int v7; // ecx
  unsigned __int64 v8; // rcx
  LPVOID v9; // rax

  v2 = a2 + 1;
  if ( a2 + 1 < a2 )
    return (unsigned int)-2147024362;
  v4 = *(_QWORD *)(a1 + 16);
  v5 = -1;
  if ( v4 == -1 )
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
    v4 = (v5 + 1) & -(__int64)(*(_QWORD *)a1 != 0);
    *(_QWORD *)(a1 + 16) = v4;
  }
  if ( !v4 )
  {
    if ( is_mul_ok(v2, 2u) )
    {
      v6 = CoTaskMemAlloc(2 * v2);
      if ( v6 )
      {
        *(_QWORD *)(a1 + 16) = v2;
        *(_QWORD *)a1 = v6;
        *v6 = 0;
        return 0;
      }
      return (unsigned int)-2147024882;
    }
    return (unsigned int)-2147024362;
  }
  v7 = 0;
  if ( v2 > v4 )
  {
    if ( is_mul_ok(v4, 2u) )
    {
      v8 = v4 + 2048;
      if ( v4 <= 0x800 )
        v8 = 2 * v4;
      if ( v2 <= v8 )
        v2 = v8;
      v9 = CoTaskMemRealloc(*(LPVOID *)a1, 2 * v2);
      if ( v9 )
      {
        *(_QWORD *)(a1 + 16) = v2;
        *(_QWORD *)a1 = v9;
        return 0;
      }
      return (unsigned int)-2147024882;
    }
    return (unsigned int)-2147024362;
  }
  return v7;
}

```

## disassembly

```asm
0x18000d294  mov     [rsp+arg_0], rbx
0x18000d299  mov     [rsp+arg_10], rsi
0x18000d29e  push    rdi
0x18000d29f  sub     rsp, 20h
0x18000d2a3  lea     rdi, [rdx+1]
0x18000d2a7  mov     rbx, rcx
0x18000d2aa  cmp     rdi, rdx
0x18000d2ad  jb      loc_18000D37C
0x18000d2b3  mov     r8, [rcx+10h]
0x18000d2b7  xor     esi, esi
0x18000d2b9  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000d2bd  cmp     r8, rcx
0x18000d2c0  jnz     short loc_18000D2FB
0x18000d2c2  cmp     [rbx+8], rcx
0x18000d2c6  jnz     short loc_18000D2E4
0x18000d2c8  mov     rax, [rbx]
0x18000d2cb  test    rax, rax
0x18000d2ce  jz      short loc_18000D2DB
0x18000d2d0  inc     rcx
0x18000d2d3  cmp     [rax+rcx*2], si
0x18000d2d7  jnz     short loc_18000D2D0
0x18000d2d9  jmp     short loc_18000D2DE
0x18000d2db  mov     rcx, rsi
0x18000d2de  mov     [rbx+8], rcx
0x18000d2e2  jmp     short loc_18000D2E8
0x18000d2e4  mov     rcx, [rbx+8]
0x18000d2e8  mov     rax, [rbx]
0x18000d2eb  inc     rcx
0x18000d2ee  neg     rax
0x18000d2f1  sbb     r8, r8
0x18000d2f4  and     r8, rcx
0x18000d2f7  mov     [rbx+10h], r8
0x18000d2fb  test    r8, r8
0x18000d2fe  jnz     short loc_18000D326
0x18000d300  lea     eax, [r8+2]
0x18000d304  mul     rdi
0x18000d307  test    rdx, rdx
0x18000d30a  jnz     short loc_18000D37C
0x18000d30c  mov     rcx, rax; cb
0x18000d30f  call    cs:__imp_CoTaskMemAlloc
0x18000d315  test    rax, rax
0x18000d318  jz      short loc_18000D375
0x18000d31a  mov     [rbx+10h], rdi
0x18000d31e  mov     [rbx], rax
0x18000d321  mov     [rax], si
0x18000d324  jmp     short loc_18000D371
0x18000d326  mov     ecx, esi
0x18000d328  cmp     rdi, r8
0x18000d32b  jbe     short loc_18000D381
0x18000d32d  mov     eax, 2
0x18000d332  mul     r8
0x18000d335  mov     r9, rax
0x18000d338  test    rdx, rdx
0x18000d33b  jnz     short loc_18000D37C
0x18000d33d  sub     rax, r8
0x18000d340  lea     rcx, [r8+800h]
0x18000d347  cmp     rax, 800h
0x18000d34d  cmovbe  rcx, r9
0x18000d351  cmp     rdi, rcx
0x18000d354  cmovbe  rdi, rcx
0x18000d358  mov     rcx, [rbx]; pv
0x18000d35b  lea     rdx, [rdi+rdi]; cb
0x18000d35f  call    cs:__imp_CoTaskMemRealloc
0x18000d365  test    rax, rax
0x18000d368  jz      short loc_18000D375
0x18000d36a  mov     [rbx+10h], rdi
0x18000d36e  mov     [rbx], rax
0x18000d371  mov     ecx, esi
0x18000d373  jmp     short loc_18000D381
0x18000d375  mov     ecx, 8007000Eh
0x18000d37a  jmp     short loc_18000D381
0x18000d37c  mov     ecx, 80070216h
0x18000d381  mov     rbx, [rsp+28h+arg_0]
0x18000d386  mov     eax, ecx
0x18000d388  mov     rsi, [rsp+28h+arg_10]
0x18000d38d  add     rsp, 20h
0x18000d391  pop     rdi
0x18000d392  retn
```
