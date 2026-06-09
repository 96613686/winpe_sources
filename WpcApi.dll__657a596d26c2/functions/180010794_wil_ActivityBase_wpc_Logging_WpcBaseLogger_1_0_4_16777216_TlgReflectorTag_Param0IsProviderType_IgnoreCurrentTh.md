# wil::ActivityBase<wpc::Logging::WpcBaseLogger,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)

- ea: `0x180010794`
- end: `0x180010808`
- name: `?IgnoreCurrentThread@?$ActivityBase@VWpcBaseLogger@Logging@wpc@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ`
- size: `116`
- prototype: `void __fastcall(__int64)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180013010`
- `0x180013140`
- `0x1800133c0`
- `0x180013640`
- `0x1800138c0`

## callees

- `0x180010794`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800107aa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800107aa`

## string_xrefs

- `0x1800107c6`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

## pseudocode

```c
void __fastcall wil::ActivityBase<wpc::Logging::WpcBaseLogger,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
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
0x180010794  push    rbx
0x180010796  sub     rsp, 20h
0x18001079a  cmp     dword ptr [rcx+138h], 0
0x1800107a1  jz      short loc_180010802
0x1800107a3  lea     rbx, [rcx+120h]
0x1800107aa  call    cs:__imp_GetCurrentThreadId
0x1800107b0  cmp     [rbx+18h], eax
0x1800107b3  jz      short loc_1800107D2
0x1800107b5  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x1800107bc  test    rax, rax
0x1800107bf  jz      short loc_1800107D2
0x1800107c1  mov     rdx, [rsp+28h]
0x1800107c6  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x1800107cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800107d2  mov     dword ptr [rbx+18h], 0
0x1800107d9  mov     rcx, [rbx]
0x1800107dc  jmp     short loc_1800107EA
0x1800107de  cmp     rax, rbx
0x1800107e1  jz      short loc_1800107F4
0x1800107e3  lea     rcx, [rax+10h]
0x1800107e7  mov     [rbx], rcx
0x1800107ea  mov     rax, [rcx]
0x1800107ed  test    rax, rax
0x1800107f0  jnz     short loc_1800107DE
0x1800107f2  jmp     short loc_1800107FB
0x1800107f4  mov     rax, [rbx+10h]
0x1800107f8  mov     [rcx], rax
0x1800107fb  mov     qword ptr [rbx], 0
0x180010802  add     rsp, 20h
0x180010806  pop     rbx
0x180010807  retn
```
