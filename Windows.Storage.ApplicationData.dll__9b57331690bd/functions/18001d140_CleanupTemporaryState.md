# CleanupTemporaryState

- ea: `0x18001d140`
- end: `0x18001d211`
- name: `CleanupTemporaryState`
- size: `209`
- prototype: `void()`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x18001d140`
- `0x180024138`
- `0x180028924`
- `0x18004107c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001d154`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001d198`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001d1d8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001d154`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001d198`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001d1d8`
- `ntdll!NtSetInformationThread` at `0x18001d1b0`
- `ntdll!NtSetInformationThread` at `0x18001d1f0`
- `ntdll!NtSetInformationThread` at `0x18001d1b0`
- `ntdll!NtSetInformationThread` at `0x18001d1f0`
- `ntdll!NtQueryInformationThread` at `0x18001d175`
- `ntdll!NtQueryInformationThread` at `0x18001d175`

## pseudocode

```c
void CleanupTemporaryState()
{
  HANDLE CurrentThread; // rax
  NTSTATUS v1; // eax
  const char *v2; // r8
  HANDLE v3; // rax
  NTSTATUS v4; // eax
  const char *v5; // r8
  HANDLE v6; // rax
  NTSTATUS v7; // eax
  const char *v8; // r8
  void *retaddr; // [rsp+38h] [rbp+0h]
  _MEMORY_PRIORITY_INFORMATION memPriOriginal; // [rsp+40h] [rbp+8h] BYREF
  _MEMORY_PRIORITY_INFORMATION memPriLow; // [rsp+48h] [rbp+10h] BYREF

  memPriLow.MemoryPriority = 2;
  memPriOriginal.MemoryPriority = 0;
  CurrentThread = GetCurrentThread();
  v1 = NtQueryInformationThread(CurrentThread, ThreadPagePriority, &memPriOriginal, 4u, 0);
  if ( v1 >= 0 )
  {
    v3 = GetCurrentThread();
    v4 = NtSetInformationThread(v3, ThreadPagePriority, &memPriLow, 4u);
    if ( v4 >= 0 )
    {
      anonymous_namespace_::TempCleanup::Cleanup();
    }
    else
    {
      wil::details::in1diag3::_Log_NtStatus(retaddr, 0x17Fu, v5, v4);
      Windows::Storage::StateABIHelpers::Logging::LogTempCleanupAborted();
    }
    v6 = GetCurrentThread();
    v7 = NtSetInformationThread(v6, ThreadPagePriority, &memPriOriginal, 4u);
    if ( v7 < 0 )
      wil::details::in1diag3::_Log_NtStatus(retaddr, 0x188u, v8, v7);
  }
  else
  {
    wil::details::in1diag3::_Log_NtStatus(retaddr, 0x17Du, v2, v1);
    Windows::Storage::StateABIHelpers::Logging::LogTempCleanupAborted();
  }
}

```

## disassembly

```asm
0x18001d140  sub     rsp, 38h
0x18001d144  mov     [rsp+38h+memPriLow.MemoryPriority], 2
0x18001d14c  mov     [rsp+38h+memPriOriginal.MemoryPriority], 0
0x18001d154  call    cs:__imp_GetCurrentThread
0x18001d15a  mov     r9d, 4; ThreadInformationLength
0x18001d160  mov     [rsp+38h+ReturnLength], 0; ReturnLength
0x18001d169  mov     rcx, rax; ThreadHandle
0x18001d16c  lea     r8, [rsp+38h+memPriOriginal]; ThreadInformation
0x18001d171  lea     edx, [r9+14h]; ThreadInformationClass
0x18001d175  call    cs:__imp_NtQueryInformationThread
0x18001d17b  test    eax, eax
0x18001d17d  jns     short loc_18001D198
0x18001d17f  mov     rcx, [rsp+38h]; callerReturnAddress
0x18001d184  mov     r9d, eax; callerReturnAddress
0x18001d187  mov     edx, 17Dh; lineNumber
0x18001d18c  call    ?_Log_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_NtStatus(void *,uint,char const *,long)
0x18001d191  call    ?LogTempCleanupAborted@Logging@StateABIHelpers@Storage@Windows@@SAJXZ; Windows::Storage::StateABIHelpers::Logging::LogTempCleanupAborted(void)
0x18001d196  jmp     short loc_18001D20C
0x18001d198  call    cs:__imp_GetCurrentThread
0x18001d19e  mov     r9d, 4; ThreadInformationLength
0x18001d1a4  lea     r8, [rsp+38h+memPriLow]; ThreadInformation
0x18001d1a9  mov     rcx, rax; ThreadHandle
0x18001d1ac  lea     edx, [r9+14h]; ThreadInformationClass
0x18001d1b0  call    cs:__imp_NtSetInformationThread
0x18001d1b6  test    eax, eax
0x18001d1b8  jns     short loc_18001D1D3
0x18001d1ba  mov     rcx, [rsp+38h]; callerReturnAddress
0x18001d1bf  mov     r9d, eax; callerReturnAddress
0x18001d1c2  mov     edx, 17Fh; lineNumber
0x18001d1c7  call    ?_Log_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_NtStatus(void *,uint,char const *,long)
0x18001d1cc  call    ?LogTempCleanupAborted@Logging@StateABIHelpers@Storage@Windows@@SAJXZ; Windows::Storage::StateABIHelpers::Logging::LogTempCleanupAborted(void)
0x18001d1d1  jmp     short loc_18001D1D8
0x18001d1d3  call    _anonymous_namespace___TempCleanup__Cleanup
0x18001d1d8  call    cs:__imp_GetCurrentThread
0x18001d1de  mov     r9d, 4; ThreadInformationLength
0x18001d1e4  lea     r8, [rsp+38h+memPriOriginal]; ThreadInformation
0x18001d1e9  mov     rcx, rax; ThreadHandle
0x18001d1ec  lea     edx, [r9+14h]; ThreadInformationClass
0x18001d1f0  call    cs:__imp_NtSetInformationThread
0x18001d1f6  test    eax, eax
0x18001d1f8  jns     short loc_18001D20C
0x18001d1fa  mov     rcx, [rsp+38h]; callerReturnAddress
0x18001d1ff  mov     r9d, eax; callerReturnAddress
0x18001d202  mov     edx, 188h; lineNumber
0x18001d207  call    ?_Log_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_NtStatus(void *,uint,char const *,long)
0x18001d20c  add     rsp, 38h
0x18001d210  retn
```
