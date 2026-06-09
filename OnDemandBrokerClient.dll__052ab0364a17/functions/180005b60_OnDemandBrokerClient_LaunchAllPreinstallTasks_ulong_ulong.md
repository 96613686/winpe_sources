# OnDemandBrokerClient::LaunchAllPreinstallTasks(ulong *,ulong *)

- ea: `0x180005b60`
- end: `0x180005b66`
- name: `?LaunchAllPreinstallTasks@OnDemandBrokerClient@@UEAAJPEAK0@Z`
- size: `6`
- prototype: `__int64 __fastcall(OnDemandBrokerClient *__hidden this, unsigned int *, unsigned int *)`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, installer_update, broker_com_uri`

## pseudocode

```c
__int64 __fastcall OnDemandBrokerClient::LaunchAllPreinstallTasks(
        OnDemandBrokerClient *this,
        unsigned int *a2,
        unsigned int *a3)
{
  return 1;
}

```

## disassembly

```asm
0x180005b60  mov     eax, 1
0x180005b65  retn
```
