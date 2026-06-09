# CPrintAbstractHelper::WhyConstrainedInternal(CPrintCoreConfig *,char const *,char const *,_PRINT_FEATURE_OPTION const * *,ulong *)

- ea: `0x180034280`
- end: `0x180034318`
- name: `?WhyConstrainedInternal@CPrintAbstractHelper@@MEAAJPEAVCPrintCoreConfig@@PEBD1PEAPEBU_PRINT_FEATURE_OPTION@@PEAK@Z`
- size: `152`
- prototype: `__int64 __fastcall(CPrintAbstractHelper *__hidden this, struct CPrintCoreConfig *, const char *, const char *, const struct _PRINT_FEATURE_OPTION **, unsigned int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x1800333c0`
- `0x180033d58`
- `0x180033ff8`
- `0x180034280`
- `0x18005f010`

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
0x180034280  push    rbx
0x180034282  push    rbp
0x180034283  push    rsi
0x180034284  push    rdi
0x180034285  sub     rsp, 38h
0x180034289  mov     rbp, r9
0x18003428c  mov     rdi, r8
0x18003428f  mov     rsi, rdx
0x180034292  mov     rbx, rcx
0x180034295  call    ?IsPrivateTableFeature@CPrintAbstractHelper@@IEAAHPEAVCPrintCoreConfig@@PEBD@Z; CPrintAbstractHelper::IsPrivateTableFeature(CPrintCoreConfig *,char const *)
0x18003429a  test    eax, eax
0x18003429c  jz      short loc_1800342E6
0x18003429e  mov     rax, [rbx]
0x1800342a1  mov     rcx, rbx
0x1800342a4  mov     rax, [rax+78h]
0x1800342a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800342ad  test    rax, rax
0x1800342b0  jz      short loc_1800342DF
0x1800342b2  mov     rax, [rsp+58h+arg_28]
0x1800342ba  mov     r9, rbp; char *
0x1800342bd  mov     [rsp+58h+var_30], rax; unsigned int *
0x1800342c2  mov     r8, rdi; char *
0x1800342c5  mov     rax, [rsp+58h+arg_20]
0x1800342cd  mov     rdx, rsi; struct CPrintCoreConfig *
0x1800342d0  mov     rcx, rbx; this
0x1800342d3  mov     [rsp+58h+var_38], rax; struct _PRINT_FEATURE_OPTION **
0x1800342d8  call    ?WhyConstrainedFromTable@CPrintAbstractHelper@@IEAAJPEAVCPrintCoreConfig@@PEBD1PEAPEBU_PRINT_FEATURE_OPTION@@PEAK@Z; CPrintAbstractHelper::WhyConstrainedFromTable(CPrintCoreConfig *,char const *,char const *,_PRINT_FEATURE_OPTION const * *,ulong *)
0x1800342dd  jmp     short loc_18003430E
0x1800342df  mov     eax, 8007000Eh
0x1800342e4  jmp     short loc_18003430E
0x1800342e6  mov     rax, [rsp+58h+arg_28]
0x1800342ee  mov     r9, rbp; char *
0x1800342f1  mov     [rsp+58h+var_30], rax; unsigned int *
0x1800342f6  mov     r8, rdi; char *
0x1800342f9  mov     rax, [rsp+58h+arg_20]
0x180034301  mov     rdx, rsi; struct CPrintCoreConfig *
0x180034304  mov     [rsp+58h+var_38], rax; struct _PRINT_FEATURE_OPTION **
0x180034309  call    ?WhyConstrainedFromParser@CPrintAbstractHelper@@IEAAJPEAVCPrintCoreConfig@@PEBD1PEAPEBU_PRINT_FEATURE_OPTION@@PEAK@Z; CPrintAbstractHelper::WhyConstrainedFromParser(CPrintCoreConfig *,char const *,char const *,_PRINT_FEATURE_OPTION const * *,ulong *)
0x18003430e  add     rsp, 38h
0x180034312  pop     rdi
0x180034313  pop     rsi
0x180034314  pop     rbp
0x180034315  pop     rbx
0x180034316  retn
```
