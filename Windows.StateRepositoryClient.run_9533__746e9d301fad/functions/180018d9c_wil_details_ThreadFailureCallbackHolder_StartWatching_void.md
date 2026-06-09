# wil::details::ThreadFailureCallbackHolder::StartWatching(void)

- ea: `0x180018d9c`
- end: `0x180018e09`
- name: `?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `109`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180018c60`

## callees

- `0x180003630`
- `0x18000630c`
- `0x180008118`
- `0x180018d9c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018dee`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018dee`

## pseudocode

```c
void __fastcall wil::details::ThreadFailureCallbackHolder::StartWatching(
        wil::details::ThreadFailureCallbackHolder *this)
{
  const struct wil::FailureInfo *v2; // rdx
  _QWORD *Local; // rax
  _BYTE v4[168]; // [rsp+20h] [rbp-A8h] BYREF

  if ( *((_DWORD *)this + 6) )
  {
    memset_0(v4, 0, 0x98u);
    wil::details::WilFailFast((wil::details *)v4, v2);
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
0x180018d9c  push    rbx
0x180018d9e  sub     rsp, 0C0h
0x180018da5  cmp     dword ptr [rcx+18h], 0
0x180018da9  mov     rbx, rcx
0x180018dac  jz      short loc_180018DCB
0x180018dae  xor     edx, edx; Val
0x180018db0  lea     rcx, [rsp+0C8h+var_A8]; void *
0x180018db5  mov     r8d, 98h; Size
0x180018dbb  call    memset_0
0x180018dc0  lea     rcx, [rsp+0C8h+var_A8]; this
0x180018dc5  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180018dcb  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180018dd3  jz      short loc_180018DF9
0x180018dd5  mov     dl, 1
0x180018dd7  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x180018ddc  mov     [rbx], rax
0x180018ddf  test    rax, rax
0x180018de2  jz      short loc_180018E00
0x180018de4  mov     rcx, [rax]
0x180018de7  mov     [rbx+10h], rcx
0x180018deb  mov     [rax], rbx
0x180018dee  call    cs:__imp_GetCurrentThreadId
0x180018df4  mov     [rbx+18h], eax
0x180018df7  jmp     short loc_180018E00
0x180018df9  mov     qword ptr [rcx], 0
0x180018e00  add     rsp, 0C0h
0x180018e07  pop     rbx
0x180018e08  retn
```
