# wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)

- ea: `0x180018c84`
- end: `0x180018cf8`
- name: `?IgnoreCurrentThread@?$ActivityBase@VMtfPlatformTelemetry@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ`
- size: `116`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x18001b8f4`
- `0x18001ba00`
- `0x18001bc80`
- `0x18001bf00`
- `0x18001c180`
- `0x18001c400`

## callees

- `0x180018c84`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018c9a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018c9a`

## string_xrefs

- `0x180018cb6`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

## pseudocode

```c
void __fastcall wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
        __int64 a1)
{
  __int64 v1; // rbx
  __int64 *v2; // rcx
  __int64 v3; // rax
  void *retaddr; // [rsp+28h] [rbp+0h]

  if ( *(_DWORD *)(a1 + 312) )
  {
    v1 = a1 + 288;
    if ( *(_DWORD *)(a1 + 312) != GetCurrentThreadId() )
    {
      if ( wil::details::g_pfnReportFatalUsageError )
        wil::details::g_pfnReportFatalUsageError(
          "MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread",
          retaddr);
    }
    *(_DWORD *)(v1 + 24) = 0;
    v2 = *(__int64 **)v1;
    while ( 1 )
    {
      v3 = *v2;
      if ( !*v2 )
        break;
      if ( v3 == v1 )
      {
        *v2 = *(_QWORD *)(v1 + 16);
        break;
      }
      v2 = (__int64 *)(v3 + 16);
      *(_QWORD *)v1 = v3 + 16;
    }
    *(_QWORD *)v1 = 0;
  }
}

```

## disassembly

```asm
0x180018c84  push    rbx
0x180018c86  sub     rsp, 20h
0x180018c8a  cmp     dword ptr [rcx+138h], 0
0x180018c91  jz      short loc_180018CF2
0x180018c93  lea     rbx, [rcx+120h]
0x180018c9a  call    cs:__imp_GetCurrentThreadId
0x180018ca0  cmp     [rbx+18h], eax
0x180018ca3  jz      short loc_180018CC2
0x180018ca5  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x180018cac  test    rax, rax
0x180018caf  jz      short loc_180018CC2
0x180018cb1  mov     rdx, [rsp+28h]
0x180018cb6  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x180018cbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018cc2  mov     dword ptr [rbx+18h], 0
0x180018cc9  mov     rcx, [rbx]
0x180018ccc  jmp     short loc_180018CDA
0x180018cce  cmp     rax, rbx
0x180018cd1  jz      short loc_180018CE4
0x180018cd3  lea     rcx, [rax+10h]
0x180018cd7  mov     [rbx], rcx
0x180018cda  mov     rax, [rcx]
0x180018cdd  test    rax, rax
0x180018ce0  jnz     short loc_180018CCE
0x180018ce2  jmp     short loc_180018CEB
0x180018ce4  mov     rax, [rbx+10h]
0x180018ce8  mov     [rcx], rax
0x180018ceb  mov     qword ptr [rbx], 0
0x180018cf2  add     rsp, 20h
0x180018cf6  pop     rbx
0x180018cf7  retn
```
