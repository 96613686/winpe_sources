# wil::ActivityBase<AutoPilotTelemProvider,1,140737488355328,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)

- ea: `0x180015e10`
- end: `0x180015e8b`
- name: `?IgnoreCurrentThread@?$ActivityBase@VAutoPilotTelemProvider@@$00$0IAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ`
- size: `123`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180016ebc`
- `0x180017360`

## callees

- `0x180015e10`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180015e26`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180015e26`

## string_xrefs

- `0x180015e48`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

## pseudocode

```c
void __fastcall wil::ActivityBase<AutoPilotTelemProvider,1,140737488355328,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
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
0x180015e10  push    rbx
0x180015e12  sub     rsp, 20h
0x180015e16  cmp     dword ptr [rcx+138h], 0
0x180015e1d  jz      short loc_180015E84
0x180015e1f  lea     rbx, [rcx+120h]
0x180015e26  call    cs:__imp_GetCurrentThreadId
0x180015e2d  nop     dword ptr [rax+rax+00h]
0x180015e32  cmp     [rbx+18h], eax
0x180015e35  jz      short loc_180015E54
0x180015e37  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x180015e3e  test    rax, rax
0x180015e41  jz      short loc_180015E54
0x180015e43  mov     rdx, [rsp+28h]
0x180015e48  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x180015e4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015e54  mov     dword ptr [rbx+18h], 0
0x180015e5b  mov     rcx, [rbx]
0x180015e5e  jmp     short loc_180015E6C
0x180015e60  cmp     rax, rbx
0x180015e63  jz      short loc_180015E76
0x180015e65  lea     rcx, [rax+10h]
0x180015e69  mov     [rbx], rcx
0x180015e6c  mov     rax, [rcx]
0x180015e6f  test    rax, rax
0x180015e72  jnz     short loc_180015E60
0x180015e74  jmp     short loc_180015E7D
0x180015e76  mov     rax, [rbx+10h]
0x180015e7a  mov     [rcx], rax
0x180015e7d  mov     qword ptr [rbx], 0
0x180015e84  add     rsp, 20h
0x180015e88  pop     rbx
0x180015e89  retn
```
