# VirtualEnvironmentManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::RemoveProcessFromVE(ulong,kernel_std::shared_ptr<VirtualEnvironment<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>> &)

- ea: `0x18000855c`
- end: `0x180008697`
- name: `?RemoveProcessFromVE@?$VirtualEnvironmentManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@AEAAJKAEAV?$shared_ptr@V?$VirtualEnvironment@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@Z`
- size: `315`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18000da60`
- `0x18001a594`

## callees

- `0x18000855c`
- `0x1800086a0`
- `0x180009d44`
- `0x18001b3cc`

## string_xrefs

- `0x18000863f`: `irtualEnvironmentManager::RemoveProcessFromVE() - Failed to remove process from VE. Package %s, user %s, pid %d, error %d`

## pseudocode

```c
__int64 __fastcall VirtualEnvironmentManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::RemoveProcessFromVE(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  int v4; // esi
  int v5; // edi
  __int64 v6; // rcx
  int *v7; // r9
  __int64 v8; // rax
  __int64 v9; // rdx
  unsigned int v10; // ecx
  __int16 v11; // r8
  __int16 v12; // ax
  int *v13; // r8
  __int64 v14; // rax
  __int64 v15; // r9
  unsigned int v16; // ecx
  __int16 v17; // dx
  __int16 v18; // ax
  __int64 v19; // r8
  __int64 v20; // r9
  int v22; // [rsp+88h] [rbp+20h] BYREF

  v22 = 0;
  v4 = a2;
  v5 = VirtualEnvironmentManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::RemoveProcessFromVEInternal(
         a1,
         a2,
         a3,
         &v22);
  if ( v5 >= 0 )
  {
    if ( v22 )
    {
      v19 = *a3;
      if ( *(_DWORD *)(*a3 + 40LL) )
        v20 = **(_QWORD **)(v19 + 72) + 48LL;
      else
        LODWORD(v20) = v19 + 136;
      return (unsigned int)VirtualEnvironmentManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::VETerminatedNotificationUpcall(
                             *(_DWORD *)(*a3 + 112LL),
                             v4,
                             (int)v19 + 120,
                             v20,
                             *(_DWORD *)(*a3 + 112LL));
    }
  }
  else
  {
    v6 = a3[1];
    v7 = &dword_18001E3EC;
    if ( v6 && *(_DWORD *)(v6 + 8) && (v8 = *a3) != 0 )
    {
      if ( *(_DWORD *)(v8 + 40) )
        v9 = **(_QWORD **)(v8 + 72) + 48LL;
      else
        v9 = v8 + 136;
      v10 = *(_DWORD *)v9 >> 1;
      if ( v10 > 0xFFFF )
        v11 = -1;
      else
        v11 = *(_DWORD *)v9 >> 1;
      v12 = 0;
      if ( v10 <= 0xFFFF )
        v12 = v11;
      if ( v12 )
        v13 = *(int **)(v9 + 8);
      else
        v13 = 0;
    }
    else
    {
      v13 = &dword_18001E3EC;
    }
    v14 = a3[1];
    if ( v14 && *(_DWORD *)(v14 + 8) && *a3 )
    {
      v15 = *(_QWORD *)(*a3 + 120LL);
      v16 = *(_DWORD *)v15 >> 1;
      if ( v16 > 0xFFFF )
        v17 = -1;
      else
        v17 = *(_DWORD *)v15 >> 1;
      v18 = 0;
      if ( v16 <= 0xFFFF )
        v18 = v17;
      if ( v18 )
        v7 = *(int **)(v15 + 8);
      else
        v7 = 0;
    }
    LogWrite(
      1,
      0,
      L"irtualEnvironmentManager::RemoveProcessFromVE() - Failed to remove process from VE. Package %s, user %s, pid %d, error %d",
      v7,
      v13,
      v4,
      v5);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000855c  mov     rax, rsp
0x18000855f  push    rbx
0x180008560  push    rbp
0x180008561  push    rsi
0x180008562  push    rdi
0x180008563  sub     rsp, 48h
0x180008567  xor     ebp, ebp
0x180008569  lea     r9, [rax+20h]
0x18000856d  mov     [rax+20h], ebp
0x180008570  mov     rbx, r8
0x180008573  mov     esi, edx
0x180008575  call    ?RemoveProcessFromVEInternal@?$VirtualEnvironmentManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@AEAAJKAEAV?$shared_ptr@V?$VirtualEnvironment@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@AEAW4RemoveVEDisposition@?$VirtualEnvironmentTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@Z; VirtualEnvironmentManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::RemoveProcessFromVEInternal(ulong,kernel_std::shared_ptr<VirtualEnvironment<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>> &,VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::RemoveVEDisposition &)
0x18000857a  mov     edi, eax
0x18000857c  test    eax, eax
0x18000857e  jns     loc_180008650
0x180008584  mov     rcx, [rbx+8]
0x180008588  lea     r9, dword_18001E3EC
0x18000858f  mov     r10d, 0FFFFh
0x180008595  test    rcx, rcx
0x180008598  jz      short loc_1800085EB
0x18000859a  mov     ecx, [rcx+8]
0x18000859d  test    ecx, ecx
0x18000859f  jz      short loc_1800085EB
0x1800085a1  mov     rax, [rbx]
0x1800085a4  test    rax, rax
0x1800085a7  jz      short loc_1800085EB
0x1800085a9  cmp     [rax+28h], ebp
0x1800085ac  jz      short loc_1800085BB
0x1800085ae  mov     rax, [rax+48h]
0x1800085b2  mov     rdx, [rax]
0x1800085b5  add     rdx, 30h ; '0'
0x1800085b9  jmp     short loc_1800085C2
0x1800085bb  lea     rdx, [rax+88h]
0x1800085c2  mov     ecx, [rdx]
0x1800085c4  shr     ecx, 1
0x1800085c6  cmp     ecx, r10d
0x1800085c9  ja      short loc_1800085D1
0x1800085cb  movzx   r8d, cx
0x1800085cf  jmp     short loc_1800085D4
0x1800085d1  mov     r8d, r10d
0x1800085d4  mov     eax, ebp
0x1800085d6  cmovbe  ax, r8w
0x1800085db  test    ax, ax
0x1800085de  jnz     short loc_1800085E5
0x1800085e0  mov     r8, rbp
0x1800085e3  jmp     short loc_1800085EE
0x1800085e5  mov     r8, [rdx+8]
0x1800085e9  jmp     short loc_1800085EE
0x1800085eb  mov     r8, r9
0x1800085ee  mov     rax, [rbx+8]
0x1800085f2  test    rax, rax
0x1800085f5  jz      short loc_180008630
0x1800085f7  mov     eax, [rax+8]
0x1800085fa  test    eax, eax
0x1800085fc  jz      short loc_180008630
0x1800085fe  mov     rax, [rbx]
0x180008601  test    rax, rax
0x180008604  jz      short loc_180008630
0x180008606  mov     r9, [rax+78h]
0x18000860a  mov     ecx, [r9]
0x18000860d  shr     ecx, 1
0x18000860f  cmp     ecx, r10d
0x180008612  ja      short loc_180008619
0x180008614  movzx   edx, cx
0x180008617  jmp     short loc_18000861C
0x180008619  mov     edx, r10d
0x18000861c  mov     eax, ebp
0x18000861e  cmovbe  ax, dx
0x180008622  test    ax, ax
0x180008625  jnz     short loc_18000862C
0x180008627  mov     r9, rbp
0x18000862a  jmp     short loc_180008630
0x18000862c  mov     r9, [r9+8]
0x180008630  xor     edx, edx
0x180008632  mov     [rsp+68h+var_38], edi
0x180008636  mov     [rsp+68h+var_40], esi
0x18000863a  mov     [rsp+68h+var_48], r8
0x18000863f  lea     r8, aIrtualenvironm; "irtualEnvironmentManager::RemoveProcess"...
0x180008646  lea     ecx, [rdx+1]
0x180008649  call    LogWrite
0x18000864e  jmp     short loc_18000868B
0x180008650  cmp     [rsp+68h+arg_18], ebp
0x180008657  jz      short loc_18000868B
0x180008659  mov     r8, [rbx]
0x18000865c  mov     ecx, [r8+70h]
0x180008660  cmp     [r8+28h], ebp
0x180008664  jz      short loc_180008673
0x180008666  mov     rax, [r8+48h]
0x18000866a  mov     r9, [rax]
0x18000866d  add     r9, 30h ; '0'
0x180008671  jmp     short loc_18000867A
0x180008673  lea     r9, [r8+88h]
0x18000867a  add     r8, 78h ; 'x'
0x18000867e  mov     dword ptr [rsp+68h+var_48], ecx
0x180008682  mov     edx, esi
0x180008684  call    ?VETerminatedNotificationUpcall@?$VirtualEnvironmentManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@AEAAJKAEBV?$shared_ptr@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@kernel_std@@AEBV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@K@Z; VirtualEnvironmentManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::VETerminatedNotificationUpcall(ulong,kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>> const &,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &,ulong)
0x180008689  mov     edi, eax
0x18000868b  mov     eax, edi
0x18000868d  add     rsp, 48h
0x180008691  pop     rdi
0x180008692  pop     rsi
0x180008693  pop     rbp
0x180008694  pop     rbx
0x180008695  retn
```
