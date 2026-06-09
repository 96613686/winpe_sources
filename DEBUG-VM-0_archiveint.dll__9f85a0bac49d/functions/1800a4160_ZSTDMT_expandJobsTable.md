# ZSTDMT_expandJobsTable

- ea: `0x1800a4160`
- end: `0x1800a42c9`
- name: `ZSTDMT_expandJobsTable`
- size: `361`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800a49c0`

## callees

- `0x180015810`
- `0x1800a4160`
- `0x18011a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x1800a4245`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x1800a4245`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800a41e3`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800a41e3`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800a4290`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800a4290`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800a41bf`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800a41bf`
- `api-ms-win-core-synch-l1-2-0!InitializeConditionVariable` at `0x1800a429d`
- `api-ms-win-core-synch-l1-2-0!InitializeConditionVariable` at `0x1800a429d`

## pseudocode

```c
__int64 __fastcall ZSTDMT_expandJobsTable(__int64 a1, int a2)
{
  unsigned int v2; // r12d
  unsigned int v3; // edi
  char *v5; // rbp
  unsigned int v6; // ebx
  __int64 v7; // r13
  void (__fastcall *v8)(__int64, char *); // r15
  __int64 (__fastcall *v9)(_QWORD, size_t); // rax
  unsigned int v10; // ecx
  unsigned int v11; // ebp
  size_t v12; // rdx
  char *v13; // r14
  unsigned int i; // edi
  __int64 v16; // rbx

  v2 = a2 + 2;
  v3 = *(_DWORD *)(a1 + 2944) + 1;
  if ( a2 + 2 > v3 )
  {
    v5 = *(char **)(a1 + 8);
    if ( v5 )
    {
      v6 = 0;
      v7 = *(_QWORD *)(a1 + 3008);
      v8 = *(void (__fastcall **)(__int64, char *))(a1 + 3000);
      if ( *(_DWORD *)(a1 + 2944) != -1 )
      {
        do
          DeleteCriticalSection((LPCRITICAL_SECTION)&v5[416 * v6++ + 16]);
        while ( v6 < v3 );
      }
      if ( v8 )
        v8(v7, v5);
      else
        free(v5);
    }
    v9 = *(__int64 (__fastcall **)(_QWORD, size_t))(a1 + 2992);
    _BitScanReverse(&v10, v2);
    *(_DWORD *)(a1 + 2944) = 0;
    v11 = 1 << (v10 + 1);
    v12 = 416LL * v11;
    if ( v9 )
    {
      v13 = (char *)v9(*(_QWORD *)(a1 + 3008), v12);
      memset_0(v13, 0, 416LL * v11);
    }
    else
    {
      v13 = (char *)calloc(1u, v12);
    }
    if ( !v13 )
    {
      *(_QWORD *)(a1 + 8) = 0;
      return -64;
    }
    for ( i = 0; i < v11; ++i )
    {
      v16 = 416LL * i;
      InitializeCriticalSection((LPCRITICAL_SECTION)&v13[v16 + 16]);
      InitializeConditionVariable((PCONDITION_VARIABLE)&v13[v16 + 56]);
    }
    *(_QWORD *)(a1 + 8) = v13;
    *(_DWORD *)(a1 + 2944) = v11 - 1;
  }
  return 0;
}

```

## disassembly

```asm
0x1800a4160  mov     [rsp+arg_10], rbx
0x1800a4165  push    rbp
0x1800a4166  push    rsi
0x1800a4167  push    rdi
0x1800a4168  push    r12
0x1800a416a  push    r14
0x1800a416c  sub     rsp, 20h
0x1800a4170  mov     edi, [rcx+0B80h]
0x1800a4176  lea     r12d, [rdx+2]
0x1800a417a  inc     edi
0x1800a417c  mov     rsi, rcx
0x1800a417f  cmp     r12d, edi
0x1800a4182  jbe     loc_1800A42B6
0x1800a4188  mov     rbp, [rcx+8]
0x1800a418c  test    rbp, rbp
0x1800a418f  jz      short loc_1800A41F3
0x1800a4191  mov     [rsp+48h+arg_0], r13
0x1800a4196  xor     ebx, ebx
0x1800a4198  mov     r13, [rcx+0BC0h]
0x1800a419f  mov     [rsp+48h+arg_8], r15
0x1800a41a4  mov     r15, [rcx+0BB8h]
0x1800a41ab  test    edi, edi
0x1800a41ad  jz      short loc_1800A41CB
0x1800a41af  lea     r14, [rbp+10h]
0x1800a41b3  mov     eax, ebx
0x1800a41b5  imul    rcx, rax, 1A0h
0x1800a41bc  add     rcx, r14; lpCriticalSection
0x1800a41bf  call    cs:__imp_DeleteCriticalSection
0x1800a41c5  inc     ebx
0x1800a41c7  cmp     ebx, edi
0x1800a41c9  jb      short loc_1800A41B3
0x1800a41cb  test    r15, r15
0x1800a41ce  jz      short loc_1800A41E0
0x1800a41d0  mov     rdx, rbp
0x1800a41d3  mov     rcx, r13
0x1800a41d6  mov     rax, r15
0x1800a41d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a41de  jmp     short loc_1800A41E9
0x1800a41e0  mov     rcx, rbp; Block
0x1800a41e3  call    cs:__imp_free
0x1800a41e9  mov     r13, [rsp+48h+arg_0]
0x1800a41ee  mov     r15, [rsp+48h+arg_8]
0x1800a41f3  mov     rax, [rsi+0BB0h]
0x1800a41fa  mov     ebp, 1
0x1800a41ff  bsr     ecx, r12d
0x1800a4203  mov     dword ptr [rsi+0B80h], 0
0x1800a420d  inc     ecx
0x1800a420f  shl     ebp, cl
0x1800a4211  mov     ecx, ebp
0x1800a4213  imul    rbx, rcx, 1A0h
0x1800a421a  mov     rdx, rbx; Size
0x1800a421d  test    rax, rax
0x1800a4220  jz      short loc_1800A4240
0x1800a4222  mov     rcx, [rsi+0BC0h]
0x1800a4229  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a422e  mov     r8, rbx; Size
0x1800a4231  xor     edx, edx; Val
0x1800a4233  mov     rcx, rax; void *
0x1800a4236  mov     r14, rax
0x1800a4239  call    memset_0
0x1800a423e  jmp     short loc_1800A424E
0x1800a4240  mov     ecx, 1; Count
0x1800a4245  call    cs:__imp_calloc
0x1800a424b  mov     r14, rax
0x1800a424e  test    r14, r14
0x1800a4251  jnz     short loc_1800A426F
0x1800a4253  mov     [rsi+8], r14
0x1800a4257  mov     rax, 0FFFFFFFFFFFFFFC0h
0x1800a425e  mov     rbx, [rsp+48h+arg_10]
0x1800a4263  add     rsp, 20h
0x1800a4267  pop     r14
0x1800a4269  pop     r12
0x1800a426b  pop     rdi
0x1800a426c  pop     rsi
0x1800a426d  pop     rbp
0x1800a426e  retn
0x1800a426f  xor     edi, edi
0x1800a4271  test    ebp, ebp
0x1800a4273  jz      short loc_1800A42A9
0x1800a4275  nop     word ptr [rax+rax+00000000h]
0x1800a4280  mov     eax, edi
0x1800a4282  imul    rbx, rax, 1A0h
0x1800a4289  lea     rcx, [rbx+10h]
0x1800a428d  add     rcx, r14; lpCriticalSection
0x1800a4290  call    cs:__imp_InitializeCriticalSection
0x1800a4296  lea     rcx, [rbx+38h]
0x1800a429a  add     rcx, r14; ConditionVariable
0x1800a429d  call    cs:__imp_InitializeConditionVariable
0x1800a42a3  inc     edi
0x1800a42a5  cmp     edi, ebp
0x1800a42a7  jb      short loc_1800A4280
0x1800a42a9  lea     eax, [rbp-1]
0x1800a42ac  mov     [rsi+8], r14
0x1800a42b0  mov     [rsi+0B80h], eax
0x1800a42b6  mov     rbx, [rsp+48h+arg_10]
0x1800a42bb  xor     eax, eax
0x1800a42bd  add     rsp, 20h
0x1800a42c1  pop     r14
0x1800a42c3  pop     r12
0x1800a42c5  pop     rdi
0x1800a42c6  pop     rsi
0x1800a42c7  pop     rbp
0x1800a42c8  retn
```
