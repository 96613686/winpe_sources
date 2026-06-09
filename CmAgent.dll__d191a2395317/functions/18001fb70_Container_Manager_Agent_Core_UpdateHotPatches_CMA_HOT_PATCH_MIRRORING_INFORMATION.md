# Container::Manager::Agent::Core::UpdateHotPatches(_CMA_HOT_PATCH_MIRRORING_INFORMATION &)

- ea: `0x18001fb70`
- end: `0x18001fff7`
- name: `?UpdateHotPatches@Core@Agent@Manager@Container@@YAJAEAU_CMA_HOT_PATCH_MIRRORING_INFORMATION@@@Z`
- size: `1159`
- prototype: `__int64 __fastcall(Container::Manager::Agent::Core *this, struct _CMA_HOT_PATCH_MIRRORING_INFORMATION *, __int64, __int64)`
- caller_count: `3`
- callee_count: `20`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, installer_update`

## callers

- `0x180004e30`
- `0x180005270`
- `0x1800178e0`

## callees

- `0x180002140`
- `0x180002534`
- `0x180002c48`
- `0x1800045e4`
- `0x180005934`
- `0x1800059f8`
- `0x1800063e8`
- `0x18000892c`
- `0x1800095f8`
- `0x18000a768`
- `0x18000a930`
- `0x18000af30`
- `0x18000b904`
- `0x180010c5c`
- `0x180019624`
- `0x18001c50c`
- `0x18001edfc`
- `0x18001fb70`
- `0x1800200e4`
- `0x180024d60`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18001feb1`
- `ntdll!RtlInitUnicodeString` at `0x18001feb1`
- `ntdll!NtManageHotPatch` at `0x18001fed3`
- `ntdll!NtManageHotPatch` at `0x18001fed3`
- `ntdll!RtlAcquirePrivilege` at `0x18001fdfe`
- `ntdll!RtlAcquirePrivilege` at `0x18001fdfe`

## string_xrefs

- `0x18001fba0`: `UpdateHotPatches`
- `0x18001fe18`: `onecore\base\gendrv\silos\csl\lib\CslPrivilege.h`
- `0x18001fc79`: `onecore\base\gendrv\silos\clem\agent\core\lib\core.cpp`
- `0x18001fd7b`: `onecore\base\gendrv\silos\clem\agent\core\lib\core.cpp`
- `0x18001fe34`: `onecore\base\gendrv\silos\clem\agent\core\lib\core.cpp`
- `0x18001ff77`: `onecore\base\gendrv\silos\clem\agent\core\lib\core.cpp`
- `0x18001fc13`: `Windows\System32\CatRoot\`

## pseudocode

```c
__int64 __fastcall Container::Manager::Agent::Core::UpdateHotPatches(
        Container::Manager::Agent::Core *this,
        struct _CMA_HOT_PATCH_MIRRORING_INFORMATION *a2,
        __int64 a3,
        __int64 a4)
{
  unsigned int v5; // ebx
  __int64 v6; // r9
  __int64 v7; // rdx
  int v8; // eax
  unsigned int v9; // ebx
  __int64 v10; // rcx
  __int64 v11; // rax
  __int64 v12; // rdx
  __int64 v13; // r9
  int v14; // eax
  NTSTATUS v15; // eax
  int updated; // eax
  __int64 v17; // rdx
  unsigned int v18; // r14d
  char v19; // r15
  char v20; // bl
  ULONG v21; // edx
  char *v22; // r13
  int v23; // eax
  int v24; // r12d
  int v25; // eax
  ULONG Privilege; // [rsp+20h] [rbp-E0h] BYREF
  PCWSTR SourceString[2]; // [rsp+28h] [rbp-D8h] BYREF
  _WORD v29[8]; // [rsp+38h] [rbp-C8h] BYREF
  PVOID ReturnedState; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v31[2]; // [rsp+50h] [rbp-B0h] BYREF
  int v32; // [rsp+60h] [rbp-A0h] BYREF
  PCWSTR v33[2]; // [rsp+68h] [rbp-98h] BYREF
  _WORD v34[8]; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v35[3]; // [rsp+88h] [rbp-78h] BYREF
  int v36; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v37[4]; // [rsp+A4h] [rbp-5Ch] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+A8h] [rbp-58h] BYREF
  _QWORD v39[42]; // [rsp+110h] [rbp+10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+1B8h]

  wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
    v39,
    "UpdateHotPatches",
    a3,
    a4);
  v39[0] = &CmAgentTraceProvider::UpdateHotPatches::`vftable';
  CmAgentTraceProvider::UpdateHotPatches::StartActivity((CmAgentTraceProvider::UpdateHotPatches *)v39);
  SourceString[0] = v29;
  SourceString[1] = v29;
  v29[0] = 0;
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           SourceString,
                           L"\\Device\\vmsmb\\VSMB-{dcc079ae-60ba-4d07-847c-3493609c0870}\\os\\",
                           61) )
  {
    v5 = -2147024882;
    v6 = 2147942414LL;
    v7 = 846;
LABEL_9:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\agent\\core\\lib\\core.cpp",
      (const char *)v6,
      Privilege);
    goto LABEL_10;
  }
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                           SourceString,
                           L"Windows\\System32\\CatRoot\\",
                           25) )
  {
    v5 = -2147024882;
    v6 = 2147942414LL;
    v7 = 847;
    goto LABEL_9;
  }
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                           SourceString,
                           L"{F750E6C3-38EE-11d1-85E5-00C04FC295EE}",
                           38) )
  {
    v5 = -2147024882;
    v6 = 2147942414LL;
    v7 = 848;
    goto LABEL_9;
  }
  v8 = Container::Manager::Agent::Core::_anonymous_namespace_::PurgeRdrCache(SourceString[0]);
  v5 = v8;
  if ( v8 < 0 )
  {
    v6 = (unsigned int)v8;
    v7 = 850;
    goto LABEL_9;
  }
  v9 = 0;
  if ( *((_DWORD *)this + 2) )
  {
    while ( 1 )
    {
      v31[0] = L"\\Systemroot\\WinSxS";
      v31[1] = 18;
      v10 = *((_QWORD *)this + 3 * v9 + 3);
      v35[0] = v10;
      v11 = -1;
      do
        ++v11;
      while ( *(_WORD *)(v10 + 2 * v11) );
      v35[1] = v11;
      if ( (unsigned __int8)Csl::StringStartsWith(v35, v31) )
        break;
      if ( ++v9 >= *((_DWORD *)this + 2) )
        goto LABEL_29;
    }
    v33[0] = v34;
    v33[1] = v34;
    v34[0] = 0;
    if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                             v33,
                             L"\\Device\\vmsmb\\VSMB-{dcc079ae-60ba-4d07-847c-3493609c0870}\\os\\",
                             61) )
    {
      v12 = 866;
LABEL_22:
      v5 = -2147024882;
      v13 = 2147942414LL;
      goto LABEL_23;
    }
    if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                             v33,
                             L"Windows\\WinSxS",
                             14) )
    {
      v12 = 867;
      goto LABEL_22;
    }
    v14 = Container::Manager::Agent::Core::_anonymous_namespace_::PurgeRdrCache(v33[0]);
    v5 = v14;
    if ( v14 < 0 )
    {
      v13 = (unsigned int)v14;
      v12 = 869;
LABEL_23:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v12,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\agent\\core\\lib\\core.cpp",
        (const char *)v13,
        Privilege);
      if ( v33[0] != v34 )
        operator delete((void *)v33[0], (const struct std::nothrow_t *)&std::nothrow);
      goto LABEL_10;
    }
    if ( v33[0] != v34 )
      operator delete((void *)v33[0], (const struct std::nothrow_t *)&std::nothrow);
  }
LABEL_29:
  ReturnedState = 0;
  Privilege = 10;
  v15 = RtlAcquirePrivilege(&Privilege, 1u, 0, &ReturnedState);
  if ( v15 < 0 )
  {
    updated = wil::details::in1diag3::Return_NtStatus(
                retaddr,
                (void *)0x52,
                (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\CslPrivilege.h",
                (const char *)(unsigned int)v15,
                Privilege);
    v5 = updated;
    if ( updated < 0 )
    {
      v17 = 877;
LABEL_32:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v17,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\agent\\core\\lib\\core.cpp",
        (const char *)(unsigned int)updated,
        Privilege);
      Csl::AcquiredPrivileges::~AcquiredPrivileges((Csl::AcquiredPrivileges *)&ReturnedState);
LABEL_10:
      if ( SourceString[0] != v29 )
        operator delete((void *)SourceString[0], (const struct std::nothrow_t *)&std::nothrow);
      goto LABEL_53;
    }
  }
  v31[0] = 0;
  v18 = 0;
  v19 = 0;
  if ( *((_DWORD *)this + 2) )
  {
    v20 = 0;
    v21 = 0;
    Privilege = 0;
    do
    {
      v22 = (char *)this + 24 * v18;
      if ( v20 && v21 != *((_DWORD *)v22 + 8) )
        break;
      memset_0(v37, 0, 0x64u);
      v36 = 2;
      RtlInitUnicodeString(&DestinationString, *((PCWSTR *)v22 + 3));
      v32 = 0;
      v23 = NtManageHotPatch(0, &v36, 104, &v32);
      v24 = v23;
      LODWORD(v31[0]) = v23;
      if ( v23 == -1073740758 )
      {
        v24 = 0;
      }
      else if ( v23 < 0 )
      {
        if ( !v20 )
        {
          Privilege = *((_DWORD *)v22 + 8);
          v19 = 1;
          v20 = 1;
        }
        CmAgentTraceProvider::HotPatchLoadFailed<long &,unsigned short * &,unsigned long &,unsigned long &>(
          v31,
          v22 + 24,
          v22 + 16,
          v22 + 20);
      }
      *((_DWORD *)v22 + 9) = v24;
      ++v18;
      v21 = Privilege;
    }
    while ( v18 < *((_DWORD *)this + 2) );
  }
  if ( v19 )
  {
    v25 = Container::Manager::Agent::Core::_anonymous_namespace_::StopBootTraceIfNeeded();
    if ( v25 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x3B7,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\agent\\core\\lib\\core.cpp",
        (const char *)(unsigned int)v25,
        Privilege);
  }
  else if ( *(_QWORD *)this )
  {
    updated = Container::Manager::Agent::Core::_anonymous_namespace_::UpdateUbrRegistryValue(**(_DWORD **)this);
    v5 = updated;
    if ( updated < 0 )
    {
      v17 = 945;
      goto LABEL_32;
    }
  }
  wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(
    v39,
    0);
  Csl::AcquiredPrivileges::~AcquiredPrivileges((Csl::AcquiredPrivileges *)&ReturnedState);
  if ( SourceString[0] != v29 )
    operator delete((void *)SourceString[0], (const struct std::nothrow_t *)&std::nothrow);
  v5 = 0;
LABEL_53:
  v39[0] = &CmAgentTraceProvider::UpdateHotPatches::`vftable';
  wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v39);
  wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v39);
  return v5;
}

```

## disassembly

```asm
0x18001fb70  push    rbp
0x18001fb72  push    rbx
0x18001fb73  push    rsi
0x18001fb74  push    rdi
0x18001fb75  push    r12
0x18001fb77  push    r13
0x18001fb79  push    r14
0x18001fb7b  push    r15
0x18001fb7d  lea     rbp, [rsp-178h]
0x18001fb85  sub     rsp, 278h
0x18001fb8c  mov     rax, cs:__security_cookie
0x18001fb93  xor     rax, rsp
0x18001fb96  mov     [rbp+1B0h+var_50], rax
0x18001fb9d  mov     rdi, rcx
0x18001fba0  lea     rdx, aUpdatehotpatch; "UpdateHotPatches"
0x18001fba7  lea     rcx, [rbp+1B0h+var_1A0]
0x18001fbab  call    ??0?$ActivityBase@VCmAgentTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18001fbb0  lea     r13, ??_7UpdateHotPatches@CmAgentTraceProvider@@6B@; const CmAgentTraceProvider::UpdateHotPatches::`vftable'
0x18001fbb7  mov     [rbp+1B0h+var_1A0], r13
0x18001fbbb  lea     rcx, [rbp+1B0h+var_1A0]; this
0x18001fbbf  call    ?StartActivity@UpdateHotPatches@CmAgentTraceProvider@@QEAAXXZ; CmAgentTraceProvider::UpdateHotPatches::StartActivity(void)
0x18001fbc4  lea     rax, [rsp+2B0h+var_278]
0x18001fbc9  mov     [rsp+2B0h+SourceString], rax
0x18001fbce  lea     rax, [rsp+2B0h+var_278]
0x18001fbd3  mov     [rsp+2B0h+var_280], rax
0x18001fbd8  xor     r12d, r12d
0x18001fbdb  mov     [rsp+2B0h+var_278], r12w
0x18001fbe1  lea     esi, [r12+3Dh]
0x18001fbe6  mov     r8d, esi
0x18001fbe9  lea     rdx, aDeviceVmsmbVsm; "\\Device\\vmsmb\\VSMB-{dcc079ae-60ba-4d"...
0x18001fbf0  lea     rcx, [rsp+2B0h+SourceString]
0x18001fbf5  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x18001fbfa  test    al, al
0x18001fbfc  jnz     short loc_18001FC0D
0x18001fbfe  mov     ebx, 8007000Eh
0x18001fc03  mov     r9d, ebx
0x18001fc06  mov     edx, 34Eh
0x18001fc0b  jmp     short loc_18001FC79
0x18001fc0d  mov     r8d, 19h
0x18001fc13  lea     rdx, aWindowsSystem3; "Windows\\System32\\CatRoot\\"
0x18001fc1a  lea     rcx, [rsp+2B0h+SourceString]
0x18001fc1f  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x18001fc24  test    al, al
0x18001fc26  jnz     short loc_18001FC37
0x18001fc28  mov     ebx, 8007000Eh
0x18001fc2d  mov     r9d, ebx
0x18001fc30  mov     edx, 34Fh
0x18001fc35  jmp     short loc_18001FC79
0x18001fc37  mov     r8d, 26h ; '&'
0x18001fc3d  lea     rdx, aF750e6c338ee11; "{F750E6C3-38EE-11d1-85E5-00C04FC295EE}"
0x18001fc44  lea     rcx, [rsp+2B0h+SourceString]
0x18001fc49  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x18001fc4e  test    al, al
0x18001fc50  jnz     short loc_18001FC61
0x18001fc52  mov     ebx, 8007000Eh
0x18001fc57  mov     r9d, ebx
0x18001fc5a  mov     edx, 350h
0x18001fc5f  jmp     short loc_18001FC79
0x18001fc61  mov     rcx, [rsp+2B0h+SourceString]; SourceString
0x18001fc66  call    Container__Manager__Agent__Core___anonymous_namespace___PurgeRdrCache
0x18001fc6b  mov     ebx, eax
0x18001fc6d  test    eax, eax
0x18001fc6f  jns     short loc_18001FCB0
0x18001fc71  mov     r9d, eax; char *
0x18001fc74  mov     edx, 352h; void *
0x18001fc79  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\clem\\age"...
0x18001fc80  mov     rcx, [rbp+1B8h]; this
0x18001fc87  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001fc8c  lea     rax, [rsp+2B0h+var_278]
0x18001fc91  mov     rcx, [rsp+2B0h+SourceString]; void *
0x18001fc96  cmp     rcx, rax
0x18001fc99  jz      loc_18001FFBB
0x18001fc9f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001fca6  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001fcab  jmp     loc_18001FFBB
0x18001fcb0  mov     ebx, r12d
0x18001fcb3  cmp     [rdi+8], r12d
0x18001fcb7  jbe     loc_18001FDE0
0x18001fcbd  lea     rax, aSystemrootWins; "\\Systemroot\\WinSxS"
0x18001fcc4  mov     [rsp+2B0h+var_260], rax
0x18001fcc9  mov     [rsp+2B0h+var_258], 12h
0x18001fcd2  mov     eax, ebx
0x18001fcd4  inc     rax
0x18001fcd7  lea     rax, [rax+rax*2]
0x18001fcdb  mov     rcx, [rdi+rax*8]
0x18001fcdf  mov     [rbp+1B0h+var_228], rcx
0x18001fce3  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001fce7  inc     rax
0x18001fcea  cmp     [rcx+rax*2], r12w
0x18001fcef  jnz     short loc_18001FCE7
0x18001fcf1  mov     [rbp+1B0h+var_220], rax
0x18001fcf5  lea     rdx, [rsp+2B0h+var_260]
0x18001fcfa  lea     rcx, [rbp+1B0h+var_228]
0x18001fcfe  call    ?StringStartsWith@Csl@@YA_NAEBV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@0_N@Z; Csl::StringStartsWith(utl::basic_string_view<ushort,utl::char_traits<ushort>> const &,utl::basic_string_view<ushort,utl::char_traits<ushort>> const &,bool)
0x18001fd03  test    al, al
0x18001fd05  jnz     short loc_18001FD13
0x18001fd07  inc     ebx
0x18001fd09  cmp     ebx, [rdi+8]
0x18001fd0c  jb      short loc_18001FCBD
0x18001fd0e  jmp     loc_18001FDE0
0x18001fd13  lea     rax, [rsp+2B0h+var_238]
0x18001fd18  mov     [rsp+2B0h+var_248], rax
0x18001fd1d  lea     rax, [rsp+2B0h+var_238]
0x18001fd22  mov     [rsp+2B0h+var_240], rax
0x18001fd27  mov     [rsp+2B0h+var_238], r12w
0x18001fd2d  mov     r8, rsi
0x18001fd30  lea     rdx, aDeviceVmsmbVsm; "\\Device\\vmsmb\\VSMB-{dcc079ae-60ba-4d"...
0x18001fd37  lea     rcx, [rsp+2B0h+var_248]
0x18001fd3c  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x18001fd41  test    al, al
0x18001fd43  jnz     short loc_18001FD4C
0x18001fd45  mov     edx, 362h
0x18001fd4a  jmp     short loc_18001FD6C
0x18001fd4c  mov     r8d, 0Eh
0x18001fd52  lea     rdx, aWindowsWinsxs; "Windows\\WinSxS"
0x18001fd59  lea     rcx, [rsp+2B0h+var_248]
0x18001fd5e  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x18001fd63  test    al, al
0x18001fd65  jnz     short loc_18001FDAB
0x18001fd67  mov     edx, 363h; void *
0x18001fd6c  mov     ebx, 8007000Eh
0x18001fd71  mov     r9d, ebx; char *
0x18001fd74  mov     rcx, [rbp+1B8h]; this
0x18001fd7b  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\clem\\age"...
0x18001fd82  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001fd87  lea     rax, [rsp+2B0h+var_238]
0x18001fd8c  mov     rcx, [rsp+2B0h+var_248]; void *
0x18001fd91  cmp     rcx, rax
0x18001fd94  jz      loc_18001FC8C
0x18001fd9a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001fda1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001fda6  jmp     loc_18001FC8C
0x18001fdab  mov     rcx, [rsp+2B0h+var_248]; SourceString
0x18001fdb0  call    Container__Manager__Agent__Core___anonymous_namespace___PurgeRdrCache
0x18001fdb5  mov     ebx, eax
0x18001fdb7  test    eax, eax
0x18001fdb9  jns     short loc_18001FDC5
0x18001fdbb  mov     r9d, eax
0x18001fdbe  mov     edx, 365h
0x18001fdc3  jmp     short loc_18001FD74
0x18001fdc5  lea     rax, [rsp+2B0h+var_238]
0x18001fdca  mov     rcx, [rsp+2B0h+var_248]; void *
0x18001fdcf  cmp     rcx, rax
0x18001fdd2  jz      short loc_18001FDE0
0x18001fdd4  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001fddb  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001fde0  mov     [rsp+2B0h+ReturnedState], r12
0x18001fde5  mov     [rsp+2B0h+Privilege], 0Ah; int
0x18001fded  lea     r9, [rsp+2B0h+ReturnedState]; ReturnedState
0x18001fdf2  xor     r8d, r8d; Flags
0x18001fdf5  lea     edx, [r8+1]; NumPriv
0x18001fdf9  lea     rcx, [rsp+2B0h+Privilege]; Privilege
0x18001fdfe  call    cs:__imp_RtlAcquirePrivilege
0x18001fe05  nop     dword ptr [rax+rax+00h]
0x18001fe0a  test    eax, eax
0x18001fe0c  jns     short loc_18001FE59
0x18001fe0e  mov     rcx, [rbp+1B8h]; this
0x18001fe15  mov     r9d, eax; char *
0x18001fe18  lea     r8, aOnecoreBaseGen; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x18001fe1f  mov     edx, 52h ; 'R'; void *
0x18001fe24  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18001fe29  mov     ebx, eax
0x18001fe2b  test    eax, eax
0x18001fe2d  jns     short loc_18001FE59
0x18001fe2f  mov     edx, 36Dh; void *
0x18001fe34  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\clem\\age"...
0x18001fe3b  mov     r9d, eax; char *
0x18001fe3e  mov     rcx, [rbp+1B8h]; this
0x18001fe45  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001fe4a  lea     rcx, [rsp+2B0h+ReturnedState]; this
0x18001fe4f  call    ??1AcquiredPrivileges@Csl@@QEAA@XZ; Csl::AcquiredPrivileges::~AcquiredPrivileges(void)
0x18001fe54  jmp     loc_18001FC8C
0x18001fe59  mov     [rsp+2B0h+var_260], r12
0x18001fe5e  mov     r14d, r12d
0x18001fe61  mov     r15b, byte ptr [rsp+2B0h+var_260+4]
0x18001fe66  cmp     [rdi+8], r12d
0x18001fe6a  jbe     loc_18001FF40
0x18001fe70  mov     bl, r12b
0x18001fe73  mov     edx, r12d
0x18001fe76  mov     [rsp+2B0h+Privilege], edx
0x18001fe7a  mov     eax, r14d
0x18001fe7d  lea     rcx, [rax+rax*2]
0x18001fe81  lea     r13, [rdi+rcx*8]
0x18001fe85  test    bl, bl
0x18001fe87  jz      short loc_18001FE93
0x18001fe89  cmp     edx, [r13+20h]
0x18001fe8d  jnz     loc_18001FF39
0x18001fe93  xor     edx, edx; Val
0x18001fe95  lea     r8d, [rdx+64h]; Size
0x18001fe99  lea     rcx, [rbp+1B0h+var_20C]; void *
0x18001fe9d  call    memset_0
0x18001fea2  mov     [rbp+1B0h+var_210], 2
0x18001fea9  mov     rdx, [r13+18h]; SourceString
0x18001fead  lea     rcx, [rbp+1B0h+DestinationString]; DestinationString
0x18001feb1  call    cs:__imp_RtlInitUnicodeString
0x18001feb8  nop     dword ptr [rax+rax+00h]
0x18001febd  mov     [rsp+2B0h+var_250], r12d
0x18001fec2  lea     r9, [rsp+2B0h+var_250]
0x18001fec7  mov     r8d, 68h ; 'h'
0x18001fecd  lea     rdx, [rbp+1B0h+var_210]
0x18001fed1  xor     ecx, ecx
0x18001fed3  call    cs:__imp_NtManageHotPatch
0x18001feda  nop     dword ptr [rax+rax+00h]
0x18001fedf  mov     r12d, eax
0x18001fee2  mov     dword ptr [rsp+2B0h+var_260], eax
0x18001fee6  cmp     eax, 0C000042Ah
0x18001feeb  jnz     short loc_18001FEF2
0x18001feed  xor     r12d, r12d
0x18001fef0  jmp     short loc_18001FF1E
0x18001fef2  test    eax, eax
0x18001fef4  jns     short loc_18001FF1E
0x18001fef6  test    bl, bl
0x18001fef8  jnz     short loc_18001FF08
0x18001fefa  mov     eax, [r13+20h]
0x18001fefe  mov     [rsp+2B0h+Privilege], eax; int
0x18001ff02  mov     r15b, 1
0x18001ff05  mov     bl, r15b
0x18001ff08  lea     r9, [r13+14h]
0x18001ff0c  lea     r8, [r13+10h]
0x18001ff10  lea     rdx, [r13+18h]
0x18001ff14  lea     rcx, [rsp+2B0h+var_260]
0x18001ff19  call    ??$HotPatchLoadFailed@AEAJAEAPEAGAEAKAEAK@CmAgentTraceProvider@@SAXAEAJAEAPEAGAEAK2@Z; CmAgentTraceProvider::HotPatchLoadFailed<long &,ushort * &,ulong &,ulong &>(long &,ushort * &,ulong &,ulong &)
0x18001ff1e  mov     [r13+24h], r12d
0x18001ff22  inc     r14d
0x18001ff25  cmp     r14d, [rdi+8]
0x18001ff29  mov     edx, [rsp+2B0h+Privilege]
0x18001ff2d  mov     r12d, 0
0x18001ff33  jb      loc_18001FE7A
0x18001ff39  lea     r13, ??_7UpdateHotPatches@CmAgentTraceProvider@@6B@; const CmAgentTraceProvider::UpdateHotPatches::`vftable'
0x18001ff40  test    r15b, r15b
0x18001ff43  jnz     short loc_18001FF64
0x18001ff45  mov     rcx, [rdi]
0x18001ff48  test    rcx, rcx
0x18001ff4b  jz      short loc_18001FF88
0x18001ff4d  mov     ecx, [rcx]; unsigned int
0x18001ff4f  call    Container__Manager__Agent__Core___anonymous_namespace___UpdateUbrRegistryValue
0x18001ff54  mov     ebx, eax
0x18001ff56  test    eax, eax
0x18001ff58  jns     short loc_18001FF88
0x18001ff5a  mov     edx, 3B1h
0x18001ff5f  jmp     loc_18001FE34
0x18001ff64  call    Container__Manager__Agent__Core___anonymous_namespace___StopBootTraceIfNeeded
0x18001ff69  test    eax, eax
0x18001ff6b  jns     short loc_18001FF88
0x18001ff6d  mov     rcx, [rbp+1B8h]; this
0x18001ff74  mov     r9d, eax; char *
0x18001ff77  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\clem\\age"...
0x18001ff7e  mov     edx, 3B7h; void *
0x18001ff83  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001ff88  xor     edx, edx
0x18001ff8a  lea     rcx, [rbp+1B0h+var_1A0]
0x18001ff8e  call    ?Stop@?$ActivityBase@VCmAgentTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18001ff93  lea     rcx, [rsp+2B0h+ReturnedState]; this
0x18001ff98  call    ??1AcquiredPrivileges@Csl@@QEAA@XZ; Csl::AcquiredPrivileges::~AcquiredPrivileges(void)
0x18001ff9d  lea     rax, [rsp+2B0h+var_278]
0x18001ffa2  mov     rcx, [rsp+2B0h+SourceString]; void *
0x18001ffa7  cmp     rcx, rax
0x18001ffaa  jz      short loc_18001FFB8
0x18001ffac  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001ffb3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001ffb8  mov     ebx, r12d
0x18001ffbb  mov     [rbp+1B0h+var_1A0], r13
0x18001ffbf  lea     rcx, [rbp+1B0h+var_1A0]
0x18001ffc3  call    ?Destroy@?$ActivityBase@VCmAgentTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18001ffc8  lea     rcx, [rbp+1B0h+var_1A0]
0x18001ffcc  call    ??1?$ActivityBase@VCmAgentTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x18001ffd1  mov     eax, ebx
0x18001ffd3  mov     rcx, [rbp+1B0h+var_50]
0x18001ffda  xor     rcx, rsp; StackCookie
0x18001ffdd  call    __security_check_cookie
0x18001ffe2  add     rsp, 278h
0x18001ffe9  pop     r15
0x18001ffeb  pop     r14
0x18001ffed  pop     r13
0x18001ffef  pop     r12
0x18001fff1  pop     rdi
0x18001fff2  pop     rsi
0x18001fff3  pop     rbx
0x18001fff4  pop     rbp
0x18001fff5  retn
```
