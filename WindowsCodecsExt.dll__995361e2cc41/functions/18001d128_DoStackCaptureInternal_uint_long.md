# DoStackCaptureInternal(uint,long)

- ea: `0x18001d128`
- end: `0x18001d236`
- name: `?DoStackCaptureInternal@@YAXIJ@Z`
- size: `270`
- prototype: `void __fastcall(unsigned int, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800171c4`

## callees

- `0x18001d128`
- `0x1800228b8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001d1d4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001d1d4`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001d1de`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001d1de`
- `ntdll!RtlCaptureStackBackTrace` at `0x18001d206`
- `ntdll!RtlCaptureStackBackTrace` at `0x18001d206`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001d17b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001d17b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001d18e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001d18e`

## pseudocode

```c
void __fastcall DoStackCaptureInternal(__int64 a1, int a2)
{
  __int64 *i; // rcx
  HANDLE ProcessHeap; // rax
  volatile int v5; // ecx
  __int64 v6; // rdx
  _DWORD *v7; // rbx
  __int64 v8; // rdi
  char *v9; // rbx
  __m128i si128; // xmm0

  if ( a2 )
  {
    for ( i = qword_1800402F8;
          i != (__int64 *)((char *)qword_1800402F8 + 4 * (unsigned int)dword_1800402F4);
          i = (__int64 *)((char *)i + 4) )
    {
      if ( a2 == *(_DWORD *)i )
        return;
    }
    if ( !_InterlockedCompareExchange(&dword_180040328, 1, 0) )
    {
      ProcessHeap = GetProcessHeap();
      lpMem = HeapAlloc(ProcessHeap, 8u, 0x2800u);
    }
    if ( lpMem )
    {
      EnsureStackCaptureRegisteredWithWER();
      do
      {
        v5 = g_nCurrentStackCaptureIndex;
        v6 = (unsigned __int8)(g_nCurrentStackCaptureIndex + 1);
      }
      while ( v5 != _InterlockedCompareExchange(&g_nCurrentStackCaptureIndex, v6, g_nCurrentStackCaptureIndex) );
      v7 = lpMem;
      v8 = 5 * v6;
      *((_DWORD *)lpMem + 10 * v6) = a2;
      v7[2 * v8 + 1] = GetCurrentThreadId();
      v7[2 * v8 + 2] = GetTickCount();
      v9 = (char *)&v7[2 * v8];
      *((_OWORD *)v9 + 1) = 0;
      *((_QWORD *)v9 + 4) = 0;
      if ( !RtlCaptureStackBackTrace(1u, 3u, (PVOID *)v9 + 2, 0) )
      {
        si128 = _mm_load_si128((const __m128i *)&_xmm_e0e0e0e0e0e0e0e0e0e0e0e0e0e0e0e0);
        *((__m128i *)v9 + 1) = si128;
        *((_QWORD *)v9 + 4) = si128.m128i_i64[0];
      }
    }
  }
}

```

## disassembly

```asm
0x18001d128  test    edx, edx
0x18001d12a  jz      locret_18001D235
0x18001d130  mov     [rsp+arg_8], rbx
0x18001d135  mov     [rsp+arg_10], rbp
0x18001d13a  push    rsi
0x18001d13b  push    rdi
0x18001d13c  push    r14
0x18001d13e  sub     rsp, 20h
0x18001d142  mov     eax, cs:dword_1800402F4
0x18001d148  lea     rcx, qword_1800402F8
0x18001d14f  mov     esi, edx
0x18001d151  xor     ebp, ebp
0x18001d153  lea     rdx, [rcx+rax*4]
0x18001d157  cmp     rcx, rdx
0x18001d15a  jz      short loc_18001D16A
0x18001d15c  cmp     esi, [rcx]
0x18001d15e  jz      loc_18001D223
0x18001d164  add     rcx, 4
0x18001d168  jmp     short loc_18001D157
0x18001d16a  xor     eax, eax
0x18001d16c  lea     r14d, [rax+1]
0x18001d170  lock cmpxchg cs:dword_180040328, r14d
0x18001d179  jnz     short loc_18001D19B
0x18001d17b  call    cs:__imp_GetProcessHeap
0x18001d181  lea     edx, [r14+7]; dwFlags
0x18001d185  mov     r8d, 2800h; dwBytes
0x18001d18b  mov     rcx, rax; hHeap
0x18001d18e  call    cs:__imp_HeapAlloc
0x18001d194  mov     cs:lpMem, rax
0x18001d19b  mov     rax, cs:lpMem
0x18001d1a2  test    rax, rax
0x18001d1a5  jz      short loc_18001D223
0x18001d1a7  call    ?EnsureStackCaptureRegisteredWithWER@@YAXXZ; EnsureStackCaptureRegisteredWithWER(void)
0x18001d1ac  mov     ecx, cs:?g_nCurrentStackCaptureIndex@@3JC; long volatile g_nCurrentStackCaptureIndex
0x18001d1b2  lea     eax, [rcx+1]
0x18001d1b5  movzx   edx, al
0x18001d1b8  mov     eax, ecx
0x18001d1ba  lock cmpxchg cs:?g_nCurrentStackCaptureIndex@@3JC, edx; long volatile g_nCurrentStackCaptureIndex
0x18001d1c2  cmp     ecx, eax
0x18001d1c4  jnz     short loc_18001D1AC
0x18001d1c6  mov     rbx, cs:lpMem
0x18001d1cd  lea     rdi, [rdx+rdx*4]
0x18001d1d1  mov     [rbx+rdi*8], esi
0x18001d1d4  call    cs:__imp_GetCurrentThreadId
0x18001d1da  mov     [rbx+rdi*8+4], eax
0x18001d1de  call    cs:__imp_GetTickCount
0x18001d1e4  mov     [rbx+rdi*8+8], eax
0x18001d1e8  xorps   xmm0, xmm0
0x18001d1eb  lea     rbx, [rbx+rdi*8]
0x18001d1ef  xor     r9d, r9d; BackTraceHash
0x18001d1f2  xor     eax, eax
0x18001d1f4  lea     r8, [rbx+10h]; BackTrace
0x18001d1f8  movups  xmmword ptr [rbx+10h], xmm0
0x18001d1fc  mov     ecx, r14d; FramesToSkip
0x18001d1ff  mov     [rbx+20h], rax
0x18001d203  lea     edx, [rax+3]; FramesToCapture
0x18001d206  call    cs:__imp_RtlCaptureStackBackTrace
0x18001d20c  test    ax, ax
0x18001d20f  jnz     short loc_18001D223
0x18001d211  movdqa  xmm0, cs:__xmm@e0e0e0e0e0e0e0e0e0e0e0e0e0e0e0e0
0x18001d219  movups  xmmword ptr [rbx+10h], xmm0
0x18001d21d  movq    qword ptr [rbx+20h], xmm0
0x18001d223  mov     rbx, [rsp+38h+arg_8]
0x18001d228  mov     rbp, [rsp+38h+arg_10]
0x18001d22d  add     rsp, 20h
0x18001d231  pop     r14
0x18001d233  pop     rdi
0x18001d234  pop     rsi
0x18001d235  retn
```
