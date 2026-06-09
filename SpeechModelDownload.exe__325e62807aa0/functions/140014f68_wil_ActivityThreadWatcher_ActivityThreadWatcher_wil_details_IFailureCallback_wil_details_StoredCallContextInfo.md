# wil::ActivityThreadWatcher::ActivityThreadWatcher(wil::details::IFailureCallback *,wil::details::StoredCallContextInfo const &)

- ea: `0x140014f68`
- end: `0x14001505f`
- name: `??0ActivityThreadWatcher@wil@@QEAA@PEAUIFailureCallback@details@1@AEBVStoredCallContextInfo@31@@Z`
- size: `247`
- prototype: `wil::ActivityThreadWatcher *__fastcall(wil::ActivityThreadWatcher *this, struct wil::details::IFailureCallback *, const struct wil::details::StoredCallContextInfo *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1400161c0`

## callees

- `0x140003026`
- `0x1400030dc`
- `0x1400068f0`
- `0x140014f68`
- `0x14001bb9c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140014ff4`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140014ff4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140014fc0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140014fc0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140014fb2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140014fb2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140015048`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140015048`

## pseudocode

```c
wil::ActivityThreadWatcher *__fastcall wil::ActivityThreadWatcher::ActivityThreadWatcher(
        wil::ActivityThreadWatcher *this,
        struct wil::details::IFailureCallback *a2,
        const struct wil::details::StoredCallContextInfo *a3)
{
  struct wil::details::IFailureCallback *v3; // rbp
  _WORD *v5; // rbx
  __int64 v6; // rax
  SIZE_T v7; // rsi
  HANDLE ProcessHeap; // rax
  void *v9; // rax
  _QWORD *v10; // rbx
  _QWORD *Local; // rax

  v3 = a2;
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
  *((_QWORD *)this + 5) = v3;
  *((_QWORD *)this + 6) = 0;
  *((_DWORD *)this + 14) = 0;
  *((_QWORD *)this + 8) = this;
  *((_BYTE *)this + 72) = 0;
  if ( wil::details::g_pThreadFailureCallbacks )
  {
    LOBYTE(a2) = 1;
    Local = (_QWORD *)wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
                        this,
                        a2);
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
0x140014f68  push    rbx
0x140014f6a  push    rbp
0x140014f6b  push    rsi
0x140014f6c  push    rdi
0x140014f6d  push    r14
0x140014f6f  sub     rsp, 20h
0x140014f73  mov     rbp, rdx
0x140014f76  mov     rdi, rcx
0x140014f79  xor     r14d, r14d
0x140014f7c  mov     [rcx+18h], r14b
0x140014f80  mov     eax, [r8]
0x140014f83  mov     [rcx], eax
0x140014f85  mov     rax, [r8+8]
0x140014f89  mov     [rcx+8], rax
0x140014f8d  mov     rbx, [r8+10h]
0x140014f91  cmp     [r8+18h], r14b
0x140014f95  jz      short loc_140015007
0x140014f97  or      rax, 0FFFFFFFFFFFFFFFFh
0x140014f9b  inc     rax
0x140014f9e  cmp     [rbx+rax*2], r14w
0x140014fa3  jnz     short loc_140014F9B
0x140014fa5  test    rax, rax
0x140014fa8  jz      short loc_14001500B
0x140014faa  lea     rsi, ds:2[rax*2]
0x140014fb2  call    cs:__imp_GetProcessHeap
0x140014fb8  mov     rcx, rax; hHeap
0x140014fbb  mov     r8, rsi; dwBytes
0x140014fbe  xor     edx, edx; dwFlags
0x140014fc0  call    cs:__imp_HeapAlloc
0x140014fc6  mov     [rdi+10h], rax
0x140014fca  test    rax, rax
0x140014fcd  jz      short loc_14001500B
0x140014fcf  mov     byte ptr [rdi+18h], 1
0x140014fd3  test    rsi, rsi
0x140014fd6  jz      short loc_14001500B
0x140014fd8  mov     r8, rsi; Size
0x140014fdb  mov     rcx, rax; void *
0x140014fde  test    rbx, rbx
0x140014fe1  jz      short loc_140014FED
0x140014fe3  mov     rdx, rbx; Src
0x140014fe6  call    memcpy_0
0x140014feb  jmp     short loc_14001500B
0x140014fed  xor     edx, edx; Val
0x140014fef  call    memset_0
0x140014ff4  call    cs:__imp__o__errno
0x140014ffa  mov     dword ptr [rax], 16h
0x140015000  call    _invalid_parameter_noinfo
0x140015005  jmp     short loc_14001500B
0x140015007  mov     [rcx+10h], rbx
0x14001500b  lea     rbx, [rdi+20h]
0x14001500f  mov     [rbx], r14
0x140015012  mov     [rbx+8], rbp
0x140015016  mov     [rbx+10h], r14
0x14001501a  mov     [rbx+18h], r14d
0x14001501e  mov     [rbx+20h], rdi
0x140015022  mov     [rbx+28h], r14b
0x140015026  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, r14; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x14001502d  jz      short loc_140015051
0x14001502f  mov     dl, 1
0x140015031  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x140015036  mov     [rbx], rax
0x140015039  test    rax, rax
0x14001503c  jz      short loc_140015051
0x14001503e  mov     rcx, [rax]
0x140015041  mov     [rbx+10h], rcx
0x140015045  mov     [rax], rbx
0x140015048  call    cs:__imp_GetCurrentThreadId
0x14001504e  mov     [rbx+18h], eax
0x140015051  mov     rax, rdi
0x140015054  add     rsp, 20h
0x140015058  pop     r14
0x14001505a  pop     rdi
0x14001505b  pop     rsi
0x14001505c  pop     rbp
0x14001505d  pop     rbx
0x14001505e  retn
```
