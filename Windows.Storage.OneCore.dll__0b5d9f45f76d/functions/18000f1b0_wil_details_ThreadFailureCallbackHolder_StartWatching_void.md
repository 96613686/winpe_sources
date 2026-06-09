# wil::details::ThreadFailureCallbackHolder::StartWatching(void)

- ea: `0x18000f1b0`
- end: `0x18000f21d`
- name: `?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `109`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x18000cd40`
- `0x18000dfcc`

## callees

- `0x1800037c8`
- `0x180005dec`
- `0x180009278`
- `0x18000f1b0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f202`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f202`

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
0x18000f1b0  push    rbx
0x18000f1b2  sub     rsp, 0C0h
0x18000f1b9  cmp     dword ptr [rcx+18h], 0
0x18000f1bd  mov     rbx, rcx
0x18000f1c0  jz      short loc_18000F1DF
0x18000f1c2  xor     edx, edx; Val
0x18000f1c4  lea     rcx, [rsp+0C8h+var_A8]; void *
0x18000f1c9  mov     r8d, 98h; Size
0x18000f1cf  call    memset_0
0x18000f1d4  lea     rcx, [rsp+0C8h+var_A8]; this
0x18000f1d9  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18000f1df  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000f1e7  jz      short loc_18000F20D
0x18000f1e9  mov     dl, 1
0x18000f1eb  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x18000f1f0  mov     [rbx], rax
0x18000f1f3  test    rax, rax
0x18000f1f6  jz      short loc_18000F214
0x18000f1f8  mov     rcx, [rax]
0x18000f1fb  mov     [rbx+10h], rcx
0x18000f1ff  mov     [rax], rbx
0x18000f202  call    cs:__imp_GetCurrentThreadId
0x18000f208  mov     [rbx+18h], eax
0x18000f20b  jmp     short loc_18000F214
0x18000f20d  mov     qword ptr [rcx], 0
0x18000f214  add     rsp, 0C0h
0x18000f21b  pop     rbx
0x18000f21c  retn
```
