# wil::details::shared_cloud_store_state::get_cloud_store(void)

- ea: `0x1800075bc`
- end: `0x180007664`
- name: `?get_cloud_store@shared_cloud_store_state@details@wil@@QEAAAEBV?$com_ptr_t@UICloudStore@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@3@XZ`
- size: `168`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `11`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800071e0`
- `0x180007fd8`
- `0x180012594`
- `0x1800179f4`
- `0x18001aed8`
- `0x18001bce8`
- `0x180025df4`
- `0x18002607c`
- `0x18003019c`
- `0x180035be4`
- `0x180035f68`

## callees

- `0x1800075bc`
- `0x18001ea20`
- `0x18002d124`
- `0x180041010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007607`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007607`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000761b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000761b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall wil::details::shared_cloud_store_state::get_cloud_store(__int64 a1)
{
  _QWORD *v2; // rdi
  _QWORD *v3; // rcx
  RTL_SRWLOCK *v4; // rbx
  __int64 v6; // rdx
  __int64 v7; // [rsp+40h] [rbp+8h] BYREF

  v2 = (_QWORD *)(a1 + 72);
  if ( !*(_QWORD *)(a1 + 72) )
  {
    v3 = (_QWORD *)(a1 + 24);
    if ( v3[3] > 7u )
      v3 = (_QWORD *)*v3;
    wil::details::CreateCloudStoreDefaultWithWaitTime(
      (unsigned int)&v7,
      *(_DWORD *)a1,
      *(_QWORD *)(a1 + 8),
      *(_QWORD *)(a1 + 16),
      (__int64)v3,
      a1 + 56);
    v4 = (RTL_SRWLOCK *)(a1 + 64);
    AcquireSRWLockExclusive(v4);
    if ( !*v2 )
    {
      v6 = v7;
      v7 = 0;
      wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudStore,wil::err_exception_policy>::attach(v2, v6);
    }
    if ( v4 )
      ReleaseSRWLockExclusive(v4);
    if ( v7 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  }
  return v2;
}

```

## disassembly

```asm
0x1800075bc  mov     [rsp+arg_8], rbx
0x1800075c1  push    rdi
0x1800075c2  sub     rsp, 30h
0x1800075c6  mov     rbx, rcx
0x1800075c9  lea     rdi, [rcx+48h]
0x1800075cd  cmp     qword ptr [rdi], 0
0x1800075d1  jnz     short loc_180007639
0x1800075d3  add     rcx, 18h
0x1800075d7  cmp     qword ptr [rcx+18h], 7
0x1800075dc  ja      short loc_180007647
0x1800075de  lea     rax, [rbx+38h]
0x1800075e2  mov     [rsp+38h+var_10], rax
0x1800075e7  mov     [rsp+38h+var_18], rcx
0x1800075ec  mov     r9, [rbx+10h]
0x1800075f0  mov     r8, [rbx+8]
0x1800075f4  mov     edx, [rbx]
0x1800075f6  lea     rcx, [rsp+38h+arg_0]
0x1800075fb  call    ?CreateCloudStoreDefaultWithWaitTime@details@wil@@YA?AV?$com_ptr_t@UICloudStore@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@2@W4CloudStoreOptions@Cloud@Storage@Internal@Windows@@PEAUIUser@System@8@PEAUIWebAccount@Credentials@Security@8@PEBGAEBUWaitTimes@5678@@Z; wil::details::CreateCloudStoreDefaultWithWaitTime(Windows::Internal::Storage::Cloud::CloudStoreOptions,Windows::System::IUser *,Windows::Security::Credentials::IWebAccount *,ushort const *,Windows::Internal::Storage::Cloud::WaitTimes const &)
0x180007600  add     rbx, 40h ; '@'
0x180007604  mov     rcx, rbx; SRWLock
0x180007607  call    cs:__imp_AcquireSRWLockExclusive
0x18000760d  cmp     qword ptr [rdi], 0
0x180007611  jz      short loc_18000764C
0x180007613  test    rbx, rbx
0x180007616  jz      short loc_180007622
0x180007618  mov     rcx, rbx; SRWLock
0x18000761b  call    cs:__imp_ReleaseSRWLockExclusive
0x180007621  nop
0x180007622  mov     rcx, [rsp+38h+arg_0]
0x180007627  test    rcx, rcx
0x18000762a  jz      short loc_180007639
0x18000762c  mov     rdx, [rcx]
0x18000762f  mov     rax, [rdx+10h]
0x180007633  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007638  nop
0x180007639  mov     rax, rdi
0x18000763c  mov     rbx, [rsp+38h+arg_8]
0x180007641  add     rsp, 30h
0x180007645  pop     rdi
0x180007646  retn
0x180007647  mov     rcx, [rcx]
0x18000764a  jmp     short loc_1800075DE
0x18000764c  mov     rdx, [rsp+38h+arg_0]
0x180007651  mov     [rsp+38h+arg_0], 0
0x18000765a  mov     rcx, rdi
0x18000765d  call    ?attach@?$com_ptr_t@UICloudStore@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAAXPEAUICloudStore@Cloud@Storage@Internal@Windows@@@Z; wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudStore,wil::err_exception_policy>::attach(Windows::Internal::Storage::Cloud::ICloudStore *)
0x180007662  jmp     short loc_180007613
```
