# wil::ActivityBase<StorageReserveTelemetry::Internal::StorageReserveProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)

- ea: `0x180028494`
- end: `0x180028508`
- name: `?IgnoreCurrentThread@?$ActivityBase@VStorageReserveProvider@Internal@StorageReserveTelemetry@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ`
- size: `116`
- prototype: `void __fastcall(__int64)`
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x18002ac04`
- `0x18002afa8`
- `0x18002b4e4`
- `0x18002b8c4`
- `0x18002bc70`
- `0x18002bf10`
- `0x18002c1b0`
- `0x18002c730`

## callees

- `0x180028494`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800284aa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800284aa`

## string_xrefs

- `0x1800284c6`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

## pseudocode

```c
void __fastcall wil::ActivityBase<StorageReserveTelemetry::Internal::StorageReserveProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
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
0x180028494  push    rbx
0x180028496  sub     rsp, 20h
0x18002849a  cmp     dword ptr [rcx+138h], 0
0x1800284a1  jz      short loc_180028502
0x1800284a3  lea     rbx, [rcx+120h]
0x1800284aa  call    cs:__imp_GetCurrentThreadId
0x1800284b0  cmp     [rbx+18h], eax
0x1800284b3  jz      short loc_1800284D2
0x1800284b5  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x1800284bc  test    rax, rax
0x1800284bf  jz      short loc_1800284D2
0x1800284c1  mov     rdx, [rsp+28h]
0x1800284c6  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x1800284cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800284d2  mov     rcx, [rbx]
0x1800284d5  mov     dword ptr [rbx+18h], 0
0x1800284dc  jmp     short loc_1800284EA
0x1800284de  cmp     rax, rbx
0x1800284e1  jz      short loc_1800284F4
0x1800284e3  lea     rcx, [rax+10h]
0x1800284e7  mov     [rbx], rcx
0x1800284ea  mov     rax, [rcx]
0x1800284ed  test    rax, rax
0x1800284f0  jnz     short loc_1800284DE
0x1800284f2  jmp     short loc_1800284FB
0x1800284f4  mov     rax, [rbx+10h]
0x1800284f8  mov     [rcx], rax
0x1800284fb  mov     qword ptr [rbx], 0
0x180028502  add     rsp, 20h
0x180028506  pop     rbx
0x180028507  retn
```
