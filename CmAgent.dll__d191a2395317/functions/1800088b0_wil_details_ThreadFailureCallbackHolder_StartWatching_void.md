# wil::details::ThreadFailureCallbackHolder::StartWatching(void)

- ea: `0x1800088b0`
- end: `0x180008924`
- name: `?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `116`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `17`
- callee_count: `4`
- tags: ``

## callers

- `0x180008648`
- `0x18000877c`
- `0x18001bb20`
- `0x18001bc8c`
- `0x18001bdc0`
- `0x18001bfb4`
- `0x18001c0e8`
- `0x18001c21c`
- `0x18001c350`
- `0x18001c50c`
- `0x18001c640`
- `0x18001c774`
- `0x18001c8a8`
- `0x18001c9dc`
- `0x18002239c`
- `0x180022614`
- `0x180022f5c`

## callees

- `0x180002c48`
- `0x18000478c`
- `0x18000685c`
- `0x1800088b0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800088e5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800088e5`

## pseudocode

```c
void __fastcall wil::details::ThreadFailureCallbackHolder::StartWatching(
        wil::details::ThreadFailureCallbackHolder *this)
{
  _QWORD *Local; // rax
  const struct wil::FailureInfo *v3; // rdx
  _BYTE v4[168]; // [rsp+20h] [rbp-A8h] BYREF

  if ( *((_DWORD *)this + 6) )
  {
    memset_0(v4, 0, 0x98u);
    wil::details::WilFailFast((wil::details *)v4, v3);
  }
  if ( wil::details::g_pThreadFailureCallbacks )
  {
    Local = (_QWORD *)wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
                        (__int64)this,
                        1);
    *(_QWORD *)this = Local;
    if ( Local )
    {
      *((_QWORD *)this + 2) = *Local;
      *Local = this;
      *((_DWORD *)this + 6) = GetCurrentThreadId();
    }
  }
  else
  {
    *(_QWORD *)this = 0;
  }
}

```

## disassembly

```asm
0x1800088b0  push    rbx
0x1800088b2  sub     rsp, 0C0h
0x1800088b9  cmp     dword ptr [rcx+18h], 0
0x1800088bd  mov     rbx, rcx
0x1800088c0  jnz     short loc_180008907
0x1800088c2  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800088ca  jz      short loc_1800088F6
0x1800088cc  mov     dl, 1
0x1800088ce  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x1800088d3  mov     [rbx], rax
0x1800088d6  test    rax, rax
0x1800088d9  jz      short loc_1800088FD
0x1800088db  mov     rcx, [rax]
0x1800088de  mov     [rbx+10h], rcx
0x1800088e2  mov     [rax], rbx
0x1800088e5  call    cs:__imp_GetCurrentThreadId
0x1800088ec  nop     dword ptr [rax+rax+00h]
0x1800088f1  mov     [rbx+18h], eax
0x1800088f4  jmp     short loc_1800088FD
0x1800088f6  mov     qword ptr [rcx], 0
0x1800088fd  add     rsp, 0C0h
0x180008904  pop     rbx
0x180008905  retn
0x180008907  xor     edx, edx; Val
0x180008909  lea     rcx, [rsp+0C8h+var_A8]; void *
0x18000890e  mov     r8d, 98h; Size
0x180008914  call    memset_0
0x180008919  lea     rcx, [rsp+0C8h+var_A8]; this
0x18000891e  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
