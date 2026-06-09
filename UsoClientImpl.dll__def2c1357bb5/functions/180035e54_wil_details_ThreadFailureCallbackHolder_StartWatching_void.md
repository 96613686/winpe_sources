# wil::details::ThreadFailureCallbackHolder::StartWatching(void)

- ea: `0x180035e54`
- end: `0x180035ec1`
- name: `?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `109`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x18000a844`
- `0x18003e568`

## callees

- `0x180007630`
- `0x1800091b8`
- `0x180035e54`
- `0x18005c660`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180035e89`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180035e89`

## pseudocode

```c
void __fastcall wil::details::ThreadFailureCallbackHolder::StartWatching(
        wil::details::ThreadFailureCallbackHolder *this,
        __int64 a2)
{
  _QWORD *Local; // rax
  const struct wil::FailureInfo *v4; // rdx
  _BYTE v5[168]; // [rsp+20h] [rbp-A8h] BYREF

  if ( *((_DWORD *)this + 6) )
  {
    memset(v5, 0, 0x98u);
    wil::details::WilFailFast((wil::details *)v5, v4);
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
0x180035e54  push    rbx
0x180035e56  sub     rsp, 0C0h
0x180035e5d  cmp     dword ptr [rcx+18h], 0
0x180035e61  mov     rbx, rcx
0x180035e64  jnz     short loc_180035EA4
0x180035e66  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180035e6e  jz      short loc_180035E94
0x180035e70  mov     dl, 1
0x180035e72  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x180035e77  mov     [rbx], rax
0x180035e7a  test    rax, rax
0x180035e7d  jz      short loc_180035E9B
0x180035e7f  mov     rcx, [rax]
0x180035e82  mov     [rbx+10h], rcx
0x180035e86  mov     [rax], rbx
0x180035e89  call    cs:__imp_GetCurrentThreadId
0x180035e8f  mov     [rbx+18h], eax
0x180035e92  jmp     short loc_180035E9B
0x180035e94  mov     qword ptr [rcx], 0
0x180035e9b  add     rsp, 0C0h
0x180035ea2  pop     rbx
0x180035ea3  retn
0x180035ea4  xor     edx, edx; Val
0x180035ea6  lea     rcx, [rsp+0C8h+var_A8]; void *
0x180035eab  mov     r8d, 98h; Size
0x180035eb1  call    memset
0x180035eb6  lea     rcx, [rsp+0C8h+var_A8]; this
0x180035ebb  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
