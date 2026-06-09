# wil::SetLastError(wil::FailureInfo const &)

- ea: `0x140007244`
- end: `0x1400072a3`
- name: `?SetLastError@wil@@YAXAEBUFailureInfo@1@@Z`
- size: `95`
- prototype: `void __fastcall(wil *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140007160`

## callees

- `0x140007244`
- `0x1400072ac`
- `0x14000c824`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000724d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000724d`

## pseudocode

```c
void __fastcall wil::SetLastError(wil *this, const struct wil::FailureInfo *a2)
{
  DWORD CurrentThreadId; // eax
  wil::details_abi *v4; // rcx
  int v5; // edx
  wil::details_abi::ThreadLocalData *ThreadLocalDataCache; // rax

  CurrentThreadId = GetCurrentThreadId();
  if ( `wil::SetLastError'::`2'::lastThread != CurrentThreadId )
  {
    v5 = _InterlockedIncrement(&`wil::SetLastError'::`5'::depth);
    if ( v5 < 4 )
    {
      `wil::SetLastError'::`2'::lastThread = CurrentThreadId;
      ThreadLocalDataCache = wil::details_abi::GetThreadLocalDataCache(v4, v5);
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
0x140007244  push    rbx
0x140007246  sub     rsp, 20h
0x14000724a  mov     rbx, rcx
0x14000724d  call    cs:__imp_GetCurrentThreadId
0x140007253  mov     edx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x140007259  cmp     edx, eax
0x14000725b  jz      short loc_14000729D
0x14000725d  mov     edx, 1
0x140007262  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, edx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x14000726a  inc     edx; bool
0x14000726c  cmp     edx, 4
0x14000726f  jge     short loc_140007296
0x140007271  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x140007277  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x14000727c  test    rax, rax
0x14000727f  jz      short loc_14000728C
0x140007281  mov     rdx, rbx; struct wil::FailureInfo *
0x140007284  mov     rcx, rax; this
0x140007287  call    ?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z; wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)
0x14000728c  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x140007296  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x14000729d  add     rsp, 20h
0x1400072a1  pop     rbx
0x1400072a2  retn
```
