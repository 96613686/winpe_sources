# wil::details::ThreadFailureCallbackHolder::StartWatching(void)

- ea: `0x180017a50`
- end: `0x180017abd`
- name: `?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `109`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18002afd0`

## callees

- `0x1800042f4`
- `0x18000963c`
- `0x18000abb8`
- `0x180017a50`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180017aa2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180017aa2`

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
0x180017a50  push    rbx
0x180017a52  sub     rsp, 0C0h
0x180017a59  cmp     dword ptr [rcx+18h], 0
0x180017a5d  mov     rbx, rcx
0x180017a60  jz      short loc_180017A7F
0x180017a62  xor     edx, edx; Val
0x180017a64  lea     rcx, [rsp+0C8h+var_A8]; void *
0x180017a69  mov     r8d, 98h; Size
0x180017a6f  call    memset_0
0x180017a74  lea     rcx, [rsp+0C8h+var_A8]; this
0x180017a79  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180017a7f  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180017a87  jz      short loc_180017AAD
0x180017a89  mov     dl, 1
0x180017a8b  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x180017a90  mov     [rbx], rax
0x180017a93  test    rax, rax
0x180017a96  jz      short loc_180017AB4
0x180017a98  mov     rcx, [rax]
0x180017a9b  mov     [rbx+10h], rcx
0x180017a9f  mov     [rax], rbx
0x180017aa2  call    cs:__imp_GetCurrentThreadId
0x180017aa8  mov     [rbx+18h], eax
0x180017aab  jmp     short loc_180017AB4
0x180017aad  mov     qword ptr [rcx], 0
0x180017ab4  add     rsp, 0C0h
0x180017abb  pop     rbx
0x180017abc  retn
```
