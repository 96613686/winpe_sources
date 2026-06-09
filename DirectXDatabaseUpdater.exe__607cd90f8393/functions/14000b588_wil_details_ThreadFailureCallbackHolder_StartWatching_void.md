# wil::details::ThreadFailureCallbackHolder::StartWatching(void)

- ea: `0x14000b588`
- end: `0x14000b5f5`
- name: `?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `109`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140006df4`

## callees

- `0x140003ab8`
- `0x14000757c`
- `0x14000b588`
- `0x14000d6a8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000b5da`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000b5da`

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
0x14000b588  push    rbx
0x14000b58a  sub     rsp, 0C0h
0x14000b591  cmp     dword ptr [rcx+18h], 0
0x14000b595  mov     rbx, rcx
0x14000b598  jz      short loc_14000B5B7
0x14000b59a  xor     edx, edx; Val
0x14000b59c  lea     rcx, [rsp+0C8h+var_A8]; void *
0x14000b5a1  mov     r8d, 98h; Size
0x14000b5a7  call    memset_0
0x14000b5ac  lea     rcx, [rsp+0C8h+var_A8]; this
0x14000b5b1  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x14000b5b7  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x14000b5bf  jz      short loc_14000B5E5
0x14000b5c1  mov     dl, 1
0x14000b5c3  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x14000b5c8  mov     [rbx], rax
0x14000b5cb  test    rax, rax
0x14000b5ce  jz      short loc_14000B5EC
0x14000b5d0  mov     rcx, [rax]
0x14000b5d3  mov     [rbx+10h], rcx
0x14000b5d7  mov     [rax], rbx
0x14000b5da  call    cs:__imp_GetCurrentThreadId
0x14000b5e0  mov     [rbx+18h], eax
0x14000b5e3  jmp     short loc_14000B5EC
0x14000b5e5  mov     qword ptr [rcx], 0
0x14000b5ec  add     rsp, 0C0h
0x14000b5f3  pop     rbx
0x14000b5f4  retn
```
