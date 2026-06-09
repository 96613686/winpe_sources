# WindowsPerformanceRecorder::Impl::RemoveDirectoryRecursively(ushort const *)

- ea: `0x18005ce34`
- end: `0x18005d01c`
- name: `?RemoveDirectoryRecursively@Impl@WindowsPerformanceRecorder@@YAJPEBG@Z`
- size: `488`
- prototype: `__int64 __fastcall(WindowsPerformanceRecorder::Impl *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800599c0`
- `0x18005ce34`

## callees

- `0x180008330`
- `0x1800102d8`
- `0x18001c458`
- `0x18001c820`
- `0x18001e6e0`
- `0x18004b39c`
- `0x18004ece0`
- `0x180057a88`
- `0x180058764`
- `0x18005ce34`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18005cfa5`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18005cfa5`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18005cead`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18005cead`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18005cfe3`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18005cfe3`

## string_xrefs

- `0x18005cf65`: `COMGUARD`
- `0x18005cf7a`: `RemoveDirectoryRecursively`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall WindowsPerformanceRecorder::Impl::RemoveDirectoryRecursively(
        const WCHAR *this,
        const unsigned __int16 *a2)
{
  unsigned int v3; // ebx
  __int64 result; // rax
  const unsigned __int16 *v5; // rdx
  signed int v6; // ebx
  unsigned int Error; // ebx
  int i; // eax
  const char *v9; // [rsp+28h] [rbp-2C0h]
  LPCWSTR lpPathName[2]; // [rsp+30h] [rbp-2B8h] BYREF
  ATL::CAtlException *v11; // [rsp+40h] [rbp-2A8h] BYREF
  void **v12; // [rsp+50h] [rbp-298h] BYREF
  const WCHAR *v13; // [rsp+58h] [rbp-290h]
  const wchar_t *v14; // [rsp+60h] [rbp-288h]
  HANDLE hFindFile; // [rsp+68h] [rbp-280h]
  __int64 v16; // [rsp+70h] [rbp-278h]
  _WIN32_FIND_DATAW FindFileData; // [rsp+78h] [rbp-270h] BYREF

  lpPathName[1] = (LPCWSTR)-2LL;
  v12 = &WindowsPerformanceRecorder::Impl::CAutoFindFile::`vftable';
  v13 = this;
  v14 = L"*.*";
  hFindFile = (HANDLE)-1LL;
  v16 = 0;
  try
  {
    WindowsPerformanceRecorder::Impl::CAutoFindFile::Begin((WindowsPerformanceRecorder::Impl::CAutoFindFile *)&v12);
    for ( i = HIDWORD(v16); i; HIDWORD(v16) = i )
    {
      if ( FindFileData.cFileName[0] != 46
        || FindFileData.cFileName[1] && (FindFileData.cFileName[1] != 46 || FindFileData.cFileName[2]) )
      {
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(lpPathName);
        ATL::CSimpleStringT<unsigned short,0>::SetString(lpPathName, v13);
        ATL::CSimpleStringT<unsigned short,0>::Append(lpPathName, L"\\");
        ATL::CSimpleStringT<unsigned short,0>::Append(lpPathName, FindFileData.cFileName);
        if ( (FindFileData.dwFileAttributes & 0x10) != 0 )
        {
          v6 = WindowsPerformanceRecorder::Impl::RemoveDirectoryRecursively(
                 (WindowsPerformanceRecorder::Impl *)lpPathName[0],
                 v5);
          if ( v6 < 0 )
          {
            WindowsPerformanceRecorder::TraceHR(
              (WindowsPerformanceRecorder *)2,
              (unsigned __int8)"RemoveDirectoryRecursively",
              (const char *)0x122,
              v6,
              "COMGUARD",
              v9);
            WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)lpPathName);
            WindowsPerformanceRecorder::Impl::CAutoFindFile::~CAutoFindFile((WindowsPerformanceRecorder::Impl::CAutoFindFile *)&v12);
            return (unsigned int)v6;
          }
        }
        else if ( !DeleteFileW(lpPathName[0]) )
        {
          Error = ATL::AtlHresultFromLastError();
          WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)lpPathName);
          WindowsPerformanceRecorder::Impl::CAutoFindFile::~CAutoFindFile((WindowsPerformanceRecorder::Impl::CAutoFindFile *)&v12);
          return Error;
        }
        WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)lpPathName);
      }
      i = FindNextFileW(hFindFile, &FindFileData);
    }
    if ( !(_DWORD)v16 || RemoveDirectoryW(this) )
    {
      WindowsPerformanceRecorder::Impl::CAutoFindFile::~CAutoFindFile((WindowsPerformanceRecorder::Impl::CAutoFindFile *)&v12);
      result = 0;
    }
    else
    {
      v3 = ATL::AtlHresultFromLastError();
      WindowsPerformanceRecorder::Impl::CAutoFindFile::~CAutoFindFile((WindowsPerformanceRecorder::Impl::CAutoFindFile *)&v12);
      result = v3;
    }
  }
  catch ( ATL::CAtlException *v11 )
  {
    return *(unsigned int *)v11;
  }
  return result;
}

```

## disassembly

```asm
0x18005ce34  mov     rax, rsp
0x18005ce37  push    rdi
0x18005ce38  sub     rsp, 2E0h
0x18005ce3f  mov     [rsp+2E8h+var_2B0], 0FFFFFFFFFFFFFFFEh
0x18005ce48  mov     [rax+10h], rbx
0x18005ce4c  mov     [rax+18h], rsi
0x18005ce50  mov     rax, cs:__security_cookie
0x18005ce57  xor     rax, rsp
0x18005ce5a  mov     [rsp+2E8h+var_18], rax
0x18005ce62  mov     rdi, rcx
0x18005ce65  lea     rax, ??_7CAutoFindFile@Impl@WindowsPerformanceRecorder@@6B@; const WindowsPerformanceRecorder::Impl::CAutoFindFile::`vftable'
0x18005ce6c  mov     [rsp+2E8h+var_298], rax
0x18005ce71  mov     [rsp+2E8h+var_290], rcx
0x18005ce76  lea     rax, asc_18009B048; "*.*"
0x18005ce7d  mov     [rsp+2E8h+var_288], rax
0x18005ce82  mov     [rsp+2E8h+hFindFile], 0FFFFFFFFFFFFFFFFh
0x18005ce8b  xor     esi, esi
0x18005ce8d  mov     [rsp+2E8h+var_278], rsi
0x18005ce92  lea     rcx, [rsp+2E8h+var_298]; this
0x18005ce97  call    ?Begin@CAutoFindFile@Impl@WindowsPerformanceRecorder@@QEAAXXZ; WindowsPerformanceRecorder::Impl::CAutoFindFile::Begin(void)
0x18005ce9c  mov     eax, dword ptr [rsp+2E8h+var_278+4]
0x18005cea0  test    eax, eax
0x18005cea2  jnz     short loc_18005CEE1
0x18005cea4  cmp     dword ptr [rsp+2E8h+var_278], esi
0x18005cea8  jz      short loc_18005CECF
0x18005ceaa  mov     rcx, rdi; lpPathName
0x18005cead  call    cs:__imp_RemoveDirectoryW
0x18005ceb3  test    eax, eax
0x18005ceb5  jnz     short loc_18005CECF
0x18005ceb7  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18005cebc  mov     ebx, eax
0x18005cebe  lea     rcx, [rsp+2E8h+var_298]; this
0x18005cec3  call    ??1CAutoFindFile@Impl@WindowsPerformanceRecorder@@UEAA@XZ; WindowsPerformanceRecorder::Impl::CAutoFindFile::~CAutoFindFile(void)
0x18005cec8  mov     eax, ebx
0x18005ceca  jmp     loc_18005CFF6
0x18005cecf  lea     rcx, [rsp+2E8h+var_298]; this
0x18005ced4  call    ??1CAutoFindFile@Impl@WindowsPerformanceRecorder@@UEAA@XZ; WindowsPerformanceRecorder::Impl::CAutoFindFile::~CAutoFindFile(void)
0x18005ced9  nop
0x18005ceda  xor     eax, eax
0x18005cedc  jmp     loc_18005CFF6
0x18005cee1  cmp     [rsp+2E8h+FindFileData.cFileName], 2Eh ; '.'
0x18005ceea  jnz     short loc_18005CF11
0x18005ceec  movzx   eax, [rsp+2E8h+FindFileData.cFileName+2]
0x18005cef4  test    ax, ax
0x18005cef7  jz      loc_18005CFD9
0x18005cefd  cmp     ax, 2Eh ; '.'
0x18005cf01  jnz     short loc_18005CF11
0x18005cf03  cmp     [rsp+2E8h+FindFileData.cFileName+4], si
0x18005cf0b  jz      loc_18005CFD9
0x18005cf11  lea     rcx, [rsp+2E8h+lpPathName]; void *
0x18005cf16  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18005cf1b  nop
0x18005cf1c  mov     rdx, [rsp+2E8h+var_290]
0x18005cf21  lea     rcx, [rsp+2E8h+lpPathName]
0x18005cf26  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x18005cf2b  lea     rdx, SubBlock; "\\"
0x18005cf32  lea     rcx, [rsp+2E8h+lpPathName]
0x18005cf37  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *)
0x18005cf3c  lea     rdx, [rsp+2E8h+FindFileData.cFileName]
0x18005cf44  lea     rcx, [rsp+2E8h+lpPathName]
0x18005cf49  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *)
0x18005cf4e  mov     rcx, [rsp+2E8h+lpPathName]; this
0x18005cf53  test    byte ptr [rsp+2E8h+FindFileData.dwFileAttributes], 10h
0x18005cf58  jz      short loc_18005CFA5
0x18005cf5a  call    ?RemoveDirectoryRecursively@Impl@WindowsPerformanceRecorder@@YAJPEBG@Z; WindowsPerformanceRecorder::Impl::RemoveDirectoryRecursively(ushort const *)
0x18005cf5f  mov     ebx, eax
0x18005cf61  test    eax, eax
0x18005cf63  jns     short loc_18005CFCF
0x18005cf65  lea     rax, aComguard; "COMGUARD"
0x18005cf6c  mov     [rsp+2E8h+Format], rax; Format
0x18005cf71  mov     r9d, ebx; unsigned int
0x18005cf74  mov     r8d, 122h; char *
0x18005cf7a  lea     rdx, aRemovedirector; "RemoveDirectoryRecursively"
0x18005cf81  mov     ecx, 2; this
0x18005cf86  call    ?TraceHR@WindowsPerformanceRecorder@@YAXEPEBDIJ0ZZ; WindowsPerformanceRecorder::TraceHR(uchar,char const *,uint,long,char const *,...)
0x18005cf8b  nop
0x18005cf8c  lea     rcx, [rsp+2E8h+lpPathName]; this
0x18005cf91  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x18005cf96  nop
0x18005cf97  lea     rcx, [rsp+2E8h+var_298]; this
0x18005cf9c  call    ??1CAutoFindFile@Impl@WindowsPerformanceRecorder@@UEAA@XZ; WindowsPerformanceRecorder::Impl::CAutoFindFile::~CAutoFindFile(void)
0x18005cfa1  mov     eax, ebx
0x18005cfa3  jmp     short loc_18005CFF6
0x18005cfa5  call    cs:__imp_DeleteFileW
0x18005cfab  test    eax, eax
0x18005cfad  jnz     short loc_18005CFCF
0x18005cfaf  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18005cfb4  mov     ebx, eax
0x18005cfb6  lea     rcx, [rsp+2E8h+lpPathName]; this
0x18005cfbb  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x18005cfc0  nop
0x18005cfc1  lea     rcx, [rsp+2E8h+var_298]; this
0x18005cfc6  call    ??1CAutoFindFile@Impl@WindowsPerformanceRecorder@@UEAA@XZ; WindowsPerformanceRecorder::Impl::CAutoFindFile::~CAutoFindFile(void)
0x18005cfcb  mov     eax, ebx
0x18005cfcd  jmp     short loc_18005CFF6
0x18005cfcf  lea     rcx, [rsp+2E8h+lpPathName]; this
0x18005cfd4  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x18005cfd9  lea     rdx, [rsp+2E8h+FindFileData]; lpFindFileData
0x18005cfde  mov     rcx, [rsp+2E8h+hFindFile]; hFindFile
0x18005cfe3  call    cs:__imp_FindNextFileW
0x18005cfe9  mov     dword ptr [rsp+2E8h+var_278+4], eax
0x18005cfed  jmp     loc_18005CEA0
0x18005cff2  mov     eax, dword ptr [rsp+2E8h+lpPathName]
0x18005cff6  mov     rcx, [rsp+2E8h+var_18]
0x18005cffe  xor     rcx, rsp; StackCookie
0x18005d001  call    __security_check_cookie
0x18005d006  lea     r11, [rsp+2E8h+var_8]
0x18005d00e  mov     rbx, [r11+18h]
0x18005d012  mov     rsi, [r11+20h]
0x18005d016  mov     rsp, r11
0x18005d019  pop     rdi
0x18005d01a  retn
```
