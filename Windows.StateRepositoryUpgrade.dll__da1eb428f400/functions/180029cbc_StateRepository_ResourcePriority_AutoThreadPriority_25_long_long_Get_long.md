# StateRepository::ResourcePriority::AutoThreadPriority<25,long,long>::_Get(long &)

- ea: `0x180029cbc`
- end: `0x180029d13`
- name: `?_Get@?$AutoThreadPriority@$0BJ@JJ@ResourcePriority@StateRepository@@IEAAJAEAJ@Z`
- size: `87`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800298b8`

## callees

- `0x180013728`
- `0x180018e58`
- `0x180029cbc`

## import_xrefs

- `ntdll!NtQueryInformationThread` at `0x180029ce3`
- `ntdll!NtQueryInformationThread` at `0x180029ce3`

## string_xrefs

- `0x180029cf2`: `onecore\base\appmodel\StateRepository\DataAccessLayer\ResourcePriority.hpp`

## pseudocode

```c
int __fastcall StateRepository::ResourcePriority::AutoThreadPriority<25,long,long>::_Get(
        __int64 a1,
        void *a2,
        __int64 a3,
        __int64 a4,
        int a5)
{
  void *EffectiveThreadHandle; // rax
  NTSTATUS InformationThread; // eax
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  EffectiveThreadHandle = (void *)StateRepository::ResourcePriority::AutoThreadPriority<24,unsigned long,_MEMORY_PRIORITY_INFORMATION>::GetEffectiveThreadHandle();
  InformationThread = NtQueryInformationThread(EffectiveThreadHandle, ThreadActualBasePriority, a2, 4u, 0);
  if ( InformationThread >= 0 )
    return 0;
  else
    return wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)0x7E,
             (unsigned int)"onecore\\base\\appmodel\\StateRepository\\DataAccessLayer\\ResourcePriority.hpp",
             (const char *)(unsigned int)InformationThread,
             a5);
}

```

## disassembly

```asm
0x180029cbc  push    rbx
0x180029cbe  sub     rsp, 30h
0x180029cc2  mov     rbx, rdx
0x180029cc5  call    ?GetEffectiveThreadHandle@?$AutoThreadPriority@$0BI@KU_MEMORY_PRIORITY_INFORMATION@@@ResourcePriority@StateRepository@@IEAAPEAXXZ; StateRepository::ResourcePriority::AutoThreadPriority<24,ulong,_MEMORY_PRIORITY_INFORMATION>::GetEffectiveThreadHandle(void)
0x180029cca  mov     r9d, 4; ThreadInformationLength
0x180029cd0  mov     [rsp+38h+ReturnLength], 0; ReturnLength
0x180029cd9  mov     rcx, rax; ThreadHandle
0x180029cdc  mov     r8, rbx; ThreadInformation
0x180029cdf  lea     edx, [r9+15h]; ThreadInformationClass
0x180029ce3  call    cs:__imp_NtQueryInformationThread
0x180029ce9  test    eax, eax
0x180029ceb  jns     short loc_180029D0B
0x180029ced  mov     rcx, [rsp+38h]; this
0x180029cf2  lea     r8, aOnecoreBaseApp_36; "onecore\\base\\appmodel\\StateRepositor"...
0x180029cf9  mov     r9d, eax; char *
0x180029cfc  mov     edx, 7Eh ; '~'; void *
0x180029d01  add     rsp, 30h
0x180029d05  pop     rbx
0x180029d06  jmp     ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180029d0b  xor     eax, eax
0x180029d0d  add     rsp, 30h
0x180029d11  pop     rbx
0x180029d12  retn
```
