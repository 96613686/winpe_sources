# UtilGetTempFile(tlx::unique_any<tlx::file_handle_traits> *,wchar_t const *,wchar_t const *,wchar_t *,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong)

- ea: `0x1400158e8`
- end: `0x140015e54`
- name: `?UtilGetTempFile@@YAJPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@PEB_W1PEA_WKPEAU_SECURITY_ATTRIBUTES@@KK@Z`
- size: `1388`
- prototype: ``
- caller_count: `7`
- callee_count: `16`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140017998`
- `0x140021b9c`
- `0x140021f64`
- `0x14002430c`
- `0x140029018`
- `0x1400311d8`
- `0x14005bf14`

## callees

- `0x140002490`
- `0x140002748`
- `0x1400030f8`
- `0x1400054e4`
- `0x14000aab4`
- `0x14000aad4`
- `0x14000b50c`
- `0x14000ca20`
- `0x14000d544`
- `0x1400130f8`
- `0x140014f14`
- `0x140015580`
- `0x1400158e8`
- `0x14001637c`
- `0x14001646c`
- `0x140016564`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140015ce3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140015ce3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140015c73`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140015d66`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140015daa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140015c73`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140015d66`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140015daa`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140015c02`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140015c02`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x140015cce`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x140015cce`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x140015a77`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x140015a77`

## string_xrefs

- `0x140015952`: `onecore\windows\feedback\core\common\lib\utilitydownlevel.cpp`
- `0x140015a39`: `onecore\windows\feedback\core\common\lib\utilitydownlevel.cpp`
- `0x140015ba2`: `onecore\windows\feedback\core\common\lib\utilitydownlevel.cpp`
- `0x140015c29`: `onecore\windows\feedback\core\common\lib\utilitydownlevel.cpp`
- `0x140015c5c`: `onecore\windows\feedback\core\common\lib\utilitydownlevel.cpp`
- `0x140015dff`: `onecore\windows\feedback\core\common\lib\utilitydownlevel.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall UtilGetTempFile(
        void **a1,
        WCHAR *a2,
        __int64 a3,
        wchar_t *a4,
        __int64 a5,
        struct _SECURITY_ATTRIBUTES *lpSecurityAttributes,
        DWORD a7,
        int a8)
{
  __int64 v12; // rdx
  int TempDirPath; // ebx
  unsigned int v14; // edx
  __int64 v15; // r8
  __int64 v16; // rdx
  const WCHAR *v17; // rcx
  __int64 v18; // r9
  LPCWSTR v19; // rdx
  const wchar_t *v20; // r8
  DWORD FileAttributesW; // eax
  __int64 v23; // rdx
  int v24; // eax
  HANDLE FileW; // rax
  int v26; // r8d
  const char *v27; // r9
  void *v28; // rbx
  void *v29; // rsi
  int v30; // edi
  __int64 v31; // rdx
  signed int LastError; // eax
  void *v33; // rcx
  int dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  int dwCreationDispositiona; // [rsp+20h] [rbp-E0h]
  LPCWSTR lpFileName; // [rsp+40h] [rbp-C0h] BYREF
  _WORD *v37; // [rsp+48h] [rbp-B8h]
  _WORD v38[8]; // [rsp+50h] [rbp-B0h] BYREF
  LPCWSTR lpszShortPath[2]; // [rsp+60h] [rbp-A0h] BYREF
  _WORD v40[8]; // [rsp+70h] [rbp-90h] BYREF
  DWORD dwShareMode[4]; // [rsp+80h] [rbp-80h]
  wchar_t v42[40]; // [rsp+90h] [rbp-70h] BYREF
  WCHAR FileName[264]; // [rsp+E0h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+348h] [rbp+248h]

  dwShareMode[0] = a7;
  if ( !a4 )
  {
    v12 = 75;
LABEL_3:
    TempDirPath = -2147024809;
LABEL_4:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\windows\\feedback\\core\\common\\lib\\utilitydownlevel.cpp",
      (const char *)(unsigned int)TempDirPath,
      dwCreationDisposition);
    return (unsigned int)TempDirPath;
  }
  memset_0(FileName, 0, 0x208u);
  if ( !a2 )
  {
    TempDirPath = UtilGetTempDirPath(FileName, v14);
    if ( TempDirPath < 0 )
    {
      v12 = 80;
      goto LABEL_4;
    }
    a2 = FileName;
  }
  if ( !*a2 )
  {
    v12 = 89;
    goto LABEL_3;
  }
  lpFileName = v38;
  v37 = v38;
  v38[0] = 0;
  v15 = -1;
  do
    ++v15;
  while ( a2[v15] );
  if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                           &lpFileName,
                           a2) )
  {
    v16 = 94;
LABEL_22:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v16,
      (unsigned int)"onecore\\windows\\feedback\\core\\common\\lib\\utilitydownlevel.cpp",
      (const char *)0x8007000ELL,
      dwCreationDisposition);
    if ( lpFileName != v38 )
      operator delete((void *)lpFileName, (const struct std::nothrow_t *)&std::nothrow);
    return 2147942414LL;
  }
  v17 = lpFileName;
  if ( (unsigned __int64)(v37 - lpFileName) >= 4 )
  {
    v18 = 4;
    v19 = lpFileName;
    v20 = L"\\\\?\\";
    while ( *v20 == *v19 )
    {
      ++v20;
      ++v19;
      if ( !--v18 )
        goto LABEL_26;
    }
  }
  if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::insert(&lpFileName) )
  {
    v16 = 100;
    goto LABEL_22;
  }
  v17 = lpFileName;
LABEL_26:
  FileAttributesW = GetFileAttributesW(v17);
  if ( FileAttributesW == -1 || (FileAttributesW & 0x10) == 0 )
  {
    TempDirPath = -2147024809;
    v23 = 106;
    goto LABEL_74;
  }
  if ( a3 )
  {
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_SS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        (unsigned int)WPP_69e296c8cfbe35481aeff25676a4a37b_Traceguids,
        (_DWORD)lpFileName,
        a3);
    }
  }
  else if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_69e296c8cfbe35481aeff25676a4a37b_Traceguids, lpFileName);
  }
  TempDirPath = UtilUuidCreateAsString(v42);
  if ( TempDirPath < 0 )
  {
    v23 = 118;
LABEL_74:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v23,
      (unsigned int)"onecore\\windows\\feedback\\core\\common\\lib\\utilitydownlevel.cpp",
      (const char *)(unsigned int)TempDirPath,
      dwCreationDisposition);
LABEL_75:
    if ( lpFileName != v38 )
      operator delete((void *)lpFileName, (const struct std::nothrow_t *)&std::nothrow);
    return (unsigned int)TempDirPath;
  }
  lpszShortPath[0] = v40;
  lpszShortPath[1] = v40;
  v40[0] = 0;
  v24 = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
          lpszShortPath,
          L"%ls%lsWER.%ls.tmp%ls");
  TempDirPath = v24;
  if ( v24 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7F,
      (unsigned int)"onecore\\windows\\feedback\\core\\common\\lib\\utilitydownlevel.cpp",
      (const char *)(unsigned int)v24,
      (int)v42);
    goto LABEL_39;
  }
  FileW = CreateFileW(lpszShortPath[0], 0xC0000000, dwShareMode[0], lpSecurityAttributes, 1u, a8 | 0x80u, 0);
  v28 = FileW;
  v29 = FileW;
  *(_QWORD *)dwShareMode = FileW;
  if ( (unsigned __int64)FileW + 1 <= 1 )
  {
    TempDirPath = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x8A,
                    (unsigned int)"onecore\\windows\\feedback\\core\\common\\lib\\utilitydownlevel.cpp",
                    v27);
LABEL_39:
    if ( lpszShortPath[0] != v40 )
      operator delete((void *)lpszShortPath[0], (const struct std::nothrow_t *)&std::nothrow);
    goto LABEL_75;
  }
  v30 = UtilVerifyFilePath((wchar_t *)lpszShortPath[0], FileW, v26, (int)v27);
  if ( v30 < 0 )
  {
    v31 = 142;
LABEL_45:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v31,
      (unsigned int)"onecore\\windows\\feedback\\core\\common\\lib\\utilitydownlevel.cpp",
      (const char *)(unsigned int)v30,
      dwCreationDispositiona);
    CloseHandle(v28);
    if ( lpszShortPath[0] != v40 )
      operator delete((void *)lpszShortPath[0], (const struct std::nothrow_t *)&std::nothrow);
    if ( lpFileName != v38 )
      operator delete((void *)lpFileName, (const struct std::nothrow_t *)&std::nothrow);
    return (unsigned int)v30;
  }
  if ( GetLongPathNameW(lpszShortPath[0], a4, 0x104u) - 1 > 0x102 )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    if ( LastError >= 0 )
      LastError = -2147467259;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        12,
        WPP_69e296c8cfbe35481aeff25676a4a37b_Traceguids,
        (unsigned int)LastError);
    }
    v30 = StringCchCopyW(a4, 0x104u, lpszShortPath[0]);
    if ( v30 < 0 )
    {
      v31 = 154;
      goto LABEL_45;
    }
  }
  if ( a1 )
  {
    v29 = 0;
    v33 = *a1;
    *a1 = v28;
    if ( (unsigned __int64)v33 + 1 > 1 )
      CloseHandle(v33);
  }
  if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_69e296c8cfbe35481aeff25676a4a37b_Traceguids, a4);
  }
  if ( (unsigned __int64)v29 + 1 > 1 )
    CloseHandle(v29);
  if ( lpszShortPath[0] != v40 )
    operator delete((void *)lpszShortPath[0], (const struct std::nothrow_t *)&std::nothrow);
  if ( lpFileName != v38 )
    operator delete((void *)lpFileName, (const struct std::nothrow_t *)&std::nothrow);
  return 0;
}

```

## disassembly

```asm
0x1400158e8  push    rbp
0x1400158ea  push    rbx
0x1400158eb  push    rsi
0x1400158ec  push    rdi
0x1400158ed  push    r12
0x1400158ef  push    r13
0x1400158f1  push    r14
0x1400158f3  push    r15
0x1400158f5  lea     rbp, [rsp-208h]
0x1400158fd  sub     rsp, 308h
0x140015904  mov     rax, cs:__security_cookie
0x14001590b  xor     rax, rsp
0x14001590e  mov     [rbp+240h+var_50], rax
0x140015915  mov     r12, r9
0x140015918  mov     rdi, r8
0x14001591b  mov     rbx, rdx
0x14001591e  mov     r15, rcx
0x140015921  mov     r13, [rbp+240h+lpSecurityAttributes]
0x140015928  mov     eax, [rbp+240h+arg_30]
0x14001592e  mov     [rbp+240h+dwShareMode], eax
0x140015931  mov     esi, [rbp+240h+arg_38]
0x140015937  xor     r14d, r14d
0x14001593a  test    r9, r9
0x14001593d  jnz     short loc_140015963
0x14001593f  lea     edx, [r9+4Bh]; void *
0x140015943  mov     ebx, 80070057h
0x140015948  mov     rcx, [rbp+248h]; this
0x14001594f  mov     r9d, ebx; char *
0x140015952  lea     r8, aOnecoreWindows_8; "onecore\\windows\\feedback\\core\\commo"...
0x140015959  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001595e  jmp     loc_140015E2E
0x140015963  xor     edx, edx; Val
0x140015965  mov     r8d, 208h; Size
0x14001596b  lea     rcx, [rbp+240h+FileName]; void *
0x14001596f  call    memset_0
0x140015974  test    rbx, rbx
0x140015977  jnz     short loc_140015993
0x140015979  lea     rcx, [rbp+240h+FileName]; lpFileName
0x14001597d  call    ?UtilGetTempDirPath@@YAJPEA_WK@Z; UtilGetTempDirPath(wchar_t *,ulong)
0x140015982  mov     ebx, eax
0x140015984  test    eax, eax
0x140015986  jns     short loc_14001598F
0x140015988  mov     edx, 50h ; 'P'
0x14001598d  jmp     short loc_140015948
0x14001598f  lea     rbx, [rbp+240h+FileName]
0x140015993  cmp     [rbx], r14w
0x140015997  jnz     short loc_1400159A0
0x140015999  mov     edx, 59h ; 'Y'
0x14001599e  jmp     short loc_140015943
0x1400159a0  lea     rax, [rsp+340h+var_2F0]
0x1400159a5  mov     [rsp+340h+lpFileName], rax
0x1400159aa  lea     rax, [rsp+340h+var_2F0]
0x1400159af  mov     [rsp+340h+var_2F8], rax
0x1400159b4  mov     [rsp+340h+var_2F0], r14w
0x1400159ba  or      r8, 0FFFFFFFFFFFFFFFFh
0x1400159be  inc     r8
0x1400159c1  cmp     [rbx+r8*2], r14w
0x1400159c6  jnz     short loc_1400159BE
0x1400159c8  mov     rdx, rbx
0x1400159cb  lea     rcx, [rsp+340h+lpFileName]
0x1400159d0  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x1400159d5  test    al, al
0x1400159d7  jnz     short loc_1400159E0
0x1400159d9  mov     edx, 5Eh ; '^'
0x1400159de  jmp     short loc_140015A33
0x1400159e0  mov     rax, [rsp+340h+var_2F8]
0x1400159e5  mov     rcx, [rsp+340h+lpFileName]
0x1400159ea  sub     rax, rcx
0x1400159ed  sar     rax, 1
0x1400159f0  mov     ebx, 4
0x1400159f5  cmp     rax, rbx
0x1400159f8  jb      short loc_140015A20
0x1400159fa  mov     r9d, ebx
0x1400159fd  mov     rdx, rcx
0x140015a00  lea     r8, asc_1400679F0; "\\\\?\\"
0x140015a07  movzx   eax, word ptr [rdx]
0x140015a0a  cmp     [r8], ax
0x140015a0e  jnz     short loc_140015A20
0x140015a10  add     r8, 2
0x140015a14  add     rdx, 2
0x140015a18  sub     r9, 1
0x140015a1c  jnz     short loc_140015A07
0x140015a1e  jmp     short loc_140015A77
0x140015a20  lea     rcx, [rsp+340h+lpFileName]
0x140015a25  call    ?insert@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_KPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::insert(unsigned __int64,wchar_t const *)
0x140015a2a  test    al, al
0x140015a2c  jnz     short loc_140015A72
0x140015a2e  mov     edx, 64h ; 'd'; void *
0x140015a33  mov     r9d, 8007000Eh; char *
0x140015a39  lea     r8, aOnecoreWindows_8; "onecore\\windows\\feedback\\core\\commo"...
0x140015a40  mov     rcx, [rbp+248h]; this
0x140015a47  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140015a4c  nop
0x140015a4d  lea     rax, [rsp+340h+var_2F0]
0x140015a52  mov     rcx, [rsp+340h+lpFileName]; void *
0x140015a57  cmp     rcx, rax
0x140015a5a  jz      short loc_140015A68
0x140015a5c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140015a63  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140015a68  mov     eax, 8007000Eh
0x140015a6d  jmp     loc_140015E30
0x140015a72  mov     rcx, [rsp+340h+lpFileName]; lpFileName
0x140015a77  call    cs:__imp_GetFileAttributesW
0x140015a7e  nop     dword ptr [rax+rax+00h]
0x140015a83  cmp     eax, 0FFFFFFFFh
0x140015a86  jz      loc_140015DF2
0x140015a8c  test    al, 10h
0x140015a8e  jz      loc_140015DF2
0x140015a94  test    rdi, rdi
0x140015a97  jz      short loc_140015AD2
0x140015a99  lea     r14, WPP_GLOBAL_Control
0x140015aa0  mov     rcx, cs:WPP_GLOBAL_Control
0x140015aa7  cmp     rcx, r14
0x140015aaa  jz      short loc_140015B04
0x140015aac  test    [rcx+1Ch], bl
0x140015aaf  jz      short loc_140015B04
0x140015ab1  mov     edx, 0Ah
0x140015ab6  mov     qword ptr [rsp+340h+dwCreationDisposition], rdi
0x140015abb  mov     r9, [rsp+340h+lpFileName]
0x140015ac0  lea     r8, WPP_69e296c8cfbe35481aeff25676a4a37b_Traceguids
0x140015ac7  mov     rcx, [rcx+10h]
0x140015acb  call    WPP_SF_SS
0x140015ad0  jmp     short loc_140015B04
0x140015ad2  lea     r14, WPP_GLOBAL_Control
0x140015ad9  mov     rcx, cs:WPP_GLOBAL_Control
0x140015ae0  cmp     rcx, r14
0x140015ae3  jz      short loc_140015B04
0x140015ae5  test    [rcx+1Ch], bl
0x140015ae8  jz      short loc_140015B04
0x140015aea  mov     edx, 0Bh
0x140015aef  mov     r9, [rsp+340h+lpFileName]
0x140015af4  lea     r8, WPP_69e296c8cfbe35481aeff25676a4a37b_Traceguids
0x140015afb  mov     rcx, [rcx+10h]
0x140015aff  call    WPP_SF_S
0x140015b04  lea     rcx, [rbp+240h+var_2B0]; wchar_t *
0x140015b08  call    ?UtilUuidCreateAsString@@YAJPEA_W@Z; UtilUuidCreateAsString(wchar_t *)
0x140015b0d  mov     ebx, eax
0x140015b0f  test    eax, eax
0x140015b11  jns     short loc_140015B1D
0x140015b13  mov     edx, 76h ; 'v'
0x140015b18  jmp     loc_140015DFC
0x140015b1d  lea     rax, [rsp+340h+var_2D0]
0x140015b22  mov     [rsp+340h+lpszShortPath], rax
0x140015b27  lea     rax, [rsp+340h+var_2D0]
0x140015b2c  mov     [rsp+340h+var_2D8], rax
0x140015b31  xor     eax, eax
0x140015b33  mov     [rsp+340h+var_2D0], ax
0x140015b38  lea     r9, pwzValue
0x140015b3f  test    rdi, rdi
0x140015b42  cmovz   rdi, r9
0x140015b46  mov     r8, [rsp+340h+lpFileName]
0x140015b4b  mov     rax, [rsp+340h+var_2F8]
0x140015b50  cmp     r8, rax
0x140015b53  jz      short loc_140015B64
0x140015b55  mov     ecx, 5Ch ; '\'
0x140015b5a  cmp     cx, [rax-2]
0x140015b5e  jnz     short loc_140015B64
0x140015b60  mov     al, 1
0x140015b62  jmp     short loc_140015B66
0x140015b64  xor     al, al
0x140015b66  lea     rcx, SubBlock; "\\"
0x140015b6d  test    al, al
0x140015b6f  cmovz   r9, rcx
0x140015b73  mov     qword ptr [rsp+340h+dwFlagsAndAttributes], rdi
0x140015b78  lea     rax, [rbp+240h+var_2B0]
0x140015b7c  mov     qword ptr [rsp+340h+dwCreationDisposition], rax; int
0x140015b81  lea     rdx, aLsLswerLsTmpLs; "%ls%lsWER.%ls.tmp%ls"
0x140015b88  lea     rcx, [rsp+340h+lpszShortPath]
0x140015b8d  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x140015b92  mov     ebx, eax
0x140015b94  test    eax, eax
0x140015b96  jns     short loc_140015BD8
0x140015b98  mov     rcx, [rbp+248h]; this
0x140015b9f  mov     r9d, eax; char *
0x140015ba2  lea     r8, aOnecoreWindows_8; "onecore\\windows\\feedback\\core\\commo"...
0x140015ba9  mov     edx, 7Fh; void *
0x140015bae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140015bb3  nop
0x140015bb4  lea     rax, [rsp+340h+var_2D0]
0x140015bb9  mov     rcx, [rsp+340h+lpszShortPath]; void *
0x140015bbe  cmp     rcx, rax
0x140015bc1  jz      loc_140015E13
0x140015bc7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140015bce  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140015bd3  jmp     loc_140015E13
0x140015bd8  bts     esi, 7
0x140015bdc  mov     [rsp+340h+hTemplateFile], 0; hTemplateFile
0x140015be5  mov     [rsp+340h+dwFlagsAndAttributes], esi; dwFlagsAndAttributes
0x140015be9  mov     [rsp+340h+dwCreationDisposition], 1; int
0x140015bf1  mov     r9, r13; lpSecurityAttributes
0x140015bf4  mov     r8d, [rbp+240h+dwShareMode]; dwShareMode
0x140015bf8  mov     edx, 0C0000000h; dwDesiredAccess
0x140015bfd  mov     rcx, [rsp+340h+lpszShortPath]; lpFileName
0x140015c02  call    cs:__imp_CreateFileW
0x140015c09  nop     dword ptr [rax+rax+00h]
0x140015c0e  mov     rbx, rax
0x140015c11  mov     rsi, rax
0x140015c14  mov     qword ptr [rbp+240h+dwShareMode], rax
0x140015c18  lea     rcx, [rax+1]
0x140015c1c  cmp     rcx, 1
0x140015c20  ja      short loc_140015C41
0x140015c22  mov     rcx, [rbp+248h]; this
0x140015c29  lea     r8, aOnecoreWindows_8; "onecore\\windows\\feedback\\core\\commo"...
0x140015c30  mov     edx, 8Ah; void *
0x140015c35  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140015c3a  mov     ebx, eax
0x140015c3c  jmp     loc_140015BB4
0x140015c41  mov     rdx, rbx; void *
0x140015c44  mov     rcx, [rsp+340h+lpszShortPath]; wchar_t *
0x140015c49  call    ?UtilVerifyFilePath@@YAJPEB_WPEAX@Z; UtilVerifyFilePath(wchar_t const *,void *)
0x140015c4e  mov     edi, eax
0x140015c50  test    eax, eax
0x140015c52  jns     short loc_140015CBE
0x140015c54  mov     edx, 8Eh; void *
0x140015c59  mov     r9d, edi; char *
0x140015c5c  lea     r8, aOnecoreWindows_8; "onecore\\windows\\feedback\\core\\commo"...
0x140015c63  mov     rcx, [rbp+248h]; this
0x140015c6a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140015c6f  nop
0x140015c70  mov     rcx, rbx; hObject
0x140015c73  call    cs:__imp_CloseHandle
0x140015c7a  nop     dword ptr [rax+rax+00h]
0x140015c7f  nop
0x140015c80  lea     rax, [rsp+340h+var_2D0]
0x140015c85  mov     rcx, [rsp+340h+lpszShortPath]; void *
0x140015c8a  cmp     rcx, rax
0x140015c8d  jz      short loc_140015C9C
0x140015c8f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140015c96  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140015c9b  nop
0x140015c9c  lea     rax, [rsp+340h+var_2F0]
0x140015ca1  mov     rcx, [rsp+340h+lpFileName]; void *
0x140015ca6  cmp     rcx, rax
0x140015ca9  jz      short loc_140015CB7
0x140015cab  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140015cb2  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140015cb7  mov     eax, edi
0x140015cb9  jmp     loc_140015E30
0x140015cbe  mov     edi, 104h
0x140015cc3  mov     r8d, edi; cchBuffer
0x140015cc6  mov     rdx, r12; lpszLongPath
0x140015cc9  mov     rcx, [rsp+340h+lpszShortPath]; lpszShortPath
0x140015cce  call    cs:__imp_GetLongPathNameW
0x140015cd5  nop     dword ptr [rax+rax+00h]
0x140015cda  dec     eax
0x140015cdc  cmp     eax, 102h
0x140015ce1  jbe     short loc_140015D4F
0x140015ce3  call    cs:__imp_GetLastError
0x140015cea  nop     dword ptr [rax+rax+00h]
0x140015cef  test    eax, eax
0x140015cf1  jle     short loc_140015CFB
0x140015cf3  movzx   eax, ax
0x140015cf6  or      eax, 80070000h
0x140015cfb  mov     ecx, 80004005h
0x140015d00  test    eax, eax
0x140015d02  cmovns  eax, ecx
0x140015d05  mov     rcx, cs:WPP_GLOBAL_Control
0x140015d0c  cmp     rcx, r14
0x140015d0f  jz      short loc_140015D2F
0x140015d11  test    byte ptr [rcx+1Ch], 2
0x140015d15  jz      short loc_140015D2F
0x140015d17  mov     edx, 0Ch
0x140015d1c  mov     r9d, eax
0x140015d1f  lea     r8, WPP_69e296c8cfbe35481aeff25676a4a37b_Traceguids
0x140015d26  mov     rcx, [rcx+10h]
0x140015d2a  call    WPP_SF_d
0x140015d2f  mov     r8, [rsp+340h+lpszShortPath]; wchar_t *
0x140015d34  mov     rdx, rdi; unsigned __int64
0x140015d37  mov     rcx, r12; wchar_t *
0x140015d3a  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x140015d3f  mov     edi, eax
0x140015d41  test    eax, eax
0x140015d43  jns     short loc_140015D4F
0x140015d45  mov     edx, 9Ah
0x140015d4a  jmp     loc_140015C59
0x140015d4f  test    r15, r15
0x140015d52  jz      short loc_140015D72
0x140015d54  xor     esi, esi
0x140015d56  mov     rcx, [r15]; hObject
0x140015d59  mov     [r15], rbx
0x140015d5c  lea     rax, [rcx+1]
0x140015d60  cmp     rax, 1
0x140015d64  jbe     short loc_140015D72
0x140015d66  call    cs:__imp_CloseHandle
0x140015d6d  nop     dword ptr [rax+rax+00h]
0x140015d72  mov     rcx, cs:WPP_GLOBAL_Control
0x140015d79  cmp     rcx, r14
0x140015d7c  jz      short loc_140015D9D
0x140015d7e  test    byte ptr [rcx+1Ch], 4
0x140015d82  jz      short loc_140015D9D
0x140015d84  mov     edx, 0Dh
0x140015d89  mov     r9, r12
0x140015d8c  lea     r8, WPP_69e296c8cfbe35481aeff25676a4a37b_Traceguids
0x140015d93  mov     rcx, [rcx+10h]
0x140015d97  call    WPP_SF_S
0x140015d9c  nop
0x140015d9d  lea     rax, [rsi+1]
0x140015da1  cmp     rax, 1
0x140015da5  jbe     short loc_140015DB7
0x140015da7  mov     rcx, rsi; hObject
  ... truncated ...
```
