# wil::details::ThreadFailureCallbackHolder::StartWatching(void)

- ea: `0x14000f590`
- end: `0x14000f5fd`
- name: `?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `109`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x140007ab8`
- `0x140008268`
- `0x14000eee0`
- `0x14002302c`

## callees

- `0x140003848`
- `0x14000bb8c`
- `0x14000f590`
- `0x140010cd8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000f5e2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000f5e2`

## pseudocode

```c
void __fastcall wil::details::ThreadFailureCallbackHolder::StartWatching(
        wil::details::ThreadFailureCallbackHolder *this,
        __int64 a2)
{
  const struct wil::FailureInfo *v3; // rdx
  _QWORD *Local; // rax
  _BYTE v5[168]; // [rsp+20h] [rbp-A8h] BYREF

  if ( *((_DWORD *)this + 6) )
  {
    memset_0(v5, 0, 0x98u);
    wil::details::WilFailFast((wil::details *)v5, v3);
  }
  if ( wil::details::g_pThreadFailureCallbacks )
  {
    LOBYTE(a2) = 1;
    Local = (_QWORD *)wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
                        this,
                        a2);
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
0x14000f590  push    rbx
0x14000f592  sub     rsp, 0C0h
0x14000f599  cmp     dword ptr [rcx+18h], 0
0x14000f59d  mov     rbx, rcx
0x14000f5a0  jz      short loc_14000F5BF
0x14000f5a2  xor     edx, edx; Val
0x14000f5a4  lea     rcx, [rsp+0C8h+var_A8]; void *
0x14000f5a9  mov     r8d, 98h; Size
0x14000f5af  call    memset_0
0x14000f5b4  lea     rcx, [rsp+0C8h+var_A8]; this
0x14000f5b9  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x14000f5bf  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x14000f5c7  jz      short loc_14000F5ED
0x14000f5c9  mov     dl, 1
0x14000f5cb  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x14000f5d0  mov     [rbx], rax
0x14000f5d3  test    rax, rax
0x14000f5d6  jz      short loc_14000F5F4
0x14000f5d8  mov     rcx, [rax]
0x14000f5db  mov     [rbx+10h], rcx
0x14000f5df  mov     [rax], rbx
0x14000f5e2  call    cs:__imp_GetCurrentThreadId
0x14000f5e8  mov     [rbx+18h], eax
0x14000f5eb  jmp     short loc_14000F5F4
0x14000f5ed  mov     qword ptr [rcx], 0
0x14000f5f4  add     rsp, 0C0h
0x14000f5fb  pop     rbx
0x14000f5fc  retn
```
