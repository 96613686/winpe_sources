# CPrintAbstractHelper::WhyConstrainedInternal(CPrintCoreConfig *,char const *,char const *,_PRINT_FEATURE_OPTION const * *,ulong *)

- ea: `0x180032c10`
- end: `0x180032ca7`
- name: `?WhyConstrainedInternal@CPrintAbstractHelper@@MEAAJPEAVCPrintCoreConfig@@PEBD1PEAPEBU_PRINT_FEATURE_OPTION@@PEAK@Z`
- size: `151`
- prototype: `__int64 __fastcall(CPrintAbstractHelper *__hidden this, struct CPrintCoreConfig *, const char *, const char *, const struct _PRINT_FEATURE_OPTION **, unsigned int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x180031d60`
- `0x1800326f8`
- `0x180032998`
- `0x180032c10`
- `0x18005d010`

## pseudocode

```c
__int64 __fastcall CPrintAbstractHelper::WhyConstrainedInternal(
        CPrintAbstractHelper *this,
        struct CPrintCoreConfig *a2,
        const char *a3,
        const char *a4,
        struct _PRINT_FEATURE_OPTION **a5,
        unsigned int *a6)
{
  CPrintAbstractHelper *v10; // rcx

  if ( !(unsigned int)CPrintAbstractHelper::IsPrivateTableFeature(this, a2, a3) )
    return CPrintAbstractHelper::WhyConstrainedFromParser(
             v10,
             a2,
             a3,
             a4,
             (const struct _PRINT_FEATURE_OPTION **)a5,
             a6);
  if ( (*(__int64 (__fastcall **)(CPrintAbstractHelper *))(*(_QWORD *)this + 120LL))(this) )
    return CPrintAbstractHelper::WhyConstrainedFromTable(this, a2, a3, a4, a5, a6);
  return 2147942414LL;
}

```

## disassembly

```asm
0x180032c10  push    rbx
0x180032c12  push    rbp
0x180032c13  push    rsi
0x180032c14  push    rdi
0x180032c15  sub     rsp, 38h
0x180032c19  mov     rbp, r9
0x180032c1c  mov     rdi, r8
0x180032c1f  mov     rsi, rdx
0x180032c22  mov     rbx, rcx
0x180032c25  call    ?IsPrivateTableFeature@CPrintAbstractHelper@@IEAAHPEAVCPrintCoreConfig@@PEBD@Z; CPrintAbstractHelper::IsPrivateTableFeature(CPrintCoreConfig *,char const *)
0x180032c2a  test    eax, eax
0x180032c2c  jz      short loc_180032C76
0x180032c2e  mov     rax, [rbx]
0x180032c31  mov     rcx, rbx
0x180032c34  mov     rax, [rax+78h]
0x180032c38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032c3d  test    rax, rax
0x180032c40  jz      short loc_180032C6F
0x180032c42  mov     rax, [rsp+58h+arg_28]
0x180032c4a  mov     r9, rbp; char *
0x180032c4d  mov     [rsp+58h+var_30], rax; unsigned int *
0x180032c52  mov     r8, rdi; char *
0x180032c55  mov     rax, [rsp+58h+arg_20]
0x180032c5d  mov     rdx, rsi; struct CPrintCoreConfig *
0x180032c60  mov     rcx, rbx; this
0x180032c63  mov     [rsp+58h+var_38], rax; struct _PRINT_FEATURE_OPTION **
0x180032c68  call    ?WhyConstrainedFromTable@CPrintAbstractHelper@@IEAAJPEAVCPrintCoreConfig@@PEBD1PEAPEBU_PRINT_FEATURE_OPTION@@PEAK@Z; CPrintAbstractHelper::WhyConstrainedFromTable(CPrintCoreConfig *,char const *,char const *,_PRINT_FEATURE_OPTION const * *,ulong *)
0x180032c6d  jmp     short loc_180032C9E
0x180032c6f  mov     eax, 8007000Eh
0x180032c74  jmp     short loc_180032C9E
0x180032c76  mov     rax, [rsp+58h+arg_28]
0x180032c7e  mov     r9, rbp; char *
0x180032c81  mov     [rsp+58h+var_30], rax; unsigned int *
0x180032c86  mov     r8, rdi; char *
0x180032c89  mov     rax, [rsp+58h+arg_20]
0x180032c91  mov     rdx, rsi; struct CPrintCoreConfig *
0x180032c94  mov     [rsp+58h+var_38], rax; struct _PRINT_FEATURE_OPTION **
0x180032c99  call    ?WhyConstrainedFromParser@CPrintAbstractHelper@@IEAAJPEAVCPrintCoreConfig@@PEBD1PEAPEBU_PRINT_FEATURE_OPTION@@PEAK@Z; CPrintAbstractHelper::WhyConstrainedFromParser(CPrintCoreConfig *,char const *,char const *,_PRINT_FEATURE_OPTION const * *,ulong *)
0x180032c9e  add     rsp, 38h
0x180032ca2  pop     rdi
0x180032ca3  pop     rsi
0x180032ca4  pop     rbp
0x180032ca5  pop     rbx
0x180032ca6  retn
```
