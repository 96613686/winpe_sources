# Microsoft::DiagnosticsHub::StandardCollector::ManagedInformationAgent::AddMetadataToPackage(DhPackaging::IDhPackage *)

- ea: `0x180038f48`
- end: `0x1800395eb`
- name: `?AddMetadataToPackage@ManagedInformationAgent@StandardCollector@DiagnosticsHub@Microsoft@@AEAAXPEAUIDhPackage@DhPackaging@@@Z`
- size: `1699`
- prototype: `void __fastcall(Microsoft::DiagnosticsHub::StandardCollector::ManagedInformationAgent *__hidden this, struct DhPackaging::IDhPackage *)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180037f10`

## callees

- `0x1800021fc`
- `0x180002604`
- `0x18000288c`
- `0x180027bc8`
- `0x180038f48`
- `0x180039824`
- `0x18003d864`
- `0x18004106c`
- `0x1800415c8`
- `0x180041618`
- `0x1800435e8`
- `0x180043860`
- `0x180043b34`
- `0x180049b50`
- `0x18004b640`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x18003905b`
- `KERNEL32!CreateFileW` at `0x18003925b`
- `KERNEL32!CreateFileW` at `0x18003905b`
- `KERNEL32!CreateFileW` at `0x18003925b`
- `KERNEL32!LeaveCriticalSection` at `0x180039592`
- `KERNEL32!LeaveCriticalSection` at `0x180039592`
- `KERNEL32!EnterCriticalSection` at `0x180038f88`
- `KERNEL32!EnterCriticalSection` at `0x180038f88`
- `KERNEL32!CloseHandle` at `0x1800392be`
- `KERNEL32!CloseHandle` at `0x1800392fb`
- `KERNEL32!CloseHandle` at `0x180039563`
- `KERNEL32!CloseHandle` at `0x1800392be`
- `KERNEL32!CloseHandle` at `0x1800392fb`
- `KERNEL32!CloseHandle` at `0x180039563`
- `KERNEL32!GetLastError` at `0x18003926b`
- `KERNEL32!GetLastError` at `0x1800392db`
- `KERNEL32!GetLastError` at `0x18003926b`
- `KERNEL32!GetLastError` at `0x1800392db`
- `KERNEL32!WriteFile` at `0x1800392a3`
- `KERNEL32!WriteFile` at `0x180039401`
- `KERNEL32!WriteFile` at `0x1800392a3`
- `KERNEL32!WriteFile` at `0x180039401`

## string_xrefs

- `0x180039383`: `D:\a\_work\1\s\sources\Base\Collection\StandardCollector.Runtime\ManagedInformationAgent.cpp`
- `0x180039463`: `D:\a\_work\1\s\sources\Base\Collection\StandardCollector.Runtime\ManagedInformationAgent.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
void __fastcall Microsoft::DiagnosticsHub::StandardCollector::ManagedInformationAgent::AddMetadataToPackage(
        Microsoft::DiagnosticsHub::StandardCollector::ManagedInformationAgent *this,
        struct DhPackaging::IDhPackage *a2)
{
  struct _RTL_CRITICAL_SECTION *v3; // r12
  const unsigned __int16 *v4; // rdx
  bool v5; // r8
  DiagHubCommon **v6; // rdi
  int Directory; // eax
  const unsigned __int16 *v8; // rdx
  struct ATL::IAtlStringMgr *Instance; // rax
  const WCHAR *v10; // r14
  HANDLE FileW; // rax
  struct ATL::IAtlStringMgr *v12; // rax
  LPCVOID v13; // r15
  struct ATL::IAtlStringMgr *v14; // rax
  const WCHAR *v15; // r13
  struct ATL::IAtlStringMgr *v16; // rax
  __int64 v17; // rsi
  unsigned __int64 v18; // r8
  _QWORD *v19; // rax
  _QWORD *v20; // rdi
  _QWORD *v21; // rcx
  DiagHubCommon **v22; // rbx
  DiagHubCommon *v23; // rcx
  const unsigned __int16 *LastPathPart; // rax
  Microsoft::DiagnosticsHub::StandardCollector::ManagedInformationAgent *v25; // rcx
  const WCHAR *v26; // rcx
  int v27; // ecx
  void (__fastcall ***v28)(_QWORD, __int64); // rbx
  __int64 v29; // rax
  __int64 v30; // r8
  const void *v31; // rax
  unsigned int v32; // eax
  HANDLE v33; // rax
  signed int LastError; // eax
  unsigned int v35; // ecx
  signed int v36; // eax
  unsigned int v37; // ecx
  unsigned int *v38; // rbx
  bool v39; // zf
  _QWORD *v40; // rax
  __int64 v41; // rdx
  DWORD v42; // ebx
  char v43; // al
  void (__fastcall *v44)(struct DhPackaging::IDhPackage *, const wchar_t *, _QWORD, _QWORD, int, _QWORD); // rdi
  Microsoft::DiagnosticsHub::StandardCollector::ManagedInformationAgent *v45; // rbx
  __int64 v46; // rdx
  DWORD dwCreationDisposition[2]; // [rsp+20h] [rbp-89h]
  char v48; // [rsp+40h] [rbp-69h]
  _BYTE nNumberOfBytesToWrite[12]; // [rsp+44h] [rbp-65h]
  DWORD nNumberOfBytesToWritea; // [rsp+44h] [rbp-65h]
  signed int nNumberOfBytesToWriteb; // [rsp+44h] [rbp-65h]
  LPCVOID lpBuffer; // [rsp+48h] [rbp-61h]
  HANDLE hObject; // [rsp+58h] [rbp-51h] BYREF
  LPCWSTR lpFileName; // [rsp+60h] [rbp-49h] BYREF
  LPCWSTR v55; // [rsp+68h] [rbp-41h] BYREF
  __int64 v56; // [rsp+70h] [rbp-39h] BYREF
  LPCVOID v57; // [rsp+78h] [rbp-31h] BYREF
  _QWORD *v58; // [rsp+80h] [rbp-29h]
  Microsoft::DiagnosticsHub::StandardCollector::ManagedInformationAgent *v59; // [rsp+88h] [rbp-21h]
  struct DhPackaging::IDhPackage *v60; // [rsp+90h] [rbp-19h]
  HANDLE hFile; // [rsp+98h] [rbp-11h]
  _QWORD *v62; // [rsp+A0h] [rbp-9h]
  char *v63; // [rsp+A8h] [rbp-1h]
  HANDLE v64; // [rsp+B0h] [rbp+7h]
  DWORD NumberOfBytesWritten; // [rsp+B8h] [rbp+Fh] BYREF
  DWORD v66; // [rsp+BCh] [rbp+13h] BYREF

  v60 = a2;
  v59 = this;
  v3 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 64);
  v63 = (char *)this + 64;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  if ( *((_BYTE *)this + 113) )
  {
    *((_BYTE *)this + 113) = 0;
    v6 = (DiagHubCommon **)((char *)this + 456);
    v62 = (_QWORD *)((char *)this + 456);
    Directory = DiagHubCommon::DeleteDirectory(*((DiagHubCommon **)this + 57), v4, v5);
    if ( !Directory || Directory == -2147024893 )
      Directory = DiagHubCommon::VerifyOrCreateDirectory(*v6, v8);
    if ( Directory >= 0 )
    {
      Instance = ATL::CAtlStringMgr::GetInstance();
      if ( !Instance )
        ATL::AtlThrowImpl(-2147467259);
      lpFileName = (LPCWSTR)((*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)Instance + 24LL))(Instance)
                           + 24);
      if ( *((int *)*v6 - 2) > 1 )
        ATL::CSimpleStringT<unsigned short,0>::Fork((char *)this + 456, *((unsigned int *)*v6 - 4));
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
        &lpFileName,
        L"%s\\MetadataLookupMap.txt",
        *v6);
      v10 = lpFileName;
      if ( *((int *)lpFileName - 2) > 1 )
      {
        ATL::CSimpleStringT<unsigned short,0>::Fork(&lpFileName, *((unsigned int *)lpFileName - 4));
        v10 = lpFileName;
      }
      FileW = CreateFileW(v10, 2u, 0, 0, 2u, 0x80u, 0);
      hFile = FileW;
      if ( FileW != (HANDLE)-1LL )
      {
        v64 = FileW;
        v48 = 0;
        v12 = ATL::CAtlStringMgr::GetInstance();
        if ( !v12 )
          ATL::AtlThrowImpl(-2147467259);
        v13 = (LPCVOID)((*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)v12 + 24LL))(v12) + 24);
        v57 = v13;
        v14 = ATL::CAtlStringMgr::GetInstance();
        if ( !v14 )
          ATL::AtlThrowImpl(-2147467259);
        v15 = (const WCHAR *)((*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)v14 + 24LL))(v14) + 24);
        v55 = v15;
        v16 = ATL::CAtlStringMgr::GetInstance();
        if ( !v16 )
          ATL::AtlThrowImpl(-2147467259);
        v17 = (*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)v16 + 24LL))(v16) + 24;
        v56 = v17;
        v19 = (_QWORD *)*((_QWORD *)this + 25);
        v58 = v19;
        v20 = (_QWORD *)*v19;
        if ( (_QWORD *)*v19 != v19 )
        {
          v21 = v19;
          while ( 1 )
          {
            v22 = (DiagHubCommon **)(v20 + 3);
            if ( !*((_BYTE *)v20 + 73) )
              break;
LABEL_66:
            v43 = v48;
LABEL_67:
            v20 = (_QWORD *)*v20;
            if ( v20 == v21 )
            {
              if ( v43 )
              {
                v44 = *(void (__fastcall **)(struct DhPackaging::IDhPackage *, const wchar_t *, _QWORD, _QWORD, int, _QWORD))(*(_QWORD *)v60 + 64LL);
                v45 = v59;
                v46 = *((_QWORD *)v59 + 57);
                if ( *(int *)(v46 - 8) > 1 )
                  ATL::CSimpleStringT<unsigned short,0>::Fork((char *)v59 + 456, *(unsigned int *)(v46 - 16));
                v44(v60, L"DiagnosticsHub.Resource.ManagedMetadata", *((_QWORD *)v45 + 57), 0, 1, 0);
              }
              goto LABEL_72;
            }
          }
          *((_BYTE *)v20 + 73) = 1;
          v23 = (DiagHubCommon *)(v20 + 3);
          if ( v20[6] > 7u )
            v23 = *v22;
          LastPathPart = DiagHubCommon::GetLastPathPart(v23, 0, v18);
          v25 = v59;
          ++*((_DWORD *)v59 + 30);
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
            &v56,
            L"%s_%d.metadata",
            LastPathPart,
            *((unsigned int *)v25 + 30));
          v17 = v56;
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
            &v55,
            L"%s\\%s",
            *v62,
            v56);
          v15 = v55;
          if ( *((int *)v55 - 2) > 1 )
          {
            ATL::CSimpleStringT<unsigned short,0>::Fork(&v55, *((unsigned int *)v55 - 4));
            v15 = v55;
          }
          v26 = (const WCHAR *)(v20 + 3);
          if ( v20[6] > 7u )
            v26 = (const WCHAR *)*v22;
          *(_DWORD *)&nNumberOfBytesToWrite[8] = 0;
          *(_QWORD *)nNumberOfBytesToWrite = (unsigned int)DiagHubCommon::PeHelper::CreateFromFile(v26);
          if ( *(int *)nNumberOfBytesToWrite < 0 )
          {
            v27 = *(_DWORD *)nNumberOfBytesToWrite;
LABEL_62:
            _mm_lfence();
            if ( (unsigned __int64)v22[3] > 7 )
              v22 = (DiagHubCommon **)v20[3];
            dwCreationDisposition[0] = v27;
            DiagHubCommon::LogStream::Write(
              (DiagHubCommon::LogStream *)((char *)_logger + 168),
              L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\ManagedInformationAgent.cpp",
              L"Failed to extract metadata from '%s' (HRESULT %#08x)",
              v22,
              *(_QWORD *)dwCreationDisposition);
LABEL_65:
            v21 = v58;
            goto LABEL_66;
          }
          v28 = *(void (__fastcall ****)(_QWORD, __int64))&nNumberOfBytesToWrite[4];
          DiagHubCommon::PeHelper::EnsureCor20HeaderRead(*(DiagHubCommon::PeHelper **)&nNumberOfBytesToWrite[4]);
          v29 = *(_QWORD *)(*(_QWORD *)&nNumberOfBytesToWrite[4] + 72LL);
          if ( v29 )
            nNumberOfBytesToWritea = *(_DWORD *)(v29 + 12);
          else
            nNumberOfBytesToWritea = 0;
          DiagHubCommon::PeHelper::EnsureCor20HeaderRead(*(DiagHubCommon::PeHelper **)&nNumberOfBytesToWrite[4]);
          v30 = *(_QWORD *)(*(_QWORD *)&nNumberOfBytesToWrite[4] + 72LL);
          if ( v30
            && (v32 = DiagHubCommon::PeHelper::PeHelperDataSource::RvaToOffset(
                        *(DiagHubCommon::PeHelper::PeHelperDataSource **)(*(_QWORD *)&nNumberOfBytesToWrite[4] + 8LL),
                        *(struct DiagHubCommon::PeHelper **)&nNumberOfBytesToWrite[4],
                        *(_DWORD *)(v30 + 8))) != 0 )
          {
            v31 = (const void *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)&nNumberOfBytesToWrite[4] + 8LL) + 8LL) + v32);
          }
          else
          {
            v31 = 0;
          }
          lpBuffer = v31;
          if ( nNumberOfBytesToWritea && v31 )
          {
            v33 = CreateFileW(v15, 2u, 0, 0, 2u, 0x80u, 0);
            hObject = v33;
            if ( v33 == (HANDLE)-1LL )
            {
              LastError = GetLastError();
              v35 = (unsigned __int16)LastError | 0x80070000;
              if ( LastError <= 0 )
                v35 = LastError;
              nNumberOfBytesToWriteb = v35;
            }
            else
            {
              NumberOfBytesWritten = 0;
              if ( WriteFile(v33, lpBuffer, nNumberOfBytesToWritea, &NumberOfBytesWritten, 0)
                && NumberOfBytesWritten == nNumberOfBytesToWritea )
              {
                if ( hObject )
                  CloseHandle(hObject);
                (**v28)(v28, 1);
                goto LABEL_49;
              }
              v36 = GetLastError();
              v37 = (unsigned __int16)v36 | 0x80070000;
              if ( v36 <= 0 )
                v37 = v36;
              nNumberOfBytesToWriteb = v37;
              if ( hObject )
                CloseHandle(hObject);
            }
            (**v28)(v28, 1);
            v27 = nNumberOfBytesToWriteb;
            if ( nNumberOfBytesToWriteb >= 0 )
            {
LABEL_49:
              _mm_lfence();
              hObject = 0;
              std::_Hash<std::_Umap_traits<unsigned __int64,Microsoft::DiagnosticsHub::StandardCollector::ManagedInformationAgent::AssemblyDetails,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,Microsoft::DiagnosticsHub::StandardCollector::ManagedInformationAgent::AssemblyDetails>>,0>>::find(
                (char *)v59 + 256,
                &hObject,
                v20 + 7);
              v38 = (unsigned int *)hObject;
              v39 = hObject == *((HANDLE *)v59 + 33);
              _mm_lfence();
              if ( !v39 )
              {
                if ( *(int *)(v17 - 8) > 1 )
                {
                  ATL::CSimpleStringT<unsigned short,0>::Fork(&v56, *(unsigned int *)(v17 - 16));
                  v17 = v56;
                }
                ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
                  &v57,
                  L"%lu;%llu;%s\n",
                  v38[8],
                  v20[8],
                  v17);
                v13 = v57;
                v41 = *((unsigned int *)v57 - 4);
                v42 = 2 * v41;
                if ( *((int *)v57 - 2) > 1 )
                {
                  ATL::CSimpleStringT<unsigned short,0>::Fork(&v57, v41);
                  v13 = v57;
                }
                if ( !WriteFile(hFile, v13, v42, &v66, 0) || v66 != v42 )
                  goto LABEL_72;
                v43 = 1;
                v48 = 1;
                v21 = v58;
                goto LABEL_67;
              }
              v40 = v20 + 3;
              if ( v20[6] > 7u )
                v40 = (_QWORD *)v20[3];
              DiagHubCommon::LogStream::Write(
                (DiagHubCommon::LogStream *)((char *)_logger + 168),
                L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\ManagedInformationAgent.cpp",
                L"Could not find assembly details for '%s' while writing metadata file.",
                v40);
              goto LABEL_65;
            }
          }
          else
          {
            (**v28)(v28, 1);
            v27 = -2146231243;
          }
          v22 = (DiagHubCommon **)(v20 + 3);
          goto LABEL_62;
        }
LABEL_72:
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v17 - 24 + 16), 0xFFFFFFFF) <= 1 )
        {
          _mm_lfence();
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v17 - 24) + 8LL))(*(_QWORD *)(v17 - 24));
        }
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v15 - 2, 0xFFFFFFFF) <= 1 )
        {
          _mm_lfence();
          (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v15 - 3) + 8LL))(*((_QWORD *)v15 - 3));
        }
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v13 - 2, 0xFFFFFFFF) <= 1 )
        {
          _mm_lfence();
          (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v13 - 3) + 8LL))(*((_QWORD *)v13 - 3));
        }
        if ( hFile )
          CloseHandle(hFile);
      }
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v10 - 2, 0xFFFFFFFF) <= 1 )
      {
        _mm_lfence();
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v10 - 3) + 8LL))(*((_QWORD *)v10 - 3));
      }
    }
  }
  LeaveCriticalSection(v3);
}

```

## disassembly

```asm
0x180038f48  mov     [rsp-8+arg_10], rbx
0x180038f4d  push    rbp
0x180038f4e  push    rsi
0x180038f4f  push    rdi
0x180038f50  push    r12
0x180038f52  push    r13
0x180038f54  push    r14
0x180038f56  push    r15
0x180038f58  lea     rbp, [rsp-27h]
0x180038f5d  sub     rsp, 0D0h
0x180038f64  mov     rax, cs:__security_cookie
0x180038f6b  xor     rax, rsp
0x180038f6e  mov     [rbp+57h+var_40], rax
0x180038f72  mov     [rbp+57h+var_70], rdx
0x180038f76  mov     rbx, rcx
0x180038f79  mov     [rbp+57h+var_78], rcx
0x180038f7d  lea     r12, [rcx+40h]
0x180038f81  mov     [rbp+57h+var_58], r12
0x180038f85  mov     rcx, r12; lpCriticalSection
0x180038f88  call    cs:__imp_EnterCriticalSection
0x180038f8e  nop
0x180038f8f  mov     al, [rbx+71h]
0x180038f92  test    al, al
0x180038f94  jz      loc_18003958F
0x180038f9a  xor     eax, eax
0x180038f9c  xchg    al, [rbx+71h]
0x180038f9f  lea     rdi, [rbx+1C8h]
0x180038fa6  mov     [rbp+57h+var_60], rdi
0x180038faa  mov     rcx, [rdi]; this
0x180038fad  call    ?DeleteDirectory@DiagHubCommon@@YAJPEBG_N@Z; DiagHubCommon::DeleteDirectory(ushort const *,bool)
0x180038fb2  test    eax, eax
0x180038fb4  jz      short loc_180038FBD
0x180038fb6  cmp     eax, 80070003h
0x180038fbb  jnz     short loc_180038FC5
0x180038fbd  mov     rcx, [rdi]; this
0x180038fc0  call    ?VerifyOrCreateDirectory@DiagHubCommon@@YAJPEBG@Z; DiagHubCommon::VerifyOrCreateDirectory(ushort const *)
0x180038fc5  test    eax, eax
0x180038fc7  js      loc_18003958F
0x180038fcd  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x180038fd2  mov     rcx, rax
0x180038fd5  test    rax, rax
0x180038fd8  jz      loc_1800395CA
0x180038fde  mov     rax, [rax]
0x180038fe1  mov     rax, [rax+18h]
0x180038fe5  call    cs:__guard_dispatch_icall_fptr
0x180038feb  add     rax, 18h
0x180038fef  mov     [rbp+57h+lpFileName], rax
0x180038ff3  mov     rdx, [rdi]
0x180038ff6  cmp     dword ptr [rdx-8], 1
0x180038ffa  jle     short loc_180039007
0x180038ffc  mov     edx, [rdx-10h]
0x180038fff  mov     rcx, rdi
0x180039002  call    ?Fork@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::Fork(int)
0x180039007  mov     r8, [rdi]
0x18003900a  lea     rdx, aSMetadatalooku; "%s\\MetadataLookupMap.txt"
0x180039011  lea     rcx, [rbp+57h+lpFileName]
0x180039015  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x18003901a  mov     r14, [rbp+57h+lpFileName]
0x18003901e  cmp     dword ptr [r14-8], 1
0x180039023  jle     short loc_180039036
0x180039025  mov     edx, [r14-10h]
0x180039029  lea     rcx, [rbp+57h+lpFileName]
0x18003902d  call    ?Fork@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::Fork(int)
0x180039032  mov     r14, [rbp+57h+lpFileName]
0x180039036  mov     [rsp+100h+hTemplateFile], 0; hTemplateFile
0x18003903f  mov     [rsp+100h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180039047  mov     eax, 2
0x18003904c  mov     [rsp+100h+dwCreationDisposition], eax; dwCreationDisposition
0x180039050  xor     r9d, r9d; lpSecurityAttributes
0x180039053  xor     r8d, r8d; dwShareMode
0x180039056  mov     edx, eax; dwDesiredAccess
0x180039058  mov     rcx, r14; lpFileName
0x18003905b  call    cs:__imp_CreateFileW
0x180039061  mov     [rbp+57h+hFile], rax
0x180039065  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180039069  jz      loc_18003956A
0x18003906f  mov     [rbp+57h+var_50], rax
0x180039073  mov     [rbp+57h+var_C0], 0
0x180039077  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x18003907c  mov     rcx, rax
0x18003907f  test    rax, rax
0x180039082  jz      loc_1800395D5
0x180039088  mov     rax, [rax]
0x18003908b  mov     rax, [rax+18h]
0x18003908f  call    cs:__guard_dispatch_icall_fptr
0x180039095  lea     r15, [rax+18h]
0x180039099  mov     [rbp+57h+var_88], r15
0x18003909d  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x1800390a2  mov     rcx, rax
0x1800390a5  test    rax, rax
0x1800390a8  jz      loc_1800395E0
0x1800390ae  mov     rax, [rax]
0x1800390b1  mov     rax, [rax+18h]
0x1800390b5  call    cs:__guard_dispatch_icall_fptr
0x1800390bb  lea     r13, [rax+18h]
0x1800390bf  mov     [rbp+57h+var_98], r13
0x1800390c3  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x1800390c8  mov     rcx, rax
0x1800390cb  test    rax, rax
0x1800390ce  jz      loc_1800395BF
0x1800390d4  mov     rax, [rax]
0x1800390d7  mov     rax, [rax+18h]
0x1800390db  call    cs:__guard_dispatch_icall_fptr
0x1800390e1  lea     rsi, [rax+18h]
0x1800390e5  mov     [rbp+57h+var_90], rsi
0x1800390e9  mov     rax, [rbx+0C8h]
0x1800390f0  mov     [rbp+57h+var_80], rax
0x1800390f4  mov     rdi, [rax]
0x1800390f7  cmp     rdi, rax
0x1800390fa  jz      loc_1800394E8
0x180039100  mov     rcx, rax
0x180039103  lea     rbx, [rdi+18h]
0x180039107  mov     [rbp+57h+var_B0], rbx
0x18003910b  cmp     byte ptr [rdi+49h], 0
0x18003910f  jnz     loc_18003947A
0x180039115  mov     byte ptr [rbx+31h], 1
0x180039119  mov     rcx, rbx
0x18003911c  cmp     qword ptr [rbx+18h], 7
0x180039121  jbe     short loc_180039126
0x180039123  mov     rcx, [rbx]; this
0x180039126  xor     edx, edx; unsigned __int16 *
0x180039128  call    ?GetLastPathPart@DiagHubCommon@@YAPEBGPEBG_K@Z; DiagHubCommon::GetLastPathPart(ushort const *,unsigned __int64)
0x18003912d  mov     rcx, [rbp+57h+var_78]
0x180039131  inc     dword ptr [rcx+78h]
0x180039134  mov     r9d, [rcx+78h]
0x180039138  mov     r8, rax
0x18003913b  lea     rdx, aSDMetadata; "%s_%d.metadata"
0x180039142  lea     rcx, [rbp+57h+var_90]
0x180039146  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x18003914b  mov     rsi, [rbp+57h+var_90]
0x18003914f  mov     r9, rsi
0x180039152  mov     rax, [rbp+57h+var_60]
0x180039156  mov     r8, [rax]
0x180039159  lea     rdx, aSS_2; "%s\\%s"
0x180039160  lea     rcx, [rbp+57h+var_98]
0x180039164  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x180039169  mov     r13, [rbp+57h+var_98]
0x18003916d  cmp     dword ptr [r13-8], 1
0x180039172  jle     short loc_180039185
0x180039174  mov     edx, [r13-10h]
0x180039178  lea     rcx, [rbp+57h+var_98]
0x18003917c  call    ?Fork@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::Fork(int)
0x180039181  mov     r13, [rbp+57h+var_98]
0x180039185  mov     rcx, rbx
0x180039188  cmp     qword ptr [rbx+18h], 7
0x18003918d  jbe     short loc_180039192
0x18003918f  mov     rcx, [rbx]; lpFileName
0x180039192  mov     [rbp+57h+lpBuffer], 0
0x18003919a  lea     rdx, [rbp+57h+lpBuffer]
0x18003919e  call    ?CreateFromFile@PeHelper@DiagHubCommon@@SAJPEBGAEAV?$unique_ptr@VPeHelper@DiagHubCommon@@U?$default_delete@VPeHelper@DiagHubCommon@@@std@@@std@@_N@Z; DiagHubCommon::PeHelper::CreateFromFile(ushort const *,std::unique_ptr<DiagHubCommon::PeHelper> &,bool)
0x1800391a3  mov     [rbp+57h+nNumberOfBytesToWrite], eax
0x1800391a6  test    eax, eax
0x1800391a8  jns     short loc_1800391CC
0x1800391aa  mov     rcx, [rbp+57h+lpBuffer]
0x1800391ae  test    rcx, rcx
0x1800391b1  jz      short loc_1800391C4
0x1800391b3  mov     rdx, [rcx]
0x1800391b6  mov     rax, [rdx]
0x1800391b9  mov     edx, 1
0x1800391be  call    cs:__guard_dispatch_icall_fptr
0x1800391c4  mov     ecx, [rbp+57h+nNumberOfBytesToWrite]
0x1800391c7  jmp     loc_180039440
0x1800391cc  mov     rbx, [rbp+57h+lpBuffer]
0x1800391d0  mov     rcx, rbx; this
0x1800391d3  call    ?EnsureCor20HeaderRead@PeHelper@DiagHubCommon@@AEAAXXZ; DiagHubCommon::PeHelper::EnsureCor20HeaderRead(void)
0x1800391d8  mov     rax, [rbx+48h]
0x1800391dc  test    rax, rax
0x1800391df  jnz     short loc_1800391E6
0x1800391e1  mov     [rbp+57h+nNumberOfBytesToWrite], eax
0x1800391e4  jmp     short loc_1800391EC
0x1800391e6  mov     eax, [rax+0Ch]
0x1800391e9  mov     [rbp+57h+nNumberOfBytesToWrite], eax
0x1800391ec  mov     rcx, rbx; this
0x1800391ef  call    ?EnsureCor20HeaderRead@PeHelper@DiagHubCommon@@AEAAXXZ; DiagHubCommon::PeHelper::EnsureCor20HeaderRead(void)
0x1800391f4  mov     r8, [rbx+48h]
0x1800391f8  test    r8, r8
0x1800391fb  jnz     short loc_180039201
0x1800391fd  xor     eax, eax
0x1800391ff  jmp     short loc_18003921F
0x180039201  mov     rcx, [rbx+8]; this
0x180039205  mov     r8d, [r8+8]; unsigned int
0x180039209  mov     rdx, rbx; struct DiagHubCommon::PeHelper *
0x18003920c  call    ?RvaToOffset@PeHelperDataSource@PeHelper@DiagHubCommon@@QEAAKPEAV23@K@Z; DiagHubCommon::PeHelper::PeHelperDataSource::RvaToOffset(DiagHubCommon::PeHelper *,ulong)
0x180039211  test    eax, eax
0x180039213  jz      short loc_1800391FD
0x180039215  mov     eax, eax
0x180039217  mov     rcx, [rbx+8]
0x18003921b  add     rax, [rcx+8]
0x18003921f  mov     [rbp+57h+lpBuffer], rax
0x180039223  cmp     [rbp+57h+nNumberOfBytesToWrite], 0
0x180039227  jz      loc_180039423
0x18003922d  test    rax, rax
0x180039230  jz      loc_180039423
0x180039236  mov     [rsp+100h+hTemplateFile], 0; hTemplateFile
0x18003923f  mov     [rsp+100h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180039247  mov     eax, 2
0x18003924c  mov     [rsp+100h+dwCreationDisposition], eax; dwCreationDisposition
0x180039250  xor     r9d, r9d; lpSecurityAttributes
0x180039253  xor     r8d, r8d; dwShareMode
0x180039256  mov     edx, eax; dwDesiredAccess
0x180039258  mov     rcx, r13; lpFileName
0x18003925b  call    cs:__imp_CreateFileW
0x180039261  mov     [rbp+57h+hObject], rax
0x180039265  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180039269  jnz     short loc_180039284
0x18003926b  call    cs:__imp_GetLastError
0x180039271  movzx   ecx, ax
0x180039274  or      ecx, 80070000h
0x18003927a  test    eax, eax
0x18003927c  cmovle  ecx, eax
0x18003927f  mov     [rbp+57h+nNumberOfBytesToWrite], ecx
0x180039282  jmp     short loc_180039302
0x180039284  mov     [rbp+57h+NumberOfBytesWritten], 0
0x18003928b  mov     qword ptr [rsp+100h+dwCreationDisposition], 0; lpOverlapped
0x180039294  lea     r9, [rbp+57h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180039298  mov     r8d, [rbp+57h+nNumberOfBytesToWrite]; nNumberOfBytesToWrite
0x18003929c  mov     rdx, [rbp+57h+lpBuffer]; lpBuffer
0x1800392a0  mov     rcx, rax; hFile
0x1800392a3  call    cs:__imp_WriteFile
0x1800392a9  test    eax, eax
0x1800392ab  jz      short loc_1800392DB
0x1800392ad  mov     eax, [rbp+57h+nNumberOfBytesToWrite]
0x1800392b0  cmp     [rbp+57h+NumberOfBytesWritten], eax
0x1800392b3  jnz     short loc_1800392DB
0x1800392b5  mov     rcx, [rbp+57h+hObject]; hObject
0x1800392b9  test    rcx, rcx
0x1800392bc  jz      short loc_1800392C5
0x1800392be  call    cs:__imp_CloseHandle
0x1800392c4  nop
0x1800392c5  mov     rax, [rbx]
0x1800392c8  mov     edx, 1
0x1800392cd  mov     rcx, rbx
0x1800392d0  mov     rax, [rax]
0x1800392d3  call    cs:__guard_dispatch_icall_fptr
0x1800392d9  jmp     short loc_180039321
0x1800392db  call    cs:__imp_GetLastError
0x1800392e1  movzx   ecx, ax
0x1800392e4  or      ecx, 80070000h
0x1800392ea  test    eax, eax
0x1800392ec  cmovle  ecx, eax
0x1800392ef  mov     [rbp+57h+nNumberOfBytesToWrite], ecx
0x1800392f2  mov     rcx, [rbp+57h+hObject]; hObject
0x1800392f6  test    rcx, rcx
0x1800392f9  jz      short loc_180039302
0x1800392fb  call    cs:__imp_CloseHandle
0x180039301  nop
0x180039302  mov     rax, [rbx]
0x180039305  mov     edx, 1
0x18003930a  mov     rcx, rbx
0x18003930d  mov     rax, [rax]
0x180039310  call    cs:__guard_dispatch_icall_fptr
0x180039316  mov     ecx, [rbp+57h+nNumberOfBytesToWrite]
0x180039319  test    ecx, ecx
0x18003931b  js      loc_18003943C
0x180039321  lfence
0x180039324  mov     [rbp+57h+hObject], 0
0x18003932c  mov     r8, [rbp+57h+var_B0]
0x180039330  add     r8, 20h ; ' '
0x180039334  mov     rcx, [rbp+57h+var_78]
0x180039338  add     rcx, 100h
0x18003933f  lea     rdx, [rbp+57h+hObject]
0x180039343  call    ?find@?$_Hash@V?$_Umap_traits@_KUAssemblyDetails@ManagedInformationAgent@StandardCollector@DiagnosticsHub@Microsoft@@V?$_Uhash_compare@_KU?$hash@_K@std@@U?$equal_to@_K@2@@std@@V?$allocator@U?$pair@$$CB_KUAssemblyDetails@ManagedInformationAgent@StandardCollector@DiagnosticsHub@Microsoft@@@std@@@7@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CB_KUAssemblyDetails@ManagedInformationAgent@StandardCollector@DiagnosticsHub@Microsoft@@@std@@@std@@@std@@@2@AEB_K@Z; std::_Hash<std::_Umap_traits<unsigned __int64,Microsoft::DiagnosticsHub::StandardCollector::ManagedInformationAgent::AssemblyDetails,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,Microsoft::DiagnosticsHub::StandardCollector::ManagedInformationAgent::AssemblyDetails>>,0>>::find(unsigned __int64 const &)
0x180039348  mov     rbx, [rbp+57h+hObject]
0x18003934c  mov     rax, [rbp+57h+var_78]
0x180039350  cmp     rbx, [rax+108h]
0x180039357  lfence
0x18003935a  jnz     short loc_180039394
0x18003935c  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x180039363  add     rcx, 0A8h; this
0x18003936a  mov     rax, [rbp+57h+var_B0]
0x18003936e  cmp     qword ptr [rax+18h], 7
0x180039373  jbe     short loc_180039379
0x180039375  mov     rax, [rdi+18h]
0x180039379  mov     r9, rax
0x18003937c  lea     r8, aCouldNotFindAs; "Could not find assembly details for '%s"...
0x180039383  lea     rdx, aDAWork1SSource_1; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x18003938a  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x18003938f  jmp     loc_180039476
0x180039394  cmp     dword ptr [rsi-8], 1
0x180039398  jle     short loc_1800393AA
0x18003939a  mov     edx, [rsi-10h]
0x18003939d  lea     rcx, [rbp+57h+var_90]
0x1800393a1  call    ?Fork@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::Fork(int)
0x1800393a6  mov     rsi, [rbp+57h+var_90]
0x1800393aa  mov     qword ptr [rsp+100h+dwCreationDisposition], rsi
0x1800393af  mov     rax, [rbp+57h+var_B0]
0x1800393b3  mov     r9, [rax+28h]
0x1800393b7  mov     r8d, [rbx+20h]
0x1800393bb  lea     rdx, aLuLluS; "%lu;%llu;%s\n"
0x1800393c2  lea     rcx, [rbp+57h+var_88]
0x1800393c6  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x1800393cb  mov     r15, [rbp+57h+var_88]
0x1800393cf  mov     edx, [r15-10h]
0x1800393d3  lea     ebx, [rdx+rdx]
0x1800393d6  cmp     dword ptr [r15-8], 1
0x1800393db  jle     short loc_1800393EA
0x1800393dd  lea     rcx, [rbp+57h+var_88]
0x1800393e1  call    ?Fork@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::Fork(int)
0x1800393e6  mov     r15, [rbp+57h+var_88]
0x1800393ea  mov     qword ptr [rsp+100h+dwCreationDisposition], 0; lpOverlapped
  ... truncated ...
```
