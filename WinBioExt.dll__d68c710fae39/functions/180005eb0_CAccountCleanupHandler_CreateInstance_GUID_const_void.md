# CAccountCleanupHandler_CreateInstance(_GUID const &,void * *)

- ea: `0x180005eb0`
- end: `0x180005f4d`
- name: `?CAccountCleanupHandler_CreateInstance@@YAJAEBU_GUID@@PEAPEAX@Z`
- size: `157`
- prototype: `__int64 __fastcall(const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180001a1c`
- `0x180002084`
- `0x180005eb0`
- `0x18000b010`

## pseudocode

```c
__int64 __fastcall CAccountCleanupHandler_CreateInstance(const struct _GUID *a1, void **a2)
{
  unsigned int v4; // edi
  _QWORD *v5; // rbx

  *a2 = 0;
  v4 = -2147024882;
  v5 = operator new(0x68u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v5 )
  {
    ++dword_1800105B4;
    *v5 = &CAccountCleanupHandler::`vftable';
    v5[1] = 1;
    v5[12] = 0;
    memset_0(v5 + 2, 0, 0x4Cu);
    v4 = (*(__int64 (__fastcall **)(_QWORD *, const struct _GUID *, void **))*v5)(v5, a1, a2);
    (*(void (__fastcall **)(_QWORD *))(*v5 + 16LL))(v5);
  }
  return v4;
}

```

## disassembly

```asm
0x180005eb0  push    rbx
0x180005eb2  push    rbp
0x180005eb3  push    rsi
0x180005eb4  push    rdi
0x180005eb5  sub     rsp, 28h
0x180005eb9  mov     rsi, rdx
0x180005ebc  mov     qword ptr [rdx], 0
0x180005ec3  mov     rbp, rcx
0x180005ec6  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180005ecd  mov     ecx, 68h ; 'h'; unsigned __int64
0x180005ed2  mov     edi, 8007000Eh
0x180005ed7  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180005edc  mov     [rsp+48h+arg_8], rax
0x180005ee1  mov     rbx, rax
0x180005ee4  test    rax, rax
0x180005ee7  jz      short loc_180005F42
0x180005ee9  inc     cs:dword_1800105B4
0x180005eef  lea     rax, ??_7CAccountCleanupHandler@@6B@; const CAccountCleanupHandler::`vftable'
0x180005ef6  xor     edx, edx; Val
0x180005ef8  mov     [rbx], rax
0x180005efb  mov     qword ptr [rbx+8], 1
0x180005f03  lea     rcx, [rbx+10h]; void *
0x180005f07  mov     qword ptr [rbx+60h], 0
0x180005f0f  lea     r8d, [rdx+4Ch]; Size
0x180005f13  call    memset_0
0x180005f18  test    rbx, rbx
0x180005f1b  jz      short loc_180005F42
0x180005f1d  mov     rax, [rbx]
0x180005f20  mov     r8, rsi
0x180005f23  mov     rdx, rbp
0x180005f26  mov     rcx, rbx
0x180005f29  mov     rax, [rax]
0x180005f2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f31  mov     rdx, [rbx]
0x180005f34  mov     edi, eax
0x180005f36  mov     rcx, rbx
0x180005f39  mov     rax, [rdx+10h]
0x180005f3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f42  mov     eax, edi
0x180005f44  add     rsp, 28h
0x180005f48  pop     rdi
0x180005f49  pop     rsi
0x180005f4a  pop     rbp
0x180005f4b  pop     rbx
0x180005f4c  retn
```
