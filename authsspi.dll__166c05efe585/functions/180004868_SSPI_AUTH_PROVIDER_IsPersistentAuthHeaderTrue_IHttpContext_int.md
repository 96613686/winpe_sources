# SSPI_AUTH_PROVIDER::IsPersistentAuthHeaderTrue(IHttpContext *,int)

- ea: `0x180004868`
- end: `0x1800048ea`
- name: `?IsPersistentAuthHeaderTrue@SSPI_AUTH_PROVIDER@@AEAAHPEAVIHttpContext@@H@Z`
- size: `130`
- prototype: `_BOOL8 __fastcall(SSPI_AUTH_PROVIDER *this, struct IHttpContext *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800021f0`

## callees

- `0x180004868`
- `0x1800085e8`
- `0x180009010`

## pseudocode

```c
_BOOL8 __fastcall SSPI_AUTH_PROVIDER::IsPersistentAuthHeaderTrue(
        SSPI_AUTH_PROVIDER *this,
        struct IHttpContext *a2,
        int a3)
{
  __int64 v5; // rax
  __int64 (__fastcall ***v6)(_QWORD, void *); // rax
  __int64 v7; // rax

  v5 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 160LL))(a2);
  v6 = (__int64 (__fastcall ***)(_QWORD, void *))(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 24LL))(v5);
  v7 = (**v6)(v6, s_ModuleId);
  return *(_DWORD *)(v7 + 132) && (*(_DWORD *)(v7 + 136) || a3) && (unsigned int)IsProxyRequest(a2) == 0;
}

```

## disassembly

```asm
0x180004868  mov     [rsp+arg_0], rbx
0x18000486d  push    rdi
0x18000486e  sub     rsp, 20h
0x180004872  mov     rax, [rdx]
0x180004875  mov     rcx, rdx
0x180004878  mov     edi, r8d
0x18000487b  mov     rbx, rdx
0x18000487e  mov     rax, [rax+0A0h]
0x180004885  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000488a  mov     r9, rax
0x18000488d  mov     rcx, [rax]
0x180004890  mov     rax, [rcx+18h]
0x180004894  mov     rcx, r9
0x180004897  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000489c  mov     rdx, cs:?s_ModuleId@@3PEAXEA; void * s_ModuleId
0x1800048a3  mov     r8, rax
0x1800048a6  mov     rcx, [rax]
0x1800048a9  mov     rax, [rcx]
0x1800048ac  mov     rcx, r8
0x1800048af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800048b4  cmp     dword ptr [rax+84h], 0
0x1800048bb  jz      short loc_1800048DD
0x1800048bd  cmp     dword ptr [rax+88h], 0
0x1800048c4  jnz     short loc_1800048CA
0x1800048c6  test    edi, edi
0x1800048c8  jz      short loc_1800048DD
0x1800048ca  mov     rcx, rbx; struct IHttpContext *
0x1800048cd  call    ?IsProxyRequest@@YAHPEAVIHttpContext@@@Z; IsProxyRequest(IHttpContext *)
0x1800048d2  xor     ecx, ecx
0x1800048d4  test    eax, eax
0x1800048d6  setz    cl
0x1800048d9  mov     eax, ecx
0x1800048db  jmp     short loc_1800048DF
0x1800048dd  xor     eax, eax
0x1800048df  mov     rbx, [rsp+28h+arg_0]
0x1800048e4  add     rsp, 20h
0x1800048e8  pop     rdi
0x1800048e9  retn
```
