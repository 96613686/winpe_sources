# Windows::Internal::ServiceModule::ConnectCallback(void)

- ea: `0x180004ab0`
- end: `0x180004abd`
- name: `?ConnectCallback@ServiceModule@Internal@Windows@@UEAAJXZ`
- size: `13`
- prototype: `__int64 __fastcall(Windows::Internal::ServiceModule *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x180002930`

## pseudocode

```c
__int64 __fastcall Windows::Internal::ServiceModule::ConnectCallback(Windows::Internal::ServiceModule *this)
{
  return Microsoft::WRL::Details::RegisterObjects<2>((char *)this + 40, *((_QWORD *)this + 4));
}

```

## disassembly

```asm
0x180004ab0  mov     rdx, [rcx+20h]
0x180004ab4  add     rcx, 28h ; '('
0x180004ab8  jmp     ??$RegisterObjects@$01@Details@WRL@Microsoft@@YAJPEAVModuleBase@012@PEBG@Z; Microsoft::WRL::Details::RegisterObjects<2>(Microsoft::WRL::Details::ModuleBase *,ushort const *)
```
