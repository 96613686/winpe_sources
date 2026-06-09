# DoStackCapture(long,uint,void *)

- ea: `0x18006f3c0`
- end: `0x18006f4fb`
- name: `?DoStackCapture@@YAXJIPEAX@Z`
- size: `315`
- prototype: `void __fastcall(int, unsigned int, void *)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18001f43c`
- `0x180083a90`

## callees

- `0x18006f3c0`
- `0x18006f504`
- `0x18006f59c`
- `0x18008fd80`
- `0x180095130`
- `0x180095b4c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006f426`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006f426`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18006f43d`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18006f43d`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureStackBackTrace` at `0x18006f473`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureStackBackTrace` at `0x18006f473`

## pseudocode

```c
void __fastcall DoStackCapture(int a1, int a2, void *a3)
{
  volatile int v6; // r8d
  __int64 v7; // r9
  __int64 v8; // rbx
  DWORD CurrentThreadId; // eax
  char *v10; // rdi
  PVOID *v11; // rbx
  __int64 v12; // rax
  __int64 v13; // rdx
  unsigned __int64 v14; // rbx
  __m128i si128; // xmm0
  PVOID BackTrace[12]; // [rsp+20h] [rbp-88h] BYREF

  EnsureStackCaptureRegisteredWithWER();
  do
  {
    v6 = g_nCurrentStackCaptureIndex;
    v7 = (unsigned __int8)(g_nCurrentStackCaptureIndex + 1);
  }
  while ( v6 != _InterlockedCompareExchange(&g_nCurrentStackCaptureIndex, v7, g_nCurrentStackCaptureIndex) );
  v8 = 12 * v7;
  g_StackCaptureFrames[12 * v7] = a1;
  CurrentThreadId = GetCurrentThreadId();
  g_StackCaptureFrames[v8 + 2] = a2;
  g_StackCaptureFrames[v8 + 1] = CurrentThreadId;
  QueryPerformanceCounter((LARGE_INTEGER *)&g_StackCaptureFrames[v8 + 4]);
  v10 = (char *)&g_StackCaptureFrames[v8];
  *(_OWORD *)(v10 + 24) = 0;
  *((_QWORD *)v10 + 5) = 0;
  memset_0(BackTrace, 0, 0x58u);
  v11 = &BackTrace[RtlCaptureStackBackTrace(1u, 0xBu, BackTrace, 0)];
  v12 = std::_Find_vectorized<CWindowData *,CWindowData const *>(BackTrace, v11, a3);
  v13 = 3;
  v14 = ((__int64)v11 - v12) >> 3;
  if ( v14 <= 3 )
  {
    if ( !v14 )
    {
      si128 = _mm_load_si128((const __m128i *)&_xmm_e0e0e0e0e0e0e0e0e0e0e0e0e0e0e0e0);
      *(__m128i *)(v10 + 24) = si128;
      *((_QWORD *)v10 + 5) = si128.m128i_i64[0];
      return;
    }
    v13 = v14;
  }
  std::_Copy_memmove_n<void * *,void * *>(v12, v13, v10 + 24);
}

```

## disassembly

```asm
0x18006f3c0  mov     [rsp+arg_0], rbx
0x18006f3c5  mov     [rsp+arg_8], rbp
0x18006f3ca  push    rsi
0x18006f3cb  push    rdi
0x18006f3cc  push    r14
0x18006f3ce  sub     rsp, 90h
0x18006f3d5  mov     rax, cs:__security_cookie
0x18006f3dc  xor     rax, rsp
0x18006f3df  mov     [rsp+0A8h+var_28], rax
0x18006f3e7  mov     rbp, r8
0x18006f3ea  mov     edi, edx
0x18006f3ec  mov     esi, ecx
0x18006f3ee  call    ?EnsureStackCaptureRegisteredWithWER@@YAXXZ; EnsureStackCaptureRegisteredWithWER(void)
0x18006f3f3  mov     r8d, cs:?g_nCurrentStackCaptureIndex@@3JC; long volatile g_nCurrentStackCaptureIndex
0x18006f3fa  lea     eax, [r8+1]
0x18006f3fe  movzx   r9d, al
0x18006f402  mov     eax, r8d
0x18006f405  lock cmpxchg cs:?g_nCurrentStackCaptureIndex@@3JC, r9d; long volatile g_nCurrentStackCaptureIndex
0x18006f40e  cmp     r8d, eax
0x18006f411  jnz     short loc_18006F3F3
0x18006f413  lea     rbx, [r9+r9*2]
0x18006f417  shl     rbx, 4
0x18006f41b  lea     r14, ?g_StackCaptureFrames@@3PAUStackCaptureFrame@@A; StackCaptureFrame near * g_StackCaptureFrames
0x18006f422  mov     [rbx+r14], esi
0x18006f426  call    cs:__imp_GetCurrentThreadId
0x18006f42c  lea     rcx, [r14+10h]
0x18006f430  mov     [rbx+r14+8], edi
0x18006f435  add     rcx, rbx; lpPerformanceCount
0x18006f438  mov     [rbx+r14+4], eax
0x18006f43d  call    cs:__imp_QueryPerformanceCounter
0x18006f443  xor     eax, eax
0x18006f445  lea     rdi, [rbx+r14]
0x18006f449  xorps   xmm0, xmm0
0x18006f44c  lea     rcx, [rsp+0A8h+BackTrace]; void *
0x18006f451  movups  xmmword ptr [rdi+18h], xmm0
0x18006f455  xor     edx, edx; Val
0x18006f457  mov     [rdi+28h], rax
0x18006f45b  lea     r8d, [rax+58h]; Size
0x18006f45f  call    memset_0
0x18006f464  xor     r9d, r9d; BackTraceHash
0x18006f467  lea     r8, [rsp+0A8h+BackTrace]; BackTrace
0x18006f46c  lea     edx, [r9+0Bh]; FramesToCapture
0x18006f470  lea     ecx, [rdx-0Ah]; FramesToSkip
0x18006f473  call    cs:__imp_RtlCaptureStackBackTrace
0x18006f479  movzx   eax, ax
0x18006f47c  lea     rbx, [rsp+0A8h+BackTrace]
0x18006f481  mov     r8, rbp
0x18006f484  lea     rcx, [rsp+0A8h+BackTrace]
0x18006f489  lea     rbx, [rbx+rax*8]
0x18006f48d  mov     rdx, rbx
0x18006f490  call    ??$_Find_vectorized@PEAVCWindowData@@PEBV1@@std@@YAPEAPEAVCWindowData@@QEAPEAV1@0QEBV1@@Z; std::_Find_vectorized<CWindowData *,CWindowData const *>(CWindowData * * const,CWindowData * * const,CWindowData const * const)
0x18006f495  sub     rbx, rax
0x18006f498  mov     edx, 3
0x18006f49d  sar     rbx, 3
0x18006f4a1  cmp     rbx, rdx
0x18006f4a4  ja      short loc_18006F4C7
0x18006f4a6  test    rbx, rbx
0x18006f4a9  jnz     short loc_18006F4BF
0x18006f4ab  movdqa  xmm0, cs:__xmm@e0e0e0e0e0e0e0e0e0e0e0e0e0e0e0e0
0x18006f4b3  movups  xmmword ptr [rdi+18h], xmm0
0x18006f4b7  movq    qword ptr [rdi+28h], xmm0
0x18006f4bd  jmp     short loc_18006F4D3
0x18006f4bf  mov     rdx, rbx
0x18006f4c2  test    rbx, rbx
0x18006f4c5  jz      short loc_18006F4D3
0x18006f4c7  lea     r8, [rdi+18h]
0x18006f4cb  mov     rcx, rax
0x18006f4ce  call    ??$_Copy_memmove_n@PEAPEAXPEAPEAX@std@@YAPEAPEAXPEAPEAX_K0@Z; std::_Copy_memmove_n<void * *,void * *>(void * *,unsigned __int64,void * *)
0x18006f4d3  mov     rcx, [rsp+0A8h+var_28]
0x18006f4db  xor     rcx, rsp; StackCookie
0x18006f4de  call    __security_check_cookie
0x18006f4e3  lea     r11, [rsp+0A8h+var_18]
0x18006f4eb  mov     rbx, [r11+20h]
0x18006f4ef  mov     rbp, [r11+28h]
0x18006f4f3  mov     rsp, r11
0x18006f4f6  pop     r14
0x18006f4f8  pop     rdi
0x18006f4f9  pop     rsi
0x18006f4fa  retn
```
