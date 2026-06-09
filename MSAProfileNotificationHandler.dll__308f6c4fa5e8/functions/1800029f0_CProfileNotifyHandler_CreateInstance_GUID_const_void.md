# CProfileNotifyHandler_CreateInstance(_GUID const &,void * *)

- ea: `0x1800029f0`
- end: `0x180002a72`
- name: `?CProfileNotifyHandler_CreateInstance@@YAJAEBU_GUID@@PEAPEAX@Z`
- size: `130`
- prototype: `__int64 __fastcall(const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x180001ce0`
- `0x1800029f0`
- `0x180009010`

## pseudocode

```c
__int64 __fastcall CProfileNotifyHandler_CreateInstance(const struct _GUID *a1, void **a2)
{
  unsigned int v4; // edi
  _DWORD *v5; // rbx

  *a2 = 0;
  v4 = -2147024882;
  v5 = operator new(0x10u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v5 )
  {
    ++g_cRefDll;
    *(_QWORD *)v5 = &CProfileNotifyHandler::`vftable';
    v5[2] = 1;
    v4 = ((__int64 (__fastcall *)(_DWORD *, const struct _GUID *, void **))CProfileNotifyHandler::`vftable')(v5, a1, a2);
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v5 + 16LL))(v5);
  }
  return v4;
}

```

## disassembly

```asm
0x1800029f0  push    rbx
0x1800029f2  push    rbp
0x1800029f3  push    rsi
0x1800029f4  push    rdi
0x1800029f5  sub     rsp, 28h
0x1800029f9  mov     rsi, rdx
0x1800029fc  mov     qword ptr [rdx], 0
0x180002a03  mov     rbp, rcx
0x180002a06  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180002a0d  mov     ecx, 10h; unsigned __int64
0x180002a12  mov     edi, 8007000Eh
0x180002a17  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180002a1c  mov     [rsp+48h+arg_8], rax
0x180002a21  mov     rbx, rax
0x180002a24  test    rax, rax
0x180002a27  jz      short loc_180002A67
0x180002a29  inc     cs:?g_cRefDll@@3JA; long g_cRefDll
0x180002a2f  lea     rax, ??_7CProfileNotifyHandler@@6B@; const CProfileNotifyHandler::`vftable'
0x180002a36  mov     [rbx], rax
0x180002a39  mov     dword ptr [rbx+8], 1
0x180002a40  test    rbx, rbx
0x180002a43  jz      short loc_180002A67
0x180002a45  mov     rax, [rax]
0x180002a48  mov     r8, rsi
0x180002a4b  mov     rdx, rbp
0x180002a4e  mov     rcx, rbx
0x180002a51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a56  mov     rdx, [rbx]
0x180002a59  mov     edi, eax
0x180002a5b  mov     rcx, rbx
0x180002a5e  mov     rax, [rdx+10h]
0x180002a62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a67  mov     eax, edi
0x180002a69  add     rsp, 28h
0x180002a6d  pop     rdi
0x180002a6e  pop     rsi
0x180002a6f  pop     rbp
0x180002a70  pop     rbx
0x180002a71  retn
```
