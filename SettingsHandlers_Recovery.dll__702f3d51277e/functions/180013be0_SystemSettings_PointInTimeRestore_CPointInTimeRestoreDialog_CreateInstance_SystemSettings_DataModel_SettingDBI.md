# SystemSettings::PointInTimeRestore::CPointInTimeRestoreDialog::CreateInstance(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)

- ea: `0x180013be0`
- end: `0x180013c72`
- name: `?CreateInstance@CPointInTimeRestoreDialog@PointInTimeRestore@SystemSettings@@SAJPEBUSettingDBItem@DataModel@3@PEAPEAUISettingItem@53@@Z`
- size: `146`
- prototype: `__int64 __fastcall(const struct SystemSettings::DataModel::SettingDBItem *, struct SystemSettings::DataModel::ISettingItem **)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000f7fc`
- `0x180013be0`
- `0x18002b010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SystemSettings::PointInTimeRestore::CPointInTimeRestoreDialog::CreateInstance(
        const struct SystemSettings::DataModel::SettingDBItem *a1,
        struct SystemSettings::DataModel::ISettingItem **a2)
{
  unsigned int v4; // edi
  _QWORD *v5; // rcx
  _QWORD *v7; // [rsp+40h] [rbp+18h] BYREF

  v4 = -2147024882;
  Microsoft::WRL::Details::Make<SystemSettings::PointInTimeRestore::CPointInTimeRestoreDialog,>((__int64 *)&v7);
  v5 = v7;
  if ( v7 )
  {
    if ( a1 )
    {
      v7[11] = *((_QWORD *)a1 + 5);
      v5 = v7;
    }
    v5[12] = a1;
    v4 = (*(__int64 (__fastcall **)(_QWORD *, GUID *, struct SystemSettings::DataModel::ISettingItem **))*v7)(
           v7,
           &GUID_40c037cc_d8bf_489e_8697_d66baa3221bf,
           a2);
    v5 = v7;
  }
  if ( v5 )
  {
    v7 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v5 + 16LL))(v5);
  }
  return v4;
}

```

## disassembly

```asm
0x180013be0  mov     [rsp+arg_0], rbx
0x180013be5  mov     [rsp+arg_8], rsi
0x180013bea  push    rdi
0x180013beb  sub     rsp, 20h
0x180013bef  mov     rsi, rdx
0x180013bf2  mov     rbx, rcx
0x180013bf5  mov     edi, 8007000Eh
0x180013bfa  lea     rcx, [rsp+28h+arg_10]
0x180013bff  call    ??$Make@VCPointInTimeRestoreDialog@PointInTimeRestore@SystemSettings@@$$V@Details@WRL@Microsoft@@YA?AV?$ComPtr@VCPointInTimeRestoreDialog@PointInTimeRestore@SystemSettings@@@12@XZ; Microsoft::WRL::Details::Make<SystemSettings::PointInTimeRestore::CPointInTimeRestoreDialog,>(void)
0x180013c04  mov     rcx, [rsp+28h+arg_10]
0x180013c09  test    rcx, rcx
0x180013c0c  jz      short loc_180013C45
0x180013c0e  test    rbx, rbx
0x180013c11  jz      short loc_180013C20
0x180013c13  mov     rax, [rbx+28h]
0x180013c17  mov     [rcx+58h], rax
0x180013c1b  mov     rcx, [rsp+28h+arg_10]
0x180013c20  mov     [rcx+60h], rbx
0x180013c24  mov     rcx, [rsp+28h+arg_10]
0x180013c29  mov     rax, [rcx]
0x180013c2c  mov     r8, rsi
0x180013c2f  lea     rdx, _GUID_40c037cc_d8bf_489e_8697_d66baa3221bf
0x180013c36  mov     rax, [rax]
0x180013c39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013c3e  mov     edi, eax
0x180013c40  mov     rcx, [rsp+28h+arg_10]
0x180013c45  test    rcx, rcx
0x180013c48  jz      short loc_180013C60
0x180013c4a  mov     [rsp+28h+arg_10], 0
0x180013c53  mov     rdx, [rcx]
0x180013c56  mov     rax, [rdx+10h]
0x180013c5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013c5f  nop
0x180013c60  mov     eax, edi
0x180013c62  mov     rbx, [rsp+28h+arg_0]
0x180013c67  mov     rsi, [rsp+28h+arg_8]
0x180013c6c  add     rsp, 20h
0x180013c70  pop     rdi
0x180013c71  retn
```
