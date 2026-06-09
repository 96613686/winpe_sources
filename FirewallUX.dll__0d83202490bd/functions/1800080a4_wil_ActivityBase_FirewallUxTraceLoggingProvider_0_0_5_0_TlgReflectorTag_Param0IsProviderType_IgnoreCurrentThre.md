# wil::ActivityBase<FirewallUxTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)

- ea: `0x1800080a4`
- end: `0x180008118`
- name: `?IgnoreCurrentThread@?$ActivityBase@VFirewallUxTraceLoggingProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ`
- size: `116`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x18000a040`
- `0x180013488`
- `0x1800135a0`
- `0x1800203d0`
- `0x180020650`

## callees

- `0x1800080a4`
- `0x18002d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800080ba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800080ba`

## string_xrefs

- `0x1800080d6`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

## pseudocode

```c
void __fastcall wil::ActivityBase<FirewallUxTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
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
0x1800080a4  push    rbx
0x1800080a6  sub     rsp, 20h
0x1800080aa  cmp     dword ptr [rcx+138h], 0
0x1800080b1  jz      short loc_180008112
0x1800080b3  lea     rbx, [rcx+120h]
0x1800080ba  call    cs:__imp_GetCurrentThreadId
0x1800080c0  cmp     [rbx+18h], eax
0x1800080c3  jz      short loc_1800080E2
0x1800080c5  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x1800080cc  test    rax, rax
0x1800080cf  jz      short loc_1800080E2
0x1800080d1  mov     rdx, [rsp+28h]
0x1800080d6  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x1800080dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800080e2  mov     dword ptr [rbx+18h], 0
0x1800080e9  mov     rcx, [rbx]
0x1800080ec  jmp     short loc_1800080FA
0x1800080ee  cmp     rax, rbx
0x1800080f1  jz      short loc_180008104
0x1800080f3  lea     rcx, [rax+10h]
0x1800080f7  mov     [rbx], rcx
0x1800080fa  mov     rax, [rcx]
0x1800080fd  test    rax, rax
0x180008100  jnz     short loc_1800080EE
0x180008102  jmp     short loc_18000810B
0x180008104  mov     rax, [rbx+10h]
0x180008108  mov     [rcx], rax
0x18000810b  mov     qword ptr [rbx], 0
0x180008112  add     rsp, 20h
0x180008116  pop     rbx
0x180008117  retn
```
