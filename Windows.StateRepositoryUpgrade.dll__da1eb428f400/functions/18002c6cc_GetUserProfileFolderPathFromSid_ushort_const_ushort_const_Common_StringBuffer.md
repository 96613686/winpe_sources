# GetUserProfileFolderPathFromSid(ushort const *,ushort const *,Common::StringBuffer &)

- ea: `0x18002c6cc`
- end: `0x18002c9d9`
- name: `?GetUserProfileFolderPathFromSid@@YAJPEBG0AEAVStringBuffer@Common@@@Z`
- size: `781`
- prototype: `__int64 __fastcall(PCWSTR pszPathIn, const unsigned __int16 *, struct Common::StringBuffer *)`
- caller_count: `1`
- callee_count: `10`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18002c3e8`

## callees

- `0x18000a3c0`
- `0x18000d9a4`
- `0x18000f62c`
- `0x180017670`
- `0x18002c1b0`
- `0x18002c304`
- `0x18002c3e8`
- `0x18002c6cc`
- `0x18002d190`
- `0x18002d2dc`

## import_xrefs

- `ntdll!RtlDetermineDosPathNameType_U` at `0x18002c809`
- `ntdll!RtlDetermineDosPathNameType_U` at `0x18002c809`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002c890`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002c890`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18002c73e`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18002c907`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18002c73e`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18002c907`

## string_xrefs

- `0x18002c753`: `onecore\base\appmodel\common\userprofile.cpp`
- `0x18002c78f`: `onecore\base\appmodel\common\userprofile.cpp`
- `0x18002c7e8`: `onecore\base\appmodel\common\userprofile.cpp`
- `0x18002c840`: `onecore\base\appmodel\common\userprofile.cpp`
- `0x18002c8c8`: `onecore\base\appmodel\common\userprofile.cpp`
- `0x18002c91c`: `onecore\base\appmodel\common\userprofile.cpp`
- `0x18002c9a1`: `onecore\base\appmodel\common\userprofile.cpp`

## pseudocode

```c
__int64 __fastcall GetUserProfileFolderPathFromSid(
        PCWSTR pszPathIn,
        const unsigned __int16 *a2,
        struct Common::StringBuffer *a3)
{
  __int64 v4; // rdx
  HRESULT v7; // eax
  unsigned int v8; // ebx
  __int64 v9; // rdx
  int v10; // eax
  int v11; // eax
  unsigned __int64 v12; // r8
  int StringValue; // eax
  __int64 v14; // rdx
  PCWSTR v15; // rbx
  int UserProfileFolderPath; // eax
  unsigned int v17; // edi
  int v18; // eax
  int v19; // eax
  HRESULT v20; // eax
  __int64 v21; // rdx
  int bIgnoreCase; // [rsp+20h] [rbp-59h]
  int bIgnoreCasea; // [rsp+20h] [rbp-59h]
  unsigned int bIgnoreCaseb; // [rsp+20h] [rbp-59h]
  HKEY phkResult; // [rsp+30h] [rbp-49h] BYREF
  PCWSTR Path[2]; // [rsp+38h] [rbp-41h] BYREF
  int v28; // [rsp+48h] [rbp-31h]
  PCWSTR pszPathIna[2]; // [rsp+50h] [rbp-29h] BYREF
  int v30; // [rsp+60h] [rbp-19h]
  PWSTR v31[2]; // [rsp+68h] [rbp-11h] BYREF
  int v32; // [rsp+78h] [rbp-1h]
  PWSTR pszPathOut[2]; // [rsp+80h] [rbp+7h] BYREF
  int v34; // [rsp+90h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]
  unsigned int v36; // [rsp+F8h] [rbp+7Fh] BYREF

  v34 = 0;
  *(_OWORD *)pszPathOut = 0;
  v4 = -1;
  do
    ++v4;
  while ( pszPathIn[v4] );
  v7 = Common::StringBuffer::SetLength((Common::StringBuffer *)pszPathOut, v4 + 70);
  v8 = v7;
  if ( v7 >= 0 )
  {
    if ( v34 )
      v10 = v34 - 1;
    else
      v10 = 0;
    v7 = PathCchCombine(
           pszPathOut[1],
           (unsigned int)(v10 + 1),
           pszPathIn,
           L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\User Shell Folders");
    v8 = v7;
    if ( v7 < 0 )
    {
      v9 = 42;
      goto LABEL_10;
    }
    phkResult = 0;
    v11 = Common::RegistryKey::Open(&phkResult, HKEY_USERS, pszPathOut[1], 0x20019u);
    v8 = v11;
    if ( v11 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2D,
        (unsigned int)"onecore\\base\\appmodel\\common\\userprofile.cpp",
        (const char *)(unsigned int)v11,
        bIgnoreCase);
LABEL_13:
      Common::AutoHandleCloseHKEY<HKEY__ *>(phkResult);
      goto LABEL_36;
    }
    v36 = 0;
    v28 = 0;
    *(_OWORD *)Path = 0;
    StringValue = Common::RegistryKey::GetStringValue(
                    (Common::RegistryKey *)&phkResult,
                    a2,
                    v12,
                    (struct Common::StringBuffer *)Path,
                    &v36);
    v8 = StringValue;
    if ( StringValue < 0 )
    {
      v14 = 49;
LABEL_16:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v14,
        (unsigned int)"onecore\\base\\appmodel\\common\\userprofile.cpp",
        (const char *)(unsigned int)StringValue,
        bIgnoreCasea);
LABEL_17:
      Common::StringBuffer::~StringBuffer((Common::StringBuffer *)Path);
      goto LABEL_13;
    }
    v15 = Path[1];
    if ( (unsigned int)(RtlDetermineDosPathNameType_U(Path[1]) - 1) <= 1 )
    {
      StringValue = Common::StringBuffer::SetValueFromString(a3, v15);
      v8 = StringValue;
      if ( StringValue < 0 )
      {
        v14 = 55;
        goto LABEL_16;
      }
    }
    else
    {
      v30 = 0;
      *(_OWORD *)pszPathIna = 0;
      UserProfileFolderPath = Common::UserProfile::GetUserProfileFolderPath(5, pszPathIn, pszPathIna);
      v17 = UserProfileFolderPath;
      if ( UserProfileFolderPath < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x40,
          (unsigned int)"onecore\\base\\appmodel\\common\\userprofile.cpp",
          (const char *)(unsigned int)UserProfileFolderPath,
          bIgnoreCasea);
LABEL_21:
        Common::StringBuffer::~StringBuffer((Common::StringBuffer *)pszPathIna);
        Common::StringBuffer::~StringBuffer((Common::StringBuffer *)Path);
        Common::AutoHandleCloseHKEY<HKEY__ *>(phkResult);
        v8 = v17;
        goto LABEL_36;
      }
      if ( CompareStringOrdinal(v15, 13, L"%USERPROFILE%", 13, 1) != 2 )
      {
        v8 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x56,
               (unsigned int)"onecore\\base\\appmodel\\common\\userprofile.cpp",
               (const char *)0xA1,
               bIgnoreCaseb);
        goto LABEL_31;
      }
      v32 = 0;
      *(_OWORD *)v31 = 0;
      v18 = Common::StringBuffer::SetLength((Common::StringBuffer *)v31, LODWORD(Path[0]) - 12 + LODWORD(pszPathIna[0]));
      v17 = v18;
      if ( v18 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x4B,
          (unsigned int)"onecore\\base\\appmodel\\common\\userprofile.cpp",
          (const char *)(unsigned int)v18,
          bIgnoreCaseb);
        Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v31);
        goto LABEL_21;
      }
      if ( v32 )
        v19 = v32 - 1;
      else
        v19 = 0;
      v20 = PathCchCombine(v31[1], (unsigned int)(v19 + 1), pszPathIna[1], v15 + 14);
      v8 = v20;
      if ( v20 < 0 )
      {
        v21 = 80;
LABEL_30:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v21,
          (unsigned int)"onecore\\base\\appmodel\\common\\userprofile.cpp",
          (const char *)(unsigned int)v20,
          bIgnoreCaseb);
        Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v31);
LABEL_31:
        Common::StringBuffer::~StringBuffer((Common::StringBuffer *)pszPathIna);
        goto LABEL_17;
      }
      v20 = Common::StringBuffer::SetValueFromString(a3, v31[1]);
      v8 = v20;
      if ( v20 < 0 )
      {
        v21 = 82;
        goto LABEL_30;
      }
      Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v31);
      Common::StringBuffer::~StringBuffer((Common::StringBuffer *)pszPathIna);
    }
    Common::StringBuffer::~StringBuffer((Common::StringBuffer *)Path);
    Common::AutoHandleCloseHKEY<HKEY__ *>(phkResult);
    v8 = 0;
    goto LABEL_36;
  }
  v9 = 36;
LABEL_10:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v9,
    (unsigned int)"onecore\\base\\appmodel\\common\\userprofile.cpp",
    (const char *)(unsigned int)v7,
    bIgnoreCase);
LABEL_36:
  Common::StringBuffer::~StringBuffer((Common::StringBuffer *)pszPathOut);
  return v8;
}

```

## disassembly

```asm
0x18002c6cc  push    rbp
0x18002c6ce  push    rbx
0x18002c6cf  push    rsi
0x18002c6d0  push    rdi
0x18002c6d1  push    r14
0x18002c6d3  push    r15
0x18002c6d5  lea     rbp, [rsp-2Fh]
0x18002c6da  sub     rsp, 0A8h
0x18002c6e1  xor     r15d, r15d
0x18002c6e4  xorps   xmm0, xmm0
0x18002c6e7  mov     r14, rdx
0x18002c6ea  mov     [rbp+57h+var_40], r15d
0x18002c6ee  movups  xmmword ptr [rbp+57h+pszPathOut], xmm0
0x18002c6f2  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18002c6f6  mov     rsi, r8
0x18002c6f9  mov     rdi, rcx
0x18002c6fc  inc     rdx
0x18002c6ff  cmp     [rcx+rdx*2], r15w
0x18002c704  jnz     short loc_18002C6FC
0x18002c706  add     edx, 46h ; 'F'; unsigned int
0x18002c709  lea     rcx, [rbp+57h+pszPathOut]; this
0x18002c70d  call    ?SetLength@StringBuffer@Common@@QEAAJK@Z; Common::StringBuffer::SetLength(ulong)
0x18002c712  mov     ebx, eax
0x18002c714  test    eax, eax
0x18002c716  jns     short loc_18002C71F
0x18002c718  mov     edx, 24h ; '$'
0x18002c71d  jmp     short loc_18002C74F
0x18002c71f  mov     eax, [rbp+57h+var_40]
0x18002c722  test    eax, eax
0x18002c724  jnz     short loc_18002C72B
0x18002c726  mov     eax, r15d
0x18002c729  jmp     short loc_18002C72D
0x18002c72b  dec     eax
0x18002c72d  mov     rcx, [rbp+57h+pszPathOut+8]; pszPathOut
0x18002c731  lea     edx, [rax+1]; cchPathOut
0x18002c734  lea     r9, pszMore; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18002c73b  mov     r8, rdi; pszPathIn
0x18002c73e  call    cs:__imp_PathCchCombine
0x18002c744  mov     ebx, eax
0x18002c746  test    eax, eax
0x18002c748  jns     short loc_18002C767
0x18002c74a  mov     edx, 2Ah ; '*'; void *
0x18002c74f  mov     rcx, [rbp+5Fh]; this
0x18002c753  lea     r8, aOnecoreBaseApp_14; "onecore\\base\\appmodel\\common\\userpr"...
0x18002c75a  mov     r9d, eax; char *
0x18002c75d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c762  jmp     loc_18002C982
0x18002c767  mov     r8, [rbp+57h+pszPathOut+8]; lpSubKey
0x18002c76b  lea     rcx, [rbp+57h+phkResult]; phkResult
0x18002c76f  mov     r9d, 20019h; samDesired
0x18002c775  mov     [rbp+57h+phkResult], r15
0x18002c779  mov     rdx, 0FFFFFFFF80000003h; hKey
0x18002c780  call    ?Open@RegistryKey@Common@@QEAAJQEAUHKEY__@@PEBGK@Z; Common::RegistryKey::Open(HKEY__ * const,ushort const *,ulong)
0x18002c785  mov     ebx, eax
0x18002c787  test    eax, eax
0x18002c789  jns     short loc_18002C7B1
0x18002c78b  mov     rcx, [rbp+5Fh]; this
0x18002c78f  lea     r8, aOnecoreBaseApp_14; "onecore\\base\\appmodel\\common\\userpr"...
0x18002c796  mov     r9d, eax; char *
0x18002c799  mov     edx, 2Dh ; '-'; void *
0x18002c79e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c7a3  mov     rcx, [rbp+57h+phkResult]
0x18002c7a7  call    ??$AutoHandleCloseHKEY@PEAUHKEY__@@@Common@@YAXPEAUHKEY__@@@Z; Common::AutoHandleCloseHKEY<HKEY__ *>(HKEY__ *)
0x18002c7ac  jmp     loc_18002C982
0x18002c7b1  xorps   xmm0, xmm0
0x18002c7b4  mov     [rbp+57h+arg_18], r15d
0x18002c7b8  lea     rax, [rbp+57h+arg_18]
0x18002c7bc  mov     [rbp+57h+var_88], r15d
0x18002c7c0  lea     r9, [rbp+57h+Path]; struct Common::StringBuffer *
0x18002c7c4  mov     qword ptr [rsp+0D0h+bIgnoreCase], rax; int
0x18002c7c9  mov     rdx, r14; unsigned __int16 *
0x18002c7cc  lea     rcx, [rbp+57h+phkResult]; this
0x18002c7d0  movups  xmmword ptr [rbp+57h+Path], xmm0
0x18002c7d4  call    ?GetStringValue@RegistryKey@Common@@QEAAJPEBG_KAEAVStringBuffer@2@PEAK@Z; Common::RegistryKey::GetStringValue(ushort const *,unsigned __int64,Common::StringBuffer &,ulong *)
0x18002c7d9  mov     ebx, eax
0x18002c7db  test    eax, eax
0x18002c7dd  jns     short loc_18002C802
0x18002c7df  mov     edx, 31h ; '1'; void *
0x18002c7e4  mov     rcx, [rbp+5Fh]; this
0x18002c7e8  lea     r8, aOnecoreBaseApp_14; "onecore\\base\\appmodel\\common\\userpr"...
0x18002c7ef  mov     r9d, eax; char *
0x18002c7f2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c7f7  lea     rcx, [rbp+57h+Path]; this
0x18002c7fb  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x18002c800  jmp     short loc_18002C7A3
0x18002c802  mov     rbx, [rbp+57h+Path+8]
0x18002c806  mov     rcx, rbx; Path
0x18002c809  call    cs:__imp_RtlDetermineDosPathNameType_U
0x18002c80f  dec     eax
0x18002c811  cmp     eax, 1
0x18002c814  jbe     loc_18002C9BE
0x18002c81a  xorps   xmm0, xmm0
0x18002c81d  mov     [rbp+57h+var_70], r15d
0x18002c821  lea     r8, [rbp+57h+pszPathIn]
0x18002c825  mov     rdx, rdi
0x18002c828  mov     ecx, 5
0x18002c82d  movups  xmmword ptr [rbp+57h+pszPathIn], xmm0
0x18002c831  call    ?GetUserProfileFolderPath@UserProfile@Common@@YAJW4PROFILE_FOLDER_ID@12@PEBGAEAVStringBuffer@2@@Z; Common::UserProfile::GetUserProfileFolderPath(Common::UserProfile::PROFILE_FOLDER_ID,ushort const *,Common::StringBuffer &)
0x18002c836  mov     edi, eax
0x18002c838  test    eax, eax
0x18002c83a  jns     short loc_18002C876
0x18002c83c  mov     rcx, [rbp+5Fh]; this
0x18002c840  lea     r8, aOnecoreBaseApp_14; "onecore\\base\\appmodel\\common\\userpr"...
0x18002c847  mov     r9d, eax; char *
0x18002c84a  mov     edx, 40h ; '@'; void *
0x18002c84f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c854  lea     rcx, [rbp+57h+pszPathIn]; this
0x18002c858  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x18002c85d  lea     rcx, [rbp+57h+Path]; this
0x18002c861  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x18002c866  mov     rcx, [rbp+57h+phkResult]
0x18002c86a  call    ??$AutoHandleCloseHKEY@PEAUHKEY__@@@Common@@YAXPEAUHKEY__@@@Z; Common::AutoHandleCloseHKEY<HKEY__ *>(HKEY__ *)
0x18002c86f  mov     ebx, edi
0x18002c871  jmp     loc_18002C982
0x18002c876  mov     edx, 0Dh; cchCount1
0x18002c87b  mov     [rsp+0D0h+bIgnoreCase], 1; unsigned int
0x18002c883  mov     r9d, edx; cchCount2
0x18002c886  lea     r8, aUserprofile; "%USERPROFILE%"
0x18002c88d  mov     rcx, rbx; lpString1
0x18002c890  call    cs:__imp_CompareStringOrdinal
0x18002c896  cmp     eax, 2
0x18002c899  jnz     loc_18002C99D
0x18002c89f  mov     eax, dword ptr [rbp+57h+Path]
0x18002c8a2  lea     rcx, [rbp+57h+var_68]; this
0x18002c8a6  mov     edx, dword ptr [rbp+57h+pszPathIn]
0x18002c8a9  add     eax, 0FFFFFFF4h
0x18002c8ac  xorps   xmm0, xmm0
0x18002c8af  mov     [rbp+57h+var_58], r15d
0x18002c8b3  add     edx, eax; unsigned int
0x18002c8b5  movups  xmmword ptr [rbp+57h+var_68], xmm0
0x18002c8b9  call    ?SetLength@StringBuffer@Common@@QEAAJK@Z; Common::StringBuffer::SetLength(ulong)
0x18002c8be  mov     edi, eax
0x18002c8c0  test    eax, eax
0x18002c8c2  jns     short loc_18002C8EA
0x18002c8c4  mov     rcx, [rbp+5Fh]; this
0x18002c8c8  lea     r8, aOnecoreBaseApp_14; "onecore\\base\\appmodel\\common\\userpr"...
0x18002c8cf  mov     r9d, eax; char *
0x18002c8d2  mov     edx, 4Bh ; 'K'; void *
0x18002c8d7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c8dc  lea     rcx, [rbp+57h+var_68]; this
0x18002c8e0  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x18002c8e5  jmp     loc_18002C854
0x18002c8ea  mov     eax, [rbp+57h+var_58]
0x18002c8ed  test    eax, eax
0x18002c8ef  jnz     short loc_18002C8F6
0x18002c8f1  mov     eax, r15d
0x18002c8f4  jmp     short loc_18002C8F8
0x18002c8f6  dec     eax
0x18002c8f8  mov     r8, [rbp+57h+pszPathIn+8]; pszPathIn
0x18002c8fc  lea     r9, [rbx+1Ch]; pszMore
0x18002c900  mov     rcx, [rbp+57h+var_68+8]; pszPathOut
0x18002c904  lea     edx, [rax+1]; cchPathOut
0x18002c907  call    cs:__imp_PathCchCombine
0x18002c90d  mov     ebx, eax
0x18002c90f  test    eax, eax
0x18002c911  jns     short loc_18002C942
0x18002c913  mov     edx, 50h ; 'P'; void *
0x18002c918  mov     rcx, [rbp+5Fh]; this
0x18002c91c  lea     r8, aOnecoreBaseApp_14; "onecore\\base\\appmodel\\common\\userpr"...
0x18002c923  mov     r9d, eax; char *
0x18002c926  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c92b  lea     rcx, [rbp+57h+var_68]; this
0x18002c92f  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x18002c934  lea     rcx, [rbp+57h+pszPathIn]; this
0x18002c938  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x18002c93d  jmp     loc_18002C7F7
0x18002c942  mov     rdx, [rbp+57h+var_68+8]; unsigned __int16 *
0x18002c946  mov     rcx, rsi; this
0x18002c949  call    ?SetValueFromString@StringBuffer@Common@@QEAAJPEBG@Z; Common::StringBuffer::SetValueFromString(ushort const *)
0x18002c94e  mov     ebx, eax
0x18002c950  test    eax, eax
0x18002c952  jns     short loc_18002C95B
0x18002c954  mov     edx, 52h ; 'R'
0x18002c959  jmp     short loc_18002C918
0x18002c95b  lea     rcx, [rbp+57h+var_68]; this
0x18002c95f  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x18002c964  lea     rcx, [rbp+57h+pszPathIn]; this
0x18002c968  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x18002c96d  lea     rcx, [rbp+57h+Path]; this
0x18002c971  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x18002c976  mov     rcx, [rbp+57h+phkResult]
0x18002c97a  call    ??$AutoHandleCloseHKEY@PEAUHKEY__@@@Common@@YAXPEAUHKEY__@@@Z; Common::AutoHandleCloseHKEY<HKEY__ *>(HKEY__ *)
0x18002c97f  mov     ebx, r15d
0x18002c982  lea     rcx, [rbp+57h+pszPathOut]; this
0x18002c986  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x18002c98b  mov     eax, ebx
0x18002c98d  add     rsp, 0A8h
0x18002c994  pop     r15
0x18002c996  pop     r14
0x18002c998  pop     rdi
0x18002c999  pop     rsi
0x18002c99a  pop     rbx
0x18002c99b  pop     rbp
0x18002c99c  retn
0x18002c99d  mov     rcx, [rbp+5Fh]; this
0x18002c9a1  lea     r8, aOnecoreBaseApp_14; "onecore\\base\\appmodel\\common\\userpr"...
0x18002c9a8  mov     r9d, 0A1h; char *
0x18002c9ae  lea     edx, [r9-4Bh]; void *
0x18002c9b2  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002c9b7  mov     ebx, eax
0x18002c9b9  jmp     loc_18002C934
0x18002c9be  mov     rdx, rbx; unsigned __int16 *
0x18002c9c1  mov     rcx, rsi; this
0x18002c9c4  call    ?SetValueFromString@StringBuffer@Common@@QEAAJPEBG@Z; Common::StringBuffer::SetValueFromString(ushort const *)
0x18002c9c9  mov     ebx, eax
0x18002c9cb  test    eax, eax
0x18002c9cd  jns     short loc_18002C96D
0x18002c9cf  mov     edx, 37h ; '7'
0x18002c9d4  jmp     loc_18002C7E4
```
