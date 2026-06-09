# wil::details::ThreadFailureCallbackHolder::StartWatching(void)

- ea: `0x180031204`
- end: `0x180031271`
- name: `?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `109`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18003104c`

## callees

- `0x1800030a0`
- `0x18000a35c`
- `0x180020ce0`
- `0x180031204`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180031256`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180031256`

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
0x180031204  push    rbx
0x180031206  sub     rsp, 0C0h
0x18003120d  cmp     dword ptr [rcx+18h], 0
0x180031211  mov     rbx, rcx
0x180031214  jz      short loc_180031233
0x180031216  xor     edx, edx; Val
0x180031218  lea     rcx, [rsp+0C8h+var_A8]; void *
0x18003121d  mov     r8d, 98h; Size
0x180031223  call    memset_0
0x180031228  lea     rcx, [rsp+0C8h+var_A8]; this
0x18003122d  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180031233  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18003123b  jz      short loc_180031261
0x18003123d  mov     dl, 1
0x18003123f  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x180031244  mov     [rbx], rax
0x180031247  test    rax, rax
0x18003124a  jz      short loc_180031268
0x18003124c  mov     rcx, [rax]
0x18003124f  mov     [rbx+10h], rcx
0x180031253  mov     [rax], rbx
0x180031256  call    cs:__imp_GetCurrentThreadId
0x18003125c  mov     [rbx+18h], eax
0x18003125f  jmp     short loc_180031268
0x180031261  mov     qword ptr [rcx], 0
0x180031268  add     rsp, 0C0h
0x18003126f  pop     rbx
0x180031270  retn
```
