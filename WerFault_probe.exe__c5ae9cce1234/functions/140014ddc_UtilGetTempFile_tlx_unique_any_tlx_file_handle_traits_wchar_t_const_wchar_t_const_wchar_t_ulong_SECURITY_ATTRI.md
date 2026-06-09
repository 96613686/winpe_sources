# UtilGetTempFile(tlx::unique_any<tlx::file_handle_traits> *,wchar_t const *,wchar_t const *,wchar_t *,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong)

- ea: `0x140014ddc`
- end: `0x14001531d`
- name: `?UtilGetTempFile@@YAJPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@PEB_W1PEA_WKPEAU_SECURITY_ATTRIBUTES@@KK@Z`
- size: `1345`
- prototype: ``
- caller_count: `7`
- callee_count: `16`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140016cbc`
- `0x1400205c8`
- `0x1400209ac`
- `0x140022c1c`
- `0x140027624`
- `0x14002f31c`
- `0x140058160`

## callees

- `0x140002470`
- `0x140002728`
- `0x1400030a8`
- `0x140005430`
- `0x14000a9a4`
- `0x14000a9c4`
- `0x14000b4cc`
- `0x14000c8a0`
- `0x14000d28c`
- `0x14001280c`
- `0x140014474`
- `0x140014a94`
- `0x140014ddc`
- `0x1400157ec`
- `0x1400158d4`
- `0x1400159cc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400151bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400151bf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001515b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001523c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001527a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001515b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001523c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001527a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1400150f0`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1400150f0`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x1400151b0`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x1400151b0`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x140014f6b`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x140014f6b`

## string_xrefs

- `0x140014e46`: `onecore\windows\feedback\core\common\lib\utilitydownlevel.cpp`
- `0x140014f2d`: `onecore\windows\feedback\core\common\lib\utilitydownlevel.cpp`
- `0x140015090`: `onecore\windows\feedback\core\common\lib\utilitydownlevel.cpp`
- `0x140015111`: `onecore\windows\feedback\core\common\lib\utilitydownlevel.cpp`
- `0x140015144`: `onecore\windows\feedback\core\common\lib\utilitydownlevel.cpp`
- `0x1400152c9`: `onecore\windows\feedback\core\common\lib\utilitydownlevel.cpp`

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
                           a2,
                           v15) )
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
        (unsigned int)&WPP_69e296c8cfbe35481aeff25676a4a37b_Traceguids,
        (_DWORD)lpFileName,
        a3);
    }
  }
  else if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_69e296c8cfbe35481aeff25676a4a37b_Traceguids, lpFileName);
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
        &WPP_69e296c8cfbe35481aeff25676a4a37b_Traceguids,
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
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_69e296c8cfbe35481aeff25676a4a37b_Traceguids, a4);
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
0x140014ddc  push    rbp
0x140014dde  push    rbx
0x140014ddf  push    rsi
0x140014de0  push    rdi
0x140014de1  push    r12
0x140014de3  push    r13
0x140014de5  push    r14
0x140014de7  push    r15
0x140014de9  lea     rbp, [rsp-208h]
0x140014df1  sub     rsp, 308h
0x140014df8  mov     rax, cs:__security_cookie
0x140014dff  xor     rax, rsp
0x140014e02  mov     [rbp+240h+var_50], rax
0x140014e09  mov     r12, r9
0x140014e0c  mov     rdi, r8
0x140014e0f  mov     rbx, rdx
0x140014e12  mov     r15, rcx
0x140014e15  mov     r13, [rbp+240h+lpSecurityAttributes]
0x140014e1c  mov     eax, [rbp+240h+arg_30]
0x140014e22  mov     [rbp+240h+dwShareMode], eax
0x140014e25  mov     esi, [rbp+240h+arg_38]
0x140014e2b  xor     r14d, r14d
0x140014e2e  test    r9, r9
0x140014e31  jnz     short loc_140014E57
0x140014e33  lea     edx, [r9+4Bh]; void *
0x140014e37  mov     ebx, 80070057h
0x140014e3c  mov     rcx, [rbp+248h]; this
0x140014e43  mov     r9d, ebx; char *
0x140014e46  lea     r8, aOnecoreWindows_8; "onecore\\windows\\feedback\\core\\commo"...
0x140014e4d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140014e52  jmp     loc_1400152F8
0x140014e57  xor     edx, edx; Val
0x140014e59  mov     r8d, 208h; Size
0x140014e5f  lea     rcx, [rbp+240h+FileName]; void *
0x140014e63  call    memset_0
0x140014e68  test    rbx, rbx
0x140014e6b  jnz     short loc_140014E87
0x140014e6d  lea     rcx, [rbp+240h+FileName]; lpFileName
0x140014e71  call    ?UtilGetTempDirPath@@YAJPEA_WK@Z; UtilGetTempDirPath(wchar_t *,ulong)
0x140014e76  mov     ebx, eax
0x140014e78  test    eax, eax
0x140014e7a  jns     short loc_140014E83
0x140014e7c  mov     edx, 50h ; 'P'
0x140014e81  jmp     short loc_140014E3C
0x140014e83  lea     rbx, [rbp+240h+FileName]
0x140014e87  cmp     [rbx], r14w
0x140014e8b  jnz     short loc_140014E94
0x140014e8d  mov     edx, 59h ; 'Y'
0x140014e92  jmp     short loc_140014E37
0x140014e94  lea     rax, [rsp+340h+var_2F0]
0x140014e99  mov     [rsp+340h+lpFileName], rax
0x140014e9e  lea     rax, [rsp+340h+var_2F0]
0x140014ea3  mov     [rsp+340h+var_2F8], rax
0x140014ea8  mov     [rsp+340h+var_2F0], r14w
0x140014eae  or      r8, 0FFFFFFFFFFFFFFFFh
0x140014eb2  inc     r8
0x140014eb5  cmp     [rbx+r8*2], r14w
0x140014eba  jnz     short loc_140014EB2
0x140014ebc  mov     rdx, rbx
0x140014ebf  lea     rcx, [rsp+340h+lpFileName]
0x140014ec4  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x140014ec9  test    al, al
0x140014ecb  jnz     short loc_140014ED4
0x140014ecd  mov     edx, 5Eh ; '^'
0x140014ed2  jmp     short loc_140014F27
0x140014ed4  mov     rax, [rsp+340h+var_2F8]
0x140014ed9  mov     rcx, [rsp+340h+lpFileName]
0x140014ede  sub     rax, rcx
0x140014ee1  sar     rax, 1
0x140014ee4  mov     ebx, 4
0x140014ee9  cmp     rax, rbx
0x140014eec  jb      short loc_140014F14
0x140014eee  mov     r9d, ebx
0x140014ef1  mov     rdx, rcx
0x140014ef4  lea     r8, asc_1400639F0; "\\\\?\\"
0x140014efb  movzx   eax, word ptr [rdx]
0x140014efe  cmp     [r8], ax
0x140014f02  jnz     short loc_140014F14
0x140014f04  add     r8, 2
0x140014f08  add     rdx, 2
0x140014f0c  sub     r9, 1
0x140014f10  jnz     short loc_140014EFB
0x140014f12  jmp     short loc_140014F6B
0x140014f14  lea     rcx, [rsp+340h+lpFileName]
0x140014f19  call    ?insert@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_KPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::insert(unsigned __int64,wchar_t const *)
0x140014f1e  test    al, al
0x140014f20  jnz     short loc_140014F66
0x140014f22  mov     edx, 64h ; 'd'; void *
0x140014f27  mov     r9d, 8007000Eh; char *
0x140014f2d  lea     r8, aOnecoreWindows_8; "onecore\\windows\\feedback\\core\\commo"...
0x140014f34  mov     rcx, [rbp+248h]; this
0x140014f3b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140014f40  nop
0x140014f41  lea     rax, [rsp+340h+var_2F0]
0x140014f46  mov     rcx, [rsp+340h+lpFileName]; void *
0x140014f4b  cmp     rcx, rax
0x140014f4e  jz      short loc_140014F5C
0x140014f50  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140014f57  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140014f5c  mov     eax, 8007000Eh
0x140014f61  jmp     loc_1400152FA
0x140014f66  mov     rcx, [rsp+340h+lpFileName]; lpFileName
0x140014f6b  call    cs:__imp_GetFileAttributesW
0x140014f71  cmp     eax, 0FFFFFFFFh
0x140014f74  jz      loc_1400152BC
0x140014f7a  test    al, 10h
0x140014f7c  jz      loc_1400152BC
0x140014f82  test    rdi, rdi
0x140014f85  jz      short loc_140014FC0
0x140014f87  lea     r14, WPP_GLOBAL_Control
0x140014f8e  mov     rcx, cs:WPP_GLOBAL_Control
0x140014f95  cmp     rcx, r14
0x140014f98  jz      short loc_140014FF2
0x140014f9a  test    [rcx+1Ch], bl
0x140014f9d  jz      short loc_140014FF2
0x140014f9f  mov     edx, 0Ah
0x140014fa4  mov     qword ptr [rsp+340h+dwCreationDisposition], rdi
0x140014fa9  mov     r9, [rsp+340h+lpFileName]
0x140014fae  lea     r8, WPP_69e296c8cfbe35481aeff25676a4a37b_Traceguids
0x140014fb5  mov     rcx, [rcx+10h]
0x140014fb9  call    WPP_SF_SS
0x140014fbe  jmp     short loc_140014FF2
0x140014fc0  lea     r14, WPP_GLOBAL_Control
0x140014fc7  mov     rcx, cs:WPP_GLOBAL_Control
0x140014fce  cmp     rcx, r14
0x140014fd1  jz      short loc_140014FF2
0x140014fd3  test    [rcx+1Ch], bl
0x140014fd6  jz      short loc_140014FF2
0x140014fd8  mov     edx, 0Bh
0x140014fdd  mov     r9, [rsp+340h+lpFileName]
0x140014fe2  lea     r8, WPP_69e296c8cfbe35481aeff25676a4a37b_Traceguids
0x140014fe9  mov     rcx, [rcx+10h]
0x140014fed  call    WPP_SF_S
0x140014ff2  lea     rcx, [rbp+240h+var_2B0]; wchar_t *
0x140014ff6  call    ?UtilUuidCreateAsString@@YAJPEA_W@Z; UtilUuidCreateAsString(wchar_t *)
0x140014ffb  mov     ebx, eax
0x140014ffd  test    eax, eax
0x140014fff  jns     short loc_14001500B
0x140015001  mov     edx, 76h ; 'v'
0x140015006  jmp     loc_1400152C6
0x14001500b  lea     rax, [rsp+340h+var_2D0]
0x140015010  mov     [rsp+340h+lpszShortPath], rax
0x140015015  lea     rax, [rsp+340h+var_2D0]
0x14001501a  mov     [rsp+340h+var_2D8], rax
0x14001501f  xor     eax, eax
0x140015021  mov     [rsp+340h+var_2D0], ax
0x140015026  lea     r9, pwzValue
0x14001502d  test    rdi, rdi
0x140015030  cmovz   rdi, r9
0x140015034  mov     r8, [rsp+340h+lpFileName]
0x140015039  mov     rax, [rsp+340h+var_2F8]
0x14001503e  cmp     r8, rax
0x140015041  jz      short loc_140015052
0x140015043  mov     ecx, 5Ch ; '\'
0x140015048  cmp     cx, [rax-2]
0x14001504c  jnz     short loc_140015052
0x14001504e  mov     al, 1
0x140015050  jmp     short loc_140015054
0x140015052  xor     al, al
0x140015054  lea     rcx, SubBlock; "\\"
0x14001505b  test    al, al
0x14001505d  cmovz   r9, rcx
0x140015061  mov     qword ptr [rsp+340h+dwFlagsAndAttributes], rdi
0x140015066  lea     rax, [rbp+240h+var_2B0]
0x14001506a  mov     qword ptr [rsp+340h+dwCreationDisposition], rax; int
0x14001506f  lea     rdx, aLsLswerLsTmpLs; "%ls%lsWER.%ls.tmp%ls"
0x140015076  lea     rcx, [rsp+340h+lpszShortPath]
0x14001507b  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x140015080  mov     ebx, eax
0x140015082  test    eax, eax
0x140015084  jns     short loc_1400150C6
0x140015086  mov     rcx, [rbp+248h]; this
0x14001508d  mov     r9d, eax; char *
0x140015090  lea     r8, aOnecoreWindows_8; "onecore\\windows\\feedback\\core\\commo"...
0x140015097  mov     edx, 7Fh; void *
0x14001509c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400150a1  nop
0x1400150a2  lea     rax, [rsp+340h+var_2D0]
0x1400150a7  mov     rcx, [rsp+340h+lpszShortPath]; void *
0x1400150ac  cmp     rcx, rax
0x1400150af  jz      loc_1400152DD
0x1400150b5  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400150bc  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400150c1  jmp     loc_1400152DD
0x1400150c6  bts     esi, 7
0x1400150ca  mov     [rsp+340h+hTemplateFile], 0; hTemplateFile
0x1400150d3  mov     [rsp+340h+dwFlagsAndAttributes], esi; dwFlagsAndAttributes
0x1400150d7  mov     [rsp+340h+dwCreationDisposition], 1; int
0x1400150df  mov     r9, r13; lpSecurityAttributes
0x1400150e2  mov     r8d, [rbp+240h+dwShareMode]; dwShareMode
0x1400150e6  mov     edx, 0C0000000h; dwDesiredAccess
0x1400150eb  mov     rcx, [rsp+340h+lpszShortPath]; lpFileName
0x1400150f0  call    cs:__imp_CreateFileW
0x1400150f6  mov     rbx, rax
0x1400150f9  mov     rsi, rax
0x1400150fc  mov     qword ptr [rbp+240h+dwShareMode], rax
0x140015100  lea     rcx, [rax+1]
0x140015104  cmp     rcx, 1
0x140015108  ja      short loc_140015129
0x14001510a  mov     rcx, [rbp+248h]; this
0x140015111  lea     r8, aOnecoreWindows_8; "onecore\\windows\\feedback\\core\\commo"...
0x140015118  mov     edx, 8Ah; void *
0x14001511d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140015122  mov     ebx, eax
0x140015124  jmp     loc_1400150A2
0x140015129  mov     rdx, rbx; void *
0x14001512c  mov     rcx, [rsp+340h+lpszShortPath]; wchar_t *
0x140015131  call    ?UtilVerifyFilePath@@YAJPEB_WPEAX@Z; UtilVerifyFilePath(wchar_t const *,void *)
0x140015136  mov     edi, eax
0x140015138  test    eax, eax
0x14001513a  jns     short loc_1400151A0
0x14001513c  mov     edx, 8Eh; void *
0x140015141  mov     r9d, edi; char *
0x140015144  lea     r8, aOnecoreWindows_8; "onecore\\windows\\feedback\\core\\commo"...
0x14001514b  mov     rcx, [rbp+248h]; this
0x140015152  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140015157  nop
0x140015158  mov     rcx, rbx; hObject
0x14001515b  call    cs:__imp_CloseHandle
0x140015161  nop
0x140015162  lea     rax, [rsp+340h+var_2D0]
0x140015167  mov     rcx, [rsp+340h+lpszShortPath]; void *
0x14001516c  cmp     rcx, rax
0x14001516f  jz      short loc_14001517E
0x140015171  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140015178  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14001517d  nop
0x14001517e  lea     rax, [rsp+340h+var_2F0]
0x140015183  mov     rcx, [rsp+340h+lpFileName]; void *
0x140015188  cmp     rcx, rax
0x14001518b  jz      short loc_140015199
0x14001518d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140015194  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140015199  mov     eax, edi
0x14001519b  jmp     loc_1400152FA
0x1400151a0  mov     edi, 104h
0x1400151a5  mov     r8d, edi; cchBuffer
0x1400151a8  mov     rdx, r12; lpszLongPath
0x1400151ab  mov     rcx, [rsp+340h+lpszShortPath]; lpszShortPath
0x1400151b0  call    cs:__imp_GetLongPathNameW
0x1400151b6  dec     eax
0x1400151b8  cmp     eax, 102h
0x1400151bd  jbe     short loc_140015225
0x1400151bf  call    cs:__imp_GetLastError
0x1400151c5  test    eax, eax
0x1400151c7  jle     short loc_1400151D1
0x1400151c9  movzx   eax, ax
0x1400151cc  or      eax, 80070000h
0x1400151d1  mov     ecx, 80004005h
0x1400151d6  test    eax, eax
0x1400151d8  cmovns  eax, ecx
0x1400151db  mov     rcx, cs:WPP_GLOBAL_Control
0x1400151e2  cmp     rcx, r14
0x1400151e5  jz      short loc_140015205
0x1400151e7  test    byte ptr [rcx+1Ch], 2
0x1400151eb  jz      short loc_140015205
0x1400151ed  mov     edx, 0Ch
0x1400151f2  mov     r9d, eax
0x1400151f5  lea     r8, WPP_69e296c8cfbe35481aeff25676a4a37b_Traceguids
0x1400151fc  mov     rcx, [rcx+10h]
0x140015200  call    WPP_SF_d
0x140015205  mov     r8, [rsp+340h+lpszShortPath]; wchar_t *
0x14001520a  mov     rdx, rdi; unsigned __int64
0x14001520d  mov     rcx, r12; wchar_t *
0x140015210  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x140015215  mov     edi, eax
0x140015217  test    eax, eax
0x140015219  jns     short loc_140015225
0x14001521b  mov     edx, 9Ah
0x140015220  jmp     loc_140015141
0x140015225  test    r15, r15
0x140015228  jz      short loc_140015242
0x14001522a  xor     esi, esi
0x14001522c  mov     rcx, [r15]; hObject
0x14001522f  mov     [r15], rbx
0x140015232  lea     rax, [rcx+1]
0x140015236  cmp     rax, 1
0x14001523a  jbe     short loc_140015242
0x14001523c  call    cs:__imp_CloseHandle
0x140015242  mov     rcx, cs:WPP_GLOBAL_Control
0x140015249  cmp     rcx, r14
0x14001524c  jz      short loc_14001526D
0x14001524e  test    byte ptr [rcx+1Ch], 4
0x140015252  jz      short loc_14001526D
0x140015254  mov     edx, 0Dh
0x140015259  mov     r9, r12
0x14001525c  lea     r8, WPP_69e296c8cfbe35481aeff25676a4a37b_Traceguids
0x140015263  mov     rcx, [rcx+10h]
0x140015267  call    WPP_SF_S
0x14001526c  nop
0x14001526d  lea     rax, [rsi+1]
0x140015271  cmp     rax, 1
0x140015275  jbe     short loc_140015281
0x140015277  mov     rcx, rsi; hObject
0x14001527a  call    cs:__imp_CloseHandle
0x140015280  nop
0x140015281  lea     rax, [rsp+340h+var_2D0]
0x140015286  mov     rcx, [rsp+340h+lpszShortPath]; void *
0x14001528b  cmp     rcx, rax
0x14001528e  jz      short loc_14001529D
  ... truncated ...
```
