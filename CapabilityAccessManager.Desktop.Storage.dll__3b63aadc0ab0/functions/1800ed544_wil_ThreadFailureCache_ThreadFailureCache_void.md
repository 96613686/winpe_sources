# wil::ThreadFailureCache::ThreadFailureCache(void)

- ea: `0x1800ed544`
- end: `0x1800ed5e9`
- name: `??0ThreadFailureCache@wil@@QEAA@XZ`
- size: `165`
- prototype: `wil::ThreadFailureCache *__fastcall(wil::ThreadFailureCache *this)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x1800f28f4`
- `0x1800f6a20`
- `0x18010b11c`

## callees

- `0x180003a40`
- `0x1800e8310`
- `0x1800ed544`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800ed5d2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800ed5d2`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
wil::ThreadFailureCache *__fastcall wil::ThreadFailureCache::ThreadFailureCache(wil::ThreadFailureCache *this)
{
  _QWORD *v2; // rcx
  __int64 v3; // rdx
  __int64 v4; // rcx
  _QWORD *v5; // rbx
  _QWORD *Local; // rax

  *(_QWORD *)this = &wil::ThreadFailureCache::`vftable';
  v2 = (_QWORD *)((char *)this + 8);
  v2[19] = 0;
  v2[20] = 0;
  memset_0(v2, 0, 0x98u);
  v5 = (_QWORD *)((char *)this + 176);
  *((_QWORD *)this + 22) = 0;
  *((_QWORD *)this + 23) = this;
  *((_QWORD *)this + 24) = 0;
  *((_DWORD *)this + 50) = 0;
  *((_QWORD *)this + 26) = 0;
  *((_BYTE *)this + 216) = 0;
  if ( wil::details::g_pThreadFailureCallbacks )
  {
    LOBYTE(v3) = 1;
    Local = (_QWORD *)wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
                        v4,
                        v3);
    *v5 = Local;
    if ( Local )
    {
      *((_QWORD *)this + 24) = *Local;
      *Local = v5;
      *((_DWORD *)this + 50) = GetCurrentThreadId();
    }
  }
  return this;
}

```

## disassembly

```asm
0x1800ed544  mov     [rsp+arg_0], rbx
0x1800ed549  push    rdi
0x1800ed54a  sub     rsp, 20h
0x1800ed54e  mov     rdi, rcx
0x1800ed551  lea     rax, ??_7ThreadFailureCache@wil@@6B@; const wil::ThreadFailureCache::`vftable'
0x1800ed558  mov     [rcx], rax
0x1800ed55b  add     rcx, 8; void *
0x1800ed55f  mov     qword ptr [rcx+98h], 0
0x1800ed56a  mov     qword ptr [rcx+0A0h], 0
0x1800ed575  xor     edx, edx; Val
0x1800ed577  mov     r8d, 98h; Size
0x1800ed57d  call    memset_0
0x1800ed582  lea     rbx, [rdi+0B0h]
0x1800ed589  mov     qword ptr [rbx], 0
0x1800ed590  mov     [rbx+8], rdi
0x1800ed594  mov     qword ptr [rbx+10h], 0
0x1800ed59c  mov     dword ptr [rbx+18h], 0
0x1800ed5a3  mov     qword ptr [rbx+20h], 0
0x1800ed5ab  mov     byte ptr [rbx+28h], 0
0x1800ed5af  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800ed5b7  jz      short loc_1800ED5DB
0x1800ed5b9  mov     dl, 1
0x1800ed5bb  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x1800ed5c0  mov     [rbx], rax
0x1800ed5c3  test    rax, rax
0x1800ed5c6  jz      short loc_1800ED5DB
0x1800ed5c8  mov     rcx, [rax]
0x1800ed5cb  mov     [rbx+10h], rcx
0x1800ed5cf  mov     [rax], rbx
0x1800ed5d2  call    cs:__imp_GetCurrentThreadId
0x1800ed5d8  mov     [rbx+18h], eax
0x1800ed5db  mov     rax, rdi
0x1800ed5de  mov     rbx, [rsp+28h+arg_0]
0x1800ed5e3  add     rsp, 20h
0x1800ed5e7  pop     rdi
0x1800ed5e8  retn
```
