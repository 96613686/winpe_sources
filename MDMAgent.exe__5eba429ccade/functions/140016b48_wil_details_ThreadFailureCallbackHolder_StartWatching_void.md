# wil::details::ThreadFailureCallbackHolder::StartWatching(void)

- ea: `0x140016b48`
- end: `0x140016bb5`
- name: `?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `109`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140015b74`

## callees

- `0x14000349c`
- `0x1400056fc`
- `0x1400077a8`
- `0x140016b48`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140016b9a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140016b9a`

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
0x140016b48  push    rbx
0x140016b4a  sub     rsp, 0C0h
0x140016b51  cmp     dword ptr [rcx+18h], 0
0x140016b55  mov     rbx, rcx
0x140016b58  jz      short loc_140016B77
0x140016b5a  xor     edx, edx; Val
0x140016b5c  lea     rcx, [rsp+0C8h+var_A8]; void *
0x140016b61  mov     r8d, 98h; Size
0x140016b67  call    memset_0
0x140016b6c  lea     rcx, [rsp+0C8h+var_A8]; this
0x140016b71  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x140016b77  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x140016b7f  jz      short loc_140016BA5
0x140016b81  mov     dl, 1
0x140016b83  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x140016b88  mov     [rbx], rax
0x140016b8b  test    rax, rax
0x140016b8e  jz      short loc_140016BAC
0x140016b90  mov     rcx, [rax]
0x140016b93  mov     [rbx+10h], rcx
0x140016b97  mov     [rax], rbx
0x140016b9a  call    cs:__imp_GetCurrentThreadId
0x140016ba0  mov     [rbx+18h], eax
0x140016ba3  jmp     short loc_140016BAC
0x140016ba5  mov     qword ptr [rcx], 0
0x140016bac  add     rsp, 0C0h
0x140016bb3  pop     rbx
0x140016bb4  retn
```
