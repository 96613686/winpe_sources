# BASIC_AUTH_PROVIDER::IsEnabled(IHttpContext *,int *)

- ea: `0x180002910`
- end: `0x18000297a`
- name: `?IsEnabled@BASIC_AUTH_PROVIDER@@UEAAJPEAVIHttpContext@@PEAH@Z`
- size: `106`
- prototype: `__int64 __fastcall(BASIC_AUTH_PROVIDER *__hidden this, struct IHttpContext *, int *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180002910`
- `0x180006010`

## pseudocode

```c
__int64 __fastcall BASIC_AUTH_PROVIDER::IsEnabled(BASIC_AUTH_PROVIDER *this, struct IHttpContext *a2, int *a3)
{
  __int64 v5; // rax
  __int64 (__fastcall ***v6)(_QWORD, void *); // rax
  __int64 v7; // rax

  if ( !a3 )
    return 2147942487LL;
  *a3 = 0;
  v5 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 160LL))(a2);
  v6 = (__int64 (__fastcall ***)(_QWORD, void *))(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 24LL))(v5);
  v7 = (**v6)(v6, s_pModuleContext);
  if ( v7 )
    *a3 = *(_DWORD *)(v7 + 12);
  return 0;
}

```

## disassembly

```asm
0x180002910  push    rbx
0x180002912  sub     rsp, 20h
0x180002916  mov     rbx, r8
0x180002919  test    r8, r8
0x18000291c  jnz     short loc_180002925
0x18000291e  mov     eax, 80070057h
0x180002923  jmp     short loc_180002974
0x180002925  mov     dword ptr [r8], 0
0x18000292c  mov     rcx, rdx
0x18000292f  mov     rax, [rdx]
0x180002932  mov     rax, [rax+0A0h]
0x180002939  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000293e  mov     rdx, rax
0x180002941  mov     rcx, [rax]
0x180002944  mov     rax, [rcx+18h]
0x180002948  mov     rcx, rdx
0x18000294b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002950  mov     rdx, cs:?s_pModuleContext@@3PEAXEA; void * s_pModuleContext
0x180002957  mov     r8, rax
0x18000295a  mov     rcx, [rax]
0x18000295d  mov     rax, [rcx]
0x180002960  mov     rcx, r8
0x180002963  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002968  test    rax, rax
0x18000296b  jz      short loc_180002972
0x18000296d  mov     eax, [rax+0Ch]
0x180002970  mov     [rbx], eax
0x180002972  xor     eax, eax
0x180002974  add     rsp, 20h
0x180002978  pop     rbx
0x180002979  retn
```
