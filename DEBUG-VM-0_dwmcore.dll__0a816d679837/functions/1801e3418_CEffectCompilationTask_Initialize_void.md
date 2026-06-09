# CEffectCompilationTask::Initialize(void)

- ea: `0x1801e3418`
- end: `0x1801e3459`
- name: `?Initialize@CEffectCompilationTask@@AEAAJXZ`
- size: `65`
- prototype: `__int64 __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800f8708`

## callees

- `0x1801e3418`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801e3445`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801e3445`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1801e342e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1801e342e`

## pseudocode

```c
signed int __fastcall CEffectCompilationTask::Initialize(PVOID pv)
{
  PTP_WORK ThreadpoolWork; // rax
  signed int result; // eax

  ThreadpoolWork = CreateThreadpoolWork(
                     CEffectCompilationTask::Initialize_::_2_::_lambda_1_::_lambda_invoker_cdecl_,
                     pv,
                     0);
  *((_QWORD *)pv + 8) = ThreadpoolWork;
  if ( ThreadpoolWork )
    return 0;
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x1801e3418  push    rbx
0x1801e341a  sub     rsp, 20h
0x1801e341e  mov     rbx, rcx
0x1801e3421  mov     rdx, rcx; pv
0x1801e3424  lea     rcx, _CEffectCompilationTask__Initialize____2____lambda_1____lambda_invoker_cdecl_; pfnwk
0x1801e342b  xor     r8d, r8d; pcbe
0x1801e342e  call    cs:__imp_CreateThreadpoolWork
0x1801e3434  mov     [rbx+40h], rax
0x1801e3438  test    rax, rax
0x1801e343b  jz      short loc_1801E3445
0x1801e343d  xor     eax, eax
0x1801e343f  add     rsp, 20h
0x1801e3443  pop     rbx
0x1801e3444  retn
0x1801e3445  call    cs:__imp_GetLastError
0x1801e344b  test    eax, eax
0x1801e344d  jle     short loc_1801E343F
0x1801e344f  movzx   eax, ax
0x1801e3452  or      eax, 80070000h
0x1801e3457  jmp     short loc_1801E343F
```
