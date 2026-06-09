# StateRepository::ResourcePriority::AutoThreadPriority<25,long,long>::_Set(long &)

- ea: `0x18001a038`
- end: `0x18001a086`
- name: `?_Set@?$AutoThreadPriority@$0BJ@JJ@ResourcePriority@StateRepository@@IEAAJAEAJ@Z`
- size: `78`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800197e0`

## callees

- `0x180013728`
- `0x180018e58`
- `0x18001a038`

## import_xrefs

- `ntdll!NtSetInformationThread` at `0x18001a056`
- `ntdll!NtSetInformationThread` at `0x18001a056`

## string_xrefs

- `0x18001a065`: `onecore\base\appmodel\StateRepository\DataAccessLayer\ResourcePriority.hpp`

## pseudocode

```c
int __fastcall StateRepository::ResourcePriority::AutoThreadPriority<25,long,long>::_Set(
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
  v7 = NtSetInformationThread(EffectiveThreadHandle, ThreadActualBasePriority, a2, 4u);
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
0x18001a038  push    rbx
0x18001a03a  sub     rsp, 20h
0x18001a03e  mov     rbx, rdx
0x18001a041  call    ?GetEffectiveThreadHandle@?$AutoThreadPriority@$0BI@KU_MEMORY_PRIORITY_INFORMATION@@@ResourcePriority@StateRepository@@IEAAPEAXXZ; StateRepository::ResourcePriority::AutoThreadPriority<24,ulong,_MEMORY_PRIORITY_INFORMATION>::GetEffectiveThreadHandle(void)
0x18001a046  mov     r9d, 4; ThreadInformationLength
0x18001a04c  mov     rcx, rax; ThreadHandle
0x18001a04f  mov     r8, rbx; ThreadInformation
0x18001a052  lea     edx, [r9+15h]; ThreadInformationClass
0x18001a056  call    cs:__imp_NtSetInformationThread
0x18001a05c  test    eax, eax
0x18001a05e  jns     short loc_18001A07E
0x18001a060  mov     rcx, [rsp+28h]; this
0x18001a065  lea     r8, aOnecoreBaseApp_36; "onecore\\base\\appmodel\\StateRepositor"...
0x18001a06c  mov     r9d, eax; char *
0x18001a06f  mov     edx, 8Dh; void *
0x18001a074  add     rsp, 20h
0x18001a078  pop     rbx
0x18001a079  jmp     ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18001a07e  xor     eax, eax
0x18001a080  add     rsp, 20h
0x18001a084  pop     rbx
0x18001a085  retn
```
