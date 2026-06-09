# VirtualEnvironmentManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::RemoveProcessFromVEInternal_Unlocked(ulong,kernel_std::shared_ptr<VirtualEnvironment<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>> &,VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::RemoveVEDisposition &)

- ea: `0x180008778`
- end: `0x1800088fa`
- name: `?RemoveProcessFromVEInternal_Unlocked@?$VirtualEnvironmentManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@AEAAJKAEAV?$shared_ptr@V?$VirtualEnvironment@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@AEAW4RemoveVEDisposition@?$VirtualEnvironmentTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@Z`
- size: `386`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64 *, __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180008164`
- `0x1800086a0`

## callees

- `0x180008778`
- `0x180008900`
- `0x180008dd4`
- `0x18001b3cc`

## string_xrefs

- `0x180008822`: `VirtualEnvironmentManager::RemoveProcessFromVEInternal_Unlocked() - Failed to remove process from ProcessTracker. Package %s, user %s, pid %d, error %d`
- `0x1800088c8`: `VirtualEnvironmentManager::RemoveProcessFromVEInternal_Unlocked() - Failed to remove process from VETracker. Package %s, user %s, pid %d, error %d`

## pseudocode

```c
__int64 __fastcall VirtualEnvironmentManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::RemoveProcessFromVEInternal_Unlocked(
        __int64 a1,
        unsigned int a2,
        __int64 *a3,
        __int64 a4)
{
  int v8; // ebx
  __int64 v9; // r8
  __int64 v10; // rcx
  unsigned int v11; // edx
  __int16 v12; // r9
  __int16 v13; // ax
  __int64 v14; // r10
  __int64 v15; // r9
  unsigned int v16; // ecx
  __int16 v17; // dx
  __int16 v18; // ax
  __int64 v19; // r9
  int v20; // edi
  __int64 v21; // r8
  __int64 v22; // rdx
  unsigned int v23; // ecx
  __int16 v24; // r9
  __int16 v25; // ax
  __int64 v26; // r10
  __int64 v27; // r9
  unsigned int v28; // ecx
  __int16 v29; // dx
  __int16 v30; // ax
  __int64 v31; // r9
  __int64 v33; // [rsp+28h] [rbp-50h]
  __int64 v34; // [rsp+30h] [rbp-48h]

  v8 = VirtualEnvironmentManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::RemoveProcessVEFromProcessTracker();
  if ( v8 < 0 )
  {
    v9 = *a3;
    if ( *(_DWORD *)(*a3 + 40) )
      v10 = **(_QWORD **)(v9 + 72) + 48LL;
    else
      v10 = v9 + 136;
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
    v15 = *(_QWORD *)(v9 + 120);
    v16 = *(_DWORD *)v15 >> 1;
    if ( v16 > 0xFFFF )
      v17 = -1;
    else
      v17 = *(_DWORD *)v15 >> 1;
    v18 = 0;
    if ( v16 <= 0xFFFF )
      v18 = v17;
    if ( v18 )
      v19 = *(_QWORD *)(v15 + 8);
    else
      v19 = 0;
    LogWrite(
      1,
      0,
      L"VirtualEnvironmentManager::RemoveProcessFromVEInternal_Unlocked() - Failed to remove process from ProcessTracker. "
       "Package %s, user %s, pid %d, error %d",
      v19,
      v14,
      a2,
      v8);
  }
  v20 = VirtualEnvironmentManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::RemoveProcessFromVETracker(
          a1,
          a2,
          a3,
          a4);
  if ( v20 < 0 )
  {
    v21 = *a3;
    if ( *(_DWORD *)(*a3 + 40) )
      v22 = **(_QWORD **)(v21 + 72) + 48LL;
    else
      v22 = v21 + 136;
    v23 = *(_DWORD *)v22 >> 1;
    if ( v23 > 0xFFFF )
      v24 = -1;
    else
      v24 = *(_DWORD *)v22 >> 1;
    v25 = 0;
    v26 = 0;
    if ( v23 <= 0xFFFF )
      v25 = v24;
    if ( v25 )
      v26 = *(_QWORD *)(v22 + 8);
    v27 = *(_QWORD *)(v21 + 120);
    v28 = *(_DWORD *)v27 >> 1;
    if ( v28 > 0xFFFF )
      v29 = -1;
    else
      v29 = *(_DWORD *)v27 >> 1;
    v30 = 0;
    if ( v28 <= 0xFFFF )
      v30 = v29;
    if ( v30 )
      v31 = *(_QWORD *)(v27 + 8);
    else
      v31 = 0;
    LODWORD(v34) = v20;
    LODWORD(v33) = a2;
    LogWrite(
      1,
      0,
      L"VirtualEnvironmentManager::RemoveProcessFromVEInternal_Unlocked() - Failed to remove process from VETracker. Packa"
       "ge %s, user %s, pid %d, error %d",
      v31,
      v26,
      v33,
      v34);
  }
  if ( v8 >= 0 )
  {
    v8 = 0;
    if ( v20 < 0 )
      return (unsigned int)v20;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180008778  push    rbx
0x18000877a  push    rbp
0x18000877b  push    rsi
0x18000877c  push    rdi
0x18000877d  push    r12
0x18000877f  push    r14
0x180008781  push    r15
0x180008783  sub     rsp, 40h
0x180008787  mov     r14, r9
0x18000878a  mov     rsi, r8
0x18000878d  mov     ebp, edx
0x18000878f  mov     rdi, rcx
0x180008792  call    ?RemoveProcessVEFromProcessTracker@?$VirtualEnvironmentManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@AEAAJKAEAV?$shared_ptr@V?$VirtualEnvironment@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@Z; VirtualEnvironmentManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::RemoveProcessVEFromProcessTracker(ulong,kernel_std::shared_ptr<VirtualEnvironment<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>> &)
0x180008797  xor     r15d, r15d
0x18000879a  mov     ebx, eax
0x18000879c  mov     r12d, 0FFFFh
0x1800087a2  test    eax, eax
0x1800087a4  jns     loc_180008836
0x1800087aa  mov     r8, [rsi]
0x1800087ad  cmp     [r8+28h], r15d
0x1800087b1  jz      short loc_1800087C0
0x1800087b3  mov     rax, [r8+48h]
0x1800087b7  mov     rcx, [rax]
0x1800087ba  add     rcx, 30h ; '0'
0x1800087be  jmp     short loc_1800087C7
0x1800087c0  lea     rcx, [r8+88h]
0x1800087c7  mov     edx, [rcx]
0x1800087c9  shr     edx, 1
0x1800087cb  cmp     edx, r12d
0x1800087ce  ja      short loc_1800087D6
0x1800087d0  movzx   r9d, dx
0x1800087d4  jmp     short loc_1800087D9
0x1800087d6  mov     r9d, r12d
0x1800087d9  mov     eax, r15d
0x1800087dc  mov     r10, r15
0x1800087df  cmovbe  ax, r9w
0x1800087e4  test    ax, ax
0x1800087e7  jz      short loc_1800087ED
0x1800087e9  mov     r10, [rcx+8]
0x1800087ed  mov     r9, [r8+78h]
0x1800087f1  mov     ecx, [r9]
0x1800087f4  shr     ecx, 1
0x1800087f6  cmp     ecx, r12d
0x1800087f9  ja      short loc_180008800
0x1800087fb  movzx   edx, cx
0x1800087fe  jmp     short loc_180008803
0x180008800  mov     edx, r12d
0x180008803  mov     eax, r15d
0x180008806  cmovbe  ax, dx
0x18000880a  test    ax, ax
0x18000880d  jnz     short loc_180008814
0x18000880f  mov     r9, r15
0x180008812  jmp     short loc_180008818
0x180008814  mov     r9, [r9+8]
0x180008818  xor     edx, edx
0x18000881a  mov     dword ptr [rsp+78h+var_48], ebx
0x18000881e  mov     dword ptr [rsp+78h+var_50], ebp
0x180008822  lea     r8, aVirtualenviron; "VirtualEnvironmentManager::RemoveProces"...
0x180008829  mov     [rsp+78h+var_58], r10
0x18000882e  lea     ecx, [rdx+1]
0x180008831  call    LogWrite
0x180008836  mov     r9, r14
0x180008839  mov     r8, rsi
0x18000883c  mov     edx, ebp
0x18000883e  mov     rcx, rdi
0x180008841  call    ?RemoveProcessFromVETracker@?$VirtualEnvironmentManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@AEAAJKAEAV?$shared_ptr@V?$VirtualEnvironment@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@AEAW4RemoveVEDisposition@?$VirtualEnvironmentTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@Z; VirtualEnvironmentManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::RemoveProcessFromVETracker(ulong,kernel_std::shared_ptr<VirtualEnvironment<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>> &,VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::RemoveVEDisposition &)
0x180008846  mov     edi, eax
0x180008848  test    eax, eax
0x18000884a  jns     loc_1800088DC
0x180008850  mov     r8, [rsi]
0x180008853  cmp     [r8+28h], r15d
0x180008857  jz      short loc_180008866
0x180008859  mov     rcx, [r8+48h]
0x18000885d  mov     rdx, [rcx]
0x180008860  add     rdx, 30h ; '0'
0x180008864  jmp     short loc_18000886D
0x180008866  lea     rdx, [r8+88h]
0x18000886d  mov     ecx, [rdx]
0x18000886f  shr     ecx, 1
0x180008871  cmp     ecx, r12d
0x180008874  ja      short loc_18000887C
0x180008876  movzx   r9d, cx
0x18000887a  jmp     short loc_18000887F
0x18000887c  mov     r9d, r12d
0x18000887f  mov     eax, r15d
0x180008882  mov     r10, r15
0x180008885  cmovbe  ax, r9w
0x18000888a  test    ax, ax
0x18000888d  jz      short loc_180008893
0x18000888f  mov     r10, [rdx+8]
0x180008893  mov     r9, [r8+78h]
0x180008897  mov     ecx, [r9]
0x18000889a  shr     ecx, 1
0x18000889c  cmp     ecx, r12d
0x18000889f  ja      short loc_1800088A6
0x1800088a1  movzx   edx, cx
0x1800088a4  jmp     short loc_1800088A9
0x1800088a6  mov     edx, r12d
0x1800088a9  mov     eax, r15d
0x1800088ac  cmovbe  ax, dx
0x1800088b0  test    ax, ax
0x1800088b3  jnz     short loc_1800088BA
0x1800088b5  mov     r9, r15
0x1800088b8  jmp     short loc_1800088BE
0x1800088ba  mov     r9, [r9+8]
0x1800088be  xor     edx, edx
0x1800088c0  mov     dword ptr [rsp+78h+var_48], edi
0x1800088c4  mov     dword ptr [rsp+78h+var_50], ebp
0x1800088c8  lea     r8, aVirtualenviron_4; "VirtualEnvironmentManager::RemoveProces"...
0x1800088cf  mov     [rsp+78h+var_58], r10
0x1800088d4  lea     ecx, [rdx+1]
0x1800088d7  call    LogWrite
0x1800088dc  test    ebx, ebx
0x1800088de  js      short loc_1800088E8
0x1800088e0  test    edi, edi
0x1800088e2  mov     ebx, r15d
0x1800088e5  cmovs   ebx, edi
0x1800088e8  mov     eax, ebx
0x1800088ea  add     rsp, 40h
0x1800088ee  pop     r15
0x1800088f0  pop     r14
0x1800088f2  pop     r12
0x1800088f4  pop     rdi
0x1800088f5  pop     rsi
0x1800088f6  pop     rbp
0x1800088f7  pop     rbx
0x1800088f8  retn
```
