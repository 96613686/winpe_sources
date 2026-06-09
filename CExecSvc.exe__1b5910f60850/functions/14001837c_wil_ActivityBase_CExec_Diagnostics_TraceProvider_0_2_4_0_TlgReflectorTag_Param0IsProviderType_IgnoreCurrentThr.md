# wil::ActivityBase<CExec::Diagnostics::TraceProvider,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)

- ea: `0x14001837c`
- end: `0x1400183f0`
- name: `?IgnoreCurrentThread@?$ActivityBase@VTraceProvider@Diagnostics@CExec@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ`
- size: `116`
- prototype: `void __fastcall(__int64)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140019a9c`
- `0x140019bd0`
- `0x140019ea0`
- `0x14001a170`

## callees

- `0x14001837c`
- `0x140024010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140018392`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140018392`

## string_xrefs

- `0x1400183ae`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

## pseudocode

```c
void __fastcall wil::ActivityBase<CExec::Diagnostics::TraceProvider,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
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
0x14001837c  push    rbx
0x14001837e  sub     rsp, 20h
0x140018382  cmp     dword ptr [rcx+138h], 0
0x140018389  jz      short loc_1400183EA
0x14001838b  lea     rbx, [rcx+120h]
0x140018392  call    cs:__imp_GetCurrentThreadId
0x140018398  cmp     [rbx+18h], eax
0x14001839b  jz      short loc_1400183BA
0x14001839d  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x1400183a4  test    rax, rax
0x1400183a7  jz      short loc_1400183BA
0x1400183a9  mov     rdx, [rsp+28h]
0x1400183ae  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x1400183b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400183ba  mov     dword ptr [rbx+18h], 0
0x1400183c1  mov     rcx, [rbx]
0x1400183c4  jmp     short loc_1400183D2
0x1400183c6  cmp     rax, rbx
0x1400183c9  jz      short loc_1400183DC
0x1400183cb  lea     rcx, [rax+10h]
0x1400183cf  mov     [rbx], rcx
0x1400183d2  mov     rax, [rcx]
0x1400183d5  test    rax, rax
0x1400183d8  jnz     short loc_1400183C6
0x1400183da  jmp     short loc_1400183E3
0x1400183dc  mov     rax, [rbx+10h]
0x1400183e0  mov     [rcx], rax
0x1400183e3  mov     qword ptr [rbx], 0
0x1400183ea  add     rsp, 20h
0x1400183ee  pop     rbx
0x1400183ef  retn
```
