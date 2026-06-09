# wil::details::ThreadFailureCallbackHolder::StartWatching(void)

- ea: `0x18001b028`
- end: `0x18001b095`
- name: `?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `109`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180018364`

## callees

- `0x18000b560`
- `0x18000df50`
- `0x18001b028`
- `0x1800204ee`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001b07a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001b07a`

## pseudocode

```c
void __fastcall wil::details::ThreadFailureCallbackHolder::StartWatching(
        wil::details::ThreadFailureCallbackHolder *this)
{
  wil::details::ThreadFailureCallbackHolder **Local; // rax
  wil::FailureInfo failure; // [rsp+20h] [rbp-A8h] BYREF

  if ( this->m_threadId )
  {
    memset_0((void *)&failure, 0, sizeof(failure));
    wil::details::WilFailFast(&failure);
  }
  if ( wil::details::g_pThreadFailureCallbacks )
  {
    Local = wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
              (wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> *)this,
              1);
    this->m_ppThreadList = Local;
    if ( Local )
    {
      this->m_pNext = *Local;
      *Local = this;
      this->m_threadId = GetCurrentThreadId();
    }
  }
  else
  {
    this->m_ppThreadList = 0;
  }
}

```

## disassembly

```asm
0x18001b028  push    rbx
0x18001b02a  sub     rsp, 0C0h
0x18001b031  cmp     dword ptr [this+18h], 0
0x18001b035  mov     rbx, this
0x18001b038  jz      short loc_18001B057
0x18001b03a  xor     edx, edx; Val
0x18001b03c  lea     this, [rsp+0C8h+failure]; void *
0x18001b041  mov     r8d, 98h; Size
0x18001b047  call    memset_0
0x18001b04c  lea     this, [rsp+0C8h+failure]; failure
0x18001b051  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18001b057  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18001b05f  jz      short loc_18001B085
0x18001b061  mov     dl, 1; shouldAllocate
0x18001b063  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x18001b068  mov     [rbx], rax
0x18001b06b  test    rax, rax
0x18001b06e  jz      short loc_18001B08C
0x18001b070  mov     this, [rax]
0x18001b073  mov     [rbx+10h], this
0x18001b077  mov     [rax], rbx
0x18001b07a  call    cs:__imp_GetCurrentThreadId
0x18001b080  mov     [rbx+18h], eax
0x18001b083  jmp     short loc_18001B08C
0x18001b085  mov     qword ptr [this], 0
0x18001b08c  add     rsp, 0C0h
0x18001b093  pop     rbx
0x18001b094  retn
```
