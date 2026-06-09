# StateRepository::ResourcePriority::AutoThreadPriority<22,_IO_PRIORITY_HINT,_FILE_IO_PRIORITY_HINT_INFORMATION>::_Set(_FILE_IO_PRIORITY_HINT_INFORMATION &)

- ea: `0x180019f90`
- end: `0x180019fde`
- name: `?_Set@?$AutoThreadPriority@$0BG@W4_IO_PRIORITY_HINT@@U_FILE_IO_PRIORITY_HINT_INFORMATION@@@ResourcePriority@StateRepository@@IEAAJAEAU_FILE_IO_PRIORITY_HINT_INFORMATION@@@Z`
- size: `78`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180019730`

## callees

- `0x180013728`
- `0x180018e58`
- `0x180019f90`

## import_xrefs

- `ntdll!NtSetInformationThread` at `0x180019fae`
- `ntdll!NtSetInformationThread` at `0x180019fae`

## string_xrefs

- `0x180019fbd`: `onecore\base\appmodel\StateRepository\DataAccessLayer\ResourcePriority.hpp`

## pseudocode

```c
int __fastcall StateRepository::ResourcePriority::AutoThreadPriority<22,enum _IO_PRIORITY_HINT,_FILE_IO_PRIORITY_HINT_INFORMATION>::_Set(
        __int64 a1,
        void *a2,
        __int64 a3,
        __int64 a4,
        int a5)
{
  void *EffectiveThreadHandle; // rax
  NTSTATUS v7; // eax
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  EffectiveThreadHandle = (void *)StateRepository::ResourcePriority::AutoThreadPriority<24,unsigned long,_MEMORY_PRIORITY_INFORMATION>::GetEffectiveThreadHandle();
  v7 = NtSetInformationThread(EffectiveThreadHandle, ThreadIoPriority, a2, 4u);
  if ( v7 >= 0 )
    return 0;
  else
    return wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)0x8D,
             (unsigned int)"onecore\\base\\appmodel\\StateRepository\\DataAccessLayer\\ResourcePriority.hpp",
             (const char *)(unsigned int)v7,
             a5);
}

```

## disassembly

```asm
0x180019f90  push    rbx
0x180019f92  sub     rsp, 20h
0x180019f96  mov     rbx, rdx
0x180019f99  call    ?GetEffectiveThreadHandle@?$AutoThreadPriority@$0BI@KU_MEMORY_PRIORITY_INFORMATION@@@ResourcePriority@StateRepository@@IEAAPEAXXZ; StateRepository::ResourcePriority::AutoThreadPriority<24,ulong,_MEMORY_PRIORITY_INFORMATION>::GetEffectiveThreadHandle(void)
0x180019f9e  mov     r9d, 4; ThreadInformationLength
0x180019fa4  mov     rcx, rax; ThreadHandle
0x180019fa7  mov     r8, rbx; ThreadInformation
0x180019faa  lea     edx, [r9+12h]; ThreadInformationClass
0x180019fae  call    cs:__imp_NtSetInformationThread
0x180019fb4  test    eax, eax
0x180019fb6  jns     short loc_180019FD6
0x180019fb8  mov     rcx, [rsp+28h]; this
0x180019fbd  lea     r8, aOnecoreBaseApp_36; "onecore\\base\\appmodel\\StateRepositor"...
0x180019fc4  mov     r9d, eax; char *
0x180019fc7  mov     edx, 8Dh; void *
0x180019fcc  add     rsp, 20h
0x180019fd0  pop     rbx
0x180019fd1  jmp     ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180019fd6  xor     eax, eax
0x180019fd8  add     rsp, 20h
0x180019fdc  pop     rbx
0x180019fdd  retn
```
