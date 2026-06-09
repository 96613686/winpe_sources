# Microsoft::WRL::Details::Make<SystemSettings::PointInTimeRestore::CPointInTimeRestoreDialog,>(void)

- ea: `0x18000f7fc`
- end: `0x18000f882`
- name: `??$Make@VCPointInTimeRestoreDialog@PointInTimeRestore@SystemSettings@@$$V@Details@WRL@Microsoft@@YA?AV?$ComPtr@VCPointInTimeRestoreDialog@PointInTimeRestore@SystemSettings@@@12@XZ`
- size: `134`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180013be0`

## callees

- `0x180002380`
- `0x180002820`
- `0x18000f7fc`
- `0x180011124`
- `0x18002b010`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 *__fastcall Microsoft::WRL::Details::Make<SystemSettings::PointInTimeRestore::CPointInTimeRestoreDialog,>(
        __int64 *a1)
{
  SystemSettings::PointInTimeRestore::CPointInTimeRestoreDialog *v2; // rax
  __int64 v3; // rdi

  *a1 = 0;
  v2 = (SystemSettings::PointInTimeRestore::CPointInTimeRestoreDialog *)operator new(
                                                                          0x150u,
                                                                          (const struct std::nothrow_t *)&std::nothrow);
  if ( v2 )
  {
    v3 = SystemSettings::PointInTimeRestore::CPointInTimeRestoreDialog::CPointInTimeRestoreDialog(v2);
    if ( *a1 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)*a1 + 16LL))(*a1);
    *a1 = v3;
  }
  return a1;
}

```

## disassembly

```asm
0x18000f7fc  mov     [rsp+arg_0], rcx
0x18000f801  push    rbx
0x18000f802  push    rdi
0x18000f803  sub     rsp, 38h
0x18000f807  mov     rbx, rcx
0x18000f80a  mov     [rsp+48h+var_28], 0
0x18000f812  mov     qword ptr [rcx], 0
0x18000f819  mov     [rsp+48h+var_28], 1
0x18000f821  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000f828  mov     ecx, 150h; unsigned __int64
0x18000f82d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000f832  mov     [rsp+48h+arg_8], rax
0x18000f837  mov     [rsp+48h+arg_10], rax
0x18000f83c  test    rax, rax
0x18000f83f  jz      short loc_18000F86A
0x18000f841  mov     [rsp+48h+arg_18], rax
0x18000f846  mov     rcx, rax; this
0x18000f849  call    ??0CPointInTimeRestoreDialog@PointInTimeRestore@SystemSettings@@QEAA@XZ; SystemSettings::PointInTimeRestore::CPointInTimeRestoreDialog::CPointInTimeRestoreDialog(void)
0x18000f84e  mov     rdi, rax
0x18000f851  mov     rcx, [rbx]
0x18000f854  test    rcx, rcx
0x18000f857  jz      short loc_18000F865
0x18000f859  mov     rdx, [rcx]
0x18000f85c  mov     rax, [rdx+10h]
0x18000f860  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f865  mov     [rbx], rdi
0x18000f868  xor     eax, eax
0x18000f86a  test    rax, rax
0x18000f86d  jz      short loc_18000F877
0x18000f86f  mov     rcx, rax; Block
0x18000f872  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000f877  mov     rax, rbx
0x18000f87a  add     rsp, 38h
0x18000f87e  pop     rdi
0x18000f87f  pop     rbx
0x18000f880  retn
```
