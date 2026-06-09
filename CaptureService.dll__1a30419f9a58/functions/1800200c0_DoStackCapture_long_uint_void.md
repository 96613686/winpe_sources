# DoStackCapture(long,uint,void *)

- ea: `0x1800200c0`
- end: `0x18002022a`
- name: `?DoStackCapture@@YAXJIPEAX@Z`
- size: `362`
- prototype: `void __fastcall(int, unsigned int, void *)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800202ec`
- `0x180020370`

## callees

- `0x180002a60`
- `0x180002e60`
- `0x180003bbc`
- `0x180003bc8`
- `0x1800200c0`
- `0x18002040c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180020140`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180020140`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180020157`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180020157`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureStackBackTrace` at `0x1800201a5`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureStackBackTrace` at `0x1800201a5`

## pseudocode

```c
void __fastcall DoStackCapture(int a1, int a2, void *a3)
{
  volatile int v6; // ecx
  __int64 v7; // rdx
  __int64 v8; // rbx
  DWORD CurrentThreadId; // eax
  struct StackCaptureFrame *v10; // rcx
  char *v11; // rdi
  PVOID *v12; // rbx
  _BYTE *trivial_8; // rax
  __int64 v14; // r8
  unsigned __int64 v15; // rbx
  __m128i si128; // xmm0
  PVOID BackTrace[12]; // [rsp+20h] [rbp-A8h] BYREF

  if ( !_InterlockedCompareExchange(&dword_18002F6D8, 1, 0) )
  {
    MilWerRegisterMemoryBlock(&g_StackCaptureFrames, 0x3800u);
    MilWerRegisterMemoryBlock((const void *)&g_nCurrentStackCaptureIndex, 4u);
  }
  do
  {
    v6 = g_nCurrentStackCaptureIndex;
    v7 = (unsigned __int8)(g_nCurrentStackCaptureIndex + 1);
  }
  while ( v6 != _InterlockedCompareExchange(&g_nCurrentStackCaptureIndex, v7, g_nCurrentStackCaptureIndex) );
  v8 = 56 * v7;
  *((_DWORD *)&g_StackCaptureFrames + 14 * v7) = a1;
  CurrentThreadId = GetCurrentThreadId();
  *(_DWORD *)((char *)&g_StackCaptureFrames + v8 + 8) = a2;
  *(_DWORD *)((char *)&g_StackCaptureFrames + v8 + 4) = CurrentThreadId;
  QueryPerformanceCounter((LARGE_INTEGER *)((char *)&g_StackCaptureFrames + v8 + 16));
  if ( g_pFrameId )
    v10 = (struct StackCaptureFrame *)*g_pFrameId;
  else
    v10 = 0;
  *(struct StackCaptureFrame near **)((char *)&g_StackCaptureFrames + v8 + 48) = v10;
  v11 = (char *)&g_StackCaptureFrames + v8;
  *(_OWORD *)(v11 + 24) = 0;
  *((_QWORD *)v11 + 5) = 0;
  memset_0(BackTrace, 0, 0x58u);
  v12 = &BackTrace[RtlCaptureStackBackTrace(1u, 0xBu, BackTrace, 0)];
  trivial_8 = (_BYTE *)_std_find_trivial_8(BackTrace, v12, a3);
  v14 = 3;
  v15 = ((char *)v12 - trivial_8) >> 3;
  if ( v15 <= 3 )
  {
    if ( !v15 )
    {
      si128 = _mm_load_si128((const __m128i *)&_xmm_e0e0e0e0e0e0e0e0e0e0e0e0e0e0e0e0);
      *(__m128i *)(v11 + 24) = si128;
      *((_QWORD *)v11 + 5) = si128.m128i_i64[0];
      return;
    }
    v14 = v15;
  }
  memmove_0(v11 + 24, trivial_8, 8 * v14);
}

```

## disassembly

```asm
0x1800200c0  push    rbx
0x1800200c2  push    rbp
0x1800200c3  push    rsi
0x1800200c4  push    rdi
0x1800200c5  push    r14
0x1800200c7  push    r15
0x1800200c9  sub     rsp, 98h
0x1800200d0  mov     rax, cs:__security_cookie
0x1800200d7  xor     rax, rsp
0x1800200da  mov     [rsp+0C8h+var_48], rax
0x1800200e2  xor     eax, eax
0x1800200e4  lea     r14, ?g_StackCaptureFrames@@3PAUStackCaptureFrame@@A; StackCaptureFrame near * g_StackCaptureFrames
0x1800200eb  mov     rbp, r8
0x1800200ee  mov     edi, edx
0x1800200f0  mov     esi, ecx
0x1800200f2  lea     r15d, [rax+1]
0x1800200f6  lock cmpxchg cs:dword_18002F6D8, r15d
0x1800200ff  jnz     short loc_18002011E
0x180020101  mov     edx, 3800h; unsigned int
0x180020106  mov     rcx, r14; void *
0x180020109  call    ?MilWerRegisterMemoryBlock@@YAXPEBXI@Z; MilWerRegisterMemoryBlock(void const *,uint)
0x18002010e  lea     edx, [r15+3]; unsigned int
0x180020112  lea     rcx, ?g_nCurrentStackCaptureIndex@@3JC; void *
0x180020119  call    ?MilWerRegisterMemoryBlock@@YAXPEBXI@Z; MilWerRegisterMemoryBlock(void const *,uint)
0x18002011e  mov     ecx, cs:?g_nCurrentStackCaptureIndex@@3JC; long volatile g_nCurrentStackCaptureIndex
0x180020124  lea     eax, [rcx+1]
0x180020127  movzx   edx, al
0x18002012a  mov     eax, ecx
0x18002012c  lock cmpxchg cs:?g_nCurrentStackCaptureIndex@@3JC, edx; long volatile g_nCurrentStackCaptureIndex
0x180020134  cmp     ecx, eax
0x180020136  jnz     short loc_18002011E
0x180020138  imul    rbx, rdx, 38h ; '8'
0x18002013c  mov     [rbx+r14], esi
0x180020140  call    cs:__imp_GetCurrentThreadId
0x180020146  lea     rcx, [r14+10h]
0x18002014a  mov     [rbx+r14+8], edi
0x18002014f  add     rcx, rbx; lpPerformanceCount
0x180020152  mov     [rbx+r14+4], eax
0x180020157  call    cs:__imp_QueryPerformanceCounter
0x18002015d  mov     rax, cs:?g_pFrameId@@3PEA_KEA; unsigned __int64 * g_pFrameId
0x180020164  test    rax, rax
0x180020167  jz      short loc_18002016E
0x180020169  mov     rcx, [rax]
0x18002016c  jmp     short loc_180020170
0x18002016e  xor     ecx, ecx
0x180020170  mov     [rbx+r14+30h], rcx
0x180020175  lea     rdi, [rbx+r14]
0x180020179  xor     eax, eax
0x18002017b  lea     rcx, [rsp+0C8h+BackTrace]; void *
0x180020180  xorps   xmm0, xmm0
0x180020183  xor     edx, edx; Val
0x180020185  movups  xmmword ptr [rdi+18h], xmm0
0x180020189  mov     [rdi+28h], rax
0x18002018d  lea     r8d, [rax+58h]; Size
0x180020191  call    memset_0
0x180020196  xor     r9d, r9d; BackTraceHash
0x180020199  lea     r8, [rsp+0C8h+BackTrace]; BackTrace
0x18002019e  mov     ecx, r15d; FramesToSkip
0x1800201a1  lea     edx, [r9+0Bh]; FramesToCapture
0x1800201a5  call    cs:__imp_RtlCaptureStackBackTrace
0x1800201ab  movzx   eax, ax
0x1800201ae  lea     rbx, [rsp+0C8h+BackTrace]
0x1800201b3  mov     r8, rbp
0x1800201b6  lea     rcx, [rsp+0C8h+BackTrace]
0x1800201bb  lea     rbx, [rbx+rax*8]
0x1800201bf  mov     rdx, rbx
0x1800201c2  call    __std_find_trivial_8
0x1800201c7  sub     rbx, rax
0x1800201ca  mov     r8d, 3
0x1800201d0  sar     rbx, 3
0x1800201d4  cmp     rbx, r8
0x1800201d7  ja      short loc_1800201FA
0x1800201d9  test    rbx, rbx
0x1800201dc  jnz     short loc_1800201F2
0x1800201de  movdqa  xmm0, cs:__xmm@e0e0e0e0e0e0e0e0e0e0e0e0e0e0e0e0
0x1800201e6  movups  xmmword ptr [rdi+18h], xmm0
0x1800201ea  movq    qword ptr [rdi+28h], xmm0
0x1800201f0  jmp     short loc_18002020A
0x1800201f2  mov     r8, rbx
0x1800201f5  test    rbx, rbx
0x1800201f8  jz      short loc_18002020A
0x1800201fa  shl     r8, 3; Size
0x1800201fe  lea     rcx, [rdi+18h]; void *
0x180020202  mov     rdx, rax; Src
0x180020205  call    memmove_0
0x18002020a  mov     rcx, [rsp+0C8h+var_48]
0x180020212  xor     rcx, rsp; StackCookie
0x180020215  call    __security_check_cookie
0x18002021a  add     rsp, 98h
0x180020221  pop     r15
0x180020223  pop     r14
0x180020225  pop     rdi
0x180020226  pop     rsi
0x180020227  pop     rbp
0x180020228  pop     rbx
0x180020229  retn
```
