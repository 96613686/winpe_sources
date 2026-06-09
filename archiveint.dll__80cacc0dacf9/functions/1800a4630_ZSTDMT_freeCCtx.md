# ZSTDMT_freeCCtx

- ea: `0x1800a4630`
- end: `0x1800a47fb`
- name: `ZSTDMT_freeCCtx`
- size: `459`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180042570`
- `0x1800a3a50`

## callees

- `0x180042610`
- `0x1800a4550`
- `0x1800a4630`
- `0x1800a4810`
- `0x1800a5130`
- `0x1800ab340`
- `0x18011a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800a46d9`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800a4750`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800a477c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800a47c1`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800a47ed`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800a46d9`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800a4750`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800a477c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800a47c1`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800a47ed`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800a46b0`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800a471c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800a4729`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800a46b0`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800a471c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800a4729`

## pseudocode

```c
__int64 __fastcall ZSTDMT_freeCCtx(char *Block)
{
  char *v2; // rsi
  unsigned int v3; // edi
  __int64 v4; // r12
  void (__fastcall *v5)(__int64, char *); // r15
  unsigned int v6; // ebp
  void (__fastcall *v7)(__int64, void *); // rsi
  __int64 v8; // rbp
  void *v9; // rcx
  void *v10; // rcx
  void *v11; // rcx
  void (__fastcall *v12)(_QWORD, _QWORD); // rax
  void (__fastcall *v13)(_QWORD, char *); // rax

  if ( Block )
  {
    if ( (Block[3032] & 1) == 0 )
      POOL_free(*(void **)Block);
    ZSTDMT_releaseAllJobResources(Block);
    v2 = (char *)*((_QWORD *)Block + 1);
    if ( v2 )
    {
      v3 = 0;
      v4 = *((_QWORD *)Block + 376);
      v5 = (void (__fastcall *)(__int64, char *))*((_QWORD *)Block + 375);
      v6 = *((_DWORD *)Block + 736) + 1;
      if ( *((_DWORD *)Block + 736) != -1 )
      {
        do
          DeleteCriticalSection((LPCRITICAL_SECTION)&v2[416 * v3++ + 16]);
        while ( v3 < v6 );
      }
      if ( v5 )
        v5(v4, v2);
      else
        free(v2);
    }
    ZSTDMT_freeBufferPool(*((void **)Block + 2));
    ZSTDMT_freeCCtxPool(*((void **)Block + 3));
    ZSTDMT_freeBufferPool(*((void **)Block + 4));
    v7 = (void (__fastcall *)(__int64, void *))*((_QWORD *)Block + 72);
    v8 = *((_QWORD *)Block + 73);
    DeleteCriticalSection((LPCRITICAL_SECTION)(Block + 352));
    DeleteCriticalSection((LPCRITICAL_SECTION)(Block + 2832));
    v9 = (void *)*((_QWORD *)Block + 83);
    if ( v9 )
    {
      if ( v7 )
        v7(v8, *((void **)Block + 83));
      else
        free(v9);
    }
    v10 = (void *)*((_QWORD *)Block + 85);
    if ( v10 )
    {
      if ( v7 )
        v7(v8, v10);
      else
        free(v10);
    }
    ZSTD_freeCDict(*((void **)Block + 377));
    v11 = (void *)*((_QWORD *)Block + 41);
    if ( v11 )
    {
      v12 = (void (__fastcall *)(_QWORD, _QWORD))*((_QWORD *)Block + 375);
      if ( v12 )
        v12(*((_QWORD *)Block + 376), *((_QWORD *)Block + 41));
      else
        free(v11);
    }
    v13 = (void (__fastcall *)(_QWORD, char *))*((_QWORD *)Block + 375);
    if ( v13 )
    {
      v13(*((_QWORD *)Block + 376), Block);
      return 0;
    }
    free(Block);
  }
  return 0;
}

```

## disassembly

```asm
0x1800a4630  push    rbx
0x1800a4632  sub     rsp, 30h
0x1800a4636  mov     rbx, rcx
0x1800a4639  test    rcx, rcx
0x1800a463c  jz      loc_1800A47F3
0x1800a4642  test    byte ptr [rcx+0BD8h], 1
0x1800a4649  mov     [rsp+38h+arg_0], rbp
0x1800a464e  mov     [rsp+38h+arg_8], rsi
0x1800a4653  mov     [rsp+38h+arg_10], rdi
0x1800a4658  jnz     short loc_1800A4662
0x1800a465a  mov     rcx, [rcx]; Block
0x1800a465d  call    POOL_free
0x1800a4662  mov     rcx, rbx
0x1800a4665  call    ZSTDMT_releaseAllJobResources
0x1800a466a  mov     rsi, [rbx+8]
0x1800a466e  test    rsi, rsi
0x1800a4671  jz      short loc_1800A46E9
0x1800a4673  mov     ebp, [rbx+0B80h]
0x1800a4679  mov     edi, 0
0x1800a467e  mov     [rsp+38h+arg_18], r12
0x1800a4683  mov     r12, [rbx+0BC0h]
0x1800a468a  mov     [rsp+38h+var_18], r15
0x1800a468f  mov     r15, [rbx+0BB8h]
0x1800a4696  add     ebp, 1
0x1800a4699  jz      short loc_1800A46C1
0x1800a469b  mov     [rsp+38h+var_10], r14
0x1800a46a0  lea     r14, [rsi+10h]
0x1800a46a4  mov     eax, edi
0x1800a46a6  imul    rcx, rax, 1A0h
0x1800a46ad  add     rcx, r14; lpCriticalSection
0x1800a46b0  call    cs:__imp_DeleteCriticalSection
0x1800a46b6  inc     edi
0x1800a46b8  cmp     edi, ebp
0x1800a46ba  jb      short loc_1800A46A4
0x1800a46bc  mov     r14, [rsp+38h+var_10]
0x1800a46c1  test    r15, r15
0x1800a46c4  jz      short loc_1800A46D6
0x1800a46c6  mov     rdx, rsi
0x1800a46c9  mov     rcx, r12
0x1800a46cc  mov     rax, r15
0x1800a46cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a46d4  jmp     short loc_1800A46DF
0x1800a46d6  mov     rcx, rsi; Block
0x1800a46d9  call    cs:__imp_free
0x1800a46df  mov     r12, [rsp+38h+arg_18]
0x1800a46e4  mov     r15, [rsp+38h+var_18]
0x1800a46e9  mov     rcx, [rbx+10h]; Block
0x1800a46ed  call    ZSTDMT_freeBufferPool
0x1800a46f2  mov     rcx, [rbx+18h]; Block
0x1800a46f6  call    ZSTDMT_freeCCtxPool
0x1800a46fb  mov     rcx, [rbx+20h]; Block
0x1800a46ff  call    ZSTDMT_freeBufferPool
0x1800a4704  mov     rsi, [rbx+240h]
0x1800a470b  lea     rdi, [rbx+160h]
0x1800a4712  mov     rbp, [rdi+0E8h]
0x1800a4719  mov     rcx, rdi; lpCriticalSection
0x1800a471c  call    cs:__imp_DeleteCriticalSection
0x1800a4722  lea     rcx, [rdi+9B0h]; lpCriticalSection
0x1800a4729  call    cs:__imp_DeleteCriticalSection
0x1800a472f  mov     rcx, [rdi+138h]; Block
0x1800a4736  test    rcx, rcx
0x1800a4739  jz      short loc_1800A4756
0x1800a473b  test    rsi, rsi
0x1800a473e  jz      short loc_1800A4750
0x1800a4740  mov     rdx, rcx
0x1800a4743  mov     rax, rsi
0x1800a4746  mov     rcx, rbp
0x1800a4749  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a474e  jmp     short loc_1800A4756
0x1800a4750  call    cs:__imp_free
0x1800a4756  mov     rcx, [rdi+148h]; Block
0x1800a475d  mov     rdi, [rsp+38h+arg_10]
0x1800a4762  test    rcx, rcx
0x1800a4765  jz      short loc_1800A4782
0x1800a4767  test    rsi, rsi
0x1800a476a  jz      short loc_1800A477C
0x1800a476c  mov     rdx, rcx
0x1800a476f  mov     rax, rsi
0x1800a4772  mov     rcx, rbp
0x1800a4775  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a477a  jmp     short loc_1800A4782
0x1800a477c  call    cs:__imp_free
0x1800a4782  mov     rcx, [rbx+0BC8h]; Block
0x1800a4789  call    ZSTD_freeCDict
0x1800a478e  mov     rcx, [rbx+148h]; Block
0x1800a4795  mov     rsi, [rsp+38h+arg_8]
0x1800a479a  mov     rbp, [rsp+38h+arg_0]
0x1800a479f  test    rcx, rcx
0x1800a47a2  jz      short loc_1800A47C7
0x1800a47a4  mov     rax, [rbx+0BB8h]
0x1800a47ab  test    rax, rax
0x1800a47ae  jz      short loc_1800A47C1
0x1800a47b0  mov     rdx, rcx
0x1800a47b3  mov     rcx, [rbx+0BC0h]
0x1800a47ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a47bf  jmp     short loc_1800A47C7
0x1800a47c1  call    cs:__imp_free
0x1800a47c7  mov     rax, [rbx+0BB8h]
0x1800a47ce  test    rax, rax
0x1800a47d1  jz      short loc_1800A47EA
0x1800a47d3  mov     rcx, [rbx+0BC0h]
0x1800a47da  mov     rdx, rbx
0x1800a47dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a47e2  xor     eax, eax
0x1800a47e4  add     rsp, 30h
0x1800a47e8  pop     rbx
0x1800a47e9  retn
0x1800a47ea  mov     rcx, rbx; Block
0x1800a47ed  call    cs:__imp_free
0x1800a47f3  xor     eax, eax
0x1800a47f5  add     rsp, 30h
0x1800a47f9  pop     rbx
0x1800a47fa  retn
```
