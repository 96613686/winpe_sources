# DeviceConfiguration::ConfigurationManager::_RestartSpoolerService(void)

- ea: `0x180013600`
- end: `0x18001363c`
- name: `?_RestartSpoolerService@ConfigurationManager@DeviceConfiguration@@AEAAXXZ`
- size: `60`
- prototype: `void __fastcall(DeviceConfiguration::ConfigurationManager *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x1800121c0`
- `0x180012a50`
- `0x180012df8`

## callees

- `0x18001260c`
- `0x180013e50`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001361b`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001361b`

## pseudocode

```c
void __fastcall DeviceConfiguration::ConfigurationManager::_RestartSpoolerService(
        DeviceConfiguration::ConfigurationManager *this)
{
  DeviceConfiguration::ConfigurationManager *v1; // rcx
  DeviceConfiguration::ConfigurationManager *v2; // rcx

  DeviceConfiguration::ConfigurationManager::_ChangeSpoolerServiceState(this, 2u, 4u, 0x20u);
  Sleep(0x3E8u);
  DeviceConfiguration::ConfigurationManager::_ChangeSpoolerServiceState(v1, 3u, 1u, 0x10u);
  DeviceConfiguration::ConfigurationManager::_WaitForSpoolerServiceRunning(v2);
}

```

## disassembly

```asm
0x180013600  sub     rsp, 28h
0x180013604  mov     edx, 2; unsigned int
0x180013609  lea     r9d, [rdx+1Eh]; unsigned int
0x18001360d  lea     r8d, [rdx+2]; unsigned int
0x180013611  call    ?_ChangeSpoolerServiceState@ConfigurationManager@DeviceConfiguration@@AEAAJKKK@Z; DeviceConfiguration::ConfigurationManager::_ChangeSpoolerServiceState(ulong,ulong,ulong)
0x180013616  mov     ecx, 3E8h; dwMilliseconds
0x18001361b  call    cs:__imp_Sleep
0x180013621  mov     edx, 3; unsigned int
0x180013626  lea     r9d, [rdx+0Dh]; unsigned int
0x18001362a  lea     r8d, [rdx-2]; unsigned int
0x18001362e  call    ?_ChangeSpoolerServiceState@ConfigurationManager@DeviceConfiguration@@AEAAJKKK@Z; DeviceConfiguration::ConfigurationManager::_ChangeSpoolerServiceState(ulong,ulong,ulong)
0x180013633  add     rsp, 28h
0x180013637  jmp     ?_WaitForSpoolerServiceRunning@ConfigurationManager@DeviceConfiguration@@AEAAXXZ; DeviceConfiguration::ConfigurationManager::_WaitForSpoolerServiceRunning(void)
```
