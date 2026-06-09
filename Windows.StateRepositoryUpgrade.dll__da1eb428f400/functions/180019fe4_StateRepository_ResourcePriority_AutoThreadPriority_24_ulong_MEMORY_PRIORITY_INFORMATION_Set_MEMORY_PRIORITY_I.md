# StateRepository::ResourcePriority::AutoThreadPriority<24,ulong,_MEMORY_PRIORITY_INFORMATION>::_Set(_MEMORY_PRIORITY_INFORMATION &)

- ea: `0x180019fe4`
- end: `0x18001a032`
- name: `?_Set@?$AutoThreadPriority@$0BI@KU_MEMORY_PRIORITY_INFORMATION@@@ResourcePriority@StateRepository@@IEAAJAEAU_MEMORY_PRIORITY_INFORMATION@@@Z`
- size: `78`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180019788`

## callees

- `0x180013728`
- `0x180018e58`
- `0x180019fe4`

## import_xrefs

- `ntdll!NtSetInformationThread` at `0x18001a002`
- `ntdll!NtSetInformationThread` at `0x18001a002`

## string_xrefs

- `0x18001a011`: `onecore\base\appmodel\StateRepository\DataAccessLayer\ResourcePriority.hpp`

## pseudocode

```c
int __fastcall StateRepository::ResourcePriority::AutoThreadPriority<24,unsigned long,_MEMORY_PRIORITY_INFORMATION>::_Set(
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
  v7 = NtSetInformationThread(EffectiveThreadHandle, ThreadPagePriority, a2, 4u);
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
0x180019fe4  push    rbx
0x180019fe6  sub     rsp, 20h
0x180019fea  mov     rbx, rdx
0x180019fed  call    ?GetEffectiveThreadHandle@?$AutoThreadPriority@$0BI@KU_MEMORY_PRIORITY_INFORMATION@@@ResourcePriority@StateRepository@@IEAAPEAXXZ; StateRepository::ResourcePriority::AutoThreadPriority<24,ulong,_MEMORY_PRIORITY_INFORMATION>::GetEffectiveThreadHandle(void)
0x180019ff2  mov     r9d, 4; ThreadInformationLength
0x180019ff8  mov     rcx, rax; ThreadHandle
0x180019ffb  mov     r8, rbx; ThreadInformation
0x180019ffe  lea     edx, [r9+14h]; ThreadInformationClass
0x18001a002  call    cs:__imp_NtSetInformationThread
0x18001a008  test    eax, eax
0x18001a00a  jns     short loc_18001A02A
0x18001a00c  mov     rcx, [rsp+28h]; this
0x18001a011  lea     r8, aOnecoreBaseApp_36; "onecore\\base\\appmodel\\StateRepositor"...
0x18001a018  mov     r9d, eax; char *
0x18001a01b  mov     edx, 8Dh; void *
0x18001a020  add     rsp, 20h
0x18001a024  pop     rbx
0x18001a025  jmp     ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18001a02a  xor     eax, eax
0x18001a02c  add     rsp, 20h
0x18001a030  pop     rbx
0x18001a031  retn
```
