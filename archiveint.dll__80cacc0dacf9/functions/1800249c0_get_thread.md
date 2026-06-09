# get_thread

- ea: `0x1800249c0`
- end: `0x180024c5a`
- name: `get_thread`
- size: `666`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180025060`

## callees

- `0x180021a90`
- `0x180022090`
- `0x1800249c0`
- `0x18002be10`
- `0x18002bfd0`
- `0x180031f80`
- `0x180032130`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x180024b27`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x180024b27`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180024aac`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180024aac`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180024a56`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180024c16`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180024a56`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180024c16`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180024a28`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180024b58`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180024a28`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180024b58`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180024c34`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180024c34`
- `api-ms-win-core-synch-l1-2-0!WakeConditionVariable` at `0x180024c02`
- `api-ms-win-core-synch-l1-2-0!WakeConditionVariable` at `0x180024c02`
- `api-ms-win-core-synch-l1-2-0!InitializeConditionVariable` at `0x180024ab9`
- `api-ms-win-core-synch-l1-2-0!InitializeConditionVariable` at `0x180024ab9`

## pseudocode

```c
__int64 __fastcall get_thread(__int64 a1, __int64 a2)
{
  __int64 result; // rax
  __int64 v5; // rax
  __int64 v6; // rax
  __int64 v7; // rbx
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rbx
  _OWORD *v11; // rax
  RTL_CONDITION_VARIABLE *v12; // rcx

  if ( *(_DWORD *)(a1 + 392) >= *(_DWORD *)(a1 + 400) )
    return 0;
  result = lzma_outq_prealloc_buf(a1 + 344, a2, *(_QWORD *)(a1 + 408));
  if ( !(_DWORD)result )
  {
    if ( *(_QWORD *)(a1 + 96) != -1 || (result = lzma_filters_copy(a1 + 16, a1 + 96, a2), !(_DWORD)result) )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 472));
      v5 = *(_QWORD *)(a1 + 440);
      if ( v5 )
      {
        *(_QWORD *)(a1 + 448) = v5;
        *(_QWORD *)(a1 + 440) = *(_QWORD *)(v5 + 432);
      }
      LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 472));
      if ( *(_QWORD *)(a1 + 448) )
        goto LABEL_12;
      v6 = *(unsigned int *)(a1 + 436);
      if ( (_DWORD)v6 == *(_DWORD *)(a1 + 432) )
        return 0;
      v7 = *(_QWORD *)(a1 + 424) + 496 * v6;
      v8 = lzma_alloc(*(_QWORD *)(a1 + 8), a2);
      *(_QWORD *)(v7 + 8) = v8;
      if ( v8 )
      {
        InitializeCriticalSection((LPCRITICAL_SECTION)(v7 + 440));
        InitializeConditionVariable((PCONDITION_VARIABLE)(v7 + 480));
        *(_DWORD *)v7 = 0;
        *(_QWORD *)(v7 + 40) = a2;
        *(_QWORD *)(v7 + 32) = a1;
        *(_QWORD *)(v7 + 48) = 0;
        *(_QWORD *)(v7 + 56) = 0;
        *(_QWORD *)(v7 + 64) = 0;
        *(_QWORD *)(v7 + 72) = -1;
        *(_QWORD *)(v7 + 80) = 0;
        *(_QWORD *)(v7 + 88) = 0;
        *(_QWORD *)(v7 + 96) = 0;
        *(_QWORD *)(v7 + 104) = 0;
        *(_QWORD *)(v7 + 112) = 0;
        *(_QWORD *)(v7 + 120) = 0;
        *(_QWORD *)(v7 + 128) = 0;
        *(_QWORD *)(v7 + 136) = 0;
        *(_QWORD *)(v7 + 352) = -1;
        v9 = _o__beginthreadex(0, 0, worker_start, v7, 0, 0);
        if ( v9 )
        {
          *(_QWORD *)(v7 + 488) = v9;
          ++*(_DWORD *)(a1 + 436);
          *(_QWORD *)(a1 + 448) = v7;
LABEL_12:
          EnterCriticalSection((LPCRITICAL_SECTION)(*(_QWORD *)(a1 + 448) + 440LL));
          **(_DWORD **)(a1 + 448) = 1;
          *(_QWORD *)(*(_QWORD *)(a1 + 448) + 16LL) = 0;
          v10 = *(_QWORD *)(a1 + 448);
          *(_QWORD *)(v10 + 24) = lzma_outq_get_buf(a1 + 344, 0);
          lzma_filters_free(*(_QWORD *)(a1 + 448) + 352LL, a2);
          v11 = *(_OWORD **)(a1 + 448);
          v11[22] = *(_OWORD *)(a1 + 96);
          v11[23] = *(_OWORD *)(a1 + 112);
          v11[24] = *(_OWORD *)(a1 + 128);
          v11[25] = *(_OWORD *)(a1 + 144);
          v11[26] = *(_OWORD *)(a1 + 160);
          v12 = (RTL_CONDITION_VARIABLE *)(*(_QWORD *)(a1 + 448) + 480LL);
          *(_QWORD *)(a1 + 96) = -1;
          WakeConditionVariable(v12);
          LeaveCriticalSection((LPCRITICAL_SECTION)(*(_QWORD *)(a1 + 448) + 440LL));
          return 0;
        }
        DeleteCriticalSection((LPCRITICAL_SECTION)(v7 + 440));
        lzma_free(*(_QWORD *)(v7 + 8), a2);
      }
      return 5;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800249c0  push    rbx
0x1800249c2  push    rbp
0x1800249c3  push    rsi
0x1800249c4  push    rdi
0x1800249c5  push    r12
0x1800249c7  push    r14
0x1800249c9  push    r15
0x1800249cb  sub     rsp, 30h
0x1800249cf  mov     eax, [rcx+190h]
0x1800249d5  mov     rsi, rdx
0x1800249d8  mov     rdi, rcx
0x1800249db  cmp     [rcx+188h], eax
0x1800249e1  jnb     loc_180024C1C
0x1800249e7  mov     r8, [rcx+198h]
0x1800249ee  add     rcx, 158h
0x1800249f5  call    lzma_outq_prealloc_buf
0x1800249fa  test    eax, eax
0x1800249fc  jnz     loc_180024C1E
0x180024a02  cmp     qword ptr [rdi+60h], 0FFFFFFFFFFFFFFFFh
0x180024a07  jnz     short loc_180024A21
0x180024a09  lea     rcx, [rdi+10h]
0x180024a0d  mov     r8, rsi
0x180024a10  lea     rdx, [rdi+60h]
0x180024a14  call    lzma_filters_copy
0x180024a19  test    eax, eax
0x180024a1b  jnz     loc_180024C1E
0x180024a21  lea     rcx, [rdi+1D8h]; lpCriticalSection
0x180024a28  call    cs:__imp_EnterCriticalSection
0x180024a2e  mov     rax, [rdi+1B8h]
0x180024a35  test    rax, rax
0x180024a38  jz      short loc_180024A4F
0x180024a3a  mov     [rdi+1C0h], rax
0x180024a41  mov     rax, [rax+1B0h]
0x180024a48  mov     [rdi+1B8h], rax
0x180024a4f  lea     rcx, [rdi+1D8h]; lpCriticalSection
0x180024a56  call    cs:__imp_LeaveCriticalSection
0x180024a5c  xor     r12d, r12d
0x180024a5f  cmp     [rdi+1C0h], r12
0x180024a66  jnz     loc_180024B4A
0x180024a6c  mov     eax, [rdi+1B4h]
0x180024a72  cmp     eax, [rdi+1B0h]
0x180024a78  jz      loc_180024C1C
0x180024a7e  mov     rcx, [rdi+8]
0x180024a82  mov     rdx, rsi
0x180024a85  imul    rbx, rax, 1F0h
0x180024a8c  add     rbx, [rdi+1A8h]
0x180024a93  call    lzma_alloc
0x180024a98  mov     [rbx+8], rax
0x180024a9c  test    rax, rax
0x180024a9f  jz      loc_180024C46
0x180024aa5  lea     rcx, [rbx+1B8h]; lpCriticalSection
0x180024aac  call    cs:__imp_InitializeCriticalSection
0x180024ab2  lea     rcx, [rbx+1E0h]; ConditionVariable
0x180024ab9  call    cs:__imp_InitializeConditionVariable
0x180024abf  mov     [rbx], r12d
0x180024ac2  lea     r8, worker_start
0x180024ac9  mov     [rbx+28h], rsi
0x180024acd  mov     r9, rbx
0x180024ad0  mov     [rbx+20h], rdi
0x180024ad4  xor     edx, edx
0x180024ad6  mov     [rbx+30h], r12
0x180024ada  xor     ecx, ecx
0x180024adc  mov     [rbx+38h], r12
0x180024ae0  mov     [rbx+40h], r12
0x180024ae4  mov     qword ptr [rbx+48h], 0FFFFFFFFFFFFFFFFh
0x180024aec  mov     [rbx+50h], r12
0x180024af0  mov     [rbx+58h], r12
0x180024af4  mov     [rbx+60h], r12
0x180024af8  mov     [rbx+68h], r12
0x180024afc  mov     [rbx+70h], r12
0x180024b00  mov     [rbx+78h], r12
0x180024b04  mov     [rbx+80h], r12
0x180024b0b  mov     [rbx+88h], r12
0x180024b12  mov     [rsp+68h+var_40], r12
0x180024b17  mov     qword ptr [rbx+160h], 0FFFFFFFFFFFFFFFFh
0x180024b22  mov     [rsp+68h+var_48], r12d
0x180024b27  call    cs:__imp__o__beginthreadex
0x180024b2d  test    rax, rax
0x180024b30  jz      loc_180024C2D
0x180024b36  mov     [rbx+1E8h], rax
0x180024b3d  inc     dword ptr [rdi+1B4h]
0x180024b43  mov     [rdi+1C0h], rbx
0x180024b4a  mov     rcx, [rdi+1C0h]
0x180024b51  add     rcx, 1B8h; lpCriticalSection
0x180024b58  call    cs:__imp_EnterCriticalSection
0x180024b5e  mov     rax, [rdi+1C0h]
0x180024b65  lea     rcx, [rdi+158h]
0x180024b6c  xor     edx, edx
0x180024b6e  mov     dword ptr [rax], 1
0x180024b74  mov     rax, [rdi+1C0h]
0x180024b7b  mov     [rax+10h], r12
0x180024b7f  mov     rbx, [rdi+1C0h]
0x180024b86  call    lzma_outq_get_buf
0x180024b8b  mov     [rbx+18h], rax
0x180024b8f  mov     rdx, rsi
0x180024b92  mov     rcx, [rdi+1C0h]
0x180024b99  add     rcx, 160h
0x180024ba0  call    lzma_filters_free
0x180024ba5  movups  xmm0, xmmword ptr [rdi+60h]
0x180024ba9  mov     rax, [rdi+1C0h]
0x180024bb0  movups  xmmword ptr [rax+160h], xmm0
0x180024bb7  movups  xmm1, xmmword ptr [rdi+70h]
0x180024bbb  movups  xmmword ptr [rax+170h], xmm1
0x180024bc2  movups  xmm0, xmmword ptr [rdi+80h]
0x180024bc9  movups  xmmword ptr [rax+180h], xmm0
0x180024bd0  movups  xmm1, xmmword ptr [rdi+90h]
0x180024bd7  movups  xmmword ptr [rax+190h], xmm1
0x180024bde  movups  xmm0, xmmword ptr [rdi+0A0h]
0x180024be5  movups  xmmword ptr [rax+1A0h], xmm0
0x180024bec  mov     rcx, [rdi+1C0h]
0x180024bf3  add     rcx, 1E0h; ConditionVariable
0x180024bfa  mov     qword ptr [rdi+60h], 0FFFFFFFFFFFFFFFFh
0x180024c02  call    cs:__imp_WakeConditionVariable
0x180024c08  mov     rcx, [rdi+1C0h]
0x180024c0f  add     rcx, 1B8h; lpCriticalSection
0x180024c16  call    cs:__imp_LeaveCriticalSection
0x180024c1c  xor     eax, eax
0x180024c1e  add     rsp, 30h
0x180024c22  pop     r15
0x180024c24  pop     r14
0x180024c26  pop     r12
0x180024c28  pop     rdi
0x180024c29  pop     rsi
0x180024c2a  pop     rbp
0x180024c2b  pop     rbx
0x180024c2c  retn
0x180024c2d  lea     rcx, [rbx+1B8h]; lpCriticalSection
0x180024c34  call    cs:__imp_DeleteCriticalSection
0x180024c3a  mov     rcx, [rbx+8]
0x180024c3e  mov     rdx, rsi
0x180024c41  call    lzma_free
0x180024c46  mov     eax, 5
0x180024c4b  add     rsp, 30h
0x180024c4f  pop     r15
0x180024c51  pop     r14
0x180024c53  pop     r12
0x180024c55  pop     rdi
0x180024c56  pop     rsi
0x180024c57  pop     rbp
0x180024c58  pop     rbx
0x180024c59  retn
```
