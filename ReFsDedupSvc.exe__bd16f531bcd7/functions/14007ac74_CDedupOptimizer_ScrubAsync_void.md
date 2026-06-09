# CDedupOptimizer::ScrubAsync(void)

- ea: `0x14007ac74`
- end: `0x14007acd9`
- name: `?ScrubAsync@CDedupOptimizer@@AEAAKXZ`
- size: `101`
- prototype: `unsigned int __fastcall(PVOID pv)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140076244`
- `0x1400793e8`
- `0x14007a6fc`

## callees

- `0x1400635dc`
- `0x14007ac74`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007ac96`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007ac96`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x14007acc5`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x14007acc5`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x14007ac85`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x14007ac85`

## pseudocode

```c
__int64 __fastcall CDedupOptimizer::ScrubAsync(PVOID pv)
{
  struct _TP_WORK *ThreadpoolWork; // rax
  DWORD LastError; // [rsp+38h] [rbp+10h] BYREF

  ThreadpoolWork = CreateThreadpoolWork(CDedupOptimizer::ScrubWorkCallback, pv, 0);
  if ( ThreadpoolWork )
  {
    SubmitThreadpoolWork(ThreadpoolWork);
    return 0;
  }
  else
  {
    LastError = GetLastError();
    DedupUtil::Print<unsigned long &>(6, L"Unable to queue scrub callback, error = 0x%x\n", &LastError);
    return LastError;
  }
}

```

## disassembly

```asm
0x14007ac74  sub     rsp, 28h
0x14007ac78  mov     rdx, rcx; pv
0x14007ac7b  xor     r8d, r8d; pcbe
0x14007ac7e  lea     rcx, ?ScrubWorkCallback@CDedupOptimizer@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x14007ac85  call    cs:__imp_CreateThreadpoolWork
0x14007ac8c  nop     dword ptr [rax+rax+00h]
0x14007ac91  test    rax, rax
0x14007ac94  jnz     short loc_14007ACC2
0x14007ac96  call    cs:__imp_GetLastError
0x14007ac9d  nop     dword ptr [rax+rax+00h]
0x14007aca2  lea     r8, [rsp+28h+arg_8]
0x14007aca7  mov     ecx, 6
0x14007acac  lea     rdx, aUnableToQueueS; "Unable to queue scrub callback, error ="...
0x14007acb3  mov     [rsp+28h+arg_8], eax
0x14007acb7  call    ??$Print@AEAK@DedupUtil@@YAXW4MessageType@0@PEBGAEAK@Z; DedupUtil::Print<ulong &>(DedupUtil::MessageType,ushort const *,ulong &)
0x14007acbc  mov     eax, [rsp+28h+arg_8]
0x14007acc0  jmp     short loc_14007ACD3
0x14007acc2  mov     rcx, rax; pwk
0x14007acc5  call    cs:__imp_SubmitThreadpoolWork
0x14007accc  nop     dword ptr [rax+rax+00h]
0x14007acd1  xor     eax, eax
0x14007acd3  add     rsp, 28h
0x14007acd7  retn
```
