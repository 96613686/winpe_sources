# Microsoft::WRL::Details::MakeAndInitialize<SystemSettings::PointInTimeRestore::CPointInTimeRestoreSnapshotCadenceSetting,SystemSettings::PointInTimeRestore::CPointInTimeRestoreSnapshotCadenceSetting,>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<SystemSettings::PointInTimeRestore::CPointInTimeRestoreSnapshotCadenceSetting>>)

- ea: `0x18000fb44`
- end: `0x18000fbee`
- name: `??$MakeAndInitialize@VCPointInTimeRestoreSnapshotCadenceSetting@PointInTimeRestore@SystemSettings@@V123@$$V@Details@WRL@Microsoft@@YAJV?$ComPtrRef@V?$ComPtr@VCPointInTimeRestoreSnapshotCadenceSetting@PointInTimeRestore@SystemSettings@@@WRL@Microsoft@@@012@@Z`
- size: `170`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180017de0`

## callees

- `0x180002380`
- `0x18000fb44`
- `0x180011378`
- `0x18002b010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::MakeAndInitialize<SystemSettings::PointInTimeRestore::CPointInTimeRestoreSnapshotCadenceSetting,SystemSettings::PointInTimeRestore::CPointInTimeRestoreSnapshotCadenceSetting,>(
        __int64 *a1)
{
  __int64 v2; // rcx
  SystemSettings::PointInTimeRestore::CPointInTimeRestoreSnapshotCadenceSetting *v3; // rax
  __int64 v5; // rax
  __int64 v6; // rdi

  v2 = *a1;
  if ( v2 )
  {
    *a1 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  }
  *a1 = 0;
  v3 = (SystemSettings::PointInTimeRestore::CPointInTimeRestoreSnapshotCadenceSetting *)operator new(
                                                                                          0xF8u,
                                                                                          (const struct std::nothrow_t *)&std::nothrow);
  if ( !v3 )
    return 2147942414LL;
  v5 = SystemSettings::PointInTimeRestore::CPointInTimeRestoreSnapshotCadenceSetting::CPointInTimeRestoreSnapshotCadenceSetting(v3);
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
0x18000fb44  mov     [rsp+arg_18], rbx
0x18000fb49  push    rdi
0x18000fb4a  sub     rsp, 20h
0x18000fb4e  mov     rbx, rcx
0x18000fb51  mov     rcx, [rcx]
0x18000fb54  test    rcx, rcx
0x18000fb57  jz      short loc_18000FB6D
0x18000fb59  mov     qword ptr [rbx], 0
0x18000fb60  mov     rax, [rcx]
0x18000fb63  mov     rax, [rax+10h]
0x18000fb67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fb6c  nop
0x18000fb6d  mov     qword ptr [rbx], 0
0x18000fb74  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000fb7b  mov     ecx, 0F8h; unsigned __int64
0x18000fb80  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000fb85  mov     [rsp+28h+arg_0], rax
0x18000fb8a  mov     [rsp+28h+arg_8], rax
0x18000fb8f  test    rax, rax
0x18000fb92  jnz     short loc_18000FB9B
0x18000fb94  mov     eax, 8007000Eh
0x18000fb99  jmp     short loc_18000FBE3
0x18000fb9b  mov     [rsp+28h+arg_10], rax
0x18000fba0  mov     rcx, rax; this
0x18000fba3  call    ??0CPointInTimeRestoreSnapshotCadenceSetting@PointInTimeRestore@SystemSettings@@QEAA@XZ; SystemSettings::PointInTimeRestore::CPointInTimeRestoreSnapshotCadenceSetting::CPointInTimeRestoreSnapshotCadenceSetting(void)
0x18000fba8  mov     rdi, rax
0x18000fbab  mov     [rsp+28h+arg_0], 0
0x18000fbb4  test    rax, rax
0x18000fbb7  jz      short loc_18000FBC9
0x18000fbb9  mov     rcx, [rax]
0x18000fbbc  mov     rax, [rcx+8]
0x18000fbc0  mov     rcx, rdi
0x18000fbc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fbc8  nop
0x18000fbc9  mov     [rbx], rdi
0x18000fbcc  test    rdi, rdi
0x18000fbcf  jz      short loc_18000FBE1
0x18000fbd1  mov     rax, [rdi]
0x18000fbd4  mov     rcx, rdi
0x18000fbd7  mov     rax, [rax+10h]
0x18000fbdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fbe0  nop
0x18000fbe1  xor     eax, eax
0x18000fbe3  mov     rbx, [rsp+28h+arg_18]
0x18000fbe8  add     rsp, 20h
0x18000fbec  pop     rdi
0x18000fbed  retn
```
