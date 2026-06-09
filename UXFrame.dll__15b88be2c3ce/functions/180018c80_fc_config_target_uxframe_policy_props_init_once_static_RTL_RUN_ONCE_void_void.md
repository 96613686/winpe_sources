# fc::config_target<uxframe_policy_props>::init_once_static(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x180018c80`
- end: `0x180018cb9`
- name: `?init_once_static@?$config_target@Uuxframe_policy_props@@@fc@@KAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `57`
- prototype: `BOOL __stdcall(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x180019284`
- `0x18001d1d0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018c89`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018c89`

## pseudocode

```c
__int64 __fastcall fc::config_target<uxframe_policy_props>::init_once_static(
        PINIT_ONCE InitOnce,
        _DWORD *Parameter,
        PVOID *Context)
{
  unsigned int System; // eax
  __int64 result; // rax

  Parameter[36] = GetCurrentThreadId();
  System = _FC_Query_System();
  fc::config_target<uxframe_policy_props>::load_payload(Parameter, System);
  result = 1;
  Parameter[36] = 0;
  return result;
}

```

## disassembly

```asm
0x180018c80  push    rbx
0x180018c82  sub     rsp, 20h
0x180018c86  mov     rbx, rdx
0x180018c89  call    cs:__imp_GetCurrentThreadId
0x180018c8f  mov     [rbx+90h], eax
0x180018c95  call    __FC_Query_System
0x180018c9a  mov     edx, eax
0x180018c9c  mov     rcx, rbx
0x180018c9f  call    ?load_payload@?$config_target@Uuxframe_policy_props@@@fc@@IEAAXW4__FC_System_Flags@@@Z; fc::config_target<uxframe_policy_props>::load_payload(__FC_System_Flags)
0x180018ca4  mov     eax, 1
0x180018ca9  mov     dword ptr [rbx+90h], 0
0x180018cb3  add     rsp, 20h
0x180018cb7  pop     rbx
0x180018cb8  retn
```
