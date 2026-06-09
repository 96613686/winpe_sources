# appv::shared::kernel::flt_connection<vemgr_listener_connection_manager,vemgr::vemgr_pool_info>::disconnect_client(void)

- ea: `0x18000bb18`
- end: `0x18000bbbd`
- name: `?disconnect_client@?$flt_connection@Vvemgr_listener_connection_manager@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@QEAAXXZ`
- size: `165`
- prototype: `void __fastcall(__int64)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180009ef0`
- `0x18000ade8`
- `0x18000b09c`
- `0x18000be70`
- `0x18000da30`

## callees

- `0x18000bb18`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x18000bb94`
- `ntoskrnl!ExReleaseResourceLite` at `0x18000bb94`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18000bba0`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18000bba0`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x18000bb4c`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x18000bb4c`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18000bb34`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18000bb34`
- `FLTMGR!FltCloseClientPort` at `0x18000bb73`
- `FLTMGR!FltCloseClientPort` at `0x18000bb73`

## pseudocode

```c
void __fastcall appv::shared::kernel::flt_connection<vemgr_listener_connection_manager,vemgr::vemgr_pool_info>::disconnect_client(
        __int64 a1)
{
  bool v1; // si
  struct _ERESOURCE *v3; // rcx

  v1 = 0;
  if ( *(_QWORD *)(a1 + 24) )
  {
    KeEnterCriticalRegion();
    v1 = ExAcquireResourceExclusiveLite(*(PERESOURCE *)(a1 + 24), 1u) == 1;
  }
  if ( *(_QWORD *)(a1 + 8) )
  {
    FltCloseClientPort(*(PFLT_FILTER *)(a1 + 40), (PFLT_PORT *)(a1 + 8));
    *(_QWORD *)(a1 + 8) = 0;
  }
  if ( v1 )
  {
    v3 = *(struct _ERESOURCE **)(a1 + 24);
    if ( v3 )
    {
      ExReleaseResourceLite(v3);
      KeLeaveCriticalRegion();
    }
  }
}

```

## disassembly

```asm
0x18000bb18  mov     [rsp+arg_0], rbx
0x18000bb1d  mov     [rsp+arg_8], rsi
0x18000bb22  push    rdi
0x18000bb23  sub     rsp, 20h
0x18000bb27  xor     sil, sil
0x18000bb2a  mov     rbx, rcx
0x18000bb2d  cmp     qword ptr [rcx+18h], 0
0x18000bb32  jz      short loc_18000BB62
0x18000bb34  call    cs:__imp_KeEnterCriticalRegion
0x18000bb3b  nop     dword ptr [rax+rax+00h]
0x18000bb40  mov     rcx, [rbx+18h]; Resource
0x18000bb44  mov     edi, 1
0x18000bb49  mov     dl, dil; Wait
0x18000bb4c  call    cs:__imp_ExAcquireResourceExclusiveLite
0x18000bb53  nop     dword ptr [rax+rax+00h]
0x18000bb58  cmp     al, dil
0x18000bb5b  movzx   esi, sil
0x18000bb5f  cmovz   esi, edi
0x18000bb62  lea     rdi, [rbx+8]
0x18000bb66  cmp     qword ptr [rdi], 0
0x18000bb6a  jz      short loc_18000BB86
0x18000bb6c  mov     rcx, [rbx+28h]; Filter
0x18000bb70  mov     rdx, rdi; ClientPort
0x18000bb73  call    cs:__imp_FltCloseClientPort
0x18000bb7a  nop     dword ptr [rax+rax+00h]
0x18000bb7f  mov     qword ptr [rdi], 0
0x18000bb86  test    sil, sil
0x18000bb89  jz      short loc_18000BBAC
0x18000bb8b  mov     rcx, [rbx+18h]; Resource
0x18000bb8f  test    rcx, rcx
0x18000bb92  jz      short loc_18000BBAC
0x18000bb94  call    cs:__imp_ExReleaseResourceLite
0x18000bb9b  nop     dword ptr [rax+rax+00h]
0x18000bba0  call    cs:__imp_KeLeaveCriticalRegion
0x18000bba7  nop     dword ptr [rax+rax+00h]
0x18000bbac  mov     rbx, [rsp+28h+arg_0]
0x18000bbb1  mov     rsi, [rsp+28h+arg_8]
0x18000bbb6  add     rsp, 20h
0x18000bbba  pop     rdi
0x18000bbbb  retn
```
