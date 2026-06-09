# wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)

- ea: `0x14000827c`
- end: `0x1400082f9`
- name: `?IgnoreCurrentThread@?$ActivityBase@VTelemetryProvider@WaasMedic@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ`
- size: `125`
- prototype: `void __fastcall(__int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x140008f2c`
- `0x1400090b0`
- `0x14000a4f0`

## callees

- `0x14000827c`
- `0x140013010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000829b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000829b`

## string_xrefs

- `0x1400082b7`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

## pseudocode

```c
void __fastcall wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
        __int64 a1)
{
  __int64 v1; // rbx
  __int64 *v2; // rcx
  __int64 v3; // rax
  void *retaddr; // [rsp+38h] [rbp+0h]

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
0x14000827c  push    rbx
0x14000827e  sub     rsp, 30h
0x140008282  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x14000828b  cmp     dword ptr [rcx+138h], 0
0x140008292  jz      short loc_1400082F3
0x140008294  lea     rbx, [rcx+120h]
0x14000829b  call    cs:__imp_GetCurrentThreadId
0x1400082a1  cmp     [rbx+18h], eax
0x1400082a4  jz      short loc_1400082C3
0x1400082a6  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x1400082ad  test    rax, rax
0x1400082b0  jz      short loc_1400082C3
0x1400082b2  mov     rdx, [rsp+38h]
0x1400082b7  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x1400082be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400082c3  mov     dword ptr [rbx+18h], 0
0x1400082ca  mov     rcx, [rbx]
0x1400082cd  jmp     short loc_1400082DB
0x1400082cf  cmp     rax, rbx
0x1400082d2  jz      short loc_1400082E5
0x1400082d4  lea     rcx, [rax+10h]
0x1400082d8  mov     [rbx], rcx
0x1400082db  mov     rax, [rcx]
0x1400082de  test    rax, rax
0x1400082e1  jnz     short loc_1400082CF
0x1400082e3  jmp     short loc_1400082EC
0x1400082e5  mov     rax, [rbx+10h]
0x1400082e9  mov     [rcx], rax
0x1400082ec  mov     qword ptr [rbx], 0
0x1400082f3  add     rsp, 30h
0x1400082f7  pop     rbx
0x1400082f8  retn
```
