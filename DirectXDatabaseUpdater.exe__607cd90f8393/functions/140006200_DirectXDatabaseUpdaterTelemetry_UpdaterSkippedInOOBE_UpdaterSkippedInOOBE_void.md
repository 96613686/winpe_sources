# DirectXDatabaseUpdaterTelemetry::UpdaterSkippedInOOBE::~UpdaterSkippedInOOBE(void)

- ea: `0x140006200`
- end: `0x140006225`
- name: `??1UpdaterSkippedInOOBE@DirectXDatabaseUpdaterTelemetry@@QEAA@XZ`
- size: `37`
- prototype: `void __fastcall(DirectXDatabaseUpdaterTelemetry::UpdaterSkippedInOOBE *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x14000f2a4`
- `0x140018a9e`

## callees

- `0x140005884`
- `0x140006b80`

## pseudocode

```c
void __fastcall DirectXDatabaseUpdaterTelemetry::UpdaterSkippedInOOBE::~UpdaterSkippedInOOBE(
        DirectXDatabaseUpdaterTelemetry::UpdaterSkippedInOOBE *this)
{
  *(_QWORD *)this = &DirectXDatabaseUpdaterTelemetry::UpdaterSkippedInOOBE::`vftable';
  wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy((__int64)this);
  wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>((__int64)this);
}

```

## disassembly

```asm
0x140006200  push    rbx
0x140006202  sub     rsp, 20h
0x140006206  lea     rax, ??_7UpdaterSkippedInOOBE@DirectXDatabaseUpdaterTelemetry@@6B@; const DirectXDatabaseUpdaterTelemetry::UpdaterSkippedInOOBE::`vftable'
0x14000620d  mov     rbx, rcx
0x140006210  mov     [rcx], rax
0x140006213  call    ?Destroy@?$ActivityBase@VDirectXDatabaseUpdaterLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x140006218  mov     rcx, rbx
0x14000621b  add     rsp, 20h
0x14000621f  pop     rbx
0x140006220  jmp     ??1?$ActivityBase@VDirectXDatabaseUpdaterLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
```
