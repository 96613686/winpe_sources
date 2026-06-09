# fc::config_target<uxframe_policy_props>::ensure_store_initialized(void)

- ea: `0x180017be0`
- end: `0x180017c38`
- name: `?ensure_store_initialized@?$config_target@Uuxframe_policy_props@@@fc@@MEAA_NXZ`
- size: `88`
- prototype: `__int64 __fastcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180017be0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180017bf7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180017bf7`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180017c1f`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180017c1f`

## pseudocode

```c
char __fastcall fc::config_target<uxframe_policy_props>::ensure_store_initialized(PVOID Parameter)
{
  if ( !_InterlockedCompareExchange((volatile signed __int32 *)Parameter + 35, 0, 0) )
  {
    if ( *((_DWORD *)Parameter + 36) == GetCurrentThreadId() )
      return 0;
    InitOnceExecuteOnce(
      (PINIT_ONCE)Parameter + 19,
      (PINIT_ONCE_FN)fc::config_target<uxframe_policy_props>::init_once_static,
      Parameter,
      0);
    _InterlockedExchange((volatile __int32 *)Parameter + 35, 1);
  }
  return 1;
}

```

## disassembly

```asm
0x180017be0  push    rbx
0x180017be2  sub     rsp, 20h
0x180017be6  mov     rbx, rcx
0x180017be9  xor     ecx, ecx
0x180017beb  xor     eax, eax
0x180017bed  lock cmpxchg [rbx+8Ch], ecx
0x180017bf5  jnz     short loc_180017C30
0x180017bf7  call    cs:__imp_GetCurrentThreadId
0x180017bfd  mov     edx, [rbx+90h]
0x180017c03  cmp     edx, eax
0x180017c05  jnz     short loc_180017C0B
0x180017c07  xor     al, al
0x180017c09  jmp     short loc_180017C32
0x180017c0b  lea     rcx, [rbx+98h]; InitOnce
0x180017c12  xor     r9d, r9d; Context
0x180017c15  mov     r8, rbx; Parameter
0x180017c18  lea     rdx, ?init_once_static@?$config_target@Uuxframe_policy_props@@@fc@@KAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x180017c1f  call    cs:__imp_InitOnceExecuteOnce
0x180017c25  mov     ecx, 1
0x180017c2a  xchg    ecx, [rbx+8Ch]
0x180017c30  mov     al, 1
0x180017c32  add     rsp, 20h
0x180017c36  pop     rbx
0x180017c37  retn
```
