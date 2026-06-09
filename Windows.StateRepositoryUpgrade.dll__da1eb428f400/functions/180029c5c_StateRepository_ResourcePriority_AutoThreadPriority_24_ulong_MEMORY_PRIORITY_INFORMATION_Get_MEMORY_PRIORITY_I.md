# StateRepository::ResourcePriority::AutoThreadPriority<24,ulong,_MEMORY_PRIORITY_INFORMATION>::_Get(_MEMORY_PRIORITY_INFORMATION &)

- ea: `0x180029c5c`
- end: `0x180029cb3`
- name: `?_Get@?$AutoThreadPriority@$0BI@KU_MEMORY_PRIORITY_INFORMATION@@@ResourcePriority@StateRepository@@IEAAJAEAU_MEMORY_PRIORITY_INFORMATION@@@Z`
- size: `87`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18002985c`

## callees

- `0x180013728`
- `0x180018e58`
- `0x180029c5c`

## import_xrefs

- `ntdll!NtQueryInformationThread` at `0x180029c83`
- `ntdll!NtQueryInformationThread` at `0x180029c83`

## string_xrefs

- `0x180029c92`: `onecore\base\appmodel\StateRepository\DataAccessLayer\ResourcePriority.hpp`

## pseudocode

```c
int __fastcall StateRepository::ResourcePriority::AutoThreadPriority<24,unsigned long,_MEMORY_PRIORITY_INFORMATION>::_Get(
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
  InformationThread = NtQueryInformationThread(EffectiveThreadHandle, ThreadPagePriority, a2, 4u, 0);
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
0x180029c5c  push    rbx
0x180029c5e  sub     rsp, 30h
0x180029c62  mov     rbx, rdx
0x180029c65  call    ?GetEffectiveThreadHandle@?$AutoThreadPriority@$0BI@KU_MEMORY_PRIORITY_INFORMATION@@@ResourcePriority@StateRepository@@IEAAPEAXXZ; StateRepository::ResourcePriority::AutoThreadPriority<24,ulong,_MEMORY_PRIORITY_INFORMATION>::GetEffectiveThreadHandle(void)
0x180029c6a  mov     r9d, 4; ThreadInformationLength
0x180029c70  mov     [rsp+38h+ReturnLength], 0; ReturnLength
0x180029c79  mov     rcx, rax; ThreadHandle
0x180029c7c  mov     r8, rbx; ThreadInformation
0x180029c7f  lea     edx, [r9+14h]; ThreadInformationClass
0x180029c83  call    cs:__imp_NtQueryInformationThread
0x180029c89  test    eax, eax
0x180029c8b  jns     short loc_180029CAB
0x180029c8d  mov     rcx, [rsp+38h]; this
0x180029c92  lea     r8, aOnecoreBaseApp_36; "onecore\\base\\appmodel\\StateRepositor"...
0x180029c99  mov     r9d, eax; char *
0x180029c9c  mov     edx, 7Eh ; '~'; void *
0x180029ca1  add     rsp, 30h
0x180029ca5  pop     rbx
0x180029ca6  jmp     ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180029cab  xor     eax, eax
0x180029cad  add     rsp, 30h
0x180029cb1  pop     rbx
0x180029cb2  retn
```
