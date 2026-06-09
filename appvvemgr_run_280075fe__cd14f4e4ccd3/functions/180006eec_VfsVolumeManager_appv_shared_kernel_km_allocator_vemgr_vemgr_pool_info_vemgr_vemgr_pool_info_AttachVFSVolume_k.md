# VfsVolumeManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::AttachVFSVolume(kernel_std::shared_ptr<VfsVolumeManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVolume<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>> const &)

- ea: `0x180006eec`
- end: `0x180007199`
- name: `?AttachVFSVolume@?$VfsVolumeManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@AEAAJAEBV?$shared_ptr@V?$CountedVolume@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@?$VfsVolumeManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@Z`
- size: `685`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180006880`

## callees

- `0x180006eec`
- `0x18000ce10`
- `0x18000e23c`
- `0x18001b3cc`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x1800070f6`
- `ntoskrnl!ZwClose` at `0x1800070f6`
- `ntoskrnl!KeDelayExecutionThread` at `0x180007021`
- `ntoskrnl!KeDelayExecutionThread` at `0x180007021`
- `FLTMGR!FltAttachVolume` at `0x180006f3d`
- `FLTMGR!FltAttachVolume` at `0x180006f3d`
- `FLTMGR!FltGetFilterFromName` at `0x180006f19`
- `FLTMGR!FltGetFilterFromName` at `0x180006f19`
- `FLTMGR!FltObjectDereference` at `0x180007063`
- `FLTMGR!FltObjectDereference` at `0x180007063`
- `FLTMGR!FltEnumerateInstances` at `0x180006fe1`
- `FLTMGR!FltEnumerateInstances` at `0x180006fe1`

## string_xrefs

- `0x180006f63`: `\Registry\Machine\Software\Microsoft\AppV\MAV\Configuration`
- `0x1800070dd`: `VfsVolumeManager::AttachVFSVolume() - Failed to read MaxAttachWaitTimeInMilliseconds from the registry after a collision attaching filter driver to volume. Volume: %s. Error: %d`

## pseudocode

```c
NTSTATUS __fastcall VfsVolumeManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::AttachVFSVolume(
        const UNICODE_STRING *a1,
        __int64 *a2)
{
  PFLT_FILTER *p_Buffer; // r15
  NTSTATUS result; // eax
  NTSTATUS v5; // ebx
  int v6; // eax
  PFLT_INSTANCE v7; // rbx
  int value; // edx
  ULONG v9; // r14d
  unsigned int v10; // r12d
  __int64 v11; // rcx
  struct _FLT_FILTER *v12; // rdx
  NTSTATUS v13; // eax
  NTSTATUS v14; // r8d
  unsigned int v15; // ecx
  __int16 v16; // dx
  __int16 v17; // ax
  __int64 v18; // r9
  unsigned int v19; // ecx
  __int16 v20; // r8
  __int16 v21; // ax
  __int64 v22; // r9
  unsigned int v23; // ecx
  __int16 v24; // dx
  unsigned int v25; // ecx
  __int16 v26; // dx
  __int16 v27; // ax
  __int64 v28; // r9
  __int16 v29; // ax
  __int64 v30; // r9
  PULONG NumberInstancesReturned; // [rsp+20h] [rbp-10h]
  ULONG v32; // [rsp+70h] [rbp+40h] BYREF
  PFLT_INSTANCE InstanceList; // [rsp+80h] [rbp+50h] BYREF
  union _LARGE_INTEGER Interval; // [rsp+88h] [rbp+58h] BYREF

  p_Buffer = (PFLT_FILTER *)&a1[1].Buffer;
  if ( a1[1].Buffer || (result = FltGetFilterFromName(a1 + 3, p_Buffer), result >= 0) )
  {
    v5 = FltAttachVolume(*p_Buffer, *(PFLT_VOLUME *)(*a2 + 32), 0, 0);
    if ( v5 == -1071906798 )
    {
      v32 = 0;
      InstanceList = 0;
      v6 = registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::open_key(
             0,
             L"\\Registry\\Machine\\Software\\Microsoft\\AppV\\MAV\\Configuration",
             &InstanceList);
      v7 = InstanceList;
      value = v6;
      if ( v6 < 0
        || (value = registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::get_value(
                      InstanceList,
                      L"MaxAttachWaitTimeInMilliseconds",
                      &v32),
            value < 0) )
      {
        v19 = *(_DWORD *)*a2 >> 1;
        if ( v19 > 0xFFFF )
          v20 = -1;
        else
          v20 = *(_DWORD *)*a2 >> 1;
        v21 = 0;
        if ( v19 <= 0xFFFF )
          v21 = v20;
        if ( v21 )
          v22 = *(_QWORD *)(*a2 + 8);
        else
          v22 = 0;
        LogWrite(
          2,
          0,
          L"VfsVolumeManager::AttachVFSVolume() - Failed to read MaxAttachWaitTimeInMilliseconds from the registry after a"
           " collision attaching filter driver to volume. Volume: %s. Error: %d",
          v22,
          value);
      }
      else
      {
        v9 = v32;
        if ( v32 )
        {
          v10 = 0;
          if ( v32 > 0x2710 )
            v9 = 10000;
          while ( 1 )
          {
            v11 = *a2;
            v12 = *p_Buffer;
            v32 = 0;
            InstanceList = 0;
            v13 = FltEnumerateInstances(*(PFLT_VOLUME *)(v11 + 32), v12, &InstanceList, 1u, &v32);
            v14 = v13;
            if ( v13 < 0 || v32 )
              break;
            Interval.QuadPart = (int)(-10000 * v9) / 100;
            KeDelayExecutionThread(0, 0, &Interval);
            if ( (int)++v10 >= 100 )
            {
              if ( v10 == 100 )
                LogWrite(
                  3,
                  0,
                  L"VfsVolumeManager::AttachVFSVolume() - Collision occurred while attaching to the volume, instance is st"
                   "ill not available after %d sleeps.",
                  100);
              goto LABEL_37;
            }
          }
          if ( v32 )
          {
            if ( v13 >= 0 )
              FltObjectDereference(InstanceList);
            LogWrite(
              3,
              0,
              L"VfsVolumeManager::AttachVFSVolume() - Collision occurred while attaching to the volume, instance is now av"
               "ailable after %d sleeps.",
              v10);
          }
          else
          {
            v15 = *(_DWORD *)*a2 >> 1;
            if ( v15 > 0xFFFF )
              v16 = -1;
            else
              v16 = *(_DWORD *)*a2 >> 1;
            v17 = 0;
            if ( v15 <= 0xFFFF )
              v17 = v16;
            if ( v17 )
              v18 = *(_QWORD *)(*a2 + 8);
            else
              v18 = 0;
            LODWORD(NumberInstancesReturned) = v14;
            LogWrite(
              2,
              0,
              L"VfsVolumeManager::AttachVFSVolume() - Failed to retrieve instance after a collision attaching filter drive"
               "r to volume. Volume: %s. Error: %d",
              v18,
              NumberInstancesReturned);
          }
        }
      }
LABEL_37:
      if ( v7 )
        ZwClose(v7);
    }
    else if ( v5 < 0 )
    {
      v25 = *(_DWORD *)*a2 >> 1;
      if ( v25 > 0xFFFF )
        v26 = -1;
      else
        v26 = *(_DWORD *)*a2 >> 1;
      v27 = 0;
      if ( v25 <= 0xFFFF )
        v27 = v26;
      if ( v27 )
        v28 = *(_QWORD *)(*a2 + 8);
      else
        v28 = 0;
      LogWrite(
        2,
        0,
        L"VfsVolumeManager::AttachVFSVolume() - Failed to attach filter driver to volume. Volume: %s. Error: %d",
        v28,
        v5);
      return v5;
    }
    v23 = *(_DWORD *)*a2 >> 1;
    if ( v23 > 0xFFFF )
      v24 = -1;
    else
      v24 = *(_DWORD *)*a2 >> 1;
    v29 = 0;
    if ( v23 <= 0xFFFF )
      v29 = v24;
    if ( v29 )
      v30 = *(_QWORD *)(*a2 + 8);
    else
      v30 = 0;
    LogWrite(
      3,
      0,
      L"VfsVolumeManager::AttachVFSVolume() - Successfully attached filter driver to volume. Volume: %s.",
      v30);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180006eec  mov     [rsp-38h+arg_8], rbx
0x180006ef1  push    rbp
0x180006ef2  push    rsi
0x180006ef3  push    rdi
0x180006ef4  push    r12
0x180006ef6  push    r13
0x180006ef8  push    r14
0x180006efa  push    r15
0x180006efc  mov     rbp, rsp
0x180006eff  sub     rsp, 30h
0x180006f03  lea     r15, [rcx+18h]
0x180006f07  xor     r13d, r13d
0x180006f0a  mov     rsi, rdx
0x180006f0d  cmp     [r15], r13
0x180006f10  jnz     short loc_180006F2D
0x180006f12  add     rcx, 30h ; '0'; FilterName
0x180006f16  mov     rdx, r15; RetFilter
0x180006f19  call    cs:__imp_FltGetFilterFromName
0x180006f20  nop     dword ptr [rax+rax+00h]
0x180006f25  test    eax, eax
0x180006f27  js      loc_180007183
0x180006f2d  mov     rdx, [rsi]
0x180006f30  xor     r9d, r9d; RetInstance
0x180006f33  mov     rcx, [r15]; Filter
0x180006f36  xor     r8d, r8d; InstanceName
0x180006f39  mov     rdx, [rdx+20h]; Volume
0x180006f3d  call    cs:__imp_FltAttachVolume
0x180006f44  nop     dword ptr [rax+rax+00h]
0x180006f49  mov     ebx, eax
0x180006f4b  mov     edi, 0FFFFh
0x180006f50  cmp     eax, 0C01C0012h
0x180006f55  jnz     loc_180007113
0x180006f5b  lea     r8, [rbp+InstanceList]
0x180006f5f  mov     [rbp+arg_0], r13d
0x180006f63  lea     rdx, aRegistryMachin_2; "\\Registry\\Machine\\Software\\Microsof"...
0x180006f6a  mov     [rbp+InstanceList], r13
0x180006f6e  xor     ecx, ecx
0x180006f70  call    ?open_key@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXPEB_WAEAVhandle@kernel@shared@appv@@K@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::open_key(void *,wchar_t const *,appv::shared::kernel::handle &,ulong)
0x180006f75  mov     rbx, [rbp+InstanceList]
0x180006f79  mov     edx, eax
0x180006f7b  test    eax, eax
0x180006f7d  js      loc_1800070AE
0x180006f83  lea     r8, [rbp+arg_0]
0x180006f87  mov     rcx, rbx
0x180006f8a  lea     rdx, aMaxattachwaitt; "MaxAttachWaitTimeInMilliseconds"
0x180006f91  call    ?get_value@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXPEB_WAEAK@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::get_value(void *,wchar_t const *,ulong &)
0x180006f96  mov     edx, eax
0x180006f98  test    eax, eax
0x180006f9a  js      loc_1800070AE
0x180006fa0  mov     r14d, [rbp+arg_0]
0x180006fa4  test    r14d, r14d
0x180006fa7  jz      loc_1800070EE
0x180006fad  mov     eax, 2710h
0x180006fb2  mov     r12d, r13d
0x180006fb5  cmp     r14d, eax
0x180006fb8  cmova   r14d, eax
0x180006fbc  mov     rcx, [rsi]
0x180006fbf  lea     rax, [rbp+arg_0]
0x180006fc3  mov     rdx, [r15]; Filter
0x180006fc6  lea     r8, [rbp+InstanceList]; InstanceList
0x180006fca  mov     [rbp+arg_0], r13d
0x180006fce  mov     r9d, 1; InstanceListSize
0x180006fd4  mov     [rbp+InstanceList], r13
0x180006fd8  mov     rcx, [rcx+20h]; Volume
0x180006fdc  mov     [rsp+30h+NumberInstancesReturned], rax; NumberInstancesReturned
0x180006fe1  call    cs:__imp_FltEnumerateInstances
0x180006fe8  nop     dword ptr [rax+rax+00h]
0x180006fed  mov     ecx, [rbp+arg_0]
0x180006ff0  mov     r8d, eax
0x180006ff3  test    eax, eax
0x180006ff5  js      short loc_180007055
0x180006ff7  test    ecx, ecx
0x180006ff9  jnz     short loc_180007055
0x180006ffb  imul    ecx, r14d, 0FFFFD8F0h
0x180007002  lea     r8, [rbp+Interval]; Interval
0x180007006  mov     eax, 51EB851Fh
0x18000700b  imul    ecx
0x18000700d  xor     ecx, ecx; WaitMode
0x18000700f  sar     edx, 5
0x180007012  mov     eax, edx
0x180007014  shr     eax, 1Fh
0x180007017  add     eax, edx
0x180007019  xor     edx, edx; Alertable
0x18000701b  cdqe
0x18000701d  mov     qword ptr [rbp+Interval], rax
0x180007021  call    cs:__imp_KeDelayExecutionThread
0x180007028  nop     dword ptr [rax+rax+00h]
0x18000702d  inc     r12d
0x180007030  cmp     r12d, 64h ; 'd'
0x180007034  jl      short loc_180006FBC
0x180007036  jnz     loc_1800070EE
0x18000703c  lea     r8, aVfsvolumemanag_2; "VfsVolumeManager::AttachVFSVolume() - C"...
0x180007043  xor     edx, edx
0x180007045  mov     r9d, r12d
0x180007048  lea     ecx, [rdx+3]
0x18000704b  call    LogWrite
0x180007050  jmp     loc_1800070EE
0x180007055  cmp     ecx, 1
0x180007058  jb      short loc_180007078
0x18000705a  test    r8d, r8d
0x18000705d  js      short loc_18000706F
0x18000705f  mov     rcx, [rbp+InstanceList]; FltObject
0x180007063  call    cs:__imp_FltObjectDereference
0x18000706a  nop     dword ptr [rax+rax+00h]
0x18000706f  lea     r8, aVfsvolumemanag_7; "VfsVolumeManager::AttachVFSVolume() - C"...
0x180007076  jmp     short loc_180007043
0x180007078  mov     r9, [rsi]
0x18000707b  mov     ecx, [r9]
0x18000707e  shr     ecx, 1
0x180007080  cmp     ecx, edi
0x180007082  ja      short loc_180007089
0x180007084  movzx   edx, cx
0x180007087  jmp     short loc_18000708B
0x180007089  mov     edx, edi
0x18000708b  mov     eax, r13d
0x18000708e  cmovbe  ax, dx
0x180007092  test    ax, ax
0x180007095  jnz     short loc_18000709C
0x180007097  mov     r9, r13
0x18000709a  jmp     short loc_1800070A0
0x18000709c  mov     r9, [r9+8]
0x1800070a0  mov     dword ptr [rsp+30h+NumberInstancesReturned], r8d
0x1800070a5  lea     r8, aVfsvolumemanag_8; "VfsVolumeManager::AttachVFSVolume() - F"...
0x1800070ac  jmp     short loc_1800070E4
0x1800070ae  mov     r9, [rsi]
0x1800070b1  mov     ecx, [r9]
0x1800070b4  shr     ecx, 1
0x1800070b6  cmp     ecx, edi
0x1800070b8  ja      short loc_1800070C0
0x1800070ba  movzx   r8d, cx
0x1800070be  jmp     short loc_1800070C3
0x1800070c0  mov     r8d, edi
0x1800070c3  mov     eax, r13d
0x1800070c6  cmovbe  ax, r8w
0x1800070cb  test    ax, ax
0x1800070ce  jnz     short loc_1800070D5
0x1800070d0  mov     r9, r13
0x1800070d3  jmp     short loc_1800070D9
0x1800070d5  mov     r9, [r9+8]
0x1800070d9  mov     dword ptr [rsp+30h+NumberInstancesReturned], edx
0x1800070dd  lea     r8, aVfsvolumemanag_3; "VfsVolumeManager::AttachVFSVolume() - F"...
0x1800070e4  xor     edx, edx
0x1800070e6  lea     ecx, [rdx+2]
0x1800070e9  call    LogWrite
0x1800070ee  test    rbx, rbx
0x1800070f1  jz      short loc_180007102
0x1800070f3  mov     rcx, rbx; Handle
0x1800070f6  call    cs:__imp_ZwClose
0x1800070fd  nop     dword ptr [rax+rax+00h]
0x180007102  mov     r9, [rsi]
0x180007105  mov     ecx, [r9]
0x180007108  shr     ecx, 1
0x18000710a  cmp     ecx, edi
0x18000710c  ja      short loc_180007156
0x18000710e  movzx   edx, cx
0x180007111  jmp     short loc_180007158
0x180007113  test    ebx, ebx
0x180007115  jns     short loc_180007102
0x180007117  mov     r9, [rsi]
0x18000711a  mov     ecx, [r9]
0x18000711d  shr     ecx, 1
0x18000711f  cmp     ecx, edi
0x180007121  ja      short loc_180007128
0x180007123  movzx   edx, cx
0x180007126  jmp     short loc_18000712A
0x180007128  mov     edx, edi
0x18000712a  mov     eax, r13d
0x18000712d  cmovbe  ax, dx
0x180007131  test    ax, ax
0x180007134  jnz     short loc_18000713B
0x180007136  mov     r9, r13
0x180007139  jmp     short loc_18000713F
0x18000713b  mov     r9, [r9+8]
0x18000713f  xor     edx, edx
0x180007141  mov     dword ptr [rsp+30h+NumberInstancesReturned], ebx
0x180007145  lea     r8, aVfsvolumemanag_5; "VfsVolumeManager::AttachVFSVolume() - F"...
0x18000714c  lea     ecx, [rdx+2]
0x18000714f  call    LogWrite
0x180007154  jmp     short loc_180007181
0x180007156  mov     edx, edi
0x180007158  mov     eax, r13d
0x18000715b  cmovbe  ax, dx
0x18000715f  test    ax, ax
0x180007162  jnz     short loc_180007169
0x180007164  mov     r9, r13
0x180007167  jmp     short loc_18000716D
0x180007169  mov     r9, [r9+8]
0x18000716d  xor     edx, edx
0x18000716f  lea     r8, aVfsvolumemanag; "VfsVolumeManager::AttachVFSVolume() - S"...
0x180007176  lea     ecx, [rdx+3]
0x180007179  call    LogWrite
0x18000717e  mov     ebx, r13d
0x180007181  mov     eax, ebx
0x180007183  mov     rbx, [rsp+30h+arg_8]
0x180007188  add     rsp, 30h
0x18000718c  pop     r15
0x18000718e  pop     r14
0x180007190  pop     r13
0x180007192  pop     r12
0x180007194  pop     rdi
0x180007195  pop     rsi
0x180007196  pop     rbp
0x180007197  retn
```
