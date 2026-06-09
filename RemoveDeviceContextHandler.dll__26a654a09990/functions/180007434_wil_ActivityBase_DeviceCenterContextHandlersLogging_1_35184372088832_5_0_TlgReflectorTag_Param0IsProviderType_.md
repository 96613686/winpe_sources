# wil::ActivityBase<DeviceCenterContextHandlersLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ContinueOnCurrentThread(void)

- ea: `0x180007434`
- end: `0x180007541`
- name: `?ContinueOnCurrentThread@?$ActivityBase@VDeviceCenterContextHandlersLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA?AVActivityThreadWatcher@2@XZ`
- size: `269`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180007a10`
- `0x18000b5dc`

## callees

- `0x1800042fc`
- `0x180007434`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800074bd`
- `msvcrt!memcpy_s` at `0x1800074bd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007490`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007490`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000749e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000749e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007506`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007506`

## pseudocode

```c
__int64 __fastcall wil::ActivityBase<DeviceCenterContextHandlersLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ContinueOnCurrentThread(
        __int64 a1,
        __int64 a2)
{
  int *v3; // rdx
  int v5; // eax
  _WORD *v6; // rdi
  __int64 v7; // rax
  __int64 v8; // rsi
  HANDLE ProcessHeap; // rax
  void *v10; // rax
  _QWORD *v11; // rdi
  _QWORD *Local; // rax

  v3 = *(int **)(a1 + 272);
  v5 = *v3;
  *(_BYTE *)(a2 + 24) = 0;
  if ( v5 == 1 )
  {
    *(_DWORD *)a2 = v3[10];
    *(_QWORD *)(a2 + 8) = *((_QWORD *)v3 + 6);
    v6 = (_WORD *)*((_QWORD *)v3 + 7);
    if ( *((_BYTE *)v3 + 64) )
    {
      v7 = -1;
      do
        ++v7;
      while ( v6[v7] );
      if ( v7 )
      {
        v8 = 2 * v7 + 2;
        ProcessHeap = GetProcessHeap();
        v10 = HeapAlloc(ProcessHeap, 0, v8);
        *(_QWORD *)(a2 + 16) = v10;
        if ( v10 )
        {
          *(_BYTE *)(a2 + 24) = 1;
          memcpy_s(v10, v8, v6, v8);
        }
      }
    }
    else
    {
      *(_QWORD *)(a2 + 16) = v6;
    }
    v11 = (_QWORD *)(a2 + 32);
    *(_QWORD *)(a2 + 32) = 0;
    *(_QWORD *)(a2 + 40) = a1;
    *(_QWORD *)(a2 + 48) = 0;
    *(_DWORD *)(a2 + 56) = 0;
    *(_QWORD *)(a2 + 64) = a2;
    *(_BYTE *)(a2 + 72) = 0;
    if ( wil::details::g_pThreadFailureCallbacks )
    {
      Local = (_QWORD *)wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
                          a1,
                          1);
      *v11 = Local;
      if ( Local )
      {
        *(_QWORD *)(a2 + 48) = *Local;
        *Local = v11;
        *(_DWORD *)(a2 + 56) = GetCurrentThreadId();
      }
    }
  }
  else
  {
    *(_OWORD *)a2 = 0;
    *(_OWORD *)(a2 + 16) = 0;
    *(_QWORD *)(a2 + 32) = 0;
    *(_QWORD *)(a2 + 40) = 0;
    *(_QWORD *)(a2 + 48) = 0;
    *(_DWORD *)(a2 + 56) = 0;
    *(_QWORD *)(a2 + 64) = 0;
    *(_BYTE *)(a2 + 72) = 0;
  }
  return a2;
}

```

## disassembly

```asm
0x180007434  push    rbx
0x180007436  push    rbp
0x180007437  push    rsi
0x180007438  push    rdi
0x180007439  push    r14
0x18000743b  sub     rsp, 20h
0x18000743f  mov     rbx, rdx
0x180007442  xor     r14d, r14d
0x180007445  mov     rdx, [rcx+110h]
0x18000744c  mov     rbp, rcx
0x18000744f  mov     eax, [rdx]
0x180007451  mov     [rbx+18h], r14b
0x180007455  cmp     eax, 1
0x180007458  jnz     loc_180007511
0x18000745e  mov     eax, [rdx+28h]
0x180007461  mov     [rbx], eax
0x180007463  mov     rax, [rdx+30h]
0x180007467  mov     [rbx+8], rax
0x18000746b  mov     rdi, [rdx+38h]
0x18000746f  cmp     [rdx+40h], r14b
0x180007473  jz      short loc_1800074C5
0x180007475  or      rax, 0FFFFFFFFFFFFFFFFh
0x180007479  inc     rax
0x18000747c  cmp     [rdi+rax*2], r14w
0x180007481  jnz     short loc_180007479
0x180007483  test    rax, rax
0x180007486  jz      short loc_1800074C9
0x180007488  lea     rsi, ds:2[rax*2]
0x180007490  call    cs:__imp_GetProcessHeap
0x180007496  mov     r8, rsi; dwBytes
0x180007499  xor     edx, edx; dwFlags
0x18000749b  mov     rcx, rax; hHeap
0x18000749e  call    cs:__imp_HeapAlloc
0x1800074a4  mov     [rbx+10h], rax
0x1800074a8  test    rax, rax
0x1800074ab  jz      short loc_1800074C9
0x1800074ad  mov     r9, rsi; SourceSize
0x1800074b0  mov     byte ptr [rbx+18h], 1
0x1800074b4  mov     r8, rdi; Source
0x1800074b7  mov     rdx, rsi; DestinationSize
0x1800074ba  mov     rcx, rax; Destination
0x1800074bd  call    cs:__imp_memcpy_s
0x1800074c3  jmp     short loc_1800074C9
0x1800074c5  mov     [rbx+10h], rdi
0x1800074c9  lea     rdi, [rbx+20h]
0x1800074cd  mov     [rdi], r14
0x1800074d0  mov     [rdi+8], rbp
0x1800074d4  mov     [rdi+10h], r14
0x1800074d8  mov     [rdi+18h], r14d
0x1800074dc  mov     [rdi+20h], rbx
0x1800074e0  mov     [rdi+28h], r14b
0x1800074e4  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, r14; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800074eb  jz      short loc_180007533
0x1800074ed  mov     dl, 1
0x1800074ef  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x1800074f4  mov     [rdi], rax
0x1800074f7  test    rax, rax
0x1800074fa  jz      short loc_180007533
0x1800074fc  mov     rcx, [rax]
0x1800074ff  mov     [rdi+10h], rcx
0x180007503  mov     [rax], rdi
0x180007506  call    cs:__imp_GetCurrentThreadId
0x18000750c  mov     [rdi+18h], eax
0x18000750f  jmp     short loc_180007533
0x180007511  xorps   xmm0, xmm0
0x180007514  movups  xmmword ptr [rbx], xmm0
0x180007517  movups  xmmword ptr [rbx+10h], xmm0
0x18000751b  mov     [rbx+20h], r14
0x18000751f  mov     [rbx+28h], r14
0x180007523  mov     [rbx+30h], r14
0x180007527  mov     [rbx+38h], r14d
0x18000752b  mov     [rbx+40h], r14
0x18000752f  mov     [rbx+48h], r14b
0x180007533  mov     rax, rbx
0x180007536  add     rsp, 20h
0x18000753a  pop     r14
0x18000753c  pop     rdi
0x18000753d  pop     rsi
0x18000753e  pop     rbp
0x18000753f  pop     rbx
0x180007540  retn
```
