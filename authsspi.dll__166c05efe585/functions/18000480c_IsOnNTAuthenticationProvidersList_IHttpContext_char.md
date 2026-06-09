# IsOnNTAuthenticationProvidersList(IHttpContext *,char *)

- ea: `0x18000480c`
- end: `0x180004861`
- name: `?IsOnNTAuthenticationProvidersList@@YAHPEAVIHttpContext@@PEAD@Z`
- size: `85`
- prototype: `int __fastcall(struct IHttpContext *, char *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180003a10`
- `0x180004070`

## callees

- `0x180009010`

## import_xrefs

- `iisutil!?FindString@MULTISZA@@QEAAHPEBD@Z` at `0x18000485a`

## pseudocode

```c
int __fastcall IsOnNTAuthenticationProvidersList(struct IHttpContext *a1, char *a2)
{
  __int64 v3; // rax
  __int64 (__fastcall ***v4)(_QWORD, void *); // rax
  __int64 v5; // rax

  v3 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 160LL))(a1);
  v4 = (__int64 (__fastcall ***)(_QWORD, void *))(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 24LL))(v3);
  v5 = (**v4)(v4, s_ModuleId);
  return MULTISZA::FindString((MULTISZA *)(v5 + 16), a2);
}

```

## disassembly

```asm
0x18000480c  push    rbx
0x18000480e  sub     rsp, 20h
0x180004812  mov     rax, [rcx]
0x180004815  mov     rbx, rdx
0x180004818  mov     rax, [rax+0A0h]
0x18000481f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004824  mov     r8, rax
0x180004827  mov     rcx, [rax]
0x18000482a  mov     rax, [rcx+18h]
0x18000482e  mov     rcx, r8
0x180004831  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004836  mov     rdx, cs:?s_ModuleId@@3PEAXEA; void * s_ModuleId
0x18000483d  mov     r8, rax
0x180004840  mov     rcx, [rax]
0x180004843  mov     rax, [rcx]
0x180004846  mov     rcx, r8
0x180004849  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000484e  mov     rdx, rbx
0x180004851  lea     rcx, [rax+10h]
0x180004855  add     rsp, 20h
0x180004859  pop     rbx
0x18000485a  jmp     cs:__imp_?FindString@MULTISZA@@QEAAHPEBD@Z; MULTISZA::FindString(char const *)
```
