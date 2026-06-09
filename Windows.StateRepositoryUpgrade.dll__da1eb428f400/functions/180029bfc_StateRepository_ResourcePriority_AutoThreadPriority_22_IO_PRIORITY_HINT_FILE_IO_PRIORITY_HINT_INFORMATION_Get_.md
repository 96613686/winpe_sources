# StateRepository::ResourcePriority::AutoThreadPriority<22,_IO_PRIORITY_HINT,_FILE_IO_PRIORITY_HINT_INFORMATION>::_Get(_FILE_IO_PRIORITY_HINT_INFORMATION &)

- ea: `0x180029bfc`
- end: `0x180029c53`
- name: `?_Get@?$AutoThreadPriority@$0BG@W4_IO_PRIORITY_HINT@@U_FILE_IO_PRIORITY_HINT_INFORMATION@@@ResourcePriority@StateRepository@@IEAAJAEAU_FILE_IO_PRIORITY_HINT_INFORMATION@@@Z`
- size: `87`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180029800`

## callees

- `0x180013728`
- `0x180018e58`
- `0x180029bfc`

## import_xrefs

- `ntdll!NtQueryInformationThread` at `0x180029c23`
- `ntdll!NtQueryInformationThread` at `0x180029c23`

## string_xrefs

- `0x180029c32`: `onecore\base\appmodel\StateRepository\DataAccessLayer\ResourcePriority.hpp`

## pseudocode

```c
int __fastcall StateRepository::ResourcePriority::AutoThreadPriority<22,enum _IO_PRIORITY_HINT,_FILE_IO_PRIORITY_HINT_INFORMATION>::_Get(
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
  InformationThread = NtQueryInformationThread(EffectiveThreadHandle, ThreadIoPriority, a2, 4u, 0);
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
0x180029bfc  push    rbx
0x180029bfe  sub     rsp, 30h
0x180029c02  mov     rbx, rdx
0x180029c05  call    ?GetEffectiveThreadHandle@?$AutoThreadPriority@$0BI@KU_MEMORY_PRIORITY_INFORMATION@@@ResourcePriority@StateRepository@@IEAAPEAXXZ; StateRepository::ResourcePriority::AutoThreadPriority<24,ulong,_MEMORY_PRIORITY_INFORMATION>::GetEffectiveThreadHandle(void)
0x180029c0a  mov     r9d, 4; ThreadInformationLength
0x180029c10  mov     [rsp+38h+ReturnLength], 0; ReturnLength
0x180029c19  mov     rcx, rax; ThreadHandle
0x180029c1c  mov     r8, rbx; ThreadInformation
0x180029c1f  lea     edx, [r9+12h]; ThreadInformationClass
0x180029c23  call    cs:__imp_NtQueryInformationThread
0x180029c29  test    eax, eax
0x180029c2b  jns     short loc_180029C4B
0x180029c2d  mov     rcx, [rsp+38h]; this
0x180029c32  lea     r8, aOnecoreBaseApp_36; "onecore\\base\\appmodel\\StateRepositor"...
0x180029c39  mov     r9d, eax; char *
0x180029c3c  mov     edx, 7Eh ; '~'; void *
0x180029c41  add     rsp, 30h
0x180029c45  pop     rbx
0x180029c46  jmp     ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180029c4b  xor     eax, eax
0x180029c4d  add     rsp, 30h
0x180029c51  pop     rbx
0x180029c52  retn
```
