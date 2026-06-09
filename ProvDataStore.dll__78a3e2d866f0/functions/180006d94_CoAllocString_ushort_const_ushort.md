# CoAllocString(ushort const *,ushort * *)

- ea: `0x180006d94`
- end: `0x180006e24`
- name: `?CoAllocString@@YAJPEBGPEAPEAG@Z`
- size: `144`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180007050`
- `0x18000bf1c`
- `0x18000e184`

## callees

- `0x180006d94`
- `0x180007910`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006dd9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006dd9`

## pseudocode

```c
__int64 __fastcall CoAllocString(const unsigned __int16 *a1, unsigned __int16 **a2)
{
  unsigned __int64 v2; // rdi
  unsigned __int64 v5; // rsi
  unsigned __int16 *v6; // rax
  unsigned int v7; // ebx
  unsigned __int16 **v9; // [rsp+20h] [rbp-38h]
  unsigned __int64 *v10; // [rsp+28h] [rbp-30h]
  unsigned int v11; // [rsp+30h] [rbp-28h]

  v2 = -1;
  do
    ++v2;
  while ( a1[v2] );
  v5 = v2 + 1;
  *a2 = 0;
  if ( v2 + 1 >= v2 && is_mul_ok(v5, 2u) )
  {
    v6 = (unsigned __int16 *)CoTaskMemAlloc(2 * v5);
    *a2 = v6;
    v7 = v6 == 0 ? 0x8007000E : 0;
    if ( v6 )
      StringCchCopyNExW(v6, v2 + 1, a1, v2, v9, v10, v11);
  }
  else
  {
    return (unsigned int)-2147024362;
  }
  return v7;
}

```

## disassembly

```asm
0x180006d94  mov     [rsp+arg_0], rbx
0x180006d99  mov     [rsp+arg_10], rbp
0x180006d9e  push    rsi
0x180006d9f  push    rdi
0x180006da0  push    r14
0x180006da2  sub     rsp, 40h
0x180006da6  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180006daa  mov     rbx, rdx
0x180006dad  xor     r14d, r14d
0x180006db0  mov     rbp, rcx
0x180006db3  inc     rdi
0x180006db6  cmp     [rcx+rdi*2], r14w
0x180006dbb  jnz     short loc_180006DB3
0x180006dbd  lea     rsi, [rdi+1]
0x180006dc1  mov     [rdx], r14
0x180006dc4  cmp     rsi, rdi
0x180006dc7  jb      short loc_180006E0A
0x180006dc9  mov     eax, 2
0x180006dce  mul     rsi
0x180006dd1  test    rdx, rdx
0x180006dd4  jnz     short loc_180006E0A
0x180006dd6  mov     rcx, rax; cb
0x180006dd9  call    cs:__imp_CoTaskMemAlloc
0x180006ddf  mov     [rbx], rax
0x180006de2  mov     rcx, rax
0x180006de5  neg     rcx
0x180006de8  sbb     ebx, ebx
0x180006dea  not     ebx
0x180006dec  and     ebx, 8007000Eh
0x180006df2  test    rax, rax
0x180006df5  jz      short loc_180006E0F
0x180006df7  mov     r9, rdi; unsigned __int64
0x180006dfa  mov     r8, rbp; unsigned __int16 *
0x180006dfd  mov     rdx, rsi; unsigned __int64
0x180006e00  mov     rcx, rax; unsigned __int16 *
0x180006e03  call    ?StringCchCopyNExW@@YAJPEAG_KPEBG1PEAPEAGPEA_KK@Z; StringCchCopyNExW(ushort *,unsigned __int64,ushort const *,unsigned __int64,ushort * *,unsigned __int64 *,ulong)
0x180006e08  jmp     short loc_180006E0F
0x180006e0a  mov     ebx, 80070216h
0x180006e0f  mov     rbp, [rsp+58h+arg_10]
0x180006e14  mov     eax, ebx
0x180006e16  mov     rbx, [rsp+58h+arg_0]
0x180006e1b  add     rsp, 40h
0x180006e1f  pop     r14
0x180006e21  pop     rdi
0x180006e22  pop     rsi
0x180006e23  retn
```
