# DoStackCaptureInternal(uint,long)

- ea: `0x1800c9c90`
- end: `0x1800c9d9e`
- name: `?DoStackCaptureInternal@@YAXIJ@Z`
- size: `270`
- prototype: `void __fastcall(unsigned int, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800bb784`

## callees

- `0x1800c9c90`
- `0x1801bea3c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800c9d3c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800c9d3c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800c9d46`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800c9d46`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800c9cf6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800c9cf6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800c9ce3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800c9ce3`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureStackBackTrace` at `0x1800c9d6e`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureStackBackTrace` at `0x1800c9d6e`

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
    for ( i = qword_180265D60;
          i != (__int64 *)((char *)qword_180265D60 + 4 * (unsigned int)dword_180265D5C);
          i = (__int64 *)((char *)i + 4) )
    {
      if ( a2 == *(_DWORD *)i )
        return;
    }
    if ( !_InterlockedCompareExchange(&dword_180265D58, 1, 0) )
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
0x1800c9c90  test    edx, edx
0x1800c9c92  jz      locret_1800C9D9D
0x1800c9c98  mov     [rsp+arg_8], rbx
0x1800c9c9d  mov     [rsp+arg_10], rbp
0x1800c9ca2  push    rsi
0x1800c9ca3  push    rdi
0x1800c9ca4  push    r14
0x1800c9ca6  sub     rsp, 20h
0x1800c9caa  mov     eax, cs:dword_180265D5C
0x1800c9cb0  lea     rcx, qword_180265D60
0x1800c9cb7  mov     esi, edx
0x1800c9cb9  xor     ebp, ebp
0x1800c9cbb  lea     rdx, [rcx+rax*4]
0x1800c9cbf  cmp     rcx, rdx
0x1800c9cc2  jz      short loc_1800C9CD2
0x1800c9cc4  cmp     esi, [rcx]
0x1800c9cc6  jz      loc_1800C9D8B
0x1800c9ccc  add     rcx, 4
0x1800c9cd0  jmp     short loc_1800C9CBF
0x1800c9cd2  xor     eax, eax
0x1800c9cd4  lea     r14d, [rax+1]
0x1800c9cd8  lock cmpxchg cs:dword_180265D58, r14d
0x1800c9ce1  jnz     short loc_1800C9D03
0x1800c9ce3  call    cs:__imp_GetProcessHeap
0x1800c9ce9  lea     edx, [r14+7]; dwFlags
0x1800c9ced  mov     r8d, 2800h; dwBytes
0x1800c9cf3  mov     rcx, rax; hHeap
0x1800c9cf6  call    cs:__imp_HeapAlloc
0x1800c9cfc  mov     cs:lpMem, rax
0x1800c9d03  mov     rax, cs:lpMem
0x1800c9d0a  test    rax, rax
0x1800c9d0d  jz      short loc_1800C9D8B
0x1800c9d0f  call    ?EnsureStackCaptureRegisteredWithWER@@YAXXZ; EnsureStackCaptureRegisteredWithWER(void)
0x1800c9d14  mov     ecx, cs:?g_nCurrentStackCaptureIndex@@3JC; long volatile g_nCurrentStackCaptureIndex
0x1800c9d1a  lea     eax, [rcx+1]
0x1800c9d1d  movzx   edx, al
0x1800c9d20  mov     eax, ecx
0x1800c9d22  lock cmpxchg cs:?g_nCurrentStackCaptureIndex@@3JC, edx; long volatile g_nCurrentStackCaptureIndex
0x1800c9d2a  cmp     ecx, eax
0x1800c9d2c  jnz     short loc_1800C9D14
0x1800c9d2e  mov     rbx, cs:lpMem
0x1800c9d35  lea     rdi, [rdx+rdx*4]
0x1800c9d39  mov     [rbx+rdi*8], esi
0x1800c9d3c  call    cs:__imp_GetCurrentThreadId
0x1800c9d42  mov     [rbx+rdi*8+4], eax
0x1800c9d46  call    cs:__imp_GetTickCount
0x1800c9d4c  mov     [rbx+rdi*8+8], eax
0x1800c9d50  xorps   xmm0, xmm0
0x1800c9d53  lea     rbx, [rbx+rdi*8]
0x1800c9d57  xor     r9d, r9d; BackTraceHash
0x1800c9d5a  xor     eax, eax
0x1800c9d5c  lea     r8, [rbx+10h]; BackTrace
0x1800c9d60  movups  xmmword ptr [rbx+10h], xmm0
0x1800c9d64  mov     ecx, r14d; FramesToSkip
0x1800c9d67  mov     [rbx+20h], rax
0x1800c9d6b  lea     edx, [rax+3]; FramesToCapture
0x1800c9d6e  call    cs:__imp_RtlCaptureStackBackTrace
0x1800c9d74  test    ax, ax
0x1800c9d77  jnz     short loc_1800C9D8B
0x1800c9d79  movdqa  xmm0, cs:__xmm@e0e0e0e0e0e0e0e0e0e0e0e0e0e0e0e0
0x1800c9d81  movups  xmmword ptr [rbx+10h], xmm0
0x1800c9d85  movq    qword ptr [rbx+20h], xmm0
0x1800c9d8b  mov     rbx, [rsp+38h+arg_8]
0x1800c9d90  mov     rbp, [rsp+38h+arg_10]
0x1800c9d95  add     rsp, 20h
0x1800c9d99  pop     r14
0x1800c9d9b  pop     rdi
0x1800c9d9c  pop     rsi
0x1800c9d9d  retn
```
