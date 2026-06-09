# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCapacity(unsigned __int64)

- ea: `0x180011a90`
- end: `0x180011baa`
- name: `?_EnsureCapacity@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJ_K@Z`
- size: `282`
- prototype: `__int64 __fastcall(__int64, unsigned __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800118bc`
- `0x180011994`
- `0x18001d918`

## callees

- `0x180011a90`
- `0x180011bb0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180011b4f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180011b4f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180011ad0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180011ad0`

## pseudocode

```c
__int64 __fastcall Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCapacity(
        __int64 a1,
        unsigned __int64 a2)
{
  unsigned __int64 v2; // rdi
  unsigned __int64 v4; // r8
  _WORD *v5; // rdx
  __int64 result; // rax
  unsigned __int64 v7; // rdx
  LPVOID v8; // rcx
  _QWORD *v9; // rcx

  v2 = a2 + 1;
  if ( a2 + 1 < a2 )
    return 2147942934LL;
  v4 = *(_QWORD *)(a1 + 16);
  if ( v4 == -1 )
  {
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCount();
    if ( *v9 )
      v4 = v9[1] + 1LL;
    else
      v4 = 0;
    v9[2] = v4;
  }
  if ( !v4 )
  {
    if ( is_mul_ok(v2, 2u) )
    {
      v5 = CoTaskMemAlloc(2 * v2);
      if ( v5 )
      {
        *(_QWORD *)(a1 + 16) = v2;
        result = 0;
        *(_QWORD *)a1 = v5;
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
      if ( v4 <= 0x800 )
        v7 = 2 * v4;
      if ( v2 <= v7 )
        v2 = v7;
      v8 = CoTaskMemRealloc(*(LPVOID *)a1, 2 * v2);
      if ( v8 )
      {
        result = 0;
        *(_QWORD *)(a1 + 16) = v2;
        *(_QWORD *)a1 = v8;
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
0x180011a90  mov     [rsp+arg_10], rbx
0x180011a95  push    rdi
0x180011a96  sub     rsp, 20h
0x180011a9a  lea     rdi, [rdx+1]
0x180011a9e  mov     rbx, rcx
0x180011aa1  cmp     rdi, rdx
0x180011aa4  jb      short loc_180011AFE
0x180011aa6  mov     r8, [rcx+10h]
0x180011aaa  mov     [rsp+28h+arg_0], rsi
0x180011aaf  xor     esi, esi
0x180011ab1  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x180011ab5  jz      loc_180011B76
0x180011abb  test    r8, r8
0x180011abe  jnz     short loc_180011B15
0x180011ac0  mov     eax, 2
0x180011ac5  mul     rdi
0x180011ac8  test    rdx, rdx
0x180011acb  jnz     short loc_180011B0E
0x180011acd  mov     rcx, rax; cb
0x180011ad0  call    cs:__imp_CoTaskMemAlloc
0x180011ad6  mov     rdx, rax
0x180011ad9  test    rax, rax
0x180011adc  jz      loc_180011B90
0x180011ae2  mov     [rbx+10h], rdi
0x180011ae6  mov     eax, esi
0x180011ae8  mov     [rbx], rdx
0x180011aeb  mov     [rdx], si
0x180011aee  mov     rsi, [rsp+28h+arg_0]
0x180011af3  mov     rbx, [rsp+28h+arg_10]
0x180011af8  add     rsp, 20h
0x180011afc  pop     rdi
0x180011afd  retn
0x180011afe  mov     eax, 80070216h
0x180011b03  mov     rbx, [rsp+28h+arg_10]
0x180011b08  add     rsp, 20h
0x180011b0c  pop     rdi
0x180011b0d  retn
0x180011b0e  mov     eax, 80070216h
0x180011b13  jmp     short loc_180011AEE
0x180011b15  mov     eax, esi
0x180011b17  cmp     rdi, r8
0x180011b1a  jbe     short loc_180011AEE
0x180011b1c  mov     eax, 2
0x180011b21  mul     r8
0x180011b24  test    rdx, rdx
0x180011b27  jnz     short loc_180011B0E
0x180011b29  mov     rcx, rax
0x180011b2c  lea     rdx, [r8+800h]
0x180011b33  sub     rcx, r8
0x180011b36  cmp     rcx, 800h
0x180011b3d  mov     rcx, [rbx]; pv
0x180011b40  cmovbe  rdx, rax
0x180011b44  cmp     rdi, rdx
0x180011b47  cmovbe  rdi, rdx
0x180011b4b  lea     rdx, [rdi+rdi]; cb
0x180011b4f  call    cs:__imp_CoTaskMemRealloc
0x180011b55  mov     rcx, rax
0x180011b58  test    rax, rax
0x180011b5b  jz      short loc_180011B90
0x180011b5d  mov     eax, esi
0x180011b5f  mov     [rbx+10h], rdi
0x180011b63  mov     rsi, [rsp+28h+arg_0]
0x180011b68  mov     [rbx], rcx
0x180011b6b  mov     rbx, [rsp+28h+arg_10]
0x180011b70  add     rsp, 20h
0x180011b74  pop     rdi
0x180011b75  retn
0x180011b76  call    ?_EnsureCount@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCount(void)
0x180011b7b  cmp     [rcx], rsi
0x180011b7e  jz      short loc_180011BA5
0x180011b80  mov     r8, [rcx+8]
0x180011b84  inc     r8
0x180011b87  mov     [rcx+10h], r8
0x180011b8b  jmp     loc_180011ABB
0x180011b90  mov     rsi, [rsp+28h+arg_0]
0x180011b95  mov     eax, 8007000Eh
0x180011b9a  mov     rbx, [rsp+28h+arg_10]
0x180011b9f  add     rsp, 20h
0x180011ba3  pop     rdi
0x180011ba4  retn
0x180011ba5  mov     r8, rsi
0x180011ba8  jmp     short loc_180011B87
```
