# wil::ActivityBase<LanguageComponentsInstallerTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)

- ea: `0x180018580`
- end: `0x1800185f4`
- name: `?IgnoreCurrentThread@?$ActivityBase@VLanguageComponentsInstallerTelemetryProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ`
- size: `116`
- prototype: `void __fastcall(__int64)`
- caller_count: `6`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18001c058`
- `0x18001c1d0`
- `0x18001c460`
- `0x180025550`
- `0x180025660`
- `0x1800258e0`

## callees

- `0x180018580`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018596`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018596`

## string_xrefs

- `0x1800185b2`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

## pseudocode

```c
void __fastcall wil::ActivityBase<LanguageComponentsInstallerTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
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
0x180018580  push    rbx
0x180018582  sub     rsp, 20h
0x180018586  cmp     dword ptr [rcx+138h], 0
0x18001858d  jz      short loc_1800185EE
0x18001858f  lea     rbx, [rcx+120h]
0x180018596  call    cs:__imp_GetCurrentThreadId
0x18001859c  cmp     [rbx+18h], eax
0x18001859f  jz      short loc_1800185BE
0x1800185a1  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x1800185a8  test    rax, rax
0x1800185ab  jz      short loc_1800185BE
0x1800185ad  mov     rdx, [rsp+28h]
0x1800185b2  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x1800185b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800185be  mov     dword ptr [rbx+18h], 0
0x1800185c5  mov     rcx, [rbx]
0x1800185c8  jmp     short loc_1800185D6
0x1800185ca  cmp     rax, rbx
0x1800185cd  jz      short loc_1800185E0
0x1800185cf  lea     rcx, [rax+10h]
0x1800185d3  mov     [rbx], rcx
0x1800185d6  mov     rax, [rcx]
0x1800185d9  test    rax, rax
0x1800185dc  jnz     short loc_1800185CA
0x1800185de  jmp     short loc_1800185E7
0x1800185e0  mov     rax, [rbx+10h]
0x1800185e4  mov     [rcx], rax
0x1800185e7  mov     qword ptr [rbx], 0
0x1800185ee  add     rsp, 20h
0x1800185f2  pop     rbx
0x1800185f3  retn
```
