# CLogger::PurgeOld(void)

- ea: `0x1800389d4`
- end: `0x180038b2d`
- name: `?PurgeOld@CLogger@@QEAAXXZ`
- size: `345`
- prototype: `void __fastcall(CLogger *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x18003886c`

## callees

- `0x180002300`
- `0x18000306c`
- `0x18000e658`
- `0x18000ee48`
- `0x180011884`
- `0x180015178`
- `0x180037dec`
- `0x180038018`
- `0x180038730`
- `0x1800389d4`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180038ae8`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180038ae8`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180038a50`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180038a50`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180038aba`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180038aba`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180038ad7`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180038ad7`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall CLogger::PurgeOld(CLogger *this)
{
  LPCWSTR v2; // rbx
  char *v3; // rsi
  int v4; // r8d
  __int64 FirstFileW; // rdi
  LPCWSTR v6; // [rsp+20h] [rbp-288h] BYREF
  LPCWSTR lpFileName; // [rsp+28h] [rbp-280h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+30h] [rbp-278h] BYREF
  __int64 v9; // [rsp+38h] [rbp-270h] BYREF
  _WIN32_FIND_DATAW FindFileData; // [rsp+40h] [rbp-268h] BYREF

  ATL::CTime::GetTickCount(&v6);
  v2 = v6 - 302400;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v3 = (char *)this + 24;
  try
  {
    ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(
      &lpFileName,
      (char *)this + 24);
    ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::operator+=(&lpFileName, "*.txt");
    FirstFileW = (__int64)FindFirstFileW(lpFileName, &FindFileData);
    while ( FirstFileW != -1 )
    {
      ftLastWriteTime = FindFileData.ftLastWriteTime;
      ATL::CTime::CTime((ATL::CTime *)&v9, &ftLastWriteTime, v4);
      if ( v9 < (__int64)v2 )
      {
        ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(
          &v6,
          v3);
        ATL::CSimpleStringT<wchar_t,0>::Append(&v6, FindFileData.cFileName);
        if ( (int)ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::Find(&v6, L".txt") > 0 )
          DeleteFileW(v6);
        ATL::CStringData::Release((ATL::CStringData *)(v6 - 12));
      }
      if ( !FindNextFileW((HANDLE)FirstFileW, &FindFileData) )
      {
        FindClose((HANDLE)FirstFileW);
        FirstFileW = -1;
      }
    }
    ATL::CStringData::Release((ATL::CStringData *)(lpFileName - 12));
  }
  catch ( ... )
  {
  }
}

```

## disassembly

```asm
0x1800389d4  mov     [rsp+arg_8], rbx
0x1800389d9  mov     [rsp+arg_10], rsi
0x1800389de  push    rdi
0x1800389df  sub     rsp, 2A0h
0x1800389e6  mov     rax, cs:__security_cookie
0x1800389ed  xor     rax, rsp
0x1800389f0  mov     [rsp+2A8h+var_18], rax
0x1800389f8  mov     rdi, rcx
0x1800389fb  lea     rcx, [rsp+2A8h+var_288]
0x180038a00  call    ?GetTickCount@CTime@ATL@@SA?AV12@XZ; ATL::CTime::GetTickCount(void)
0x180038a05  mov     rbx, [rsp+2A8h+var_288]
0x180038a0a  sub     rbx, 93A80h
0x180038a11  xor     edx, edx; Val
0x180038a13  mov     r8d, 250h; Size
0x180038a19  lea     rcx, [rsp+2A8h+FindFileData]; void *
0x180038a1e  call    memset_0
0x180038a23  lea     rsi, [rdi+18h]
0x180038a27  mov     rdx, rsi
0x180038a2a  lea     rcx, [rsp+2A8h+lpFileName]
0x180038a2f  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> const &)
0x180038a34  nop
0x180038a35  lea     rdx, aTxt_0; "*.txt"
0x180038a3c  lea     rcx, [rsp+2A8h+lpFileName]
0x180038a41  call    ??Y?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAAAEAV01@PEBD@Z; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::operator+=(char const *)
0x180038a46  lea     rdx, [rsp+2A8h+FindFileData]; lpFindFileData
0x180038a4b  mov     rcx, [rsp+2A8h+lpFileName]; lpFileName
0x180038a50  call    cs:__imp_FindFirstFileW
0x180038a56  mov     rdi, rax
0x180038a59  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180038a5d  jz      loc_180038AF7
0x180038a63  mov     rcx, qword ptr [rsp+2A8h+FindFileData.ftLastWriteTime.dwLowDateTime]
0x180038a68  mov     qword ptr [rsp+2A8h+var_278.dwLowDateTime], rcx
0x180038a6d  lea     rdx, [rsp+2A8h+var_278]; struct _FILETIME *
0x180038a72  lea     rcx, [rsp+2A8h+var_270]; this
0x180038a77  call    ??0CTime@ATL@@QEAA@AEBU_FILETIME@@H@Z; ATL::CTime::CTime(_FILETIME const &,int)
0x180038a7c  cmp     [rsp+2A8h+var_270], rbx
0x180038a81  jge     short loc_180038ACF
0x180038a83  mov     rdx, rsi
0x180038a86  lea     rcx, [rsp+2A8h+var_288]
0x180038a8b  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> const &)
0x180038a90  nop
0x180038a91  lea     rdx, [rsp+2A8h+FindFileData.cFileName]
0x180038a96  lea     rcx, [rsp+2A8h+var_288]
0x180038a9b  call    ?Append@?$CSimpleStringT@_W$0A@@ATL@@QEAAXPEB_W@Z; ATL::CSimpleStringT<wchar_t,0>::Append(wchar_t const *)
0x180038aa0  lea     rdx, aTxt; ".txt"
0x180038aa7  lea     rcx, [rsp+2A8h+var_288]
0x180038aac  call    ?Find@?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEBAHPEB_WH@Z; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::Find(wchar_t const *,int)
0x180038ab1  test    eax, eax
0x180038ab3  jle     short loc_180038AC1
0x180038ab5  mov     rcx, [rsp+2A8h+var_288]; lpFileName
0x180038aba  call    cs:__imp_DeleteFileW
0x180038ac0  nop
0x180038ac1  mov     rcx, [rsp+2A8h+var_288]
0x180038ac6  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180038aca  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180038acf  lea     rdx, [rsp+2A8h+FindFileData]; lpFindFileData
0x180038ad4  mov     rcx, rdi; hFindFile
0x180038ad7  call    cs:__imp_FindNextFileW
0x180038add  test    eax, eax
0x180038adf  jnz     loc_180038A59
0x180038ae5  mov     rcx, rdi; hFindFile
0x180038ae8  call    cs:__imp_FindClose
0x180038aee  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180038af2  jmp     loc_180038A59
0x180038af7  mov     rcx, [rsp+2A8h+lpFileName]
0x180038afc  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180038b00  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180038b05  nop
0x180038b06  jmp     short $+2
0x180038b08  mov     rcx, [rsp+2A8h+var_18]
0x180038b10  xor     rcx, rsp; StackCookie
0x180038b13  call    __security_check_cookie
0x180038b18  lea     r11, [rsp+2A8h+var_8]
0x180038b20  mov     rbx, [r11+18h]
0x180038b24  mov     rsi, [r11+20h]
0x180038b28  mov     rsp, r11
0x180038b2b  pop     rdi
0x180038b2c  retn
```
