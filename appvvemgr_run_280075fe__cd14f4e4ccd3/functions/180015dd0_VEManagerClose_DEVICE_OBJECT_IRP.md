# VEManagerClose(_DEVICE_OBJECT *,_IRP *)

- ea: `0x180015dd0`
- end: `0x180015e55`
- name: `?VEManagerClose@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `133`
- prototype: `int(struct _DEVICE_OBJECT *, struct _IRP *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180015978`
- `0x180015dd0`
- `0x18001b3cc`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x180015e3b`
- `ntoskrnl!IofCompleteRequest` at `0x180015e3b`

## pseudocode

```c
__int64 __fastcall VEManagerClose(struct _DEVICE_OBJECT *a1, struct _IRP *a2)
{
  unsigned int v2; // ebx
  __int64 v4; // rax
  int v5; // eax

  v2 = 0;
  if ( vemgr::g_pDeviceExtn )
  {
    v4 = *((_QWORD *)vemgr::g_pDeviceExtn + 5);
    if ( v4 )
    {
      if ( *(_DWORD *)(v4 + 8) )
      {
        if ( *((_QWORD *)vemgr::g_pDeviceExtn + 4) )
        {
          v5 = VirtualEnvironmentManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::TerminateAll(*((__int64 **)vemgr::g_pDeviceExtn + 4));
          v2 = v5;
          if ( v5 < 0 )
            LogWrite(
              1,
              0,
              L"VEManagerClose() - Failed to termiante all virtual enviornments. error %d.",
              (unsigned int)v5);
        }
      }
    }
  }
  a2->IoStatus.Information = 0;
  a2->IoStatus.Status = v2;
  IofCompleteRequest(a2, 0);
  return v2;
}

```

## disassembly

```asm
0x180015dd0  mov     [rsp+arg_0], rbx
0x180015dd5  push    rdi
0x180015dd6  sub     rsp, 20h
0x180015dda  mov     rcx, cs:?g_pDeviceExtn@vemgr@@3PEAUDEVICE_EXTENSION@1@EA; vemgr::DEVICE_EXTENSION * vemgr::g_pDeviceExtn
0x180015de1  xor     ebx, ebx
0x180015de3  mov     rdi, rdx
0x180015de6  test    rcx, rcx
0x180015de9  jz      short loc_180015E2B
0x180015deb  mov     rax, [rcx+28h]
0x180015def  test    rax, rax
0x180015df2  jz      short loc_180015E2B
0x180015df4  mov     eax, [rax+8]
0x180015df7  test    eax, eax
0x180015df9  jz      short loc_180015E2B
0x180015dfb  cmp     [rcx+20h], rbx
0x180015dff  jz      short loc_180015E2B
0x180015e01  mov     rcx, cs:?g_pDeviceExtn@vemgr@@3PEAUDEVICE_EXTENSION@1@EA; vemgr::DEVICE_EXTENSION * vemgr::g_pDeviceExtn
0x180015e08  mov     rcx, [rcx+20h]
0x180015e0c  call    ?TerminateAll@?$VirtualEnvironmentManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@QEAAJXZ; VirtualEnvironmentManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::TerminateAll(void)
0x180015e11  mov     ebx, eax
0x180015e13  test    eax, eax
0x180015e15  jns     short loc_180015E2B
0x180015e17  xor     edx, edx
0x180015e19  lea     r8, aVemanagerclose; "VEManagerClose() - Failed to termiante "...
0x180015e20  mov     r9d, eax
0x180015e23  lea     ecx, [rdx+1]
0x180015e26  call    LogWrite
0x180015e2b  xor     edx, edx; PriorityBoost
0x180015e2d  mov     qword ptr [rdi+38h], 0
0x180015e35  mov     rcx, rdi; Irp
0x180015e38  mov     [rdi+30h], ebx
0x180015e3b  call    cs:__imp_IofCompleteRequest
0x180015e42  nop     dword ptr [rax+rax+00h]
0x180015e47  mov     eax, ebx
0x180015e49  mov     rbx, [rsp+28h+arg_0]
0x180015e4e  add     rsp, 20h
0x180015e52  pop     rdi
0x180015e53  retn
```
