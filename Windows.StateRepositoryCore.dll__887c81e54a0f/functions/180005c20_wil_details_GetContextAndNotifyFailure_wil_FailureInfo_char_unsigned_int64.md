# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180005c20`
- end: `0x180005c84`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `100`
- prototype: `void __fastcall(wil::details *this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180005b54`
- `0x180005c20`
- `0x180006b04`
- `0x180009940`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005c2e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005c2e`

## pseudocode

```c
void __fastcall wil::details::GetContextAndNotifyFailure(wil::details *this, struct wil::FailureInfo *a2, char *a3)
{
  DWORD CurrentThreadId; // eax
  wil::details_abi *v5; // rcx
  int v6; // edx
  wil::details_abi::ThreadLocalData *ThreadLocalDataCache; // rax

  wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(this, (char *)a2, (unsigned __int64)a3);
  CurrentThreadId = GetCurrentThreadId();
  if ( `wil::SetLastError'::`2'::lastThread != CurrentThreadId )
  {
    v6 = _InterlockedIncrement(&`wil::SetLastError'::`5'::depth);
    if ( v6 < 4 )
    {
      `wil::SetLastError'::`2'::lastThread = CurrentThreadId;
      ThreadLocalDataCache = wil::details_abi::GetThreadLocalDataCache(v5, v6);
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
0x180005c20  push    rbx
0x180005c22  sub     rsp, 20h
0x180005c26  mov     rbx, rcx
0x180005c29  call    ?GetContextAndNotifyFailure@ThreadFailureCallbackHolder@details@wil@@SAXPEAUFailureInfo@3@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)
0x180005c2e  call    cs:__imp_GetCurrentThreadId
0x180005c34  mov     edx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180005c3a  cmp     edx, eax
0x180005c3c  jz      short loc_180005C7E
0x180005c3e  mov     edx, 1
0x180005c43  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, edx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180005c4b  inc     edx; bool
0x180005c4d  cmp     edx, 4
0x180005c50  jge     short loc_180005C77
0x180005c52  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180005c58  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x180005c5d  test    rax, rax
0x180005c60  jz      short loc_180005C6D
0x180005c62  mov     rdx, rbx; struct wil::FailureInfo *
0x180005c65  mov     rcx, rax; this
0x180005c68  call    ?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z; wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)
0x180005c6d  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180005c77  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180005c7e  add     rsp, 20h
0x180005c82  pop     rbx
0x180005c83  retn
```
