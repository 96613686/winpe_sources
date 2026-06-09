# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x140004420`
- end: `0x14000448b`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `107`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x140004354`
- `0x140004420`
- `0x14000516c`
- `0x140006a30`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000442e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000442e`

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
0x140004420  push    rbx
0x140004422  sub     rsp, 20h
0x140004426  mov     rbx, rcx
0x140004429  call    ?GetContextAndNotifyFailure@ThreadFailureCallbackHolder@details@wil@@SAXPEAUFailureInfo@3@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)
0x14000442e  call    cs:__imp_GetCurrentThreadId
0x140004435  nop     dword ptr [rax+rax+00h]
0x14000443a  mov     edx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x140004440  cmp     edx, eax
0x140004442  jz      short loc_140004484
0x140004444  mov     edx, 1
0x140004449  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, edx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x140004451  inc     edx; bool
0x140004453  cmp     edx, 4
0x140004456  jge     short loc_14000447D
0x140004458  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x14000445e  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x140004463  test    rax, rax
0x140004466  jz      short loc_140004473
0x140004468  mov     rdx, rbx; struct wil::FailureInfo *
0x14000446b  mov     rcx, rax; this
0x14000446e  call    ?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z; wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)
0x140004473  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x14000447d  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x140004484  add     rsp, 20h
0x140004488  pop     rbx
0x140004489  retn
```
