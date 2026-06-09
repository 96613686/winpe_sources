# DoStackCaptureInternal(uint,long)

- ea: `0x1800cc19c`
- end: `0x1800cc281`
- name: `?DoStackCaptureInternal@@YAXIJ@Z`
- size: `229`
- prototype: `void __fastcall(unsigned int, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800bd9d4`

## callees

- `0x1800cc19c`
- `0x1801c22fc`
- `0x1801c234c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800cc216`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800cc216`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800cc226`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800cc226`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureStackBackTrace` at `0x1800cc254`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureStackBackTrace` at `0x1800cc254`

## pseudocode

```c
void __fastcall DoStackCaptureInternal(__int64 a1, int a2)
{
  __int64 *i; // rcx
  volatile int v4; // ecx
  __int64 v5; // rdx
  _DWORD *v6; // rbx
  __int64 v7; // rdi
  char *v8; // rbx
  __m128i si128; // xmm0

  if ( a2 )
  {
    for ( i = qword_180269E88;
          i != (__int64 *)((char *)qword_180269E88 + 4 * (unsigned int)dword_180269E80);
          i = (__int64 *)((char *)i + 4) )
    {
      if ( a2 == *(_DWORD *)i )
        return;
    }
    EnsureStackCaptureAllocation();
    if ( lpMem )
    {
      EnsureStackCaptureRegisteredWithWER();
      do
      {
        v4 = g_nCurrentStackCaptureIndex;
        v5 = (unsigned __int8)(g_nCurrentStackCaptureIndex + 1);
      }
      while ( v4 != _InterlockedCompareExchange(&g_nCurrentStackCaptureIndex, v5, g_nCurrentStackCaptureIndex) );
      v6 = lpMem;
      v7 = 5 * v5;
      *((_DWORD *)lpMem + 10 * v5) = a2;
      v6[2 * v7 + 1] = GetCurrentThreadId();
      v6[2 * v7 + 2] = GetTickCount();
      v8 = (char *)&v6[2 * v7];
      *((_OWORD *)v8 + 1) = 0;
      *((_QWORD *)v8 + 4) = 0;
      if ( !RtlCaptureStackBackTrace(1u, 3u, (PVOID *)v8 + 2, 0) )
      {
        si128 = _mm_load_si128((const __m128i *)&_xmm_e0e0e0e0e0e0e0e0e0e0e0e0e0e0e0e0);
        *((__m128i *)v8 + 1) = si128;
        *((_QWORD *)v8 + 4) = si128.m128i_i64[0];
      }
    }
  }
}

```

## disassembly

```asm
0x1800cc19c  test    edx, edx
0x1800cc19e  jz      locret_1800CC27F
0x1800cc1a4  push    rbx
0x1800cc1a5  push    rbp
0x1800cc1a6  push    rsi
0x1800cc1a7  push    rdi
0x1800cc1a8  sub     rsp, 28h
0x1800cc1ac  mov     eax, cs:dword_180269E80
0x1800cc1b2  lea     rcx, qword_180269E88
0x1800cc1b9  mov     esi, edx
0x1800cc1bb  xor     ebp, ebp
0x1800cc1bd  lea     rdx, [rcx+rax*4]
0x1800cc1c1  cmp     rcx, rdx
0x1800cc1c4  jz      short loc_1800CC1D4
0x1800cc1c6  cmp     esi, [rcx]
0x1800cc1c8  jz      loc_1800CC277
0x1800cc1ce  add     rcx, 4
0x1800cc1d2  jmp     short loc_1800CC1C1
0x1800cc1d4  call    ?EnsureStackCaptureAllocation@@YAXXZ; EnsureStackCaptureAllocation(void)
0x1800cc1d9  mov     rax, cs:lpMem
0x1800cc1e0  test    rax, rax
0x1800cc1e3  jz      loc_1800CC277
0x1800cc1e9  call    ?EnsureStackCaptureRegisteredWithWER@@YAXXZ; EnsureStackCaptureRegisteredWithWER(void)
0x1800cc1ee  mov     ecx, cs:?g_nCurrentStackCaptureIndex@@3JC; long volatile g_nCurrentStackCaptureIndex
0x1800cc1f4  lea     eax, [rcx+1]
0x1800cc1f7  movzx   edx, al
0x1800cc1fa  mov     eax, ecx
0x1800cc1fc  lock cmpxchg cs:?g_nCurrentStackCaptureIndex@@3JC, edx; long volatile g_nCurrentStackCaptureIndex
0x1800cc204  cmp     ecx, eax
0x1800cc206  jnz     short loc_1800CC1EE
0x1800cc208  mov     rbx, cs:lpMem
0x1800cc20f  lea     rdi, [rdx+rdx*4]
0x1800cc213  mov     [rbx+rdi*8], esi
0x1800cc216  call    cs:__imp_GetCurrentThreadId
0x1800cc21d  nop     dword ptr [rax+rax+00h]
0x1800cc222  mov     [rbx+rdi*8+4], eax
0x1800cc226  call    cs:__imp_GetTickCount
0x1800cc22d  nop     dword ptr [rax+rax+00h]
0x1800cc232  mov     [rbx+rdi*8+8], eax
0x1800cc236  xorps   xmm0, xmm0
0x1800cc239  lea     rbx, [rbx+rdi*8]
0x1800cc23d  xor     r9d, r9d; BackTraceHash
0x1800cc240  xor     eax, eax
0x1800cc242  lea     r8, [rbx+10h]; BackTrace
0x1800cc246  movups  xmmword ptr [rbx+10h], xmm0
0x1800cc24a  mov     [rbx+20h], rax
0x1800cc24e  lea     edx, [rax+3]; FramesToCapture
0x1800cc251  lea     ecx, [rax+1]; FramesToSkip
0x1800cc254  call    cs:__imp_RtlCaptureStackBackTrace
0x1800cc25b  nop     dword ptr [rax+rax+00h]
0x1800cc260  test    ax, ax
0x1800cc263  jnz     short loc_1800CC277
0x1800cc265  movdqa  xmm0, cs:__xmm@e0e0e0e0e0e0e0e0e0e0e0e0e0e0e0e0
0x1800cc26d  movups  xmmword ptr [rbx+10h], xmm0
0x1800cc271  movq    qword ptr [rbx+20h], xmm0
0x1800cc277  add     rsp, 28h
0x1800cc27b  pop     rdi
0x1800cc27c  pop     rsi
0x1800cc27d  pop     rbp
0x1800cc27e  pop     rbx
0x1800cc27f  retn
```
