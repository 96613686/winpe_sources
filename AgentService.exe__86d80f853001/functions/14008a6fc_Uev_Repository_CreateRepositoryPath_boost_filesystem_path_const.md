# Uev::Repository::CreateRepositoryPath(boost::filesystem::path const &)

- ea: `0x14008a6fc`
- end: `0x14008ab33`
- name: `?CreateRepositoryPath@Repository@Uev@@QEAAJAEBVpath@filesystem@boost@@@Z`
- size: `1079`
- prototype: `int(Uev::Repository *__hidden this, const struct boost::filesystem::path *)`
- caller_count: `1`
- callee_count: `22`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x14008d380`

## callees

- `0x140003e50`
- `0x140005e60`
- `0x14000ba60`
- `0x14000bc7c`
- `0x14000c2b8`
- `0x14000d7b4`
- `0x140015190`
- `0x140020568`
- `0x1400205f4`
- `0x140020f6c`
- `0x1400380d4`
- `0x140046e04`
- `0x140046f94`
- `0x140047fa0`
- `0x14008a5dc`
- `0x14008a66c`
- `0x14008a6fc`
- `0x14008b730`
- `0x14008b878`
- `0x14008ba34`
- `0x14008cd48`
- `0x14008d0c8`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14008a840`
- `KERNEL32!GetLastError` at `0x14008a840`
- `KERNEL32!SetFileAttributesW` at `0x14008a836`
- `KERNEL32!SetFileAttributesW` at `0x14008a836`
- `KERNEL32!GetFileAttributesW` at `0x14008a763`
- `KERNEL32!GetFileAttributesW` at `0x14008a811`
- `KERNEL32!GetFileAttributesW` at `0x14008a763`
- `KERNEL32!GetFileAttributesW` at `0x14008a811`

## string_xrefs

- `0x14008a736`: `Repository::CreateRepositoryPath()`
- `0x14008a9bf`: `Failed to clear Active Directory settings storage path cache`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Uev::Repository::CreateRepositoryPath(Uev::Repository *this, const wchar_t *a2)
{
  const WCHAR *v4; // rcx
  DWORD FileAttributesW; // eax
  signed int v6; // esi
  Uev::Repository *v7; // rcx
  bool IsCurrentRepositoryPath; // bl
  char v9; // bl
  Uev::Repository *v10; // rcx
  _QWORD *v11; // r14
  Uev::Repository *v12; // rcx
  Uev::Repository *v13; // rcx
  unsigned int SettingsStoragePathAttributes; // ebx
  const WCHAR *v15; // rcx
  DWORD v16; // eax
  Uev::Repository *v17; // rcx
  const WCHAR *v18; // rcx
  signed int LastError; // eax
  __int64 v20; // r8
  __int64 v21; // rax
  int v22; // eax
  __int64 v23; // rbx
  __int64 v24; // rdx
  __int64 v25; // rcx
  _QWORD *v26; // rax
  _QWORD *v27; // rbx
  __int128 *v28; // r9
  __int128 *v29; // r14
  int v30; // edx
  int v31; // ecx
  __int128 *v32; // r9
  int v34; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v35; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v36; // [rsp+48h] [rbp-B8h]
  unsigned int v37; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v38; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v39[128]; // [rsp+70h] [rbp-90h] BYREF
  __int128 v40; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v41; // [rsp+100h] [rbp+0h]
  const wchar_t *v42; // [rsp+110h] [rbp+10h]
  int v43; // [rsp+118h] [rbp+18h]
  int v44; // [rsp+11Ch] [rbp+1Ch]
  int *v45; // [rsp+120h] [rbp+20h]
  __int64 v46; // [rsp+128h] [rbp+28h]

  v34 = 0;
  Uev::ScopeTracker::ScopeTracker((Uev::ScopeTracker *)v39, L"CscChangeManager", L"Repository::CreateRepositoryPath()");
  v38 = 0;
  if ( *((_QWORD *)a2 + 3) <= 7u )
    v4 = a2;
  else
    v4 = *(const WCHAR **)a2;
  FileAttributesW = GetFileAttributesW(v4);
  if ( FileAttributesW == -1 || (FileAttributesW & 0x10) == 0 )
  {
    v6 = -2147024894;
    Uev::Repository::ClearCurrentRepositoryPath((Uev::Repository *)0x80070002LL);
  }
  else
  {
    v6 = 0;
  }
  boost::filesystem::path::parent_path(a2, &v40);
  IsCurrentRepositoryPath = Uev::Repository::IsCurrentRepositoryPath(v7, (const struct boost::filesystem::path *)&v40);
  std::wstring::_Tidy_deallocate(&v40);
  if ( IsCurrentRepositoryPath )
    goto LABEL_57;
  boost::filesystem::path::parent_path(a2, &v40);
  v9 = 12;
  Uev::Repository::SetCurrentRepositoryPath(v10, (const struct boost::filesystem::path *)&v40);
  std::wstring::_Tidy_deallocate(&v40);
  v11 = (_QWORD *)((char *)this + 16);
  std::wstring::operator=((char *)this + 16, a2);
  if ( v6 == -2147024894 )
  {
    if ( Uev::Repository::CreateFolder(v12, (const struct boost::filesystem::path *)a2) )
    {
      SettingsStoragePathAttributes = Uev::Repository::GetSettingsStoragePathAttributes(v13);
      if ( *((_QWORD *)a2 + 3) <= 7u )
        v15 = a2;
      else
        v15 = *(const WCHAR **)a2;
      v16 = GetFileAttributesW(v15);
      if ( v16 == -1
        || (v6 = 0, (SettingsStoragePathAttributes | v16) != v16)
        && (*((_QWORD *)a2 + 3) <= 7u ? (v18 = a2) : (v18 = *(const WCHAR **)a2),
            !SetFileAttributesW(v18, SettingsStoragePathAttributes | v16)) )
      {
        LastError = GetLastError();
        v6 = LastError;
        if ( LastError > 0 )
          v6 = (unsigned __int16)LastError | 0x80070000;
      }
      if ( v6 < 0 && (Microsoft_User_Experience_Virtualization_App_AgentEnableBits & 0x10) != 0 )
      {
        if ( *((_QWORD *)a2 + 3) > 7u )
          a2 = *(const wchar_t **)a2;
        v37 = Uev::Repository::GetSettingsStoragePathAttributes(v17);
        v34 = v6;
        *(_QWORD *)&v41 = &v37;
        *((_QWORD *)&v41 + 1) = 4;
        if ( a2 )
        {
          v21 = -1;
          do
            ++v21;
          while ( a2[v21] );
          v22 = 2 * v21 + 2;
        }
        else
        {
          a2 = L"NULL";
          v22 = 10;
        }
        v42 = a2;
        v43 = v22;
        v44 = 0;
        v45 = &v34;
        v46 = 4;
        McGenEventWrite_EventWriteTransfer(
          UevAppAgentProvider_Context,
          ChangeManagerMsgAddAttributesFailed,
          v20,
          4,
          &v40);
      }
      goto LABEL_57;
    }
    v6 = -2147024893;
    if ( (Microsoft_User_Experience_Virtualization_App_AgentEnableBits & 0x10) != 0 )
    {
      if ( *((_QWORD *)a2 + 3) > 7u )
        a2 = *(const wchar_t **)a2;
      McTemplateU0zq_EventWriteTransfer(v13, ChangeManagerMsgNewRepositoryDirFailed, a2, 2147942403LL);
    }
    Uev::Repository::ClearCurrentRepositoryPath(v13);
    *((_QWORD *)this + 4) = 0;
    if ( *((_QWORD *)this + 5) > 7u )
      v11 = (_QWORD *)*v11;
    *(_WORD *)v11 = 0;
    v23 = Uev::Singleton<Uev::Configuration,Uev::Configuration>::Instance() + 18656;
    v35 = 0;
    v36 = 0;
    std::wstring::_Construct<1,wchar_t *>(&v35, &Data, 0);
    LOBYTE(v23) = Uev::Setting<std::wstring>::Set(v23, v24, &v35, &v38);
    std::wstring::_Tidy_deallocate(&v35);
    if ( !(_BYTE)v23 )
    {
      v26 = (_QWORD *)Uev::Singleton<Uev::Log,Uev::Log>::Instance(v25);
      if ( (*(_BYTE *)(*v26 + 32LL) & 8) != 0 )
      {
        v27 = (_QWORD *)Uev::Singleton<Uev::Log,Uev::Log>::Instance(*v26);
        v35 = 0;
        v36 = 0;
        std::wstring::_Construct<1,wchar_t *>(
          &v35,
          L"Failed to clear Active Directory settings storage path cache",
          0x3Cu);
        v40 = 0;
        v41 = 0;
        std::wstring::_Construct<1,wchar_t *>(&v40, L"CscChangeManager", 0x10u);
        v28 = &v35;
        if ( *((_QWORD *)&v36 + 1) > 7u )
          v28 = (__int128 *)v35;
        Uev::LogImpl::Write(*v27, 8, &v40, v28);
        std::wstring::_Tidy_deallocate(&v40);
LABEL_56:
        std::wstring::_Tidy_deallocate(&v35);
      }
    }
  }
  else if ( !*((_BYTE *)this + 8)
         && !Uev::Repository::IsFolderOwnerTheCurrentUser(v12, (const struct boost::filesystem::path *)a2) )
  {
    v6 = -2147023589;
    if ( (Microsoft_User_Experience_Virtualization_App_AgentEnableBits & 0x10) != 0 )
    {
      boost::filesystem::path::parent_path(a2, &v35);
      v34 = 29;
      v29 = &v35;
      if ( *((_QWORD *)&v36 + 1) > 7u )
        v29 = (__int128 *)v35;
      boost::filesystem::path::filename_v3(a2, &v40);
      v9 = 63;
      v32 = &v40;
      if ( *((_QWORD *)&v41 + 1) > 7u )
        LODWORD(v32) = v40;
      if ( *((_QWORD *)a2 + 3) > 7u )
        a2 = *(const wchar_t **)a2;
      McTemplateU0zzz_EventWriteTransfer(v31, v30, (_DWORD)a2, (_DWORD)v32, (__int64)v29);
    }
    if ( (v9 & 2) != 0 )
    {
      v9 &= ~2u;
      std::wstring::_Tidy_deallocate(&v40);
    }
    if ( (v9 & 1) != 0 )
      goto LABEL_56;
  }
LABEL_57:
  Uev::ScopeTracker::~ScopeTracker((Uev::ScopeTracker *)v39);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x14008a6fc  mov     [rsp-8+arg_10], rbx
0x14008a701  mov     [rsp-8+arg_18], rsi
0x14008a706  push    rbp
0x14008a707  push    rdi
0x14008a708  push    r12
0x14008a70a  push    r14
0x14008a70c  push    r15
0x14008a70e  lea     rbp, [rsp-40h]
0x14008a713  sub     rsp, 140h
0x14008a71a  mov     rax, cs:__security_cookie
0x14008a721  xor     rax, rsp
0x14008a724  mov     [rbp+60h+var_30], rax
0x14008a728  mov     rdi, rdx
0x14008a72b  mov     r15, rcx
0x14008a72e  xor     r12d, r12d
0x14008a731  mov     [rsp+160h+var_130], r12d
0x14008a736  lea     r8, aRepositoryCrea; "Repository::CreateRepositoryPath()"
0x14008a73d  lea     rdx, aCscchangemanag; "CscChangeManager"
0x14008a744  lea     rcx, [rsp+160h+var_F0]; this
0x14008a749  call    ??0ScopeTracker@Uev@@QEAA@PEB_W0@Z; Uev::ScopeTracker::ScopeTracker(wchar_t const *,wchar_t const *)
0x14008a74e  nop
0x14008a74f  mov     [rsp+160h+var_100], r12
0x14008a754  cmp     qword ptr [rdi+18h], 7
0x14008a759  jbe     short loc_14008A760
0x14008a75b  mov     rcx, [rdi]
0x14008a75e  jmp     short loc_14008A763
0x14008a760  mov     rcx, rdi; lpFileName
0x14008a763  call    cs:__imp_GetFileAttributesW
0x14008a769  mov     ecx, 80070002h; this
0x14008a76e  cmp     eax, 0FFFFFFFFh
0x14008a771  jz      short loc_14008A77C
0x14008a773  test    al, 10h
0x14008a775  jz      short loc_14008A77C
0x14008a777  mov     esi, r12d
0x14008a77a  jmp     short loc_14008A783
0x14008a77c  mov     esi, ecx
0x14008a77e  call    ?ClearCurrentRepositoryPath@Repository@Uev@@AEBAXXZ; Uev::Repository::ClearCurrentRepositoryPath(void)
0x14008a783  lea     rdx, [rbp+60h+var_70]
0x14008a787  mov     rcx, rdi
0x14008a78a  call    ?parent_path@path@filesystem@boost@@QEBA?AV123@XZ; boost::filesystem::path::parent_path(void)
0x14008a78f  nop
0x14008a790  lea     rdx, [rbp+60h+var_70]; struct boost::filesystem::path *
0x14008a794  call    ?IsCurrentRepositoryPath@Repository@Uev@@AEBA_NAEBVpath@filesystem@boost@@@Z; Uev::Repository::IsCurrentRepositoryPath(boost::filesystem::path const &)
0x14008a799  mov     bl, al
0x14008a79b  lea     rcx, [rbp+60h+var_70]
0x14008a79f  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14008a7a4  test    bl, bl
0x14008a7a6  jnz     loc_14008AAFF
0x14008a7ac  lea     rdx, [rbp+60h+var_70]
0x14008a7b0  mov     rcx, rdi
0x14008a7b3  call    ?parent_path@path@filesystem@boost@@QEBA?AV123@XZ; boost::filesystem::path::parent_path(void)
0x14008a7b8  mov     ebx, 0Ch
0x14008a7bd  lea     rdx, [rbp+60h+var_70]; struct boost::filesystem::path *
0x14008a7c1  call    ?SetCurrentRepositoryPath@Repository@Uev@@AEBAXAEBVpath@filesystem@boost@@@Z; Uev::Repository::SetCurrentRepositoryPath(boost::filesystem::path const &)
0x14008a7c6  nop
0x14008a7c7  lea     rcx, [rbp+60h+var_70]
0x14008a7cb  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14008a7d0  lea     r14, [r15+10h]
0x14008a7d4  mov     rdx, rdi
0x14008a7d7  mov     rcx, r14
0x14008a7da  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x14008a7df  cmp     esi, 80070002h
0x14008a7e5  jnz     loc_14008AA29
0x14008a7eb  mov     rdx, rdi; struct boost::filesystem::path *
0x14008a7ee  call    ?CreateFolder@Repository@Uev@@AEBA_NAEBVpath@filesystem@boost@@@Z; Uev::Repository::CreateFolder(boost::filesystem::path const &)
0x14008a7f3  test    al, al
0x14008a7f5  jz      loc_14008A8F5
0x14008a7fb  call    ?GetSettingsStoragePathAttributes@Repository@Uev@@AEBAKXZ; Uev::Repository::GetSettingsStoragePathAttributes(void)
0x14008a800  mov     ebx, eax
0x14008a802  cmp     qword ptr [rdi+18h], 7
0x14008a807  jbe     short loc_14008A80E
0x14008a809  mov     rcx, [rdi]
0x14008a80c  jmp     short loc_14008A811
0x14008a80e  mov     rcx, rdi; lpFileName
0x14008a811  call    cs:__imp_GetFileAttributesW
0x14008a817  cmp     eax, 0FFFFFFFFh
0x14008a81a  jz      short loc_14008A840
0x14008a81c  mov     esi, r12d
0x14008a81f  mov     edx, eax
0x14008a821  or      edx, ebx; dwFileAttributes
0x14008a823  cmp     edx, eax
0x14008a825  jz      short loc_14008A855
0x14008a827  cmp     qword ptr [rdi+18h], 7
0x14008a82c  jbe     short loc_14008A833
0x14008a82e  mov     rcx, [rdi]
0x14008a831  jmp     short loc_14008A836
0x14008a833  mov     rcx, rdi; lpFileName
0x14008a836  call    cs:__imp_SetFileAttributesW
0x14008a83c  test    eax, eax
0x14008a83e  jnz     short loc_14008A855
0x14008a840  call    cs:__imp_GetLastError
0x14008a846  test    eax, eax
0x14008a848  mov     esi, eax
0x14008a84a  jle     short loc_14008A855
0x14008a84c  movzx   esi, ax
0x14008a84f  or      esi, 80070000h
0x14008a855  test    esi, esi
0x14008a857  jns     loc_14008AAFF
0x14008a85d  test    cs:Microsoft_User_Experience_Virtualization_App_AgentEnableBits, 10h
0x14008a864  jz      loc_14008AAFF
0x14008a86a  cmp     qword ptr [rdi+18h], 7
0x14008a86f  jbe     short loc_14008A874
0x14008a871  mov     rdi, [rdi]
0x14008a874  call    ?GetSettingsStoragePathAttributes@Repository@Uev@@AEBAKXZ; Uev::Repository::GetSettingsStoragePathAttributes(void)
0x14008a879  mov     [rsp+160h+var_108], eax
0x14008a87d  mov     [rsp+160h+var_130], esi
0x14008a881  lea     rax, [rsp+160h+var_108]
0x14008a886  mov     qword ptr [rbp+60h+var_60], rax
0x14008a88a  mov     r9d, 4
0x14008a890  mov     qword ptr [rbp+60h+var_60+8], r9
0x14008a894  test    rdi, rdi
0x14008a897  jz      short loc_14008A8B0
0x14008a899  or      rax, 0FFFFFFFFFFFFFFFFh
0x14008a89d  inc     rax
0x14008a8a0  cmp     [rdi+rax*2], r12w
0x14008a8a5  jnz     short loc_14008A89D
0x14008a8a7  lea     eax, ds:2[rax*2]
0x14008a8ae  jmp     short loc_14008A8BC
0x14008a8b0  lea     rdi, aNull_0; "NULL"
0x14008a8b7  mov     eax, 0Ah
0x14008a8bc  mov     [rbp+60h+var_50], rdi
0x14008a8c0  mov     [rbp+60h+var_48], eax
0x14008a8c3  mov     [rbp+60h+var_44], r12d
0x14008a8c7  lea     rax, [rsp+160h+var_130]
0x14008a8cc  mov     [rbp+60h+var_40], rax
0x14008a8d0  mov     [rbp+60h+var_38], r9
0x14008a8d4  lea     rax, [rbp+60h+var_70]
0x14008a8d8  mov     [rsp+160h+var_140], rax
0x14008a8dd  lea     rdx, ChangeManagerMsgAddAttributesFailed
0x14008a8e4  lea     rcx, UevAppAgentProvider_Context
0x14008a8eb  call    McGenEventWrite_EventWriteTransfer
0x14008a8f0  jmp     loc_14008AAFF
0x14008a8f5  mov     esi, 80070003h
0x14008a8fa  test    cs:Microsoft_User_Experience_Virtualization_App_AgentEnableBits, 10h
0x14008a901  jz      short loc_14008A91F
0x14008a903  cmp     qword ptr [rdi+18h], 7
0x14008a908  jbe     short loc_14008A90D
0x14008a90a  mov     rdi, [rdi]
0x14008a90d  mov     r9d, esi
0x14008a910  mov     r8, rdi
0x14008a913  lea     rdx, ChangeManagerMsgNewRepositoryDirFailed
0x14008a91a  call    McTemplateU0zq_EventWriteTransfer
0x14008a91f  call    ?ClearCurrentRepositoryPath@Repository@Uev@@AEBAXXZ; Uev::Repository::ClearCurrentRepositoryPath(void)
0x14008a924  mov     [r14+10h], r12
0x14008a928  cmp     qword ptr [r14+18h], 7
0x14008a92d  jbe     short loc_14008A932
0x14008a92f  mov     r14, [r14]
0x14008a932  mov     [r14], r12w
0x14008a936  call    ?Instance@?$Singleton@VConfiguration@Uev@@V12@@Uev@@SAPEAVConfiguration@2@XZ; Uev::Singleton<Uev::Configuration,Uev::Configuration>::Instance(void)
0x14008a93b  lea     rbx, [rax+48E0h]
0x14008a942  xorps   xmm0, xmm0
0x14008a945  movups  [rsp+160h+var_128], xmm0
0x14008a94a  xorps   xmm1, xmm1
0x14008a94d  movdqu  [rsp+160h+var_118], xmm1
0x14008a953  xor     r8d, r8d
0x14008a956  lea     rdx, Data
0x14008a95d  lea     rcx, [rsp+160h+var_128]
0x14008a962  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x14008a967  nop
0x14008a968  lea     r9, [rsp+160h+var_100]
0x14008a96d  lea     r8, [rsp+160h+var_128]
0x14008a972  mov     rcx, rbx
0x14008a975  call    ?Set@?$Setting@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Uev@@QEAA_NW4SettingSource@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAUSettingInfo@2@@Z; Uev::Setting<std::wstring>::Set(Uev::SettingSource,std::wstring const &,Uev::SettingInfo &)
0x14008a97a  mov     bl, al
0x14008a97c  lea     rcx, [rsp+160h+var_128]
0x14008a981  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14008a986  test    bl, bl
0x14008a988  jnz     loc_14008AAFF
0x14008a98e  call    ?Instance@?$Singleton@VLog@Uev@@V12@@Uev@@SAPEAVLog@2@XZ; Uev::Singleton<Uev::Log,Uev::Log>::Instance(void)
0x14008a993  mov     rcx, [rax]
0x14008a996  test    byte ptr [rcx+20h], 8
0x14008a99a  jbe     loc_14008AAFF
0x14008a9a0  call    ?Instance@?$Singleton@VLog@Uev@@V12@@Uev@@SAPEAVLog@2@XZ; Uev::Singleton<Uev::Log,Uev::Log>::Instance(void)
0x14008a9a5  mov     rbx, rax
0x14008a9a8  xorps   xmm0, xmm0
0x14008a9ab  movups  [rsp+160h+var_128], xmm0
0x14008a9b0  xorps   xmm1, xmm1
0x14008a9b3  movdqu  [rsp+160h+var_118], xmm1
0x14008a9b9  mov     r8d, 3Ch ; '<'
0x14008a9bf  lea     rdx, aFailedToClearA; "Failed to clear Active Directory settin"...
0x14008a9c6  lea     rcx, [rsp+160h+var_128]
0x14008a9cb  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x14008a9d0  nop
0x14008a9d1  xorps   xmm0, xmm0
0x14008a9d4  movups  [rbp+60h+var_70], xmm0
0x14008a9d8  xorps   xmm1, xmm1
0x14008a9db  movdqu  [rbp+60h+var_60], xmm1
0x14008a9e0  mov     r8d, 10h
0x14008a9e6  lea     rdx, aCscchangemanag; "CscChangeManager"
0x14008a9ed  lea     rcx, [rbp+60h+var_70]
0x14008a9f1  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x14008a9f6  nop
0x14008a9f7  lea     r9, [rsp+160h+var_128]
0x14008a9fc  cmp     qword ptr [rsp+160h+var_118+8], 7
0x14008aa02  cmova   r9, qword ptr [rsp+160h+var_128]
0x14008aa08  lea     r8, [rbp+60h+var_70]
0x14008aa0c  mov     edx, 8
0x14008aa11  mov     rcx, [rbx]
0x14008aa14  call    ?Write@LogImpl@Uev@@QEBAXW4UEV_LOG_LEVEL@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W@Z; Uev::LogImpl::Write(Uev::UEV_LOG_LEVEL,std::wstring const &,wchar_t const *)
0x14008aa19  nop
0x14008aa1a  lea     rcx, [rbp+60h+var_70]
0x14008aa1e  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14008aa23  nop
0x14008aa24  jmp     loc_14008AACD
0x14008aa29  test    esi, esi
0x14008aa2b  js      loc_14008AAD9
0x14008aa31  cmp     [r15+8], r12b
0x14008aa35  jnz     loc_14008AAFF
0x14008aa3b  mov     rdx, rdi; struct boost::filesystem::path *
0x14008aa3e  call    ?IsFolderOwnerTheCurrentUser@Repository@Uev@@AEBA_NAEBVpath@filesystem@boost@@@Z; Uev::Repository::IsFolderOwnerTheCurrentUser(boost::filesystem::path const &)
0x14008aa43  test    al, al
0x14008aa45  jnz     loc_14008AAFF
0x14008aa4b  mov     esi, 8007051Bh
0x14008aa50  test    cs:Microsoft_User_Experience_Virtualization_App_AgentEnableBits, 10h
0x14008aa57  jz      short loc_14008AAB6
0x14008aa59  lea     rdx, [rsp+160h+var_128]
0x14008aa5e  mov     rcx, rdi
0x14008aa61  call    ?parent_path@path@filesystem@boost@@QEBA?AV123@XZ; boost::filesystem::path::parent_path(void)
0x14008aa66  nop
0x14008aa67  mov     [rsp+160h+var_130], 1Dh
0x14008aa6f  lea     r14, [rsp+160h+var_128]
0x14008aa74  cmp     qword ptr [rsp+160h+var_118+8], 7
0x14008aa7a  cmova   r14, qword ptr [rsp+160h+var_128]
0x14008aa80  lea     rdx, [rbp+60h+var_70]
0x14008aa84  mov     rcx, rdi
0x14008aa87  call    ?filename_v3@path@filesystem@boost@@AEBA?AV123@XZ; boost::filesystem::path::filename_v3(void)
0x14008aa8c  mov     ebx, 3Fh ; '?'
0x14008aa91  lea     r9, [rbp+60h+var_70]
0x14008aa95  cmp     qword ptr [rbp+60h+var_60+8], 7
0x14008aa9a  cmova   r9, qword ptr [rbp+60h+var_70]
0x14008aa9f  cmp     qword ptr [rdi+18h], 7
0x14008aaa4  jbe     short loc_14008AAA9
0x14008aaa6  mov     rdi, [rdi]
0x14008aaa9  mov     [rsp+160h+var_140], r14
0x14008aaae  mov     r8, rdi
0x14008aab1  call    McTemplateU0zzz_EventWriteTransfer
0x14008aab6  test    bl, 2
0x14008aab9  jz      short loc_14008AAC8
0x14008aabb  and     ebx, 0FFFFFFFDh
0x14008aabe  lea     rcx, [rbp+60h+var_70]
0x14008aac2  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14008aac7  nop
0x14008aac8  test    bl, 1
0x14008aacb  jz      short loc_14008AAFF
0x14008aacd  lea     rcx, [rsp+160h+var_128]
0x14008aad2  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14008aad7  jmp     short loc_14008AAFF
0x14008aad9  test    cs:Microsoft_User_Experience_Virtualization_App_AgentEnableBits, 10h
0x14008aae0  jz      short loc_14008AAFF
0x14008aae2  cmp     qword ptr [rdi+18h], 7
0x14008aae7  jbe     short loc_14008AAEC
0x14008aae9  mov     rdi, [rdi]
0x14008aaec  mov     r9d, esi
0x14008aaef  mov     r8, rdi
0x14008aaf2  lea     rdx, ChangeManagerMsgNewRepositoryDirFailed
0x14008aaf9  call    McTemplateU0zq_EventWriteTransfer
0x14008aafe  nop
0x14008aaff  lea     rcx, [rsp+160h+var_F0]; this
0x14008ab04  call    ??1ScopeTracker@Uev@@UEAA@XZ; Uev::ScopeTracker::~ScopeTracker(void)
0x14008ab09  mov     eax, esi
0x14008ab0b  mov     rcx, [rbp+60h+var_30]
0x14008ab0f  xor     rcx, rsp; StackCookie
0x14008ab12  call    __security_check_cookie
0x14008ab17  lea     r11, [rsp+160h+var_20]
0x14008ab1f  mov     rbx, [r11+40h]
0x14008ab23  mov     rsi, [r11+48h]
0x14008ab27  mov     rsp, r11
0x14008ab2a  pop     r15
0x14008ab2c  pop     r14
0x14008ab2e  pop     r12
0x14008ab30  pop     rdi
0x14008ab31  pop     rbp
0x14008ab32  retn
```
