# CommonUtil::CNewSprintfPolicy<wchar_t>::ReAllocateNoCopy(wchar_t * *,unsigned __int64)

- ea: `0x140003310`
- end: `0x14000337d`
- name: `?ReAllocateNoCopy@?$CNewSprintfPolicy@_W@CommonUtil@@SAJPEAPEA_W_K@Z`
- size: `109`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1400030e4`

## callees

- `0x140003310`
- `0x140005c40`
- `0x140006170`

## pseudocode

```c
__int64 __fastcall CommonUtil::CNewSprintfPolicy<wchar_t>::ReAllocateNoCopy(void **a1, unsigned __int64 a2)
{
  void *v2; // rbx
  unsigned __int64 v5; // rax
  void *v6; // rax

  v2 = *a1;
  operator delete(*a1);
  if ( v2 )
    *a1 = (void *)33059;
  v5 = 2 * a2;
  if ( !is_mul_ok(a2, 2u) )
    v5 = -1;
  v6 = operator new[](v5, (const struct std::nothrow_t *)&std::nothrow);
  *a1 = v6;
  return v6 == 0 ? 0x8007000E : 0;
}

```

## disassembly

```asm
0x140003310  mov     [rsp+arg_0], rbx
0x140003315  mov     [rsp+arg_8], rsi
0x14000331a  push    rdi
0x14000331b  sub     rsp, 20h
0x14000331f  mov     rbx, [rcx]
0x140003322  mov     rdi, rcx
0x140003325  mov     rcx, rbx; void *
0x140003328  mov     rsi, rdx
0x14000332b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140003330  test    rbx, rbx
0x140003333  jz      short loc_14000333C
0x140003335  mov     qword ptr [rdi], 8123h
0x14000333c  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x140003343  mov     eax, 2
0x140003348  mul     rsi
0x14000334b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140003352  cmovb   rax, rcx
0x140003356  mov     rcx, rax; unsigned __int64
0x140003359  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x14000335e  mov     rbx, [rsp+28h+arg_0]
0x140003363  mov     rsi, [rsp+28h+arg_8]
0x140003368  mov     [rdi], rax
0x14000336b  neg     rax
0x14000336e  sbb     eax, eax
0x140003370  not     eax
0x140003372  and     eax, 8007000Eh
0x140003377  add     rsp, 20h
0x14000337b  pop     rdi
0x14000337c  retn
```
