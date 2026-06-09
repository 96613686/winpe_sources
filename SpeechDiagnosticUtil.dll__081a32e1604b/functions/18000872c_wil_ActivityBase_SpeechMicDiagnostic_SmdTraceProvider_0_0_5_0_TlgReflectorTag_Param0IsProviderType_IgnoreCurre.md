# wil::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)

- ea: `0x18000872c`
- end: `0x1800087a7`
- name: `?IgnoreCurrentThread@?$ActivityBase@VSmdTraceProvider@SpeechMicDiagnostic@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ`
- size: `123`
- prototype: ``
- caller_count: `15`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000a964`
- `0x18000ac60`
- `0x18000af58`
- `0x18000b26c`
- `0x18000b590`
- `0x18000b888`
- `0x18000bb90`
- `0x18000be20`
- `0x18000c0b0`
- `0x18000c340`
- `0x18000c5d0`
- `0x18000c860`
- `0x18000caf0`
- `0x18000cd80`
- `0x18000d010`

## callees

- `0x18000872c`
- `0x180011010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180008742`
- `KERNEL32!GetCurrentThreadId` at `0x180008742`

## string_xrefs

- `0x180008764`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

## pseudocode

```c
void __fastcall wil::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
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
0x18000872c  push    rbx
0x18000872e  sub     rsp, 20h
0x180008732  cmp     dword ptr [rcx+138h], 0
0x180008739  jz      short loc_1800087A0
0x18000873b  lea     rbx, [rcx+120h]
0x180008742  call    cs:__imp_GetCurrentThreadId
0x180008749  nop     dword ptr [rax+rax+00h]
0x18000874e  cmp     [rbx+18h], eax
0x180008751  jz      short loc_180008770
0x180008753  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x18000875a  test    rax, rax
0x18000875d  jz      short loc_180008770
0x18000875f  mov     rdx, [rsp+28h]
0x180008764  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x18000876b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008770  mov     dword ptr [rbx+18h], 0
0x180008777  mov     rcx, [rbx]
0x18000877a  jmp     short loc_180008788
0x18000877c  cmp     rax, rbx
0x18000877f  jz      short loc_180008792
0x180008781  lea     rcx, [rax+10h]
0x180008785  mov     [rbx], rcx
0x180008788  mov     rax, [rcx]
0x18000878b  test    rax, rax
0x18000878e  jnz     short loc_18000877C
0x180008790  jmp     short loc_180008799
0x180008792  mov     rax, [rbx+10h]
0x180008796  mov     [rcx], rax
0x180008799  mov     qword ptr [rbx], 0
0x1800087a0  add     rsp, 20h
0x1800087a4  pop     rbx
0x1800087a5  retn
```
