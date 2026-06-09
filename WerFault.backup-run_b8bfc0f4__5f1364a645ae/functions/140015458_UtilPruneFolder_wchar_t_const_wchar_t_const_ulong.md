# UtilPruneFolder(wchar_t const *,wchar_t const *,ulong)

- ea: `0x140015458`
- end: `0x140015703`
- name: `?UtilPruneFolder@@YAJPEB_W0K@Z`
- size: `683`
- prototype: `__int64 __fastcall(const wchar_t *, const wchar_t *, unsigned int)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x14003546c`
- `0x14003c398`

## callees

- `0x140002470`
- `0x140002728`
- `0x1400030a8`
- `0x140005430`
- `0x140014474`
- `0x140015458`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001564a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140015659`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001564a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140015659`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1400155c9`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x14001563b`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1400155c9`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x14001563b`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x140015534`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x140015534`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1400155bc`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1400155bc`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1400155e3`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1400155e3`

## pseudocode

```c
__int64 __fastcall UtilPruneFolder(const wchar_t *a1, const wchar_t *a2, int a3)
{
  const wchar_t *v3; // r13
  int v4; // edi
  CUserModeHangReport *v5; // rcx
  __int64 v6; // rdx
  int v7; // r15d
  int v8; // r12d
  HANDLE FirstFileW; // rbx
  int dwLowDateTime; // r14d
  int dwHighDateTime; // edi
  unsigned int v12; // esi
  unsigned int v13; // r13d
  signed int LastError; // eax
  __int64 v16; // [rsp+20h] [rbp-E0h]
  FILETIME ftLastWriteTime; // [rsp+30h] [rbp-D0h]
  LPCWSTR v19; // [rsp+38h] [rbp-C8h] BYREF
  const WCHAR *v20; // [rsp+40h] [rbp-C0h]
  _WORD v21[8]; // [rsp+48h] [rbp-B8h] BYREF
  LPCWSTR lpFileName[2]; // [rsp+58h] [rbp-A8h] BYREF
  _WORD v23[12]; // [rsp+68h] [rbp-98h] BYREF
  _WIN32_FIND_DATAW FindFileData; // [rsp+80h] [rbp-80h] BYREF

  LODWORD(v16) = a3;
  v3 = a1;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  lpFileName[0] = v23;
  lpFileName[1] = v23;
  v23[0] = 0;
  v19 = v21;
  v20 = v21;
  v21[0] = 0;
  v4 = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
         lpFileName,
         L"%ls\\%ls",
         v3,
         L"*.dmp");
  if ( v4 >= 0 )
  {
    v7 = 0;
    v8 = 0;
    while ( 1 )
    {
      FirstFileW = FindFirstFileW(lpFileName[0], &FindFileData);
      if ( FirstFileW == (HANDLE)-1LL )
        break;
      dwLowDateTime = -1;
      dwHighDateTime = -1;
      v20 = v19;
      v12 = 0;
      *v19 = 0;
      while ( 1 )
      {
        if ( *(_QWORD *)&FindFileData.ftLastWriteTime < __PAIR64__(dwHighDateTime, dwLowDateTime)
          && *(_QWORD *)&FindFileData.ftLastWriteTime > __PAIR64__(v8, v7) )
        {
          ftLastWriteTime = FindFileData.ftLastWriteTime;
          v4 = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
                 &v19,
                 L"%ls\\%ls",
                 v3,
                 FindFileData.cFileName,
                 v16);
          if ( v4 < 0 )
          {
            if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                35,
                WPP_69e296c8cfbe35481aeff25676a4a37b_Traceguids,
                (unsigned int)v4);
            }
            FindClose(FirstFileW);
            goto LABEL_35;
          }
          dwHighDateTime = ftLastWriteTime.dwHighDateTime;
          dwLowDateTime = ftLastWriteTime.dwLowDateTime;
        }
        v13 = v12++;
        if ( !FindNextFileW(FirstFileW, &FindFileData) )
          break;
        v3 = a1;
      }
      FindClose(FirstFileW);
      if ( v12 <= (unsigned int)v16 )
        goto LABEL_26;
      if ( v19 == v20 )
      {
        v4 = -2147467259;
        goto LABEL_35;
      }
      if ( DeleteFileW(v19) )
      {
        if ( v13 <= (unsigned int)v16 )
          goto LABEL_26;
      }
      else
      {
        v7 = dwLowDateTime;
        v8 = dwHighDateTime;
      }
      v3 = a1;
    }
    if ( GetLastError() == 2 )
    {
LABEL_26:
      v4 = 0;
      goto LABEL_35;
    }
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    if ( LastError >= 0 )
      LastError = -2147467259;
    v4 = LastError;
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v6 = 34;
      goto LABEL_34;
    }
  }
  else
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v6 = 33;
LABEL_34:
      WPP_SF_d(*((_QWORD *)v5 + 2), v6, WPP_69e296c8cfbe35481aeff25676a4a37b_Traceguids, (unsigned int)v4);
    }
  }
LABEL_35:
  if ( v19 != v21 )
    operator delete((void *)v19, (const struct std::nothrow_t *)&std::nothrow);
  if ( lpFileName[0] != v23 )
    operator delete((void *)lpFileName[0], (const struct std::nothrow_t *)&std::nothrow);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x140015458  push    rbp
0x14001545a  push    rbx
0x14001545b  push    rsi
0x14001545c  push    rdi
0x14001545d  push    r12
0x14001545f  push    r13
0x140015461  push    r14
0x140015463  push    r15
0x140015465  lea     rbp, [rsp-1E8h]
0x14001546d  sub     rsp, 2E8h
0x140015474  mov     rax, cs:__security_cookie
0x14001547b  xor     rax, rsp
0x14001547e  mov     [rbp+220h+var_50], rax
0x140015485  mov     dword ptr [rsp+320h+var_300], r8d
0x14001548a  mov     r13, rcx
0x14001548d  mov     [rsp+320h+var_2F8], rcx
0x140015492  mov     r8d, 250h; Size
0x140015498  lea     rcx, [rbp+220h+FindFileData]; void *
0x14001549c  xor     edx, edx; Val
0x14001549e  call    memset_0
0x1400154a3  lea     rax, [rsp+320h+var_2B8]
0x1400154a8  mov     r8, r13
0x1400154ab  mov     [rsp+320h+lpFileName], rax
0x1400154b0  lea     r9, aDmp; "*.dmp"
0x1400154b7  lea     rax, [rsp+320h+var_2B8]
0x1400154bc  mov     [rsp+320h+var_2C0], rax
0x1400154c1  lea     rdx, aLsLs; "%ls\\%ls"
0x1400154c8  xor     eax, eax
0x1400154ca  lea     rcx, [rsp+320h+lpFileName]
0x1400154cf  mov     [rsp+320h+var_2B8], ax
0x1400154d4  lea     rax, [rsp+320h+var_2D8]
0x1400154d9  mov     [rsp+320h+var_2E8], rax
0x1400154de  lea     rax, [rsp+320h+var_2D8]
0x1400154e3  mov     [rsp+320h+var_2E0], rax
0x1400154e8  xor     eax, eax
0x1400154ea  mov     [rsp+320h+var_2D8], ax
0x1400154ef  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x1400154f4  mov     edi, eax
0x1400154f6  test    eax, eax
0x1400154f8  jns     short loc_140015525
0x1400154fa  mov     rcx, cs:WPP_GLOBAL_Control
0x140015501  lea     rax, WPP_GLOBAL_Control
0x140015508  cmp     rcx, rax
0x14001550b  jz      loc_1400156A8
0x140015511  test    byte ptr [rcx+1Ch], 1
0x140015515  jz      loc_1400156A8
0x14001551b  mov     edx, 21h ; '!'
0x140015520  jmp     loc_140015695
0x140015525  xor     r15d, r15d
0x140015528  xor     r12d, r12d
0x14001552b  mov     rcx, [rsp+320h+lpFileName]; lpFileName
0x140015530  lea     rdx, [rbp+220h+FindFileData]; lpFindFileData
0x140015534  call    cs:__imp_FindFirstFileW
0x14001553a  mov     rbx, rax
0x14001553d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140015541  jz      loc_14001564A
0x140015547  mov     rcx, [rsp+320h+var_2E8]
0x14001554c  or      r14d, 0FFFFFFFFh
0x140015550  or      edi, r14d
0x140015553  mov     [rsp+320h+var_2E0], rcx
0x140015558  xor     esi, esi
0x14001555a  xor     eax, eax
0x14001555c  mov     [rcx], ax
0x14001555f  jmp     short loc_140015566
0x140015561  mov     r13, [rsp+320h+var_2F8]
0x140015566  mov     ecx, [rbp+220h+FindFileData.ftLastWriteTime.dwHighDateTime]
0x140015569  mov     rax, [rbp-6Ch]
0x14001556d  cmp     ecx, edi
0x14001556f  jb      short loc_140015578
0x140015571  ja      short loc_1400155B0
0x140015573  cmp     eax, r14d
0x140015576  jnb     short loc_1400155B0
0x140015578  cmp     ecx, r12d
0x14001557b  jb      short loc_1400155B0
0x14001557d  ja      short loc_140015584
0x14001557f  cmp     eax, r15d
0x140015582  jbe     short loc_1400155B0
0x140015584  lea     r9, [rbp+220h+FindFileData.cFileName]
0x140015588  mov     [rsp+320h+var_2F0], rax
0x14001558d  mov     r8, r13
0x140015590  lea     rdx, aLsLs; "%ls\\%ls"
0x140015597  lea     rcx, [rsp+320h+var_2E8]
0x14001559c  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x1400155a1  mov     edi, eax
0x1400155a3  test    eax, eax
0x1400155a5  js      short loc_140015607
0x1400155a7  mov     edi, dword ptr [rsp+320h+var_2F0+4]
0x1400155ab  mov     r14d, dword ptr [rsp+320h+var_2F0]
0x1400155b0  mov     r13d, esi
0x1400155b3  lea     rdx, [rbp+220h+FindFileData]; lpFindFileData
0x1400155b7  mov     rcx, rbx; hFindFile
0x1400155ba  inc     esi
0x1400155bc  call    cs:__imp_FindNextFileW
0x1400155c2  test    eax, eax
0x1400155c4  jnz     short loc_140015561
0x1400155c6  mov     rcx, rbx; hFindFile
0x1400155c9  call    cs:__imp_FindClose
0x1400155cf  mov     ebx, dword ptr [rsp+320h+var_300]
0x1400155d3  cmp     esi, ebx
0x1400155d5  jbe     short loc_140015655
0x1400155d7  mov     rcx, [rsp+320h+var_2E8]; lpFileName
0x1400155dc  cmp     rcx, [rsp+320h+var_2E0]
0x1400155e1  jz      short loc_140015643
0x1400155e3  call    cs:__imp_DeleteFileW
0x1400155e9  test    eax, eax
0x1400155eb  jz      short loc_1400155FF
0x1400155ed  mov     esi, r13d
0x1400155f0  cmp     r13d, ebx
0x1400155f3  jbe     short loc_140015655
0x1400155f5  mov     r13, [rsp+320h+var_2F8]
0x1400155fa  jmp     loc_14001552B
0x1400155ff  mov     r15d, r14d
0x140015602  mov     r12d, edi
0x140015605  jmp     short loc_1400155F5
0x140015607  mov     rcx, cs:WPP_GLOBAL_Control
0x14001560e  lea     rax, WPP_GLOBAL_Control
0x140015615  cmp     rcx, rax
0x140015618  jz      short loc_140015638
0x14001561a  test    byte ptr [rcx+1Ch], 1
0x14001561e  jz      short loc_140015638
0x140015620  mov     rcx, [rcx+10h]
0x140015624  lea     r8, WPP_69e296c8cfbe35481aeff25676a4a37b_Traceguids
0x14001562b  mov     edx, 23h ; '#'
0x140015630  mov     r9d, edi
0x140015633  call    WPP_SF_d
0x140015638  mov     rcx, rbx; hFindFile
0x14001563b  call    cs:__imp_FindClose
0x140015641  jmp     short loc_1400156A8
0x140015643  mov     edi, 80004005h
0x140015648  jmp     short loc_1400156A8
0x14001564a  call    cs:__imp_GetLastError
0x140015650  cmp     eax, 2
0x140015653  jnz     short loc_140015659
0x140015655  xor     edi, edi
0x140015657  jmp     short loc_1400156A8
0x140015659  call    cs:__imp_GetLastError
0x14001565f  test    eax, eax
0x140015661  jle     short loc_14001566B
0x140015663  movzx   eax, ax
0x140015666  or      eax, 80070000h
0x14001566b  mov     edi, 80004005h
0x140015670  test    eax, eax
0x140015672  cmovns  eax, edi
0x140015675  mov     edi, eax
0x140015677  mov     rcx, cs:WPP_GLOBAL_Control
0x14001567e  lea     rax, WPP_GLOBAL_Control
0x140015685  cmp     rcx, rax
0x140015688  jz      short loc_1400156A8
0x14001568a  test    byte ptr [rcx+1Ch], 1
0x14001568e  jz      short loc_1400156A8
0x140015690  mov     edx, 22h ; '"'
0x140015695  mov     rcx, [rcx+10h]
0x140015699  lea     r8, WPP_69e296c8cfbe35481aeff25676a4a37b_Traceguids
0x1400156a0  mov     r9d, edi
0x1400156a3  call    WPP_SF_d
0x1400156a8  mov     rcx, [rsp+320h+var_2E8]; void *
0x1400156ad  lea     rax, [rsp+320h+var_2D8]
0x1400156b2  cmp     rcx, rax
0x1400156b5  jz      short loc_1400156C3
0x1400156b7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400156be  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400156c3  mov     rcx, [rsp+320h+lpFileName]; void *
0x1400156c8  lea     rax, [rsp+320h+var_2B8]
0x1400156cd  cmp     rcx, rax
0x1400156d0  jz      short loc_1400156DE
0x1400156d2  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400156d9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400156de  mov     eax, edi
0x1400156e0  mov     rcx, [rbp+220h+var_50]
0x1400156e7  xor     rcx, rsp; StackCookie
0x1400156ea  call    __security_check_cookie
0x1400156ef  add     rsp, 2E8h
0x1400156f6  pop     r15
0x1400156f8  pop     r14
0x1400156fa  pop     r13
0x1400156fc  pop     r12
0x1400156fe  pop     rdi
0x1400156ff  pop     rsi
0x140015700  pop     rbx
0x140015701  pop     rbp
0x140015702  retn
```
