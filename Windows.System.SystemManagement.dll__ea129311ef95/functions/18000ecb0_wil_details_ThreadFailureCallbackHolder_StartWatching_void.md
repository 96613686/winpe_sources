# wil::details::ThreadFailureCallbackHolder::StartWatching(void)

- ea: `0x18000ecb0`
- end: `0x18000ed1d`
- name: `?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `109`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000da8c`

## callees

- `0x18000399c`
- `0x180006b3c`
- `0x180008858`
- `0x18000ecb0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ed02`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ed02`

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
0x18000ecb0  push    rbx
0x18000ecb2  sub     rsp, 0C0h
0x18000ecb9  cmp     dword ptr [rcx+18h], 0
0x18000ecbd  mov     rbx, rcx
0x18000ecc0  jz      short loc_18000ECDF
0x18000ecc2  xor     edx, edx; Val
0x18000ecc4  lea     rcx, [rsp+0C8h+var_A8]; void *
0x18000ecc9  mov     r8d, 98h; Size
0x18000eccf  call    memset_0
0x18000ecd4  lea     rcx, [rsp+0C8h+var_A8]; this
0x18000ecd9  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18000ecdf  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000ece7  jz      short loc_18000ED0D
0x18000ece9  mov     dl, 1
0x18000eceb  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x18000ecf0  mov     [rbx], rax
0x18000ecf3  test    rax, rax
0x18000ecf6  jz      short loc_18000ED14
0x18000ecf8  mov     rcx, [rax]
0x18000ecfb  mov     [rbx+10h], rcx
0x18000ecff  mov     [rax], rbx
0x18000ed02  call    cs:__imp_GetCurrentThreadId
0x18000ed08  mov     [rbx+18h], eax
0x18000ed0b  jmp     short loc_18000ED14
0x18000ed0d  mov     qword ptr [rcx], 0
0x18000ed14  add     rsp, 0C0h
0x18000ed1b  pop     rbx
0x18000ed1c  retn
```
