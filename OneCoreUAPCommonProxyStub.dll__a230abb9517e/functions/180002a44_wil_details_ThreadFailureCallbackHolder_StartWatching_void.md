# wil::details::ThreadFailureCallbackHolder::StartWatching(void)

- ea: `0x180002a44`
- end: `0x180002ab1`
- name: `?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `109`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x18000314c`
- `0x1800033f8`

## callees

- `0x180002a44`
- `0x180002ab8`
- `0x18000363c`
- `0x1800045ba`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002a96`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002a96`

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
0x180002a44  push    rbx
0x180002a46  sub     rsp, 0C0h
0x180002a4d  cmp     dword ptr [rcx+18h], 0
0x180002a51  mov     rbx, rcx
0x180002a54  jz      short loc_180002A73
0x180002a56  xor     edx, edx; Val
0x180002a58  lea     rcx, [rsp+0C8h+var_A8]; void *
0x180002a5d  mov     r8d, 98h; Size
0x180002a63  call    memset_0
0x180002a68  lea     rcx, [rsp+0C8h+var_A8]; this
0x180002a6d  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180002a73  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180002a7b  jz      short loc_180002AA1
0x180002a7d  mov     dl, 1
0x180002a7f  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x180002a84  mov     [rbx], rax
0x180002a87  test    rax, rax
0x180002a8a  jz      short loc_180002AA8
0x180002a8c  mov     rcx, [rax]
0x180002a8f  mov     [rbx+10h], rcx
0x180002a93  mov     [rax], rbx
0x180002a96  call    cs:__imp_GetCurrentThreadId
0x180002a9c  mov     [rbx+18h], eax
0x180002a9f  jmp     short loc_180002AA8
0x180002aa1  mov     qword ptr [rcx], 0
0x180002aa8  add     rsp, 0C0h
0x180002aaf  pop     rbx
0x180002ab0  retn
```
