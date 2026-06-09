# wil::details::ThreadFailureCallbackHolder::StartWatching(void)

- ea: `0x18000eebc`
- end: `0x18000ef29`
- name: `?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `109`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x18000ee64`
- `0x180017730`
- `0x1800267a0`

## callees

- `0x18000eebc`
- `0x18000ef30`
- `0x1800241c4`
- `0x18002aad0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ef0e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ef0e`

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
0x18000eebc  push    rbx
0x18000eebe  sub     rsp, 0C0h
0x18000eec5  cmp     dword ptr [rcx+18h], 0
0x18000eec9  mov     rbx, rcx
0x18000eecc  jz      short loc_18000EEEB
0x18000eece  xor     edx, edx; Val
0x18000eed0  lea     rcx, [rsp+0C8h+var_A8]; void *
0x18000eed5  mov     r8d, 98h; Size
0x18000eedb  call    memset_0
0x18000eee0  lea     rcx, [rsp+0C8h+var_A8]; this
0x18000eee5  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18000eeeb  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000eef3  jz      short loc_18000EF19
0x18000eef5  mov     dl, 1
0x18000eef7  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x18000eefc  mov     [rbx], rax
0x18000eeff  test    rax, rax
0x18000ef02  jz      short loc_18000EF20
0x18000ef04  mov     rcx, [rax]
0x18000ef07  mov     [rbx+10h], rcx
0x18000ef0b  mov     [rax], rbx
0x18000ef0e  call    cs:__imp_GetCurrentThreadId
0x18000ef14  mov     [rbx+18h], eax
0x18000ef17  jmp     short loc_18000EF20
0x18000ef19  mov     qword ptr [rcx], 0
0x18000ef20  add     rsp, 0C0h
0x18000ef27  pop     rbx
0x18000ef28  retn
```
