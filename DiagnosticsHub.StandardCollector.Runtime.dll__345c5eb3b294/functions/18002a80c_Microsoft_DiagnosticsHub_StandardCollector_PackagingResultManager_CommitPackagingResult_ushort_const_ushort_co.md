# Microsoft::DiagnosticsHub::StandardCollector::PackagingResultManager::CommitPackagingResult(ushort const *,ushort const *,bool,ushort * *)

- ea: `0x18002a80c`
- end: `0x18002af98`
- name: `?CommitPackagingResult@PackagingResultManager@StandardCollector@DiagnosticsHub@Microsoft@@QEAAJPEBG0_NPEAPEAG@Z`
- size: `1932`
- prototype: `__int64 __fastcall(Microsoft::DiagnosticsHub::StandardCollector::PackagingResultManager *this, unsigned __int16 *, wchar_t *, char, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `22`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000b150`

## callees

- `0x180002354`
- `0x1800023c4`
- `0x180002604`
- `0x18000288c`
- `0x18000a0f0`
- `0x18000a2d0`
- `0x18002a6b8`
- `0x18002a80c`
- `0x18002b418`
- `0x18002b520`
- `0x18002d9a4`
- `0x18002e994`
- `0x18002eaac`
- `0x18002eb3c`
- `0x18003d864`
- `0x180041834`
- `0x180041a48`
- `0x180049b04`
- `0x180049b50`
- `0x18004a078`
- `0x18004ad58`
- `0x18004b640`

## import_xrefs

- `VCRUNTIME140!wcschr` at `0x18002a8b6`
- `VCRUNTIME140!wcschr` at `0x18002a8b6`
- `KERNEL32!MoveFileW` at `0x18002ab2e`
- `KERNEL32!MoveFileW` at `0x18002ab2e`
- `KERNEL32!LocalFree` at `0x18002ac6e`
- `KERNEL32!LocalFree` at `0x18002ac6e`
- `KERNEL32!GetLastError` at `0x18002ab37`
- `KERNEL32!GetLastError` at `0x18002ab37`
- `ole32!CoCreateGuid` at `0x18002a947`
- `ole32!CoCreateGuid` at `0x18002a947`
- `ole32!CoImpersonateClient` at `0x18002ab12`
- `ole32!CoImpersonateClient` at `0x18002ab12`
- `ole32!CoRevertToSelf` at `0x18002ab40`
- `ole32!CoRevertToSelf` at `0x18002ab40`
- `ole32!StringFromGUID2` at `0x18002a970`
- `ole32!StringFromGUID2` at `0x18002a970`
- `OLEAUT32!__imp_SysFreeString` at `0x18002af0b`
- `OLEAUT32!__imp_SysFreeString` at `0x18002af0b`
- `api-ms-win-crt-string-l1-1-0!wcsncmp` at `0x18002adb6`
- `api-ms-win-crt-string-l1-1-0!wcsncmp` at `0x18002add0`
- `api-ms-win-crt-string-l1-1-0!wcsncmp` at `0x18002adb6`
- `api-ms-win-crt-string-l1-1-0!wcsncmp` at `0x18002add0`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x18002aa96`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x18002aaba`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x18002aade`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x18002adeb`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x18002aa96`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x18002aaba`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x18002aade`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x18002adeb`

## string_xrefs

- `0x18002abd5`: `Failed to commit package path (CommitOptions: %#08x). HRESULT: %#08x`

## pseudocode

```c
__int64 __fastcall Microsoft::DiagnosticsHub::StandardCollector::PackagingResultManager::CommitPackagingResult(
        Microsoft::DiagnosticsHub::StandardCollector::PackagingResultManager *this,
        unsigned __int16 *a2,
        wchar_t *a3,
        char a4,
        unsigned __int16 **a5)
{
  int DirectoryPath; // r14d
  int v11; // ebx
  int v12; // ecx
  bool v13; // dl
  int v14; // eax
  OLECHAR *v15; // rbx
  void *v16; // r14
  __int64 v17; // rdi
  unsigned __int16 *v18; // rcx
  unsigned __int16 v19; // ax
  unsigned __int16 *v20; // rax
  Microsoft::DiagnosticsHub::StandardCollector::SecuredDirectory *v21; // rdi
  struct ATL::IAtlStringMgr *Instance; // rax
  const WCHAR *v23; // rsi
  struct DhPackaging::IDhPackage *v24; // rcx
  int v25; // eax
  int v26; // eax
  int v27; // eax
  BOOL v28; // r12d
  signed int LastError; // r15d
  const unsigned __int16 *v30; // rdx
  unsigned int v31; // esi
  const WCHAR *v32; // rdi
  const unsigned __int16 *v33; // r8
  const struct _GUID *v34; // rdx
  wchar_t *v35; // r15
  _DWORD *v36; // rax
  int v37; // edx
  unsigned int v38; // r14d
  int v39; // eax
  DiagHubCommon::LogStream *v40; // rdi
  __int64 FileSizeInBytes; // rax
  OLECHAR *v42; // rax
  _QWORD *v43; // rdx
  __int64 v44; // [rsp+20h] [rbp-E0h]
  bool v45; // [rsp+30h] [rbp-D0h]
  void *Block; // [rsp+38h] [rbp-C8h] BYREF
  wchar_t *String1; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v48; // [rsp+48h] [rbp-B8h]
  LPCWSTR lpNewFileName; // [rsp+50h] [rbp-B0h] BYREF
  HLOCAL hMem[3]; // [rsp+58h] [rbp-A8h] BYREF
  OLECHAR sz[39]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 v52[73]; // [rsp+BEh] [rbp-42h] BYREF
  struct DhPackaging::IDhPackage *v53; // [rsp+150h] [rbp+50h] BYREF
  GUID pguid; // [rsp+158h] [rbp+58h] BYREF
  LPCWSTR lpExistingFileName[3]; // [rsp+168h] [rbp+68h] BYREF

  hMem[0] = a5;
  if ( a2 && a3 && a5 )
  {
    *a5 = 0;
    lpExistingFileName[0] = (LPCWSTR)this;
    Block = Microsoft::DiagnosticsHub::StandardCollector::PackagingResultManager::Initialize;
    std::call_once<void (Microsoft::DiagnosticsHub::StandardCollector::PackagingResultManager::*)(void),Microsoft::DiagnosticsHub::StandardCollector::PackagingResultManager *>((LPINIT_ONCE)this);
    if ( !*((_QWORD *)this + 4) )
      return 2147943568LL;
    CodeMarker(25219);
    if ( wcschr(a3, 0x5Cu) )
    {
      DirectoryPath = -2147024809;
LABEL_91:
      CodeMarker(25220);
      return (unsigned int)DirectoryPath;
    }
    v11 = 0;
    v12 = *((_DWORD *)this + 2);
    if ( v12 )
    {
      if ( (unsigned int)(v12 - 1) >= 2 )
      {
        DirectoryPath = -2147467259;
        goto LABEL_91;
      }
    }
    else
    {
      v11 = 1;
    }
    v53 = 0;
    if ( a4 )
    {
      v11 |= 0x100u;
      v13 = 1;
    }
    else
    {
      v13 = 0;
    }
    DirectoryPath = Microsoft::DiagnosticsHub::StandardCollector::SequentialPackageHandler::ResetInternal(
                      *((Microsoft::DiagnosticsHub::StandardCollector::SequentialPackageHandler **)this + 4),
                      v13,
                      &v53);
    if ( DirectoryPath < 0 )
    {
LABEL_89:
      if ( v53 )
        (*(void (__fastcall **)(struct DhPackaging::IDhPackage *))(*(_QWORD *)v53 + 16LL))(v53);
      goto LABEL_91;
    }
    v14 = *((_DWORD *)this + 6);
    if ( v14 == -1 )
      v14 = v11;
    v48 = v14;
    v15 = 0;
    lpNewFileName = 0;
    v45 = (v14 & 1) == 0;
    if ( (v14 & 1) != 0 )
    {
      lpExistingFileName[0] = 0;
      DirectoryPath = Microsoft::DiagnosticsHub::StandardCollector::SecuredDirectory::Create(
                        a2,
                        a3,
                        *((void **)this + 2),
                        0,
                        (Microsoft::DiagnosticsHub::StandardCollector::SecuredDirectory **)lpExistingFileName);
      v21 = (Microsoft::DiagnosticsHub::StandardCollector::SecuredDirectory *)lpExistingFileName[0];
      if ( DirectoryPath >= 0 )
      {
        DirectoryPath = Microsoft::DiagnosticsHub::StandardCollector::SecuredDirectory::GetDirectoryPath(
                          (Microsoft::DiagnosticsHub::StandardCollector::SecuredDirectory *)lpExistingFileName[0],
                          (const unsigned __int16 **)&String1);
        if ( DirectoryPath >= 0 )
        {
          Block = 0;
          v35 = String1;
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
            &Block,
            String1);
          v36 = Block;
          v37 = *((_DWORD *)Block - 4);
          LODWORD(String1) = v37;
          v38 = v37 - 1;
          if ( v37 - 1 < 0 )
            goto LABEL_93;
          if ( (((*((_DWORD *)Block - 3) - v38) | (1 - *((_DWORD *)Block - 2))) & 0x80000000) != 0 )
          {
            _mm_lfence();
            ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(&Block, v38, 0);
            v36 = Block;
            v37 = (int)String1;
          }
          if ( (signed int)v38 > *(v36 - 3) )
LABEL_93:
            ATL::AtlThrowImpl(-2147024809);
          *(v36 - 4) = v38;
          *((_WORD *)Block + v37 - 1) = 0;
          v31 = v48;
          LODWORD(String1) = (*(__int64 (__fastcall **)(struct DhPackaging::IDhPackage *, void *, _QWORD))(*(_QWORD *)v53 + 144LL))(
                               v53,
                               Block,
                               v48);
          DirectoryPath = Microsoft::DiagnosticsHub::StandardCollector::SecuredDirectory::ExposeDirectory(v21);
          if ( DirectoryPath >= 0 )
          {
            _mm_lfence();
            if ( wcsncmp(a2, L"\\\\?\\", 4u) && !wcsncmp(v35, L"\\\\?\\", 4u) )
              v35 += 4;
            if ( v35 )
              v39 = wcslen(v35);
            else
              v39 = 0;
            DirectoryPath = ATL::CComBSTR::Append((ATL::CComBSTR *)&lpNewFileName, v35, v39);
            if ( DirectoryPath >= 0 )
            {
              v30 = (const unsigned __int16 *)((char *)Block - 24);
              if ( _InterlockedExchangeAdd((volatile signed __int32 *)Block - 2, 0xFFFFFFFF) <= 1 )
              {
                _mm_lfence();
                (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v30 + 8LL))(*(_QWORD *)v30);
              }
              if ( v21 )
              {
                Microsoft::DiagnosticsHub::StandardCollector::SecuredDirectory::~SecuredDirectory(v21);
                operator delete(v21);
              }
              v15 = (OLECHAR *)lpNewFileName;
              goto LABEL_49;
            }
            v15 = (OLECHAR *)lpNewFileName;
          }
          v43 = (char *)Block - 24;
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)Block - 2, 0xFFFFFFFF) <= 1 )
          {
            _mm_lfence();
            (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v43 + 8LL))(*v43);
          }
        }
      }
    }
    else
    {
      DirectoryPath = CoCreateGuid(&pguid);
      if ( DirectoryPath < 0 )
      {
LABEL_88:
        SysFreeString(v15);
        goto LABEL_89;
      }
      Block = 0;
      v16 = (void *)*((_QWORD *)this + 2);
      v17 = 39;
      if ( !StringFromGUID2(&pguid, sz, 39) )
      {
        LODWORD(String1) = -2147024882;
        throw (long *)&String1;
      }
      v52[0] = 0;
      v52[39] = 0;
      v18 = v52;
      do
      {
        if ( v17 == 3 )
          break;
        v19 = *(v18 - 38);
        if ( !v19 )
          break;
        *v18++ = v19;
        --v17;
      }
      while ( v17 );
      v20 = v18 - 1;
      if ( v17 )
        v20 = v18;
      *v20 = 0;
      if ( !v17 )
        v52[0] = 0;
      DirectoryPath = Microsoft::DiagnosticsHub::StandardCollector::SecuredDirectory::Create(
                        a2,
                        v52,
                        v16,
                        1,
                        (Microsoft::DiagnosticsHub::StandardCollector::SecuredDirectory **)&Block);
      v21 = (Microsoft::DiagnosticsHub::StandardCollector::SecuredDirectory *)Block;
      if ( DirectoryPath >= 0 )
      {
        Instance = ATL::CAtlStringMgr::GetInstance();
        if ( !Instance )
          ATL::AtlThrowImpl(-2147467259);
        v23 = (const WCHAR *)((*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)Instance + 24LL))(Instance)
                            + 24);
        lpExistingFileName[0] = v23;
        DirectoryPath = Microsoft::DiagnosticsHub::StandardCollector::SecuredDirectory::GetDirectoryPath(
                          v21,
                          (const unsigned __int16 **)&String1);
        if ( DirectoryPath < 0 )
          goto LABEL_57;
        _mm_lfence();
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
          lpExistingFileName,
          L"%s%s%s",
          String1,
          a3,
          L".diagsession");
        v23 = lpExistingFileName[0];
        LODWORD(String1) = (*(__int64 (__fastcall **)(struct DhPackaging::IDhPackage *, LPCWSTR, _QWORD))(*(_QWORD *)v53 + 144LL))(
                             v53,
                             lpExistingFileName[0],
                             v48);
        v24 = v53;
        if ( v53 )
        {
          v53 = 0;
          (*(void (__fastcall **)(struct DhPackaging::IDhPackage *))(*(_QWORD *)v24 + 16LL))(v24);
        }
        _mm_lfence();
        v25 = wcslen(a2);
        DirectoryPath = ATL::CComBSTR::Append((ATL::CComBSTR *)&lpNewFileName, a2, v25);
        if ( DirectoryPath < 0
          || (v26 = wcslen(a3),
              DirectoryPath = ATL::CComBSTR::Append((ATL::CComBSTR *)&lpNewFileName, a3, v26),
              DirectoryPath < 0)
          || (v27 = wcslen(L".diagsession"),
              DirectoryPath = ATL::CComBSTR::Append((ATL::CComBSTR *)&lpNewFileName, L".diagsession", v27),
              DirectoryPath < 0)
          || (DirectoryPath = Microsoft::DiagnosticsHub::StandardCollector::SecuredDirectory::ExposeDirectory(v21),
              DirectoryPath < 0)
          || (DirectoryPath = CoImpersonateClient(), DirectoryPath < 0) )
        {
          v15 = (OLECHAR *)lpNewFileName;
        }
        else
        {
          v15 = (OLECHAR *)lpNewFileName;
          v28 = MoveFileW(v23, lpNewFileName);
          LastError = GetLastError();
          DirectoryPath = CoRevertToSelf();
          if ( DirectoryPath >= 0 )
          {
            if ( !v28 )
            {
              DirectoryPath = (unsigned __int16)LastError | 0x80070000;
              if ( LastError <= 0 )
                DirectoryPath = LastError;
              goto LABEL_57;
            }
            v30 = v23 - 12;
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)v23 - 2, 0xFFFFFFFF) <= 1 )
            {
              _mm_lfence();
              (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v30 + 8LL))(*(_QWORD *)v30);
            }
            if ( v21 )
            {
              Microsoft::DiagnosticsHub::StandardCollector::SecuredDirectory::~SecuredDirectory(v21);
              operator delete(v21);
            }
            v31 = v48;
LABEL_49:
            v32 = (const WCHAR *)(int)String1;
            if ( (_DWORD)String1 )
            {
              LODWORD(v44) = (_DWORD)String1;
              DiagHubCommon::LogStream::Write(
                (DiagHubCommon::LogStream *)((char *)_logger + 168),
                L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\PackagingResultManager.cpp",
                L"Failed to commit package path (CommitOptions: %#08x). HRESULT: %#08x",
                v31,
                v44);
              lpExistingFileName[0] = v15;
              lpExistingFileName[1] = v32;
              hMem[0] = 0;
              hMem[1] = (HLOCAL)3775987772LL;
              DiagHubCommon::HResultFormatter::Init(
                (DiagHubCommon::HResultFormatter *)hMem,
                *((_WORD *)this + 6),
                -518979524,
                (const void **const)lpExistingFileName);
              v34 = (const struct _GUID *)L"<unknown error>";
              if ( hMem[0] )
                v34 = (const struct _GUID *)hMem[0];
              DiagHubCommon::SetErrorInfo((DiagHubCommon *)&IID_ICollectionSession, v34, v33);
              DirectoryPath = (int)hMem[1];
              if ( hMem[0] && hMem[0] != &word_180055D48 && hMem[0] != L"Out of memory" )
                LocalFree(hMem[0]);
            }
            else
            {
              if ( v45 )
              {
                v40 = _logger;
                if ( *((_QWORD *)_logger + 28) != *((_QWORD *)_logger + 29) )
                {
                  FileSizeInBytes = DiagHubCommon::GetFileSizeInBytes((DiagHubCommon *)v15, v30);
                  DiagHubCommon::LogStream::Write(
                    (DiagHubCommon::LogStream *)((char *)v40 + 224),
                    L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\PackagingResultManager.cpp",
                    L"ArchivedFile(Name,ByteSize)",
                    L"(%s,%I64d)",
                    v15,
                    FileSizeInBytes);
                }
              }
              v42 = v15;
              v15 = 0;
              *(_QWORD *)hMem[0] = v42;
              DirectoryPath = 0;
            }
            goto LABEL_88;
          }
        }
LABEL_57:
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v23 - 2, 0xFFFFFFFF) <= 1 )
        {
          _mm_lfence();
          (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v23 - 3) + 8LL))(*((_QWORD *)v23 - 3));
        }
      }
    }
    if ( v21 )
    {
      Microsoft::DiagnosticsHub::StandardCollector::SecuredDirectory::~SecuredDirectory(v21);
      operator delete(v21);
    }
    goto LABEL_88;
  }
  return 2147500035LL;
}

```

## disassembly

```asm
0x18002a80c  mov     [rsp-8+arg_18], rbx
0x18002a811  push    rbp
0x18002a812  push    rsi
0x18002a813  push    rdi
0x18002a814  push    r12
0x18002a816  push    r13
0x18002a818  push    r14
0x18002a81a  push    r15
0x18002a81c  lea     rbp, [rsp-90h]
0x18002a824  sub     rsp, 190h
0x18002a82b  mov     rax, cs:__security_cookie
0x18002a832  xor     rax, rsp
0x18002a835  mov     [rbp+0C0h+var_40], rax
0x18002a83c  mov     dil, r9b
0x18002a83f  mov     r15, r8
0x18002a842  mov     r12, rdx
0x18002a845  mov     r13, rcx
0x18002a848  mov     rax, [rbp+0C0h+arg_20]
0x18002a84f  mov     [rsp+1C0h+hMem], rax
0x18002a854  xor     r14d, r14d
0x18002a857  test    rdx, rdx
0x18002a85a  jz      loc_18002AF39
0x18002a860  test    r8, r8
0x18002a863  jz      loc_18002AF39
0x18002a869  test    rax, rax
0x18002a86c  jz      loc_18002AF39
0x18002a872  mov     [rax], r14
0x18002a875  mov     [rbp+0C0h+lpExistingFileName], rcx
0x18002a879  lea     rax, ?Initialize@PackagingResultManager@StandardCollector@DiagnosticsHub@Microsoft@@AEAAXXZ; Microsoft::DiagnosticsHub::StandardCollector::PackagingResultManager::Initialize(void)
0x18002a880  mov     [rsp+1C0h+Block], rax
0x18002a885  lea     r8, [rbp+0C0h+lpExistingFileName]
0x18002a889  lea     rdx, [rsp+1C0h+Block]
0x18002a88e  call    ??$call_once@P8PackagingResultManager@StandardCollector@DiagnosticsHub@Microsoft@@EAAXXZPEAV1234@@std@@YAXAEAUonce_flag@0@$$QEAP8PackagingResultManager@StandardCollector@DiagnosticsHub@Microsoft@@EAAXXZ$$QEAPEAV2345@@Z; std::call_once<void (Microsoft::DiagnosticsHub::StandardCollector::PackagingResultManager::*)(void),Microsoft::DiagnosticsHub::StandardCollector::PackagingResultManager *>(std::once_flag &,void (Microsoft::DiagnosticsHub::StandardCollector::PackagingResultManager::*&&)(void),Microsoft::DiagnosticsHub::StandardCollector::PackagingResultManager * &&)
0x18002a893  cmp     [r13+20h], r14
0x18002a897  jnz     short loc_18002A8A3
0x18002a899  mov     eax, 80070490h
0x18002a89e  jmp     loc_18002AF3E
0x18002a8a3  mov     ecx, 6283h
0x18002a8a8  call    ?CodeMarker@@YAXW4CodeMarkerEvent@Performance@Internal@Microsoft@@@Z; CodeMarker(Microsoft::Internal::Performance::CodeMarkerEvent)
0x18002a8ad  nop
0x18002a8ae  mov     edx, 5Ch ; '\'; Ch
0x18002a8b3  mov     rcx, r15; Str
0x18002a8b6  call    cs:__imp_wcschr
0x18002a8bc  test    rax, rax
0x18002a8bf  jz      short loc_18002A8CC
0x18002a8c1  mov     r14d, 80070057h
0x18002a8c7  jmp     loc_18002AF29
0x18002a8cc  mov     ebx, r14d
0x18002a8cf  mov     ecx, [r13+8]
0x18002a8d3  mov     esi, 1
0x18002a8d8  test    ecx, ecx
0x18002a8da  jz      short loc_18002A8EF
0x18002a8dc  sub     ecx, esi
0x18002a8de  jz      short loc_18002A8F1
0x18002a8e0  cmp     ecx, esi
0x18002a8e2  jz      short loc_18002A8F1
0x18002a8e4  mov     r14d, 80004005h
0x18002a8ea  jmp     loc_18002AF29
0x18002a8ef  mov     ebx, esi
0x18002a8f1  mov     [rbp+0C0h+var_70], r14
0x18002a8f5  mov     rcx, [r13+20h]; this
0x18002a8f9  lea     r8, [rbp+0C0h+var_70]; struct DhPackaging::IDhPackage **
0x18002a8fd  test    dil, dil
0x18002a900  jz      short loc_18002A90B
0x18002a902  bts     ebx, 8
0x18002a906  mov     dl, sil
0x18002a909  jmp     short loc_18002A90D
0x18002a90b  xor     edx, edx; bool
0x18002a90d  call    ?ResetInternal@SequentialPackageHandler@StandardCollector@DiagnosticsHub@Microsoft@@AEAAJ_NPEAPEAUIDhPackage@DhPackaging@@@Z; Microsoft::DiagnosticsHub::StandardCollector::SequentialPackageHandler::ResetInternal(bool,DhPackaging::IDhPackage * *)
0x18002a912  xor     edi, edi
0x18002a914  test    eax, eax
0x18002a916  mov     r14d, eax
0x18002a919  js      loc_18002AF12
0x18002a91f  mov     eax, [r13+18h]
0x18002a923  cmp     eax, 0FFFFFFFFh
0x18002a926  cmovz   eax, ebx
0x18002a929  mov     [rsp+1C0h+var_178], eax
0x18002a92d  mov     ebx, edi
0x18002a92f  mov     [rsp+1C0h+lpNewFileName], rbx
0x18002a934  not     al
0x18002a936  and     al, sil
0x18002a939  mov     [rsp+1C0h+var_190], al
0x18002a93d  jz      loc_18002ACA8
0x18002a943  lea     rcx, [rbp+0C0h+pguid]; pguid
0x18002a947  call    cs:__imp_CoCreateGuid
0x18002a94d  mov     r14d, eax
0x18002a950  test    eax, eax
0x18002a952  js      loc_18002AF08
0x18002a958  mov     [rsp+1C0h+Block], rdi
0x18002a95d  mov     r14, [r13+10h]
0x18002a961  lea     edi, [rbx+27h]
0x18002a964  mov     r8d, edi; cchMax
0x18002a967  lea     rdx, [rsp+1C0h+sz]; lpsz
0x18002a96c  lea     rcx, [rbp+0C0h+pguid]; rguid
0x18002a970  call    cs:__imp_StringFromGUID2
0x18002a976  xor     edx, edx
0x18002a978  test    eax, eax
0x18002a97a  jz      loc_18002AF73
0x18002a980  mov     [rbp+0C0h+var_102], dx
0x18002a984  mov     [rbp+0C0h+var_B4], dx
0x18002a988  lea     rcx, [rbp+0C0h+var_102]
0x18002a98c  lea     rax, [rdi-3]
0x18002a990  test    rax, rax
0x18002a993  jz      short loc_18002A9AA
0x18002a995  movzx   eax, word ptr [rcx-4Ch]
0x18002a999  test    ax, ax
0x18002a99c  jz      short loc_18002A9AA
0x18002a99e  mov     [rcx], ax
0x18002a9a1  add     rcx, 2
0x18002a9a5  sub     rdi, rsi
0x18002a9a8  jnz     short loc_18002A98C
0x18002a9aa  lea     rax, [rcx-2]
0x18002a9ae  test    rdi, rdi
0x18002a9b1  cmovnz  rax, rcx
0x18002a9b5  mov     [rax], dx
0x18002a9b8  jnz     short loc_18002A9BE
0x18002a9ba  mov     [rbp+0C0h+var_102], dx
0x18002a9be  lea     rax, [rsp+1C0h+Block]
0x18002a9c3  mov     [rsp+1C0h+var_1A0], rax; __int64
0x18002a9c8  mov     r9b, sil; bool
0x18002a9cb  mov     r8, r14; void *
0x18002a9ce  lea     rdx, [rbp+0C0h+var_102]; unsigned __int16 *
0x18002a9d2  mov     rcx, r12; unsigned __int16 *
0x18002a9d5  call    ?Create@SecuredDirectory@StandardCollector@DiagnosticsHub@Microsoft@@SAJPEBG0PEAX_NAEAV?$unique_ptr@VSecuredDirectory@StandardCollector@DiagnosticsHub@Microsoft@@U?$default_delete@VSecuredDirectory@StandardCollector@DiagnosticsHub@Microsoft@@@std@@@std@@@Z; Microsoft::DiagnosticsHub::StandardCollector::SecuredDirectory::Create(ushort const *,ushort const *,void *,bool,std::unique_ptr<Microsoft::DiagnosticsHub::StandardCollector::SecuredDirectory> &)
0x18002a9da  mov     r14d, eax
0x18002a9dd  mov     rdi, [rsp+1C0h+Block]
0x18002a9e2  test    eax, eax
0x18002a9e4  js      loc_18002ACA3
0x18002a9ea  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x18002a9ef  mov     rcx, rax
0x18002a9f2  test    rax, rax
0x18002a9f5  jz      loc_18002AF8D
0x18002a9fb  mov     rax, [rax]
0x18002a9fe  mov     rax, [rax+18h]
0x18002aa02  call    cs:__guard_dispatch_icall_fptr
0x18002aa08  lea     rsi, [rax+18h]
0x18002aa0c  mov     [rbp+0C0h+lpExistingFileName], rsi
0x18002aa10  lea     rdx, [rsp+1C0h+String1]; unsigned __int16 **
0x18002aa15  mov     rcx, rdi; this
0x18002aa18  call    ?GetDirectoryPath@SecuredDirectory@StandardCollector@DiagnosticsHub@Microsoft@@QEAAJPEAPEBG@Z; Microsoft::DiagnosticsHub::StandardCollector::SecuredDirectory::GetDirectoryPath(ushort const * *)
0x18002aa1d  mov     r14d, eax
0x18002aa20  test    eax, eax
0x18002aa22  js      loc_18002AC7E
0x18002aa28  lfence
0x18002aa2b  lea     rbx, aDiagsession; ".diagsession"
0x18002aa32  mov     [rsp+1C0h+var_1A0], rbx
0x18002aa37  mov     r9, r15
0x18002aa3a  mov     r8, [rsp+1C0h+String1]
0x18002aa3f  lea     rdx, aSSS_0; "%s%s%s"
0x18002aa46  lea     rcx, [rbp+0C0h+lpExistingFileName]
0x18002aa4a  call    ?AppendFormat@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AppendFormat(ushort const *,...)
0x18002aa4f  mov     rcx, [rbp+0C0h+var_70]
0x18002aa53  mov     rax, [rcx]
0x18002aa56  mov     r8d, [rsp+1C0h+var_178]
0x18002aa5b  mov     rsi, [rbp+0C0h+lpExistingFileName]
0x18002aa5f  mov     rdx, rsi
0x18002aa62  mov     rax, [rax+90h]
0x18002aa69  call    cs:__guard_dispatch_icall_fptr
0x18002aa6f  mov     dword ptr [rsp+1C0h+String1], eax
0x18002aa73  mov     rcx, [rbp+0C0h+var_70]
0x18002aa77  xor     eax, eax
0x18002aa79  test    rcx, rcx
0x18002aa7c  jz      short loc_18002AA90
0x18002aa7e  mov     [rbp+0C0h+var_70], rax
0x18002aa82  mov     rdx, [rcx]
0x18002aa85  mov     rax, [rdx+10h]
0x18002aa89  call    cs:__guard_dispatch_icall_fptr
0x18002aa8f  nop
0x18002aa90  lfence
0x18002aa93  mov     rcx, r12; String
0x18002aa96  call    cs:__imp_wcslen
0x18002aa9c  mov     r8d, eax; int
0x18002aa9f  mov     rdx, r12; unsigned __int16 *
0x18002aaa2  lea     rcx, [rsp+1C0h+lpNewFileName]; this
0x18002aaa7  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x18002aaac  mov     r14d, eax
0x18002aaaf  test    eax, eax
0x18002aab1  js      loc_18002AC79
0x18002aab7  mov     rcx, r15; String
0x18002aaba  call    cs:__imp_wcslen
0x18002aac0  mov     r8d, eax; int
0x18002aac3  mov     rdx, r15; unsigned __int16 *
0x18002aac6  lea     rcx, [rsp+1C0h+lpNewFileName]; this
0x18002aacb  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x18002aad0  mov     r14d, eax
0x18002aad3  test    eax, eax
0x18002aad5  js      loc_18002AC79
0x18002aadb  mov     rcx, rbx; String
0x18002aade  call    cs:__imp_wcslen
0x18002aae4  mov     r8d, eax; int
0x18002aae7  mov     rdx, rbx; unsigned __int16 *
0x18002aaea  lea     rcx, [rsp+1C0h+lpNewFileName]; this
0x18002aaef  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x18002aaf4  mov     r14d, eax
0x18002aaf7  test    eax, eax
0x18002aaf9  js      loc_18002AC79
0x18002aaff  mov     rcx, rdi; this
0x18002ab02  call    ?ExposeDirectory@SecuredDirectory@StandardCollector@DiagnosticsHub@Microsoft@@QEAAJXZ; Microsoft::DiagnosticsHub::StandardCollector::SecuredDirectory::ExposeDirectory(void)
0x18002ab07  mov     r14d, eax
0x18002ab0a  test    eax, eax
0x18002ab0c  js      loc_18002AC79
0x18002ab12  call    cs:__imp_CoImpersonateClient
0x18002ab18  mov     r14d, eax
0x18002ab1b  test    eax, eax
0x18002ab1d  js      loc_18002AC79
0x18002ab23  mov     rbx, [rsp+1C0h+lpNewFileName]
0x18002ab28  mov     rdx, rbx; lpNewFileName
0x18002ab2b  mov     rcx, rsi; lpExistingFileName
0x18002ab2e  call    cs:__imp_MoveFileW
0x18002ab34  mov     r12d, eax
0x18002ab37  call    cs:__imp_GetLastError
0x18002ab3d  mov     r15d, eax
0x18002ab40  call    cs:__imp_CoRevertToSelf
0x18002ab46  mov     r14d, eax
0x18002ab49  test    eax, eax
0x18002ab4b  js      loc_18002AC7E
0x18002ab51  test    r12d, r12d
0x18002ab54  jnz     short loc_18002AB6D
0x18002ab56  movzx   r14d, r15w
0x18002ab5a  or      r14d, 80070000h
0x18002ab61  test    r15d, r15d
0x18002ab64  cmovle  r14d, r15d
0x18002ab68  jmp     loc_18002AC7E
0x18002ab6d  lea     rdx, [rsi-18h]
0x18002ab71  or      eax, 0FFFFFFFFh
0x18002ab74  lock xadd [rdx+10h], eax
0x18002ab79  xor     r12d, r12d
0x18002ab7c  sub     eax, 1
0x18002ab7f  jg      short loc_18002AB95
0x18002ab81  lfence
0x18002ab84  mov     rcx, [rdx]
0x18002ab87  mov     rax, [rcx]
0x18002ab8a  mov     rax, [rax+8]
0x18002ab8e  call    cs:__guard_dispatch_icall_fptr
0x18002ab94  nop
0x18002ab95  test    rdi, rdi
0x18002ab98  jz      short loc_18002ABAF
0x18002ab9a  mov     rcx, rdi; this
0x18002ab9d  call    ??1SecuredDirectory@StandardCollector@DiagnosticsHub@Microsoft@@QEAA@XZ; Microsoft::DiagnosticsHub::StandardCollector::SecuredDirectory::~SecuredDirectory(void)
0x18002aba2  mov     edx, 0D0h
0x18002aba7  mov     rcx, rdi; Block
0x18002abaa  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002abaf  mov     esi, [rsp+1C0h+var_178]
0x18002abb3  movsxd  rdi, dword ptr [rsp+1C0h+String1]
0x18002abb8  test    edi, edi
0x18002abba  jz      loc_18002AE5A
0x18002abc0  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x18002abc7  add     rcx, 0A8h; this
0x18002abce  mov     dword ptr [rsp+1C0h+var_1A0], edi
0x18002abd2  mov     r9d, esi
0x18002abd5  lea     r8, aFailedToCommit; "Failed to commit package path (CommitOp"...
0x18002abdc  lea     rdx, aDAWork1SSource_20; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x18002abe3  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x18002abe8  mov     [rbp+0C0h+lpExistingFileName], rbx
0x18002abec  mov     [rbp+0C0h+var_50], rdi
0x18002abf0  xorps   xmm0, xmm0
0x18002abf3  movups  xmmword ptr [rsp+1C0h+hMem], xmm0
0x18002abf8  mov     [rsp+1C0h+hMem], r12
0x18002abfd  mov     r8d, 0E111003Ch; int
0x18002ac03  mov     dword ptr [rsp+1C0h+hMem+8], r8d
0x18002ac08  lea     r9, [rbp+0C0h+lpExistingFileName]; void **
0x18002ac0c  movzx   edx, word ptr [r13+0Ch]; unsigned __int16
0x18002ac11  lea     rcx, [rsp+1C0h+hMem]; this
0x18002ac16  call    ?Init@HResultFormatter@DiagHubCommon@@AEAAXGJQEAPEBX@Z; DiagHubCommon::HResultFormatter::Init(ushort,long,void const * * const)
0x18002ac1b  nop
0x18002ac1c  lea     rdx, aUnknownError; "<unknown error>"
0x18002ac23  mov     rax, [rsp+1C0h+hMem]
0x18002ac28  test    rax, rax
0x18002ac2b  cmovnz  rdx, rax; struct _GUID *
0x18002ac2f  lea     rcx, IID_ICollectionSession; this
0x18002ac36  call    ?SetErrorInfo@DiagHubCommon@@YAXAEBU_GUID@@PEBG@Z; DiagHubCommon::SetErrorInfo(_GUID const &,ushort const *)
0x18002ac3b  mov     r14d, dword ptr [rsp+1C0h+hMem+8]
0x18002ac40  mov     rcx, [rsp+1C0h+hMem]; hMem
0x18002ac45  test    rcx, rcx
0x18002ac48  jz      loc_18002AF08
0x18002ac4e  lea     rax, word_180055D48
0x18002ac55  cmp     rcx, rax
0x18002ac58  jz      loc_18002AF08
0x18002ac5e  lea     rax, aOutOfMemory; "Out of memory"
0x18002ac65  cmp     rcx, rax
0x18002ac68  jz      loc_18002AF08
0x18002ac6e  call    cs:__imp_LocalFree
0x18002ac74  jmp     loc_18002AF08
0x18002ac79  mov     rbx, [rsp+1C0h+lpNewFileName]
0x18002ac7e  lea     rdx, [rsi-18h]
0x18002ac82  or      eax, 0FFFFFFFFh
0x18002ac85  lock xadd [rdx+10h], eax
0x18002ac8a  sub     eax, 1
0x18002ac8d  jg      short loc_18002ACA3
0x18002ac8f  lfence
0x18002ac92  mov     rcx, [rdx]
0x18002ac95  mov     rax, [rcx]
0x18002ac98  mov     rax, [rax+8]
0x18002ac9c  call    cs:__guard_dispatch_icall_fptr
0x18002aca2  nop
0x18002aca3  jmp     loc_18002AEED
0x18002aca8  mov     [rbp+0C0h+lpExistingFileName], rdi
0x18002acac  lea     rax, [rbp+0C0h+lpExistingFileName]
0x18002acb0  mov     [rsp+1C0h+var_1A0], rax; __int64
0x18002acb5  xor     r9d, r9d; bool
  ... truncated ...
```
