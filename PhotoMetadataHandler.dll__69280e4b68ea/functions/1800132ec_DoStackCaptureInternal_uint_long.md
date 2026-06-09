# DoStackCaptureInternal(uint,long)

- ea: `0x1800132ec`
- end: `0x1800133d1`
- name: `?DoStackCaptureInternal@@YAXIJ@Z`
- size: `229`
- prototype: `void __fastcall(unsigned int, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800132dc`

## callees

- `0x1800132ec`
- `0x1800274f8`
- `0x180027548`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013366`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013366`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180013376`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180013376`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureStackBackTrace` at `0x1800133a4`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureStackBackTrace` at `0x1800133a4`

## pseudocode

```c
void __fastcall DoStackCaptureInternal(__int64 a1, int a2)
{
  __int64 *i; // rcx
  volatile int v4; // ecx
  __int64 v5; // rdx
  __int64 v6; // rbx
  __int64 v7; // rdi
  __int64 v8; // rbx
  __m128i si128; // xmm0

  if ( a2 )
  {
    for ( i = qword_18009A350;
          i != (__int64 *)((char *)qword_18009A350 + 4 * (unsigned int)dword_18009A348);
          i = (__int64 *)((char *)i + 4) )
    {
      if ( a2 == *(_DWORD *)i )
        return;
    }
    EnsureStackCaptureAllocation();
    if ( qword_18009A378 )
    {
      EnsureStackCaptureRegisteredWithWER();
      do
      {
        v4 = g_nCurrentStackCaptureIndex;
        v5 = (unsigned __int8)(g_nCurrentStackCaptureIndex + 1);
      }
      while ( v4 != _InterlockedCompareExchange(&g_nCurrentStackCaptureIndex, v5, g_nCurrentStackCaptureIndex) );
      v6 = qword_18009A378;
      v7 = 5 * v5;
      *(_DWORD *)(qword_18009A378 + 40 * v5) = a2;
      *(_DWORD *)(v6 + 8 * v7 + 4) = GetCurrentThreadId();
      *(_DWORD *)(v6 + 8 * v7 + 8) = GetTickCount();
      v8 = v6 + 8 * v7;
      *(_OWORD *)(v8 + 16) = 0;
      *(_QWORD *)(v8 + 32) = 0;
      if ( !RtlCaptureStackBackTrace(1u, 3u, (PVOID *)(v8 + 16), 0) )
      {
        si128 = _mm_load_si128((const __m128i *)&_xmm_e0e0e0e0e0e0e0e0e0e0e0e0e0e0e0e0);
        *(__m128i *)(v8 + 16) = si128;
        *(_QWORD *)(v8 + 32) = si128.m128i_i64[0];
      }
    }
  }
}

```

## disassembly

```asm
0x1800132ec  test    edx, edx
0x1800132ee  jz      locret_1800133CF
0x1800132f4  push    rbx
0x1800132f5  push    rbp
0x1800132f6  push    rsi
0x1800132f7  push    rdi
0x1800132f8  sub     rsp, 28h
0x1800132fc  mov     eax, cs:dword_18009A348
0x180013302  lea     rcx, qword_18009A350
0x180013309  mov     esi, edx
0x18001330b  xor     ebp, ebp
0x18001330d  lea     rdx, [rcx+rax*4]
0x180013311  cmp     rcx, rdx
0x180013314  jz      short loc_180013324
0x180013316  cmp     esi, [rcx]
0x180013318  jz      loc_1800133C7
0x18001331e  add     rcx, 4
0x180013322  jmp     short loc_180013311
0x180013324  call    ?EnsureStackCaptureAllocation@@YAXXZ; EnsureStackCaptureAllocation(void)
0x180013329  mov     rax, cs:qword_18009A378
0x180013330  test    rax, rax
0x180013333  jz      loc_1800133C7
0x180013339  call    ?EnsureStackCaptureRegisteredWithWER@@YAXXZ; EnsureStackCaptureRegisteredWithWER(void)
0x18001333e  mov     ecx, cs:?g_nCurrentStackCaptureIndex@@3JC; long volatile g_nCurrentStackCaptureIndex
0x180013344  lea     eax, [rcx+1]
0x180013347  movzx   edx, al
0x18001334a  mov     eax, ecx
0x18001334c  lock cmpxchg cs:?g_nCurrentStackCaptureIndex@@3JC, edx; long volatile g_nCurrentStackCaptureIndex
0x180013354  cmp     ecx, eax
0x180013356  jnz     short loc_18001333E
0x180013358  mov     rbx, cs:qword_18009A378
0x18001335f  lea     rdi, [rdx+rdx*4]
0x180013363  mov     [rbx+rdi*8], esi
0x180013366  call    cs:__imp_GetCurrentThreadId
0x18001336d  nop     dword ptr [rax+rax+00h]
0x180013372  mov     [rbx+rdi*8+4], eax
0x180013376  call    cs:__imp_GetTickCount
0x18001337d  nop     dword ptr [rax+rax+00h]
0x180013382  mov     [rbx+rdi*8+8], eax
0x180013386  xorps   xmm0, xmm0
0x180013389  lea     rbx, [rbx+rdi*8]
0x18001338d  xor     r9d, r9d; BackTraceHash
0x180013390  xor     eax, eax
0x180013392  lea     r8, [rbx+10h]; BackTrace
0x180013396  movups  xmmword ptr [rbx+10h], xmm0
0x18001339a  mov     [rbx+20h], rax
0x18001339e  lea     edx, [rax+3]; FramesToCapture
0x1800133a1  lea     ecx, [rax+1]; FramesToSkip
0x1800133a4  call    cs:__imp_RtlCaptureStackBackTrace
0x1800133ab  nop     dword ptr [rax+rax+00h]
0x1800133b0  test    ax, ax
0x1800133b3  jnz     short loc_1800133C7
0x1800133b5  movdqa  xmm0, cs:__xmm@e0e0e0e0e0e0e0e0e0e0e0e0e0e0e0e0
0x1800133bd  movups  xmmword ptr [rbx+10h], xmm0
0x1800133c1  movq    qword ptr [rbx+20h], xmm0
0x1800133c7  add     rsp, 28h
0x1800133cb  pop     rdi
0x1800133cc  pop     rsi
0x1800133cd  pop     rbp
0x1800133ce  pop     rbx
0x1800133cf  retn
```
