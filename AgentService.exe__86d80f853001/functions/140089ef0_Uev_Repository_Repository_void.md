# Uev::Repository::Repository(void)

- ea: `0x140089ef0`
- end: `0x14008a523`
- name: `??0Repository@Uev@@AEAA@XZ`
- size: `1587`
- prototype: `Uev::Repository *__fastcall(Uev::Repository *this)`
- caller_count: `1`
- callee_count: `31`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x140067eb8`

## callees

- `0x140003e50`
- `0x140004ab4`
- `0x140004df0`
- `0x14000adb4`
- `0x14000afc0`
- `0x14000ba60`
- `0x14000bcd0`
- `0x14000c1cc`
- `0x14000c2b8`
- `0x14000d1d8`
- `0x14000d448`
- `0x14000d7b4`
- `0x140012a14`
- `0x140013bb0`
- `0x140015190`
- `0x140015874`
- `0x14001a2a4`
- `0x140020568`
- `0x1400205f4`
- `0x1400218a0`
- `0x140023dbc`
- `0x140023e54`
- `0x1400259f8`
- `0x1400380d4`
- `0x140046e04`
- `0x140046f94`
- `0x140047fa0`
- `0x140089ef0`
- `0x14008c0e4`
- `0x14008c424`
- `0x14008c774`

## import_xrefs

- `ADVAPI32!CreateWellKnownSid` at `0x140089fc7`
- `ADVAPI32!CreateWellKnownSid` at `0x140089fc7`
- `KERNEL32!GetLastError` at `0x14008a36c`
- `KERNEL32!GetLastError` at `0x14008a36c`

## string_xrefs

- `0x14008a388`: `Repository::Repository() - CreateWellKnownSid() returned error `
- `0x14008a4a6`: `Repository::Repository() - Error no repository path was configured.`
- `0x14008a426`: `No repository path found`
- `0x14008a3e0`: `Failed to create administrator group SID`
- `0x14008a26c`: `Repository path found`
- `0x14008a17e`: `The settings storage path has been set to: `

## pseudocode

```c
// Hidden C++ exception states: #wind=5
Uev::Repository *__fastcall Uev::Repository::Repository(Uev::Repository *this)
{
  boost::filesystem::path *v2; // rbx
  Uev::Repository *v3; // rcx
  Uev::Repository *v4; // rcx
  __int64 v5; // rcx
  Uev::Repository *v6; // rcx
  __int64 v7; // rax
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int128 *v10; // r8
  const wchar_t *v11; // rax
  _QWORD *v12; // rdi
  __int64 v13; // rbx
  _QWORD *v14; // rax
  _QWORD *v15; // rbx
  __int64 v17; // rax
  __int64 v18; // rdi
  __int64 v19; // rax
  __int64 v20; // rbx
  __int64 v21; // rax
  __int64 v22; // rbx
  DWORD LastError; // [rsp+30h] [rbp-D0h] BYREF
  __int128 Src; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v25; // [rsp+48h] [rbp-B8h]
  _OWORD v26[2]; // [rsp+58h] [rbp-A8h] BYREF
  Uev::Repository *v27; // [rsp+78h] [rbp-88h]
  _QWORD pExceptionObject[8]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v29[64]; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v30; // [rsp+100h] [rbp+0h] BYREF
  __int128 v31; // [rsp+110h] [rbp+10h]
  DWORD cbSid; // [rsp+120h] [rbp+20h] BYREF
  __int64 v33; // [rsp+128h] [rbp+28h] BYREF
  _OWORD v34[2]; // [rsp+130h] [rbp+30h] BYREF
  _OWORD v35[2]; // [rsp+150h] [rbp+50h] BYREF
  _QWORD v36[7]; // [rsp+170h] [rbp+70h] BYREF
  _BYTE v37[32]; // [rsp+1A8h] [rbp+A8h] BYREF
  _BYTE v38[40]; // [rsp+1C8h] [rbp+C8h] BYREF
  _BYTE v39[128]; // [rsp+1F0h] [rbp+F0h] BYREF

  v27 = this;
  *(_QWORD *)this = &Uev::Repository::`vftable';
  *((_BYTE *)this + 8) = 1;
  v2 = (Uev::Repository *)((char *)this + 16);
  *((_OWORD *)this + 1) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  std::wstring::_Construct<1,wchar_t *>((_QWORD *)this + 2, &Data, 0);
  *((_OWORD *)this + 3) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 0;
  std::wstring::_Construct<1,wchar_t *>((_QWORD *)this + 6, &Data, 0);
  Uev::ScopeTracker::ScopeTracker((Uev::ScopeTracker *)v39, L"CscChangeManager", L"Repository::Repository()");
  if ( !Uev::Repository::s_LocalAdminGroupSid )
  {
    cbSid = 68;
    if ( !CreateWellKnownSid(WinBuiltinAdministratorsSid, 0, &Uev::Repository::s_LocalAdminGroupSidBuffer, &cbSid) )
    {
      v17 = Uev::Singleton<Uev::Log,Uev::Log>::Instance();
      if ( (unsigned __int8)Uev::Log::WriteEnabled(v17, 8) )
      {
        v18 = Uev::Singleton<Uev::Log,Uev::Log>::Instance();
        LastError = GetLastError();
        v19 = boost::lexical_cast<std::wstring,unsigned long>(&v30, &LastError);
        v20 = std::operator+<wchar_t>(&Src, L"Repository::Repository() - CreateWellKnownSid() returned error ", v19);
        std::wstring::wstring(v26, L"CscChangeManager");
        Uev::Log::Write(v18, 8, v26, v20);
        boost::filesystem::path::~path((boost::filesystem::path *)v26);
        boost::filesystem::path::~path((boost::filesystem::path *)&Src);
        boost::filesystem::path::~path((boost::filesystem::path *)&v30);
      }
      std::wstring::wstring(v26, L"Failed to create administrator group SID");
      Uev::UevException::UevException(pExceptionObject, v26);
      throw (Uev::UevException *)pExceptionObject;
    }
    Uev::Repository::s_LocalAdminGroupSid = &Uev::Repository::s_LocalAdminGroupSidBuffer;
  }
  v33 = 0;
  memset(v34, 0, sizeof(v34));
  std::wstring::_Construct<1,wchar_t *>(v34, &Data, 0);
  memset(v35, 0, sizeof(v35));
  std::wstring::_Construct<1,wchar_t *>(v35, &Data, 0);
  if ( Uev::Repository::LookupSettingsStoragePath(
         v3,
         (struct boost::filesystem::path *)v34,
         (struct boost::filesystem::path *)v35) )
  {
    std::wstring::operator=(v2, v34);
    std::wstring::operator=((char *)this + 48, v35);
    *((_BYTE *)this + 8) = 0;
  }
  else if ( Uev::Repository::LookupCachedADSettingsStoragePath(
              v4,
              (struct boost::filesystem::path *)v34,
              (struct boost::filesystem::path *)v35) )
  {
    std::wstring::operator=(v2, v34);
    std::wstring::operator=((char *)this + 48, v35);
  }
  else if ( Uev::Repository::LookupADSettingsStoragePath(
              v6,
              (struct boost::filesystem::path *)v34,
              (struct boost::filesystem::path *)v35) )
  {
    std::wstring::operator=(v2, v34);
    std::wstring::operator=((char *)this + 48, v35);
    std::wstring::wstring((__int64)&v30, (__int64)v34);
    v7 = Uev::Singleton<Uev::Configuration,Uev::Configuration>::Instance();
    if ( !(unsigned __int8)Uev::Setting<std::wstring>::Set(v7 + 18656, v8, &v30, &v33)
      && (Microsoft_User_Experience_Virtualization_App_AgentEnableBits & 4) != 0 )
    {
      v10 = &v30;
      if ( *((_QWORD *)&v31 + 1) > 7u )
        v10 = (__int128 *)v30;
      McTemplateU0zq_EventWriteTransfer(v9, ChangeManagerMsgSetADRemoteRepositoryFailed, v10, (unsigned int)v33);
    }
    std::wstring::_Tidy_deallocate(&v30);
  }
  if ( !*((_QWORD *)this + 4) )
  {
    if ( (Microsoft_User_Experience_Virtualization_App_AgentEnableBits & 4) != 0 )
      McTemplateU0_EventWriteTransfer(v5, ChangeManagerMsgNoRemoteRepository);
    std::wstring::wstring(&Src, L"No repository path found");
    std::wstring::wstring(v26, &Data);
    Uev::UevHealthEvent::UevHealthEvent((unsigned int)v36, (unsigned int)v26, (unsigned int)&Src, 4050, 2);
    boost::filesystem::path::~path((boost::filesystem::path *)v26);
    boost::filesystem::path::~path((boost::filesystem::path *)&Src);
    Uev::UevIPC::Send((Uev::UevIPC *)v36);
    v21 = Uev::Singleton<Uev::Log,Uev::Log>::Instance();
    if ( (unsigned __int8)Uev::Log::WriteEnabled(v21, 8) )
    {
      v22 = Uev::Singleton<Uev::Log,Uev::Log>::Instance();
      std::wstring::wstring(&Src, L"Repository::Repository() - Error no repository path was configured.");
      std::wstring::wstring(v26, L"CscChangeManager");
      Uev::Log::Write(v22, 8, v26, &Src);
      boost::filesystem::path::~path((boost::filesystem::path *)v26);
      boost::filesystem::path::~path((boost::filesystem::path *)&Src);
    }
    std::wstring::wstring(pExceptionObject, L"Failed to initialize the repository");
    Uev::UevException::UevException(v29, pExceptionObject);
    throw (Uev::UevException *)v29;
  }
  v11 = &Uev::Repository::s_settingsPackages;
  if ( (unsigned __int64)qword_1400D1948 > 7 )
    v11 = *(const wchar_t **)&Uev::Repository::s_settingsPackages;
  boost::filesystem::path::append_v3(v2, v11, &v11[qword_1400D1940]);
  if ( (*(_BYTE *)(*(_QWORD *)Uev::Singleton<Uev::Log,Uev::Log>::Instance() + 32LL) & 4) != 0 )
  {
    v12 = (_QWORD *)Uev::Singleton<Uev::Log,Uev::Log>::Instance();
    v13 = std::wstring::wstring((__int64)pExceptionObject, (__int64)v2);
    Src = 0;
    v25 = 0;
    std::wstring::_Construct<1,wchar_t *>(&Src, L"The settings storage path has been set to: ", 0x2Bu);
    v14 = std::wstring::_Append<wchar_t>(&Src, L": ", 2u);
    v26[0] = *(_OWORD *)v14;
    v26[1] = *((_OWORD *)v14 + 1);
    v14[2] = 0;
    v14[3] = 7;
    *(_WORD *)v14 = 0;
    v15 = (_QWORD *)std::operator+<wchar_t>(v29, v26, v13);
    v30 = 0;
    v31 = 0;
    std::wstring::_Construct<1,wchar_t *>(&v30, L"CscChangeManager", 0x10u);
    if ( v15[3] > 7u )
      v15 = (_QWORD *)*v15;
    Uev::LogImpl::Write(*v12, 4, &v30, v15);
    std::wstring::_Tidy_deallocate(&v30);
    std::wstring::_Tidy_deallocate(v29);
    std::wstring::_Tidy_deallocate(v26);
    std::wstring::_Tidy_deallocate(&Src);
    std::wstring::_Tidy_deallocate(pExceptionObject);
  }
  v30 = 0;
  v31 = 0;
  std::wstring::_Construct<1,wchar_t *>(&v30, L"Repository path found", 0x15u);
  Src = 0;
  v25 = 0;
  std::wstring::_Construct<1,wchar_t *>(&Src, &Data, 0);
  Uev::UevHealthEvent::UevHealthEvent((unsigned int)v36, (unsigned int)&Src, (unsigned int)&v30, 52, 4);
  std::wstring::_Tidy_deallocate(&Src);
  std::wstring::_Tidy_deallocate(&v30);
  Uev::UevIPC::Send((Uev::UevIPC *)v36);
  v36[0] = &Uev::UevHealthEvent::`vftable';
  std::wstring::_Tidy_deallocate(v38);
  std::wstring::_Tidy_deallocate(v37);
  Uev::UevIPC::~UevIPC((Uev::UevIPC *)v36);
  std::wstring::_Tidy_deallocate(v35);
  std::wstring::_Tidy_deallocate(v34);
  Uev::ScopeTracker::~ScopeTracker((Uev::ScopeTracker *)v39);
  return this;
}

```

## disassembly

```asm
0x140089ef0  push    rbp
0x140089ef2  push    rbx
0x140089ef3  push    rsi
0x140089ef4  push    rdi
0x140089ef5  push    r12
0x140089ef7  push    r15
0x140089ef9  lea     rbp, [rsp-188h]
0x140089f01  sub     rsp, 288h
0x140089f08  mov     rax, cs:__security_cookie
0x140089f0f  xor     rax, rsp
0x140089f12  mov     [rbp+1B0h+var_40], rax
0x140089f19  mov     rsi, rcx
0x140089f1c  mov     [rsp+2B0h+var_238], rcx
0x140089f21  lea     rax, ??_7Repository@Uev@@6B@; const Uev::Repository::`vftable'
0x140089f28  mov     [rcx], rax
0x140089f2b  mov     byte ptr [rcx+8], 1
0x140089f2f  lea     rbx, [rcx+10h]
0x140089f33  xorps   xmm0, xmm0
0x140089f36  movups  xmmword ptr [rbx], xmm0
0x140089f39  mov     qword ptr [rbx+10h], 0
0x140089f41  mov     qword ptr [rbx+18h], 0
0x140089f49  xor     r8d, r8d
0x140089f4c  lea     r12, Data
0x140089f53  mov     rdx, r12
0x140089f56  mov     rcx, rbx
0x140089f59  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x140089f5e  nop
0x140089f5f  lea     rdi, [rsi+30h]
0x140089f63  xorps   xmm0, xmm0
0x140089f66  movups  xmmword ptr [rdi], xmm0
0x140089f69  mov     qword ptr [rdi+10h], 0
0x140089f71  mov     qword ptr [rdi+18h], 0
0x140089f79  xor     r8d, r8d
0x140089f7c  mov     rdx, r12
0x140089f7f  mov     rcx, rdi
0x140089f82  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x140089f87  nop
0x140089f88  lea     r8, aRepositoryRepo; "Repository::Repository()"
0x140089f8f  lea     rdx, aCscchangemanag; "CscChangeManager"
0x140089f96  lea     rcx, [rbp+1B0h+var_C0]; this
0x140089f9d  call    ??0ScopeTracker@Uev@@QEAA@PEB_W0@Z; Uev::ScopeTracker::ScopeTracker(wchar_t const *,wchar_t const *)
0x140089fa2  nop
0x140089fa3  cmp     cs:?s_LocalAdminGroupSid@Repository@Uev@@0PEAXEA, 0; void * Uev::Repository::s_LocalAdminGroupSid
0x140089fab  jnz     short loc_140089FDC
0x140089fad  mov     [rbp+1B0h+cbSid], 44h ; 'D'
0x140089fb4  lea     r9, [rbp+1B0h+cbSid]; cbSid
0x140089fb8  lea     r15, ?s_LocalAdminGroupSidBuffer@Repository@Uev@@0PADA; char near * Uev::Repository::s_LocalAdminGroupSidBuffer
0x140089fbf  mov     r8, r15; pSid
0x140089fc2  xor     edx, edx; DomainSid
0x140089fc4  lea     ecx, [rdx+1Ah]; WellKnownSidType
0x140089fc7  call    cs:__imp_CreateWellKnownSid
0x140089fcd  test    eax, eax
0x140089fcf  jz      loc_14008A34B
0x140089fd5  mov     cs:?s_LocalAdminGroupSid@Repository@Uev@@0PEAXEA, r15; void * Uev::Repository::s_LocalAdminGroupSid
0x140089fdc  mov     [rbp+1B0h+var_188], 0
0x140089fe4  xorps   xmm0, xmm0
0x140089fe7  movups  [rbp+1B0h+var_180], xmm0
0x140089feb  xorps   xmm1, xmm1
0x140089fee  movdqu  [rbp+1B0h+var_170], xmm1
0x140089ff3  xor     r8d, r8d
0x140089ff6  mov     rdx, r12
0x140089ff9  lea     rcx, [rbp+1B0h+var_180]
0x140089ffd  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x14008a002  nop
0x14008a003  xorps   xmm0, xmm0
0x14008a006  movups  [rbp+1B0h+var_160], xmm0
0x14008a00a  xorps   xmm1, xmm1
0x14008a00d  movdqu  [rbp+1B0h+var_150], xmm1
0x14008a012  xor     r8d, r8d
0x14008a015  mov     rdx, r12
0x14008a018  lea     rcx, [rbp+1B0h+var_160]
0x14008a01c  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x14008a021  nop
0x14008a022  lea     r8, [rbp+1B0h+var_160]; struct boost::filesystem::path *
0x14008a026  lea     rdx, [rbp+1B0h+var_180]; struct boost::filesystem::path *
0x14008a02a  call    ?LookupSettingsStoragePath@Repository@Uev@@AEBA_NAEAVpath@filesystem@boost@@0@Z; Uev::Repository::LookupSettingsStoragePath(boost::filesystem::path &,boost::filesystem::path &)
0x14008a02f  mov     r15d, 4
0x14008a035  lea     rdx, [rbp+1B0h+var_180]; struct boost::filesystem::path *
0x14008a039  test    al, al
0x14008a03b  jz      short loc_14008A05A
0x14008a03d  mov     rcx, rbx
0x14008a040  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x14008a045  lea     rdx, [rbp+1B0h+var_160]
0x14008a049  mov     rcx, rdi
0x14008a04c  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x14008a051  mov     byte ptr [rsi+8], 0
0x14008a055  jmp     loc_14008A105
0x14008a05a  lea     r8, [rbp+1B0h+var_160]; struct boost::filesystem::path *
0x14008a05e  call    ?LookupCachedADSettingsStoragePath@Repository@Uev@@AEBA_NAEAVpath@filesystem@boost@@0@Z; Uev::Repository::LookupCachedADSettingsStoragePath(boost::filesystem::path &,boost::filesystem::path &)
0x14008a063  lea     rdx, [rbp+1B0h+var_180]; struct boost::filesystem::path *
0x14008a067  test    al, al
0x14008a069  jz      short loc_14008A084
0x14008a06b  mov     rcx, rbx
0x14008a06e  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x14008a073  lea     rdx, [rbp+1B0h+var_160]
0x14008a077  mov     rcx, rdi
0x14008a07a  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x14008a07f  jmp     loc_14008A105
0x14008a084  lea     r8, [rbp+1B0h+var_160]; struct boost::filesystem::path *
0x14008a088  call    ?LookupADSettingsStoragePath@Repository@Uev@@AEBA_NAEAVpath@filesystem@boost@@0@Z; Uev::Repository::LookupADSettingsStoragePath(boost::filesystem::path &,boost::filesystem::path &)
0x14008a08d  test    al, al
0x14008a08f  jz      short loc_14008A105
0x14008a091  lea     rdx, [rbp+1B0h+var_180]
0x14008a095  mov     rcx, rbx
0x14008a098  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x14008a09d  lea     rdx, [rbp+1B0h+var_160]
0x14008a0a1  mov     rcx, rdi
0x14008a0a4  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x14008a0a9  lea     rdx, [rbp+1B0h+var_180]
0x14008a0ad  lea     rcx, [rbp+1B0h+var_1B0]
0x14008a0b1  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14008a0b6  nop
0x14008a0b7  call    ?Instance@?$Singleton@VConfiguration@Uev@@V12@@Uev@@SAPEAVConfiguration@2@XZ; Uev::Singleton<Uev::Configuration,Uev::Configuration>::Instance(void)
0x14008a0bc  lea     rcx, [rax+48E0h]
0x14008a0c3  lea     r9, [rbp+1B0h+var_188]
0x14008a0c7  lea     r8, [rbp+1B0h+var_1B0]
0x14008a0cb  call    ?Set@?$Setting@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Uev@@QEAA_NW4SettingSource@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAUSettingInfo@2@@Z; Uev::Setting<std::wstring>::Set(Uev::SettingSource,std::wstring const &,Uev::SettingInfo &)
0x14008a0d0  test    al, al
0x14008a0d2  jnz     short loc_14008A0FC
0x14008a0d4  test    cs:Microsoft_User_Experience_Virtualization_App_AgentEnableBits, r15b
0x14008a0db  jz      short loc_14008A0FC
0x14008a0dd  lea     r8, [rbp+1B0h+var_1B0]
0x14008a0e1  cmp     [rbp+1B0h+var_198], 7
0x14008a0e6  cmova   r8, qword ptr [rbp+1B0h+var_1B0]
0x14008a0eb  mov     r9d, dword ptr [rbp+1B0h+var_188]
0x14008a0ef  lea     rdx, ChangeManagerMsgSetADRemoteRepositoryFailed
0x14008a0f6  call    McTemplateU0zq_EventWriteTransfer
0x14008a0fb  nop
0x14008a0fc  lea     rcx, [rbp+1B0h+var_1B0]
0x14008a100  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14008a105  cmp     qword ptr [rsi+20h], 0
0x14008a10a  jz      loc_14008A411
0x14008a110  mov     rcx, cs:qword_1400D1940
0x14008a117  cmp     cs:qword_1400D1948, 7
0x14008a11f  lea     rax, ?s_settingsPackages@Repository@Uev@@0V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@A; std::wstring Uev::Repository::s_settingsPackages
0x14008a126  jbe     short loc_14008A12F
0x14008a128  mov     rax, cs:?s_settingsPackages@Repository@Uev@@0V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@A; std::wstring Uev::Repository::s_settingsPackages
0x14008a12f  mov     rdx, rax; wchar_t *
0x14008a132  lea     r8, [rax+rcx*2]; wchar_t *
0x14008a136  mov     rcx, rbx; this
0x14008a139  call    ?append_v3@path@filesystem@boost@@AEAAXPEB_W0@Z; boost::filesystem::path::append_v3(wchar_t const *,wchar_t const *)
0x14008a13e  call    ?Instance@?$Singleton@VLog@Uev@@V12@@Uev@@SAPEAVLog@2@XZ; Uev::Singleton<Uev::Log,Uev::Log>::Instance(void)
0x14008a143  mov     rax, [rax]
0x14008a146  test    [rax+20h], r15b
0x14008a14a  jbe     loc_14008A257
0x14008a150  call    ?Instance@?$Singleton@VLog@Uev@@V12@@Uev@@SAPEAVLog@2@XZ; Uev::Singleton<Uev::Log,Uev::Log>::Instance(void)
0x14008a155  mov     rdi, rax
0x14008a158  mov     rdx, rbx
0x14008a15b  lea     rcx, [rbp+1B0h+pExceptionObject]
0x14008a15f  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14008a164  mov     rbx, rax
0x14008a167  xorps   xmm0, xmm0
0x14008a16a  movups  [rsp+2B0h+Src], xmm0
0x14008a16f  xorps   xmm1, xmm1
0x14008a172  movdqu  [rsp+2B0h+var_268], xmm1
0x14008a178  mov     r8d, 2Bh ; '+'
0x14008a17e  lea     rdx, aTheSettingsSto_0; "The settings storage path has been set "...
0x14008a185  lea     rcx, [rsp+2B0h+Src]
0x14008a18a  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x14008a18f  nop
0x14008a190  mov     r8d, 2
0x14008a196  lea     rdx, asc_1400A0EA4; ": "
0x14008a19d  lea     rcx, [rsp+2B0h+Src]; Src
0x14008a1a2  call    ??$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Append<wchar_t>(wchar_t const * const,unsigned __int64)
0x14008a1a7  movups  xmm0, xmmword ptr [rax]
0x14008a1aa  movups  [rsp+2B0h+var_258], xmm0
0x14008a1af  movups  xmm1, xmmword ptr [rax+10h]
0x14008a1b3  movups  [rsp+2B0h+var_248], xmm1
0x14008a1b8  mov     qword ptr [rax+10h], 0
0x14008a1c0  mov     qword ptr [rax+18h], 7
0x14008a1c8  xor     ecx, ecx
0x14008a1ca  mov     [rax], cx
0x14008a1cd  mov     r8, rbx
0x14008a1d0  lea     rdx, [rsp+2B0h+var_258]
0x14008a1d5  lea     rcx, [rbp+1B0h+var_1F0]
0x14008a1d9  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@0@Z; std::operator+<wchar_t>(std::wstring &&,std::wstring &&)
0x14008a1de  mov     rbx, rax
0x14008a1e1  xorps   xmm0, xmm0
0x14008a1e4  movups  [rbp+1B0h+var_1B0], xmm0
0x14008a1e8  xorps   xmm1, xmm1
0x14008a1eb  movdqu  xmmword ptr [rbp+10h], xmm1
0x14008a1f0  mov     r8d, 10h
0x14008a1f6  lea     rdx, aCscchangemanag; "CscChangeManager"
0x14008a1fd  lea     rcx, [rbp+1B0h+var_1B0]
0x14008a201  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x14008a206  nop
0x14008a207  cmp     qword ptr [rbx+18h], 7
0x14008a20c  jbe     short loc_14008A211
0x14008a20e  mov     rbx, [rbx]
0x14008a211  mov     r9, rbx
0x14008a214  lea     r8, [rbp+1B0h+var_1B0]
0x14008a218  mov     edx, r15d
0x14008a21b  mov     rcx, [rdi]
0x14008a21e  call    ?Write@LogImpl@Uev@@QEBAXW4UEV_LOG_LEVEL@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W@Z; Uev::LogImpl::Write(Uev::UEV_LOG_LEVEL,std::wstring const &,wchar_t const *)
0x14008a223  nop
0x14008a224  lea     rcx, [rbp+1B0h+var_1B0]
0x14008a228  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14008a22d  nop
0x14008a22e  lea     rcx, [rbp+1B0h+var_1F0]
0x14008a232  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14008a237  nop
0x14008a238  lea     rcx, [rsp+2B0h+var_258]
0x14008a23d  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14008a242  nop
0x14008a243  lea     rcx, [rsp+2B0h+Src]
0x14008a248  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14008a24d  nop
0x14008a24e  lea     rcx, [rbp+1B0h+pExceptionObject]
0x14008a252  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14008a257  xorps   xmm0, xmm0
0x14008a25a  movups  [rbp+1B0h+var_1B0], xmm0
0x14008a25e  xorps   xmm1, xmm1
0x14008a261  movdqu  xmmword ptr [rbp+10h], xmm1
0x14008a266  mov     r8d, 15h
0x14008a26c  lea     rdx, aRepositoryPath; "Repository path found"
0x14008a273  lea     rcx, [rbp+1B0h+var_1B0]
0x14008a277  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x14008a27c  nop
0x14008a27d  xorps   xmm0, xmm0
0x14008a280  movups  [rsp+2B0h+Src], xmm0
0x14008a285  xorps   xmm1, xmm1
0x14008a288  movdqu  [rsp+2B0h+var_268], xmm1
0x14008a28e  xor     r8d, r8d
0x14008a291  mov     rdx, r12
0x14008a294  lea     rcx, [rsp+2B0h+Src]
0x14008a299  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x14008a29e  nop
0x14008a29f  mov     [rsp+2B0h+var_290], r15d
0x14008a2a4  mov     r9d, 34h ; '4'
0x14008a2aa  lea     r8, [rbp+1B0h+var_1B0]
0x14008a2ae  lea     rdx, [rsp+2B0h+Src]
0x14008a2b3  lea     rcx, [rbp+1B0h+var_140]
0x14008a2b7  call    ??0UevHealthEvent@Uev@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0W4HealthEventOpcode@1@W4HealthEventLevel@1@@Z; Uev::UevHealthEvent::UevHealthEvent(std::wstring const &,std::wstring const &,Uev::HealthEventOpcode,Uev::HealthEventLevel)
0x14008a2bc  nop
0x14008a2bd  lea     rcx, [rsp+2B0h+Src]
0x14008a2c2  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14008a2c7  nop
0x14008a2c8  lea     rcx, [rbp+1B0h+var_1B0]
0x14008a2cc  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14008a2d1  lea     rcx, [rbp+1B0h+var_140]; this
0x14008a2d5  call    ?Send@UevIPC@Uev@@QEAAXXZ; Uev::UevIPC::Send(void)
0x14008a2da  nop
0x14008a2db  lea     rax, ??_7UevHealthEvent@Uev@@6B@; const Uev::UevHealthEvent::`vftable'
0x14008a2e2  mov     [rbp+1B0h+var_140], rax
0x14008a2e6  lea     rcx, [rbp+1B0h+var_E8]
0x14008a2ed  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14008a2f2  lea     rcx, [rbp+1B0h+var_108]
0x14008a2f9  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14008a2fe  lea     rcx, [rbp+1B0h+var_140]; this
0x14008a302  call    ??1UevIPC@Uev@@UEAA@XZ; Uev::UevIPC::~UevIPC(void)
0x14008a307  nop
0x14008a308  lea     rcx, [rbp+1B0h+var_160]
0x14008a30c  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14008a311  nop
0x14008a312  lea     rcx, [rbp+1B0h+var_180]
0x14008a316  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14008a31b  nop
0x14008a31c  lea     rcx, [rbp+1B0h+var_C0]; this
0x14008a323  call    ??1ScopeTracker@Uev@@UEAA@XZ; Uev::ScopeTracker::~ScopeTracker(void)
0x14008a328  nop
0x14008a329  mov     rax, rsi
0x14008a32c  mov     rcx, [rbp+1B0h+var_40]
0x14008a333  xor     rcx, rsp; StackCookie
0x14008a336  call    __security_check_cookie
0x14008a33b  add     rsp, 288h
0x14008a342  pop     r15
0x14008a344  pop     r12
0x14008a346  pop     rdi
0x14008a347  pop     rsi
0x14008a348  pop     rbx
0x14008a349  pop     rbp
0x14008a34a  retn
0x14008a34b  call    ?Instance@?$Singleton@VLog@Uev@@V12@@Uev@@SAPEAVLog@2@XZ; Uev::Singleton<Uev::Log,Uev::Log>::Instance(void)
0x14008a350  nop
0x14008a351  mov     esi, 8
0x14008a356  mov     edx, esi
0x14008a358  mov     rcx, rax
0x14008a35b  call    ?WriteEnabled@Log@Uev@@QEBA_NW4UEV_LOG_LEVEL@2@@Z; Uev::Log::WriteEnabled(Uev::UEV_LOG_LEVEL)
0x14008a360  test    al, al
0x14008a362  jz      short loc_14008A3E0
0x14008a364  call    ?Instance@?$Singleton@VLog@Uev@@V12@@Uev@@SAPEAVLog@2@XZ; Uev::Singleton<Uev::Log,Uev::Log>::Instance(void)
0x14008a369  mov     rdi, rax
0x14008a36c  call    cs:__imp_GetLastError
0x14008a372  mov     [rsp+2B0h+var_280], eax
0x14008a376  lea     rdx, [rsp+2B0h+var_280]
0x14008a37b  lea     rcx, [rbp+1B0h+var_1B0]
0x14008a37f  call    ??$lexical_cast@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@K@boost@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBK@Z; boost::lexical_cast<std::wstring,ulong>(ulong const &)
0x14008a384  nop
0x14008a385  mov     r8, rax
0x14008a388  lea     rdx, aRepositoryRepo_0; "Repository::Repository() - CreateWellKn"...
0x14008a38f  lea     rcx, [rsp+2B0h+Src]
0x14008a394  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@QEB_W$$QEAV10@@Z; std::operator+<wchar_t>(wchar_t const * const,std::wstring &&)
0x14008a399  mov     rbx, rax
0x14008a39c  lea     rdx, aCscchangemanag; "CscChangeManager"
0x14008a3a3  lea     rcx, [rsp+2B0h+var_258]
0x14008a3a8  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x14008a3ad  nop
0x14008a3ae  mov     r9, rbx
0x14008a3b1  lea     r8, [rsp+2B0h+var_258]
0x14008a3b6  mov     edx, esi
  ... truncated ...
```
