# wil::ActivityThreadWatcher::ActivityThreadWatcher(wil::details::IFailureCallback *,wil::details::StoredCallContextInfo const &)

- ea: `0x18004f9b8`
- end: `0x18004faaf`
- name: `??0ActivityThreadWatcher@wil@@QEAA@PEAUIFailureCallback@details@1@AEBVStoredCallContextInfo@31@@Z`
- size: `247`
- prototype: `__int64 __fastcall(wil::ActivityThreadWatcher *__hidden this, struct wil::details::IFailureCallback *, const struct wil::details::StoredCallContextInfo *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180050a80`

## callees

- `0x1800084ee`
- `0x180008554`
- `0x18000856c`
- `0x180016180`
- `0x18004f9b8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18004fa44`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18004fa44`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004fa02`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004fa02`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004fa10`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004fa10`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004fa98`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004fa98`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
wil::ActivityThreadWatcher *__fastcall wil::ActivityThreadWatcher::ActivityThreadWatcher(
        wil::ActivityThreadWatcher *this,
        struct wil::details::IFailureCallback *a2,
        const struct wil::details::StoredCallContextInfo *a3)
{
  _WORD *v5; // rbx
  __int64 v6; // rax
  SIZE_T v7; // rsi
  HANDLE ProcessHeap; // rax
  void *v9; // rax
  _QWORD *v10; // rbx
  _QWORD *Local; // rax

  *((_BYTE *)this + 24) = 0;
  *(_DWORD *)this = *(_DWORD *)a3;
  *((_QWORD *)this + 1) = *((_QWORD *)a3 + 1);
  v5 = (_WORD *)*((_QWORD *)a3 + 2);
  if ( *((_BYTE *)a3 + 24) )
  {
    v6 = -1;
    do
      ++v6;
    while ( v5[v6] );
    if ( v6 )
    {
      v7 = 2 * v6 + 2;
      ProcessHeap = GetProcessHeap();
      v9 = HeapAlloc(ProcessHeap, 0, v7);
      *((_QWORD *)this + 2) = v9;
      if ( v9 )
      {
        *((_BYTE *)this + 24) = 1;
        if ( v7 )
        {
          if ( v5 )
          {
            memcpy_0(v9, v5, v7);
          }
          else
          {
            memset_0(v9, 0, v7);
            *(_DWORD *)_o__errno() = 22;
            invalid_parameter_noinfo();
          }
        }
      }
    }
  }
  else
  {
    *((_QWORD *)this + 2) = v5;
  }
  v10 = (_QWORD *)((char *)this + 32);
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = a2;
  *((_QWORD *)this + 6) = 0;
  *((_DWORD *)this + 14) = 0;
  *((_QWORD *)this + 8) = this;
  *((_BYTE *)this + 72) = 0;
  if ( wil::details::g_pThreadFailureCallbacks )
  {
    Local = (_QWORD *)wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
                        (__int64)this,
                        1);
    *v10 = Local;
    if ( Local )
    {
      *((_QWORD *)this + 6) = *Local;
      *Local = v10;
      *((_DWORD *)this + 14) = GetCurrentThreadId();
    }
  }
  return this;
}

```

## disassembly

```asm
0x18004f9b8  push    rbx
0x18004f9ba  push    rbp
0x18004f9bb  push    rsi
0x18004f9bc  push    rdi
0x18004f9bd  push    r14
0x18004f9bf  sub     rsp, 20h
0x18004f9c3  mov     rbp, rdx
0x18004f9c6  mov     rdi, rcx
0x18004f9c9  xor     r14d, r14d
0x18004f9cc  mov     [rcx+18h], r14b
0x18004f9d0  mov     eax, [r8]
0x18004f9d3  mov     [rcx], eax
0x18004f9d5  mov     rax, [r8+8]
0x18004f9d9  mov     [rcx+8], rax
0x18004f9dd  mov     rbx, [r8+10h]
0x18004f9e1  cmp     [r8+18h], r14b
0x18004f9e5  jz      short loc_18004FA57
0x18004f9e7  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004f9eb  inc     rax
0x18004f9ee  cmp     [rbx+rax*2], r14w
0x18004f9f3  jnz     short loc_18004F9EB
0x18004f9f5  test    rax, rax
0x18004f9f8  jz      short loc_18004FA5B
0x18004f9fa  lea     rsi, ds:2[rax*2]
0x18004fa02  call    cs:__imp_GetProcessHeap
0x18004fa08  mov     rcx, rax; hHeap
0x18004fa0b  mov     r8, rsi; dwBytes
0x18004fa0e  xor     edx, edx; dwFlags
0x18004fa10  call    cs:__imp_HeapAlloc
0x18004fa16  mov     [rdi+10h], rax
0x18004fa1a  test    rax, rax
0x18004fa1d  jz      short loc_18004FA5B
0x18004fa1f  mov     byte ptr [rdi+18h], 1
0x18004fa23  test    rsi, rsi
0x18004fa26  jz      short loc_18004FA5B
0x18004fa28  mov     r8, rsi; Size
0x18004fa2b  mov     rcx, rax; void *
0x18004fa2e  test    rbx, rbx
0x18004fa31  jz      short loc_18004FA3D
0x18004fa33  mov     rdx, rbx; Src
0x18004fa36  call    memcpy_0
0x18004fa3b  jmp     short loc_18004FA5B
0x18004fa3d  xor     edx, edx; Val
0x18004fa3f  call    memset_0
0x18004fa44  call    cs:__imp__o__errno
0x18004fa4a  mov     dword ptr [rax], 16h
0x18004fa50  call    _invalid_parameter_noinfo
0x18004fa55  jmp     short loc_18004FA5B
0x18004fa57  mov     [rcx+10h], rbx
0x18004fa5b  lea     rbx, [rdi+20h]
0x18004fa5f  mov     [rbx], r14
0x18004fa62  mov     [rbx+8], rbp
0x18004fa66  mov     [rbx+10h], r14
0x18004fa6a  mov     [rbx+18h], r14d
0x18004fa6e  mov     [rbx+20h], rdi
0x18004fa72  mov     [rbx+28h], r14b
0x18004fa76  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, r14; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18004fa7d  jz      short loc_18004FAA1
0x18004fa7f  mov     dl, 1
0x18004fa81  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x18004fa86  mov     [rbx], rax
0x18004fa89  test    rax, rax
0x18004fa8c  jz      short loc_18004FAA1
0x18004fa8e  mov     rcx, [rax]
0x18004fa91  mov     [rbx+10h], rcx
0x18004fa95  mov     [rax], rbx
0x18004fa98  call    cs:__imp_GetCurrentThreadId
0x18004fa9e  mov     [rbx+18h], eax
0x18004faa1  mov     rax, rdi
0x18004faa4  add     rsp, 20h
0x18004faa8  pop     r14
0x18004faaa  pop     rdi
0x18004faab  pop     rsi
0x18004faac  pop     rbp
0x18004faad  pop     rbx
0x18004faae  retn
```
