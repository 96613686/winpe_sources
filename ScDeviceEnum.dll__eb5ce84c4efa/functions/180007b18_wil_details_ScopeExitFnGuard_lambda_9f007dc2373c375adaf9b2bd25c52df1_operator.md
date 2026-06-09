# wil::details::ScopeExitFnGuard__lambda_9f007dc2373c375adaf9b2bd25c52df1___::operator()

- ea: `0x180007b18`
- end: `0x180007b4e`
- name: `wil::details::ScopeExitFnGuard__lambda_9f007dc2373c375adaf9b2bd25c52df1___::operator()`
- size: `54`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180007620`
- `0x180007ec0`

## callees

- `0x180007b18`
- `0x180008070`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x180007b34`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x180007b34`

## pseudocode

```c
void __fastcall wil::details::ScopeExitFnGuard__lambda_9f007dc2373c375adaf9b2bd25c52df1___::operator()(__int64 a1)
{
  struct CTaskCounter *v1; // rax
  wil *v2; // rcx
  unsigned int v3; // eax
  void *v4; // rdx
  unsigned int v5; // r8d
  unsigned int v6; // eax
  void *v7; // rdx
  unsigned int v8; // r8d
  int v9; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( *(_BYTE *)(a1 + 2) )
  {
    *(_BYTE *)(a1 + 2) = 0;
    try
    {
      v1 = CTaskCounter::Instance();
      CloseThreadpoolCleanupGroup(*((PTP_CLEANUP_GROUP *)v1 + 15));
      *((_QWORD *)CTaskCounter::Instance() + 15) = 0;
    }
    catch ( ... )
    {
      if ( *(_BYTE *)(a1 + 1) == 2 )
      {
        v3 = wil::ResultFromCaughtException(v2);
        wil::details::in1diag3::FailFast_Hr(retaddr, v4, v5, (const char *)v3, v9);
      }
      if ( *(_BYTE *)(a1 + 1) == 1 )
      {
        v6 = wil::ResultFromCaughtException(v2);
        wil::details::in1diag3::Log_Hr(retaddr, v7, v8, (const char *)v6, v9);
      }
    }
  }
}

```

## disassembly

```asm
0x180007b18  mov     [rsp+arg_0], rcx
0x180007b1d  sub     rsp, 28h
0x180007b21  cmp     byte ptr [rcx+2], 0
0x180007b25  jz      short loc_180007B47
0x180007b27  mov     byte ptr [rcx+2], 0
0x180007b2b  call    ?Instance@CTaskCounter@@SAAEAV1@XZ; CTaskCounter::Instance(void)
0x180007b30  mov     rcx, [rax+78h]; ptpcg
0x180007b34  call    cs:__imp_CloseThreadpoolCleanupGroup
0x180007b3a  call    ?Instance@CTaskCounter@@SAAEAV1@XZ; CTaskCounter::Instance(void)
0x180007b3f  mov     qword ptr [rax+78h], 0
0x180007b47  jmp     short $+2
0x180007b49  add     rsp, 28h
0x180007b4d  retn
```
