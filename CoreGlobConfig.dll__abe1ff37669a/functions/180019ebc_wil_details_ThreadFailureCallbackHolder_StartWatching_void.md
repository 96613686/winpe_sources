# wil::details::ThreadFailureCallbackHolder::StartWatching(void)

- ea: `0x180019ebc`
- end: `0x180019f29`
- name: `?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `109`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800145ec`

## callees

- `0x1800032dc`
- `0x1800071ec`
- `0x180008d08`
- `0x180019ebc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019f0e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019f0e`

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
0x180019ebc  push    rbx
0x180019ebe  sub     rsp, 0C0h
0x180019ec5  cmp     dword ptr [rcx+18h], 0
0x180019ec9  mov     rbx, rcx
0x180019ecc  jz      short loc_180019EEB
0x180019ece  xor     edx, edx; Val
0x180019ed0  lea     rcx, [rsp+0C8h+var_A8]; void *
0x180019ed5  mov     r8d, 98h; Size
0x180019edb  call    memset_0
0x180019ee0  lea     rcx, [rsp+0C8h+var_A8]; this
0x180019ee5  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180019eeb  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180019ef3  jz      short loc_180019F19
0x180019ef5  mov     dl, 1
0x180019ef7  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x180019efc  mov     [rbx], rax
0x180019eff  test    rax, rax
0x180019f02  jz      short loc_180019F20
0x180019f04  mov     rcx, [rax]
0x180019f07  mov     [rbx+10h], rcx
0x180019f0b  mov     [rax], rbx
0x180019f0e  call    cs:__imp_GetCurrentThreadId
0x180019f14  mov     [rbx+18h], eax
0x180019f17  jmp     short loc_180019F20
0x180019f19  mov     qword ptr [rcx], 0
0x180019f20  add     rsp, 0C0h
0x180019f27  pop     rbx
0x180019f28  retn
```
