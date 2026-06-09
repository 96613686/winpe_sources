# wil::ActivityBase<AutoPilotTelemProvider,1,140737488355328,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)

- ea: `0x1800159d4`
- end: `0x180015a48`
- name: `?IgnoreCurrentThread@?$ActivityBase@VAutoPilotTelemProvider@@$00$0IAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ`
- size: `116`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800169c0`
- `0x180016e50`

## callees

- `0x1800159d4`
- `0x18002e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800159ea`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800159ea`

## string_xrefs

- `0x180015a06`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

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
0x1800159d4  push    rbx
0x1800159d6  sub     rsp, 20h
0x1800159da  cmp     dword ptr [rcx+138h], 0
0x1800159e1  jz      short loc_180015A42
0x1800159e3  lea     rbx, [rcx+120h]
0x1800159ea  call    cs:__imp_GetCurrentThreadId
0x1800159f0  cmp     [rbx+18h], eax
0x1800159f3  jz      short loc_180015A12
0x1800159f5  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA; __annotation("Debug", "TelemetryAssert", "MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread")
0x1800159fc  test    rax, rax
0x1800159ff  jz      short loc_180015A12
0x180015a01  mov     rdx, [rsp+28h]
0x180015a06  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x180015a0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015a12  mov     dword ptr [rbx+18h], 0
0x180015a19  mov     rcx, [rbx]
0x180015a1c  jmp     short loc_180015A2A
0x180015a1e  cmp     rax, rbx
0x180015a21  jz      short loc_180015A34
0x180015a23  lea     rcx, [rax+10h]
0x180015a27  mov     [rbx], rcx
0x180015a2a  mov     rax, [rcx]
0x180015a2d  test    rax, rax
0x180015a30  jnz     short loc_180015A1E
0x180015a32  jmp     short loc_180015A3B
0x180015a34  mov     rax, [rbx+10h]
0x180015a38  mov     [rcx], rax
0x180015a3b  mov     qword ptr [rbx], 0
0x180015a42  add     rsp, 20h
0x180015a46  pop     rbx
0x180015a47  retn
```
