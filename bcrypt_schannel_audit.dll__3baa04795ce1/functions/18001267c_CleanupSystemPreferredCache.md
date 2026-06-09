# CleanupSystemPreferredCache

- ea: `0x18001267c`
- end: `0x180012771`
- name: `CleanupSystemPreferredCache`
- size: `245`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x180009764`
- `0x180016068`

## callees

- `0x180005b00`
- `0x180009430`
- `0x18001267c`
- `0x180019b1c`

## import_xrefs

- `ntdll!RtlDeleteCriticalSection` at `0x180012748`
- `ntdll!RtlDeleteCriticalSection` at `0x180012748`
- `ntdll!RtlDeleteResource` at `0x180012719`
- `ntdll!RtlDeleteResource` at `0x180012719`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x180012690`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x180012690`

## pseudocode

```c
int CleanupSystemPreferredCache()
{
  int result; // eax

  if ( WaitHandle )
  {
    result = UnregisterWaitEx(WaitHandle, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
    WaitHandle = 0;
  }
  if ( hAlgorithm )
  {
    result = BCryptCloseAlgorithmProvider(hAlgorithm, 0);
    hAlgorithm = 0;
  }
  if ( qword_180024AA8 )
  {
    result = BCryptCloseAlgorithmProvider(qword_180024AA8, 0);
    qword_180024AA8 = 0;
  }
  if ( dword_180024AA4 )
  {
    result = BcpUnregisterConfigChangeNotifyNoLogging(qword_180024AF0);
    qword_180024AF0 = 0;
    dword_180024AA4 = 0;
  }
  if ( g_pCachedRngRWLock )
  {
    RtlDeleteResource(g_pCachedRngRWLock);
    result = MSCryptFree(g_pCachedRngRWLock);
    g_pCachedRngRWLock = 0;
  }
  if ( CriticalSection )
  {
    RtlDeleteCriticalSection(CriticalSection);
    result = MSCryptFree(CriticalSection);
    CriticalSection = 0;
  }
  return result;
}

```

## disassembly

```asm
0x18001267c  sub     rsp, 28h
0x180012680  mov     rcx, cs:WaitHandle; WaitHandle
0x180012687  test    rcx, rcx
0x18001268a  jz      short loc_1800126A7
0x18001268c  or      rdx, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x180012690  call    cs:__imp_UnregisterWaitEx
0x180012697  nop     dword ptr [rax+rax+00h]
0x18001269c  mov     cs:WaitHandle, 0
0x1800126a7  mov     rcx, cs:hAlgorithm; hAlgorithm
0x1800126ae  test    rcx, rcx
0x1800126b1  jz      short loc_1800126C5
0x1800126b3  xor     edx, edx; dwFlags
0x1800126b5  call    BCryptCloseAlgorithmProvider
0x1800126ba  mov     cs:hAlgorithm, 0
0x1800126c5  mov     rcx, cs:qword_180024AA8; hAlgorithm
0x1800126cc  test    rcx, rcx
0x1800126cf  jz      short loc_1800126E3
0x1800126d1  xor     edx, edx; dwFlags
0x1800126d3  call    BCryptCloseAlgorithmProvider
0x1800126d8  mov     cs:qword_180024AA8, 0
0x1800126e3  cmp     cs:dword_180024AA4, 0
0x1800126ea  jz      short loc_18001270D
0x1800126ec  mov     rcx, cs:qword_180024AF0; void *
0x1800126f3  call    BcpUnregisterConfigChangeNotifyNoLogging
0x1800126f8  mov     cs:qword_180024AF0, 0
0x180012703  mov     cs:dword_180024AA4, 0
0x18001270d  mov     rcx, cs:g_pCachedRngRWLock; Resource
0x180012714  test    rcx, rcx
0x180012717  jz      short loc_18001273C
0x180012719  call    cs:__imp_RtlDeleteResource
0x180012720  nop     dword ptr [rax+rax+00h]
0x180012725  mov     rcx, cs:g_pCachedRngRWLock
0x18001272c  call    MSCryptFree
0x180012731  mov     cs:g_pCachedRngRWLock, 0
0x18001273c  mov     rcx, cs:CriticalSection; CriticalSection
0x180012743  test    rcx, rcx
0x180012746  jz      short loc_18001276B
0x180012748  call    cs:__imp_RtlDeleteCriticalSection
0x18001274f  nop     dword ptr [rax+rax+00h]
0x180012754  mov     rcx, cs:CriticalSection
0x18001275b  call    MSCryptFree
0x180012760  mov     cs:CriticalSection, 0
0x18001276b  add     rsp, 28h
0x18001276f  retn
```
