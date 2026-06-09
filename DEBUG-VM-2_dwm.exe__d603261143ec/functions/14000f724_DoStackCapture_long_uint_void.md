# DoStackCapture(long,uint,void *)

- ea: `0x14000f724`
- end: `0x14000f891`
- name: `?DoStackCapture@@YAXJIPEAX@Z`
- size: `365`
- prototype: `void __fastcall(int, unsigned int, void *)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140002e6c`
- `0x14000f8b8`

## callees

- `0x140005530`
- `0x1400061b8`
- `0x14000f6d0`
- `0x14000f6e0`
- `0x14000f724`
- `0x14000f954`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000f7aa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000f7aa`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x14000f7bf`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x14000f7bf`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureStackBackTrace` at `0x14000f80c`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureStackBackTrace` at `0x14000f80c`

## pseudocode

```c
void __fastcall DoStackCapture(int a1, int a2, void *a3)
{
  volatile int v5; // ecx
  __int64 v6; // rdx
  __int64 v7; // rbx
  DWORD CurrentThreadId; // eax
  struct StackCaptureFrame *v9; // rcx
  char *v10; // rbx
  PVOID *v11; // rdi
  void *v12; // rax
  __m128i si128; // xmm0
  void *v14; // [rsp+20h] [rbp-98h] BYREF
  PVOID BackTrace[12]; // [rsp+30h] [rbp-88h] BYREF

  v14 = a3;
  if ( !_InterlockedCompareExchange(&dword_140018658, 1, 0) )
  {
    MilWerRegisterMemoryBlock(&g_StackCaptureFrames, 0x3800u);
    MilWerRegisterMemoryBlock((const void *)&g_nCurrentStackCaptureIndex, 4u);
  }
  do
  {
    v5 = g_nCurrentStackCaptureIndex;
    v6 = (unsigned __int8)(g_nCurrentStackCaptureIndex + 1);
  }
  while ( v5 != _InterlockedCompareExchange(&g_nCurrentStackCaptureIndex, v6, g_nCurrentStackCaptureIndex) );
  v7 = 56 * v6;
  *((_DWORD *)&g_StackCaptureFrames + 14 * v6) = a1;
  CurrentThreadId = GetCurrentThreadId();
  *(_DWORD *)((char *)&g_StackCaptureFrames + v7 + 8) = a2;
  *(_DWORD *)((char *)&g_StackCaptureFrames + v7 + 4) = CurrentThreadId;
  QueryPerformanceCounter((LARGE_INTEGER *)((char *)&g_StackCaptureFrames + v7 + 16));
  if ( g_pFrameId )
    v9 = (struct StackCaptureFrame *)*g_pFrameId;
  else
    v9 = 0;
  *(struct StackCaptureFrame near **)((char *)&g_StackCaptureFrames + v7 + 48) = v9;
  v10 = (char *)&g_StackCaptureFrames + v7;
  *(_OWORD *)(v10 + 24) = 0;
  *((_QWORD *)v10 + 5) = 0;
  memset_0(BackTrace, 0, 0x58u);
  v11 = &BackTrace[RtlCaptureStackBackTrace(1u, 0xBu, BackTrace, 0)];
  v12 = (void *)std::_Find_unchecked<void * *,void *>(BackTrace, v11, &v14);
  if ( ((char *)v11 - (_BYTE *)v12) >> 3 )
  {
    std::copy_n<void * *,unsigned __int64,void * *>(v12);
  }
  else
  {
    si128 = _mm_load_si128((const __m128i *)&_xmm_e0e0e0e0e0e0e0e0e0e0e0e0e0e0e0e0);
    *(__m128i *)(v10 + 24) = si128;
    *((_QWORD *)v10 + 5) = si128.m128i_i64[0];
  }
}

```

## disassembly

```asm
0x14000f724  mov     [rsp+arg_0], rbx
0x14000f729  mov     [rsp+arg_8], rbp
0x14000f72e  push    rsi
0x14000f72f  push    rdi
0x14000f730  push    r14
0x14000f732  sub     rsp, 0A0h
0x14000f739  mov     rax, cs:__security_cookie
0x14000f740  xor     rax, rsp
0x14000f743  mov     [rsp+0B8h+var_28], rax
0x14000f74b  xor     eax, eax
0x14000f74d  mov     [rsp+0B8h+var_98], r8
0x14000f752  mov     edi, edx
0x14000f754  lea     rbp, ?g_StackCaptureFrames@@3PAUStackCaptureFrame@@A; StackCaptureFrame near * g_StackCaptureFrames
0x14000f75b  mov     esi, ecx
0x14000f75d  lea     r14d, [rax+1]
0x14000f761  lock cmpxchg cs:dword_140018658, r14d
0x14000f76a  jnz     short loc_14000F789
0x14000f76c  mov     edx, 3800h; unsigned int
0x14000f771  mov     rcx, rbp; void *
0x14000f774  call    ?MilWerRegisterMemoryBlock@@YAXPEBXI@Z; MilWerRegisterMemoryBlock(void const *,uint)
0x14000f779  lea     edx, [r14+3]; unsigned int
0x14000f77d  lea     rcx, ?g_nCurrentStackCaptureIndex@@3JC; void *
0x14000f784  call    ?MilWerRegisterMemoryBlock@@YAXPEBXI@Z; MilWerRegisterMemoryBlock(void const *,uint)
0x14000f789  mov     ecx, cs:?g_nCurrentStackCaptureIndex@@3JC; long volatile g_nCurrentStackCaptureIndex
0x14000f78f  lea     eax, [rcx+1]
0x14000f792  movzx   edx, al
0x14000f795  mov     eax, ecx
0x14000f797  lock cmpxchg cs:?g_nCurrentStackCaptureIndex@@3JC, edx; long volatile g_nCurrentStackCaptureIndex
0x14000f79f  cmp     ecx, eax
0x14000f7a1  jnz     short loc_14000F789
0x14000f7a3  imul    rbx, rdx, 38h ; '8'
0x14000f7a7  mov     [rbx+rbp], esi
0x14000f7aa  call    cs:__imp_GetCurrentThreadId
0x14000f7b0  lea     rcx, [rbp+10h]
0x14000f7b4  mov     [rbx+rbp+8], edi
0x14000f7b8  add     rcx, rbx; lpPerformanceCount
0x14000f7bb  mov     [rbx+rbp+4], eax
0x14000f7bf  call    cs:__imp_QueryPerformanceCounter
0x14000f7c5  mov     rax, cs:?g_pFrameId@@3PEA_KEA; unsigned __int64 * g_pFrameId
0x14000f7cc  test    rax, rax
0x14000f7cf  jz      short loc_14000F7D6
0x14000f7d1  mov     rcx, [rax]
0x14000f7d4  jmp     short loc_14000F7D8
0x14000f7d6  xor     ecx, ecx
0x14000f7d8  mov     [rbx+rbp+30h], rcx
0x14000f7dd  xor     eax, eax
0x14000f7df  add     rbx, rbp
0x14000f7e2  lea     rcx, [rsp+0B8h+BackTrace]; void *
0x14000f7e7  xorps   xmm0, xmm0
0x14000f7ea  xor     edx, edx; Val
0x14000f7ec  lea     r8d, [rax+58h]; Size
0x14000f7f0  movups  xmmword ptr [rbx+18h], xmm0
0x14000f7f4  mov     [rbx+28h], rax
0x14000f7f8  call    memset_0
0x14000f7fd  xor     r9d, r9d; BackTraceHash
0x14000f800  lea     r8, [rsp+0B8h+BackTrace]; BackTrace
0x14000f805  mov     ecx, r14d; FramesToSkip
0x14000f808  lea     edx, [r9+0Bh]; FramesToCapture
0x14000f80c  call    cs:__imp_RtlCaptureStackBackTrace
0x14000f812  movzx   eax, ax
0x14000f815  lea     rdi, [rsp+0B8h+BackTrace]
0x14000f81a  lea     r8, [rsp+0B8h+var_98]
0x14000f81f  lea     rcx, [rsp+0B8h+BackTrace]
0x14000f824  lea     rdi, [rdi+rax*8]
0x14000f828  mov     rdx, rdi
0x14000f82b  call    ??$_Find_unchecked@PEAPEAXPEAX@std@@YAPEAPEAXPEAPEAXQEAPEAXAEBQEAX@Z; std::_Find_unchecked<void * *,void *>(void * *,void * * const,void * const &)
0x14000f830  sub     rdi, rax
0x14000f833  mov     edx, 3
0x14000f838  sar     rdi, 3
0x14000f83c  cmp     rdi, rdx
0x14000f83f  ja      short loc_14000F85D
0x14000f841  test    rdi, rdi
0x14000f844  jnz     short loc_14000F85A
0x14000f846  movdqa  xmm0, cs:__xmm@e0e0e0e0e0e0e0e0e0e0e0e0e0e0e0e0
0x14000f84e  movups  xmmword ptr [rbx+18h], xmm0
0x14000f852  movq    qword ptr [rbx+28h], xmm0
0x14000f858  jmp     short loc_14000F869
0x14000f85a  mov     rdx, rdi
0x14000f85d  lea     r8, [rbx+18h]
0x14000f861  mov     rcx, rax; Src
0x14000f864  call    ??$copy_n@PEAPEAX_KPEAPEAX@std@@YAPEAPEAXPEAPEAX_K0@Z; std::copy_n<void * *,unsigned __int64,void * *>(void * *,unsigned __int64,void * *)
0x14000f869  mov     rcx, [rsp+0B8h+var_28]
0x14000f871  xor     rcx, rsp; StackCookie
0x14000f874  call    __security_check_cookie
0x14000f879  lea     r11, [rsp+0B8h+var_18]
0x14000f881  mov     rbx, [r11+20h]
0x14000f885  mov     rbp, [r11+28h]
0x14000f889  mov     rsp, r11
0x14000f88c  pop     r14
0x14000f88e  pop     rdi
0x14000f88f  pop     rsi
0x14000f890  retn
```
