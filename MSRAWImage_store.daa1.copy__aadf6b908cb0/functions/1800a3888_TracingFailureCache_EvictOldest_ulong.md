# TracingFailureCache::EvictOldest(ulong)

- ea: `0x1800a3888`
- end: `0x1800a39b4`
- name: `?EvictOldest@TracingFailureCache@@IEAAXK@Z`
- size: `300`
- prototype: `void __fastcall(TracingFailureCache *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800a37c4`

## callees

- `0x1800a3888`
- `0x1800a3e98`
- `0x1800b0460`

## import_xrefs

- `api-ms-win-crt-utility-l1-1-0!qsort` at `0x1800a38cc`
- `api-ms-win-crt-utility-l1-1-0!qsort` at `0x1800a38cc`

## pseudocode

```c
void __fastcall TracingFailureCache::EvictOldest(TracingFailureCache *this)
{
  unsigned int v1; // ebp
  char v2; // si
  int v4; // r14d
  unsigned int v5; // ebx
  TracingFailureDetails *v6; // rcx
  unsigned int i; // esi
  __int64 v8; // r8
  __int64 v9; // rbx

  v1 = 0;
  v2 = 0;
  v4 = 7;
  if ( *((_DWORD *)this + 10) )
  {
    ++*((_DWORD *)this + 13);
    qsort(*((void **)this + 11), *((unsigned int *)this + 10), 0x918u, TracingFailureDetails::CompareByTimeNewestFirst);
    v5 = *((_DWORD *)this + 10) - 1;
    do
    {
      v6 = (TracingFailureDetails *)(*((_QWORD *)this + 11) + 2328LL * v5);
      if ( *((_DWORD *)v6 + 505) )
      {
        if ( !v2 )
        {
          v2 = 1;
          v1 = v5;
        }
      }
      else
      {
        TracingFailureDetails::Reset(v6);
        --*((_DWORD *)this + 10);
        --v4;
      }
      if ( !v5 )
        break;
      --v5;
    }
    while ( v4 );
    if ( v2 )
    {
      for ( i = 0; i < *((_DWORD *)this + 10); ++i )
      {
        v8 = *((_QWORD *)this + 11);
        if ( !*(_DWORD *)(v8 + 2328LL * i + 2304) )
        {
          for ( ; !*(_DWORD *)(2328LL * v1 + v8 + 2020); --v1 )
            ;
          v9 = 2328LL * v1;
          memmove((void *)(v8 + 2328LL * i), (const void *)(v9 + v8), 0x918u);
          TracingFailureDetails::Reset((TracingFailureDetails *)(v9 + *((_QWORD *)this + 11)));
        }
      }
    }
  }
}

```

## disassembly

```asm
0x1800a3888  mov     [rsp+arg_0], rbx
0x1800a388d  mov     [rsp+arg_8], rbp
0x1800a3892  mov     [rsp+arg_10], rsi
0x1800a3897  push    rdi
0x1800a3898  push    r12
0x1800a389a  push    r14
0x1800a389c  sub     rsp, 20h
0x1800a38a0  xor     ebp, ebp
0x1800a38a2  xor     sil, sil
0x1800a38a5  mov     rdi, rcx
0x1800a38a8  lea     r14d, [rbp+7]
0x1800a38ac  cmp     [rcx+28h], ebp
0x1800a38af  jz      loc_1800A399A
0x1800a38b5  inc     dword ptr [rcx+34h]
0x1800a38b8  lea     r9, ?CompareByTimeNewestFirst@TracingFailureDetails@@SAHPEBX0@Z; CompareFunction
0x1800a38bf  mov     edx, [rcx+28h]; NumOfElements
0x1800a38c2  mov     r8d, 918h; SizeOfElements
0x1800a38c8  mov     rcx, [rcx+58h]; Base
0x1800a38cc  call    cs:__imp_qsort
0x1800a38d3  nop     dword ptr [rax+rax+00h]
0x1800a38d8  mov     ebx, [rdi+28h]
0x1800a38db  dec     ebx
0x1800a38dd  or      r12d, 0FFFFFFFFh
0x1800a38e1  mov     eax, ebx
0x1800a38e3  imul    rcx, rax, 918h
0x1800a38ea  add     rcx, [rdi+58h]; this
0x1800a38ee  cmp     dword ptr [rcx+7E4h], 0
0x1800a38f5  jnz     short loc_1800A3905
0x1800a38f7  call    ?Reset@TracingFailureDetails@@QEAAXXZ; TracingFailureDetails::Reset(void)
0x1800a38fc  add     [rdi+28h], r12d
0x1800a3900  add     r14d, r12d
0x1800a3903  jmp     short loc_1800A390F
0x1800a3905  test    sil, sil
0x1800a3908  jnz     short loc_1800A390F
0x1800a390a  mov     sil, 1
0x1800a390d  mov     ebp, ebx
0x1800a390f  test    ebx, ebx
0x1800a3911  jz      short loc_1800A391B
0x1800a3913  add     ebx, r12d
0x1800a3916  test    r14d, r14d
0x1800a3919  jnz     short loc_1800A38E1
0x1800a391b  test    sil, sil
0x1800a391e  jz      short loc_1800A399A
0x1800a3920  xor     esi, esi
0x1800a3922  cmp     [rdi+28h], esi
0x1800a3925  jbe     short loc_1800A399A
0x1800a3927  mov     r8, [rdi+58h]
0x1800a392b  mov     eax, esi
0x1800a392d  imul    r9, rax, 918h
0x1800a3934  add     r9, r8
0x1800a3937  cmp     dword ptr [r9+900h], 0
0x1800a393f  jnz     short loc_1800A3993
0x1800a3941  mov     eax, ebp
0x1800a3943  imul    rcx, rax, 918h
0x1800a394a  cmp     dword ptr [rcx+r8+7E4h], 0
0x1800a3953  jnz     short loc_1800A396C
0x1800a3955  add     ebp, r12d
0x1800a3958  mov     eax, ebp
0x1800a395a  imul    rdx, rax, 918h
0x1800a3961  cmp     dword ptr [rdx+r8+7E4h], 0
0x1800a396a  jz      short loc_1800A3955
0x1800a396c  mov     eax, ebp
0x1800a396e  mov     rcx, r9; void *
0x1800a3971  imul    rbx, rax, 918h
0x1800a3978  lea     rdx, [rbx+r8]; Src
0x1800a397c  mov     r8d, 918h; Size
0x1800a3982  call    memmove
0x1800a3987  mov     rcx, [rdi+58h]
0x1800a398b  add     rcx, rbx; this
0x1800a398e  call    ?Reset@TracingFailureDetails@@QEAAXXZ; TracingFailureDetails::Reset(void)
0x1800a3993  inc     esi
0x1800a3995  cmp     esi, [rdi+28h]
0x1800a3998  jb      short loc_1800A3927
0x1800a399a  mov     rbx, [rsp+38h+arg_0]
0x1800a399f  mov     rbp, [rsp+38h+arg_8]
0x1800a39a4  mov     rsi, [rsp+38h+arg_10]
0x1800a39a9  add     rsp, 20h
0x1800a39ad  pop     r14
0x1800a39af  pop     r12
0x1800a39b1  pop     rdi
0x1800a39b2  retn
```
