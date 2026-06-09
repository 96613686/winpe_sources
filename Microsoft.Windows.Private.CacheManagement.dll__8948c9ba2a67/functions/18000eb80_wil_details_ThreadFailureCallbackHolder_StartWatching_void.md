# wil::details::ThreadFailureCallbackHolder::StartWatching(void)

- ea: `0x18000eb80`
- end: `0x18000ec25`
- name: `?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `165`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000e830`

## callees

- `0x180002f90`
- `0x18000eab0`
- `0x18000eb80`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18000ebb5`
- `KERNEL32!GetCurrentThreadId` at `0x18000ebb5`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall wil::details::ThreadFailureCallbackHolder::StartWatching(
        wil::details::ThreadFailureCallbackHolder *this,
        const struct wil::FailureInfo *a2)
{
  _QWORD *Local; // rax
  _OWORD v4[9]; // [rsp+20h] [rbp-A8h] BYREF
  __int64 v5; // [rsp+B0h] [rbp-18h]

  if ( *((_DWORD *)this + 6) )
  {
    memset(v4, 0, sizeof(v4));
    v5 = 0;
    wil::details::WilFailFast((wil::details *)v4, a2);
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
0x18000eb80  push    rbx
0x18000eb82  sub     rsp, 0C0h
0x18000eb89  cmp     dword ptr [rcx+18h], 0
0x18000eb8d  mov     rbx, rcx
0x18000eb90  jnz     short loc_18000EBD7
0x18000eb92  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000eb9a  jz      short loc_18000EBC7
0x18000eb9c  mov     dl, 1
0x18000eb9e  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x18000eba3  mov     [rbx], rax
0x18000eba6  test    rax, rax
0x18000eba9  jz      short loc_18000EBCE
0x18000ebab  mov     rcx, [rax]
0x18000ebae  mov     [rbx+10h], rcx
0x18000ebb2  mov     [rax], rbx
0x18000ebb5  call    cs:__imp_GetCurrentThreadId
0x18000ebbb  mov     [rbx+18h], eax
0x18000ebbe  add     rsp, 0C0h
0x18000ebc5  pop     rbx
0x18000ebc6  retn
0x18000ebc7  mov     qword ptr [rcx], 0
0x18000ebce  add     rsp, 0C0h
0x18000ebd5  pop     rbx
0x18000ebd6  retn
0x18000ebd7  xorps   xmm0, xmm0
0x18000ebda  lea     rcx, [rsp+0C8h+var_A8]; this
0x18000ebdf  xor     eax, eax
0x18000ebe1  movups  [rsp+0C8h+var_A8], xmm0
0x18000ebe6  mov     [rsp+0C8h+var_18], rax
0x18000ebee  movups  [rsp+0C8h+var_98], xmm0
0x18000ebf3  movups  [rsp+0C8h+var_88], xmm0
0x18000ebf8  movups  [rsp+0C8h+var_78], xmm0
0x18000ebfd  movups  [rsp+0C8h+var_68], xmm0
0x18000ec02  movups  [rsp+0C8h+var_58], xmm0
0x18000ec07  movups  [rsp+0C8h+var_48], xmm0
0x18000ec0f  movups  [rsp+0C8h+var_38], xmm0
0x18000ec17  movups  [rsp+0C8h+var_28], xmm0
0x18000ec1f  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
