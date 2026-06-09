# Microsoft::WRL::Details::MakeAndInitialize<SystemSettings::PointInTimeRestore::CPointInTimeRestoreCurrentDiskUsageSetting,SystemSettings::PointInTimeRestore::CPointInTimeRestoreCurrentDiskUsageSetting,>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<SystemSettings::PointInTimeRestore::CPointInTimeRestoreCurrentDiskUsageSetting>>)

- ea: `0x18000f934`
- end: `0x18000f9de`
- name: `??$MakeAndInitialize@VCPointInTimeRestoreCurrentDiskUsageSetting@PointInTimeRestore@SystemSettings@@V123@$$V@Details@WRL@Microsoft@@YAJV?$ComPtrRef@V?$ComPtr@VCPointInTimeRestoreCurrentDiskUsageSetting@PointInTimeRestore@SystemSettings@@@WRL@Microsoft@@@012@@Z`
- size: `170`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180017de0`

## callees

- `0x180002380`
- `0x18000f934`
- `0x180010efc`
- `0x18002b010`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Microsoft::WRL::Details::MakeAndInitialize<SystemSettings::PointInTimeRestore::CPointInTimeRestoreCurrentDiskUsageSetting,SystemSettings::PointInTimeRestore::CPointInTimeRestoreCurrentDiskUsageSetting,>(
        __int64 *a1)
{
  __int64 v2; // rcx
  SystemSettings::PointInTimeRestore::CPointInTimeRestoreCurrentDiskUsageSetting *v3; // rax
  __int64 v5; // rax
  __int64 v6; // rdi

  v2 = *a1;
  if ( v2 )
  {
    *a1 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  }
  *a1 = 0;
  v3 = (SystemSettings::PointInTimeRestore::CPointInTimeRestoreCurrentDiskUsageSetting *)operator new(
                                                                                           0x108u,
                                                                                           (const struct std::nothrow_t *)&std::nothrow);
  if ( !v3 )
    return 2147942414LL;
  v5 = SystemSettings::PointInTimeRestore::CPointInTimeRestoreCurrentDiskUsageSetting::CPointInTimeRestoreCurrentDiskUsageSetting(v3);
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
0x18000f934  mov     [rsp+arg_18], rbx
0x18000f939  push    rdi
0x18000f93a  sub     rsp, 20h
0x18000f93e  mov     rbx, rcx
0x18000f941  mov     rcx, [rcx]
0x18000f944  test    rcx, rcx
0x18000f947  jz      short loc_18000F95D
0x18000f949  mov     qword ptr [rbx], 0
0x18000f950  mov     rax, [rcx]
0x18000f953  mov     rax, [rax+10h]
0x18000f957  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f95c  nop
0x18000f95d  mov     qword ptr [rbx], 0
0x18000f964  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000f96b  mov     ecx, 108h; unsigned __int64
0x18000f970  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000f975  mov     [rsp+28h+arg_0], rax
0x18000f97a  mov     [rsp+28h+arg_8], rax
0x18000f97f  test    rax, rax
0x18000f982  jnz     short loc_18000F98B
0x18000f984  mov     eax, 8007000Eh
0x18000f989  jmp     short loc_18000F9D3
0x18000f98b  mov     [rsp+28h+arg_10], rax
0x18000f990  mov     rcx, rax; this
0x18000f993  call    ??0CPointInTimeRestoreCurrentDiskUsageSetting@PointInTimeRestore@SystemSettings@@QEAA@XZ; SystemSettings::PointInTimeRestore::CPointInTimeRestoreCurrentDiskUsageSetting::CPointInTimeRestoreCurrentDiskUsageSetting(void)
0x18000f998  mov     rdi, rax
0x18000f99b  mov     [rsp+28h+arg_0], 0
0x18000f9a4  test    rax, rax
0x18000f9a7  jz      short loc_18000F9B9
0x18000f9a9  mov     rcx, [rax]
0x18000f9ac  mov     rax, [rcx+8]
0x18000f9b0  mov     rcx, rdi
0x18000f9b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f9b8  nop
0x18000f9b9  mov     [rbx], rdi
0x18000f9bc  test    rdi, rdi
0x18000f9bf  jz      short loc_18000F9D1
0x18000f9c1  mov     rax, [rdi]
0x18000f9c4  mov     rcx, rdi
0x18000f9c7  mov     rax, [rax+10h]
0x18000f9cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f9d0  nop
0x18000f9d1  xor     eax, eax
0x18000f9d3  mov     rbx, [rsp+28h+arg_18]
0x18000f9d8  add     rsp, 20h
0x18000f9dc  pop     rdi
0x18000f9dd  retn
```
