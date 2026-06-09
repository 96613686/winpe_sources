# ZSTDMT_freeCCtxPool

- ea: `0x1800a4810`
- end: `0x1800a48ab`
- name: `ZSTDMT_freeCCtxPool`
- size: `155`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x1800a3920`
- `0x1800a4630`
- `0x1800a49c0`

## callees

- `0x1800424e0`
- `0x1800a4810`
- `0x18011a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800a487c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800a489f`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800a487c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800a489f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800a4821`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800a4821`

## pseudocode

```c
void __fastcall ZSTDMT_freeCCtxPool(struct _RTL_CRITICAL_SECTION *Block)
{
  int i; // edi
  void *SpinCount; // rcx
  void (__fastcall *OwningThread)(HANDLE, ULONG_PTR); // rax
  void (__fastcall *v5)(HANDLE, struct _RTL_CRITICAL_SECTION *); // rax

  if ( Block )
  {
    DeleteCriticalSection(Block);
    if ( Block[1].SpinCount )
    {
      for ( i = 0; i < SLODWORD(Block[1].DebugInfo); ++i )
        ZSTD_freeCCtx(*(void **)(Block[1].SpinCount + 8LL * i));
      SpinCount = (void *)Block[1].SpinCount;
      if ( SpinCount )
      {
        OwningThread = (void (__fastcall *)(HANDLE, ULONG_PTR))Block[1].OwningThread;
        if ( OwningThread )
          OwningThread(Block[1].LockSemaphore, Block[1].SpinCount);
        else
          free(SpinCount);
      }
    }
    v5 = (void (__fastcall *)(HANDLE, struct _RTL_CRITICAL_SECTION *))Block[1].OwningThread;
    if ( v5 )
      v5(Block[1].LockSemaphore, Block);
    else
      free(Block);
  }
}

```

## disassembly

```asm
0x1800a4810  test    rcx, rcx
0x1800a4813  jz      locret_1800A48AA
0x1800a4819  push    rbx
0x1800a481a  sub     rsp, 20h
0x1800a481e  mov     rbx, rcx
0x1800a4821  call    cs:__imp_DeleteCriticalSection
0x1800a4827  cmp     qword ptr [rbx+48h], 0
0x1800a482c  jz      short loc_1800A4882
0x1800a482e  mov     [rsp+28h+arg_0], rdi
0x1800a4833  xor     edi, edi
0x1800a4835  cmp     [rbx+28h], edi
0x1800a4838  jle     short loc_1800A4857
0x1800a483a  nop     word ptr [rax+rax+00h]
0x1800a4840  mov     rcx, [rbx+48h]
0x1800a4844  movsxd  rax, edi
0x1800a4847  mov     rcx, [rcx+rax*8]; Block
0x1800a484b  call    ZSTD_freeCCtx
0x1800a4850  inc     edi
0x1800a4852  cmp     edi, [rbx+28h]
0x1800a4855  jl      short loc_1800A4840
0x1800a4857  mov     rcx, [rbx+48h]; Block
0x1800a485b  mov     rdi, [rsp+28h+arg_0]
0x1800a4860  test    rcx, rcx
0x1800a4863  jz      short loc_1800A4882
0x1800a4865  mov     rax, [rbx+38h]
0x1800a4869  test    rax, rax
0x1800a486c  jz      short loc_1800A487C
0x1800a486e  mov     rdx, rcx
0x1800a4871  mov     rcx, [rbx+40h]
0x1800a4875  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a487a  jmp     short loc_1800A4882
0x1800a487c  call    cs:__imp_free
0x1800a4882  mov     rax, [rbx+38h]
0x1800a4886  test    rax, rax
0x1800a4889  jz      short loc_1800A489C
0x1800a488b  mov     rcx, [rbx+40h]
0x1800a488f  mov     rdx, rbx
0x1800a4892  add     rsp, 20h
0x1800a4896  pop     rbx
0x1800a4897  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x1800a489c  mov     rcx, rbx; Block
0x1800a489f  call    cs:__imp_free
0x1800a48a5  add     rsp, 20h
0x1800a48a9  pop     rbx
0x1800a48aa  retn
```
