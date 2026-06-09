# wil::details::ThreadFailureCallbackHolder::StartWatching(void)

- ea: `0x180016e40`
- end: `0x180016eb4`
- name: `?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `116`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180016ce4`

## callees

- `0x1800053c4`
- `0x18000d620`
- `0x180011efc`
- `0x180016e40`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180016e75`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180016e75`

## pseudocode

```c
void __fastcall wil::details::ThreadFailureCallbackHolder::StartWatching(
        wil::details::ThreadFailureCallbackHolder *this)
{
  _QWORD *Local; // rax
  const struct wil::FailureInfo *v3; // rdx
  _BYTE v4[168]; // [rsp+20h] [rbp-A8h] BYREF

  if ( *((_DWORD *)this + 6) )
  {
    memset_0(v4, 0, 0x98u);
    wil::details::WilFailFast((wil::details *)v4, v3);
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
0x180016e40  push    rbx
0x180016e42  sub     rsp, 0C0h
0x180016e49  cmp     dword ptr [rcx+18h], 0
0x180016e4d  mov     rbx, rcx
0x180016e50  jnz     short loc_180016E97
0x180016e52  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180016e5a  jz      short loc_180016E86
0x180016e5c  mov     dl, 1
0x180016e5e  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x180016e63  mov     [rbx], rax
0x180016e66  test    rax, rax
0x180016e69  jz      short loc_180016E8D
0x180016e6b  mov     rcx, [rax]
0x180016e6e  mov     [rbx+10h], rcx
0x180016e72  mov     [rax], rbx
0x180016e75  call    cs:__imp_GetCurrentThreadId
0x180016e7c  nop     dword ptr [rax+rax+00h]
0x180016e81  mov     [rbx+18h], eax
0x180016e84  jmp     short loc_180016E8D
0x180016e86  mov     qword ptr [rcx], 0
0x180016e8d  add     rsp, 0C0h
0x180016e94  pop     rbx
0x180016e95  retn
0x180016e97  xor     edx, edx; Val
0x180016e99  lea     rcx, [rsp+0C8h+var_A8]; void *
0x180016e9e  mov     r8d, 98h; Size
0x180016ea4  call    memset_0
0x180016ea9  lea     rcx, [rsp+0C8h+var_A8]; this
0x180016eae  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
