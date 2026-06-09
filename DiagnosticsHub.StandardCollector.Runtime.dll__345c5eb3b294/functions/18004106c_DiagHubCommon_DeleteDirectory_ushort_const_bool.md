# DiagHubCommon::DeleteDirectory(ushort const *,bool)

- ea: `0x18004106c`
- end: `0x1800412ab`
- name: `?DeleteDirectory@DiagHubCommon@@YAJPEBG_N@Z`
- size: `575`
- prototype: `__int64 __fastcall(DiagHubCommon *__hidden this, const unsigned __int16 *, bool)`
- caller_count: `6`
- callee_count: `9`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x180020004`
- `0x18002e994`
- `0x180038a24`
- `0x180038f48`
- `0x18004106c`
- `0x1800412ac`

## callees

- `0x180002604`
- `0x18000288c`
- `0x180027bc8`
- `0x180040e40`
- `0x180040fb8`
- `0x18004106c`
- `0x180049b50`
- `0x18004ad26`
- `0x18004b640`

## import_xrefs

- `KERNEL32!DeleteFileW` at `0x180041198`
- `KERNEL32!DeleteFileW` at `0x180041198`
- `KERNEL32!FindClose` at `0x1800411f5`
- `KERNEL32!FindClose` at `0x18004126d`
- `KERNEL32!FindClose` at `0x1800411f5`
- `KERNEL32!FindClose` at `0x18004126d`
- `KERNEL32!DeleteVolumeMountPointW` at `0x1800410ee`
- `KERNEL32!DeleteVolumeMountPointW` at `0x1800410ee`
- `KERNEL32!RemoveDirectoryW` at `0x1800410fb`
- `KERNEL32!RemoveDirectoryW` at `0x1800411fe`
- `KERNEL32!RemoveDirectoryW` at `0x1800410fb`
- `KERNEL32!RemoveDirectoryW` at `0x1800411fe`
- `KERNEL32!GetLastError` at `0x180041208`
- `KERNEL32!GetLastError` at `0x18004122a`
- `KERNEL32!GetLastError` at `0x180041208`
- `KERNEL32!GetLastError` at `0x18004122a`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall DiagHubCommon::DeleteDirectory(DiagHubCommon *this, const unsigned __int16 *a2)
{
  const unsigned __int16 *v3; // r8
  bool v4; // r9
  signed int v5; // edi
  struct ATL::IAtlStringMgr *Instance; // rax
  __int64 v7; // rax
  const wchar_t *v8; // rdx
  const unsigned __int16 *v9; // rdx
  bool v10; // r8
  LPCWSTR v11; // rbx
  signed int LastError; // ecx
  __int64 result; // rax
  signed int v14; // eax
  LPCWSTR lpszVolumeMountPoint[2]; // [rsp+20h] [rbp-E0h] BYREF
  HANDLE hFindFile; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v17[44]; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v18[548]; // [rsp+64h] [rbp-9Ch] BYREF
  __int16 v19; // [rsp+288h] [rbp+188h]

  memset_0(&hFindFile, 0, 0x260u);
  hFindFile = 0;
  memset_0(v17, 0, 0x250u);
  v19 = 0;
  v5 = DiagHubCommon::CFileSystemIterator::Initialize(
         (DiagHubCommon::CFileSystemIterator *)&hFindFile,
         (const unsigned __int16 *)this,
         v3,
         v4);
  if ( v5 < 0 )
    goto LABEL_31;
  _mm_lfence();
  if ( DeleteVolumeMountPointW((LPCWSTR)this) || RemoveDirectoryW((LPCWSTR)this) )
  {
    v5 = 0;
    goto LABEL_31;
  }
  while ( 1 )
  {
    if ( HIBYTE(v19) )
    {
      if ( hFindFile )
        FindClose(hFindFile);
      if ( RemoveDirectoryW((LPCWSTR)this) )
        return 0;
      LastError = GetLastError();
      if ( LastError == 2 )
        LastError = 3;
      result = (unsigned __int16)LastError | 0x80070000;
      if ( LastError <= 0 )
        return (unsigned int)LastError;
      return result;
    }
    Instance = ATL::CAtlStringMgr::GetInstance();
    if ( !Instance )
      ATL::AtlThrowImpl(-2147467259);
    lpszVolumeMountPoint[0] = (LPCWSTR)((*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)Instance
                                                                                               + 24LL))(Instance)
                                      + 24);
    v7 = -1;
    do
      ++v7;
    while ( *((_WORD *)this + v7) );
    if ( !v7 || (v8 = L"%s\\%s", *((_WORD *)this + v7 - 1) == 92) )
      v8 = L"%s%s";
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
      lpszVolumeMountPoint,
      v8,
      this,
      v18);
    v11 = lpszVolumeMountPoint[0];
    if ( (v17[0] & 0x10) == 0 )
      break;
    LOBYTE(v9) = 1;
    v5 = DiagHubCommon::DeleteDirectory((DiagHubCommon *)lpszVolumeMountPoint[0], v9, v10);
    if ( v5 < 0 )
      goto LABEL_29;
LABEL_15:
    v5 = DiagHubCommon::CFileSystemIterator::Next((DiagHubCommon::CFileSystemIterator *)&hFindFile);
    if ( v5 < 0 )
      goto LABEL_29;
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v11 - 2, 0xFFFFFFFF) <= 1 )
    {
      _mm_lfence();
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v11 - 3) + 8LL))(*((_QWORD *)v11 - 3));
    }
  }
  if ( DeleteFileW(lpszVolumeMountPoint[0]) )
    goto LABEL_15;
  v14 = GetLastError();
  v5 = (unsigned __int16)v14 | 0x80070000;
  if ( v14 <= 0 )
    v5 = v14;
LABEL_29:
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v11 - 2, 0xFFFFFFFF) <= 1 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v11 - 3) + 8LL))(*((_QWORD *)v11 - 3));
  }
LABEL_31:
  if ( hFindFile )
    FindClose(hFindFile);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18004106c  mov     [rsp-8+arg_8], rbx
0x180041071  mov     [rsp-8+arg_10], rsi
0x180041076  push    rbp
0x180041077  push    rdi
0x180041078  push    r14
0x18004107a  lea     rbp, [rsp-1A0h]
0x180041082  sub     rsp, 2A0h
0x180041089  mov     rax, cs:__security_cookie
0x180041090  xor     rax, rsp
0x180041093  mov     [rbp+1B0h+var_20], rax
0x18004109a  mov     rsi, rcx
0x18004109d  xor     edx, edx; Val
0x18004109f  mov     r8d, 260h; Size
0x1800410a5  lea     rcx, [rsp+2B0h+hFindFile]; void *
0x1800410aa  call    memset_0
0x1800410af  xor     r14d, r14d
0x1800410b2  mov     [rsp+2B0h+hFindFile], r14
0x1800410b7  xor     edx, edx; Val
0x1800410b9  mov     r8d, 250h; Size
0x1800410bf  lea     rcx, [rsp+2B0h+var_278]; void *
0x1800410c4  call    memset_0
0x1800410c9  mov     [rbp+1B0h+var_28], r14w
0x1800410d1  mov     rdx, rsi; unsigned __int16 *
0x1800410d4  lea     rcx, [rsp+2B0h+hFindFile]; this
0x1800410d9  call    ?Initialize@CFileSystemIterator@DiagHubCommon@@QEAAJPEBG0_N@Z; DiagHubCommon::CFileSystemIterator::Initialize(ushort const *,ushort const *,bool)
0x1800410de  mov     edi, eax
0x1800410e0  test    eax, eax
0x1800410e2  js      loc_180041263
0x1800410e8  lfence
0x1800410eb  mov     rcx, rsi; lpszVolumeMountPoint
0x1800410ee  call    cs:__imp_DeleteVolumeMountPointW
0x1800410f4  test    eax, eax
0x1800410f6  jnz     short loc_180041109
0x1800410f8  mov     rcx, rsi; lpPathName
0x1800410fb  call    cs:__imp_RemoveDirectoryW
0x180041101  test    eax, eax
0x180041103  jz      loc_1800411DE
0x180041109  mov     edi, r14d
0x18004110c  jmp     loc_180041263
0x180041111  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x180041116  mov     rdx, rax
0x180041119  test    rax, rax
0x18004111c  jz      loc_1800412A0
0x180041122  mov     rcx, [rax]
0x180041125  mov     rax, [rcx+18h]
0x180041129  mov     rcx, rdx
0x18004112c  call    cs:__guard_dispatch_icall_fptr
0x180041132  add     rax, 18h
0x180041136  mov     [rsp+2B0h+lpszVolumeMountPoint], rax
0x18004113b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004113f  inc     rax
0x180041142  cmp     [rsi+rax*2], r14w
0x180041147  jnz     short loc_18004113F
0x180041149  test    rax, rax
0x18004114c  jz      short loc_18004115D
0x18004114e  cmp     word ptr [rsi+rax*2-2], 5Ch ; '\'
0x180041154  lea     rdx, aSS_2; "%s\\%s"
0x18004115b  jnz     short loc_180041164
0x18004115d  lea     rdx, aSS_3; "%s%s"
0x180041164  lea     r9, [rsp+2B0h+var_24C]
0x180041169  mov     r8, rsi
0x18004116c  lea     rcx, [rsp+2B0h+lpszVolumeMountPoint]
0x180041171  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x180041176  mov     rbx, [rsp+2B0h+lpszVolumeMountPoint]
0x18004117b  mov     rcx, rbx; this
0x18004117e  test    [rsp+2B0h+var_278], 10h
0x180041183  jz      short loc_180041198
0x180041185  mov     dl, 1; unsigned __int16 *
0x180041187  call    ?DeleteDirectory@DiagHubCommon@@YAJPEBG_N@Z; DiagHubCommon::DeleteDirectory(ushort const *,bool)
0x18004118c  mov     edi, eax
0x18004118e  test    eax, eax
0x180041190  js      loc_18004123E
0x180041196  jmp     short loc_1800411A6
0x180041198  call    cs:__imp_DeleteFileW
0x18004119e  test    eax, eax
0x1800411a0  jz      loc_18004122A
0x1800411a6  lea     rcx, [rsp+2B0h+hFindFile]; this
0x1800411ab  call    ?Next@CFileSystemIterator@DiagHubCommon@@QEAAJXZ; DiagHubCommon::CFileSystemIterator::Next(void)
0x1800411b0  mov     edi, eax
0x1800411b2  test    eax, eax
0x1800411b4  js      loc_18004123E
0x1800411ba  lea     rdx, [rbx-18h]
0x1800411be  or      eax, 0FFFFFFFFh
0x1800411c1  lock xadd [rdx+10h], eax
0x1800411c6  sub     eax, 1
0x1800411c9  jg      short loc_1800411DE
0x1800411cb  lfence
0x1800411ce  mov     rcx, [rdx]
0x1800411d1  mov     rax, [rcx]
0x1800411d4  mov     rax, [rax+8]
0x1800411d8  call    cs:__guard_dispatch_icall_fptr
0x1800411de  cmp     byte ptr [rbp+1B0h+var_28+1], r14b
0x1800411e5  jz      loc_180041111
0x1800411eb  mov     rcx, [rsp+2B0h+hFindFile]; hFindFile
0x1800411f0  test    rcx, rcx
0x1800411f3  jz      short loc_1800411FB
0x1800411f5  call    cs:__imp_FindClose
0x1800411fb  mov     rcx, rsi; lpPathName
0x1800411fe  call    cs:__imp_RemoveDirectoryW
0x180041204  test    eax, eax
0x180041206  jnz     short loc_180041277
0x180041208  call    cs:__imp_GetLastError
0x18004120e  mov     ecx, eax
0x180041210  mov     eax, 3
0x180041215  cmp     ecx, 2
0x180041218  cmovz   ecx, eax
0x18004121b  movzx   eax, cx
0x18004121e  or      eax, 80070000h
0x180041223  test    ecx, ecx
0x180041225  cmovle  eax, ecx
0x180041228  jmp     short loc_180041279
0x18004122a  call    cs:__imp_GetLastError
0x180041230  movzx   edi, ax
0x180041233  or      edi, 80070000h
0x180041239  test    eax, eax
0x18004123b  cmovle  edi, eax
0x18004123e  lea     rdx, [rbx-18h]
0x180041242  or      eax, 0FFFFFFFFh
0x180041245  lock xadd [rdx+10h], eax
0x18004124a  sub     eax, 1
0x18004124d  jg      short loc_180041263
0x18004124f  lfence
0x180041252  mov     rcx, [rdx]
0x180041255  mov     rax, [rcx]
0x180041258  mov     rax, [rax+8]
0x18004125c  call    cs:__guard_dispatch_icall_fptr
0x180041262  nop
0x180041263  mov     rcx, [rsp+2B0h+hFindFile]; hFindFile
0x180041268  test    rcx, rcx
0x18004126b  jz      short loc_180041273
0x18004126d  call    cs:__imp_FindClose
0x180041273  mov     eax, edi
0x180041275  jmp     short loc_180041279
0x180041277  xor     eax, eax
0x180041279  mov     rcx, [rbp+1B0h+var_20]
0x180041280  xor     rcx, rsp; StackCookie
0x180041283  call    __security_check_cookie
0x180041288  lea     r11, [rsp+2B0h+var_10]
0x180041290  mov     rbx, [r11+28h]
0x180041294  mov     rsi, [r11+30h]
0x180041298  mov     rsp, r11
0x18004129b  pop     r14
0x18004129d  pop     rdi
0x18004129e  pop     rbp
0x18004129f  retn
0x1800412a0  mov     ecx, 80004005h; int
0x1800412a5  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
