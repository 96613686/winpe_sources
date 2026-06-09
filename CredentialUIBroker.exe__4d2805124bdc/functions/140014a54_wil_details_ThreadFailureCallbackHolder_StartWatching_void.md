# wil::details::ThreadFailureCallbackHolder::StartWatching(void)

- ea: `0x140014a54`
- end: `0x140014ac1`
- name: `?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `109`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `5`
- callee_count: `4`
- tags: ``

## callers

- `0x1400084c8`
- `0x14000bb3c`
- `0x140014578`
- `0x1400147dc`
- `0x14001492c`

## callees

- `0x1400042c4`
- `0x14000da1c`
- `0x140014a54`
- `0x1400178c8`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140014aa6`
- `KERNEL32!GetCurrentThreadId` at `0x140014aa6`

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
0x140014a54  push    rbx
0x140014a56  sub     rsp, 0C0h
0x140014a5d  cmp     dword ptr [rcx+18h], 0
0x140014a61  mov     rbx, rcx
0x140014a64  jz      short loc_140014A83
0x140014a66  xor     edx, edx; Val
0x140014a68  lea     rcx, [rsp+0C8h+var_A8]; void *
0x140014a6d  mov     r8d, 98h; Size
0x140014a73  call    memset_0
0x140014a78  lea     rcx, [rsp+0C8h+var_A8]; this
0x140014a7d  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x140014a83  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x140014a8b  jz      short loc_140014AB1
0x140014a8d  mov     dl, 1
0x140014a8f  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x140014a94  mov     [rbx], rax
0x140014a97  test    rax, rax
0x140014a9a  jz      short loc_140014AB8
0x140014a9c  mov     rcx, [rax]
0x140014a9f  mov     [rbx+10h], rcx
0x140014aa3  mov     [rax], rbx
0x140014aa6  call    cs:__imp_GetCurrentThreadId
0x140014aac  mov     [rbx+18h], eax
0x140014aaf  jmp     short loc_140014AB8
0x140014ab1  mov     qword ptr [rcx], 0
0x140014ab8  add     rsp, 0C0h
0x140014abf  pop     rbx
0x140014ac0  retn
```
