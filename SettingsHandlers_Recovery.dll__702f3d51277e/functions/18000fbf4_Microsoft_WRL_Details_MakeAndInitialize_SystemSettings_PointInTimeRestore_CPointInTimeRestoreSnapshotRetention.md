# Microsoft::WRL::Details::MakeAndInitialize<SystemSettings::PointInTimeRestore::CPointInTimeRestoreSnapshotRetentionSetting,SystemSettings::PointInTimeRestore::CPointInTimeRestoreSnapshotRetentionSetting,>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<SystemSettings::PointInTimeRestore::CPointInTimeRestoreSnapshotRetentionSetting>>)

- ea: `0x18000fbf4`
- end: `0x18000fc9e`
- name: `??$MakeAndInitialize@VCPointInTimeRestoreSnapshotRetentionSetting@PointInTimeRestore@SystemSettings@@V123@$$V@Details@WRL@Microsoft@@YAJV?$ComPtrRef@V?$ComPtr@VCPointInTimeRestoreSnapshotRetentionSetting@PointInTimeRestore@SystemSettings@@@WRL@Microsoft@@@012@@Z`
- size: `170`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180017de0`

## callees

- `0x180002380`
- `0x18000fbf4`
- `0x180011544`
- `0x18002b010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::MakeAndInitialize<SystemSettings::PointInTimeRestore::CPointInTimeRestoreSnapshotRetentionSetting,SystemSettings::PointInTimeRestore::CPointInTimeRestoreSnapshotRetentionSetting,>(
        __int64 *a1)
{
  __int64 v2; // rcx
  SystemSettings::PointInTimeRestore::CPointInTimeRestoreSnapshotRetentionSetting *v3; // rax
  __int64 v5; // rax
  __int64 v6; // rdi

  v2 = *a1;
  if ( v2 )
  {
    *a1 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  }
  *a1 = 0;
  v3 = (SystemSettings::PointInTimeRestore::CPointInTimeRestoreSnapshotRetentionSetting *)operator new(
                                                                                            0xF8u,
                                                                                            (const struct std::nothrow_t *)&std::nothrow);
  if ( !v3 )
    return 2147942414LL;
  v5 = SystemSettings::PointInTimeRestore::CPointInTimeRestoreSnapshotRetentionSetting::CPointInTimeRestoreSnapshotRetentionSetting(v3);
  v6 = v5;
  if ( v5 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 8LL))(v5);
  *a1 = v6;
  if ( v6 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  return 0;
}

```

## disassembly

```asm
0x18000fbf4  mov     [rsp+arg_18], rbx
0x18000fbf9  push    rdi
0x18000fbfa  sub     rsp, 20h
0x18000fbfe  mov     rbx, rcx
0x18000fc01  mov     rcx, [rcx]
0x18000fc04  test    rcx, rcx
0x18000fc07  jz      short loc_18000FC1D
0x18000fc09  mov     qword ptr [rbx], 0
0x18000fc10  mov     rax, [rcx]
0x18000fc13  mov     rax, [rax+10h]
0x18000fc17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fc1c  nop
0x18000fc1d  mov     qword ptr [rbx], 0
0x18000fc24  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000fc2b  mov     ecx, 0F8h; unsigned __int64
0x18000fc30  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000fc35  mov     [rsp+28h+arg_0], rax
0x18000fc3a  mov     [rsp+28h+arg_8], rax
0x18000fc3f  test    rax, rax
0x18000fc42  jnz     short loc_18000FC4B
0x18000fc44  mov     eax, 8007000Eh
0x18000fc49  jmp     short loc_18000FC93
0x18000fc4b  mov     [rsp+28h+arg_10], rax
0x18000fc50  mov     rcx, rax; this
0x18000fc53  call    ??0CPointInTimeRestoreSnapshotRetentionSetting@PointInTimeRestore@SystemSettings@@QEAA@XZ; SystemSettings::PointInTimeRestore::CPointInTimeRestoreSnapshotRetentionSetting::CPointInTimeRestoreSnapshotRetentionSetting(void)
0x18000fc58  mov     rdi, rax
0x18000fc5b  mov     [rsp+28h+arg_0], 0
0x18000fc64  test    rax, rax
0x18000fc67  jz      short loc_18000FC79
0x18000fc69  mov     rcx, [rax]
0x18000fc6c  mov     rax, [rcx+8]
0x18000fc70  mov     rcx, rdi
0x18000fc73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fc78  nop
0x18000fc79  mov     [rbx], rdi
0x18000fc7c  test    rdi, rdi
0x18000fc7f  jz      short loc_18000FC91
0x18000fc81  mov     rax, [rdi]
0x18000fc84  mov     rcx, rdi
0x18000fc87  mov     rax, [rax+10h]
0x18000fc8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fc90  nop
0x18000fc91  xor     eax, eax
0x18000fc93  mov     rbx, [rsp+28h+arg_18]
0x18000fc98  add     rsp, 20h
0x18000fc9c  pop     rdi
0x18000fc9d  retn
```
