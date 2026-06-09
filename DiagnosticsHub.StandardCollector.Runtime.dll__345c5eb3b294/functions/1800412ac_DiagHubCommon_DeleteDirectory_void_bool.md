# DiagHubCommon::DeleteDirectory(void *,bool)

- ea: `0x1800412ac`
- end: `0x1800415c5`
- name: `?DeleteDirectory@DiagHubCommon@@YAJPEAX_N@Z`
- size: `793`
- prototype: `__int64 __fastcall(HANDLE hFile, void *, bool)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x18002e994`

## callees

- `0x180002604`
- `0x18000288c`
- `0x18000a17c`
- `0x180027bc8`
- `0x18002f17c`
- `0x180040e40`
- `0x180040fb8`
- `0x18004106c`
- `0x1800412ac`
- `0x180049b50`
- `0x18004ad26`
- `0x18004ad58`
- `0x18004b640`

## import_xrefs

- `KERNEL32!DeleteFileW` at `0x180041439`
- `KERNEL32!DeleteFileW` at `0x180041439`
- `KERNEL32!GetFinalPathNameByHandleW` at `0x1800412f6`
- `KERNEL32!GetFinalPathNameByHandleW` at `0x180041336`
- `KERNEL32!GetFinalPathNameByHandleW` at `0x1800412f6`
- `KERNEL32!GetFinalPathNameByHandleW` at `0x180041336`
- `KERNEL32!FindClose` at `0x1800413a0`
- `KERNEL32!FindClose` at `0x180041496`
- `KERNEL32!FindClose` at `0x180041527`
- `KERNEL32!FindClose` at `0x1800413a0`
- `KERNEL32!FindClose` at `0x180041496`
- `KERNEL32!FindClose` at `0x180041527`
- `KERNEL32!SetFileInformationByHandle` at `0x1800414be`
- `KERNEL32!SetFileInformationByHandle` at `0x1800414be`
- `KERNEL32!GetLastError` at `0x1800414c8`
- `KERNEL32!GetLastError` at `0x1800414e4`
- `KERNEL32!GetLastError` at `0x180041571`
- `KERNEL32!GetLastError` at `0x18004159b`
- `KERNEL32!GetLastError` at `0x1800414c8`
- `KERNEL32!GetLastError` at `0x1800414e4`
- `KERNEL32!GetLastError` at `0x180041571`
- `KERNEL32!GetLastError` at `0x18004159b`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall DiagHubCommon::DeleteDirectory(HANDLE hFile, void *a2)
{
  __int64 result; // rax
  DWORD FinalPathNameByHandleW; // eax
  const unsigned __int16 *v5; // r8
  bool v6; // r9
  int v7; // ebx
  struct ATL::IAtlStringMgr *Instance; // rax
  const wchar_t *v9; // rdx
  const unsigned __int16 *v10; // rdx
  bool v11; // r8
  DiagHubCommon *v12; // rbx
  signed int v13; // edi
  volatile signed __int32 *v14; // rdx
  signed int v15; // ecx
  signed int v16; // eax
  signed int LastError; // eax
  unsigned int v18; // ecx
  signed int v19; // eax
  unsigned int v20; // ecx
  DiagHubCommon *lpszFilePath; // [rsp+28h] [rbp-E0h] BYREF
  LPWSTR lpszFilePath_8[2]; // [rsp+30h] [rbp-D8h] BYREF
  __int64 v23; // [rsp+40h] [rbp-C8h]
  char FileInformation[16]; // [rsp+48h] [rbp-C0h] BYREF
  HANDLE hFindFile; // [rsp+58h] [rbp-B0h] BYREF
  _BYTE v26[44]; // [rsp+60h] [rbp-A8h] BYREF
  _BYTE v27[548]; // [rsp+8Ch] [rbp-7Ch] BYREF
  __int16 v28; // [rsp+2B0h] [rbp+1A8h]

  if ( hFile == (HANDLE)-1LL )
    return 2147942487LL;
  FinalPathNameByHandleW = GetFinalPathNameByHandleW(hFile, 0, 0, 0);
  if ( !FinalPathNameByHandleW )
  {
    LastError = GetLastError();
    v18 = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      v18 = LastError;
    LODWORD(lpszFilePath) = v18;
    throw (long *)&lpszFilePath;
  }
  *(_OWORD *)lpszFilePath_8 = 0;
  v23 = 0;
  std::vector<unsigned short>::vector<unsigned short>(lpszFilePath_8, FinalPathNameByHandleW);
  if ( !GetFinalPathNameByHandleW(hFile, lpszFilePath_8[0], lpszFilePath_8[1] - lpszFilePath_8[0], 0) )
  {
    v19 = GetLastError();
    v20 = (unsigned __int16)v19 | 0x80070000;
    if ( v19 <= 0 )
      v20 = v19;
    LODWORD(lpszFilePath) = v20;
    throw (long *)&lpszFilePath;
  }
  memset_0(&hFindFile, 0, 0x260u);
  hFindFile = 0;
  memset_0(v26, 0, 0x250u);
  v28 = 0;
  v7 = DiagHubCommon::CFileSystemIterator::Initialize(
         (DiagHubCommon::CFileSystemIterator *)&hFindFile,
         lpszFilePath_8[0],
         v5,
         v6);
  if ( v7 < 0 )
  {
    _mm_lfence();
    if ( hFindFile )
      FindClose(hFindFile);
    std::vector<unsigned short>::~vector<unsigned short>(lpszFilePath_8);
    return (unsigned int)v7;
  }
  while ( 1 )
  {
    if ( HIBYTE(v28) )
    {
      if ( hFindFile )
        FindClose(hFindFile);
      std::vector<unsigned short>::~vector<unsigned short>(lpszFilePath_8);
      FileInformation[0] = 1;
      if ( SetFileInformationByHandle(hFile, FileDispositionInfo, FileInformation, 1u) )
        return 0;
      v15 = GetLastError();
      result = (unsigned __int16)v15 | 0x80070000;
      if ( v15 <= 0 )
        return (unsigned int)v15;
      return result;
    }
    Instance = ATL::CAtlStringMgr::GetInstance();
    if ( !Instance )
      ATL::AtlThrowImpl(-2147467259);
    lpszFilePath = (DiagHubCommon *)((*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)Instance + 24LL))(Instance)
                                   + 24);
    v9 = L"%s%s";
    if ( lpszFilePath_8[0][lpszFilePath_8[1] - lpszFilePath_8[0] - 1] != 92 )
      v9 = L"%s\\%s";
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
      &lpszFilePath,
      v9,
      lpszFilePath_8[0],
      v27,
      lpszFilePath);
    v12 = lpszFilePath;
    if ( (v26[0] & 0x10) == 0 )
      break;
    v13 = DiagHubCommon::DeleteDirectory(lpszFilePath, v10, v11);
    if ( v13 < 0 )
    {
      _mm_lfence();
      goto LABEL_29;
    }
LABEL_16:
    v13 = DiagHubCommon::CFileSystemIterator::Next((DiagHubCommon::CFileSystemIterator *)&hFindFile);
    v14 = (volatile signed __int32 *)((char *)v12 - 24);
    if ( v13 < 0 )
    {
      _mm_lfence();
      goto LABEL_30;
    }
    if ( _InterlockedExchangeAdd(v14 + 4, 0xFFFFFFFF) <= 1 )
    {
      _mm_lfence();
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v14 + 8LL))(*(_QWORD *)v14);
    }
  }
  if ( DeleteFileW((LPCWSTR)lpszFilePath) )
    goto LABEL_16;
  v16 = GetLastError();
  v13 = (unsigned __int16)v16 | 0x80070000;
  if ( v16 <= 0 )
    v13 = v16;
LABEL_29:
  v14 = (volatile signed __int32 *)((char *)v12 - 24);
LABEL_30:
  if ( _InterlockedExchangeAdd(v14 + 4, 0xFFFFFFFF) <= 1 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v14 + 8LL))(*(_QWORD *)v14);
  }
  if ( hFindFile )
    FindClose(hFindFile);
  std::vector<unsigned short>::~vector<unsigned short>(lpszFilePath_8);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x1800412ac  mov     rax, rsp
0x1800412af  mov     [rax+10h], rbx
0x1800412b3  mov     [rax+18h], rsi
0x1800412b7  mov     [rax+20h], rdi
0x1800412bb  push    rbp
0x1800412bc  lea     rbp, [rax-1C8h]
0x1800412c3  sub     rsp, 2C0h
0x1800412ca  mov     rax, cs:__security_cookie
0x1800412d1  xor     rax, rsp
0x1800412d4  mov     [rbp+1C0h+var_10], rax
0x1800412db  mov     rsi, rcx
0x1800412de  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800412e2  jnz     short loc_1800412EE
0x1800412e4  mov     eax, 80070057h
0x1800412e9  jmp     loc_18004153E
0x1800412ee  xor     r9d, r9d; dwFlags
0x1800412f1  xor     r8d, r8d; cchFilePath
0x1800412f4  xor     edx, edx; lpszFilePath
0x1800412f6  call    cs:__imp_GetFinalPathNameByHandleW
0x1800412fc  mov     edx, eax
0x1800412fe  test    eax, eax
0x180041300  jz      loc_180041571
0x180041306  xorps   xmm0, xmm0
0x180041309  xor     eax, eax
0x18004130b  movups  xmmword ptr [rsp+2C0h+lpszFilePath+8], xmm0
0x180041310  mov     [rsp+2C0h+var_288], rax
0x180041315  lea     rcx, [rsp+2C0h+lpszFilePath+8]
0x18004131a  call    ??0?$vector@GV?$allocator@G@std@@@std@@QEAA@_KAEBV?$allocator@G@1@@Z; std::vector<ushort>::vector<ushort>(unsigned __int64,std::allocator<ushort> const &)
0x18004131f  nop
0x180041320  mov     rdx, [rsp+2C0h+lpszFilePath+8]; lpszFilePath
0x180041325  mov     r8, [rsp+2C0h+var_290]
0x18004132a  sub     r8, rdx
0x18004132d  sar     r8, 1; cchFilePath
0x180041330  xor     r9d, r9d; dwFlags
0x180041333  mov     rcx, rsi; hFile
0x180041336  call    cs:__imp_GetFinalPathNameByHandleW
0x18004133c  test    eax, eax
0x18004133e  jz      loc_18004159B
0x180041344  xor     edx, edx; Val
0x180041346  mov     r8d, 260h; Size
0x18004134c  lea     rcx, [rsp+2C0h+hFindFile]; void *
0x180041351  call    memset_0
0x180041356  mov     [rsp+2C0h+hFindFile], 0
0x18004135f  xor     edx, edx; Val
0x180041361  mov     r8d, 250h; Size
0x180041367  lea     rcx, [rsp+2C0h+var_268]; void *
0x18004136c  call    memset_0
0x180041371  mov     [rbp+1C0h+var_18], 0
0x18004137a  mov     rdx, [rsp+2C0h+lpszFilePath+8]; unsigned __int16 *
0x18004137f  lea     rcx, [rsp+2C0h+hFindFile]; this
0x180041384  call    ?Initialize@CFileSystemIterator@DiagHubCommon@@QEAAJPEBG0_N@Z; DiagHubCommon::CFileSystemIterator::Initialize(ushort const *,ushort const *,bool)
0x180041389  mov     ebx, eax
0x18004138b  test    eax, eax
0x18004138d  jns     loc_18004147F
0x180041393  lfence
0x180041396  mov     rcx, [rsp+2C0h+hFindFile]; hFindFile
0x18004139b  test    rcx, rcx
0x18004139e  jz      short loc_1800413A7
0x1800413a0  call    cs:__imp_FindClose
0x1800413a6  nop
0x1800413a7  lea     rcx, [rsp+2C0h+lpszFilePath+8]
0x1800413ac  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x1800413b1  mov     eax, ebx
0x1800413b3  jmp     loc_18004153E
0x1800413b8  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x1800413bd  mov     rdx, rax
0x1800413c0  test    rax, rax
0x1800413c3  jz      loc_180041566
0x1800413c9  mov     rcx, [rax]
0x1800413cc  mov     rax, [rcx+18h]
0x1800413d0  mov     rcx, rdx
0x1800413d3  call    cs:__guard_dispatch_icall_fptr
0x1800413d9  add     rax, 18h
0x1800413dd  mov     [rsp+2C0h+lpszFilePath], rax
0x1800413e2  mov     rax, [rsp+2C0h+var_290]
0x1800413e7  mov     r8, [rsp+2C0h+lpszFilePath+8]
0x1800413ec  sub     rax, r8
0x1800413ef  sar     rax, 1
0x1800413f2  lea     r9, [rbp+1C0h+var_23C]
0x1800413f6  lea     rcx, [rsp+2C0h+lpszFilePath]
0x1800413fb  cmp     word ptr [r8+rax*2-2], 5Ch ; '\'
0x180041402  lea     rdx, aSS_3; "%s%s"
0x180041409  jz      short loc_180041412
0x18004140b  lea     rdx, aSS_2; "%s\\%s"
0x180041412  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x180041417  mov     rbx, [rsp+2C0h+lpszFilePath]
0x18004141c  mov     rcx, rbx; this
0x18004141f  test    [rsp+2C0h+var_268], 10h
0x180041424  jz      short loc_180041439
0x180041426  call    ?DeleteDirectory@DiagHubCommon@@YAJPEBG_N@Z; DiagHubCommon::DeleteDirectory(ushort const *,bool)
0x18004142b  mov     edi, eax
0x18004142d  test    eax, eax
0x18004142f  jns     short loc_180041447
0x180041431  lfence
0x180041434  jmp     loc_1800414F8
0x180041439  call    cs:__imp_DeleteFileW
0x18004143f  test    eax, eax
0x180041441  jz      loc_1800414E4
0x180041447  lea     rcx, [rsp+2C0h+hFindFile]; this
0x18004144c  call    ?Next@CFileSystemIterator@DiagHubCommon@@QEAAJXZ; DiagHubCommon::CFileSystemIterator::Next(void)
0x180041451  mov     edi, eax
0x180041453  lea     rdx, [rbx-18h]
0x180041457  test    eax, eax
0x180041459  js      loc_1800414DF
0x18004145f  or      eax, 0FFFFFFFFh
0x180041462  lock xadd [rdx+10h], eax
0x180041467  sub     eax, 1
0x18004146a  jg      short loc_18004147F
0x18004146c  lfence
0x18004146f  mov     rcx, [rdx]
0x180041472  mov     rax, [rcx]
0x180041475  mov     rax, [rax+8]
0x180041479  call    cs:__guard_dispatch_icall_fptr
0x18004147f  cmp     byte ptr [rbp+1C0h+var_18+1], 0
0x180041486  jz      loc_1800413B8
0x18004148c  mov     rcx, [rsp+2C0h+hFindFile]; hFindFile
0x180041491  test    rcx, rcx
0x180041494  jz      short loc_18004149D
0x180041496  call    cs:__imp_FindClose
0x18004149c  nop
0x18004149d  lea     rcx, [rsp+2C0h+lpszFilePath+8]
0x1800414a2  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x1800414a7  mov     [rsp+2C0h+FileInformation], 1
0x1800414ac  mov     r9d, 1; dwBufferSize
0x1800414b2  lea     r8, [rsp+2C0h+FileInformation]; lpFileInformation
0x1800414b7  lea     edx, [r9+3]; FileInformationClass
0x1800414bb  mov     rcx, rsi; hFile
0x1800414be  call    cs:__imp_SetFileInformationByHandle
0x1800414c4  test    eax, eax
0x1800414c6  jnz     short loc_18004153C
0x1800414c8  call    cs:__imp_GetLastError
0x1800414ce  mov     ecx, eax
0x1800414d0  movzx   eax, ax
0x1800414d3  or      eax, 80070000h
0x1800414d8  test    ecx, ecx
0x1800414da  cmovle  eax, ecx
0x1800414dd  jmp     short loc_18004153E
0x1800414df  lfence
0x1800414e2  jmp     short loc_1800414FC
0x1800414e4  call    cs:__imp_GetLastError
0x1800414ea  movzx   edi, ax
0x1800414ed  or      edi, 80070000h
0x1800414f3  test    eax, eax
0x1800414f5  cmovle  edi, eax
0x1800414f8  lea     rdx, [rbx-18h]
0x1800414fc  or      eax, 0FFFFFFFFh
0x1800414ff  lock xadd [rdx+10h], eax
0x180041504  sub     eax, 1
0x180041507  jg      short loc_18004151D
0x180041509  lfence
0x18004150c  mov     rcx, [rdx]
0x18004150f  mov     rax, [rcx]
0x180041512  mov     rax, [rax+8]
0x180041516  call    cs:__guard_dispatch_icall_fptr
0x18004151c  nop
0x18004151d  mov     rcx, [rsp+2C0h+hFindFile]; hFindFile
0x180041522  test    rcx, rcx
0x180041525  jz      short loc_18004152E
0x180041527  call    cs:__imp_FindClose
0x18004152d  nop
0x18004152e  lea     rcx, [rsp+2C0h+lpszFilePath+8]
0x180041533  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180041538  mov     eax, edi
0x18004153a  jmp     short loc_18004153E
0x18004153c  xor     eax, eax
0x18004153e  mov     rcx, [rbp+1C0h+var_10]
0x180041545  xor     rcx, rsp; StackCookie
0x180041548  call    __security_check_cookie
0x18004154d  lea     r11, [rsp+2C0h+var_s0]
0x180041555  mov     rbx, [r11+18h]
0x180041559  mov     rsi, [r11+20h]
0x18004155d  mov     rdi, [r11+28h]
0x180041561  mov     rsp, r11
0x180041564  pop     rbp
0x180041565  retn
0x180041566  mov     ecx, 80004005h; int
0x18004156b  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180041571  call    cs:__imp_GetLastError
0x180041577  movzx   ecx, ax
0x18004157a  or      ecx, 80070000h
0x180041580  test    eax, eax
0x180041582  cmovle  ecx, eax
0x180041585  mov     dword ptr [rsp+2C0h+lpszFilePath], ecx
0x180041589  lea     rdx, _TI1J; pThrowInfo
0x180041590  lea     rcx, [rsp+2C0h+lpszFilePath]; pExceptionObject
0x180041595  call    _CxxThrowException_0
0x18004159b  call    cs:__imp_GetLastError
0x1800415a1  movzx   ecx, ax
0x1800415a4  or      ecx, 80070000h
0x1800415aa  test    eax, eax
0x1800415ac  cmovle  ecx, eax
0x1800415af  mov     dword ptr [rsp+2C0h+lpszFilePath], ecx
0x1800415b3  lea     rdx, _TI1J; pThrowInfo
0x1800415ba  lea     rcx, [rsp+2C0h+lpszFilePath]; pExceptionObject
0x1800415bf  call    _CxxThrowException_0
```
