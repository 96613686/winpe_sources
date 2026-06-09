# `Singleton<SgSftLdr::ComInterfaceMethodHook<IUnknown,long (*)(void *,_GUID const &,void * *),1>>::Instance(void)'::`2'::`dynamic atexit destructor for 's_cs''(void)

- ea: `0x18002c780`
- end: `0x18002c78e`
- name: `??__Fs_cs@?1??Instance@?$Singleton@V?$ComInterfaceMethodHook@UIUnknown@@P6AJPEAXAEBU_GUID@@PEAPEAX@Z$00@SgSftLdr@@@@SAAEAV?$ComInterfaceMethodHook@UIUnknown@@P6AJPEAXAEBU_GUID@@PEAPEAX@Z$00@SgSftLdr@@XZ@YAXXZ`
- size: `14`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18002c787`

## pseudocode

```c
void __fastcall `Singleton<SgSftLdr::ComInterfaceMethodHook<IUnknown,long (*)(void *,_GUID const &,void * *),1>>::Instance'::`2'::`dynamic atexit destructor for 's_cs''()
{
  DeleteCriticalSection(&`Singleton<SgSftLdr::ComInterfaceMethodHook<IUnknown,long (*)(void *,_GUID const &,void * *),1>>::Instance'::`2'::s_cs);
}

```

## disassembly

```asm
0x18002c780  lea     rcx, ?s_cs@?1??Instance@?$Singleton@V?$ComInterfaceMethodHook@UIUnknown@@P6AJPEAXAEBU_GUID@@PEAPEAX@Z$00@SgSftLdr@@@@SAAEAV?$ComInterfaceMethodHook@UIUnknown@@P6AJPEAXAEBU_GUID@@PEAPEAX@Z$00@SgSftLdr@@XZ@4Vcritical_section@shared@softricity@@A; softricity::shared::critical_section `Singleton<SgSftLdr::ComInterfaceMethodHook<IUnknown,long (*)(void *,_GUID const &,void * *),1>>::Instance(void)'::`2'::s_cs
0x18002c787  jmp     cs:__imp_DeleteCriticalSection
```
