# kernel_std::detail::sp_counted_impl_p<appv::shared::kernel::flt_connection<appv::shared::kernel::default_flt_connection_manager,vemgr::vemgr_pool_info>>::dispose(void)

- ea: `0x18000be70`
- end: `0x18000bee6`
- name: `?dispose@?$sp_counted_impl_p@V?$flt_connection@Vdefault_flt_connection_manager@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@detail@kernel_std@@UEAAXXZ`
- size: `118`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000bb18`
- `0x18000be70`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x18000bec2`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000bed3`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000bec2`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000bed3`
- `ntoskrnl!ExDeleteResourceLite` at `0x18000beab`
- `ntoskrnl!ExDeleteResourceLite` at `0x18000beab`
- `FLTMGR!FltCloseCommunicationPort` at `0x18000be8f`
- `FLTMGR!FltCloseCommunicationPort` at `0x18000be8f`

## pseudocode

```c
void __fastcall kernel_std::detail::sp_counted_impl_p<appv::shared::kernel::flt_connection<appv::shared::kernel::default_flt_connection_manager,vemgr::vemgr_pool_info>>::dispose(
        __int64 a1)
{
  __int64 v1; // rbx
  struct _ERESOURCE *v2; // rcx
  void *v3; // rcx

  v1 = *(_QWORD *)(a1 + 16);
  if ( v1 )
  {
    appv::shared::kernel::flt_connection<vemgr_listener_connection_manager,vemgr::vemgr_pool_info>::disconnect_client(*(_QWORD *)(a1 + 16));
    if ( *(_QWORD *)v1 )
    {
      FltCloseCommunicationPort(*(PFLT_PORT *)v1);
      *(_QWORD *)v1 = 0;
    }
    v2 = *(struct _ERESOURCE **)(v1 + 24);
    if ( v2 )
    {
      ExDeleteResourceLite(v2);
      v3 = *(void **)(v1 + 24);
      if ( v3 )
        ExFreePoolWithTag(v3, 0);
    }
    ExFreePoolWithTag((PVOID)v1, 0);
  }
}

```

## disassembly

```asm
0x18000be70  push    rbx
0x18000be72  sub     rsp, 20h
0x18000be76  mov     rbx, [rcx+10h]
0x18000be7a  test    rbx, rbx
0x18000be7d  jz      short loc_18000BEDF
0x18000be7f  mov     rcx, rbx
0x18000be82  call    ?disconnect_client@?$flt_connection@Vvemgr_listener_connection_manager@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@QEAAXXZ; appv::shared::kernel::flt_connection<vemgr_listener_connection_manager,vemgr::vemgr_pool_info>::disconnect_client(void)
0x18000be87  mov     rcx, [rbx]; ServerPort
0x18000be8a  test    rcx, rcx
0x18000be8d  jz      short loc_18000BEA2
0x18000be8f  call    cs:__imp_FltCloseCommunicationPort
0x18000be96  nop     dword ptr [rax+rax+00h]
0x18000be9b  mov     qword ptr [rbx], 0
0x18000bea2  mov     rcx, [rbx+18h]; Resource
0x18000bea6  test    rcx, rcx
0x18000bea9  jz      short loc_18000BECE
0x18000beab  call    cs:__imp_ExDeleteResourceLite
0x18000beb2  nop     dword ptr [rax+rax+00h]
0x18000beb7  mov     rcx, [rbx+18h]; P
0x18000bebb  test    rcx, rcx
0x18000bebe  jz      short loc_18000BECE
0x18000bec0  xor     edx, edx; Tag
0x18000bec2  call    cs:__imp_ExFreePoolWithTag
0x18000bec9  nop     dword ptr [rax+rax+00h]
0x18000bece  xor     edx, edx; Tag
0x18000bed0  mov     rcx, rbx; P
0x18000bed3  call    cs:__imp_ExFreePoolWithTag
0x18000beda  nop     dword ptr [rax+rax+00h]
0x18000bedf  add     rsp, 20h
0x18000bee3  pop     rbx
0x18000bee4  retn
```
