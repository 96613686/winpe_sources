# OLog::Flush(Mso::Logging::MinimumSeverity)

- ea: `0x180021610`
- end: `0x180021c30`
- name: `?Flush@OLog@@QEAAXW4MinimumSeverity@Logging@Mso@@@Z`
- size: `1568`
- prototype: ``
- caller_count: `3`
- callee_count: `20`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800056ec`
- `0x180020ef0`
- `0x180021278`

## callees

- `0x1800018e0`
- `0x180002b40`
- `0x180003fc4`
- `0x18000410c`
- `0x1800045ec`
- `0x1800048a8`
- `0x180005d04`
- `0x18000a3c4`
- `0x18000a804`
- `0x18002037c`
- `0x180020494`
- `0x1800207e4`
- `0x180020a7c`
- `0x180020ef0`
- `0x180021358`
- `0x180021610`
- `0x1800223c4`
- `0x18002265c`
- `0x1800266e0`
- `0x18002b400`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180021818`
- `KERNEL32!GetLastError` at `0x180021818`
- `KERNEL32!GetCurrentThreadId` at `0x180021670`
- `KERNEL32!GetCurrentThreadId` at `0x18002168d`
- `KERNEL32!GetCurrentThreadId` at `0x180021670`
- `KERNEL32!GetCurrentThreadId` at `0x18002168d`
- `KERNEL32!EnterCriticalSection` at `0x180021681`
- `KERNEL32!EnterCriticalSection` at `0x180021681`
- `KERNEL32!FindClose` at `0x180021a04`
- `KERNEL32!FindClose` at `0x180021a04`
- `KERNEL32!CloseHandle` at `0x180021b24`
- `KERNEL32!CloseHandle` at `0x180021b24`
- `KERNEL32!GetFileAttributesExW` at `0x1800217d2`
- `KERNEL32!GetFileAttributesExW` at `0x1800217d2`
- `KERNEL32!FindFirstFileExW` at `0x1800219f5`
- `KERNEL32!FindFirstFileExW` at `0x1800219f5`
- `KERNEL32!CreateDirectoryW` at `0x18002180a`
- `KERNEL32!CreateDirectoryW` at `0x18002180a`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180021921`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180021921`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180021928`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180021928`

## string_xrefs

- `0x18002185a`: `Log path %s is not valid.  Reverting to default log path`
- `0x180021bbb`: `==========A logging failure has occured. The process has encountered an error when writing to the log file. The messages in the log file may not be complete.`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall OLog::Flush(_QWORD *a1, unsigned __int8 a2)
{
  unsigned int v2; // r13d
  _QWORD *v3; // rsi
  _QWORD *v4; // r15
  _QWORD *v5; // r14
  _QWORD *v6; // r12
  char v7; // r12
  const WCHAR *v8; // rbx
  const wchar_t *v9; // rdx
  const wchar_t *v10; // rcx
  wchar_t *v11; // rax
  unsigned __int64 v12; // r9
  wchar_t **v13; // rcx
  const WCHAR *v14; // rcx
  __int128 v15; // xmm6
  __int128 v16; // xmm7
  void *v17; // rcx
  const WCHAR *v18; // rax
  const WCHAR *v19; // rax
  HANDLE FirstFile; // rax
  __int64 v21; // rbx
  __int64 v22; // r14
  void *v23; // rcx
  _QWORD *v24; // rax
  _QWORD *v25; // r15
  _QWORD *v26; // r14
  char v29[8]; // [rsp+40h] [rbp-338h] BYREF
  struct _RTL_CRITICAL_SECTION *v30; // [rsp+48h] [rbp-330h] BYREF
  char v31; // [rsp+50h] [rbp-328h]
  int v32; // [rsp+58h] [rbp-320h]
  _QWORD *v33; // [rsp+60h] [rbp-318h]
  _BYTE FileInformation[40]; // [rsp+68h] [rbp-310h] BYREF
  wchar_t *S1[2]; // [rsp+90h] [rbp-2E8h] BYREF
  size_t N; // [rsp+A0h] [rbp-2D8h]
  unsigned __int64 v37; // [rsp+A8h] [rbp-2D0h]
  __int128 v38; // [rsp+B0h] [rbp-2C8h] BYREF
  __int128 v39; // [rsp+C0h] [rbp-2B8h]
  _BYTE FindFileData[592]; // [rsp+D0h] [rbp-2A8h] BYREF

  v2 = a2;
  v3 = a1;
  v4 = a1;
  v33 = a1;
  v32 = 0;
  v30 = &CriticalSection;
  v31 = 0;
  if ( dword_180065BB4 != GetCurrentThreadId() )
  {
    EnterCriticalSection(&CriticalSection);
    ++dword_180065BB0;
    dword_180065BB4 = GetCurrentThreadId();
    v31 = 1;
  }
  v5 = (_QWORD *)v3[5];
  v6 = (_QWORD *)v3[6];
  if ( v6 != v5 )
  {
    if ( *((_BYTE *)v3 + 1) > (unsigned __int8)v2 )
    {
      if ( v5 != v6 )
      {
        do
        {
          std::wstring::_Tidy_deallocate(v5 + 1);
          v5[1] = 19937;
          v5[3] = 0;
          v5[4] = 15;
          v5 += 5;
        }
        while ( v5 != v6 );
        v3[6] = v3[5];
      }
      *((_BYTE *)v3 + 1) = 0;
      return AcquireExclusive<OLock>::~AcquireExclusive<OLock>(&v30);
    }
    v7 = 0;
    if ( v3[14] != -1 )
      goto LABEL_49;
    v8 = (const WCHAR *)(v3 + 1);
    if ( !v3[3] )
    {
LABEL_38:
      if ( !v3[3] )
      {
        OPath::GetTempPathW(v3 + 1);
        memset(FileInformation, 0, 32);
        std::wstring::_Construct<1,wchar_t const *>(FileInformation, L"Office(*).log", 13);
        OPath::Combine(v3 + 1, FileInformation, v3 + 1);
        std::wstring::_Tidy_deallocate(FileInformation);
      }
      OLog::EnsureUniqueFileName((OLog *)v3);
      memset(FindFileData, 0, sizeof(FindFileData));
      v19 = (const WCHAR *)(v3 + 1);
      if ( v3[4] > 7u )
        v19 = *(const WCHAR **)v8;
      if ( !v19 )
        goto LABEL_67;
      if ( v3[4] > 7u )
        v8 = *(const WCHAR **)v8;
      FirstFile = FindFirstFileExW(v8, FindExInfoStandard, FindFileData, FindExSearchNameMatch, 0, 0);
      if ( FirstFile == (HANDLE)-1LL || (FindClose(FirstFile), (FindFileData[0] & 0x10) != 0) )
      {
LABEL_67:
        try
        {
          *(_OWORD *)FileInformation = 0;
          *(__m128i *)&FileInformation[16] = _mm_load_si128((const __m128i *)&_xmm);
          *(_WORD *)FileInformation = 0;
          OFile::Open(v3 + 8, v3 + 1, 1);
        }
        catch ( OException )
        {
          v7 = 1;
          v4 = v33;
          v3 = v33;
          LOBYTE(v2) = a2;
        }
        if ( v7 )
        {
LABEL_61:
          v25 = (_QWORD *)v3[6];
          v26 = (_QWORD *)v3[5];
          if ( v26 != v25 )
          {
            do
            {
              std::wstring::_Tidy_deallocate(v26 + 1);
              v26[1] = 19937;
              v26[3] = 0;
              v26[4] = 15;
              v26 += 5;
            }
            while ( v26 != v25 );
            v3[6] = v3[5];
          }
          *((_BYTE *)v3 + 1) = 0;
          if ( v7 )
          {
            *(_OWORD *)&FileInformation[8] = 0;
            *(__m128i *)&FileInformation[24] = _mm_load_si128((const __m128i *)&_xmm);
            *(_WORD *)&FileInformation[8] = 0;
            FileInformation[0] = v2;
            std::wstring::operator=(
              &FileInformation[8],
              L"==========A logging failure has occured. The process has encountered an error when writing to the log file"
               ". The messages in the log file may not be complete.");
            std::vector<OLog::OLogLine>::insert(v3 + 5, v29, v3[5], FileInformation);
            std::wstring::_Tidy_deallocate(&FileInformation[8]);
          }
          return AcquireExclusive<OLock>::~AcquireExclusive<OLock>(&v30);
        }
      }
      else
      {
        OFile::Open(v3 + 8, v3 + 1, 0);
        *(_OWORD *)&FileInformation[8] = 0;
        *(__m128i *)&FileInformation[24] = _mm_load_si128((const __m128i *)&_xmm);
        *(_WORD *)&FileInformation[8] = 0;
        FileInformation[0] = 50;
        std::vector<OLog::OLogLine>::insert(v3 + 5, v29, v3[5], FileInformation);
        std::wstring::_Tidy_deallocate(&FileInformation[8]);
      }
LABEL_49:
      v21 = v3[5];
      v22 = v3[6];
      while ( v21 != v22 )
      {
        if ( *(_BYTE *)v21 <= (unsigned __int8)v2 )
        {
          OString::UnicodeToAnsi(FileInformation, (LPCWCH)(v21 + 8));
          std::string::append(FileInformation);
          if ( !(unsigned __int8)OFile::TryWrite(v3 + 8, FileInformation) )
          {
            v23 = (void *)v4[14];
            if ( v23 != (void *)-1LL )
            {
              CloseHandle(v23);
              v4[14] = -1;
              v24 = v4 + 10;
              v4[12] = 0;
              if ( v4[13] > 7u )
                v24 = (_QWORD *)*v24;
              *(_WORD *)v24 = 0;
            }
            v7 = 1;
            std::string::_Tidy_deallocate(FileInformation);
            goto LABEL_61;
          }
          *((_BYTE *)v3 + 128) = 1;
          std::string::_Tidy_deallocate(FileInformation);
        }
        v21 += 40;
      }
      goto LABEL_61;
    }
    *(_OWORD *)S1 = 0;
    N = 0;
    v37 = 7;
    LOWORD(S1[0]) = 0;
    OPath::GetDirectoryName(v3 + 1, S1);
    v9 = (const wchar_t *)(v3 + 1);
    if ( v3[4] > 7u )
      v9 = *(const wchar_t **)v8;
    v10 = (const wchar_t *)S1;
    v11 = S1[0];
    v12 = v37;
    if ( v37 > 7 )
      v10 = S1[0];
    if ( N == v3[3] )
    {
      if ( !N || !wmemcmp(v10, v9, N) )
      {
LABEL_37:
        std::wstring::_Tidy_deallocate(S1);
        goto LABEL_38;
      }
      v12 = v37;
      v11 = S1[0];
    }
    memset(FileInformation, 0, 36);
    v13 = S1;
    if ( v12 > 7 )
      v13 = (wchar_t **)v11;
    if ( !GetFileAttributesExW((LPCWSTR)v13, GetFileExInfoStandard, FileInformation)
      || *(_DWORD *)FileInformation == -1
      || (FileInformation[0] & 0x10) == 0 )
    {
      v14 = (const WCHAR *)S1;
      if ( v37 > 7 )
        v14 = S1[0];
      if ( !CreateDirectoryW(v14, 0) && GetLastError() != 183 )
      {
        if ( !*((_BYTE *)v3 + 129) )
        {
          *(_OWORD *)FileInformation = 0;
          *(__m128i *)&FileInformation[16] = _mm_load_si128((const __m128i *)&_xmm);
          *(_WORD *)FileInformation = 0;
          ArgumentWriter::Format<std::wstring>(
            &v38,
            L"Log path %s is not valid.  Reverting to default log path",
            56,
            v3 + 1);
          v15 = v38;
          v16 = v39;
          LOWORD(v38) = 0;
          *(_QWORD *)&v39 = 0;
          *((_QWORD *)&v39 + 1) = 7;
          std::wstring::_Tidy_deallocate(&v38);
          *(_QWORD *)&v38 = 19937;
          std::wstring::_Tidy_deallocate(FileInformation);
          *(_OWORD *)FileInformation = v15;
          *(_OWORD *)&FileInformation[16] = v16;
          _mm_lfence();
          OLog::AddLine(v3, v2, FileInformation);
          if ( *(_QWORD *)&FileInformation[24] > 7u )
          {
            v17 = *(void **)FileInformation;
            if ( (unsigned __int64)(2LL * *(_QWORD *)&FileInformation[24] + 2) >= 0x1000 )
            {
              v17 = *(void **)(*(_QWORD *)FileInformation - 8LL);
              if ( (unsigned __int64)(*(_QWORD *)FileInformation - (_QWORD)v17 - 8LL) > 0x1F )
                _invoke_watson(0, 0, 0, 0, 0);
            }
            free(v17);
          }
        }
        v3[3] = 0;
        v18 = (const WCHAR *)(v3 + 1);
        if ( v3[4] > 7u )
          v18 = *(const WCHAR **)v8;
        *v18 = 0;
      }
    }
    goto LABEL_37;
  }
  return AcquireExclusive<OLock>::~AcquireExclusive<OLock>(&v30);
}

```

## disassembly

```asm
0x180021610  mov     rax, rsp
0x180021613  mov     [rax+18h], rbx
0x180021617  mov     [rax+20h], rsi
0x18002161b  push    rdi
0x18002161c  push    r12
0x18002161e  push    r13
0x180021620  push    r14
0x180021622  push    r15
0x180021624  sub     rsp, 350h
0x18002162b  movaps  xmmword ptr [rax-38h], xmm6
0x18002162f  movaps  xmmword ptr [rax-48h], xmm7
0x180021633  mov     rax, cs:__security_cookie
0x18002163a  xor     rax, rsp
0x18002163d  mov     [rsp+378h+var_58], rax
0x180021645  movzx   r13d, dl
0x180021649  mov     rsi, rcx
0x18002164c  mov     r15, rcx
0x18002164f  mov     [rsp+378h+var_318], rcx
0x180021654  mov     [rsp+378h+var_340], r13b
0x180021659  xor     edi, edi
0x18002165b  mov     [rsp+378h+var_320], edi
0x18002165f  lea     rbx, CriticalSection
0x180021666  mov     [rsp+378h+var_330], rbx
0x18002166b  mov     [rsp+378h+var_328], dil
0x180021670  call    cs:__imp_GetCurrentThreadId
0x180021676  cmp     cs:dword_180065BB4, eax
0x18002167c  jz      short loc_18002169E
0x18002167e  mov     rcx, rbx; lpCriticalSection
0x180021681  call    cs:__imp_EnterCriticalSection
0x180021687  inc     cs:dword_180065BB0
0x18002168d  call    cs:__imp_GetCurrentThreadId
0x180021693  mov     cs:dword_180065BB4, eax
0x180021699  mov     [rsp+378h+var_328], 1
0x18002169e  mov     r14, [rsi+28h]
0x1800216a2  mov     r12, [rsi+30h]
0x1800216a6  cmp     r12, r14
0x1800216a9  jz      loc_180021BEF
0x1800216af  cmp     [rsi+1], r13b
0x1800216b3  jbe     short loc_1800216F1
0x1800216b5  cmp     r14, r12
0x1800216b8  jz      short loc_1800216E8
0x1800216ba  lea     rcx, [r14+8]
0x1800216be  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800216c3  mov     qword ptr [r14+8], 4DE1h
0x1800216cb  mov     [r14+18h], rdi
0x1800216cf  mov     qword ptr [r14+20h], 0Fh
0x1800216d7  add     r14, 28h ; '('
0x1800216db  cmp     r14, r12
0x1800216de  jnz     short loc_1800216BA
0x1800216e0  mov     rax, [rsi+28h]
0x1800216e4  mov     [rsi+30h], rax
0x1800216e8  mov     [rsi+1], dil
0x1800216ec  jmp     loc_180021BEF
0x1800216f1  mov     r12b, dil
0x1800216f4  cmp     qword ptr [rsi+70h], 0FFFFFFFFFFFFFFFFh
0x1800216f9  jnz     loc_180021AB8
0x1800216ff  lea     rbx, [rsi+8]
0x180021703  cmp     [rbx+10h], rdi
0x180021707  jz      loc_18002194F
0x18002170d  xorps   xmm0, xmm0
0x180021710  movups  xmmword ptr [rsp+378h+S1], xmm0
0x180021718  mov     [rsp+378h+N], rdi
0x180021720  mov     [rsp+378h+var_2D0], 7
0x18002172c  mov     word ptr [rsp+378h+S1], di
0x180021734  lea     rdx, [rsp+378h+S1]
0x18002173c  mov     rcx, rbx
0x18002173f  call    ?GetDirectoryName@OPath@@SAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAV23@@Z; OPath::GetDirectoryName(std::wstring const &,std::wstring &)
0x180021744  mov     rdx, rbx
0x180021747  cmp     qword ptr [rbx+18h], 7
0x18002174c  jbe     short loc_180021751
0x18002174e  mov     rdx, [rbx]; S2
0x180021751  mov     r8, [rsp+378h+N]; N
0x180021759  lea     rcx, [rsp+378h+S1]
0x180021761  mov     rax, [rsp+378h+S1]
0x180021769  mov     r9, [rsp+378h+var_2D0]
0x180021771  cmp     r9, 7
0x180021775  cmova   rcx, rax; S1
0x180021779  cmp     r8, [rbx+10h]
0x18002177d  jnz     short loc_1800217A5
0x18002177f  test    r8, r8
0x180021782  jz      loc_180021942
0x180021788  call    wmemcmp
0x18002178d  test    eax, eax
0x18002178f  jz      loc_180021942
0x180021795  mov     r9, [rsp+378h+var_2D0]
0x18002179d  mov     rax, [rsp+378h+S1]
0x1800217a5  xorps   xmm0, xmm0
0x1800217a8  xor     ecx, ecx
0x1800217aa  movups  [rsp+378h+FileInformation], xmm0
0x1800217af  movups  [rsp+378h+var_300], xmm0
0x1800217b4  mov     [rsp+378h+var_2F0], ecx
0x1800217bb  lea     rcx, [rsp+378h+S1]
0x1800217c3  cmp     r9, 7
0x1800217c7  cmova   rcx, rax; lpFileName
0x1800217cb  lea     r8, [rsp+378h+FileInformation]; lpFileInformation
0x1800217d0  xor     edx, edx; fInfoLevelId
0x1800217d2  call    cs:__imp_GetFileAttributesExW
0x1800217d8  test    eax, eax
0x1800217da  jz      short loc_1800217EE
0x1800217dc  cmp     dword ptr [rsp+378h+FileInformation], 0FFFFFFFFh
0x1800217e1  jz      short loc_1800217EE
0x1800217e3  test    byte ptr [rsp+378h+FileInformation], 10h
0x1800217e8  jnz     loc_180021942
0x1800217ee  lea     rcx, [rsp+378h+S1]
0x1800217f6  cmp     [rsp+378h+var_2D0], 7
0x1800217ff  cmova   rcx, [rsp+378h+S1]; lpPathName
0x180021808  xor     edx, edx; lpSecurityAttributes
0x18002180a  call    cs:__imp_CreateDirectoryW
0x180021810  test    eax, eax
0x180021812  jnz     loc_180021942
0x180021818  call    cs:__imp_GetLastError
0x18002181e  cmp     eax, 0B7h
0x180021823  jz      loc_180021942
0x180021829  cmp     [rsi+81h], dil
0x180021830  jnz     loc_18002192E
0x180021836  xorps   xmm0, xmm0
0x180021839  movups  [rsp+378h+FileInformation], xmm0
0x18002183e  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180021846  movdqu  [rsp+378h+var_300], xmm1
0x18002184c  mov     word ptr [rsp+378h+FileInformation], di
0x180021851  mov     r9, rbx
0x180021854  mov     r8d, 38h ; '8'
0x18002185a  lea     rdx, aLogPathSIsNotV; "Log path %s is not valid.  Reverting to"...
0x180021861  lea     rcx, [rsp+378h+var_2C8]
0x180021869  call    ??$Format@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@ArgumentWriter@@CA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W_KAEBV12@@Z; ArgumentWriter::Format<std::wstring>(wchar_t const *,unsigned __int64,std::wstring const &)
0x18002186e  movups  xmm6, [rsp+378h+var_2C8]
0x180021876  movups  xmm7, [rsp+378h+var_2B8]
0x18002187e  mov     word ptr [rsp+378h+var_2C8], di
0x180021886  mov     qword ptr [rsp+378h+var_2B8], rdi
0x18002188e  mov     qword ptr [rsp+378h+var_2B8+8], 7
0x18002189a  lea     rcx, [rsp+378h+var_2C8]
0x1800218a2  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800218a7  mov     qword ptr [rsp+378h+var_2C8], 4DE1h
0x1800218b3  lea     rcx, [rsp+378h+FileInformation]
0x1800218b8  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800218bd  movups  [rsp+378h+FileInformation], xmm6
0x1800218c2  movups  [rsp+378h+var_300], xmm7
0x1800218c7  lfence
0x1800218ca  mov     edx, r13d
0x1800218cd  lea     r8, [rsp+378h+FileInformation]
0x1800218d2  mov     rcx, rsi
0x1800218d5  call    ?AddLine@OLog@@QEAAXW4Severity@Logging@Mso@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_N@Z; OLog::AddLine(Mso::Logging::Severity,std::wstring const &,bool)
0x1800218da  nop
0x1800218db  mov     rax, qword ptr [rsp+378h+var_300+8]
0x1800218e3  cmp     rax, 7
0x1800218e7  jbe     short loc_18002192E
0x1800218e9  mov     rcx, qword ptr [rsp+378h+FileInformation]; Block
0x1800218ee  mov     rdx, rcx
0x1800218f1  lea     rax, ds:2[rax*2]
0x1800218f9  cmp     rax, 1000h
0x1800218ff  jb      short loc_180021928
0x180021901  mov     rcx, [rcx-8]
0x180021905  sub     rdx, rcx
0x180021908  lea     rax, [rdx-8]
0x18002190c  cmp     rax, 1Fh
0x180021910  jbe     short loc_180021928
0x180021912  mov     [rsp+378h+Reserved], rdi; Reserved
0x180021917  xor     r9d, r9d; LineNo
0x18002191a  xor     r8d, r8d; FileName
0x18002191d  xor     edx, edx; FunctionName
0x18002191f  xor     ecx, ecx; Expression
0x180021921  call    cs:__imp__invoke_watson
0x180021928  call    cs:__imp_free
0x18002192e  mov     [rbx+10h], rdi
0x180021932  mov     rax, rbx
0x180021935  cmp     qword ptr [rbx+18h], 7
0x18002193a  jbe     short loc_18002193F
0x18002193c  mov     rax, [rbx]
0x18002193f  mov     [rax], di
0x180021942  lea     rcx, [rsp+378h+S1]
0x18002194a  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002194f  cmp     [rsi+18h], rdi
0x180021953  jnz     short loc_18002199F
0x180021955  mov     rcx, rbx; Src
0x180021958  call    ?GetTempPathW@OPath@@SAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; OPath::GetTempPathW(std::wstring &)
0x18002195d  xorps   xmm0, xmm0
0x180021960  movups  [rsp+378h+FileInformation], xmm0
0x180021965  xorps   xmm1, xmm1
0x180021968  movdqu  [rsp+378h+var_300], xmm1
0x18002196e  mov     r8d, 0Dh
0x180021974  lea     rdx, aOfficeLog; "Office(*).log"
0x18002197b  lea     rcx, [rsp+378h+FileInformation]
0x180021980  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180021985  mov     r8, rbx
0x180021988  lea     rdx, [rsp+378h+FileInformation]
0x18002198d  mov     rcx, rbx
0x180021990  call    ?Combine@OPath@@SAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0AEAV23@@Z; OPath::Combine(std::wstring const &,std::wstring const &,std::wstring &)
0x180021995  lea     rcx, [rsp+378h+FileInformation]
0x18002199a  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002199f  mov     rcx, rsi; this
0x1800219a2  call    ?EnsureUniqueFileName@OLog@@AEAAXXZ; OLog::EnsureUniqueFileName(void)
0x1800219a7  xor     edx, edx; Val
0x1800219a9  mov     r8d, 250h; Size
0x1800219af  lea     rcx, [rsp+378h+FindFileData]; void *
0x1800219b7  call    memset
0x1800219bc  mov     rax, rbx
0x1800219bf  cmp     qword ptr [rbx+18h], 7
0x1800219c4  jbe     short loc_1800219C9
0x1800219c6  mov     rax, [rbx]
0x1800219c9  test    rax, rax
0x1800219cc  jz      loc_180021A6B
0x1800219d2  cmp     qword ptr [rbx+18h], 7
0x1800219d7  jbe     short loc_1800219DC
0x1800219d9  mov     rbx, [rbx]
0x1800219dc  mov     [rsp+378h+dwAdditionalFlags], edi; dwAdditionalFlags
0x1800219e0  mov     [rsp+378h+Reserved], rdi; lpSearchFilter
0x1800219e5  xor     r9d, r9d; fSearchOp
0x1800219e8  lea     r8, [rsp+378h+FindFileData]; lpFindFileData
0x1800219f0  xor     edx, edx; fInfoLevelId
0x1800219f2  mov     rcx, rbx; lpFileName
0x1800219f5  call    cs:__imp_FindFirstFileExW
0x1800219fb  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800219ff  jz      short loc_180021A6B
0x180021a01  mov     rcx, rax; hFindFile
0x180021a04  call    cs:__imp_FindClose
0x180021a0a  test    [rsp+378h+FindFileData], 10h
0x180021a12  jnz     short loc_180021A6B
0x180021a14  lea     rdx, [rsi+8]
0x180021a18  lea     rcx, [rsi+40h]
0x180021a1c  xor     r8d, r8d
0x180021a1f  call    ?Open@OFile@@QEAA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@W4FileMode@fm@@W4FileAccess@fa@@W4FileShare@fs@@_N@Z; OFile::Open(std::wstring const &,fm::FileMode,fa::FileAccess,fs::FileShare,bool)
0x180021a24  xorps   xmm0, xmm0
0x180021a27  movups  [rsp+378h+FileInformation+8], xmm0
0x180021a2c  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180021a34  movdqu  [rsp+378h+var_300+8], xmm1
0x180021a3d  mov     word ptr [rsp+378h+FileInformation+8], di
0x180021a42  mov     byte ptr [rsp+378h+FileInformation], 32h ; '2'
0x180021a47  mov     r8, [rsi+28h]
0x180021a4b  lea     rcx, [rsi+28h]
0x180021a4f  lea     r9, [rsp+378h+FileInformation]
0x180021a54  lea     rdx, [rsp+378h+var_338]
0x180021a59  call    ?insert@?$vector@UOLogLine@OLog@@V?$allocator@UOLogLine@OLog@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UOLogLine@OLog@@@std@@@std@@@2@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@UOLogLine@OLog@@@std@@@std@@@2@AEBUOLogLine@OLog@@@Z; std::vector<OLog::OLogLine>::insert(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<OLog::OLogLine>>>,OLog::OLogLine const &)
0x180021a5e  nop
0x180021a5f  lea     rcx, [rsp+378h+FileInformation+8]
0x180021a64  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180021a69  jmp     short loc_180021AB8
0x180021a6b  xorps   xmm0, xmm0
0x180021a6e  movups  [rsp+378h+FileInformation], xmm0
0x180021a73  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180021a7b  movdqu  [rsp+378h+var_300], xmm1
0x180021a81  mov     word ptr [rsp+378h+FileInformation], di
0x180021a86  lea     rdx, [rsi+8]
0x180021a8a  lea     rcx, [rsi+40h]
0x180021a8e  mov     r8d, 1
0x180021a94  call    ?Open@OFile@@QEAA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@W4FileMode@fm@@W4FileAccess@fa@@W4FileShare@fs@@_N@Z; OFile::Open(std::wstring const &,fm::FileMode,fa::FileAccess,fs::FileShare,bool)
0x180021a99  jmp     short loc_180021AAF
0x180021a9b  xor     edi, edi
0x180021a9d  mov     r12b, [rsp+378h+var_348]
0x180021aa2  mov     r15, [rsp+378h+var_318]
0x180021aa7  mov     rsi, r15
0x180021aaa  mov     r13b, [rsp+378h+var_340]
0x180021aaf  test    r12b, r12b
0x180021ab2  jnz     loc_180021B54
0x180021ab8  mov     rbx, [rsi+28h]
0x180021abc  mov     r14, [rsi+30h]
0x180021ac0  jmp     short loc_180021B13
0x180021ac2  cmp     [rbx], r13b
0x180021ac5  ja      short loc_180021B0F
0x180021ac7  lea     rdx, [rbx+8]; lpWideCharStr
0x180021acb  lea     rcx, [rsp+378h+FileInformation]; Src
0x180021ad0  call    ?UnicodeToAnsi@OString@@SA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@3@I@Z; OString::UnicodeToAnsi(std::wstring const &,uint)
0x180021ad5  mov     r8d, 2
0x180021adb  lea     rdx, asc_180058008; "\r\n"
0x180021ae2  lea     rcx, [rsp+378h+FileInformation]; Src
0x180021ae7  call    ?append@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD_K@Z; std::string::append(char const * const,unsigned __int64)
0x180021aec  lea     rcx, [rsi+40h]
0x180021af0  lea     rdx, [rsp+378h+FileInformation]
0x180021af5  call    ?TryWrite@OFile@@QEAA_NAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; OFile::TryWrite(std::string const &)
0x180021afa  test    al, al
0x180021afc  jz      short loc_180021B1A
0x180021afe  mov     byte ptr [rsi+80h], 1
0x180021b05  lea     rcx, [rsp+378h+FileInformation]
0x180021b0a  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180021b0f  add     rbx, 28h ; '('
0x180021b13  cmp     rbx, r14
0x180021b16  jnz     short loc_180021AC2
0x180021b18  jmp     short loc_180021B54
0x180021b1a  mov     rcx, [r15+70h]; hObject
0x180021b1e  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180021b22  jz      short loc_180021B47
0x180021b24  call    cs:__imp_CloseHandle
0x180021b2a  mov     qword ptr [r15+70h], 0FFFFFFFFFFFFFFFFh
0x180021b32  lea     rax, [r15+50h]
0x180021b36  mov     [rax+10h], rdi
0x180021b3a  cmp     qword ptr [rax+18h], 7
0x180021b3f  jbe     short loc_180021B44
0x180021b41  mov     rax, [rax]
0x180021b44  mov     [rax], di
0x180021b47  mov     r12b, 1
0x180021b4a  lea     rcx, [rsp+378h+FileInformation]
0x180021b4f  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180021b54  mov     r15, [rsi+30h]
0x180021b58  mov     r14, [rsi+28h]
0x180021b5c  cmp     r14, r15
0x180021b5f  jz      short loc_180021B8F
0x180021b61  lea     rcx, [r14+8]
0x180021b65  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180021b6a  mov     qword ptr [r14+8], 4DE1h
0x180021b72  mov     [r14+18h], rdi
0x180021b76  mov     qword ptr [r14+20h], 0Fh
  ... truncated ...
```
