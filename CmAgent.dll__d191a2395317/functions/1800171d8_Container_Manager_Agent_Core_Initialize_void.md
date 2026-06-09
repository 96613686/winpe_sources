# Container::Manager::Agent::Core::Initialize(void)

- ea: `0x1800171d8`
- end: `0x1800173eb`
- name: `?Initialize@Core@Agent@Manager@Container@@YAJXZ`
- size: `531`
- prototype: `__int64 __fastcall(Container::Manager::Agent::Core *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180008364`

## callees

- `0x180002164`
- `0x180002534`
- `0x1800045e4`
- `0x180005934`
- `0x18000b304`
- `0x18000b5b0`
- `0x1800171d8`
- `0x1800225b0`
- `0x180022c10`

## import_xrefs

- `ntdll!RtlPublishWnfStateData` at `0x18001730e`
- `ntdll!RtlPublishWnfStateData` at `0x18001730e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001723b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017345`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001738f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800173ce`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001723b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017345`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001738f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800173ce`

## string_xrefs

- `0x180017223`: `onecore\base\gendrv\silos\clem\agent\core\lib\core.cpp`
- `0x180017330`: `onecore\base\gendrv\silos\clem\agent\core\lib\core.cpp`
- `0x18001736d`: `onecore\base\gendrv\silos\clem\agent\core\lib\core.cpp`

## pseudocode

```c
__int64 __fastcall Container::Manager::Agent::Core::Initialize(Container::Manager::Agent::Core *this)
{
  Container::Manager::Agent::Core::Details::FirstBootExperienceManager *v1; // rbx
  int v2; // eax
  unsigned int v3; // edi
  __int64 v4; // rdx
  int DwordValue; // eax
  _QWORD *v7; // rax
  __int64 v8; // r8
  __int64 v9; // r9
  int v10; // eax
  unsigned __int64 v11; // r9
  __int64 v12; // rdx
  int v13; // eax
  Container::Manager::Agent::Core::Details::FirstBootExperienceManager *v14; // rdi
  int v15; // [rsp+20h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+18h]
  unsigned int v17; // [rsp+50h] [rbp+20h] BYREF
  HKEY hKey; // [rsp+58h] [rbp+28h] BYREF

  v1 = 0;
  hKey = 0;
  v2 = Csl::OpenRegistryKey(this, L"SYSTEM\\CurrentControlSet\\Control\\Containers", 131097, &hKey);
  v3 = v2;
  if ( v2 == -2147024894 )
    goto LABEL_22;
  if ( v2 < 0 )
  {
    v4 = 439;
    goto LABEL_4;
  }
  v17 = 0;
  DwordValue = Csl::RegistryKey::GetDwordValue((Csl::RegistryKey *)&hKey, L"FirstBootExperienceEnabled", &v17);
  v3 = DwordValue;
  if ( DwordValue == -2147024894 )
    goto LABEL_22;
  if ( DwordValue < 0 )
  {
    v4 = 448;
LABEL_4:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\agent\\core\\lib\\core.cpp",
      (const char *)v3,
      v15);
    if ( hKey )
      RegCloseKey(hKey);
    return v3;
  }
  if ( !v17 )
  {
LABEL_22:
    v14 = qword_18004B978;
    qword_18004B978 = v1;
    if ( v14 )
    {
      Container::Manager::Agent::Core::Details::FirstBootExperienceManager::~FirstBootExperienceManager(v14);
      operator delete(v14, (const struct std::nothrow_t *)0x178);
    }
    if ( hKey )
      RegCloseKey(hKey);
    return 0;
  }
  v7 = operator new(0x178u, (const struct std::nothrow_t *)&std::nothrow);
  v1 = (Container::Manager::Agent::Core::Details::FirstBootExperienceManager *)v7;
  if ( v7 )
  {
    *(_BYTE *)v7 = 0;
    v7[1] = 0;
    *((_DWORD *)v7 + 4) = -2147467259;
    *(_QWORD *)((char *)v7 + 20) = 0;
    *(_QWORD *)((char *)v7 + 28) = 0;
    wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
      v7 + 5,
      "FirstUserLogon",
      v8,
      v9);
    *((_QWORD *)v1 + 5) = &CmAgentTraceProvider::FirstUserLogon::`vftable';
    v10 = Container::Manager::Agent::Core::Details::FirstBootExperienceManager::Initialize(v1);
    v3 = v10;
    if ( v10 < 0 )
    {
      v11 = (unsigned int)v10;
      v12 = 456;
LABEL_16:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v12,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\agent\\core\\lib\\core.cpp",
        (const char *)v11,
        v15);
      if ( hKey )
        RegCloseKey(hKey);
      Container::Manager::Agent::Core::Details::FirstBootExperienceManager::~FirstBootExperienceManager(v1);
      operator delete(v1, (const struct std::nothrow_t *)0x178);
      return v3;
    }
    v15 = 0;
    v13 = RtlPublishWnfStateData(WNF_CONT_RESTORE_FROM_SNAPSHOT_COMPLETE, 0, 0, 0);
    v3 = v13 | 0x10000000;
    if ( v13 < 0 )
    {
      v11 = v3;
      v12 = 460;
      goto LABEL_16;
    }
    goto LABEL_22;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1C7,
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\agent\\core\\lib\\core.cpp",
    (const char *)0x8007000ELL,
    v15);
  if ( hKey )
    RegCloseKey(hKey);
  return 2147942414LL;
}

```

## disassembly

```asm
0x1800171d8  mov     [rsp-18h+arg_10], rbx
0x1800171dd  push    rbp
0x1800171de  push    rdi
0x1800171df  push    r14
0x1800171e1  mov     rbp, rsp
0x1800171e4  sub     rsp, 30h
0x1800171e8  xor     ebx, ebx
0x1800171ea  lea     r9, [rbp+hKey]
0x1800171ee  mov     r8d, 20019h
0x1800171f4  mov     [rbp+hKey], rbx
0x1800171f8  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Control\\Con"...
0x1800171ff  call    ?OpenRegistryKey@Csl@@YAJPEAUHKEY__@@PEBGW4RegistryKeyAccess@1@AEAVRegistryKey@1@@Z; Csl::OpenRegistryKey(HKEY__ *,ushort const *,Csl::RegistryKeyAccess,Csl::RegistryKey &)
0x180017204  mov     edi, eax
0x180017206  mov     r14d, 178h
0x18001720c  cmp     eax, 80070002h
0x180017211  jz      loc_18001739F
0x180017217  test    eax, eax
0x180017219  jns     short loc_18001724E
0x18001721b  lea     edx, [r14+3Fh]; void *
0x18001721f  mov     rcx, [rbp+18h]; this
0x180017223  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\clem\\age"...
0x18001722a  mov     r9d, edi; char *
0x18001722d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017232  mov     rcx, [rbp+hKey]; hKey
0x180017236  test    rcx, rcx
0x180017239  jz      short loc_180017247
0x18001723b  call    cs:__imp_RegCloseKey
0x180017242  nop     dword ptr [rax+rax+00h]
0x180017247  mov     eax, edi
0x180017249  jmp     loc_1800173DC
0x18001724e  lea     r8, [rbp+arg_0]; unsigned int *
0x180017252  mov     [rbp+arg_0], ebx
0x180017255  lea     rdx, aFirstbootexper; "FirstBootExperienceEnabled"
0x18001725c  lea     rcx, [rbp+hKey]; this
0x180017260  call    ?GetDwordValue@RegistryKey@Csl@@QEBAJPEBGAEAK@Z; Csl::RegistryKey::GetDwordValue(ushort const *,ulong &)
0x180017265  mov     edi, eax
0x180017267  cmp     eax, 80070002h
0x18001726c  jz      loc_18001739F
0x180017272  test    eax, eax
0x180017274  jns     short loc_18001727D
0x180017276  mov     edx, 1C0h
0x18001727b  jmp     short loc_18001721F
0x18001727d  cmp     [rbp+arg_0], ebx
0x180017280  jz      loc_18001739F
0x180017286  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001728d  mov     rcx, r14; unsigned __int64
0x180017290  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180017295  mov     rbx, rax
0x180017298  test    rax, rax
0x18001729b  jz      loc_180017369
0x1800172a1  lea     rdx, aFirstuserlogon; "FirstUserLogon"
0x1800172a8  mov     byte ptr [rax], 0
0x1800172ab  lea     rcx, [rax+28h]
0x1800172af  mov     qword ptr [rax+8], 0
0x1800172b7  mov     dword ptr [rax+10h], 80004005h
0x1800172be  mov     qword ptr [rax+14h], 0
0x1800172c6  mov     qword ptr [rax+1Ch], 0
0x1800172ce  call    ??0?$ActivityBase@VCmAgentTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800172d3  lea     rax, ??_7FirstUserLogon@CmAgentTraceProvider@@6B@; const CmAgentTraceProvider::FirstUserLogon::`vftable'
0x1800172da  mov     rcx, rbx; this
0x1800172dd  mov     [rbx+28h], rax
0x1800172e1  call    ?Initialize@FirstBootExperienceManager@Details@Core@Agent@Manager@Container@@QEAAJXZ; Container::Manager::Agent::Core::Details::FirstBootExperienceManager::Initialize(void)
0x1800172e6  mov     edi, eax
0x1800172e8  test    eax, eax
0x1800172ea  jns     short loc_1800172F6
0x1800172ec  mov     r9d, eax
0x1800172ef  mov     edx, 1C8h
0x1800172f4  jmp     short loc_18001732C
0x1800172f6  mov     rcx, cs:WNF_CONT_RESTORE_FROM_SNAPSHOT_COMPLETE
0x1800172fd  xor     r9d, r9d
0x180017300  xor     r8d, r8d
0x180017303  mov     qword ptr [rsp+30h+var_10], 0; int
0x18001730c  xor     edx, edx
0x18001730e  call    cs:__imp_RtlPublishWnfStateData
0x180017315  nop     dword ptr [rax+rax+00h]
0x18001731a  mov     edi, eax
0x18001731c  or      edi, 10000000h
0x180017322  jge     short loc_18001739F
0x180017324  mov     r9d, edi; char *
0x180017327  mov     edx, 1CCh; void *
0x18001732c  mov     rcx, [rbp+18h]; this
0x180017330  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\clem\\age"...
0x180017337  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001733c  mov     rcx, [rbp+hKey]; hKey
0x180017340  test    rcx, rcx
0x180017343  jz      short loc_180017351
0x180017345  call    cs:__imp_RegCloseKey
0x18001734c  nop     dword ptr [rax+rax+00h]
0x180017351  mov     rcx, rbx; this
0x180017354  call    ??1FirstBootExperienceManager@Details@Core@Agent@Manager@Container@@QEAA@XZ; Container::Manager::Agent::Core::Details::FirstBootExperienceManager::~FirstBootExperienceManager(void)
0x180017359  mov     rdx, r14; struct std::nothrow_t *
0x18001735c  mov     rcx, rbx; void *
0x18001735f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180017364  jmp     loc_180017247
0x180017369  mov     rcx, [rbp+18h]; this
0x18001736d  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\clem\\age"...
0x180017374  mov     ebx, 8007000Eh
0x180017379  mov     edx, 1C7h; void *
0x18001737e  mov     r9d, ebx; char *
0x180017381  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017386  mov     rcx, [rbp+hKey]; hKey
0x18001738a  test    rcx, rcx
0x18001738d  jz      short loc_18001739B
0x18001738f  call    cs:__imp_RegCloseKey
0x180017396  nop     dword ptr [rax+rax+00h]
0x18001739b  mov     eax, ebx
0x18001739d  jmp     short loc_1800173DC
0x18001739f  mov     rdi, cs:qword_18004B978
0x1800173a6  mov     cs:qword_18004B978, rbx
0x1800173ad  test    rdi, rdi
0x1800173b0  jz      short loc_1800173C5
0x1800173b2  mov     rcx, rdi; this
0x1800173b5  call    ??1FirstBootExperienceManager@Details@Core@Agent@Manager@Container@@QEAA@XZ; Container::Manager::Agent::Core::Details::FirstBootExperienceManager::~FirstBootExperienceManager(void)
0x1800173ba  mov     rdx, r14; struct std::nothrow_t *
0x1800173bd  mov     rcx, rdi; void *
0x1800173c0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800173c5  mov     rcx, [rbp+hKey]; hKey
0x1800173c9  test    rcx, rcx
0x1800173cc  jz      short loc_1800173DA
0x1800173ce  call    cs:__imp_RegCloseKey
0x1800173d5  nop     dword ptr [rax+rax+00h]
0x1800173da  xor     eax, eax
0x1800173dc  mov     rbx, [rsp+30h+arg_10]
0x1800173e1  add     rsp, 30h
0x1800173e5  pop     r14
0x1800173e7  pop     rdi
0x1800173e8  pop     rbp
0x1800173e9  retn
```
