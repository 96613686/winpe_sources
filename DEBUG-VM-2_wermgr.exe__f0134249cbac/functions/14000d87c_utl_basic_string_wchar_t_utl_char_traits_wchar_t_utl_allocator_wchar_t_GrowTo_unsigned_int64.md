# utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_GrowTo(unsigned __int64)

- ea: `0x14000d87c`
- end: `0x14000d920`
- name: `?_GrowTo@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEAA_N_K@Z`
- size: `164`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x14000dc18`
- `0x14000dd88`
- `0x14000e020`
- `0x14000e258`

## callees

- `0x140003224`
- `0x140003230`
- `0x14000d87c`
- `0x14001c9a8`

## pseudocode

```c
char __fastcall utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_GrowTo(
        __int64 a1,
        __int64 a2)
{
  unsigned __int64 v2; // rdx
  __int64 v4; // r14
  char *v5; // rax
  char *v6; // rbx
  char v7; // si
  __int64 v8; // rbp

  v2 = (a2 + 8) & 0xFFFFFFFFFFFFFFF8uLL;
  if ( v2 > 0x7FFFFFFFFFFFFFFFLL )
    return 0;
  v4 = 2 * v2;
  v5 = (char *)operator new(2 * v2, (const struct std::nothrow_t *)&std::nothrow);
  v6 = v5;
  if ( !v5 )
    return 0;
  v7 = 1;
  v8 = (__int64)(*(_QWORD *)(a1 + 8) - *(_QWORD *)a1) >> 1;
  memcpy_0(v5, *(const void **)a1, 2 * v8 + 2);
  if ( *(_QWORD *)a1 != a1 + 16 )
    operator delete(*(void **)a1, (const struct std::nothrow_t *)&std::nothrow);
  *(_QWORD *)a1 = v6;
  *(_QWORD *)(a1 + 8) = &v6[2 * v8];
  *(_QWORD *)(a1 + 16) = &v6[v4 - 2];
  return v7;
}

```

## disassembly

```asm
0x14000d87c  push    rbx
0x14000d87e  push    rbp
0x14000d87f  push    rsi
0x14000d880  push    rdi
0x14000d881  push    r14
0x14000d883  push    r15
0x14000d885  sub     rsp, 28h
0x14000d889  add     rdx, 8
0x14000d88d  mov     rax, 7FFFFFFFFFFFFFFFh
0x14000d897  and     rdx, 0FFFFFFFFFFFFFFF8h
0x14000d89b  mov     rdi, rcx
0x14000d89e  cmp     rdx, rax
0x14000d8a1  ja      short loc_14000D90D
0x14000d8a3  lea     r14, [rdx+rdx]
0x14000d8a7  mov     rcx, r14; unsigned __int64
0x14000d8aa  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14000d8b1  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14000d8b6  mov     rbx, rax
0x14000d8b9  test    rax, rax
0x14000d8bc  jz      short loc_14000D90D
0x14000d8be  mov     rbp, [rdi+8]
0x14000d8c2  mov     rcx, rax; void *
0x14000d8c5  sub     rbp, [rdi]
0x14000d8c8  mov     sil, 1
0x14000d8cb  mov     rdx, [rdi]; Src
0x14000d8ce  sar     rbp, 1
0x14000d8d1  lea     r8, ds:2[rbp*2]; Size
0x14000d8d9  call    memcpy_0
0x14000d8de  lea     r15, [rdi+10h]
0x14000d8e2  cmp     [rdi], r15
0x14000d8e5  jz      short loc_14000D8F6
0x14000d8e7  mov     rcx, [rdi]; void *
0x14000d8ea  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14000d8f1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000d8f6  lea     rax, [rbx+rbp*2]
0x14000d8fa  mov     [rdi], rbx
0x14000d8fd  mov     [rdi+8], rax
0x14000d901  lea     rax, [r14-2]
0x14000d905  add     rax, rbx
0x14000d908  mov     [r15], rax
0x14000d90b  jmp     short loc_14000D910
0x14000d90d  xor     sil, sil
0x14000d910  mov     al, sil
0x14000d913  add     rsp, 28h
0x14000d917  pop     r15
0x14000d919  pop     r14
0x14000d91b  pop     rdi
0x14000d91c  pop     rsi
0x14000d91d  pop     rbp
0x14000d91e  pop     rbx
0x14000d91f  retn
```
