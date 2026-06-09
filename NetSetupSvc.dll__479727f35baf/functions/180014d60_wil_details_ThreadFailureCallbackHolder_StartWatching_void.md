# wil::details::ThreadFailureCallbackHolder::StartWatching(void)

- ea: `0x180014d60`
- end: `0x180014dcd`
- name: `?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `109`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800139d8`

## callees

- `0x1800032d8`
- `0x180004bfc`
- `0x180006658`
- `0x180014d60`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180014db2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180014db2`

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
0x180014d60  push    rbx
0x180014d62  sub     rsp, 0C0h
0x180014d69  cmp     dword ptr [rcx+18h], 0
0x180014d6d  mov     rbx, rcx
0x180014d70  jz      short loc_180014D8F
0x180014d72  xor     edx, edx; Val
0x180014d74  lea     rcx, [rsp+0C8h+var_A8]; void *
0x180014d79  mov     r8d, 98h; Size
0x180014d7f  call    memset_0
0x180014d84  lea     rcx, [rsp+0C8h+var_A8]; this
0x180014d89  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180014d8f  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180014d97  jz      short loc_180014DBD
0x180014d99  mov     dl, 1
0x180014d9b  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x180014da0  mov     [rbx], rax
0x180014da3  test    rax, rax
0x180014da6  jz      short loc_180014DC4
0x180014da8  mov     rcx, [rax]
0x180014dab  mov     [rbx+10h], rcx
0x180014daf  mov     [rax], rbx
0x180014db2  call    cs:__imp_GetCurrentThreadId
0x180014db8  mov     [rbx+18h], eax
0x180014dbb  jmp     short loc_180014DC4
0x180014dbd  mov     qword ptr [rcx], 0
0x180014dc4  add     rsp, 0C0h
0x180014dcb  pop     rbx
0x180014dcc  retn
```
