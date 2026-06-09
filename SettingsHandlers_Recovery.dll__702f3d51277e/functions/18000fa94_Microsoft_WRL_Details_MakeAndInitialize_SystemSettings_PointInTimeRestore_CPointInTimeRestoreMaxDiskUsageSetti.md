# Microsoft::WRL::Details::MakeAndInitialize<SystemSettings::PointInTimeRestore::CPointInTimeRestoreMaxDiskUsageSetting,SystemSettings::PointInTimeRestore::CPointInTimeRestoreMaxDiskUsageSetting,>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<SystemSettings::PointInTimeRestore::CPointInTimeRestoreMaxDiskUsageSetting>>)

- ea: `0x18000fa94`
- end: `0x18000fb3e`
- name: `??$MakeAndInitialize@VCPointInTimeRestoreMaxDiskUsageSetting@PointInTimeRestore@SystemSettings@@V123@$$V@Details@WRL@Microsoft@@YAJV?$ComPtrRef@V?$ComPtr@VCPointInTimeRestoreMaxDiskUsageSetting@PointInTimeRestore@SystemSettings@@@WRL@Microsoft@@@012@@Z`
- size: `170`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180017de0`

## callees

- `0x180002380`
- `0x18000fa94`
- `0x18001127c`
- `0x18002b010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::MakeAndInitialize<SystemSettings::PointInTimeRestore::CPointInTimeRestoreMaxDiskUsageSetting,SystemSettings::PointInTimeRestore::CPointInTimeRestoreMaxDiskUsageSetting,>(
        __int64 *a1)
{
  __int64 v2; // rcx
  SystemSettings::PointInTimeRestore::CPointInTimeRestoreMaxDiskUsageSetting *v3; // rax
  __int64 v5; // rax
  __int64 v6; // rdi

  v2 = *a1;
  if ( v2 )
  {
    *a1 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  }
  *a1 = 0;
  v3 = (SystemSettings::PointInTimeRestore::CPointInTimeRestoreMaxDiskUsageSetting *)operator new(
                                                                                       0xF8u,
                                                                                       (const struct std::nothrow_t *)&std::nothrow);
  if ( !v3 )
    return 2147942414LL;
  v5 = SystemSettings::PointInTimeRestore::CPointInTimeRestoreMaxDiskUsageSetting::CPointInTimeRestoreMaxDiskUsageSetting(v3);
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
0x18000fa94  mov     [rsp+arg_18], rbx
0x18000fa99  push    rdi
0x18000fa9a  sub     rsp, 20h
0x18000fa9e  mov     rbx, rcx
0x18000faa1  mov     rcx, [rcx]
0x18000faa4  test    rcx, rcx
0x18000faa7  jz      short loc_18000FABD
0x18000faa9  mov     qword ptr [rbx], 0
0x18000fab0  mov     rax, [rcx]
0x18000fab3  mov     rax, [rax+10h]
0x18000fab7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fabc  nop
0x18000fabd  mov     qword ptr [rbx], 0
0x18000fac4  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000facb  mov     ecx, 0F8h; unsigned __int64
0x18000fad0  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000fad5  mov     [rsp+28h+arg_0], rax
0x18000fada  mov     [rsp+28h+arg_8], rax
0x18000fadf  test    rax, rax
0x18000fae2  jnz     short loc_18000FAEB
0x18000fae4  mov     eax, 8007000Eh
0x18000fae9  jmp     short loc_18000FB33
0x18000faeb  mov     [rsp+28h+arg_10], rax
0x18000faf0  mov     rcx, rax; this
0x18000faf3  call    ??0CPointInTimeRestoreMaxDiskUsageSetting@PointInTimeRestore@SystemSettings@@QEAA@XZ; SystemSettings::PointInTimeRestore::CPointInTimeRestoreMaxDiskUsageSetting::CPointInTimeRestoreMaxDiskUsageSetting(void)
0x18000faf8  mov     rdi, rax
0x18000fafb  mov     [rsp+28h+arg_0], 0
0x18000fb04  test    rax, rax
0x18000fb07  jz      short loc_18000FB19
0x18000fb09  mov     rcx, [rax]
0x18000fb0c  mov     rax, [rcx+8]
0x18000fb10  mov     rcx, rdi
0x18000fb13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fb18  nop
0x18000fb19  mov     [rbx], rdi
0x18000fb1c  test    rdi, rdi
0x18000fb1f  jz      short loc_18000FB31
0x18000fb21  mov     rax, [rdi]
0x18000fb24  mov     rcx, rdi
0x18000fb27  mov     rax, [rax+10h]
0x18000fb2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fb30  nop
0x18000fb31  xor     eax, eax
0x18000fb33  mov     rbx, [rsp+28h+arg_18]
0x18000fb38  add     rsp, 20h
0x18000fb3c  pop     rdi
0x18000fb3d  retn
```
