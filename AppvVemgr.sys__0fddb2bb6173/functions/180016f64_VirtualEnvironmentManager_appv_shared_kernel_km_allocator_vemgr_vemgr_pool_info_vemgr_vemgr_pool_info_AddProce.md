# VirtualEnvironmentManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::AddProcess(ulong,ulong,_UNICODE_STRING const *,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &)

- ea: `0x180016f64`
- end: `0x18001732d`
- name: `?AddProcess@?$VirtualEnvironmentManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@QEAAJKKPEBU_UNICODE_STRING@@AEBV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@Z`
- size: `969`
- prototype: `__int64 __fastcall(__int64, unsigned int, int, int, __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180018ea0`

## callees

- `0x180005ec4`
- `0x18000a9e4`
- `0x18000ce10`
- `0x18000e23c`
- `0x18000fbf4`
- `0x18000fd5c`
- `0x180016f64`
- `0x180018484`
- `0x18001931c`
- `0x18001b3cc`
- `0x18001bb30`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1800170ff`
- `ntoskrnl!ExFreePoolWithTag` at `0x180017154`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800172c9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800170ff`
- `ntoskrnl!ExFreePoolWithTag` at `0x180017154`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800172c9`
- `ntoskrnl!ZwClose` at `0x180017063`
- `ntoskrnl!ZwClose` at `0x1800171f9`
- `ntoskrnl!ZwClose` at `0x180017063`
- `ntoskrnl!ZwClose` at `0x1800171f9`
- `ntoskrnl!RtlInitUnicodeString` at `0x180016fa5`
- `ntoskrnl!RtlInitUnicodeString` at `0x180017086`
- `ntoskrnl!RtlInitUnicodeString` at `0x180016fa5`
- `ntoskrnl!RtlInitUnicodeString` at `0x180017086`

## string_xrefs

- `0x180017023`: `\Registry\Machine\Software\Microsoft\AppV\Client`
- `0x1800171b9`: `\Registry\Machine\Software\Microsoft\AppV\Client`

## pseudocode

```c
__int64 __fastcall VirtualEnvironmentManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::AddProcess(
        __int64 a1,
        unsigned int a2,
        int a3,
        int a4,
        __int64 a5)
{
  int ShouldInjectJITVLoader; // r14d
  bool v10; // r14
  int v11; // eax
  HANDLE v12; // rbx
  int v13; // ecx
  int v14; // eax
  PVOID v15; // r9
  volatile signed __int32 *v16; // rdi
  bool v18; // r14
  int v19; // eax
  __int64 v20; // rcx
  __int64 v21; // r8
  HANDLE v22; // rbx
  __int64 v23; // rcx
  __int64 v24; // r8
  PVOID v25; // r8
  unsigned int v26; // eax
  __int64 v27; // r9
  volatile signed __int32 *v28; // rdi
  __int64 v29; // [rsp+20h] [rbp-81h]
  __int64 v30; // [rsp+20h] [rbp-81h]
  __int64 v31; // [rsp+28h] [rbp-79h]
  __int64 v32; // [rsp+30h] [rbp-71h]
  char v33[8]; // [rsp+50h] [rbp-51h] BYREF
  HANDLE Handle; // [rsp+58h] [rbp-49h] BYREF
  __int128 v35; // [rsp+60h] [rbp-41h] BYREF
  __int64 v36; // [rsp+70h] [rbp-31h] BYREF
  PVOID v37; // [rsp+78h] [rbp-29h]
  struct _UNICODE_STRING DestinationString; // [rsp+80h] [rbp-21h] BYREF
  __int64 v39; // [rsp+90h] [rbp-11h] BYREF
  PVOID P; // [rsp+98h] [rbp-9h]
  struct _UNICODE_STRING v41; // [rsp+A0h] [rbp-1h] BYREF

  v33[0] = 0;
  v36 = 0;
  v37 = 0;
  v35 = 0;
  RtlInitUnicodeString(&DestinationString, 0);
  if ( (unsigned __int8)VirtualEnvironmentManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::IsProcessVirtual(
                          a1,
                          a2,
                          a3,
                          a4,
                          a5,
                          (__int64)&v35,
                          (__int64)&v36,
                          (__int64)v33) )
  {
    Handle = 0;
    v18 = 1;
    v19 = registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::open_key(
            0,
            L"\\Registry\\Machine\\Software\\Microsoft\\AppV\\Client",
            &Handle);
    v22 = Handle;
    if ( v19 >= 0 )
    {
      LODWORD(Handle) = 1;
      if ( (int)registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::get_value(
                  v22,
                  L"Enabled",
                  &Handle) >= 0 )
        v18 = (_DWORD)Handle == 1;
    }
    if ( v22 )
      ZwClose(v22);
    if ( v18 )
    {
      if ( (Microsoft_AppV_SharedPerformanceEnableBits & 1) != 0 )
        McTemplateK0q_EtwWriteTransfer(v20, VEMGR_Virtual_Process_Launch_Start, v21, a2);
      ShouldInjectJITVLoader = VirtualEnvironmentManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::AddProcessToVE(
                                 a1,
                                 a2,
                                 a3,
                                 (unsigned int)&v35,
                                 (__int64)&v36,
                                 v33[0],
                                 0);
      if ( (Microsoft_AppV_SharedPerformanceEnableBits & 1) != 0 )
        McTemplateK0q_EtwWriteTransfer(v23, VEMGR_Virtual_Process_Launch_Finish, v24, a2);
    }
    else
    {
      if ( (unsigned int)v36 >> 1 > 0xFFFF || (v25 = v37, !(unsigned __int16)((unsigned int)v36 >> 1)) )
        v25 = 0;
      v26 = *(_DWORD *)v35 >> 1;
      if ( v26 <= 0xFFFF && (_WORD)v26 )
        v27 = *(_QWORD *)(v35 + 8);
      else
        v27 = 0;
      LODWORD(v32) = a3;
      LODWORD(v31) = a2;
      LogWrite(
        3,
        0,
        L"VirtualEnvironmentManager::AddProcess() - Skipping AddProcessToVE due to AppV Client being disabled. Package %s,"
         " user %s, pid %d, parent pid %d",
        v27,
        v25,
        v31,
        v32);
      ShouldInjectJITVLoader = -1073741772;
    }
    goto LABEL_45;
  }
  v33[0] = 0;
  ShouldInjectJITVLoader = VirtualEnvironmentManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::ShouldInjectJITVLoader(
                             a1,
                             a5,
                             v33);
  if ( ShouldInjectJITVLoader < 0 )
  {
LABEL_45:
    if ( v37 )
      ExFreePoolWithTag(v37, 0);
    v28 = (volatile signed __int32 *)*((_QWORD *)&v35 + 1);
    if ( *((_QWORD *)&v35 + 1)
      && _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v35 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v28 + 8LL))(v28);
      if ( _InterlockedExchangeAdd(v28 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v28 + 16LL))(v28);
    }
    return (unsigned int)ShouldInjectJITVLoader;
  }
  if ( v33[0] )
  {
    Handle = 0;
    v10 = 1;
    v11 = registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::open_key(
            0,
            L"\\Registry\\Machine\\Software\\Microsoft\\AppV\\Client",
            &Handle);
    v12 = Handle;
    if ( v11 >= 0 )
    {
      LODWORD(Handle) = 1;
      if ( (int)registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::get_value(
                  v12,
                  L"Enabled",
                  &Handle) >= 0 )
        v10 = (_DWORD)Handle == 1;
    }
    if ( v12 )
      ZwClose(v12);
    if ( v10 )
    {
      v39 = 0;
      P = 0;
      RtlInitUnicodeString(&v41, 0);
      appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::assign(
        &v39,
        &dword_18001E3EC,
        0);
      v14 = synchrozined_vemgr_notifications<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::synchronous_vemgr_notification_on_same_thread(
              v13,
              512,
              a2,
              a3,
              (__int64)&v39,
              (__int64)&v36,
              0,
              0,
              0);
      ShouldInjectJITVLoader = v14;
      if ( v14 < 0 )
      {
        LODWORD(v30) = v14;
        LogWrite(
          1,
          0,
          L"VirtualEnvironmentManager::InjectJITVLoaderUpcall() - JITV loader injection notification failed. Process: %d. Error: %d",
          a2,
          v30);
      }
      if ( P )
        ExFreePoolWithTag(P, 0);
      if ( ShouldInjectJITVLoader < 0 )
        goto LABEL_45;
    }
    else
    {
      if ( (unsigned int)v36 >> 1 > 0xFFFF || (v15 = v37, !(unsigned __int16)((unsigned int)v36 >> 1)) )
        v15 = 0;
      LODWORD(v31) = a3;
      LODWORD(v29) = a2;
      LogWrite(
        3,
        0,
        L"VirtualEnvironmentManager::AddProcess() - Skipping InjectJITVLoaderUpcall due to AppV Client being disabled. Use"
         "r %s, pid %d, parent pid %d",
        v15,
        v29,
        v31);
    }
  }
  if ( v37 )
    ExFreePoolWithTag(v37, 0);
  v16 = (volatile signed __int32 *)*((_QWORD *)&v35 + 1);
  if ( *((_QWORD *)&v35 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v35 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v16 + 8LL))(v16);
      if ( _InterlockedExchangeAdd(v16 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v16 + 16LL))(v16);
    }
  }
  return 3221225524LL;
}

```

## disassembly

```asm
0x180016f64  push    rbp
0x180016f66  push    rbx
0x180016f67  push    rsi
0x180016f68  push    rdi
0x180016f69  push    r12
0x180016f6b  push    r13
0x180016f6d  push    r14
0x180016f6f  push    r15
0x180016f71  lea     rbp, [rsp-17h]
0x180016f76  sub     rsp, 0B8h
0x180016f7d  xor     r13d, r13d
0x180016f80  mov     esi, edx
0x180016f82  mov     r12, rcx
0x180016f85  mov     [rbp+4Fh+var_A0], r13b
0x180016f89  xorps   xmm0, xmm0
0x180016f8c  mov     [rbp+4Fh+var_80], r13
0x180016f90  xor     edx, edx; SourceString
0x180016f92  mov     [rbp+4Fh+var_78], r13
0x180016f96  lea     rcx, [rbp+4Fh+DestinationString]; DestinationString
0x180016f9a  mov     rbx, r9
0x180016f9d  movdqu  [rbp+4Fh+var_90], xmm0
0x180016fa2  mov     r15d, r8d
0x180016fa5  call    cs:__imp_RtlInitUnicodeString
0x180016fac  nop     dword ptr [rax+rax+00h]
0x180016fb1  mov     rdi, [rbp+4Fh+arg_20]
0x180016fb5  lea     rax, [rbp+4Fh+var_A0]
0x180016fb9  mov     [rsp+0F0h+var_B8], rax
0x180016fbe  mov     r9, rbx
0x180016fc1  lea     rax, [rbp+4Fh+var_80]
0x180016fc5  mov     r8d, r15d
0x180016fc8  mov     [rsp+0F0h+var_C0], rax
0x180016fcd  mov     edx, esi
0x180016fcf  lea     rax, [rbp+4Fh+var_90]
0x180016fd3  mov     rcx, r12
0x180016fd6  mov     [rsp+0F0h+var_C8], rax
0x180016fdb  mov     [rsp+0F0h+var_D0], rdi
0x180016fe0  call    ?IsProcessVirtual@?$VirtualEnvironmentManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@AEAA_NKKPEBU_UNICODE_STRING@@AEBV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@AEAV?$shared_ptr@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@kernel_std@@AEAV3456@AEA_N@Z; VirtualEnvironmentManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::IsProcessVirtual(ulong,ulong,_UNICODE_STRING const *,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &,kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>> &,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> &,bool &)
0x180016fe5  test    al, al
0x180016fe7  jnz     loc_1800171AA
0x180016fed  lea     r8, [rbp+4Fh+var_A0]
0x180016ff1  mov     [rbp+4Fh+var_A0], r13b
0x180016ff5  mov     rdx, rdi
0x180016ff8  mov     rcx, r12
0x180016ffb  call    ?ShouldInjectJITVLoader@?$VirtualEnvironmentManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@AEAAJAEBV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@AEA_N@Z; VirtualEnvironmentManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::ShouldInjectJITVLoader(appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &,bool &)
0x180017000  mov     r14d, eax
0x180017003  test    eax, eax
0x180017005  js      loc_1800172BE
0x18001700b  cmp     [rbp+4Fh+var_A0], r13b
0x18001700f  jz      loc_180017149
0x180017015  lea     edi, [r13+1]
0x180017019  mov     [rbp+4Fh+Handle], r13
0x18001701d  lea     r8, [rbp+4Fh+Handle]
0x180017021  xor     ecx, ecx
0x180017023  lea     rdx, aRegistryMachin_5; "\\Registry\\Machine\\Software\\Microsof"...
0x18001702a  mov     r14b, dil
0x18001702d  call    ?open_key@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXPEB_WAEAVhandle@kernel@shared@appv@@K@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::open_key(void *,wchar_t const *,appv::shared::kernel::handle &,ulong)
0x180017032  mov     rbx, [rbp+4Fh+Handle]
0x180017036  test    eax, eax
0x180017038  js      short loc_18001705B
0x18001703a  lea     r8, [rbp+4Fh+Handle]
0x18001703e  mov     dword ptr [rbp+4Fh+Handle], edi
0x180017041  lea     rdx, aEnabled; "Enabled"
0x180017048  mov     rcx, rbx
0x18001704b  call    ?get_value@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXPEB_WAEAK@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::get_value(void *,wchar_t const *,ulong &)
0x180017050  test    eax, eax
0x180017052  js      short loc_18001705B
0x180017054  cmp     dword ptr [rbp+4Fh+Handle], edi
0x180017057  setz    r14b
0x18001705b  test    rbx, rbx
0x18001705e  jz      short loc_18001706F
0x180017060  mov     rcx, rbx; Handle
0x180017063  call    cs:__imp_ZwClose
0x18001706a  nop     dword ptr [rax+rax+00h]
0x18001706f  test    r14b, r14b
0x180017072  jz      loc_180017115
0x180017078  xor     edx, edx; SourceString
0x18001707a  mov     [rbp+4Fh+var_60], r13
0x18001707e  lea     rcx, [rbp+4Fh+var_50]; DestinationString
0x180017082  mov     [rbp+4Fh+P], r13
0x180017086  call    cs:__imp_RtlInitUnicodeString
0x18001708d  nop     dword ptr [rax+rax+00h]
0x180017092  xor     r8d, r8d
0x180017095  lea     rdx, dword_18001E3EC
0x18001709c  lea     rcx, [rbp+4Fh+var_60]
0x1800170a0  call    ?assign@?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@AEAAJPEB_W_K@Z; appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::assign(wchar_t const *,unsigned __int64)
0x1800170a5  mov     [rsp+0F0h+var_B0], r13b
0x1800170aa  lea     rax, [rbp+4Fh+var_80]
0x1800170ae  mov     dword ptr [rsp+0F0h+var_B8], r13d
0x1800170b3  mov     r9d, r15d
0x1800170b6  mov     dword ptr [rsp+0F0h+var_C0], r13d
0x1800170bb  mov     r8d, esi
0x1800170be  mov     [rsp+0F0h+var_C8], rax
0x1800170c3  mov     edx, 200h
0x1800170c8  lea     rax, [rbp+4Fh+var_60]
0x1800170cc  mov     [rsp+0F0h+var_D0], rax
0x1800170d1  call    ?synchronous_vemgr_notification_on_same_thread@?$synchrozined_vemgr_notifications@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@QEAAJKKKAEBV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@0KK_N@Z; synchrozined_vemgr_notifications<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::synchronous_vemgr_notification_on_same_thread(ulong,ulong,ulong,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &,ulong,ulong,bool)
0x1800170d6  mov     r14d, eax
0x1800170d9  test    eax, eax
0x1800170db  jns     short loc_1800170F4
0x1800170dd  mov     r9d, esi
0x1800170e0  mov     dword ptr [rsp+0F0h+var_D0], eax
0x1800170e4  lea     r8, aVirtualenviron_1; "VirtualEnvironmentManager::InjectJITVLo"...
0x1800170eb  xor     edx, edx
0x1800170ed  mov     ecx, edi
0x1800170ef  call    LogWrite
0x1800170f4  mov     rcx, [rbp+4Fh+P]; P
0x1800170f8  test    rcx, rcx
0x1800170fb  jz      short loc_18001710B
0x1800170fd  xor     edx, edx; Tag
0x1800170ff  call    cs:__imp_ExFreePoolWithTag
0x180017106  nop     dword ptr [rax+rax+00h]
0x18001710b  test    r14d, r14d
0x18001710e  jns     short loc_180017149
0x180017110  jmp     loc_1800172BE
0x180017115  mov     eax, dword ptr [rbp+4Fh+var_80]
0x180017118  mov     ecx, 0FFFFh
0x18001711d  shr     eax, 1
0x18001711f  cmp     eax, ecx
0x180017121  ja      short loc_18001712C
0x180017123  mov     r9, [rbp+4Fh+var_78]
0x180017127  test    ax, ax
0x18001712a  jnz     short loc_18001712F
0x18001712c  mov     r9, r13
0x18001712f  xor     edx, edx
0x180017131  mov     dword ptr [rsp+0F0h+var_C8], r15d
0x180017136  lea     r8, aVirtualenviron_17; "VirtualEnvironmentManager::AddProcess()"...
0x18001713d  mov     dword ptr [rsp+0F0h+var_D0], esi
0x180017141  lea     ecx, [rdx+3]
0x180017144  call    LogWrite
0x180017149  mov     rcx, [rbp+4Fh+var_78]; P
0x18001714d  test    rcx, rcx
0x180017150  jz      short loc_180017160
0x180017152  xor     edx, edx; Tag
0x180017154  call    cs:__imp_ExFreePoolWithTag
0x18001715b  nop     dword ptr [rax+rax+00h]
0x180017160  mov     rdi, qword ptr [rbp+4Fh+var_90+8]
0x180017164  test    rdi, rdi
0x180017167  jz      short loc_1800171A0
0x180017169  or      ebx, 0FFFFFFFFh
0x18001716c  mov     eax, ebx
0x18001716e  lock xadd [rdi+8], eax
0x180017173  add     eax, ebx
0x180017175  jnz     short loc_1800171A0
0x180017177  mov     rax, [rdi]
0x18001717a  mov     rcx, rdi
0x18001717d  mov     rax, [rax+8]
0x180017181  call    _guard_dispatch_icall
0x180017186  mov     eax, ebx
0x180017188  lock xadd [rdi+0Ch], eax
0x18001718d  add     eax, ebx
0x18001718f  jnz     short loc_1800171A0
0x180017191  mov     rax, [rdi]
0x180017194  mov     rcx, rdi
0x180017197  mov     rax, [rax+10h]
0x18001719b  call    _guard_dispatch_icall
0x1800171a0  mov     eax, 0C0000034h
0x1800171a5  jmp     loc_180017318
0x1800171aa  mov     edi, 1
0x1800171af  mov     [rbp+4Fh+Handle], r13
0x1800171b3  lea     r8, [rbp+4Fh+Handle]
0x1800171b7  xor     ecx, ecx
0x1800171b9  lea     rdx, aRegistryMachin_5; "\\Registry\\Machine\\Software\\Microsof"...
0x1800171c0  mov     r14b, dil
0x1800171c3  call    ?open_key@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXPEB_WAEAVhandle@kernel@shared@appv@@K@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::open_key(void *,wchar_t const *,appv::shared::kernel::handle &,ulong)
0x1800171c8  mov     rbx, [rbp+4Fh+Handle]
0x1800171cc  test    eax, eax
0x1800171ce  js      short loc_1800171F1
0x1800171d0  lea     r8, [rbp+4Fh+Handle]
0x1800171d4  mov     dword ptr [rbp+4Fh+Handle], edi
0x1800171d7  lea     rdx, aEnabled; "Enabled"
0x1800171de  mov     rcx, rbx
0x1800171e1  call    ?get_value@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXPEB_WAEAK@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::get_value(void *,wchar_t const *,ulong &)
0x1800171e6  test    eax, eax
0x1800171e8  js      short loc_1800171F1
0x1800171ea  cmp     dword ptr [rbp+4Fh+Handle], edi
0x1800171ed  setz    r14b
0x1800171f1  test    rbx, rbx
0x1800171f4  jz      short loc_180017205
0x1800171f6  mov     rcx, rbx; Handle
0x1800171f9  call    cs:__imp_ZwClose
0x180017200  nop     dword ptr [rax+rax+00h]
0x180017205  test    r14b, r14b
0x180017208  jz      short loc_180017265
0x18001720a  test    cs:Microsoft_AppV_SharedPerformanceEnableBits, dil
0x180017211  jz      short loc_180017222
0x180017213  mov     r9d, esi
0x180017216  lea     rdx, VEMGR_Virtual_Process_Launch_Start
0x18001721d  call    McTemplateK0q_EtwWriteTransfer
0x180017222  mov     al, [rbp+4Fh+var_A0]
0x180017225  lea     r9, [rbp+4Fh+var_90]
0x180017229  mov     dword ptr [rsp+0F0h+var_C0], r13d
0x18001722e  mov     r8d, r15d
0x180017231  mov     byte ptr [rsp+0F0h+var_C8], al
0x180017235  mov     edx, esi
0x180017237  lea     rax, [rbp+4Fh+var_80]
0x18001723b  mov     rcx, r12
0x18001723e  mov     [rsp+0F0h+var_D0], rax
0x180017243  call    ?AddProcessToVE@?$VirtualEnvironmentManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@AEAAJKKAEAV?$shared_ptr@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@kernel_std@@AEAV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@_NH@Z; VirtualEnvironmentManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::AddProcessToVE(ulong,ulong,kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>> &,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> &,bool,int)
0x180017248  test    cs:Microsoft_AppV_SharedPerformanceEnableBits, dil
0x18001724f  mov     r14d, eax
0x180017252  jz      short loc_1800172BE
0x180017254  mov     r9d, esi
0x180017257  lea     rdx, VEMGR_Virtual_Process_Launch_Finish
0x18001725e  call    McTemplateK0q_EtwWriteTransfer
0x180017263  jmp     short loc_1800172BE
0x180017265  mov     eax, dword ptr [rbp+4Fh+var_80]
0x180017268  mov     ecx, 0FFFFh
0x18001726d  shr     eax, 1
0x18001726f  cmp     eax, ecx
0x180017271  ja      short loc_18001727C
0x180017273  mov     r8, [rbp+4Fh+var_78]
0x180017277  test    ax, ax
0x18001727a  jnz     short loc_18001727F
0x18001727c  mov     r8, r13
0x18001727f  mov     rdx, qword ptr [rbp+4Fh+var_90]
0x180017283  mov     eax, [rdx]
0x180017285  shr     eax, 1
0x180017287  cmp     eax, ecx
0x180017289  ja      short loc_180017296
0x18001728b  test    ax, ax
0x18001728e  jz      short loc_180017296
0x180017290  mov     r9, [rdx+8]
0x180017294  jmp     short loc_180017299
0x180017296  mov     r9, r13
0x180017299  xor     edx, edx
0x18001729b  mov     dword ptr [rsp+0F0h+var_C0], r15d
0x1800172a0  mov     dword ptr [rsp+0F0h+var_C8], esi
0x1800172a4  mov     [rsp+0F0h+var_D0], r8
0x1800172a9  lea     r8, aVirtualenviron_14; "VirtualEnvironmentManager::AddProcess()"...
0x1800172b0  lea     ecx, [rdx+3]
0x1800172b3  call    LogWrite
0x1800172b8  mov     r14d, 0C0000034h
0x1800172be  mov     rcx, [rbp+4Fh+var_78]; P
0x1800172c2  test    rcx, rcx
0x1800172c5  jz      short loc_1800172D5
0x1800172c7  xor     edx, edx; Tag
0x1800172c9  call    cs:__imp_ExFreePoolWithTag
0x1800172d0  nop     dword ptr [rax+rax+00h]
0x1800172d5  mov     rdi, qword ptr [rbp+4Fh+var_90+8]
0x1800172d9  test    rdi, rdi
0x1800172dc  jz      short loc_180017315
0x1800172de  or      ebx, 0FFFFFFFFh
0x1800172e1  mov     eax, ebx
0x1800172e3  lock xadd [rdi+8], eax
0x1800172e8  add     eax, ebx
0x1800172ea  jnz     short loc_180017315
0x1800172ec  mov     rax, [rdi]
0x1800172ef  mov     rcx, rdi
0x1800172f2  mov     rax, [rax+8]
0x1800172f6  call    _guard_dispatch_icall
0x1800172fb  mov     eax, ebx
0x1800172fd  lock xadd [rdi+0Ch], eax
0x180017302  add     eax, ebx
0x180017304  jnz     short loc_180017315
0x180017306  mov     rax, [rdi]
0x180017309  mov     rcx, rdi
0x18001730c  mov     rax, [rax+10h]
0x180017310  call    _guard_dispatch_icall
0x180017315  mov     eax, r14d
0x180017318  add     rsp, 0B8h
0x18001731f  pop     r15
0x180017321  pop     r14
0x180017323  pop     r13
0x180017325  pop     r12
0x180017327  pop     rdi
0x180017328  pop     rsi
0x180017329  pop     rbx
0x18001732a  pop     rbp
0x18001732b  retn
```
