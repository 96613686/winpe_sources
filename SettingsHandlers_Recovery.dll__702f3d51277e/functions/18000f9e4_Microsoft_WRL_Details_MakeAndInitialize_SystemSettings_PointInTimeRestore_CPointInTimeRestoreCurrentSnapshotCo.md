# Microsoft::WRL::Details::MakeAndInitialize<SystemSettings::PointInTimeRestore::CPointInTimeRestoreCurrentSnapshotCollection,SystemSettings::PointInTimeRestore::CPointInTimeRestoreCurrentSnapshotCollection,>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<SystemSettings::PointInTimeRestore::CPointInTimeRestoreCurrentSnapshotCollection>>)

- ea: `0x18000f9e4`
- end: `0x18000fa8e`
- name: `??$MakeAndInitialize@VCPointInTimeRestoreCurrentSnapshotCollection@PointInTimeRestore@SystemSettings@@V123@$$V@Details@WRL@Microsoft@@YAJV?$ComPtrRef@V?$ComPtr@VCPointInTimeRestoreCurrentSnapshotCollection@PointInTimeRestore@SystemSettings@@@WRL@Microsoft@@@012@@Z`
- size: `170`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180017de0`

## callees

- `0x180002380`
- `0x18000f9e4`
- `0x180011008`
- `0x18002b010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::MakeAndInitialize<SystemSettings::PointInTimeRestore::CPointInTimeRestoreCurrentSnapshotCollection,SystemSettings::PointInTimeRestore::CPointInTimeRestoreCurrentSnapshotCollection,>(
        __int64 *a1)
{
  __int64 v2; // rcx
  SystemSettings::PointInTimeRestore::CPointInTimeRestoreCurrentSnapshotCollection *v3; // rax
  __int64 v5; // rax
  __int64 v6; // rdi

  v2 = *a1;
  if ( v2 )
  {
    *a1 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  }
  *a1 = 0;
  v3 = (SystemSettings::PointInTimeRestore::CPointInTimeRestoreCurrentSnapshotCollection *)operator new(
                                                                                             0x108u,
                                                                                             (const struct std::nothrow_t *)&std::nothrow);
  if ( !v3 )
    return 2147942414LL;
  v5 = SystemSettings::PointInTimeRestore::CPointInTimeRestoreCurrentSnapshotCollection::CPointInTimeRestoreCurrentSnapshotCollection(v3);
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
0x18000f9e4  mov     [rsp+arg_18], rbx
0x18000f9e9  push    rdi
0x18000f9ea  sub     rsp, 20h
0x18000f9ee  mov     rbx, rcx
0x18000f9f1  mov     rcx, [rcx]
0x18000f9f4  test    rcx, rcx
0x18000f9f7  jz      short loc_18000FA0D
0x18000f9f9  mov     qword ptr [rbx], 0
0x18000fa00  mov     rax, [rcx]
0x18000fa03  mov     rax, [rax+10h]
0x18000fa07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fa0c  nop
0x18000fa0d  mov     qword ptr [rbx], 0
0x18000fa14  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000fa1b  mov     ecx, 108h; unsigned __int64
0x18000fa20  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000fa25  mov     [rsp+28h+arg_0], rax
0x18000fa2a  mov     [rsp+28h+arg_8], rax
0x18000fa2f  test    rax, rax
0x18000fa32  jnz     short loc_18000FA3B
0x18000fa34  mov     eax, 8007000Eh
0x18000fa39  jmp     short loc_18000FA83
0x18000fa3b  mov     [rsp+28h+arg_10], rax
0x18000fa40  mov     rcx, rax; this
0x18000fa43  call    ??0CPointInTimeRestoreCurrentSnapshotCollection@PointInTimeRestore@SystemSettings@@QEAA@XZ; SystemSettings::PointInTimeRestore::CPointInTimeRestoreCurrentSnapshotCollection::CPointInTimeRestoreCurrentSnapshotCollection(void)
0x18000fa48  mov     rdi, rax
0x18000fa4b  mov     [rsp+28h+arg_0], 0
0x18000fa54  test    rax, rax
0x18000fa57  jz      short loc_18000FA69
0x18000fa59  mov     rcx, [rax]
0x18000fa5c  mov     rax, [rcx+8]
0x18000fa60  mov     rcx, rdi
0x18000fa63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fa68  nop
0x18000fa69  mov     [rbx], rdi
0x18000fa6c  test    rdi, rdi
0x18000fa6f  jz      short loc_18000FA81
0x18000fa71  mov     rax, [rdi]
0x18000fa74  mov     rcx, rdi
0x18000fa77  mov     rax, [rax+10h]
0x18000fa7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fa80  nop
0x18000fa81  xor     eax, eax
0x18000fa83  mov     rbx, [rsp+28h+arg_18]
0x18000fa88  add     rsp, 20h
0x18000fa8c  pop     rdi
0x18000fa8d  retn
```
