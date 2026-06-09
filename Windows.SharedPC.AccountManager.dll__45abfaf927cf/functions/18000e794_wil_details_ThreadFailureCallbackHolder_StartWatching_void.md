# wil::details::ThreadFailureCallbackHolder::StartWatching(void)

- ea: `0x18000e794`
- end: `0x18000e801`
- name: `?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `109`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x18000db54`
- `0x18001823c`

## callees

- `0x180003fc0`
- `0x180007e0c`
- `0x18000942c`
- `0x18000e794`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e7e6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e7e6`

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
0x18000e794  push    rbx
0x18000e796  sub     rsp, 0C0h
0x18000e79d  cmp     dword ptr [rcx+18h], 0
0x18000e7a1  mov     rbx, rcx
0x18000e7a4  jz      short loc_18000E7C3
0x18000e7a6  xor     edx, edx; Val
0x18000e7a8  lea     rcx, [rsp+0C8h+var_A8]; void *
0x18000e7ad  mov     r8d, 98h; Size
0x18000e7b3  call    memset_0
0x18000e7b8  lea     rcx, [rsp+0C8h+var_A8]; this
0x18000e7bd  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18000e7c3  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000e7cb  jz      short loc_18000E7F1
0x18000e7cd  mov     dl, 1
0x18000e7cf  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x18000e7d4  mov     [rbx], rax
0x18000e7d7  test    rax, rax
0x18000e7da  jz      short loc_18000E7F8
0x18000e7dc  mov     rcx, [rax]
0x18000e7df  mov     [rbx+10h], rcx
0x18000e7e3  mov     [rax], rbx
0x18000e7e6  call    cs:__imp_GetCurrentThreadId
0x18000e7ec  mov     [rbx+18h], eax
0x18000e7ef  jmp     short loc_18000E7F8
0x18000e7f1  mov     qword ptr [rcx], 0
0x18000e7f8  add     rsp, 0C0h
0x18000e7ff  pop     rbx
0x18000e800  retn
```
