# wil::ActivityBase<StateRepository::Tracing::Service,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)

- ea: `0x1800f9cac`
- end: `0x1800f9d20`
- name: `?IgnoreCurrentThread@?$ActivityBase@VService@Tracing@StateRepository@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ`
- size: `116`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x1800fc228`
- `0x1800fc380`

## callees

- `0x1800f9cac`
- `0x18010d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800f9cc2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800f9cc2`

## string_xrefs

- `0x1800f9cde`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

## pseudocode

```c
void __fastcall wil::ActivityBase<StateRepository::Tracing::Service,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
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
0x1800f9cac  push    rbx
0x1800f9cae  sub     rsp, 20h
0x1800f9cb2  cmp     dword ptr [rcx+138h], 0
0x1800f9cb9  jz      short loc_1800F9D1A
0x1800f9cbb  lea     rbx, [rcx+120h]
0x1800f9cc2  call    cs:__imp_GetCurrentThreadId
0x1800f9cc8  cmp     [rbx+18h], eax
0x1800f9ccb  jz      short loc_1800F9CEA
0x1800f9ccd  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x1800f9cd4  test    rax, rax
0x1800f9cd7  jz      short loc_1800F9CEA
0x1800f9cd9  mov     rdx, [rsp+28h]
0x1800f9cde  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x1800f9ce5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f9cea  mov     rcx, [rbx]
0x1800f9ced  mov     dword ptr [rbx+18h], 0
0x1800f9cf4  jmp     short loc_1800F9D02
0x1800f9cf6  cmp     rax, rbx
0x1800f9cf9  jz      short loc_1800F9D0C
0x1800f9cfb  lea     rcx, [rax+10h]
0x1800f9cff  mov     [rbx], rcx
0x1800f9d02  mov     rax, [rcx]
0x1800f9d05  test    rax, rax
0x1800f9d08  jnz     short loc_1800F9CF6
0x1800f9d0a  jmp     short loc_1800F9D13
0x1800f9d0c  mov     rax, [rbx+10h]
0x1800f9d10  mov     [rcx], rax
0x1800f9d13  mov     qword ptr [rbx], 0
0x1800f9d1a  add     rsp, 20h
0x1800f9d1e  pop     rbx
0x1800f9d1f  retn
```
