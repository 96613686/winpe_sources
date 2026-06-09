# ProcessorManager::Restore(VmRepository *)

- ea: `0x14011e450`
- end: `0x14011e9c6`
- name: `?Restore@ProcessorManager@@UEAAXPEAVVmRepository@@@Z`
- size: `1398`
- prototype: `void __fastcall(ProcessorManager *__hidden this, struct VmRepository *)`
- caller_count: `0`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140042240`
- `0x140054af0`
- `0x14005606c`
- `0x14005b628`
- `0x14006af38`
- `0x1400996b8`
- `0x1400c5a1c`
- `0x14011e450`
- `0x14011fb9c`
- `0x14011fd34`
- `0x140127970`
- `0x140132940`
- `0x1401335fc`
- `0x1401356a0`
- `0x140299950`
- `0x1402c2010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x14011e7af`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x14011e86d`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x14011e7af`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x14011e86d`
- `vid!VidSetPartitionProperty` at `0x14011e5a8`
- `vid!VidSetPartitionProperty` at `0x14011e979`
- `vid!VidSetPartitionProperty` at `0x14011e5a8`
- `vid!VidSetPartitionProperty` at `0x14011e979`
- `vid!VidGetPartitionPropertyEx` at `0x14011e5f8`
- `vid!VidGetPartitionPropertyEx` at `0x14011e5f8`
- `vid!VidGetPartitionProperty` at `0x14011e51d`
- `vid!VidGetPartitionProperty` at `0x14011e543`
- `vid!VidGetPartitionProperty` at `0x14011e692`
- `vid!VidGetPartitionProperty` at `0x14011e6c7`
- `vid!VidGetPartitionProperty` at `0x14011e6ed`
- `vid!VidGetPartitionProperty` at `0x14011e51d`
- `vid!VidGetPartitionProperty` at `0x14011e543`
- `vid!VidGetPartitionProperty` at `0x14011e692`
- `vid!VidGetPartitionProperty` at `0x14011e6c7`
- `vid!VidGetPartitionProperty` at `0x14011e6ed`

## string_xrefs

- `0x14011e7c6`: `onecore\vm\common\vml\VmComputerName.h`
- `0x14011e884`: `onecore\vm\common\vml\VmComputerName.h`
- `0x14011e755`: `IgnoreNonArchitecturalCoreSharingCompatibility`
- `0x14011e955`: `Warning: Failed to read %s from saved state repository.\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ProcessorManager::Restore(ProcessorManager *this, struct VmRepository *a2)
{
  int v4; // eax
  _QWORD *v5; // rdi
  int v6; // eax
  unsigned __int64 v7; // rax
  int i; // r8d
  int j; // edi
  const char *v10; // r9
  _DWORD *v11; // rdi
  WCHAR *v12; // rax
  const char *v13; // r9
  WCHAR *v14; // rax
  const char *v15; // r9
  __int64 v16; // r8
  int v17; // [rsp+20h] [rbp-E0h]
  int v18; // [rsp+20h] [rbp-E0h]
  __int64 v19; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v20; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v21[2]; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v22[3]; // [rsp+60h] [rbp-A0h] BYREF
  HKEY phkResult; // [rsp+78h] [rbp-88h] BYREF
  DWORD nSize[2]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v25; // [rsp+88h] [rbp-78h] BYREF
  unsigned int v26; // [rsp+90h] [rbp-70h] BYREF
  unsigned int v27; // [rsp+94h] [rbp-6Ch] BYREF
  _BYTE v28[4072]; // [rsp+98h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+10A8h] [rbp+FA8h]

  phkResult = 0;
  v4 = (*(__int64 (__fastcall **)(struct VmRepository *, const unsigned __int16 *, HKEY *, __int64))(*(_QWORD *)a2 + 88LL))(
         a2,
         L"/savedVM/processor_attribute",
         &phkResult,
         8);
  if ( v4 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xF51,
      (unsigned int)"onecore\\vm\\worker\\processor\\processormanager.cpp",
      (const char *)(unsigned int)v4,
      v17);
  if ( **((unsigned int **)this + 83) < (unsigned __int64)phkResult >> 32 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xF56,
      (unsigned int)"onecore\\vm\\worker\\processor\\processormanager.cpp",
      (const char *)0x80004005LL,
      v17);
  VidGetPartitionProperty(*((_QWORD *)this + 91), 393219, (char *)this + 608);
  v5 = (_QWORD *)((char *)this + 600);
  VidGetPartitionProperty(*((_QWORD *)this + 91), 393220, (char *)this + 600);
  v26 = 0;
  v6 = (*(__int64 (__fastcall **)(struct VmRepository *, unsigned int *))(*(_QWORD *)a2 + 288LL))(a2, &v26);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xF68,
      (unsigned int)"onecore\\vm\\worker\\processor\\processormanager.cpp",
      (const char *)(unsigned int)v6,
      v17);
  if ( v26 < 0xB01 && *v5 > 1u )
  {
    VidSetPartitionProperty(*((_QWORD *)this + 91), 393220, 0);
    *v5 = 0;
  }
  *(_OWORD *)((char *)this + 520) = 0;
  *((_QWORD *)this + 67) = 0;
  memset_0(v28, 0, sizeof(v28));
  if ( (unsigned int)VidGetPartitionPropertyEx(*((_QWORD *)this + 91), 589840, 0, v28) && v28[0] )
  {
    LODWORD(phkResult) = *((_DWORD *)this + 224);
    BYTE4(phkResult) = 1;
    v22[0] = (unsigned __int16)GetVmProcessorFeaturesBankCount(phkResult);
    v22[1] = 3;
    v22[2] = v28[0];
    v7 = _std_min_8u(v22, &phkResult);
    for ( i = 0; i < v7; ++i )
      *((_QWORD *)this + i + 65) = *(_QWORD *)&v28[8 * i + 8];
  }
  else
  {
    for ( j = 0; j < 2; ++j )
    {
      if ( !(unsigned int)VidGetPartitionProperty(*((_QWORD *)this + 91), j + 393226, (char *)this + 8 * j + 520) )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0xFA2,
          (unsigned int)"onecore\\vm\\worker\\processor\\processormanager.cpp",
          v10);
    }
  }
  VidGetPartitionProperty(*((_QWORD *)this + 91), 327696, (char *)this + 616);
  v11 = (_DWORD *)((char *)this + 632);
  VidGetPartitionProperty(*((_QWORD *)this + 91), 327697, (char *)this + 632);
  v25 = 0;
  if ( (*(int (__fastcall **)(struct VmRepository *, const unsigned __int16 *, __int64 *))(*(_QWORD *)a2 + 120LL))(
         a2,
         L"/savedVM/non_architectural_core_sharing",
         &v25) < 0 )
  {
    if ( (unsigned int)VmlIsDebugTraceEnabled(32800) )
      VmlDebugTrace(
        32800,
        L"Warning: Failed to read %s from saved state repository.\n",
        L"/savedVM/non_architectural_core_sharing");
    v16 = 0;
    v25 = 0;
  }
  else
  {
    phkResult = 0;
    Vml::VmRegistryKey::Open(
      &phkResult,
      HKEY_LOCAL_MACHINE,
      L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Virtualization",
      0x20019u);
    v27 = 0;
    if ( (!Vml::VmRegistryKey::QueryValue(
             (Vml::VmRegistryKey *)&phkResult,
             L"IgnoreNonArchitecturalCoreSharingCompatibility",
             &v27)
       || !v27)
      && v25 == 1
      && *(_QWORD *)v11 != 1 )
    {
      v12 = (WCHAR *)Vml::Details::g_ComputerNameResolved;
      if ( !Vml::Details::g_ComputerNameResolved )
      {
        nSize[0] = 16;
        if ( !GetComputerNameExW(ComputerNameNetBIOS, &Vml::Details::g_ComputerName, nSize) )
          wil::details::in1diag3::Throw_GetLastError(
            retaddr,
            (void *)0x44,
            (unsigned int)"onecore\\vm\\common\\vml\\VmComputerName.h",
            v13);
        v12 = &Vml::Details::g_ComputerName;
        Vml::Details::g_ComputerNameResolved = &Vml::Details::g_ComputerName;
      }
      v20 = (__int64)v12;
      v19 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(*((_QWORD *)this + 89) + 16LL) + 8LL))(*((_QWORD *)this + 89) + 16LL);
      *(_QWORD *)nSize = (**(__int64 (__fastcall ***)(__int64))(*((_QWORD *)this + 89) + 16LL))(*((_QWORD *)this + 89) + 16LL);
      VmEventWriteAndReport<unsigned short const *,unsigned short const *,unsigned short const *>(
        (struct _EVENT_DESCRIPTOR *)&VMWP_VM_GENERIC_PROCESSOR_FEATURES_NOT_SUPPORTED_ERROR,
        4u,
        (__int64)nSize,
        (__int64)&v19,
        (__int64)&v20);
      LODWORD(v19) = *v11;
      LODWORD(v20) = v25;
      v14 = (WCHAR *)Vml::Details::g_ComputerNameResolved;
      if ( !Vml::Details::g_ComputerNameResolved )
      {
        nSize[0] = 16;
        if ( !GetComputerNameExW(ComputerNameNetBIOS, &Vml::Details::g_ComputerName, nSize) )
          wil::details::in1diag3::Throw_GetLastError(
            retaddr,
            (void *)0x44,
            (unsigned int)"onecore\\vm\\common\\vml\\VmComputerName.h",
            v15);
        v14 = &Vml::Details::g_ComputerName;
        Vml::Details::g_ComputerNameResolved = &Vml::Details::g_ComputerName;
      }
      *(_QWORD *)nSize = v14;
      v21[0] = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(*((_QWORD *)this + 89) + 16LL) + 8LL))(*((_QWORD *)this + 89) + 16LL);
      v21[1] = (**(__int64 (__fastcall ***)(__int64))(*((_QWORD *)this + 89) + 16LL))(*((_QWORD *)this + 89) + 16LL);
      VmEventWrite<unsigned short const *,unsigned short const *,unsigned short const *,unsigned int,unsigned int>(
        &VMWP_VM_PROCESSOR_CORE_SHARING_NOT_SUPPORTED_ERROR,
        (__int64)v21,
        (__int64)nSize,
        (__int64)&v20,
        (__int64)&v19);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xFDD,
        (unsigned int)"onecore\\vm\\worker\\processor\\processormanager.cpp",
        (const char *)0x80004005LL,
        v18);
    }
    Vml::VmRegistryKey::Close((Vml::VmRegistryKey *)&phkResult);
    v16 = v25;
  }
  if ( v16 != *(_QWORD *)v11 )
  {
    VidSetPartitionProperty(*((_QWORD *)this + 91), 327697, v16);
    *(_QWORD *)v11 = v25;
  }
}

```

## disassembly

```asm
0x14011e450  mov     [rsp-8+arg_10], rbx
0x14011e455  mov     [rsp-8+arg_18], rsi
0x14011e45a  push    rbp
0x14011e45b  push    rdi
0x14011e45c  push    r15
0x14011e45e  lea     rbp, [rsp-0F90h]
0x14011e466  mov     eax, 1090h
0x14011e46b  call    _alloca_probe
0x14011e470  sub     rsp, rax
0x14011e473  mov     rax, cs:__security_cookie
0x14011e47a  xor     rax, rsp
0x14011e47d  mov     [rbp+0FA0h+var_20], rax
0x14011e484  mov     rsi, rdx
0x14011e487  mov     rbx, rcx
0x14011e48a  mov     [rsp+10A0h+phkResult], 0
0x14011e493  mov     rax, [rdx]
0x14011e496  mov     r9d, 8
0x14011e49c  lea     r8, [rsp+10A0h+phkResult]
0x14011e4a1  lea     rdx, ?SAVED_VM_PROCESSOR_INFO_XPATH@@3QBGB; "/savedVM/processor_attribute"
0x14011e4a8  mov     rcx, rsi
0x14011e4ab  mov     rax, [rax+58h]
0x14011e4af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14011e4b4  mov     rcx, [rbp+0FA8h]; this
0x14011e4bb  test    eax, eax
0x14011e4bd  jns     short loc_14011E4D4
0x14011e4bf  mov     r9d, eax; char *
0x14011e4c2  lea     r8, aOnecoreVmWorke_101; "onecore\\vm\\worker\\processor\\process"...
0x14011e4c9  mov     edx, 0F51h; void *
0x14011e4ce  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14011e4d4  mov     rax, [rbx+298h]
0x14011e4db  mov     ecx, [rax]
0x14011e4dd  mov     rax, [rsp+10A0h+phkResult]
0x14011e4e2  shr     rax, 20h
0x14011e4e6  cmp     rcx, rax
0x14011e4e9  jnb     short loc_14011E50A
0x14011e4eb  mov     rcx, [rbp+0FA8h]; this
0x14011e4f2  mov     r9d, 80004005h; char *
0x14011e4f8  lea     r8, aOnecoreVmWorke_101; "onecore\\vm\\worker\\processor\\process"...
0x14011e4ff  mov     edx, 0F56h; void *
0x14011e504  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14011e50a  lea     r8, [rbx+260h]
0x14011e511  mov     edx, 60003h
0x14011e516  mov     rcx, [rbx+2D8h]
0x14011e51d  call    cs:__imp_VidGetPartitionProperty
0x14011e524  nop     dword ptr [rax+rax+00h]
0x14011e529  lea     rdi, [rbx+258h]
0x14011e530  mov     r8, rdi
0x14011e533  mov     r15d, 60004h
0x14011e539  mov     edx, r15d
0x14011e53c  mov     rcx, [rbx+2D8h]
0x14011e543  call    cs:__imp_VidGetPartitionProperty
0x14011e54a  nop     dword ptr [rax+rax+00h]
0x14011e54f  mov     [rbp+0FA0h+var_1010], 0
0x14011e556  mov     rax, [rsi]
0x14011e559  lea     rdx, [rbp+0FA0h+var_1010]
0x14011e55d  mov     rcx, rsi
0x14011e560  mov     rax, [rax+120h]
0x14011e567  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14011e56c  mov     rcx, [rbp+0FA8h]; this
0x14011e573  test    eax, eax
0x14011e575  jns     short loc_14011E58C
0x14011e577  mov     r9d, eax; char *
0x14011e57a  lea     r8, aOnecoreVmWorke_101; "onecore\\vm\\worker\\processor\\process"...
0x14011e581  mov     edx, 0F68h; void *
0x14011e586  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14011e58c  cmp     [rbp+0FA0h+var_1010], 0B01h
0x14011e593  jnb     short loc_14011E5BB
0x14011e595  cmp     qword ptr [rdi], 1
0x14011e599  jbe     short loc_14011E5BB
0x14011e59b  xor     r8d, r8d
0x14011e59e  mov     rdx, r15
0x14011e5a1  mov     rcx, [rbx+2D8h]
0x14011e5a8  call    cs:__imp_VidSetPartitionProperty
0x14011e5af  nop     dword ptr [rax+rax+00h]
0x14011e5b4  mov     qword ptr [rdi], 0
0x14011e5bb  xorps   xmm0, xmm0
0x14011e5be  xor     eax, eax
0x14011e5c0  movups  xmmword ptr [rbx+208h], xmm0
0x14011e5c7  mov     [rbx+218h], rax
0x14011e5ce  mov     edi, 0FE8h
0x14011e5d3  mov     r8d, edi; Size
0x14011e5d6  xor     edx, edx; Val
0x14011e5d8  lea     rcx, [rbp+0FA0h+var_1008]; void *
0x14011e5dc  call    memset_0
0x14011e5e1  mov     dword ptr [rsp+10A0h+var_1080], edi
0x14011e5e5  lea     r9, [rbp+0FA0h+var_1008]
0x14011e5e9  xor     r8d, r8d
0x14011e5ec  mov     edx, 90010h
0x14011e5f1  mov     rcx, [rbx+2D8h]
0x14011e5f8  call    cs:__imp_VidGetPartitionPropertyEx
0x14011e5ff  nop     dword ptr [rax+rax+00h]
0x14011e604  test    eax, eax
0x14011e606  jz      short loc_14011E675
0x14011e608  cmp     [rbp+0FA0h+var_1008], 0
0x14011e60c  jz      short loc_14011E675
0x14011e60e  mov     eax, [rbx+380h]
0x14011e614  mov     dword ptr [rsp+10A0h+phkResult], eax
0x14011e618  mov     byte ptr [rsp+10A0h+phkResult+4], 1
0x14011e61d  mov     rcx, [rsp+10A0h+phkResult]
0x14011e622  call    ?GetVmProcessorFeaturesBankCount@@YAGV?$optional@I@std@@@Z; GetVmProcessorFeaturesBankCount(std::optional<uint>)
0x14011e627  movzx   eax, ax
0x14011e62a  mov     [rsp+10A0h+var_1040], rax
0x14011e62f  mov     [rsp+10A0h+var_1038], 3
0x14011e638  movzx   eax, [rbp+0FA0h+var_1008]
0x14011e63c  mov     [rsp+10A0h+var_1030], rax
0x14011e641  lea     rdx, [rsp+10A0h+phkResult]
0x14011e646  lea     rcx, [rsp+10A0h+var_1040]
0x14011e64b  call    __std_min_8u
0x14011e650  xor     r8d, r8d
0x14011e653  test    rax, rax
0x14011e656  jz      short loc_14011E6B4
0x14011e658  movsxd  rdx, r8d
0x14011e65b  mov     rcx, [rbp+rdx*8+0FA0h+var_1000]
0x14011e660  mov     [rbx+rdx*8+208h], rcx
0x14011e668  inc     r8d
0x14011e66b  movsxd  rcx, r8d
0x14011e66e  cmp     rcx, rax
0x14011e671  jb      short loc_14011E658
0x14011e673  jmp     short loc_14011E6B4
0x14011e675  xor     edi, edi
0x14011e677  movsxd  r8, edi
0x14011e67a  add     r8, 41h ; 'A'
0x14011e67e  lea     r8, [rbx+r8*8]
0x14011e682  lea     eax, [rdi+6000Ah]
0x14011e688  movsxd  rdx, eax
0x14011e68b  mov     rcx, [rbx+2D8h]
0x14011e692  call    cs:__imp_VidGetPartitionProperty
0x14011e699  nop     dword ptr [rax+rax+00h]
0x14011e69e  mov     rcx, [rbp+0FA8h]; this
0x14011e6a5  test    eax, eax
0x14011e6a7  jz      loc_14011E9B4
0x14011e6ad  inc     edi
0x14011e6af  cmp     edi, 2
0x14011e6b2  jl      short loc_14011E677
0x14011e6b4  lea     r8, [rbx+268h]
0x14011e6bb  mov     edx, 50010h
0x14011e6c0  mov     rcx, [rbx+2D8h]
0x14011e6c7  call    cs:__imp_VidGetPartitionProperty
0x14011e6ce  nop     dword ptr [rax+rax+00h]
0x14011e6d3  lea     rdi, [rbx+278h]
0x14011e6da  mov     r8, rdi
0x14011e6dd  mov     r15d, 50011h
0x14011e6e3  mov     edx, r15d
0x14011e6e6  mov     rcx, [rbx+2D8h]
0x14011e6ed  call    cs:__imp_VidGetPartitionProperty
0x14011e6f4  nop     dword ptr [rax+rax+00h]
0x14011e6f9  mov     [rbp+0FA0h+var_1018], 0
0x14011e701  mov     rax, [rsi]
0x14011e704  lea     r8, [rbp+0FA0h+var_1018]
0x14011e708  lea     rdx, ?SAVED_VM_NON_ARCHITECURAL_CORE_SHARING_XPATH@@3QBGB; "/savedVM/non_architectural_core_sharing"
0x14011e70f  mov     rcx, rsi
0x14011e712  mov     rax, [rax+78h]
0x14011e716  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14011e71b  test    eax, eax
0x14011e71d  js      loc_14011E93E
0x14011e723  mov     [rsp+10A0h+phkResult], 0
0x14011e72c  mov     r9d, 20019h; unsigned int
0x14011e732  lea     r8, ?g_SettingsRegistryPath@Vml@@3QBGB; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x14011e739  mov     rdx, 0FFFFFFFF80000002h; hKey
0x14011e740  lea     rcx, [rsp+10A0h+phkResult]; phkResult
0x14011e745  call    ?Open@VmRegistryKey@Vml@@QEAAHPEAUHKEY__@@PEBGK@Z; Vml::VmRegistryKey::Open(HKEY__ *,ushort const *,ulong)
0x14011e74a  mov     [rbp+0FA0h+var_100C], 0
0x14011e751  lea     r8, [rbp+0FA0h+var_100C]; unsigned int *
0x14011e755  lea     rdx, ?IGNORE_NON_ARCHITECURAL_CORE_SHARING_COMPATIBILITY@@3QBGB; "IgnoreNonArchitecturalCoreSharingCompat"...
0x14011e75c  lea     rcx, [rsp+10A0h+phkResult]; this
0x14011e761  call    ?QueryValue@VmRegistryKey@Vml@@QEBAHPEBGAEAK@Z; Vml::VmRegistryKey::QueryValue(ushort const *,ulong &)
0x14011e766  test    eax, eax
0x14011e768  jz      short loc_14011E774
0x14011e76a  cmp     [rbp+0FA0h+var_100C], 0
0x14011e76e  jnz     loc_14011E92E
0x14011e774  cmp     [rbp+0FA0h+var_1018], 1
0x14011e779  jnz     loc_14011E92E
0x14011e77f  cmp     qword ptr [rdi], 1
0x14011e783  jz      loc_14011E92E
0x14011e789  mov     r15d, 10h
0x14011e78f  lea     rsi, ?g_ComputerName@Details@Vml@@3PAGA; ushort near * Vml::Details::g_ComputerName
0x14011e796  mov     rax, cs:?g_ComputerNameResolved@Details@Vml@@3PEBGEB; ushort const * const Vml::Details::g_ComputerNameResolved
0x14011e79d  test    rax, rax
0x14011e7a0  jnz     short loc_14011E7E0
0x14011e7a2  mov     [rbp+0FA0h+nSize], r15d
0x14011e7a6  lea     r8, [rbp+0FA0h+nSize]; nSize
0x14011e7aa  mov     rdx, rsi; lpBuffer
0x14011e7ad  xor     ecx, ecx; NameType
0x14011e7af  call    cs:__imp_GetComputerNameExW
0x14011e7b6  nop     dword ptr [rax+rax+00h]
0x14011e7bb  test    eax, eax
0x14011e7bd  jnz     short loc_14011E7D6
0x14011e7bf  mov     rcx, [rbp+0FA8h]; this
0x14011e7c6  lea     r8, aOnecoreVmCommo_76; "onecore\\vm\\common\\vml\\VmComputerNam"...
0x14011e7cd  lea     edx, [rax+44h]; void *
0x14011e7d0  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x14011e7d6  mov     rax, rsi
0x14011e7d9  mov     cs:?g_ComputerNameResolved@Details@Vml@@3PEBGEB, rax; ushort const * const Vml::Details::g_ComputerNameResolved
0x14011e7e0  mov     [rsp+10A0h+var_1058], rax
0x14011e7e5  mov     rcx, [rbx+2C8h]
0x14011e7ec  add     rcx, r15
0x14011e7ef  mov     rax, [rcx]
0x14011e7f2  mov     rax, [rax+8]
0x14011e7f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14011e7fb  mov     [rsp+10A0h+var_1060], rax
0x14011e800  mov     rcx, [rbx+2C8h]
0x14011e807  add     rcx, r15
0x14011e80a  mov     rax, [rcx]
0x14011e80d  mov     rax, [rax]
0x14011e810  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14011e815  mov     qword ptr [rbp+0FA0h+nSize], rax
0x14011e819  lea     rax, [rsp+10A0h+var_1058]
0x14011e81e  mov     [rsp+10A0h+var_1070], rax; __int64
0x14011e823  lea     rax, [rsp+10A0h+var_1060]
0x14011e828  mov     [rsp+10A0h+var_1078], rax; __int64
0x14011e82d  lea     rax, [rbp+0FA0h+nSize]
0x14011e831  mov     [rsp+10A0h+var_1080], rax; __int64
0x14011e836  mov     edx, 4; unsigned int
0x14011e83b  lea     rcx, VMWP_VM_GENERIC_PROCESSOR_FEATURES_NOT_SUPPORTED_ERROR; struct _EVENT_DESCRIPTOR *
0x14011e842  call    ??$VmEventWriteAndReport@PEBGPEBGPEBG@@YAXPEBU_EVENT_DESCRIPTOR@@IAEBU_GUID@@PEBG$$QEAPEBG33@Z; VmEventWriteAndReport<ushort const *,ushort const *,ushort const *>(_EVENT_DESCRIPTOR const *,uint,_GUID const &,ushort const *,ushort const * &&,ushort const * &&,ushort const * &&)
0x14011e847  mov     eax, [rdi]
0x14011e849  mov     dword ptr [rsp+10A0h+var_1060], eax
0x14011e84d  mov     eax, dword ptr [rbp+0FA0h+var_1018]
0x14011e850  mov     dword ptr [rsp+10A0h+var_1058], eax
0x14011e854  mov     rax, cs:?g_ComputerNameResolved@Details@Vml@@3PEBGEB; ushort const * const Vml::Details::g_ComputerNameResolved
0x14011e85b  test    rax, rax
0x14011e85e  jnz     short loc_14011E89E
0x14011e860  mov     [rbp+0FA0h+nSize], r15d
0x14011e864  lea     r8, [rbp+0FA0h+nSize]; nSize
0x14011e868  mov     rdx, rsi; lpBuffer
0x14011e86b  xor     ecx, ecx; NameType
0x14011e86d  call    cs:__imp_GetComputerNameExW
0x14011e874  nop     dword ptr [rax+rax+00h]
0x14011e879  test    eax, eax
0x14011e87b  jnz     short loc_14011E894
0x14011e87d  mov     rcx, [rbp+0FA8h]; this
0x14011e884  lea     r8, aOnecoreVmCommo_76; "onecore\\vm\\common\\vml\\VmComputerNam"...
0x14011e88b  lea     edx, [rax+44h]; void *
0x14011e88e  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x14011e894  mov     rax, rsi
0x14011e897  mov     cs:?g_ComputerNameResolved@Details@Vml@@3PEBGEB, rax; ushort const * const Vml::Details::g_ComputerNameResolved
0x14011e89e  mov     qword ptr [rbp+0FA0h+nSize], rax
0x14011e8a2  mov     rcx, [rbx+2C8h]
0x14011e8a9  add     rcx, r15
0x14011e8ac  mov     rax, [rcx]
0x14011e8af  mov     rax, [rax+8]
0x14011e8b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14011e8b8  mov     [rsp+10A0h+var_1050], rax
0x14011e8bd  mov     rcx, [rbx+2C8h]
0x14011e8c4  add     rcx, r15
0x14011e8c7  mov     rax, [rcx]
0x14011e8ca  mov     rax, [rax]
0x14011e8cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14011e8d2  mov     [rsp+10A0h+var_1048], rax
0x14011e8d7  lea     rax, [rsp+10A0h+var_1060]
0x14011e8dc  mov     [rsp+10A0h+var_1068], rax; __int64
0x14011e8e1  lea     rax, [rsp+10A0h+var_1058]
0x14011e8e6  mov     [rsp+10A0h+var_1070], rax; __int64
0x14011e8eb  lea     rax, [rbp+0FA0h+nSize]
0x14011e8ef  mov     [rsp+10A0h+var_1078], rax; __int64
0x14011e8f4  lea     rax, [rsp+10A0h+var_1050]
0x14011e8f9  mov     [rsp+10A0h+var_1080], rax; int
0x14011e8fe  lea     r9, [rsp+10A0h+var_1048]
0x14011e903  lea     rcx, VMWP_VM_PROCESSOR_CORE_SHARING_NOT_SUPPORTED_ERROR; EventDescriptor
0x14011e90a  call    ??$VmEventWrite@PEBGPEBGPEBGII@@YAXPEBU_EVENT_DESCRIPTOR@@IAEBU_GUID@@$$QEAPEBG22$$QEAI3@Z; VmEventWrite<ushort const *,ushort const *,ushort const *,uint,uint>(_EVENT_DESCRIPTOR const *,uint,_GUID const &,ushort const * &&,ushort const * &&,ushort const * &&,uint &&,uint &&)
0x14011e90f  mov     rcx, [rbp+0FA8h]; this
0x14011e916  mov     r9d, 80004005h; char *
0x14011e91c  lea     r8, aOnecoreVmWorke_101; "onecore\\vm\\worker\\processor\\process"...
0x14011e923  mov     edx, 0FDDh; void *
0x14011e928  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14011e92e  lea     rcx, [rsp+10A0h+phkResult]; this
0x14011e933  call    ?Close@VmRegistryKey@Vml@@QEAAXXZ; Vml::VmRegistryKey::Close(void)
0x14011e938  mov     r8, [rbp+0FA0h+var_1018]
0x14011e93c  jmp     short loc_14011E96A
0x14011e93e  mov     esi, 8020h
0x14011e943  mov     ecx, esi
0x14011e945  call    VmlIsDebugTraceEnabled
0x14011e94a  test    eax, eax
0x14011e94c  jz      short loc_14011E963
0x14011e94e  lea     r8, ?SAVED_VM_NON_ARCHITECURAL_CORE_SHARING_XPATH@@3QBGB; "/savedVM/non_architectural_core_sharing"
0x14011e955  lea     rdx, aWarningFailedT; "Warning: Failed to read %s from saved s"...
0x14011e95c  mov     ecx, esi
0x14011e95e  call    VmlDebugTrace
0x14011e963  xor     r8d, r8d
0x14011e966  mov     [rbp+0FA0h+var_1018], r8
0x14011e96a  cmp     r8, [rdi]
0x14011e96d  jz      short loc_14011E98C
0x14011e96f  mov     rdx, r15
0x14011e972  mov     rcx, [rbx+2D8h]
0x14011e979  call    cs:__imp_VidSetPartitionProperty
0x14011e980  nop     dword ptr [rax+rax+00h]
0x14011e985  mov     rax, [rbp+0FA0h+var_1018]
0x14011e989  mov     [rdi], rax
0x14011e98c  mov     rcx, [rbp+0FA0h+var_20]
0x14011e993  xor     rcx, rsp; StackCookie
0x14011e996  call    __security_check_cookie
0x14011e99b  lea     r11, [rsp+10A0h+var_10]
0x14011e9a3  mov     rbx, [r11+30h]
0x14011e9a7  mov     rsi, [r11+38h]
0x14011e9ab  mov     rsp, r11
0x14011e9ae  pop     r15
0x14011e9b0  pop     rdi
0x14011e9b1  pop     rbp
0x14011e9b2  retn
0x14011e9b4  lea     r8, aOnecoreVmWorke_101; "onecore\\vm\\worker\\processor\\process"...
  ... truncated ...
```
