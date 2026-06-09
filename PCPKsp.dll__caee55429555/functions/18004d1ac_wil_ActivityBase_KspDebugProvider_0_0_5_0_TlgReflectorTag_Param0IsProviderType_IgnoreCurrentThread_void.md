# wil::ActivityBase<KspDebugProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)

- ea: `0x18004d1ac`
- end: `0x18004d227`
- name: `?IgnoreCurrentThread@?$ActivityBase@VKspDebugProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ`
- size: `123`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18001f2f0`
- `0x18005d000`

## callees

- `0x18004d1ac`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004d1c2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004d1c2`

## string_xrefs

- `0x18004d219`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

## pseudocode

```c
void __fastcall wil::ActivityBase<KspDebugProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
        __int64 a1)
{
  __int64 **v1; // rbx
  __int64 v2; // rax
  void *retaddr; // [rsp+28h] [rbp+0h]

  if ( *(_DWORD *)(a1 + 312) )
  {
    v1 = (__int64 **)(a1 + 288);
    if ( *(_DWORD *)(a1 + 312) != GetCurrentThreadId() )
    {
      if ( wil::details::g_pfnReportFatalUsageError )
        wil::details::g_pfnReportFatalUsageError(
          "MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread",
          retaddr);
    }
    *((_DWORD *)v1 + 6) = 0;
    while ( 1 )
    {
      v2 = **v1;
      if ( !v2 )
        break;
      if ( (__int64 **)v2 == v1 )
      {
        **v1 = (__int64)v1[2];
        break;
      }
      *v1 = (__int64 *)(v2 + 16);
    }
    *v1 = 0;
  }
}

```

## disassembly

```asm
0x18004d1ac  push    rbx
0x18004d1ae  sub     rsp, 20h
0x18004d1b2  cmp     dword ptr [rcx+138h], 0
0x18004d1b9  jz      short loc_18004D1F8
0x18004d1bb  lea     rbx, [rcx+120h]
0x18004d1c2  call    cs:__imp_GetCurrentThreadId
0x18004d1c9  nop     dword ptr [rax+rax+00h]
0x18004d1ce  cmp     [rbx+18h], eax
0x18004d1d1  jnz     short loc_18004D208
0x18004d1d3  mov     dword ptr [rbx+18h], 0
0x18004d1da  mov     rcx, [rbx]
0x18004d1dd  mov     rax, [rcx]
0x18004d1e0  test    rax, rax
0x18004d1e3  jz      short loc_18004D1F1
0x18004d1e5  cmp     rax, rbx
0x18004d1e8  jnz     short loc_18004D1FF
0x18004d1ea  mov     rax, [rbx+10h]
0x18004d1ee  mov     [rcx], rax
0x18004d1f1  mov     qword ptr [rbx], 0
0x18004d1f8  add     rsp, 20h
0x18004d1fc  pop     rbx
0x18004d1fd  retn
0x18004d1ff  add     rax, 10h
0x18004d203  mov     [rbx], rax
0x18004d206  jmp     short loc_18004D1DA
0x18004d208  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x18004d20f  test    rax, rax
0x18004d212  jz      short loc_18004D1D3
0x18004d214  mov     rdx, [rsp+28h]
0x18004d219  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x18004d220  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d225  jmp     short loc_18004D1D3
```
