# wil::details::ThreadFailureCallbackHolder::StartWatching(void)

- ea: `0x180015070`
- end: `0x1800150dd`
- name: `?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `109`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180014dd4`
- `0x180014f34`

## callees

- `0x180003bc8`
- `0x180006e6c`
- `0x18000a668`
- `0x180015070`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800150c2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800150c2`

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
0x180015070  push    rbx
0x180015072  sub     rsp, 0C0h
0x180015079  cmp     dword ptr [rcx+18h], 0
0x18001507d  mov     rbx, rcx
0x180015080  jz      short loc_18001509F
0x180015082  xor     edx, edx; Val
0x180015084  lea     rcx, [rsp+0C8h+var_A8]; void *
0x180015089  mov     r8d, 98h; Size
0x18001508f  call    memset_0
0x180015094  lea     rcx, [rsp+0C8h+var_A8]; this
0x180015099  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18001509f  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800150a7  jz      short loc_1800150CD
0x1800150a9  mov     dl, 1
0x1800150ab  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x1800150b0  mov     [rbx], rax
0x1800150b3  test    rax, rax
0x1800150b6  jz      short loc_1800150D4
0x1800150b8  mov     rcx, [rax]
0x1800150bb  mov     [rbx+10h], rcx
0x1800150bf  mov     [rax], rbx
0x1800150c2  call    cs:__imp_GetCurrentThreadId
0x1800150c8  mov     [rbx+18h], eax
0x1800150cb  jmp     short loc_1800150D4
0x1800150cd  mov     qword ptr [rcx], 0
0x1800150d4  add     rsp, 0C0h
0x1800150db  pop     rbx
0x1800150dc  retn
```
