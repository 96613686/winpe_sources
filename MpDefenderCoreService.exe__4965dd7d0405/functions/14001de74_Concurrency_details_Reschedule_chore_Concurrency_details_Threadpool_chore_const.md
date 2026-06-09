# Concurrency::details::_Reschedule_chore(Concurrency::details::_Threadpool_chore const *)

- ea: `0x14001de74`
- end: `0x14001deab`
- name: `?_Reschedule_chore@details@Concurrency@@YAHPEBU_Threadpool_chore@12@@Z`
- size: `55`
- prototype: `__int64 __fastcall(Concurrency::details *__hidden this, const struct Concurrency::details::_Threadpool_chore *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14001deac`

## callees

- `0x14001de10`
- `0x14001de74`

## import_xrefs

- `KERNEL32!SubmitThreadpoolWork` at `0x14001de9d`
- `KERNEL32!SubmitThreadpoolWork` at `0x14001de9d`
- `KERNEL32!GetModuleHandleExW` at `0x14001de94`
- `KERNEL32!GetModuleHandleExW` at `0x14001de94`

## pseudocode

```c
__int64 __fastcall Concurrency::details::_Reschedule_chore(
        LPCWSTR *this,
        const struct Concurrency::details::_Threadpool_chore *a2)
{
  HMODULE phModule; // [rsp+30h] [rbp+8h] BYREF

  if ( (unsigned int)Concurrency::details::_anonymous_namespace_::_Get_STL_host_status(this, a2) )
    GetModuleHandleExW(4u, this[1], &phModule);
  SubmitThreadpoolWork((PTP_WORK)*this);
  return 0;
}

```

## disassembly

```asm
0x14001de74  push    rbx
0x14001de76  sub     rsp, 20h
0x14001de7a  mov     rbx, rcx
0x14001de7d  call    Concurrency__details___anonymous_namespace____Get_STL_host_status
0x14001de82  test    eax, eax
0x14001de84  jz      short loc_14001DE9A
0x14001de86  mov     rdx, [rbx+8]; lpModuleName
0x14001de8a  lea     r8, [rsp+28h+phModule]; phModule
0x14001de8f  mov     ecx, 4; dwFlags
0x14001de94  call    cs:__imp_GetModuleHandleExW
0x14001de9a  mov     rcx, [rbx]; pwk
0x14001de9d  call    cs:__imp_SubmitThreadpoolWork
0x14001dea3  xor     eax, eax
0x14001dea5  add     rsp, 20h
0x14001dea9  pop     rbx
0x14001deaa  retn
```
