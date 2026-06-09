# wil::ActivityBase<DeviceCenterContextHandlersLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)

- ea: `0x180008214`
- end: `0x180008288`
- name: `?IgnoreCurrentThread@?$ActivityBase@VDeviceCenterContextHandlersLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ`
- size: `116`
- prototype: `void __fastcall(__int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000ae3c`
- `0x18000afb0`
- `0x18000b5dc`

## callees

- `0x180008214`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000822a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000822a`

## string_xrefs

- `0x180008246`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

## pseudocode

```c
void __fastcall wil::ActivityBase<DeviceCenterContextHandlersLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
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
    v2 = *(__int64 **)v1;
    *(_DWORD *)(v1 + 24) = 0;
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
0x180008214  push    rbx
0x180008216  sub     rsp, 20h
0x18000821a  cmp     dword ptr [rcx+138h], 0
0x180008221  jz      short loc_180008282
0x180008223  lea     rbx, [rcx+120h]
0x18000822a  call    cs:__imp_GetCurrentThreadId
0x180008230  cmp     [rbx+18h], eax
0x180008233  jz      short loc_180008252
0x180008235  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x18000823c  test    rax, rax
0x18000823f  jz      short loc_180008252
0x180008241  mov     rdx, [rsp+28h]
0x180008246  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x18000824d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008252  mov     rcx, [rbx]
0x180008255  mov     dword ptr [rbx+18h], 0
0x18000825c  jmp     short loc_18000826A
0x18000825e  cmp     rax, rbx
0x180008261  jz      short loc_180008274
0x180008263  lea     rcx, [rax+10h]
0x180008267  mov     [rbx], rcx
0x18000826a  mov     rax, [rcx]
0x18000826d  test    rax, rax
0x180008270  jnz     short loc_18000825E
0x180008272  jmp     short loc_18000827B
0x180008274  mov     rax, [rbx+10h]
0x180008278  mov     [rcx], rax
0x18000827b  mov     qword ptr [rbx], 0
0x180008282  add     rsp, 20h
0x180008286  pop     rbx
0x180008287  retn
```
