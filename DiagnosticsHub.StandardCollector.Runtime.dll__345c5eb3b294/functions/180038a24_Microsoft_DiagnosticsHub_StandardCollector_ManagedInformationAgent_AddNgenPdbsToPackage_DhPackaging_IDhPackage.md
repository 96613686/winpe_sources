# Microsoft::DiagnosticsHub::StandardCollector::ManagedInformationAgent::AddNgenPdbsToPackage(DhPackaging::IDhPackage *)

- ea: `0x180038a24`
- end: `0x180038f46`
- name: `?AddNgenPdbsToPackage@ManagedInformationAgent@StandardCollector@DiagnosticsHub@Microsoft@@AEAAXPEAUIDhPackage@DhPackaging@@@Z`
- size: `1314`
- prototype: `void __fastcall(Microsoft::DiagnosticsHub::StandardCollector::ManagedInformationAgent *__hidden this, struct DhPackaging::IDhPackage *)`
- caller_count: `1`
- callee_count: `17`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180037f10`

## callees

- `0x1800021fc`
- `0x180002604`
- `0x18000288c`
- `0x180009d1c`
- `0x180038a24`
- `0x180039824`
- `0x1800398a4`
- `0x18003a138`
- `0x18003acac`
- `0x18003b61c`
- `0x18003bef8`
- `0x18003d864`
- `0x18004106c`
- `0x180041618`
- `0x180049b50`
- `0x18004b2a0`
- `0x18004b640`

## import_xrefs

- `KERNEL32!CompareStringOrdinal` at `0x180038ba2`
- `KERNEL32!CompareStringOrdinal` at `0x180038bca`
- `KERNEL32!CompareStringOrdinal` at `0x180038ba2`
- `KERNEL32!CompareStringOrdinal` at `0x180038bca`
- `KERNEL32!ReleaseSRWLockShared` at `0x180038b62`
- `KERNEL32!ReleaseSRWLockShared` at `0x180038c19`
- `KERNEL32!ReleaseSRWLockShared` at `0x180038b62`
- `KERNEL32!ReleaseSRWLockShared` at `0x180038c19`
- `KERNEL32!AcquireSRWLockShared` at `0x180038b09`
- `KERNEL32!AcquireSRWLockShared` at `0x180038b09`
- `KERNEL32!LeaveCriticalSection` at `0x180038f0e`
- `KERNEL32!LeaveCriticalSection` at `0x180038f0e`
- `KERNEL32!EnterCriticalSection` at `0x180038a63`
- `KERNEL32!EnterCriticalSection` at `0x180038a63`
- `SHLWAPI!PathFindExtensionW` at `0x180038b80`
- `SHLWAPI!PathFindExtensionW` at `0x180038b80`

## string_xrefs

- `0x180038ec4`: `DiagnosticsHub.Resource.SymbolCache`
- `0x180038b52`: `D:\a\_work\1\s\sources\Base\Collection\StandardCollector.Runtime\ManagedInformationAgent.cpp`
- `0x180038c05`: `D:\a\_work\1\s\sources\Base\Collection\StandardCollector.Runtime\ManagedInformationAgent.cpp`
- `0x180038cf4`: `D:\a\_work\1\s\sources\Base\Collection\StandardCollector.Runtime\ManagedInformationAgent.cpp`
- `0x180038e37`: `D:\a\_work\1\s\sources\Base\Collection\StandardCollector.Runtime\ManagedInformationAgent.cpp`
- `0x180038e55`: `D:\a\_work\1\s\sources\Base\Collection\StandardCollector.Runtime\ManagedInformationAgent.cpp`
- `0x180038e73`: `D:\a\_work\1\s\sources\Base\Collection\StandardCollector.Runtime\ManagedInformationAgent.cpp`
- `0x180038bfe`: `Attempted to add ngen module to package that isn't a dll or exe: %s`
- `0x180038e30`: `Creating pdbs from native image files using ngen and using the ngen cache took %d ms`
- `0x180038e4e`: `Created %d pdbs from native image files using ngen`
- `0x180038e6c`: `Used the cache to get %d ngen pdbs instead of creating them`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall Microsoft::DiagnosticsHub::StandardCollector::ManagedInformationAgent::AddNgenPdbsToPackage(
        Microsoft::DiagnosticsHub::StandardCollector::ManagedInformationAgent *this,
        struct DhPackaging::IDhPackage *a2)
{
  struct DhPackaging::IDhPackage *v2; // rsi
  struct _RTL_CRITICAL_SECTION *v4; // rdi
  const unsigned __int16 *v5; // rdx
  bool v6; // r8
  int Directory; // eax
  const unsigned __int16 *v8; // rdx
  _QWORD *v9; // rbx
  _QWORD *v10; // rax
  const WCHAR **v11; // r14
  _QWORD *v12; // r12
  __int64 *v13; // rax
  __int64 v14; // r13
  const WCHAR *v15; // rcx
  const WCHAR *ExtensionW; // rsi
  _QWORD *v17; // r12
  _QWORD *v18; // rcx
  unsigned __int64 v19; // r9
  _QWORD *v20; // r8
  unsigned __int64 v21; // rdx
  _QWORD *v22; // rax
  char *v23; // rsi
  __int64 v24; // rax
  __int64 v25; // rax
  __int64 v26; // rsi
  struct ATL::IAtlStringMgr *Instance; // rax
  void (__fastcall *v28)(struct DhPackaging::IDhPackage *, const wchar_t *, _QWORD, _QWORD, int, _QWORD); // rbx
  __int64 v29; // rdx
  _QWORD *v30; // rdx
  _QWORD *v31; // [rsp+40h] [rbp-59h]
  _QWORD *v32; // [rsp+48h] [rbp-51h] BYREF
  struct DhPackaging::IDhPackage *v33; // [rsp+50h] [rbp-49h] BYREF
  _QWORD *v34; // [rsp+58h] [rbp-41h]
  _QWORD *v35; // [rsp+60h] [rbp-39h]
  _QWORD v36[2]; // [rsp+68h] [rbp-31h] BYREF
  char v37[8]; // [rsp+78h] [rbp-21h] BYREF
  char *v38; // [rsp+80h] [rbp-19h]
  int v39; // [rsp+88h] [rbp-11h]
  unsigned int v40; // [rsp+90h] [rbp-9h] BYREF
  unsigned int v41; // [rsp+94h] [rbp-5h] BYREF
  __int64 v42; // [rsp+98h] [rbp-1h] BYREF
  __int128 v43; // [rsp+A0h] [rbp+7h] BYREF
  __int64 v44; // [rsp+B0h] [rbp+17h]

  v2 = a2;
  v33 = a2;
  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 24);
  v36[1] = (char *)this + 24;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  if ( !*((_BYTE *)this + 112) )
    goto LABEL_58;
  *((_BYTE *)this + 112) = 0;
  Directory = DiagHubCommon::DeleteDirectory(*((DiagHubCommon **)this + 56), v5, v6);
  if ( !Directory || Directory == -2147024893 )
    Directory = DiagHubCommon::VerifyOrCreateDirectory(*((DiagHubCommon **)this + 56), v8);
  if ( Directory < 0 )
    goto LABEL_58;
  std::chrono::steady_clock::now(v36);
  v43 = 0;
  v44 = 0;
  v31 = (_QWORD *)*((_QWORD *)this + 17);
  v9 = (_QWORD *)*v31;
  if ( (_QWORD *)*v31 == v31 )
    goto LABEL_47;
  v10 = (_QWORD *)*((_QWORD *)this + 17);
  do
  {
    v11 = (const WCHAR **)(v9 + 3);
    if ( *((_BYTE *)v9 + 73) )
      goto LABEL_45;
    *((_BYTE *)v9 + 73) = 1;
    v12 = (_QWORD *)v9[7];
    v35 = v12;
    v32 = v12;
    v38 = (char *)this + 104;
    v39 = 0;
    AcquireSRWLockShared((PSRWLOCK)this + 13);
    v13 = (__int64 *)std::_Hash<std::_Umap_traits<unsigned __int64,Microsoft::DiagnosticsHub::StandardCollector::ManagedInformationAgent::AssemblyDetails,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,Microsoft::DiagnosticsHub::StandardCollector::ManagedInformationAgent::AssemblyDetails>>,0>>::find(
                       (char *)this + 256,
                       v37,
                       &v32);
    v14 = *v13;
    if ( *v13 == *((_QWORD *)this + 33) )
    {
      if ( *((_QWORD *)_logger + 7) != *((_QWORD *)_logger + 8) )
        DiagHubCommon::LogStream::Write(
          (DiagHubCommon::LogStream *)((char *)_logger + 56),
          L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\ManagedInformationAgent.cpp",
          L"Assembly ID not found: %#08x",
          v12);
      ReleaseSRWLockShared((PSRWLOCK)this + 13);
LABEL_13:
      if ( v9[5] )
      {
        v15 = (const WCHAR *)(v9 + 3);
        if ( v9[6] > 7u )
          v15 = *v11;
        ExtensionW = PathFindExtensionW(v15);
        if ( CompareStringOrdinal(ExtensionW, -1, L".dll", -1, 1) == 2
          || CompareStringOrdinal(ExtensionW, -1, L".exe", -1, 1) == 2 )
        {
          v26 = *((_QWORD *)&v43 + 1);
          if ( *((_QWORD *)&v43 + 1) == v44 )
          {
            std::vector<Microsoft::DiagnosticsHub::StandardCollector::NgenSymbolHelper::ModuleDetails>::_Emplace_reallocate<Microsoft::DiagnosticsHub::StandardCollector::NgenSymbolHelper::ModuleDetails const &>(
              &v43,
              *((_QWORD *)&v43 + 1),
              v9 + 3);
          }
          else
          {
            std::wstring::wstring(*((_QWORD *)&v43 + 1), v9 + 3);
            *(_QWORD *)(v26 + 32) = v9[7];
            *(_QWORD *)(v26 + 40) = v9[8];
            *(_BYTE *)(v26 + 48) = *((_BYTE *)v9 + 72);
            *(_BYTE *)(v26 + 49) = *((_BYTE *)v9 + 73);
            *((_QWORD *)&v43 + 1) += 56LL;
          }
        }
        else if ( *((_QWORD *)_logger + 14) != *((_QWORD *)_logger + 15) )
        {
          if ( v9[6] > 7u )
            v11 = (const WCHAR **)*v11;
          DiagHubCommon::LogStream::Write(
            (DiagHubCommon::LogStream *)((char *)_logger + 112),
            L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\ManagedInformationAgent.cpp",
            L"Attempted to add ngen module to package that isn't a dll or exe: %s",
            v11);
        }
      }
      goto LABEL_44;
    }
    ReleaseSRWLockShared((PSRWLOCK)this + 13);
    v17 = (_QWORD *)*((_QWORD *)this + 40);
    v34 = (_QWORD *)*((_QWORD *)this + 41);
    if ( v17 == v34 )
      goto LABEL_13;
    v18 = (_QWORD *)(v14 + 40);
    while ( 1 )
    {
      v19 = v17[2];
      v20 = v17;
      if ( v17[3] > 7u )
        v20 = (_QWORD *)*v17;
      v21 = v18[2];
      v22 = v18;
      v32 = v18;
      if ( v18[3] > 7u )
      {
        v22 = (_QWORD *)*v18;
        v32 = (_QWORD *)*v18;
      }
      if ( v19 > v21 )
        goto LABEL_33;
      if ( !v19 )
        break;
      _mm_lfence();
      v23 = (char *)v22 + 2 * v21;
      v24 = _std_search_2(v22, v23, v20);
      if ( (char *)v24 != v23 && (v24 - (__int64)v32) >> 1 != -1 )
        break;
      v18 = (_QWORD *)(v14 + 40);
LABEL_33:
      v17 += 4;
      if ( v17 == v34 )
        goto LABEL_13;
    }
    if ( *((_QWORD *)_logger + 7) != *((_QWORD *)_logger + 8) )
    {
      if ( v17[3] > 7u )
        v17 = (_QWORD *)*v17;
      v25 = v14 + 40;
      if ( *(_QWORD *)(v14 + 64) > 7u )
        v25 = *(_QWORD *)(v14 + 40);
      DiagHubCommon::LogStream::Write(
        (DiagHubCommon::LogStream *)((char *)_logger + 56),
        L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\ManagedInformationAgent.cpp",
        L"Assembly ID %#08x filtered out: '%s' by '%s'",
        v35,
        v25,
        v17);
    }
LABEL_44:
    v10 = v31;
LABEL_45:
    v9 = (_QWORD *)*v9;
  }
  while ( v9 != v10 );
  v2 = v33;
LABEL_47:
  if ( (_QWORD)v43 != *((_QWORD *)&v43 + 1) )
  {
    v42 = 0;
    Instance = ATL::CAtlStringMgr::GetInstance();
    if ( !Instance )
      ATL::AtlThrowImpl(-2147467259);
    v42 = (*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)Instance + 24LL))(Instance) + 24;
    Microsoft::DiagnosticsHub::StandardCollector::NgenSymbolHelper::GetSymbolCachePath((Microsoft::DiagnosticsHub::StandardCollector::ManagedInformationAgent *)((char *)this + 344));
    v40 = 0;
    v41 = 0;
    if ( (int)Microsoft::DiagnosticsHub::StandardCollector::NgenSymbolHelper::AddNgenPdbsToScratchDir(
                (int)this + 344,
                (unsigned int)&v43,
                (int)this + 448,
                (unsigned int)&v42,
                (__int64)&v40,
                (__int64)&v41) >= 0 )
    {
      _mm_lfence();
      if ( *(_QWORD *)_logger != *((_QWORD *)_logger + 1) )
      {
        std::chrono::steady_clock::now(&v33);
        DiagHubCommon::LogStream::Write(
          _logger,
          L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\ManagedInformationAgent.cpp",
          L"Creating pdbs from native image files using ngen and using the ngen cache took %d ms",
          ((__int64)v33 - v36[0]) / 1000000);
        DiagHubCommon::LogStream::Write(
          _logger,
          L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\ManagedInformationAgent.cpp",
          L"Created %d pdbs from native image files using ngen",
          v40);
        DiagHubCommon::LogStream::Write(
          _logger,
          L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\ManagedInformationAgent.cpp",
          L"Used the cache to get %d ngen pdbs instead of creating them",
          v41);
      }
      v28 = *(void (__fastcall **)(struct DhPackaging::IDhPackage *, const wchar_t *, _QWORD, _QWORD, int, _QWORD))(*(_QWORD *)v2 + 64LL);
      v29 = *((_QWORD *)this + 56);
      if ( *(int *)(v29 - 8) > 1 )
        ATL::CSimpleStringT<unsigned short,0>::Fork((char *)this + 448, *(unsigned int *)(v29 - 16));
      v28(v2, L"DiagnosticsHub.Resource.SymbolCache", *((_QWORD *)this + 56), 0, 1, 0);
    }
    v30 = (_QWORD *)(v42 - 24);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v42 - 24 + 16), 0xFFFFFFFF) <= 1 )
    {
      _mm_lfence();
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v30 + 8LL))(*v30);
    }
  }
  std::vector<Microsoft::DiagnosticsHub::StandardCollector::NgenSymbolHelper::ModuleDetails>::~vector<Microsoft::DiagnosticsHub::StandardCollector::NgenSymbolHelper::ModuleDetails>(&v43);
LABEL_58:
  LeaveCriticalSection(v4);
}

```

## disassembly

```asm
0x180038a24  mov     [rsp-8+arg_10], rbx
0x180038a29  push    rbp
0x180038a2a  push    rsi
0x180038a2b  push    rdi
0x180038a2c  push    r12
0x180038a2e  push    r13
0x180038a30  push    r14
0x180038a32  push    r15
0x180038a34  lea     rbp, [rsp-27h]
0x180038a39  sub     rsp, 0C0h
0x180038a40  mov     rax, cs:__security_cookie
0x180038a47  xor     rax, rsp
0x180038a4a  mov     [rbp+57h+var_38], rax
0x180038a4e  mov     rsi, rdx
0x180038a51  mov     [rbp+57h+var_A0], rdx
0x180038a55  mov     r15, rcx
0x180038a58  lea     rdi, [rcx+18h]
0x180038a5c  mov     [rbp+57h+var_80], rdi
0x180038a60  mov     rcx, rdi; lpCriticalSection
0x180038a63  call    cs:__imp_EnterCriticalSection
0x180038a69  nop
0x180038a6a  mov     al, [r15+70h]
0x180038a6e  test    al, al
0x180038a70  jz      loc_180038F0B
0x180038a76  xor     eax, eax
0x180038a78  xchg    al, [r15+70h]
0x180038a7c  mov     rcx, [r15+1C0h]; this
0x180038a83  call    ?DeleteDirectory@DiagHubCommon@@YAJPEBG_N@Z; DiagHubCommon::DeleteDirectory(ushort const *,bool)
0x180038a88  test    eax, eax
0x180038a8a  jz      short loc_180038A93
0x180038a8c  cmp     eax, 80070003h
0x180038a91  jnz     short loc_180038A9F
0x180038a93  mov     rcx, [r15+1C0h]; this
0x180038a9a  call    ?VerifyOrCreateDirectory@DiagHubCommon@@YAJPEBG@Z; DiagHubCommon::VerifyOrCreateDirectory(ushort const *)
0x180038a9f  test    eax, eax
0x180038aa1  js      loc_180038F0B
0x180038aa7  lea     rcx, [rbp+57h+var_88]
0x180038aab  call    ?now@steady_clock@chrono@std@@SA?AV?$time_point@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@23@XZ; std::chrono::steady_clock::now(void)
0x180038ab0  xor     eax, eax
0x180038ab2  xorps   xmm1, xmm1
0x180038ab5  movdqu  [rbp+57h+var_50], xmm1
0x180038aba  mov     [rbp+57h+var_40], rax
0x180038abe  mov     r14, [r15+88h]
0x180038ac5  mov     [rbp+57h+var_B0], r14
0x180038ac9  mov     rbx, [r14]
0x180038acc  cmp     rbx, r14
0x180038acf  jz      loc_180038D5F
0x180038ad5  mov     rax, r14
0x180038ad8  lea     r14, [rbx+18h]
0x180038adc  cmp     byte ptr [rbx+49h], 0
0x180038ae0  jnz     loc_180038D4F
0x180038ae6  mov     byte ptr [r14+31h], 1
0x180038aeb  mov     r12, [r14+20h]
0x180038aef  mov     [rbp+57h+var_90], r12
0x180038af3  mov     [rbp+57h+var_A8], r12
0x180038af7  lea     rsi, [r15+68h]
0x180038afb  mov     [rbp+57h+var_70], rsi
0x180038aff  mov     [rbp+57h+var_68], 0
0x180038b06  mov     rcx, rsi; SRWLock
0x180038b09  call    cs:__imp_AcquireSRWLockShared
0x180038b0f  nop
0x180038b10  lea     rcx, [r15+100h]
0x180038b17  lea     r8, [rbp+57h+var_A8]
0x180038b1b  lea     rdx, [rbp+57h+var_78]
0x180038b1f  call    ?find@?$_Hash@V?$_Umap_traits@_KUAssemblyDetails@ManagedInformationAgent@StandardCollector@DiagnosticsHub@Microsoft@@V?$_Uhash_compare@_KU?$hash@_K@std@@U?$equal_to@_K@2@@std@@V?$allocator@U?$pair@$$CB_KUAssemblyDetails@ManagedInformationAgent@StandardCollector@DiagnosticsHub@Microsoft@@@std@@@7@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CB_KUAssemblyDetails@ManagedInformationAgent@StandardCollector@DiagnosticsHub@Microsoft@@@std@@@std@@@std@@@2@AEB_K@Z; std::_Hash<std::_Umap_traits<unsigned __int64,Microsoft::DiagnosticsHub::StandardCollector::ManagedInformationAgent::AssemblyDetails,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,Microsoft::DiagnosticsHub::StandardCollector::ManagedInformationAgent::AssemblyDetails>>,0>>::find(unsigned __int64 const &)
0x180038b24  mov     r13, [rax]
0x180038b27  cmp     r13, [r15+108h]
0x180038b2e  jnz     loc_180038C16
0x180038b34  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x180038b3b  add     rcx, 38h ; '8'; this
0x180038b3f  mov     rax, [rcx+8]
0x180038b43  cmp     [rcx], rax
0x180038b46  jz      short loc_180038B5F
0x180038b48  mov     r9, r12
0x180038b4b  lea     r8, aAssemblyIdNotF; "Assembly ID not found: %#08x"
0x180038b52  lea     rdx, aDAWork1SSource_1; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x180038b59  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x180038b5e  nop
0x180038b5f  mov     rcx, rsi; SRWLock
0x180038b62  call    cs:__imp_ReleaseSRWLockShared
0x180038b68  cmp     qword ptr [r14+10h], 0
0x180038b6d  jz      loc_180038D4B
0x180038b73  mov     rcx, r14
0x180038b76  cmp     qword ptr [r14+18h], 7
0x180038b7b  jbe     short loc_180038B80
0x180038b7d  mov     rcx, [r14]; pszPath
0x180038b80  call    cs:__imp_PathFindExtensionW
0x180038b86  mov     rsi, rax
0x180038b89  mov     [rsp+0F0h+bIgnoreCase], 1; bIgnoreCase
0x180038b91  or      r9d, 0FFFFFFFFh; cchCount2
0x180038b95  lea     r8, aDll_0; ".dll"
0x180038b9c  or      edx, r9d; cchCount1
0x180038b9f  mov     rcx, rax; lpString1
0x180038ba2  call    cs:__imp_CompareStringOrdinal
0x180038ba8  cmp     eax, 2
0x180038bab  jz      loc_180038D02
0x180038bb1  mov     [rsp+0F0h+bIgnoreCase], 1; bIgnoreCase
0x180038bb9  or      r9d, 0FFFFFFFFh; cchCount2
0x180038bbd  lea     r8, aExe; ".exe"
0x180038bc4  or      edx, r9d; cchCount1
0x180038bc7  mov     rcx, rsi; lpString1
0x180038bca  call    cs:__imp_CompareStringOrdinal
0x180038bd0  cmp     eax, 2
0x180038bd3  jz      loc_180038D02
0x180038bd9  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x180038be0  add     rcx, 70h ; 'p'; this
0x180038be4  mov     rax, [rcx+8]
0x180038be8  cmp     [rcx], rax
0x180038beb  jz      loc_180038D4B
0x180038bf1  cmp     qword ptr [r14+18h], 7
0x180038bf6  jbe     short loc_180038BFB
0x180038bf8  mov     r14, [r14]
0x180038bfb  mov     r9, r14
0x180038bfe  lea     r8, aAttemptedToAdd; "Attempted to add ngen module to package"...
0x180038c05  lea     rdx, aDAWork1SSource_1; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x180038c0c  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x180038c11  jmp     loc_180038D4B
0x180038c16  mov     rcx, rsi; SRWLock
0x180038c19  call    cs:__imp_ReleaseSRWLockShared
0x180038c1f  mov     r12, [r15+140h]
0x180038c26  mov     rax, [r15+148h]
0x180038c2d  mov     [rbp+57h+var_98], rax
0x180038c31  cmp     r12, rax
0x180038c34  jz      loc_180038B68
0x180038c3a  lea     rcx, [r13+28h]
0x180038c3e  mov     r9, [r12+10h]
0x180038c43  mov     r8, r12
0x180038c46  cmp     qword ptr [r12+18h], 7
0x180038c4c  jbe     short loc_180038C52
0x180038c4e  mov     r8, [r12]
0x180038c52  mov     rdx, [rcx+10h]
0x180038c56  mov     rax, rcx
0x180038c59  mov     [rbp+57h+var_A8], rcx
0x180038c5d  cmp     qword ptr [rcx+18h], 7
0x180038c62  jbe     short loc_180038C6B
0x180038c64  mov     rax, [rcx]
0x180038c67  mov     [rbp+57h+var_A8], rax
0x180038c6b  cmp     r9, rdx
0x180038c6e  ja      short loc_180038C9D
0x180038c70  test    r9, r9
0x180038c73  jz      short loc_180038CAC
0x180038c75  lfence
0x180038c78  lea     rsi, [rax+rdx*2]
0x180038c7c  mov     rdx, rsi
0x180038c7f  mov     rcx, rax
0x180038c82  call    __std_search_2
0x180038c87  cmp     rax, rsi
0x180038c8a  jz      short loc_180038C99
0x180038c8c  sub     rax, [rbp+57h+var_A8]
0x180038c90  sar     rax, 1
0x180038c93  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180038c97  jnz     short loc_180038CAC
0x180038c99  lea     rcx, [r13+28h]
0x180038c9d  add     r12, 20h ; ' '
0x180038ca1  cmp     r12, [rbp+57h+var_98]
0x180038ca5  jnz     short loc_180038C3E
0x180038ca7  jmp     loc_180038B68
0x180038cac  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x180038cb3  add     rcx, 38h ; '8'; this
0x180038cb7  mov     rax, [rcx+8]
0x180038cbb  cmp     [rcx], rax
0x180038cbe  jz      loc_180038D4B
0x180038cc4  cmp     qword ptr [r12+18h], 7
0x180038cca  jbe     short loc_180038CD0
0x180038ccc  mov     r12, [r12]
0x180038cd0  lea     rax, [r13+28h]
0x180038cd4  cmp     qword ptr [r13+40h], 7
0x180038cd9  jbe     short loc_180038CDF
0x180038cdb  mov     rax, [r13+28h]
0x180038cdf  mov     [rsp+0F0h+var_C8], r12
0x180038ce4  mov     qword ptr [rsp+0F0h+bIgnoreCase], rax
0x180038ce9  mov     r9, [rbp+57h+var_90]
0x180038ced  lea     r8, aAssemblyId08xF; "Assembly ID %#08x filtered out: '%s' by"...
0x180038cf4  lea     rdx, aDAWork1SSource_1; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x180038cfb  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x180038d00  jmp     short loc_180038D4B
0x180038d02  mov     rsi, qword ptr [rbp+57h+var_50+8]
0x180038d06  cmp     rsi, [rbp+57h+var_40]
0x180038d0a  jz      short loc_180038D3C
0x180038d0c  mov     rdx, r14
0x180038d0f  mov     rcx, rsi
0x180038d12  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180038d17  mov     rax, [r14+20h]
0x180038d1b  mov     [rsi+20h], rax
0x180038d1f  mov     rax, [r14+28h]
0x180038d23  mov     [rsi+28h], rax
0x180038d27  mov     al, [r14+30h]
0x180038d2b  mov     [rsi+30h], al
0x180038d2e  mov     al, [r14+31h]
0x180038d32  mov     [rsi+31h], al
0x180038d35  add     qword ptr [rbp+57h+var_50+8], 38h ; '8'
0x180038d3a  jmp     short loc_180038D4B
0x180038d3c  mov     r8, r14
0x180038d3f  mov     rdx, rsi
0x180038d42  lea     rcx, [rbp+57h+var_50]
0x180038d46  call    ??$_Emplace_reallocate@AEBUModuleDetails@NgenSymbolHelper@StandardCollector@DiagnosticsHub@Microsoft@@@?$vector@UModuleDetails@NgenSymbolHelper@StandardCollector@DiagnosticsHub@Microsoft@@V?$allocator@UModuleDetails@NgenSymbolHelper@StandardCollector@DiagnosticsHub@Microsoft@@@std@@@std@@AEAAPEAUModuleDetails@NgenSymbolHelper@StandardCollector@DiagnosticsHub@Microsoft@@QEAU23456@AEBU23456@@Z; std::vector<Microsoft::DiagnosticsHub::StandardCollector::NgenSymbolHelper::ModuleDetails>::_Emplace_reallocate<Microsoft::DiagnosticsHub::StandardCollector::NgenSymbolHelper::ModuleDetails const &>(Microsoft::DiagnosticsHub::StandardCollector::NgenSymbolHelper::ModuleDetails * const,Microsoft::DiagnosticsHub::StandardCollector::NgenSymbolHelper::ModuleDetails const &)
0x180038d4b  mov     rax, [rbp+57h+var_B0]
0x180038d4f  mov     rbx, [rbx]
0x180038d52  cmp     rbx, rax
0x180038d55  jnz     loc_180038AD8
0x180038d5b  mov     rsi, [rbp+57h+var_A0]
0x180038d5f  mov     rax, qword ptr [rbp+57h+var_50+8]
0x180038d63  cmp     qword ptr [rbp+57h+var_50], rax
0x180038d67  jz      loc_180038F01
0x180038d6d  mov     [rbp+57h+var_58], 0
0x180038d75  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x180038d7a  mov     rcx, rax
0x180038d7d  test    rax, rax
0x180038d80  jz      loc_180038F3B
0x180038d86  mov     rax, [rax]
0x180038d89  mov     rax, [rax+18h]
0x180038d8d  call    cs:__guard_dispatch_icall_fptr
0x180038d93  add     rax, 18h
0x180038d97  mov     [rbp+57h+var_58], rax
0x180038d9b  lea     rbx, [r15+158h]
0x180038da2  lea     rdx, [rbp+57h+var_58]
0x180038da6  mov     rcx, rbx; this
0x180038da9  call    ?GetSymbolCachePath@NgenSymbolHelper@StandardCollector@DiagnosticsHub@Microsoft@@QEAAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; Microsoft::DiagnosticsHub::StandardCollector::NgenSymbolHelper::GetSymbolCachePath(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x180038dae  mov     [rbp+57h+var_60], 0
0x180038db5  mov     [rbp+57h+var_5C], 0
0x180038dbc  lea     r8, [r15+1C0h]
0x180038dc3  lea     rax, [rbp+57h+var_5C]
0x180038dc7  mov     [rsp+0F0h+var_C8], rax
0x180038dcc  lea     rax, [rbp+57h+var_60]
0x180038dd0  mov     qword ptr [rsp+0F0h+bIgnoreCase], rax
0x180038dd5  lea     r9, [rbp+57h+var_58]
0x180038dd9  lea     rdx, [rbp+57h+var_50]
0x180038ddd  mov     rcx, rbx
0x180038de0  call    ?AddNgenPdbsToScratchDir@NgenSymbolHelper@StandardCollector@DiagnosticsHub@Microsoft@@QEAAJAEAV?$vector@UModuleDetails@NgenSymbolHelper@StandardCollector@DiagnosticsHub@Microsoft@@V?$allocator@UModuleDetails@NgenSymbolHelper@StandardCollector@DiagnosticsHub@Microsoft@@@std@@@std@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@1AEAJ2@Z; Microsoft::DiagnosticsHub::StandardCollector::NgenSymbolHelper::AddNgenPdbsToScratchDir(std::vector<Microsoft::DiagnosticsHub::StandardCollector::NgenSymbolHelper::ModuleDetails> &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,long &,long &)
0x180038de5  test    eax, eax
0x180038de7  js      loc_180038ED8
0x180038ded  lfence
0x180038df0  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x180038df7  mov     rax, [rcx+8]
0x180038dfb  cmp     [rcx], rax
0x180038dfe  jz      loc_180038E86
0x180038e04  lea     rcx, [rbp+57h+var_A0]
0x180038e08  call    ?now@steady_clock@chrono@std@@SA?AV?$time_point@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@23@XZ; std::chrono::steady_clock::now(void)
0x180038e0d  mov     rcx, [rbp+57h+var_A0]
0x180038e11  sub     rcx, [rbp+57h+var_88]
0x180038e15  mov     rax, 431BDE82D7B634DBh
0x180038e1f  imul    rcx
0x180038e22  sar     rdx, 12h
0x180038e26  mov     r9, rdx
0x180038e29  shr     r9, 3Fh
0x180038e2d  add     r9, rdx
0x180038e30  lea     r8, aCreatingPdbsFr; "Creating pdbs from native image files u"...
0x180038e37  lea     rdx, aDAWork1SSource_1; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x180038e3e  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; this
0x180038e45  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x180038e4a  mov     r9d, [rbp+57h+var_60]
0x180038e4e  lea     r8, aCreatedDPdbsFr; "Created %d pdbs from native image files"...
0x180038e55  lea     rdx, aDAWork1SSource_1; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x180038e5c  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; this
0x180038e63  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x180038e68  mov     r9d, [rbp+57h+var_5C]
0x180038e6c  lea     r8, aUsedTheCacheTo; "Used the cache to get %d ngen pdbs inst"...
0x180038e73  lea     rdx, aDAWork1SSource_1; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x180038e7a  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; this
0x180038e81  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x180038e86  mov     rax, [rsi]
0x180038e89  mov     rbx, [rax+40h]
0x180038e8d  mov     rdx, [r15+1C0h]
0x180038e94  cmp     dword ptr [rdx-8], 1
0x180038e98  jle     short loc_180038EA9
0x180038e9a  mov     edx, [rdx-10h]
0x180038e9d  lea     rcx, [r15+1C0h]
0x180038ea4  call    ?Fork@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::Fork(int)
0x180038ea9  mov     [rsp+0F0h+var_C8], 0
0x180038eb2  mov     [rsp+0F0h+bIgnoreCase], 1
0x180038eba  xor     r9d, r9d
0x180038ebd  mov     r8, [r15+1C0h]
0x180038ec4  lea     rdx, aDiagnosticshub_0; "DiagnosticsHub.Resource.SymbolCache"
0x180038ecb  mov     rcx, rsi
0x180038ece  mov     rax, rbx
0x180038ed1  call    cs:__guard_dispatch_icall_fptr
0x180038ed7  nop
0x180038ed8  mov     rdx, [rbp+57h+var_58]
0x180038edc  add     rdx, 0FFFFFFFFFFFFFFE8h
0x180038ee0  or      eax, 0FFFFFFFFh
0x180038ee3  lock xadd [rdx+10h], eax
0x180038ee8  sub     eax, 1
0x180038eeb  jg      short loc_180038F01
0x180038eed  lfence
0x180038ef0  mov     rcx, [rdx]
0x180038ef3  mov     rax, [rcx]
0x180038ef6  mov     rax, [rax+8]
0x180038efa  call    cs:__guard_dispatch_icall_fptr
0x180038f00  nop
0x180038f01  lea     rcx, [rbp+57h+var_50]
0x180038f05  call    ??1?$vector@UModuleDetails@NgenSymbolHelper@StandardCollector@DiagnosticsHub@Microsoft@@V?$allocator@UModuleDetails@NgenSymbolHelper@StandardCollector@DiagnosticsHub@Microsoft@@@std@@@std@@QEAA@XZ; std::vector<Microsoft::DiagnosticsHub::StandardCollector::NgenSymbolHelper::ModuleDetails>::~vector<Microsoft::DiagnosticsHub::StandardCollector::NgenSymbolHelper::ModuleDetails>(void)
0x180038f0a  nop
0x180038f0b  mov     rcx, rdi; lpCriticalSection
0x180038f0e  call    cs:__imp_LeaveCriticalSection
0x180038f14  mov     rcx, [rbp+57h+var_38]
0x180038f18  xor     rcx, rsp; StackCookie
0x180038f1b  call    __security_check_cookie
0x180038f20  mov     rbx, [rsp+0F0h+arg_10]
0x180038f28  add     rsp, 0C0h
0x180038f2f  pop     r15
  ... truncated ...
```
