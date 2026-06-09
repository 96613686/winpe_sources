# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x18000b050`
- end: `0x18000b0b4`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `100`
- prototype: `void __fastcall(wil::FailureInfo *pFailure, char *callContextString, unsigned __int64 callContextStringLength)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18000af88`
- `0x18000b050`
- `0x18000b918`
- `0x18000d698`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b05e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b05e`

## pseudocode

```c
void __fastcall wil::details::GetContextAndNotifyFailure(
        wil::FailureInfo *pFailure,
        char *callContextString,
        unsigned __int64 callContextStringLength)
{
  DWORD CurrentThreadId; // eax
  bool v5; // cl
  wil::details_abi::ThreadLocalData *ThreadLocalDataCache; // rax

  wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(
    pFailure,
    callContextString,
    callContextStringLength);
  CurrentThreadId = GetCurrentThreadId();
  if ( `wil::SetLastError'::`2'::lastThread != CurrentThreadId )
  {
    if ( _InterlockedIncrement(&`wil::SetLastError'::`5'::depth) < 4 )
    {
      `wil::SetLastError'::`2'::lastThread = CurrentThreadId;
      ThreadLocalDataCache = wil::details_abi::GetThreadLocalDataCache(v5);
      if ( ThreadLocalDataCache )
        wil::details_abi::ThreadLocalData::SetLastError(ThreadLocalDataCache, pFailure);
      `wil::SetLastError'::`2'::lastThread = 0;
    }
    _InterlockedDecrement(&`wil::SetLastError'::`5'::depth);
  }
}

```

## disassembly

```asm
0x18000b050  push    rbx
0x18000b052  sub     rsp, 20h
0x18000b056  mov     rbx, pFailure
0x18000b059  call    ?GetContextAndNotifyFailure@ThreadFailureCallbackHolder@details@wil@@SAXPEAUFailureInfo@3@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)
0x18000b05e  call    cs:__imp_GetCurrentThreadId
0x18000b064  mov     edx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18000b06a  cmp     edx, eax
0x18000b06c  jz      short loc_18000B0AE
0x18000b06e  mov     edx, 1
0x18000b073  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, edx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000b07b  inc     edx
0x18000b07d  cmp     edx, 4
0x18000b080  jge     short loc_18000B0A7
0x18000b082  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18000b088  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x18000b08d  test    rax, rax
0x18000b090  jz      short loc_18000B09D
0x18000b092  mov     callContextString, rbx; info
0x18000b095  mov     pFailure, rax; this
0x18000b098  call    ?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z; wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)
0x18000b09d  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18000b0a7  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000b0ae  add     rsp, 20h
0x18000b0b2  pop     rbx
0x18000b0b3  retn
```
