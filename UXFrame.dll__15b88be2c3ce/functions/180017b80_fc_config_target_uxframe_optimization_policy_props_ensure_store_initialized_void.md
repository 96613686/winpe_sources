# fc::config_target<uxframe_optimization_policy_props>::ensure_store_initialized(void)

- ea: `0x180017b80`
- end: `0x180017bd8`
- name: `?ensure_store_initialized@?$config_target@Uuxframe_optimization_policy_props@@@fc@@MEAA_NXZ`
- size: `88`
- prototype: `__int64 __fastcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180017b80`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180017b97`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180017b97`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180017bbf`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180017bbf`

## pseudocode

```c
char __fastcall fc::config_target<uxframe_optimization_policy_props>::ensure_store_initialized(PVOID Parameter)
{
  if ( !_InterlockedCompareExchange((volatile signed __int32 *)Parameter + 47, 0, 0) )
  {
    if ( *((_DWORD *)Parameter + 48) == GetCurrentThreadId() )
      return 0;
    InitOnceExecuteOnce(
      (PINIT_ONCE)Parameter + 25,
      (PINIT_ONCE_FN)fc::config_target<uxframe_optimization_policy_props>::init_once_static,
      Parameter,
      0);
    _InterlockedExchange((volatile __int32 *)Parameter + 47, 1);
  }
  return 1;
}

```

## disassembly

```asm
0x180017b80  push    rbx
0x180017b82  sub     rsp, 20h
0x180017b86  mov     rbx, rcx
0x180017b89  xor     ecx, ecx
0x180017b8b  xor     eax, eax
0x180017b8d  lock cmpxchg [rbx+0BCh], ecx
0x180017b95  jnz     short loc_180017BD0
0x180017b97  call    cs:__imp_GetCurrentThreadId
0x180017b9d  mov     edx, [rbx+0C0h]
0x180017ba3  cmp     edx, eax
0x180017ba5  jnz     short loc_180017BAB
0x180017ba7  xor     al, al
0x180017ba9  jmp     short loc_180017BD2
0x180017bab  lea     rcx, [rbx+0C8h]; InitOnce
0x180017bb2  xor     r9d, r9d; Context
0x180017bb5  mov     r8, rbx; Parameter
0x180017bb8  lea     rdx, ?init_once_static@?$config_target@Uuxframe_optimization_policy_props@@@fc@@KAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x180017bbf  call    cs:__imp_InitOnceExecuteOnce
0x180017bc5  mov     ecx, 1
0x180017bca  xchg    ecx, [rbx+0BCh]
0x180017bd0  mov     al, 1
0x180017bd2  add     rsp, 20h
0x180017bd6  pop     rbx
0x180017bd7  retn
```
