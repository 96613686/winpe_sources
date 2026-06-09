# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x140005470`
- end: `0x1400054db`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `107`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x1400053a4`
- `0x140005470`
- `0x140005c7c`
- `0x140007088`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000547e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000547e`

## pseudocode

```c
void __fastcall wil::details::GetContextAndNotifyFailure(wil::details *this, struct wil::FailureInfo *a2, char *a3)
{
  DWORD CurrentThreadId; // eax
  wil::details_abi *v5; // rcx
  wil::details_abi::ThreadLocalData *ThreadLocalDataCache; // rax

  wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(this, (char *)a2, (unsigned __int64)a3);
  CurrentThreadId = GetCurrentThreadId();
  if ( `wil::SetLastError'::`2'::lastThread != CurrentThreadId )
  {
    if ( _InterlockedIncrement(&`wil::SetLastError'::`5'::depth) < 4 )
    {
      `wil::SetLastError'::`2'::lastThread = CurrentThreadId;
      ThreadLocalDataCache = wil::details_abi::GetThreadLocalDataCache(v5);
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
0x140005470  push    rbx
0x140005472  sub     rsp, 20h
0x140005476  mov     rbx, rcx
0x140005479  call    ?GetContextAndNotifyFailure@ThreadFailureCallbackHolder@details@wil@@SAXPEAUFailureInfo@3@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)
0x14000547e  call    cs:__imp_GetCurrentThreadId
0x140005485  nop     dword ptr [rax+rax+00h]
0x14000548a  mov     edx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x140005490  cmp     edx, eax
0x140005492  jz      short loc_1400054D4
0x140005494  mov     edx, 1
0x140005499  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, edx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x1400054a1  inc     edx; bool
0x1400054a3  cmp     edx, 4
0x1400054a6  jge     short loc_1400054CD
0x1400054a8  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1400054ae  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x1400054b3  test    rax, rax
0x1400054b6  jz      short loc_1400054C3
0x1400054b8  mov     rdx, rbx; struct wil::FailureInfo *
0x1400054bb  mov     rcx, rax; this
0x1400054be  call    ?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z; wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)
0x1400054c3  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1400054cd  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x1400054d4  add     rsp, 20h
0x1400054d8  pop     rbx
0x1400054d9  retn
```
