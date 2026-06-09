# wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)

- ea: `0x18000e400`
- end: `0x18000e474`
- name: `?IgnoreCurrentThread@?$ActivityBase@VServiceHostLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ`
- size: `116`
- prototype: `void __fastcall(__int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18000f4b0`
- `0x18000f628`
- `0x18000f908`
- `0x18000fbf0`
- `0x18000fee0`

## callees

- `0x18000e400`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e416`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e416`

## string_xrefs

- `0x18000e432`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

## pseudocode

```c
void __fastcall wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
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
0x18000e400  push    rbx
0x18000e402  sub     rsp, 20h
0x18000e406  cmp     dword ptr [rcx+138h], 0
0x18000e40d  jz      short loc_18000E46E
0x18000e40f  lea     rbx, [rcx+120h]
0x18000e416  call    cs:__imp_GetCurrentThreadId
0x18000e41c  cmp     [rbx+18h], eax
0x18000e41f  jz      short loc_18000E43E
0x18000e421  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x18000e428  test    rax, rax
0x18000e42b  jz      short loc_18000E43E
0x18000e42d  mov     rdx, [rsp+28h]
0x18000e432  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x18000e439  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e43e  mov     dword ptr [rbx+18h], 0
0x18000e445  mov     rcx, [rbx]
0x18000e448  jmp     short loc_18000E456
0x18000e44a  cmp     rax, rbx
0x18000e44d  jz      short loc_18000E460
0x18000e44f  lea     rcx, [rax+10h]
0x18000e453  mov     [rbx], rcx
0x18000e456  mov     rax, [rcx]
0x18000e459  test    rax, rax
0x18000e45c  jnz     short loc_18000E44A
0x18000e45e  jmp     short loc_18000E467
0x18000e460  mov     rax, [rbx+10h]
0x18000e464  mov     [rcx], rax
0x18000e467  mov     qword ptr [rbx], 0
0x18000e46e  add     rsp, 20h
0x18000e472  pop     rbx
0x18000e473  retn
```
