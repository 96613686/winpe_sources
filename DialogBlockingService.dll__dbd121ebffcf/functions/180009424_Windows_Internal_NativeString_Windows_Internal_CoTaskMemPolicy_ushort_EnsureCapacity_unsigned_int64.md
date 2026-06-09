# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCapacity(unsigned __int64)

- ea: `0x180009424`
- end: `0x180009523`
- name: `?_EnsureCapacity@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJ_K@Z`
- size: `255`
- prototype: `__int64 __fastcall(__int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180008ec8`

## callees

- `0x180009424`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x1800094ef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x1800094ef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000949f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000949f`

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
0x180009424  mov     [rsp+arg_0], rbx
0x180009429  mov     [rsp+arg_10], rsi
0x18000942e  push    rdi
0x18000942f  sub     rsp, 20h
0x180009433  lea     rdi, [rdx+1]
0x180009437  mov     rbx, rcx
0x18000943a  cmp     rdi, rdx
0x18000943d  jb      loc_18000950C
0x180009443  mov     r8, [rcx+10h]
0x180009447  xor     esi, esi
0x180009449  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000944d  cmp     r8, rcx
0x180009450  jnz     short loc_18000948B
0x180009452  cmp     [rbx+8], rcx
0x180009456  jnz     short loc_180009474
0x180009458  mov     rax, [rbx]
0x18000945b  test    rax, rax
0x18000945e  jz      short loc_18000946B
0x180009460  inc     rcx
0x180009463  cmp     [rax+rcx*2], si
0x180009467  jnz     short loc_180009460
0x180009469  jmp     short loc_18000946E
0x18000946b  mov     rcx, rsi
0x18000946e  mov     [rbx+8], rcx
0x180009472  jmp     short loc_180009478
0x180009474  mov     rcx, [rbx+8]
0x180009478  mov     rax, [rbx]
0x18000947b  inc     rcx
0x18000947e  neg     rax
0x180009481  sbb     r8, r8
0x180009484  and     r8, rcx
0x180009487  mov     [rbx+10h], r8
0x18000948b  test    r8, r8
0x18000948e  jnz     short loc_1800094B6
0x180009490  lea     eax, [r8+2]
0x180009494  mul     rdi
0x180009497  test    rdx, rdx
0x18000949a  jnz     short loc_18000950C
0x18000949c  mov     rcx, rax; cb
0x18000949f  call    cs:__imp_CoTaskMemAlloc
0x1800094a5  test    rax, rax
0x1800094a8  jz      short loc_180009505
0x1800094aa  mov     [rbx+10h], rdi
0x1800094ae  mov     [rbx], rax
0x1800094b1  mov     [rax], si
0x1800094b4  jmp     short loc_180009501
0x1800094b6  mov     ecx, esi
0x1800094b8  cmp     rdi, r8
0x1800094bb  jbe     short loc_180009511
0x1800094bd  mov     eax, 2
0x1800094c2  mul     r8
0x1800094c5  mov     r9, rax
0x1800094c8  test    rdx, rdx
0x1800094cb  jnz     short loc_18000950C
0x1800094cd  sub     rax, r8
0x1800094d0  lea     rcx, [r8+800h]
0x1800094d7  cmp     rax, 800h
0x1800094dd  cmovbe  rcx, r9
0x1800094e1  cmp     rdi, rcx
0x1800094e4  cmovbe  rdi, rcx
0x1800094e8  mov     rcx, [rbx]; pv
0x1800094eb  lea     rdx, [rdi+rdi]; cb
0x1800094ef  call    cs:__imp_CoTaskMemRealloc
0x1800094f5  test    rax, rax
0x1800094f8  jz      short loc_180009505
0x1800094fa  mov     [rbx+10h], rdi
0x1800094fe  mov     [rbx], rax
0x180009501  mov     ecx, esi
0x180009503  jmp     short loc_180009511
0x180009505  mov     ecx, 8007000Eh
0x18000950a  jmp     short loc_180009511
0x18000950c  mov     ecx, 80070216h
0x180009511  mov     rbx, [rsp+28h+arg_0]
0x180009516  mov     eax, ecx
0x180009518  mov     rsi, [rsp+28h+arg_10]
0x18000951d  add     rsp, 20h
0x180009521  pop     rdi
0x180009522  retn
```
