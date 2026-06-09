# wil::SetLastError(wil::FailureInfo const &)

- ea: `0x180009540`
- end: `0x18000959f`
- name: `?SetLastError@wil@@YAXAEBUFailureInfo@1@@Z`
- size: `95`
- prototype: `void __fastcall(wil *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180009450`

## callees

- `0x180009540`
- `0x18000b620`
- `0x18000c734`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009549`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009549`

## pseudocode

```c
void __fastcall wil::SetLastError(wil *this, const struct wil::FailureInfo *a2)
{
  DWORD CurrentThreadId; // eax
  wil::details_abi *v4; // rcx
  wil::details_abi::ThreadLocalData *ThreadLocalDataCache; // rax

  CurrentThreadId = GetCurrentThreadId();
  if ( `wil::SetLastError'::`2'::lastThread != CurrentThreadId )
  {
    if ( _InterlockedIncrement(&`wil::SetLastError'::`5'::depth) < 4 )
    {
      `wil::SetLastError'::`2'::lastThread = CurrentThreadId;
      ThreadLocalDataCache = wil::details_abi::GetThreadLocalDataCache(v4);
      if ( ThreadLocalDataCache )
        wil::details_abi::ThreadLocalData::SetLastError(ThreadLocalDataCache, this);
      `wil::SetLastError'::`2'::lastThread = 0;
    }
    _InterlockedDecrement(&`wil::SetLastError'::`5'::depth);
  }
}

```

## disassembly

```asm
0x180009540  push    rbx
0x180009542  sub     rsp, 20h
0x180009546  mov     rbx, rcx
0x180009549  call    cs:__imp_GetCurrentThreadId
0x18000954f  mov     edx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180009555  cmp     edx, eax
0x180009557  jz      short loc_180009599
0x180009559  mov     edx, 1
0x18000955e  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, edx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180009566  inc     edx; bool
0x180009568  cmp     edx, 4
0x18000956b  jge     short loc_180009592
0x18000956d  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180009573  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x180009578  test    rax, rax
0x18000957b  jz      short loc_180009588
0x18000957d  mov     rdx, rbx; struct wil::FailureInfo *
0x180009580  mov     rcx, rax; this
0x180009583  call    ?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z; wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)
0x180009588  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180009592  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180009599  add     rsp, 20h
0x18000959d  pop     rbx
0x18000959e  retn
```
