# CERTMAP_AUTH_PROVIDER::IsEnabled(IHttpContext *,int *)

- ea: `0x180002260`
- end: `0x1800022ca`
- name: `?IsEnabled@CERTMAP_AUTH_PROVIDER@@UEAAJPEAVIHttpContext@@PEAH@Z`
- size: `106`
- prototype: `__int64 __fastcall(CERTMAP_AUTH_PROVIDER *__hidden this, struct IHttpContext *, int *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180002260`
- `0x180005010`

## pseudocode

```c
__int64 __fastcall CERTMAP_AUTH_PROVIDER::IsEnabled(CERTMAP_AUTH_PROVIDER *this, struct IHttpContext *a2, int *a3)
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
0x180002260  push    rbx
0x180002262  sub     rsp, 20h
0x180002266  mov     rbx, r8
0x180002269  test    r8, r8
0x18000226c  jnz     short loc_180002275
0x18000226e  mov     eax, 80070057h
0x180002273  jmp     short loc_1800022C4
0x180002275  mov     dword ptr [r8], 0
0x18000227c  mov     rcx, rdx
0x18000227f  mov     rax, [rdx]
0x180002282  mov     rax, [rax+0A0h]
0x180002289  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000228e  mov     rdx, rax
0x180002291  mov     rcx, [rax]
0x180002294  mov     rax, [rcx+18h]
0x180002298  mov     rcx, rdx
0x18000229b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800022a0  mov     rdx, cs:?s_pModuleContext@@3PEAXEA; void * s_pModuleContext
0x1800022a7  mov     r8, rax
0x1800022aa  mov     rcx, [rax]
0x1800022ad  mov     rax, [rcx]
0x1800022b0  mov     rcx, r8
0x1800022b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800022b8  test    rax, rax
0x1800022bb  jz      short loc_1800022C2
0x1800022bd  mov     eax, [rax+0Ch]
0x1800022c0  mov     [rbx], eax
0x1800022c2  xor     eax, eax
0x1800022c4  add     rsp, 20h
0x1800022c8  pop     rbx
0x1800022c9  retn
```
