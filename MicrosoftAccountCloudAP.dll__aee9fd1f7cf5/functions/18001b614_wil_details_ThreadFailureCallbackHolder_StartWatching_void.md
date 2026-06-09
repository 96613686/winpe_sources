# wil::details::ThreadFailureCallbackHolder::StartWatching(void)

- ea: `0x18001b614`
- end: `0x18001b681`
- name: `?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `109`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18001b520`

## callees

- `0x180003b14`
- `0x1800060ec`
- `0x1800078d8`
- `0x18001b614`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001b666`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001b666`

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
0x18001b614  push    rbx
0x18001b616  sub     rsp, 0C0h
0x18001b61d  cmp     dword ptr [rcx+18h], 0
0x18001b621  mov     rbx, rcx
0x18001b624  jz      short loc_18001B643
0x18001b626  xor     edx, edx; Val
0x18001b628  lea     rcx, [rsp+0C8h+var_A8]; void *
0x18001b62d  mov     r8d, 98h; Size
0x18001b633  call    memset_0
0x18001b638  lea     rcx, [rsp+0C8h+var_A8]; this
0x18001b63d  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18001b643  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18001b64b  jz      short loc_18001B671
0x18001b64d  mov     dl, 1
0x18001b64f  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x18001b654  mov     [rbx], rax
0x18001b657  test    rax, rax
0x18001b65a  jz      short loc_18001B678
0x18001b65c  mov     rcx, [rax]
0x18001b65f  mov     [rbx+10h], rcx
0x18001b663  mov     [rax], rbx
0x18001b666  call    cs:__imp_GetCurrentThreadId
0x18001b66c  mov     [rbx+18h], eax
0x18001b66f  jmp     short loc_18001B678
0x18001b671  mov     qword ptr [rcx], 0
0x18001b678  add     rsp, 0C0h
0x18001b67f  pop     rbx
0x18001b680  retn
```
