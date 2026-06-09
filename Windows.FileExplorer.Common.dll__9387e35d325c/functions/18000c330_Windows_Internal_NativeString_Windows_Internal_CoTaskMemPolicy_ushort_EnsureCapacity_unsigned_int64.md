# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCapacity(unsigned __int64)

- ea: `0x18000c330`
- end: `0x18000c449`
- name: `?_EnsureCapacity@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJ_K@Z`
- size: `281`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000c188`
- `0x180071260`

## callees

- `0x18000c330`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000c372`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000c372`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18000c3d3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18000c3d3`

## pseudocode

```c
__int64 __fastcall Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCapacity(
        void **a1,
        unsigned __int64 a2)
{
  unsigned __int64 v2; // rdi
  unsigned __int64 v4; // r8
  _WORD *v5; // rdx
  __int64 result; // rax
  unsigned __int64 v7; // rdx
  void *v8; // rcx
  LPVOID v9; // rcx
  char *v10; // r8

  v2 = a2 + 1;
  if ( a2 + 1 < a2 )
    return 2147942934LL;
  v4 = (unsigned __int64)a1[2];
  if ( v4 == -1 )
  {
    v10 = (char *)a1[1];
    if ( v10 == (char *)-1LL )
    {
      if ( *a1 )
      {
        do
          ++v10;
        while ( *((_WORD *)*a1 + (_QWORD)v10) );
      }
      else
      {
        v10 = 0;
      }
      a1[1] = v10;
    }
    v4 = (unsigned __int64)(v10 + 1);
    if ( !*a1 )
      v4 = 0;
    a1[2] = (void *)v4;
  }
  if ( !v4 )
  {
    if ( is_mul_ok(v2, 2u) )
    {
      v5 = CoTaskMemAlloc(2 * v2);
      if ( v5 )
      {
        result = 0;
        a1[2] = (void *)v2;
        *a1 = v5;
        *v5 = 0;
        return result;
      }
      return 2147942414LL;
    }
    return 2147942934LL;
  }
  result = 0;
  if ( v2 > v4 )
  {
    if ( is_mul_ok(v4, 2u) )
    {
      v7 = v4 + 2048;
      v8 = *a1;
      if ( v4 <= 0x800 )
        v7 = 2 * v4;
      if ( v2 <= v7 )
        v2 = v7;
      v9 = CoTaskMemRealloc(v8, 2 * v2);
      if ( v9 )
      {
        a1[2] = (void *)v2;
        result = 0;
        *a1 = v9;
        return result;
      }
      return 2147942414LL;
    }
    return 2147942934LL;
  }
  return result;
}

```

## disassembly

```asm
0x18000c330  mov     [rsp+arg_0], rbx
0x18000c335  push    rdi
0x18000c336  sub     rsp, 20h
0x18000c33a  lea     rdi, [rdx+1]
0x18000c33e  mov     rbx, rcx
0x18000c341  cmp     rdi, rdx
0x18000c344  jb      short loc_18000C399
0x18000c346  mov     r8, [rcx+10h]
0x18000c34a  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x18000c34e  jz      loc_18000C40E
0x18000c354  test    r8, r8
0x18000c357  jnz     loc_18000C3F1
0x18000c35d  mov     eax, 2
0x18000c362  mov     [rsp+28h+arg_8], r8
0x18000c367  mul     rdi
0x18000c36a  test    rdx, rdx
0x18000c36d  jnz     short loc_18000C399
0x18000c36f  mov     rcx, rax; cb
0x18000c372  call    cs:__imp_CoTaskMemAlloc
0x18000c378  mov     rdx, rax
0x18000c37b  test    rax, rax
0x18000c37e  jz      short loc_18000C3E1
0x18000c380  xor     eax, eax
0x18000c382  mov     [rbx+10h], rdi
0x18000c386  xor     ecx, ecx
0x18000c388  mov     [rbx], rdx
0x18000c38b  mov     [rdx], cx
0x18000c38e  mov     rbx, [rsp+28h+arg_0]
0x18000c393  add     rsp, 20h
0x18000c397  pop     rdi
0x18000c398  retn
0x18000c399  mov     eax, 80070216h
0x18000c39e  jmp     short loc_18000C38E
0x18000c3a0  mov     eax, 2
0x18000c3a5  mul     r8
0x18000c3a8  test    rdx, rdx
0x18000c3ab  jnz     short loc_18000C399
0x18000c3ad  mov     rcx, rax
0x18000c3b0  lea     rdx, [r8+800h]
0x18000c3b7  sub     rcx, r8
0x18000c3ba  cmp     rcx, 800h
0x18000c3c1  mov     rcx, [rbx]; pv
0x18000c3c4  cmovbe  rdx, rax
0x18000c3c8  cmp     rdi, rdx
0x18000c3cb  cmovbe  rdi, rdx
0x18000c3cf  lea     rdx, [rdi+rdi]; cb
0x18000c3d3  call    cs:__imp_CoTaskMemRealloc
0x18000c3d9  mov     rcx, rax
0x18000c3dc  test    rax, rax
0x18000c3df  jnz     short loc_18000C3FA
0x18000c3e1  mov     eax, 8007000Eh
0x18000c3e6  mov     rbx, [rsp+28h+arg_0]
0x18000c3eb  add     rsp, 20h
0x18000c3ef  pop     rdi
0x18000c3f0  retn
0x18000c3f1  xor     eax, eax
0x18000c3f3  cmp     rdi, r8
0x18000c3f6  jbe     short loc_18000C38E
0x18000c3f8  jmp     short loc_18000C3A0
0x18000c3fa  mov     [rbx+10h], rdi
0x18000c3fe  xor     eax, eax
0x18000c400  mov     [rbx], rcx
0x18000c403  mov     rbx, [rsp+28h+arg_0]
0x18000c408  add     rsp, 20h
0x18000c40c  pop     rdi
0x18000c40d  retn
0x18000c40e  mov     r8, [rcx+8]
0x18000c412  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x18000c416  jnz     short loc_18000C434
0x18000c418  mov     rax, [rcx]
0x18000c41b  test    rax, rax
0x18000c41e  jz      short loc_18000C42D
0x18000c420  inc     r8
0x18000c423  cmp     word ptr [rax+r8*2], 0
0x18000c429  jnz     short loc_18000C420
0x18000c42b  jmp     short loc_18000C430
0x18000c42d  xor     r8d, r8d
0x18000c430  mov     [rcx+8], r8
0x18000c434  inc     r8
0x18000c437  xor     eax, eax
0x18000c439  cmp     [rcx], rax
0x18000c43c  cmovz   r8, rax
0x18000c440  mov     [rcx+10h], r8
0x18000c444  jmp     loc_18000C354
```
