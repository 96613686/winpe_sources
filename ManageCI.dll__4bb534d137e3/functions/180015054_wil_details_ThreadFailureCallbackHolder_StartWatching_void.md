# wil::details::ThreadFailureCallbackHolder::StartWatching(void)

- ea: `0x180015054`
- end: `0x1800150c1`
- name: `?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `109`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180010cf4`
- `0x180014f34`

## callees

- `0x180003888`
- `0x18000627c`
- `0x180008028`
- `0x180015054`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800150a6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800150a6`

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
0x180015054  push    rbx
0x180015056  sub     rsp, 0C0h
0x18001505d  cmp     dword ptr [rcx+18h], 0
0x180015061  mov     rbx, rcx
0x180015064  jz      short loc_180015083
0x180015066  xor     edx, edx; Val
0x180015068  lea     rcx, [rsp+0C8h+var_A8]; void *
0x18001506d  mov     r8d, 98h; Size
0x180015073  call    memset_0
0x180015078  lea     rcx, [rsp+0C8h+var_A8]; this
0x18001507d  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180015083  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18001508b  jz      short loc_1800150B1
0x18001508d  mov     dl, 1
0x18001508f  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x180015094  mov     [rbx], rax
0x180015097  test    rax, rax
0x18001509a  jz      short loc_1800150B8
0x18001509c  mov     rcx, [rax]
0x18001509f  mov     [rbx+10h], rcx
0x1800150a3  mov     [rax], rbx
0x1800150a6  call    cs:__imp_GetCurrentThreadId
0x1800150ac  mov     [rbx+18h], eax
0x1800150af  jmp     short loc_1800150B8
0x1800150b1  mov     qword ptr [rcx], 0
0x1800150b8  add     rsp, 0C0h
0x1800150bf  pop     rbx
0x1800150c0  retn
```
