# UtilPruneFolder(wchar_t const *,wchar_t const *,ulong)

- ea: `0x140015fa8`
- end: `0x140016282`
- name: `?UtilPruneFolder@@YAJPEB_W0K@Z`
- size: `730`
- prototype: `__int64 __fastcall(const wchar_t *, const wchar_t *, unsigned int)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x140037978`
- `0x14003ecdc`

## callees

- `0x140002490`
- `0x140002748`
- `0x1400030f8`
- `0x1400054e4`
- `0x140014f14`
- `0x140015fa8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400161bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400161d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400161bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400161d1`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x140016125`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1400161a7`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x140016125`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1400161a7`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x140016084`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x140016084`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x140016112`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x140016112`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x140016149`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x140016149`

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
0x140015fa8  push    rbp
0x140015faa  push    rbx
0x140015fab  push    rsi
0x140015fac  push    rdi
0x140015fad  push    r12
0x140015faf  push    r13
0x140015fb1  push    r14
0x140015fb3  push    r15
0x140015fb5  lea     rbp, [rsp-1E8h]
0x140015fbd  sub     rsp, 2E8h
0x140015fc4  mov     rax, cs:__security_cookie
0x140015fcb  xor     rax, rsp
0x140015fce  mov     [rbp+220h+var_50], rax
0x140015fd5  mov     dword ptr [rsp+320h+var_300], r8d
0x140015fda  mov     r13, rcx
0x140015fdd  mov     [rsp+320h+var_2F8], rcx
0x140015fe2  mov     r8d, 250h; Size
0x140015fe8  lea     rcx, [rbp+220h+FindFileData]; void *
0x140015fec  xor     edx, edx; Val
0x140015fee  call    memset_0
0x140015ff3  lea     rax, [rsp+320h+var_2B8]
0x140015ff8  mov     r8, r13
0x140015ffb  mov     [rsp+320h+lpFileName], rax
0x140016000  lea     r9, aDmp; "*.dmp"
0x140016007  lea     rax, [rsp+320h+var_2B8]
0x14001600c  mov     [rsp+320h+var_2C0], rax
0x140016011  lea     rdx, aLsLs; "%ls\\%ls"
0x140016018  xor     eax, eax
0x14001601a  lea     rcx, [rsp+320h+lpFileName]
0x14001601f  mov     [rsp+320h+var_2B8], ax
0x140016024  lea     rax, [rsp+320h+var_2D8]
0x140016029  mov     [rsp+320h+var_2E8], rax
0x14001602e  lea     rax, [rsp+320h+var_2D8]
0x140016033  mov     [rsp+320h+var_2E0], rax
0x140016038  xor     eax, eax
0x14001603a  mov     [rsp+320h+var_2D8], ax
0x14001603f  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x140016044  mov     edi, eax
0x140016046  test    eax, eax
0x140016048  jns     short loc_140016075
0x14001604a  mov     rcx, cs:WPP_GLOBAL_Control
0x140016051  lea     rax, WPP_GLOBAL_Control
0x140016058  cmp     rcx, rax
0x14001605b  jz      loc_140016226
0x140016061  test    byte ptr [rcx+1Ch], 1
0x140016065  jz      loc_140016226
0x14001606b  mov     edx, 21h ; '!'
0x140016070  jmp     loc_140016213
0x140016075  xor     r15d, r15d
0x140016078  xor     r12d, r12d
0x14001607b  mov     rcx, [rsp+320h+lpFileName]; lpFileName
0x140016080  lea     rdx, [rbp+220h+FindFileData]; lpFindFileData
0x140016084  call    cs:__imp_FindFirstFileW
0x14001608b  nop     dword ptr [rax+rax+00h]
0x140016090  mov     rbx, rax
0x140016093  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140016097  jz      loc_1400161BC
0x14001609d  mov     rcx, [rsp+320h+var_2E8]
0x1400160a2  or      r14d, 0FFFFFFFFh
0x1400160a6  or      edi, r14d
0x1400160a9  mov     [rsp+320h+var_2E0], rcx
0x1400160ae  xor     esi, esi
0x1400160b0  xor     eax, eax
0x1400160b2  mov     [rcx], ax
0x1400160b5  jmp     short loc_1400160BC
0x1400160b7  mov     r13, [rsp+320h+var_2F8]
0x1400160bc  mov     ecx, [rbp+220h+FindFileData.ftLastWriteTime.dwHighDateTime]
0x1400160bf  mov     rax, [rbp-6Ch]
0x1400160c3  cmp     ecx, edi
0x1400160c5  jb      short loc_1400160CE
0x1400160c7  ja      short loc_140016106
0x1400160c9  cmp     eax, r14d
0x1400160cc  jnb     short loc_140016106
0x1400160ce  cmp     ecx, r12d
0x1400160d1  jb      short loc_140016106
0x1400160d3  ja      short loc_1400160DA
0x1400160d5  cmp     eax, r15d
0x1400160d8  jbe     short loc_140016106
0x1400160da  lea     r9, [rbp+220h+FindFileData.cFileName]
0x1400160de  mov     [rsp+320h+var_2F0], rax
0x1400160e3  mov     r8, r13
0x1400160e6  lea     rdx, aLsLs; "%ls\\%ls"
0x1400160ed  lea     rcx, [rsp+320h+var_2E8]
0x1400160f2  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x1400160f7  mov     edi, eax
0x1400160f9  test    eax, eax
0x1400160fb  js      short loc_140016173
0x1400160fd  mov     edi, dword ptr [rsp+320h+var_2F0+4]
0x140016101  mov     r14d, dword ptr [rsp+320h+var_2F0]
0x140016106  mov     r13d, esi
0x140016109  lea     rdx, [rbp+220h+FindFileData]; lpFindFileData
0x14001610d  mov     rcx, rbx; hFindFile
0x140016110  inc     esi
0x140016112  call    cs:__imp_FindNextFileW
0x140016119  nop     dword ptr [rax+rax+00h]
0x14001611e  test    eax, eax
0x140016120  jnz     short loc_1400160B7
0x140016122  mov     rcx, rbx; hFindFile
0x140016125  call    cs:__imp_FindClose
0x14001612c  nop     dword ptr [rax+rax+00h]
0x140016131  mov     ebx, dword ptr [rsp+320h+var_300]
0x140016135  cmp     esi, ebx
0x140016137  jbe     loc_1400161CD
0x14001613d  mov     rcx, [rsp+320h+var_2E8]; lpFileName
0x140016142  cmp     rcx, [rsp+320h+var_2E0]
0x140016147  jz      short loc_1400161B5
0x140016149  call    cs:__imp_DeleteFileW
0x140016150  nop     dword ptr [rax+rax+00h]
0x140016155  test    eax, eax
0x140016157  jz      short loc_14001616B
0x140016159  mov     esi, r13d
0x14001615c  cmp     r13d, ebx
0x14001615f  jbe     short loc_1400161CD
0x140016161  mov     r13, [rsp+320h+var_2F8]
0x140016166  jmp     loc_14001607B
0x14001616b  mov     r15d, r14d
0x14001616e  mov     r12d, edi
0x140016171  jmp     short loc_140016161
0x140016173  mov     rcx, cs:WPP_GLOBAL_Control
0x14001617a  lea     rax, WPP_GLOBAL_Control
0x140016181  cmp     rcx, rax
0x140016184  jz      short loc_1400161A4
0x140016186  test    byte ptr [rcx+1Ch], 1
0x14001618a  jz      short loc_1400161A4
0x14001618c  mov     rcx, [rcx+10h]
0x140016190  lea     r8, WPP_69e296c8cfbe35481aeff25676a4a37b_Traceguids
0x140016197  mov     edx, 23h ; '#'
0x14001619c  mov     r9d, edi
0x14001619f  call    WPP_SF_d
0x1400161a4  mov     rcx, rbx; hFindFile
0x1400161a7  call    cs:__imp_FindClose
0x1400161ae  nop     dword ptr [rax+rax+00h]
0x1400161b3  jmp     short loc_140016226
0x1400161b5  mov     edi, 80004005h
0x1400161ba  jmp     short loc_140016226
0x1400161bc  call    cs:__imp_GetLastError
0x1400161c3  nop     dword ptr [rax+rax+00h]
0x1400161c8  cmp     eax, 2
0x1400161cb  jnz     short loc_1400161D1
0x1400161cd  xor     edi, edi
0x1400161cf  jmp     short loc_140016226
0x1400161d1  call    cs:__imp_GetLastError
0x1400161d8  nop     dword ptr [rax+rax+00h]
0x1400161dd  test    eax, eax
0x1400161df  jle     short loc_1400161E9
0x1400161e1  movzx   eax, ax
0x1400161e4  or      eax, 80070000h
0x1400161e9  mov     edi, 80004005h
0x1400161ee  test    eax, eax
0x1400161f0  cmovns  eax, edi
0x1400161f3  mov     edi, eax
0x1400161f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400161fc  lea     rax, WPP_GLOBAL_Control
0x140016203  cmp     rcx, rax
0x140016206  jz      short loc_140016226
0x140016208  test    byte ptr [rcx+1Ch], 1
0x14001620c  jz      short loc_140016226
0x14001620e  mov     edx, 22h ; '"'
0x140016213  mov     rcx, [rcx+10h]
0x140016217  lea     r8, WPP_69e296c8cfbe35481aeff25676a4a37b_Traceguids
0x14001621e  mov     r9d, edi
0x140016221  call    WPP_SF_d
0x140016226  mov     rcx, [rsp+320h+var_2E8]; void *
0x14001622b  lea     rax, [rsp+320h+var_2D8]
0x140016230  cmp     rcx, rax
0x140016233  jz      short loc_140016241
0x140016235  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14001623c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140016241  mov     rcx, [rsp+320h+lpFileName]; void *
0x140016246  lea     rax, [rsp+320h+var_2B8]
0x14001624b  cmp     rcx, rax
0x14001624e  jz      short loc_14001625C
0x140016250  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140016257  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14001625c  mov     eax, edi
0x14001625e  mov     rcx, [rbp+220h+var_50]
0x140016265  xor     rcx, rsp; StackCookie
0x140016268  call    __security_check_cookie
0x14001626d  add     rsp, 2E8h
0x140016274  pop     r15
0x140016276  pop     r14
0x140016278  pop     r13
0x14001627a  pop     r12
0x14001627c  pop     rdi
0x14001627d  pop     rsi
0x14001627e  pop     rbx
0x14001627f  pop     rbp
0x140016280  retn
```
