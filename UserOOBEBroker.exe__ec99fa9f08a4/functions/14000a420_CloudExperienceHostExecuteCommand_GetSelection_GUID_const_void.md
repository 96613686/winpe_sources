# CloudExperienceHostExecuteCommand::GetSelection(_GUID const &,void * *)

- ea: `0x14000a420`
- end: `0x14000a426`
- name: `?GetSelection@CloudExperienceHostExecuteCommand@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `6`
- prototype: `__int64 __fastcall(CloudExperienceHostExecuteCommand *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
__int64 __fastcall CloudExperienceHostExecuteCommand::GetSelection(
        CloudExperienceHostExecuteCommand *this,
        const struct _GUID *a2,
        void **a3)
{
  return 2147500033LL;
}

```

## disassembly

```asm
0x14000a420  mov     eax, 80004001h
0x14000a425  retn
```
