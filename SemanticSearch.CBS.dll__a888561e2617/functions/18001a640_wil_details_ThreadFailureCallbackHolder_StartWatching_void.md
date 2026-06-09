# wil::details::ThreadFailureCallbackHolder::StartWatching(void)

- ea: `0x18001a640`
- end: `0x18001a6e5`
- name: `?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `165`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x180052c90`
- `0x180053610`
- `0x1800583b0`
- `0x18005bc90`

## callees

- `0x1800168c0`
- `0x18001a570`
- `0x18001a640`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18001a675`
- `KERNEL32!GetCurrentThreadId` at `0x18001a675`

## pseudocode

```c
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
0x18001a640  push    rbx
0x18001a642  sub     rsp, 0C0h
0x18001a649  cmp     dword ptr [rcx+18h], 0
0x18001a64d  mov     rbx, rcx
0x18001a650  jnz     short loc_18001A697
0x18001a652  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18001a65a  jz      short loc_18001A687
0x18001a65c  mov     dl, 1
0x18001a65e  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x18001a663  mov     [rbx], rax
0x18001a666  test    rax, rax
0x18001a669  jz      short loc_18001A68E
0x18001a66b  mov     rcx, [rax]
0x18001a66e  mov     [rbx+10h], rcx
0x18001a672  mov     [rax], rbx
0x18001a675  call    cs:__imp_GetCurrentThreadId
0x18001a67b  mov     [rbx+18h], eax
0x18001a67e  add     rsp, 0C0h
0x18001a685  pop     rbx
0x18001a686  retn
0x18001a687  mov     qword ptr [rcx], 0
0x18001a68e  add     rsp, 0C0h
0x18001a695  pop     rbx
0x18001a696  retn
0x18001a697  xorps   xmm0, xmm0
0x18001a69a  lea     rcx, [rsp+0C8h+var_A8]; this
0x18001a69f  xor     eax, eax
0x18001a6a1  movups  [rsp+0C8h+var_A8], xmm0
0x18001a6a6  mov     [rsp+0C8h+var_18], rax
0x18001a6ae  movups  [rsp+0C8h+var_98], xmm0
0x18001a6b3  movups  [rsp+0C8h+var_88], xmm0
0x18001a6b8  movups  [rsp+0C8h+var_78], xmm0
0x18001a6bd  movups  [rsp+0C8h+var_68], xmm0
0x18001a6c2  movups  [rsp+0C8h+var_58], xmm0
0x18001a6c7  movups  [rsp+0C8h+var_48], xmm0
0x18001a6cf  movups  [rsp+0C8h+var_38], xmm0
0x18001a6d7  movups  [rsp+0C8h+var_28], xmm0
0x18001a6df  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
