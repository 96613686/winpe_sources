# CInstallService::~CInstallService(void)

- ea: `0x18000badc`
- end: `0x18000bae1`
- name: `??1CInstallService@@QEAA@XZ`
- size: `5`
- prototype: `void __fastcall(CInstallService *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, installer_update`

## callers

- `0x18001ffc0`

## callees

- `0x18000b9e0`

## pseudocode

```c
// attributes: thunk
void __fastcall CInstallService::~CInstallService(CInstallService *this)
{
  std::list<_DeployJob>::~list<_DeployJob>(this);
}

```

## disassembly

```asm
0x18000badc  jmp     ??1?$list@U_DeployJob@@V?$allocator@U_DeployJob@@@std@@@std@@QEAA@XZ; std::list<_DeployJob>::~list<_DeployJob>(void)
```
