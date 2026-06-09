# KerbClient3961UpdateSharedConfiguration(uchar *,unsigned __int64)

- ea: `0x180016870`
- end: `0x1800168c7`
- name: `?KerbClient3961UpdateSharedConfiguration@@YAJPEAE_K@Z`
- size: `87`
- prototype: `__int64 __fastcall(unsigned __int8 *, unsigned __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callees

- `0x180016870`
- `0x180029010`

## import_xrefs

- `Kerb3961!__imp_GetLocalCipherPolicy` at `0x18001688a`
- `Kerb3961!__imp_GetLocalCipherPolicy` at `0x18001688a`

## pseudocode

```c
__int64 __fastcall KerbClient3961UpdateSharedConfiguration(unsigned __int8 *a1, __int64 a2)
{
  __int64 *LocalCipherPolicy; // rax
  __int64 v5; // r8
  _QWORD v7[3]; // [rsp+20h] [rbp-18h] BYREF
  char v8; // [rsp+40h] [rbp+8h] BYREF

  if ( !a1 || !a2 )
    return 3221225485LL;
  LocalCipherPolicy = (__int64 *)GetLocalCipherPolicy();
  v5 = *LocalCipherPolicy;
  v7[0] = a2;
  v7[1] = a1;
  return *(unsigned int *)(*(__int64 (__fastcall **)(__int64 *, char *, _QWORD *))(v5 + 40))(LocalCipherPolicy, &v8, v7);
}

```

## disassembly

```asm
0x180016870  mov     [rsp+arg_8], rbx
0x180016875  push    rdi
0x180016876  sub     rsp, 30h
0x18001687a  mov     rbx, rdx
0x18001687d  mov     rdi, rcx
0x180016880  test    rcx, rcx
0x180016883  jz      short loc_1800168B7
0x180016885  test    rdx, rdx
0x180016888  jz      short loc_1800168B7
0x18001688a  call    cs:__imp_GetLocalCipherPolicy
0x180016890  mov     rcx, rax
0x180016893  lea     rdx, [rsp+38h+arg_0]
0x180016898  mov     r8, [rax]
0x18001689b  mov     [rsp+38h+var_18], rbx
0x1800168a0  mov     [rsp+38h+var_10], rdi
0x1800168a5  mov     rax, [r8+28h]
0x1800168a9  lea     r8, [rsp+38h+var_18]
0x1800168ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800168b3  mov     eax, [rax]
0x1800168b5  jmp     short loc_1800168BC
0x1800168b7  mov     eax, 0C000000Dh
0x1800168bc  mov     rbx, [rsp+38h+arg_8]
0x1800168c1  add     rsp, 30h
0x1800168c5  pop     rdi
0x1800168c6  retn
```
