# DoStackCapture(long,uint,void *)

- ea: `0x18002b188`
- end: `0x18002b2f2`
- name: `?DoStackCapture@@YAXJIPEAX@Z`
- size: `362`
- prototype: `void __fastcall(int, unsigned int, void *)`
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18001f204`
- `0x18002b3b0`
- `0x18002b434`

## callees

- `0x180020fd0`
- `0x180021060`
- `0x180021ce0`
- `0x180021cec`
- `0x18002b188`
- `0x18002b4d0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002b208`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002b208`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18002b21f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18002b21f`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureStackBackTrace` at `0x18002b26d`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureStackBackTrace` at `0x18002b26d`

## pseudocode

```c
void __fastcall DoStackCapture(int a1, int a2, void *a3)
{
  volatile int v5; // ecx
  __int64 v6; // rdx
  __int64 v7; // rbx
  DWORD CurrentThreadId; // eax
  __int64 v9; // rcx
  char *v10; // rdi
  PVOID *v11; // rbx
  _BYTE *trivial_8; // rax
  __int64 v13; // r8
  unsigned __int64 v14; // rbx
  __m128i si128; // xmm0
  PVOID BackTrace[12]; // [rsp+20h] [rbp-A8h] BYREF

  if ( !_InterlockedCompareExchange(&dword_18003F3F0, 1, 0) )
  {
    MilWerRegisterMemoryBlock(g_StackCaptureFrames, 0x3800u);
    MilWerRegisterMemoryBlock((const void *)&g_nCurrentStackCaptureIndex, 4u);
  }
  do
  {
    v5 = g_nCurrentStackCaptureIndex;
    v6 = (unsigned __int8)(g_nCurrentStackCaptureIndex + 1);
  }
  while ( v5 != _InterlockedCompareExchange(&g_nCurrentStackCaptureIndex, v6, g_nCurrentStackCaptureIndex) );
  v7 = 14 * v6;
  g_StackCaptureFrames[14 * v6] = a1;
  CurrentThreadId = GetCurrentThreadId();
  g_StackCaptureFrames[v7 + 2] = a2;
  g_StackCaptureFrames[v7 + 1] = CurrentThreadId;
  QueryPerformanceCounter((LARGE_INTEGER *)&g_StackCaptureFrames[v7 + 4]);
  if ( g_pFrameId )
    v9 = *g_pFrameId;
  else
    v9 = 0;
  *(_QWORD *)&g_StackCaptureFrames[v7 + 12] = v9;
  v10 = (char *)&g_StackCaptureFrames[v7];
  *(_OWORD *)(v10 + 24) = 0;
  *((_QWORD *)v10 + 5) = 0;
  memset_0(BackTrace, 0, 0x58u);
  v11 = &BackTrace[RtlCaptureStackBackTrace(1u, 0xBu, BackTrace, 0)];
  trivial_8 = (_BYTE *)_std_find_trivial_8(BackTrace, v11);
  v13 = 3;
  v14 = ((char *)v11 - trivial_8) >> 3;
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
  memmove_0(v10 + 24, trivial_8, 8 * v13);
}

```

## disassembly

```asm
0x18002b188  push    rbx
0x18002b18a  push    rbp
0x18002b18b  push    rsi
0x18002b18c  push    rdi
0x18002b18d  push    r14
0x18002b18f  push    r15
0x18002b191  sub     rsp, 98h
0x18002b198  mov     rax, cs:__security_cookie
0x18002b19f  xor     rax, rsp
0x18002b1a2  mov     [rsp+0C8h+var_48], rax
0x18002b1aa  xor     eax, eax
0x18002b1ac  lea     r14, ?g_StackCaptureFrames@@3PAUStackCaptureFrame@@A; StackCaptureFrame near * g_StackCaptureFrames
0x18002b1b3  mov     rbp, r8
0x18002b1b6  mov     edi, edx
0x18002b1b8  mov     esi, ecx
0x18002b1ba  lea     r15d, [rax+1]
0x18002b1be  lock cmpxchg cs:dword_18003F3F0, r15d
0x18002b1c7  jnz     short loc_18002B1E6
0x18002b1c9  mov     edx, 3800h; unsigned int
0x18002b1ce  mov     rcx, r14; void *
0x18002b1d1  call    ?MilWerRegisterMemoryBlock@@YAXPEBXI@Z; MilWerRegisterMemoryBlock(void const *,uint)
0x18002b1d6  lea     edx, [r15+3]; unsigned int
0x18002b1da  lea     rcx, ?g_nCurrentStackCaptureIndex@@3JC; void *
0x18002b1e1  call    ?MilWerRegisterMemoryBlock@@YAXPEBXI@Z; MilWerRegisterMemoryBlock(void const *,uint)
0x18002b1e6  mov     ecx, cs:?g_nCurrentStackCaptureIndex@@3JC; long volatile g_nCurrentStackCaptureIndex
0x18002b1ec  lea     eax, [rcx+1]
0x18002b1ef  movzx   edx, al
0x18002b1f2  mov     eax, ecx
0x18002b1f4  lock cmpxchg cs:?g_nCurrentStackCaptureIndex@@3JC, edx; long volatile g_nCurrentStackCaptureIndex
0x18002b1fc  cmp     ecx, eax
0x18002b1fe  jnz     short loc_18002B1E6
0x18002b200  imul    rbx, rdx, 38h ; '8'
0x18002b204  mov     [rbx+r14], esi
0x18002b208  call    cs:__imp_GetCurrentThreadId
0x18002b20e  lea     rcx, [r14+10h]
0x18002b212  mov     [rbx+r14+8], edi
0x18002b217  add     rcx, rbx; lpPerformanceCount
0x18002b21a  mov     [rbx+r14+4], eax
0x18002b21f  call    cs:__imp_QueryPerformanceCounter
0x18002b225  mov     rax, cs:?g_pFrameId@@3PEA_KEA; unsigned __int64 * g_pFrameId
0x18002b22c  test    rax, rax
0x18002b22f  jz      short loc_18002B236
0x18002b231  mov     rcx, [rax]
0x18002b234  jmp     short loc_18002B238
0x18002b236  xor     ecx, ecx
0x18002b238  mov     [rbx+r14+30h], rcx
0x18002b23d  lea     rdi, [rbx+r14]
0x18002b241  xor     eax, eax
0x18002b243  lea     rcx, [rsp+0C8h+BackTrace]; void *
0x18002b248  xorps   xmm0, xmm0
0x18002b24b  xor     edx, edx; Val
0x18002b24d  movups  xmmword ptr [rdi+18h], xmm0
0x18002b251  mov     [rdi+28h], rax
0x18002b255  lea     r8d, [rax+58h]; Size
0x18002b259  call    memset_0
0x18002b25e  xor     r9d, r9d; BackTraceHash
0x18002b261  lea     r8, [rsp+0C8h+BackTrace]; BackTrace
0x18002b266  mov     ecx, r15d; FramesToSkip
0x18002b269  lea     edx, [r9+0Bh]; FramesToCapture
0x18002b26d  call    cs:__imp_RtlCaptureStackBackTrace
0x18002b273  movzx   eax, ax
0x18002b276  lea     rbx, [rsp+0C8h+BackTrace]
0x18002b27b  mov     r8, rbp
0x18002b27e  lea     rcx, [rsp+0C8h+BackTrace]
0x18002b283  lea     rbx, [rbx+rax*8]
0x18002b287  mov     rdx, rbx
0x18002b28a  call    __std_find_trivial_8
0x18002b28f  sub     rbx, rax
0x18002b292  mov     r8d, 3
0x18002b298  sar     rbx, 3
0x18002b29c  cmp     rbx, r8
0x18002b29f  ja      short loc_18002B2C2
0x18002b2a1  test    rbx, rbx
0x18002b2a4  jnz     short loc_18002B2BA
0x18002b2a6  movdqa  xmm0, cs:__xmm@e0e0e0e0e0e0e0e0e0e0e0e0e0e0e0e0
0x18002b2ae  movups  xmmword ptr [rdi+18h], xmm0
0x18002b2b2  movq    qword ptr [rdi+28h], xmm0
0x18002b2b8  jmp     short loc_18002B2D2
0x18002b2ba  mov     r8, rbx
0x18002b2bd  test    rbx, rbx
0x18002b2c0  jz      short loc_18002B2D2
0x18002b2c2  shl     r8, 3; Size
0x18002b2c6  lea     rcx, [rdi+18h]; void *
0x18002b2ca  mov     rdx, rax; Src
0x18002b2cd  call    memmove_0
0x18002b2d2  mov     rcx, [rsp+0C8h+var_48]
0x18002b2da  xor     rcx, rsp; StackCookie
0x18002b2dd  call    __security_check_cookie
0x18002b2e2  add     rsp, 98h
0x18002b2e9  pop     r15
0x18002b2eb  pop     r14
0x18002b2ed  pop     rdi
0x18002b2ee  pop     rsi
0x18002b2ef  pop     rbp
0x18002b2f0  pop     rbx
0x18002b2f1  retn
```
