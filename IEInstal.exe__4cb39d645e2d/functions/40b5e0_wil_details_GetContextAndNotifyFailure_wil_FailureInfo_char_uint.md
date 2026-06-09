# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,uint)

- ea: `0x40b5e0`
- end: `0x40b63f`
- name: `?GetContextAndNotifyFailure@details@wil@@YGXPAUFailureInfo@2@PADI@Z`
- size: `95`
- prototype: `void(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x40b2ec`
- `0x40b3a7`
- `0x40b4f0`
- `0x40b5e0`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x40b5f3`
- `KERNEL32!GetCurrentThreadId` at `0x40b5f3`

## pseudocode

```c

```

## disassembly

```asm
0x40b5e0  mov     edi, edi
0x40b5e2  push    ebp; this
0x40b5e3  mov     ebp, esp
0x40b5e5  push    [ebp+arg_8]; struct wil::FailureInfo *
0x40b5e8  mov     edx, [ebp+arg_4]
0x40b5eb  mov     ecx, [ebp+this]
0x40b5ee  call    ?GetContextAndNotifyFailure@ThreadFailureCallbackHolder@details@wil@@SGXPAUFailureInfo@3@PADI@Z; wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(wil::FailureInfo *,char *,uint)
0x40b5f3  call    ds:__imp__GetCurrentThreadId@0; GetCurrentThreadId()
0x40b5f9  cmp     ?lastThread@?1??SetLastError@wil@@YGXABUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x40b5ff  jz      short loc_40B63B
0x40b601  xor     ecx, ecx
0x40b603  inc     ecx
0x40b604  lock xadd ?depth@?4??SetLastError@wil@@YGXABUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x40b60c  inc     ecx
0x40b60d  cmp     ecx, 4
0x40b610  jge     short loc_40B634
0x40b612  mov     ?lastThread@?1??SetLastError@wil@@YGXABUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x40b617  call    ?GetThreadLocalDataCache@details_abi@wil@@YGPAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x40b61c  test    eax, eax
0x40b61e  jz      short loc_40B62A
0x40b620  push    [ebp+this]; struct wil::FailureInfo *
0x40b623  mov     ecx, eax; this
0x40b625  call    ?SetLastError@ThreadLocalData@details_abi@wil@@QAEXABUFailureInfo@3@@Z; wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)
0x40b62a  mov     ?lastThread@?1??SetLastError@wil@@YGXABUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x40b634  lock dec ?depth@?4??SetLastError@wil@@YGXABUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x40b63b  pop     ebp
0x40b63c  retn    0Ch
```
