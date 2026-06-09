# wil::details::ThreadFailureCallbackHolder::StartWatching(void)

- ea: `0x14000e2d4`
- end: `0x14000e341`
- name: `?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `109`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14000b0f0`

## callees

- `0x140002d50`
- `0x14000576c`
- `0x140007448`
- `0x14000e2d4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000e326`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000e326`

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
0x14000e2d4  push    rbx
0x14000e2d6  sub     rsp, 0C0h
0x14000e2dd  cmp     dword ptr [rcx+18h], 0
0x14000e2e1  mov     rbx, rcx
0x14000e2e4  jz      short loc_14000E303
0x14000e2e6  xor     edx, edx; Val
0x14000e2e8  lea     rcx, [rsp+0C8h+var_A8]; void *
0x14000e2ed  mov     r8d, 98h; Size
0x14000e2f3  call    memset_0
0x14000e2f8  lea     rcx, [rsp+0C8h+var_A8]; this
0x14000e2fd  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x14000e303  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x14000e30b  jz      short loc_14000E331
0x14000e30d  mov     dl, 1
0x14000e30f  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x14000e314  mov     [rbx], rax
0x14000e317  test    rax, rax
0x14000e31a  jz      short loc_14000E338
0x14000e31c  mov     rcx, [rax]
0x14000e31f  mov     [rbx+10h], rcx
0x14000e323  mov     [rax], rbx
0x14000e326  call    cs:__imp_GetCurrentThreadId
0x14000e32c  mov     [rbx+18h], eax
0x14000e32f  jmp     short loc_14000E338
0x14000e331  mov     qword ptr [rcx], 0
0x14000e338  add     rsp, 0C0h
0x14000e33f  pop     rbx
0x14000e340  retn
```
