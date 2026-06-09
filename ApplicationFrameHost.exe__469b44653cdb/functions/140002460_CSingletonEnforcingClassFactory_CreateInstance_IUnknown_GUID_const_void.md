# CSingletonEnforcingClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x140002460`
- end: `0x1400024b1`
- name: `?CreateInstance@CSingletonEnforcingClassFactory@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `81`
- prototype: `__int64 __fastcall(CSingletonEnforcingClassFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x140002460`
- `0x140002ce0`
- `0x14000b010`

## pseudocode

```c
__int64 __fastcall CSingletonEnforcingClassFactory::CreateInstance(
        CSingletonEnforcingClassFactory *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  int v5; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  *a4 = 0;
  if ( !a2 )
    return (***((__int64 (__fastcall ****)(_QWORD, const struct _GUID *, void **))this + 7))(
             *((_QWORD *)this + 7),
             a3,
             a4);
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x14,
    (unsigned int)"pcshell\\shell\\applicationframe\\host\\classfactory.cpp",
    (const char *)0x80040110LL,
    v5);
  return 2147746064LL;
}

```

## disassembly

```asm
0x140002460  sub     rsp, 28h
0x140002464  mov     r10, r8
0x140002467  mov     qword ptr [r9], 0
0x14000246e  test    rdx, rdx
0x140002471  jz      short loc_140002496
0x140002473  mov     rcx, [rsp+28h]; this
0x140002478  mov     r9d, 80040110h; char *
0x14000247e  lea     r8, aPcshellShellAp; "pcshell\\shell\\applicationframe\\host"...
0x140002485  mov     edx, 14h; void *
0x14000248a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000248f  mov     eax, 80040110h
0x140002494  jmp     short loc_1400024AC
0x140002496  mov     rcx, [rcx+38h]
0x14000249a  mov     rax, [rcx]
0x14000249d  mov     r8, r9
0x1400024a0  mov     rdx, r10
0x1400024a3  mov     rax, [rax]
0x1400024a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400024ab  nop
0x1400024ac  add     rsp, 28h
0x1400024b0  retn
```
