# GetUserProfileFolderPathFromSid(ushort const *,ushort const *,Common::StringBuffer &)

- ea: `0x1802797c0`
- end: `0x180279b89`
- name: `?GetUserProfileFolderPathFromSid@@YAJPEBG0AEAVStringBuffer@Common@@@Z`
- size: `969`
- prototype: `__int64 __fastcall(PCWSTR pszPathIn, const unsigned __int16 *, struct Common::StringBuffer *this)`
- caller_count: `1`
- callee_count: `10`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180279458`

## callees

- `0x18001a9e0`
- `0x1800613a8`
- `0x180061560`
- `0x180061ae8`
- `0x1800b4dbc`
- `0x1800bc824`
- `0x1800c0400`
- `0x1802792a8`
- `0x180279458`
- `0x1802797c0`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180279996`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180279996`
- `ntdll!RtlDetermineDosPathNameType_U` at `0x18027990d`
- `ntdll!RtlDetermineDosPathNameType_U` at `0x18027990d`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x180279832`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x180279a2a`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x180279832`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x180279a2a`

## string_xrefs

- `0x180279843`: `onecore\base\appmodel\common\userprofile.cpp`
- `0x180279886`: `onecore\base\appmodel\common\userprofile.cpp`
- `0x1802798dc`: `onecore\base\appmodel\common\userprofile.cpp`
- `0x180279947`: `onecore\base\appmodel\common\userprofile.cpp`
- `0x1802799d1`: `onecore\base\appmodel\common\userprofile.cpp`
- `0x180279a3d`: `onecore\base\appmodel\common\userprofile.cpp`
- `0x180279a8f`: `onecore\base\appmodel\common\userprofile.cpp`
- `0x180279b16`: `onecore\base\appmodel\common\userprofile.cpp`
- `0x180279b5f`: `onecore\base\appmodel\common\userprofile.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall GetUserProfileFolderPathFromSid(
        PCWSTR pszPathIn,
        const unsigned __int16 *a2,
        struct Common::StringBuffer *this)
{
  __int64 v6; // rdx
  HRESULT v7; // eax
  unsigned int v8; // ebx
  __int64 v9; // rdx
  int v10; // eax
  int v11; // eax
  unsigned __int64 v12; // r8
  int StringValue; // eax
  PCWSTR v14; // rbx
  int UserProfileFolderPath; // eax
  int v16; // edi
  int v17; // eax
  int v18; // eax
  HRESULT v19; // eax
  int v20; // eax
  int v22; // eax
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

  *(_OWORD *)pszPathOut = 0;
  v34 = 0;
  v6 = -1;
  do
    ++v6;
  while ( pszPathIn[v6] );
  v7 = Common::StringBuffer::SetLength((Common::StringBuffer *)pszPathOut, v6 + 70);
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
      Common::AutoHandleCloseHKEY<HKEY__ *>(phkResult);
      goto LABEL_31;
    }
    v36 = 0;
    *(_OWORD *)Path = 0;
    v28 = 0;
    StringValue = Common::RegistryKey::GetStringValue(
                    (Common::RegistryKey *)&phkResult,
                    a2,
                    v12,
                    (struct Common::StringBuffer *)Path,
                    &v36);
    v8 = StringValue;
    if ( StringValue < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x31,
        (unsigned int)"onecore\\base\\appmodel\\common\\userprofile.cpp",
        (const char *)(unsigned int)StringValue,
        bIgnoreCasea);
      Common::StringBuffer::~StringBuffer((Common::StringBuffer *)Path);
      Common::AutoHandleCloseHKEY<HKEY__ *>(phkResult);
      goto LABEL_31;
    }
    v14 = Path[1];
    if ( (unsigned int)(RtlDetermineDosPathNameType_U(Path[1]) - 1) <= 1 )
    {
      v22 = Common::StringBuffer::SetValueFromString(this, v14);
      v8 = v22;
      if ( v22 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x37,
          (unsigned int)"onecore\\base\\appmodel\\common\\userprofile.cpp",
          (const char *)(unsigned int)v22,
          bIgnoreCasea);
        Common::StringBuffer::~StringBuffer((Common::StringBuffer *)Path);
        Common::AutoHandleCloseHKEY<HKEY__ *>(phkResult);
        goto LABEL_31;
      }
    }
    else
    {
      *(_OWORD *)pszPathIna = 0;
      v30 = 0;
      UserProfileFolderPath = Common::UserProfile::GetUserProfileFolderPath(5, pszPathIn, pszPathIna);
      v16 = UserProfileFolderPath;
      if ( UserProfileFolderPath < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x40,
          (unsigned int)"onecore\\base\\appmodel\\common\\userprofile.cpp",
          (const char *)(unsigned int)UserProfileFolderPath,
          bIgnoreCasea);
        Common::StringBuffer::~StringBuffer((Common::StringBuffer *)pszPathIna);
        Common::StringBuffer::~StringBuffer((Common::StringBuffer *)Path);
        Common::AutoHandleCloseHKEY<HKEY__ *>(phkResult);
LABEL_18:
        v8 = v16;
        goto LABEL_31;
      }
      if ( CompareStringOrdinal(v14, 13, L"%USERPROFILE%", 13, 1) != 2 )
      {
        v8 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x56,
               (unsigned int)"onecore\\base\\appmodel\\common\\userprofile.cpp",
               (const char *)0xA1,
               bIgnoreCaseb);
        Common::StringBuffer::~StringBuffer((Common::StringBuffer *)pszPathIna);
        Common::StringBuffer::~StringBuffer((Common::StringBuffer *)Path);
        Common::AutoHandleCloseHKEY<HKEY__ *>(phkResult);
        goto LABEL_31;
      }
      *(_OWORD *)v31 = 0;
      v32 = 0;
      v17 = Common::StringBuffer::SetLength((Common::StringBuffer *)v31, LODWORD(Path[0]) - 12 + LODWORD(pszPathIna[0]));
      v16 = v17;
      if ( v17 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x4B,
          (unsigned int)"onecore\\base\\appmodel\\common\\userprofile.cpp",
          (const char *)(unsigned int)v17,
          bIgnoreCaseb);
        Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v31);
        Common::StringBuffer::~StringBuffer((Common::StringBuffer *)pszPathIna);
        Common::StringBuffer::~StringBuffer((Common::StringBuffer *)Path);
        Common::AutoHandleCloseHKEY<HKEY__ *>(phkResult);
        goto LABEL_18;
      }
      if ( v32 )
        v18 = v32 - 1;
      else
        v18 = 0;
      v19 = PathCchCombine(v31[1], (unsigned int)(v18 + 1), pszPathIna[1], v14 + 14);
      v8 = v19;
      if ( v19 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x50,
          (unsigned int)"onecore\\base\\appmodel\\common\\userprofile.cpp",
          (const char *)(unsigned int)v19,
          bIgnoreCaseb);
        Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v31);
        Common::StringBuffer::~StringBuffer((Common::StringBuffer *)pszPathIna);
        Common::StringBuffer::~StringBuffer((Common::StringBuffer *)Path);
        Common::AutoHandleCloseHKEY<HKEY__ *>(phkResult);
        goto LABEL_31;
      }
      v20 = Common::StringBuffer::SetValueFromString(this, v31[1]);
      v8 = v20;
      if ( v20 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x52,
          (unsigned int)"onecore\\base\\appmodel\\common\\userprofile.cpp",
          (const char *)(unsigned int)v20,
          bIgnoreCaseb);
        Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v31);
        Common::StringBuffer::~StringBuffer((Common::StringBuffer *)pszPathIna);
        Common::StringBuffer::~StringBuffer((Common::StringBuffer *)Path);
        Common::AutoHandleCloseHKEY<HKEY__ *>(phkResult);
        goto LABEL_31;
      }
      Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v31);
      Common::StringBuffer::~StringBuffer((Common::StringBuffer *)pszPathIna);
    }
    Common::StringBuffer::~StringBuffer((Common::StringBuffer *)Path);
    Common::AutoHandleCloseHKEY<HKEY__ *>(phkResult);
    v8 = 0;
    goto LABEL_31;
  }
  v9 = 36;
LABEL_10:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v9,
    (unsigned int)"onecore\\base\\appmodel\\common\\userprofile.cpp",
    (const char *)(unsigned int)v7,
    bIgnoreCase);
LABEL_31:
  Common::StringBuffer::~StringBuffer((Common::StringBuffer *)pszPathOut);
  return v8;
}

```

## disassembly

```asm
0x1802797c0  push    rbp
0x1802797c2  push    rbx
0x1802797c3  push    rsi
0x1802797c4  push    rdi
0x1802797c5  push    r14
0x1802797c7  push    r15
0x1802797c9  lea     rbp, [rsp-2Fh]
0x1802797ce  sub     rsp, 0A8h
0x1802797d5  mov     rsi, r8
0x1802797d8  mov     r14, rdx
0x1802797db  mov     rdi, rcx
0x1802797de  xorps   xmm0, xmm0
0x1802797e1  movups  xmmword ptr [rbp+57h+pszPathOut], xmm0
0x1802797e5  xor     r15d, r15d
0x1802797e8  mov     [rbp+57h+var_40], r15d
0x1802797ec  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1802797f0  inc     rdx
0x1802797f3  cmp     [rcx+rdx*2], r15w
0x1802797f8  jnz     short loc_1802797F0
0x1802797fa  add     edx, 46h ; 'F'; unsigned int
0x1802797fd  lea     rcx, [rbp+57h+pszPathOut]; this
0x180279801  call    ?SetLength@StringBuffer@Common@@QEAAJK@Z; Common::StringBuffer::SetLength(ulong)
0x180279806  mov     ebx, eax
0x180279808  test    eax, eax
0x18027980a  jns     short loc_180279813
0x18027980c  mov     edx, 24h ; '$'
0x180279811  jmp     short loc_180279843
0x180279813  mov     eax, [rbp+57h+var_40]
0x180279816  test    eax, eax
0x180279818  jnz     short loc_18027981F
0x18027981a  mov     eax, r15d
0x18027981d  jmp     short loc_180279821
0x18027981f  dec     eax
0x180279821  lea     edx, [rax+1]; cchPathOut
0x180279824  lea     r9, pszMore; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18027982b  mov     r8, rdi; pszPathIn
0x18027982e  mov     rcx, [rbp+57h+pszPathOut+8]; pszPathOut
0x180279832  call    cs:__imp_PathCchCombine
0x180279838  mov     ebx, eax
0x18027983a  test    eax, eax
0x18027983c  jns     short loc_18027985B
0x18027983e  mov     edx, 2Ah ; '*'; void *
0x180279843  lea     r8, aOnecoreBaseApp_99; "onecore\\base\\appmodel\\common\\userpr"...
0x18027984a  mov     r9d, eax; char *
0x18027984d  mov     rcx, [rbp+5Fh]; this
0x180279851  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180279856  jmp     loc_180279AF1
0x18027985b  mov     [rbp+57h+phkResult], r15
0x18027985f  mov     r9d, 20019h; samDesired
0x180279865  mov     r8, [rbp+57h+pszPathOut+8]; lpSubKey
0x180279869  mov     rdx, 0FFFFFFFF80000003h; hKey
0x180279870  lea     rcx, [rbp+57h+phkResult]; phkResult
0x180279874  call    ?Open@RegistryKey@Common@@QEAAJQEAUHKEY__@@PEBGK@Z; Common::RegistryKey::Open(HKEY__ * const,ushort const *,ulong)
0x180279879  mov     ebx, eax
0x18027987b  test    eax, eax
0x18027987d  jns     short loc_1802798A7
0x18027987f  mov     rcx, [rbp+5Fh]; this
0x180279883  mov     r9d, eax; char *
0x180279886  lea     r8, aOnecoreBaseApp_99; "onecore\\base\\appmodel\\common\\userpr"...
0x18027988d  mov     edx, 2Dh ; '-'; void *
0x180279892  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180279897  nop
0x180279898  mov     rcx, [rbp+57h+phkResult]
0x18027989c  call    ??$AutoHandleCloseHKEY@PEAUHKEY__@@@Common@@YAXPEAUHKEY__@@@Z; Common::AutoHandleCloseHKEY<HKEY__ *>(HKEY__ *)
0x1802798a1  nop
0x1802798a2  jmp     loc_180279AF1
0x1802798a7  mov     [rbp+57h+arg_18], r15d
0x1802798ab  xorps   xmm0, xmm0
0x1802798ae  movups  xmmword ptr [rbp+57h+Path], xmm0
0x1802798b2  mov     [rbp+57h+var_88], r15d
0x1802798b6  lea     rax, [rbp+57h+arg_18]
0x1802798ba  mov     qword ptr [rsp+0D0h+bIgnoreCase], rax; int
0x1802798bf  lea     r9, [rbp+57h+Path]; struct Common::StringBuffer *
0x1802798c3  mov     rdx, r14; unsigned __int16 *
0x1802798c6  lea     rcx, [rbp+57h+phkResult]; this
0x1802798ca  call    ?GetStringValue@RegistryKey@Common@@QEAAJPEBG_KAEAVStringBuffer@2@PEAK@Z; Common::RegistryKey::GetStringValue(ushort const *,unsigned __int64,Common::StringBuffer &,ulong *)
0x1802798cf  mov     ebx, eax
0x1802798d1  test    eax, eax
0x1802798d3  jns     short loc_180279906
0x1802798d5  mov     rcx, [rbp+5Fh]; this
0x1802798d9  mov     r9d, eax; char *
0x1802798dc  lea     r8, aOnecoreBaseApp_99; "onecore\\base\\appmodel\\common\\userpr"...
0x1802798e3  mov     edx, 31h ; '1'; void *
0x1802798e8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802798ed  lea     rcx, [rbp+57h+Path]; this
0x1802798f1  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x1802798f6  nop
0x1802798f7  mov     rcx, [rbp+57h+phkResult]
0x1802798fb  call    ??$AutoHandleCloseHKEY@PEAUHKEY__@@@Common@@YAXPEAUHKEY__@@@Z; Common::AutoHandleCloseHKEY<HKEY__ *>(HKEY__ *)
0x180279900  nop
0x180279901  jmp     loc_180279AF1
0x180279906  mov     rbx, [rbp+57h+Path+8]
0x18027990a  mov     rcx, rbx; Path
0x18027990d  call    cs:__imp_RtlDetermineDosPathNameType_U
0x180279913  dec     eax
0x180279915  cmp     eax, 1
0x180279918  jbe     loc_180279B47
0x18027991e  xorps   xmm0, xmm0
0x180279921  movups  xmmword ptr [rbp+57h+pszPathIn], xmm0
0x180279925  mov     [rbp+57h+var_70], r15d
0x180279929  lea     r8, [rbp+57h+pszPathIn]
0x18027992d  mov     rdx, rdi
0x180279930  mov     ecx, 5
0x180279935  call    ?GetUserProfileFolderPath@UserProfile@Common@@YAJW4PROFILE_FOLDER_ID@12@PEBGAEAVStringBuffer@2@@Z; Common::UserProfile::GetUserProfileFolderPath(Common::UserProfile::PROFILE_FOLDER_ID,ushort const *,Common::StringBuffer &)
0x18027993a  mov     edi, eax
0x18027993c  test    eax, eax
0x18027993e  jns     short loc_18027997C
0x180279940  mov     rcx, [rbp+5Fh]; this
0x180279944  mov     r9d, eax; char *
0x180279947  lea     r8, aOnecoreBaseApp_99; "onecore\\base\\appmodel\\common\\userpr"...
0x18027994e  mov     edx, 40h ; '@'; void *
0x180279953  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180279958  lea     rcx, [rbp+57h+pszPathIn]; this
0x18027995c  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x180279961  lea     rcx, [rbp+57h+Path]; this
0x180279965  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x18027996a  nop
0x18027996b  mov     rcx, [rbp+57h+phkResult]
0x18027996f  call    ??$AutoHandleCloseHKEY@PEAUHKEY__@@@Common@@YAXPEAUHKEY__@@@Z; Common::AutoHandleCloseHKEY<HKEY__ *>(HKEY__ *)
0x180279974  nop
0x180279975  mov     ebx, edi
0x180279977  jmp     loc_180279AF1
0x18027997c  mov     [rsp+0D0h+bIgnoreCase], 1; unsigned int
0x180279984  mov     edx, 0Dh; cchCount1
0x180279989  mov     r9d, edx; cchCount2
0x18027998c  lea     r8, aUserprofile; "%USERPROFILE%"
0x180279993  mov     rcx, rbx; lpString1
0x180279996  call    cs:__imp_CompareStringOrdinal
0x18027999c  add     eax, 0FFFFFFFEh
0x18027999f  jnz     loc_180279B0C
0x1802799a5  xorps   xmm0, xmm0
0x1802799a8  movups  xmmword ptr [rbp+57h+var_68], xmm0
0x1802799ac  mov     [rbp+57h+var_58], r15d
0x1802799b0  mov     edx, dword ptr [rbp+57h+pszPathIn]
0x1802799b3  mov     eax, dword ptr [rbp+57h+Path]
0x1802799b6  add     eax, 0FFFFFFF4h
0x1802799b9  add     edx, eax; unsigned int
0x1802799bb  lea     rcx, [rbp+57h+var_68]; this
0x1802799bf  call    ?SetLength@StringBuffer@Common@@QEAAJK@Z; Common::StringBuffer::SetLength(ulong)
0x1802799c4  mov     edi, eax
0x1802799c6  test    eax, eax
0x1802799c8  jns     short loc_180279A0D
0x1802799ca  mov     rcx, [rbp+5Fh]; this
0x1802799ce  mov     r9d, eax; char *
0x1802799d1  lea     r8, aOnecoreBaseApp_99; "onecore\\base\\appmodel\\common\\userpr"...
0x1802799d8  mov     edx, 4Bh ; 'K'; void *
0x1802799dd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802799e2  lea     rcx, [rbp+57h+var_68]; this
0x1802799e6  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x1802799eb  lea     rcx, [rbp+57h+pszPathIn]; this
0x1802799ef  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x1802799f4  lea     rcx, [rbp+57h+Path]; this
0x1802799f8  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x1802799fd  nop
0x1802799fe  mov     rcx, [rbp+57h+phkResult]
0x180279a02  call    ??$AutoHandleCloseHKEY@PEAUHKEY__@@@Common@@YAXPEAUHKEY__@@@Z; Common::AutoHandleCloseHKEY<HKEY__ *>(HKEY__ *)
0x180279a07  nop
0x180279a08  jmp     loc_180279975
0x180279a0d  mov     eax, [rbp+57h+var_58]
0x180279a10  test    eax, eax
0x180279a12  jnz     short loc_180279A19
0x180279a14  mov     eax, r15d
0x180279a17  jmp     short loc_180279A1B
0x180279a19  dec     eax
0x180279a1b  lea     r9, [rbx+1Ch]; pszMore
0x180279a1f  lea     edx, [rax+1]; cchPathOut
0x180279a22  mov     r8, [rbp+57h+pszPathIn+8]; pszPathIn
0x180279a26  mov     rcx, [rbp+57h+var_68+8]; pszPathOut
0x180279a2a  call    cs:__imp_PathCchCombine
0x180279a30  mov     ebx, eax
0x180279a32  test    eax, eax
0x180279a34  jns     short loc_180279A76
0x180279a36  mov     rcx, [rbp+5Fh]; this
0x180279a3a  mov     r9d, eax; char *
0x180279a3d  lea     r8, aOnecoreBaseApp_99; "onecore\\base\\appmodel\\common\\userpr"...
0x180279a44  mov     edx, 50h ; 'P'; void *
0x180279a49  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180279a4e  lea     rcx, [rbp+57h+var_68]; this
0x180279a52  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x180279a57  lea     rcx, [rbp+57h+pszPathIn]; this
0x180279a5b  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x180279a60  lea     rcx, [rbp+57h+Path]; this
0x180279a64  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x180279a69  nop
0x180279a6a  mov     rcx, [rbp+57h+phkResult]
0x180279a6e  call    ??$AutoHandleCloseHKEY@PEAUHKEY__@@@Common@@YAXPEAUHKEY__@@@Z; Common::AutoHandleCloseHKEY<HKEY__ *>(HKEY__ *)
0x180279a73  nop
0x180279a74  jmp     short loc_180279AF1
0x180279a76  mov     rdx, [rbp+57h+var_68+8]; unsigned __int16 *
0x180279a7a  mov     rcx, rsi; this
0x180279a7d  call    ?SetValueFromString@StringBuffer@Common@@QEAAJPEBG@Z; Common::StringBuffer::SetValueFromString(ushort const *)
0x180279a82  mov     ebx, eax
0x180279a84  test    eax, eax
0x180279a86  jns     short loc_180279AC8
0x180279a88  mov     rcx, [rbp+5Fh]; this
0x180279a8c  mov     r9d, eax; char *
0x180279a8f  lea     r8, aOnecoreBaseApp_99; "onecore\\base\\appmodel\\common\\userpr"...
0x180279a96  mov     edx, 52h ; 'R'; void *
0x180279a9b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180279aa0  lea     rcx, [rbp+57h+var_68]; this
0x180279aa4  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x180279aa9  lea     rcx, [rbp+57h+pszPathIn]; this
0x180279aad  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x180279ab2  lea     rcx, [rbp+57h+Path]; this
0x180279ab6  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x180279abb  nop
0x180279abc  mov     rcx, [rbp+57h+phkResult]
0x180279ac0  call    ??$AutoHandleCloseHKEY@PEAUHKEY__@@@Common@@YAXPEAUHKEY__@@@Z; Common::AutoHandleCloseHKEY<HKEY__ *>(HKEY__ *)
0x180279ac5  nop
0x180279ac6  jmp     short loc_180279AF1
0x180279ac8  lea     rcx, [rbp+57h+var_68]; this
0x180279acc  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x180279ad1  lea     rcx, [rbp+57h+pszPathIn]; this
0x180279ad5  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x180279ada  lea     rcx, [rbp+57h+Path]; this
0x180279ade  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x180279ae3  nop
0x180279ae4  mov     rcx, [rbp+57h+phkResult]
0x180279ae8  call    ??$AutoHandleCloseHKEY@PEAUHKEY__@@@Common@@YAXPEAUHKEY__@@@Z; Common::AutoHandleCloseHKEY<HKEY__ *>(HKEY__ *)
0x180279aed  nop
0x180279aee  mov     ebx, r15d
0x180279af1  lea     rcx, [rbp+57h+pszPathOut]; this
0x180279af5  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x180279afa  mov     eax, ebx
0x180279afc  add     rsp, 0A8h
0x180279b03  pop     r15
0x180279b05  pop     r14
0x180279b07  pop     rdi
0x180279b08  pop     rsi
0x180279b09  pop     rbx
0x180279b0a  pop     rbp
0x180279b0b  retn
0x180279b0c  mov     rcx, [rbp+5Fh]; this
0x180279b10  mov     r9d, 0A1h; char *
0x180279b16  lea     r8, aOnecoreBaseApp_99; "onecore\\base\\appmodel\\common\\userpr"...
0x180279b1d  lea     edx, [r9-4Bh]; void *
0x180279b21  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180279b26  mov     ebx, eax
0x180279b28  lea     rcx, [rbp+57h+pszPathIn]; this
0x180279b2c  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x180279b31  lea     rcx, [rbp+57h+Path]; this
0x180279b35  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x180279b3a  nop
0x180279b3b  mov     rcx, [rbp+57h+phkResult]
0x180279b3f  call    ??$AutoHandleCloseHKEY@PEAUHKEY__@@@Common@@YAXPEAUHKEY__@@@Z; Common::AutoHandleCloseHKEY<HKEY__ *>(HKEY__ *)
0x180279b44  nop
0x180279b45  jmp     short loc_180279AF1
0x180279b47  mov     rdx, rbx; unsigned __int16 *
0x180279b4a  mov     rcx, rsi; this
0x180279b4d  call    ?SetValueFromString@StringBuffer@Common@@QEAAJPEBG@Z; Common::StringBuffer::SetValueFromString(ushort const *)
0x180279b52  mov     ebx, eax
0x180279b54  test    eax, eax
0x180279b56  jns     short loc_180279ADA
0x180279b58  mov     rcx, [rbp+5Fh]; this
0x180279b5c  mov     r9d, eax; char *
0x180279b5f  lea     r8, aOnecoreBaseApp_99; "onecore\\base\\appmodel\\common\\userpr"...
0x180279b66  mov     edx, 37h ; '7'; void *
0x180279b6b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180279b70  lea     rcx, [rbp+57h+Path]; this
0x180279b74  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x180279b79  nop
0x180279b7a  mov     rcx, [rbp+57h+phkResult]
0x180279b7e  call    ??$AutoHandleCloseHKEY@PEAUHKEY__@@@Common@@YAXPEAUHKEY__@@@Z; Common::AutoHandleCloseHKEY<HKEY__ *>(HKEY__ *)
0x180279b83  nop
0x180279b84  jmp     loc_180279AF1
```
