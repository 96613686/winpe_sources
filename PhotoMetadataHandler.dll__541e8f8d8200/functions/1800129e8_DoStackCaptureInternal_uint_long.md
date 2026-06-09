# DoStackCaptureInternal(uint,long)

- ea: `0x1800129e8`
- end: `0x180012af6`
- name: `?DoStackCaptureInternal@@YAXIJ@Z`
- size: `270`
- prototype: `void __fastcall(unsigned int, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800129d8`

## callees

- `0x1800129e8`
- `0x18002629c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180012a4e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180012a4e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012a3b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012a3b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180012a94`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180012a94`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180012a9e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180012a9e`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureStackBackTrace` at `0x180012ac6`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureStackBackTrace` at `0x180012ac6`

## pseudocode

```c
void __fastcall DoStackCaptureInternal(__int64 a1, int a2)
{
  char *i; // rcx
  HANDLE ProcessHeap; // rax
  volatile int v5; // ecx
  __int64 v6; // rdx
  __int64 v7; // rbx
  __int64 v8; // rdi
  __int64 v9; // rbx
  __m128i si128; // xmm0

  if ( a2 )
  {
    for ( i = (char *)&unk_180099260; i != (char *)&unk_180099260 + 4 * (unsigned int)dword_180099258; i += 4 )
    {
      if ( a2 == *(_DWORD *)i )
        return;
    }
    if ( !_InterlockedCompareExchange(&dword_180099290, 1, 0) )
    {
      ProcessHeap = GetProcessHeap();
      qword_180099288 = (__int64)HeapAlloc(ProcessHeap, 8u, 0x2800u);
    }
    if ( qword_180099288 )
    {
      EnsureStackCaptureRegisteredWithWER();
      do
      {
        v5 = g_nCurrentStackCaptureIndex;
        v6 = (unsigned __int8)(g_nCurrentStackCaptureIndex + 1);
      }
      while ( v5 != _InterlockedCompareExchange(&g_nCurrentStackCaptureIndex, v6, g_nCurrentStackCaptureIndex) );
      v7 = qword_180099288;
      v8 = 5 * v6;
      *(_DWORD *)(qword_180099288 + 40 * v6) = a2;
      *(_DWORD *)(v7 + 8 * v8 + 4) = GetCurrentThreadId();
      *(_DWORD *)(v7 + 8 * v8 + 8) = GetTickCount();
      v9 = v7 + 8 * v8;
      *(_OWORD *)(v9 + 16) = 0;
      *(_QWORD *)(v9 + 32) = 0;
      if ( !RtlCaptureStackBackTrace(1u, 3u, (PVOID *)(v9 + 16), 0) )
      {
        si128 = _mm_load_si128((const __m128i *)&_xmm_e0e0e0e0e0e0e0e0e0e0e0e0e0e0e0e0);
        *(__m128i *)(v9 + 16) = si128;
        *(_QWORD *)(v9 + 32) = si128.m128i_i64[0];
      }
    }
  }
}

```

## disassembly

```asm
0x1800129e8  test    edx, edx
0x1800129ea  jz      locret_180012AF5
0x1800129f0  mov     [rsp+arg_8], rbx
0x1800129f5  mov     [rsp+arg_10], rbp
0x1800129fa  push    rsi
0x1800129fb  push    rdi
0x1800129fc  push    r14
0x1800129fe  sub     rsp, 20h
0x180012a02  mov     eax, cs:dword_180099258
0x180012a08  lea     rcx, unk_180099260
0x180012a0f  mov     esi, edx
0x180012a11  xor     ebp, ebp
0x180012a13  lea     rdx, [rcx+rax*4]
0x180012a17  cmp     rcx, rdx
0x180012a1a  jz      short loc_180012A2A
0x180012a1c  cmp     esi, [rcx]
0x180012a1e  jz      loc_180012AE3
0x180012a24  add     rcx, 4
0x180012a28  jmp     short loc_180012A17
0x180012a2a  xor     eax, eax
0x180012a2c  lea     r14d, [rax+1]
0x180012a30  lock cmpxchg cs:dword_180099290, r14d
0x180012a39  jnz     short loc_180012A5B
0x180012a3b  call    cs:__imp_GetProcessHeap
0x180012a41  lea     edx, [r14+7]; dwFlags
0x180012a45  mov     r8d, 2800h; dwBytes
0x180012a4b  mov     rcx, rax; hHeap
0x180012a4e  call    cs:__imp_HeapAlloc
0x180012a54  mov     cs:qword_180099288, rax
0x180012a5b  mov     rax, cs:qword_180099288
0x180012a62  test    rax, rax
0x180012a65  jz      short loc_180012AE3
0x180012a67  call    ?EnsureStackCaptureRegisteredWithWER@@YAXXZ; EnsureStackCaptureRegisteredWithWER(void)
0x180012a6c  mov     ecx, cs:?g_nCurrentStackCaptureIndex@@3JC; long volatile g_nCurrentStackCaptureIndex
0x180012a72  lea     eax, [rcx+1]
0x180012a75  movzx   edx, al
0x180012a78  mov     eax, ecx
0x180012a7a  lock cmpxchg cs:?g_nCurrentStackCaptureIndex@@3JC, edx; long volatile g_nCurrentStackCaptureIndex
0x180012a82  cmp     ecx, eax
0x180012a84  jnz     short loc_180012A6C
0x180012a86  mov     rbx, cs:qword_180099288
0x180012a8d  lea     rdi, [rdx+rdx*4]
0x180012a91  mov     [rbx+rdi*8], esi
0x180012a94  call    cs:__imp_GetCurrentThreadId
0x180012a9a  mov     [rbx+rdi*8+4], eax
0x180012a9e  call    cs:__imp_GetTickCount
0x180012aa4  mov     [rbx+rdi*8+8], eax
0x180012aa8  xorps   xmm0, xmm0
0x180012aab  lea     rbx, [rbx+rdi*8]
0x180012aaf  xor     r9d, r9d; BackTraceHash
0x180012ab2  xor     eax, eax
0x180012ab4  lea     r8, [rbx+10h]; BackTrace
0x180012ab8  movups  xmmword ptr [rbx+10h], xmm0
0x180012abc  mov     ecx, r14d; FramesToSkip
0x180012abf  mov     [rbx+20h], rax
0x180012ac3  lea     edx, [rax+3]; FramesToCapture
0x180012ac6  call    cs:__imp_RtlCaptureStackBackTrace
0x180012acc  test    ax, ax
0x180012acf  jnz     short loc_180012AE3
0x180012ad1  movdqa  xmm0, cs:__xmm@e0e0e0e0e0e0e0e0e0e0e0e0e0e0e0e0
0x180012ad9  movups  xmmword ptr [rbx+10h], xmm0
0x180012add  movq    qword ptr [rbx+20h], xmm0
0x180012ae3  mov     rbx, [rsp+38h+arg_8]
0x180012ae8  mov     rbp, [rsp+38h+arg_10]
0x180012aed  add     rsp, 20h
0x180012af1  pop     r14
0x180012af3  pop     rdi
0x180012af4  pop     rsi
0x180012af5  retn
```
