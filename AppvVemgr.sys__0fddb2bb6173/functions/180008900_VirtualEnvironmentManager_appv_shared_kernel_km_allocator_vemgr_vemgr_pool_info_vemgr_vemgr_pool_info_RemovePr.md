# VirtualEnvironmentManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::RemoveProcessFromVETracker(ulong,kernel_std::shared_ptr<VirtualEnvironment<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>> &,VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::RemoveVEDisposition &)

- ea: `0x180008900`
- end: `0x180008b89`
- name: `?RemoveProcessFromVETracker@?$VirtualEnvironmentManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@AEAAJKAEAV?$shared_ptr@V?$VirtualEnvironment@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@AEAW4RemoveVEDisposition@?$VirtualEnvironmentTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@Z`
- size: `649`
- prototype: `__int64 __fastcall(_QWORD *, unsigned int, __int64 *, _DWORD *)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, registry_config`

## callers

- `0x180005ec4`
- `0x180008778`

## callees

- `0x180007f88`
- `0x180008900`
- `0x180008fc8`
- `0x1800090c4`
- `0x180009208`
- `0x18001b3cc`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x180008ad1`
- `ntoskrnl!KeReleaseMutex` at `0x180008ad1`
- `ntoskrnl!KeWaitForSingleObject` at `0x180008a47`
- `ntoskrnl!KeWaitForSingleObject` at `0x180008a47`

## string_xrefs

- `0x180008b5a`: `VirtualEnvironmentManager::RemoveProcessFromVETracker() - Virtual Environment deleted. Package moniker %s. User SID %s.`
- `0x180008ab2`: `VfsVolumeManager::RemoveVolumes() - Failed to remove volume reference from tracker. Volume: %s. Error: %d`
- `0x18000898c`: `VirtualEnvironmentManager::RemovePackageNotification() - Package remove operation not sent to VFS because the VFS has been set to disabled.`
- `0x1800089cc`: `VFSNotification::RemovePackage() - VFS notification: remove package configuration. Package moniker %s. Result %d.`

## pseudocode

```c
__int64 __fastcall VirtualEnvironmentManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::RemoveProcessFromVETracker(
        _QWORD *a1,
        unsigned int a2,
        __int64 *a3,
        _DWORD *a4)
{
  __int64 result; // rax
  __int64 v8; // rax
  __int64 v9; // rcx
  __int64 v10; // rdi
  unsigned int v11; // ecx
  __int16 v12; // dx
  __int16 v13; // ax
  __int64 v14; // r9
  __int64 v15; // rcx
  PRKMUTEX *v16; // r14
  __int64 v17; // rsi
  PRKMUTEX v18; // rcx
  _QWORD *v19; // rbx
  _QWORD *v20; // rbp
  int v21; // edi
  int v22; // esi
  unsigned int v23; // ecx
  __int16 v24; // dx
  __int16 v25; // ax
  __int64 v26; // r9
  __int64 v27; // r8
  __int64 v28; // rcx
  unsigned int v29; // edx
  bool v30; // cc
  __int16 v31; // r9
  __int16 v32; // ax
  __int64 v33; // rdx
  __int64 v34; // r9
  unsigned int v35; // ecx
  __int16 v36; // r8
  __int16 v37; // ax
  __int64 v38; // r9
  PLARGE_INTEGER Timeout; // [rsp+20h] [rbp-58h]
  union _LARGE_INTEGER v40; // [rsp+80h] [rbp+8h] BYREF

  result = VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::RemoveVirtualProcess(
             *a1,
             a3,
             a2,
             a4);
  if ( (int)result >= 0 )
  {
    if ( !*a4 )
      return 0;
    VirtualEnvironmentManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::RemoveUserNotification(
      a1,
      *a3 + 40);
    if ( *a4 == 2 )
    {
      v8 = *a3;
      v9 = a1[7];
      LOBYTE(v40.LowPart) = 0;
      v10 = *(_QWORD *)(v8 + 120);
      if ( (int)ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::IsVfsStateDisabled(
                  v9,
                  &v40) >= 0
        && LOBYTE(v40.LowPart) )
      {
        LogWrite(
          4,
          0,
          L"VirtualEnvironmentManager::RemovePackageNotification() - Package remove operation not sent to VFS because the "
           "VFS has been set to disabled.");
      }
      else
      {
        v11 = *(_DWORD *)v10 >> 1;
        if ( v11 > 0xFFFF )
          v12 = -1;
        else
          v12 = *(_DWORD *)v10 >> 1;
        v13 = 0;
        v14 = 0;
        if ( v11 <= 0xFFFF )
          v13 = v12;
        if ( v13 )
          v14 = *(_QWORD *)(v10 + 8);
        LogWrite(
          3,
          0,
          L"VFSNotification::RemovePackage() - VFS notification: remove package configuration. Package moniker %s. Result %d.",
          v14,
          -1073741822);
      }
    }
    v15 = a1[7];
    LOBYTE(v40.LowPart) = 0;
    if ( (int)ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::IsVfsStateDisabled(
                v15,
                &v40) >= 0
      && LOBYTE(v40.LowPart) )
    {
      LogWrite(
        4,
        0,
        L"VirtualEnvironmentManager::AddProcessToVETracker() - Add volume operation not sent to VFS because the VFS has be"
         "en set to disabled.");
LABEL_36:
      v27 = *a3;
      if ( *(_DWORD *)(*a3 + 40) )
        v28 = **(_QWORD **)(v27 + 72) + 48LL;
      else
        v28 = v27 + 136;
      v29 = *(_DWORD *)v28 >> 1;
      v30 = v29 <= 0xFFFF;
      if ( v29 > 0xFFFF )
        v31 = -1;
      else
        v31 = *(_DWORD *)v28 >> 1;
      v32 = 0;
      v33 = 0;
      if ( v30 )
        v32 = v31;
      if ( v32 )
        v33 = *(_QWORD *)(v28 + 8);
      v34 = *(_QWORD *)(v27 + 120);
      v35 = *(_DWORD *)v34 >> 1;
      if ( v35 > 0xFFFF )
        v36 = -1;
      else
        v36 = *(_DWORD *)v34 >> 1;
      v37 = 0;
      if ( v35 <= 0xFFFF )
        v37 = v36;
      if ( v37 )
        v38 = *(_QWORD *)(v34 + 8);
      else
        v38 = 0;
      LogWrite(
        3,
        0,
        L"VirtualEnvironmentManager::RemoveProcessFromVETracker() - Virtual Environment deleted. Package moniker %s. User SID %s.",
        v38,
        v33);
      return 0;
    }
    v16 = (PRKMUTEX *)a1[6];
    v17 = *a3;
    v18 = *v16;
    if ( *v16 && (v40.QuadPart = -300000000, KeWaitForSingleObject(v18, Executive, 0, 0, &v40)) )
    {
      return (unsigned int)-1073741643;
    }
    else
    {
      v19 = *(_QWORD **)(v17 + 200);
      v20 = (_QWORD *)(v17 + 176);
      v21 = 0;
      while ( v19 != v20 )
      {
        v22 = VfsVolumeManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::RemoveVolume(
                v16,
                v19);
        if ( v22 < 0 )
        {
          v23 = *(_DWORD *)*v19 >> 1;
          if ( v23 > 0xFFFF )
            v24 = -1;
          else
            v24 = *(_DWORD *)*v19 >> 1;
          v25 = 0;
          if ( v23 <= 0xFFFF )
            v25 = v24;
          if ( v25 )
            v26 = *(_QWORD *)(*v19 + 8LL);
          else
            v26 = 0;
          LODWORD(Timeout) = v22;
          LogWrite(
            1,
            0,
            L"VfsVolumeManager::RemoveVolumes() - Failed to remove volume reference from tracker. Volume: %s. Error: %d",
            v26,
            Timeout);
          if ( v21 >= 0 )
            v21 = v22;
        }
        v19 = (_QWORD *)v19[3];
      }
      KeReleaseMutex(*v16, 0);
      if ( v21 >= 0 )
        goto LABEL_36;
    }
    return (unsigned int)v21;
  }
  return result;
}

```

## disassembly

```asm
0x180008900  push    rbx
0x180008902  push    rbp
0x180008903  push    rsi
0x180008904  push    rdi
0x180008905  push    r12
0x180008907  push    r13
0x180008909  push    r14
0x18000890b  push    r15
0x18000890d  sub     rsp, 38h
0x180008911  mov     r15, r8
0x180008914  mov     rbx, rcx
0x180008917  mov     rcx, [rcx]
0x18000891a  mov     r8d, edx
0x18000891d  mov     rdx, r15
0x180008920  mov     rdi, r9
0x180008923  call    ?RemoveVirtualProcess@?$VirtualEnvironmentTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@QEAAJAEBV?$shared_ptr@V?$VirtualEnvironment@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@KAEAW4RemoveVEDisposition@1@@Z; VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::RemoveVirtualProcess(kernel_std::shared_ptr<VirtualEnvironment<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>> const &,ulong,VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::RemoveVEDisposition &)
0x180008928  xor     r12d, r12d
0x18000892b  test    eax, eax
0x18000892d  js      loc_180008B77
0x180008933  cmp     [rdi], r12d
0x180008936  jnz     short loc_18000893F
0x180008938  xor     eax, eax
0x18000893a  jmp     loc_180008B77
0x18000893f  mov     rdx, [r15]
0x180008942  mov     rcx, rbx
0x180008945  add     rdx, 28h ; '('
0x180008949  call    ?RemoveUserNotification@?$VirtualEnvironmentManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@AEAAXAEBV?$doubly_linked_list@V?$shared_ptr@V?$Generic_UserConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@Z; VirtualEnvironmentManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::RemoveUserNotification(appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_UserConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>,vemgr::vemgr_pool_info> const &)
0x18000894e  cmp     dword ptr [rdi], 2
0x180008951  mov     esi, 4
0x180008956  mov     r13d, 0FFFFh
0x18000895c  jnz     short loc_1800089DB
0x18000895e  mov     rax, [r15]
0x180008961  lea     rdx, [rsp+78h+arg_0]
0x180008969  mov     rcx, [rbx+38h]
0x18000896d  mov     byte ptr [rsp+78h+arg_0], r12b
0x180008975  mov     rdi, [rax+78h]
0x180008979  call    ?IsVfsStateDisabled@?$ConfigurationManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@QEAAJAEA_N@Z; ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::IsVfsStateDisabled(bool &)
0x18000897e  test    eax, eax
0x180008980  js      short loc_18000899E
0x180008982  cmp     byte ptr [rsp+78h+arg_0], r12b
0x18000898a  jz      short loc_18000899E
0x18000898c  lea     r8, aVirtualenviron_10; "VirtualEnvironmentManager::RemovePackag"...
0x180008993  xor     edx, edx
0x180008995  mov     ecx, esi
0x180008997  call    LogWrite
0x18000899c  jmp     short loc_1800089DB
0x18000899e  mov     ecx, [rdi]
0x1800089a0  shr     ecx, 1
0x1800089a2  cmp     ecx, r13d
0x1800089a5  ja      short loc_1800089AC
0x1800089a7  movzx   edx, cx
0x1800089aa  jmp     short loc_1800089AF
0x1800089ac  mov     edx, r13d
0x1800089af  mov     eax, r12d
0x1800089b2  mov     r9, r12
0x1800089b5  cmovbe  ax, dx
0x1800089b9  test    ax, ax
0x1800089bc  jz      short loc_1800089C2
0x1800089be  mov     r9, [rdi+8]
0x1800089c2  xor     edx, edx
0x1800089c4  mov     dword ptr [rsp+78h+Timeout], 0C0000002h
0x1800089cc  lea     r8, aVfsnotificatio_0; "VFSNotification::RemovePackage() - VFS "...
0x1800089d3  lea     ecx, [rdx+3]
0x1800089d6  call    LogWrite
0x1800089db  mov     rcx, [rbx+38h]
0x1800089df  lea     rdx, [rsp+78h+arg_0]
0x1800089e7  mov     byte ptr [rsp+78h+arg_0], r12b
0x1800089ef  call    ?IsVfsStateDisabled@?$ConfigurationManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@QEAAJAEA_N@Z; ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::IsVfsStateDisabled(bool &)
0x1800089f4  test    eax, eax
0x1800089f6  js      short loc_180008A17
0x1800089f8  cmp     byte ptr [rsp+78h+arg_0], r12b
0x180008a00  jz      short loc_180008A17
0x180008a02  lea     r8, aVirtualenviron_26; "VirtualEnvironmentManager::AddProcessTo"...
0x180008a09  xor     edx, edx
0x180008a0b  mov     ecx, esi
0x180008a0d  call    LogWrite
0x180008a12  jmp     loc_180008AE5
0x180008a17  mov     r14, [rbx+30h]
0x180008a1b  mov     rsi, [r15]
0x180008a1e  mov     rcx, [r14]; Object
0x180008a21  test    rcx, rcx
0x180008a24  jz      short loc_180008A5B
0x180008a26  lea     rax, [rsp+78h+arg_0]
0x180008a2e  mov     qword ptr [rsp+78h+arg_0], 0FFFFFFFFEE1E5D00h
0x180008a3a  xor     r9d, r9d; Alertable
0x180008a3d  mov     [rsp+78h+Timeout], rax; Timeout
0x180008a42  xor     r8d, r8d; WaitMode
0x180008a45  xor     edx, edx; WaitReason
0x180008a47  call    cs:__imp_KeWaitForSingleObject
0x180008a4e  nop     dword ptr [rax+rax+00h]
0x180008a53  test    eax, eax
0x180008a55  jnz     loc_180008B70
0x180008a5b  mov     rbx, [rsi+0C8h]
0x180008a62  lea     rbp, [rsi+0B0h]
0x180008a69  mov     edi, r12d
0x180008a6c  cmp     rbx, rbp
0x180008a6f  jz      short loc_180008ACC
0x180008a71  mov     rdx, rbx
0x180008a74  mov     rcx, r14
0x180008a77  call    ?RemoveVolume@?$VfsVolumeManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@AEAAJAEBV?$shared_ptr@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@kernel_std@@@Z; VfsVolumeManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::RemoveVolume(kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>> const &)
0x180008a7c  mov     esi, eax
0x180008a7e  test    eax, eax
0x180008a80  jns     short loc_180008AC6
0x180008a82  mov     r9, [rbx]
0x180008a85  mov     ecx, [r9]
0x180008a88  shr     ecx, 1
0x180008a8a  cmp     ecx, r13d
0x180008a8d  ja      short loc_180008A94
0x180008a8f  movzx   edx, cx
0x180008a92  jmp     short loc_180008A97
0x180008a94  mov     edx, r13d
0x180008a97  mov     eax, r12d
0x180008a9a  cmovbe  ax, dx
0x180008a9e  test    ax, ax
0x180008aa1  jnz     short loc_180008AA8
0x180008aa3  mov     r9, r12
0x180008aa6  jmp     short loc_180008AAC
0x180008aa8  mov     r9, [r9+8]
0x180008aac  xor     edx, edx
0x180008aae  mov     dword ptr [rsp+78h+Timeout], esi
0x180008ab2  lea     r8, aVfsvolumemanag_1; "VfsVolumeManager::RemoveVolumes() - Fai"...
0x180008ab9  lea     ecx, [rdx+1]
0x180008abc  call    LogWrite
0x180008ac1  test    edi, edi
0x180008ac3  cmovns  edi, esi
0x180008ac6  mov     rbx, [rbx+18h]
0x180008aca  jmp     short loc_180008A6C
0x180008acc  mov     rcx, [r14]; Mutex
0x180008acf  xor     edx, edx; Wait
0x180008ad1  call    cs:__imp_KeReleaseMutex
0x180008ad8  nop     dword ptr [rax+rax+00h]
0x180008add  test    edi, edi
0x180008adf  js      loc_180008B75
0x180008ae5  mov     r8, [r15]
0x180008ae8  cmp     [r8+28h], r12d
0x180008aec  jnz     short loc_180008AF7
0x180008aee  lea     rcx, [r8+88h]
0x180008af5  jmp     short loc_180008B02
0x180008af7  mov     rax, [r8+48h]
0x180008afb  mov     rcx, [rax]
0x180008afe  add     rcx, 30h ; '0'
0x180008b02  mov     edx, [rcx]
0x180008b04  shr     edx, 1
0x180008b06  cmp     edx, r13d
0x180008b09  ja      short loc_180008B11
0x180008b0b  movzx   r9d, dx
0x180008b0f  jmp     short loc_180008B14
0x180008b11  mov     r9d, r13d
0x180008b14  mov     eax, r12d
0x180008b17  mov     rdx, r12
0x180008b1a  cmovbe  ax, r9w
0x180008b1f  test    ax, ax
0x180008b22  jz      short loc_180008B28
0x180008b24  mov     rdx, [rcx+8]
0x180008b28  mov     r9, [r8+78h]
0x180008b2c  mov     ecx, [r9]
0x180008b2f  shr     ecx, 1
0x180008b31  cmp     ecx, r13d
0x180008b34  ja      short loc_180008B3C
0x180008b36  movzx   r8d, cx
0x180008b3a  jmp     short loc_180008B3F
0x180008b3c  mov     r8d, r13d
0x180008b3f  mov     eax, r12d
0x180008b42  cmovbe  ax, r8w
0x180008b47  test    ax, ax
0x180008b4a  jnz     short loc_180008B51
0x180008b4c  mov     r9, r12
0x180008b4f  jmp     short loc_180008B55
0x180008b51  mov     r9, [r9+8]
0x180008b55  mov     [rsp+78h+Timeout], rdx
0x180008b5a  lea     r8, aVirtualenviron_24; "VirtualEnvironmentManager::RemoveProces"...
0x180008b61  xor     edx, edx
0x180008b63  lea     ecx, [rdx+3]
0x180008b66  call    LogWrite
0x180008b6b  jmp     loc_180008938
0x180008b70  mov     edi, 0C00000B5h
0x180008b75  mov     eax, edi
0x180008b77  add     rsp, 38h
0x180008b7b  pop     r15
0x180008b7d  pop     r14
0x180008b7f  pop     r13
0x180008b81  pop     r12
0x180008b83  pop     rdi
0x180008b84  pop     rsi
0x180008b85  pop     rbp
0x180008b86  pop     rbx
0x180008b87  retn
```
