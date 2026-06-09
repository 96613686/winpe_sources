# Common::UserProfile::GetUserProfileFolderPath(Common::UserProfile::PROFILE_FOLDER_ID,ushort const *,Common::StringBuffer &)

- ea: `0x180279458`
- end: `0x1802797ba`
- name: `?GetUserProfileFolderPath@UserProfile@Common@@YAJW4PROFILE_FOLDER_ID@12@PEBGAEAVStringBuffer@2@@Z`
- size: `866`
- prototype: `int __high(enum Common::UserProfile::PROFILE_FOLDER_ID, const unsigned __int16 *, struct Common::StringBuffer *)`
- caller_count: `2`
- callee_count: `12`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800c0250`
- `0x1802797c0`

## callees

- `0x18000e91c`
- `0x18001a9e0`
- `0x1800613a8`
- `0x180061560`
- `0x180061ae8`
- `0x1800bc824`
- `0x1800bf238`
- `0x1800c0400`
- `0x180199ee0`
- `0x1802792a8`
- `0x180279458`
- `0x1802797c0`

## import_xrefs

- `ntdll!RtlExpandEnvironmentStrings` at `0x1802795cd`
- `ntdll!RtlExpandEnvironmentStrings` at `0x180279698`
- `ntdll!RtlExpandEnvironmentStrings` at `0x1802795cd`
- `ntdll!RtlExpandEnvironmentStrings` at `0x180279698`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x1802794dd`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x1802794dd`

## string_xrefs

- `0x180279565`: `ProfileImagePath`
- `0x1802794ee`: `onecore\base\appmodel\common\userprofile.cpp`
- `0x180279531`: `onecore\base\appmodel\common\userprofile.cpp`
- `0x180279582`: `onecore\base\appmodel\common\userprofile.cpp`
- `0x1802795e5`: `onecore\base\appmodel\common\userprofile.cpp`
- `0x180279636`: `onecore\base\appmodel\common\userprofile.cpp`
- `0x1802796a9`: `onecore\base\appmodel\common\userprofile.cpp`
- `0x1802796f4`: `onecore\base\appmodel\common\userprofile.cpp`
- `0x180279791`: `onecore\base\appmodel\common\userprofile.cpp`
- `0x1802797a8`: `onecore\base\appmodel\common\userprofile.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Common::UserProfile::GetUserProfileFolderPath(__int64 a1, const WCHAR *a2, Common::StringBuffer *a3)
{
  struct Common::StringBuffer *v5; // r8
  const char *v6; // r9
  __int64 v7; // rdx
  HRESULT v8; // eax
  unsigned int v9; // edi
  __int64 v10; // rdx
  int v11; // eax
  int v12; // eax
  unsigned __int64 v13; // r8
  int StringValue; // eax
  __int64 v15; // rsi
  int v16; // eax
  int v17; // eax
  int v18; // eax
  int v19; // eax
  int v20; // eax
  int UserProfileFolderPathFromSid; // eax
  int v23; // [rsp+20h] [rbp-29h]
  int v24; // [rsp+20h] [rbp-29h]
  int v25; // [rsp+20h] [rbp-29h]
  __int128 v26; // [rsp+40h] [rbp-9h] BYREF
  int v27; // [rsp+50h] [rbp+7h]
  unsigned __int16 *v28[2]; // [rsp+58h] [rbp+Fh] BYREF
  int v29; // [rsp+68h] [rbp+1Fh]
  PWSTR pszPathOut[2]; // [rsp+70h] [rbp+27h] BYREF
  int v31; // [rsp+80h] [rbp+37h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]
  HKEY phkResult; // [rsp+C8h] [rbp+7Fh] BYREF

  Common::StringBuffer::Clear(a3);
  if ( (_DWORD)v6 == 5 )
  {
    *(_OWORD *)pszPathOut = 0;
    v31 = 0;
    v7 = -1;
    do
      ++v7;
    while ( a2[v7] );
    v8 = Common::StringBuffer::SetLength((Common::StringBuffer *)pszPathOut, v7 + 57);
    v9 = v8;
    if ( v8 < 0 )
    {
      v10 = 120;
LABEL_11:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v10,
        (unsigned int)"onecore\\base\\appmodel\\common\\userprofile.cpp",
        (const char *)(unsigned int)v8,
        v23);
LABEL_28:
      Common::StringBuffer::~StringBuffer((Common::StringBuffer *)pszPathOut);
      return v9;
    }
    if ( v31 )
      v11 = v31 - 1;
    else
      v11 = 0;
    v8 = PathCchCombine(
           pszPathOut[1],
           (unsigned int)(v11 + 1),
           L"Software\\Microsoft\\Windows NT\\CurrentVersion\\ProfileList",
           a2);
    v9 = v8;
    if ( v8 < 0 )
    {
      v10 = 125;
      goto LABEL_11;
    }
    phkResult = 0;
    v12 = Common::RegistryKey::Open(&phkResult, HKEY_LOCAL_MACHINE, pszPathOut[1], 0x20019u);
    v9 = v12;
    if ( v12 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x80,
        (unsigned int)"onecore\\base\\appmodel\\common\\userprofile.cpp",
        (const char *)(unsigned int)v12,
        v23);
      Common::AutoHandleCloseHKEY<HKEY__ *>(phkResult);
      goto LABEL_28;
    }
    v26 = 0;
    v27 = 0;
    StringValue = Common::RegistryKey::GetStringValue(
                    (Common::RegistryKey *)&phkResult,
                    L"ProfileImagePath",
                    v13,
                    (struct Common::StringBuffer *)&v26,
                    0);
    v9 = StringValue;
    if ( StringValue < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x82,
        (unsigned int)"onecore\\base\\appmodel\\common\\userprofile.cpp",
        (const char *)(unsigned int)StringValue,
        v24);
      Common::StringBuffer::~StringBuffer((Common::StringBuffer *)&v26);
      Common::AutoHandleCloseHKEY<HKEY__ *>(phkResult);
      goto LABEL_28;
    }
    v15 = (unsigned int)v26;
    v16 = RtlExpandEnvironmentStrings(0, *((_QWORD *)&v26 + 1), (unsigned int)v26, 0);
    if ( v16 != -1073741789 && v16 < 0 )
    {
      v9 = wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)0x8E,
             (unsigned int)"onecore\\base\\appmodel\\common\\userprofile.cpp",
             (const char *)(unsigned int)v16,
             0);
      Common::StringBuffer::~StringBuffer((Common::StringBuffer *)&v26);
      Common::AutoHandleCloseHKEY<HKEY__ *>(phkResult);
      goto LABEL_28;
    }
    *(_OWORD *)v28 = 0;
    v29 = 0;
    v17 = Common::StringBuffer::SetLength((Common::StringBuffer *)v28, 0xFFFFFFFF);
    v9 = v17;
    if ( v17 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x92,
        (unsigned int)"onecore\\base\\appmodel\\common\\userprofile.cpp",
        (const char *)(unsigned int)v17,
        0);
      Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v28);
      Common::StringBuffer::~StringBuffer((Common::StringBuffer *)&v26);
      Common::AutoHandleCloseHKEY<HKEY__ *>(phkResult);
      goto LABEL_28;
    }
    if ( v29 )
      v18 = v29 - 1;
    else
      v18 = 0;
    v25 = v18 + 1;
    v19 = RtlExpandEnvironmentStrings(0, *((_QWORD *)&v26 + 1), v15, v28[1]);
    if ( v19 < 0 )
    {
      v9 = wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)0x9B,
             (unsigned int)"onecore\\base\\appmodel\\common\\userprofile.cpp",
             (const char *)(unsigned int)v19,
             v25);
      Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v28);
      Common::StringBuffer::~StringBuffer((Common::StringBuffer *)&v26);
      Common::AutoHandleCloseHKEY<HKEY__ *>(phkResult);
      goto LABEL_28;
    }
    v20 = Common::StringBuffer::SetValueFromString(a3, v28[1]);
    v9 = v20;
    if ( v20 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x9D,
        (unsigned int)"onecore\\base\\appmodel\\common\\userprofile.cpp",
        (const char *)(unsigned int)v20,
        v25);
      Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v28);
      Common::StringBuffer::~StringBuffer((Common::StringBuffer *)&v26);
      Common::AutoHandleCloseHKEY<HKEY__ *>(phkResult);
      goto LABEL_28;
    }
    Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v28);
    Common::StringBuffer::~StringBuffer((Common::StringBuffer *)&v26);
    Common::AutoHandleCloseHKEY<HKEY__ *>(phkResult);
    Common::StringBuffer::~StringBuffer((Common::StringBuffer *)pszPathOut);
  }
  else
  {
    if ( (_DWORD)v6 != 6 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xCA,
        (unsigned int)"onecore\\base\\appmodel\\common\\userprofile.cpp",
        v6);
    UserProfileFolderPathFromSid = GetUserProfileFolderPathFromSid(a2, L"Local AppData", v5);
    v9 = UserProfileFolderPathFromSid;
    if ( UserProfileFolderPathFromSid < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA5,
        (unsigned int)"onecore\\base\\appmodel\\common\\userprofile.cpp",
        (const char *)(unsigned int)UserProfileFolderPathFromSid,
        v23);
      return v9;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180279458  mov     [rsp-8+arg_0], rbx
0x18027945d  mov     [rsp-8+arg_8], rsi
0x180279462  push    rbp
0x180279463  push    rdi
0x180279464  push    r14
0x180279466  lea     rbp, [rsp-47h]
0x18027946b  sub     rsp, 90h
0x180279472  mov     r14, r8
0x180279475  mov     rsi, rdx
0x180279478  mov     r9d, ecx
0x18027947b  mov     rcx, r8; this
0x18027947e  call    ?Clear@StringBuffer@Common@@QEAAXXZ; Common::StringBuffer::Clear(void)
0x180279483  cmp     r9d, 5
0x180279487  jnz     loc_18027976F
0x18027948d  xorps   xmm0, xmm0
0x180279490  movups  xmmword ptr [rbp+57h+pszPathOut], xmm0
0x180279494  xor     ebx, ebx
0x180279496  mov     [rbp+57h+var_20], ebx
0x180279499  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18027949d  inc     rdx
0x1802794a0  cmp     [rsi+rdx*2], bx
0x1802794a4  jnz     short loc_18027949D
0x1802794a6  add     edx, 39h ; '9'; unsigned int
0x1802794a9  lea     rcx, [rbp+57h+pszPathOut]; this
0x1802794ad  call    ?SetLength@StringBuffer@Common@@QEAAJK@Z; Common::StringBuffer::SetLength(ulong)
0x1802794b2  mov     edi, eax
0x1802794b4  test    eax, eax
0x1802794b6  jns     short loc_1802794BF
0x1802794b8  mov     edx, 78h ; 'x'
0x1802794bd  jmp     short loc_1802794EE
0x1802794bf  mov     eax, [rbp+57h+var_20]
0x1802794c2  test    eax, eax
0x1802794c4  jnz     short loc_1802794CA
0x1802794c6  mov     eax, ebx
0x1802794c8  jmp     short loc_1802794CC
0x1802794ca  dec     eax
0x1802794cc  lea     edx, [rax+1]; cchPathOut
0x1802794cf  mov     r9, rsi; pszMore
0x1802794d2  lea     r8, pszPathIn; "Software\\Microsoft\\Windows NT\\Curren"...
0x1802794d9  mov     rcx, [rbp+57h+pszPathOut+8]; pszPathOut
0x1802794dd  call    cs:__imp_PathCchCombine
0x1802794e3  mov     edi, eax
0x1802794e5  test    eax, eax
0x1802794e7  jns     short loc_180279506
0x1802794e9  mov     edx, 7Dh ; '}'; void *
0x1802794ee  lea     r8, aOnecoreBaseApp_99; "onecore\\base\\appmodel\\common\\userpr"...
0x1802794f5  mov     r9d, eax; char *
0x1802794f8  mov     rcx, [rbp+5Fh]; this
0x1802794fc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180279501  jmp     loc_180279722
0x180279506  mov     [rbp+57h+phkResult], rbx
0x18027950a  mov     r9d, 20019h; samDesired
0x180279510  mov     r8, [rbp+57h+pszPathOut+8]; lpSubKey
0x180279514  mov     rdx, 0FFFFFFFF80000002h; hKey
0x18027951b  lea     rcx, [rbp+57h+phkResult]; phkResult
0x18027951f  call    ?Open@RegistryKey@Common@@QEAAJQEAUHKEY__@@PEBGK@Z; Common::RegistryKey::Open(HKEY__ * const,ushort const *,ulong)
0x180279524  mov     edi, eax
0x180279526  test    eax, eax
0x180279528  jns     short loc_180279552
0x18027952a  mov     rcx, [rbp+5Fh]; this
0x18027952e  mov     r9d, eax; char *
0x180279531  lea     r8, aOnecoreBaseApp_99; "onecore\\base\\appmodel\\common\\userpr"...
0x180279538  mov     edx, 80h; void *
0x18027953d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180279542  nop
0x180279543  mov     rcx, [rbp+57h+phkResult]
0x180279547  call    ??$AutoHandleCloseHKEY@PEAUHKEY__@@@Common@@YAXPEAUHKEY__@@@Z; Common::AutoHandleCloseHKEY<HKEY__ *>(HKEY__ *)
0x18027954c  nop
0x18027954d  jmp     loc_180279722
0x180279552  xorps   xmm0, xmm0
0x180279555  movups  [rbp+57h+var_60], xmm0
0x180279559  mov     [rbp+57h+var_50], ebx
0x18027955c  mov     [rsp+0A0h+var_80], rbx; int
0x180279561  lea     r9, [rbp+57h+var_60]; struct Common::StringBuffer *
0x180279565  lea     rdx, aProfileimagepa; "ProfileImagePath"
0x18027956c  lea     rcx, [rbp+57h+phkResult]; this
0x180279570  call    ?GetStringValue@RegistryKey@Common@@QEAAJPEBG_KAEAVStringBuffer@2@PEAK@Z; Common::RegistryKey::GetStringValue(ushort const *,unsigned __int64,Common::StringBuffer &,ulong *)
0x180279575  mov     edi, eax
0x180279577  test    eax, eax
0x180279579  jns     short loc_1802795AC
0x18027957b  mov     rcx, [rbp+5Fh]; this
0x18027957f  mov     r9d, eax; char *
0x180279582  lea     r8, aOnecoreBaseApp_99; "onecore\\base\\appmodel\\common\\userpr"...
0x180279589  mov     edx, 82h; void *
0x18027958e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180279593  lea     rcx, [rbp+57h+var_60]; this
0x180279597  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x18027959c  nop
0x18027959d  mov     rcx, [rbp+57h+phkResult]
0x1802795a1  call    ??$AutoHandleCloseHKEY@PEAUHKEY__@@@Common@@YAXPEAUHKEY__@@@Z; Common::AutoHandleCloseHKEY<HKEY__ *>(HKEY__ *)
0x1802795a6  nop
0x1802795a7  jmp     loc_180279722
0x1802795ac  mov     [rbp+57h+var_70], rbx
0x1802795b0  mov     esi, dword ptr [rbp+57h+var_60]
0x1802795b3  lea     rax, [rbp+57h+var_70]
0x1802795b7  mov     [rsp+0A0h+var_78], rax
0x1802795bc  mov     [rsp+0A0h+var_80], rbx; int
0x1802795c1  xor     r9d, r9d
0x1802795c4  mov     r8d, esi
0x1802795c7  mov     rdx, qword ptr [rbp+57h+var_60+8]
0x1802795cb  xor     ecx, ecx
0x1802795cd  call    cs:__imp_RtlExpandEnvironmentStrings
0x1802795d3  cmp     eax, 0C0000023h
0x1802795d8  jz      short loc_180279611
0x1802795da  test    eax, eax
0x1802795dc  jns     short loc_180279611
0x1802795de  mov     rcx, [rbp+5Fh]; this
0x1802795e2  mov     r9d, eax; char *
0x1802795e5  lea     r8, aOnecoreBaseApp_99; "onecore\\base\\appmodel\\common\\userpr"...
0x1802795ec  mov     edx, 8Eh; void *
0x1802795f1  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1802795f6  mov     edi, eax
0x1802795f8  lea     rcx, [rbp+57h+var_60]; this
0x1802795fc  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x180279601  nop
0x180279602  mov     rcx, [rbp+57h+phkResult]
0x180279606  call    ??$AutoHandleCloseHKEY@PEAUHKEY__@@@Common@@YAXPEAUHKEY__@@@Z; Common::AutoHandleCloseHKEY<HKEY__ *>(HKEY__ *)
0x18027960b  nop
0x18027960c  jmp     loc_180279722
0x180279611  xorps   xmm0, xmm0
0x180279614  movups  xmmword ptr [rbp+57h+var_48], xmm0
0x180279618  mov     [rbp+57h+var_38], ebx
0x18027961b  mov     edx, dword ptr [rbp+57h+var_70]
0x18027961e  dec     edx; unsigned int
0x180279620  lea     rcx, [rbp+57h+var_48]; this
0x180279624  call    ?SetLength@StringBuffer@Common@@QEAAJK@Z; Common::StringBuffer::SetLength(ulong)
0x180279629  mov     edi, eax
0x18027962b  test    eax, eax
0x18027962d  jns     short loc_180279669
0x18027962f  mov     rcx, [rbp+5Fh]; this
0x180279633  mov     r9d, eax; char *
0x180279636  lea     r8, aOnecoreBaseApp_99; "onecore\\base\\appmodel\\common\\userpr"...
0x18027963d  mov     edx, 92h; void *
0x180279642  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180279647  lea     rcx, [rbp+57h+var_48]; this
0x18027964b  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x180279650  lea     rcx, [rbp+57h+var_60]; this
0x180279654  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x180279659  nop
0x18027965a  mov     rcx, [rbp+57h+phkResult]
0x18027965e  call    ??$AutoHandleCloseHKEY@PEAUHKEY__@@@Common@@YAXPEAUHKEY__@@@Z; Common::AutoHandleCloseHKEY<HKEY__ *>(HKEY__ *)
0x180279663  nop
0x180279664  jmp     loc_180279722
0x180279669  mov     [rbp+57h+var_68], rbx
0x18027966d  mov     eax, [rbp+57h+var_38]
0x180279670  test    eax, eax
0x180279672  jnz     short loc_180279678
0x180279674  mov     eax, ebx
0x180279676  jmp     short loc_18027967A
0x180279678  dec     eax
0x18027967a  lea     ecx, [rax+1]
0x18027967d  lea     rax, [rbp+57h+var_68]
0x180279681  mov     [rsp+0A0h+var_78], rax
0x180279686  mov     [rsp+0A0h+var_80], rcx; int
0x18027968b  mov     r9, [rbp+57h+var_48+8]
0x18027968f  mov     r8, rsi
0x180279692  mov     rdx, qword ptr [rbp+57h+var_60+8]
0x180279696  xor     ecx, ecx
0x180279698  call    cs:__imp_RtlExpandEnvironmentStrings
0x18027969e  test    eax, eax
0x1802796a0  jns     short loc_1802796DB
0x1802796a2  mov     rcx, [rbp+5Fh]; this
0x1802796a6  mov     r9d, eax; char *
0x1802796a9  lea     r8, aOnecoreBaseApp_99; "onecore\\base\\appmodel\\common\\userpr"...
0x1802796b0  mov     edx, 9Bh; void *
0x1802796b5  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1802796ba  mov     edi, eax
0x1802796bc  lea     rcx, [rbp+57h+var_48]; this
0x1802796c0  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x1802796c5  lea     rcx, [rbp+57h+var_60]; this
0x1802796c9  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x1802796ce  nop
0x1802796cf  mov     rcx, [rbp+57h+phkResult]
0x1802796d3  call    ??$AutoHandleCloseHKEY@PEAUHKEY__@@@Common@@YAXPEAUHKEY__@@@Z; Common::AutoHandleCloseHKEY<HKEY__ *>(HKEY__ *)
0x1802796d8  nop
0x1802796d9  jmp     short loc_180279722
0x1802796db  mov     rdx, [rbp+57h+var_48+8]; unsigned __int16 *
0x1802796df  mov     rcx, r14; this
0x1802796e2  call    ?SetValueFromString@StringBuffer@Common@@QEAAJPEBG@Z; Common::StringBuffer::SetValueFromString(ushort const *)
0x1802796e7  mov     edi, eax
0x1802796e9  test    eax, eax
0x1802796eb  jns     short loc_180279745
0x1802796ed  mov     rcx, [rbp+5Fh]; this
0x1802796f1  mov     r9d, eax; char *
0x1802796f4  lea     r8, aOnecoreBaseApp_99; "onecore\\base\\appmodel\\common\\userpr"...
0x1802796fb  mov     edx, 9Dh; void *
0x180279700  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180279705  lea     rcx, [rbp+57h+var_48]; this
0x180279709  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x18027970e  lea     rcx, [rbp+57h+var_60]; this
0x180279712  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x180279717  nop
0x180279718  mov     rcx, [rbp+57h+phkResult]
0x18027971c  call    ??$AutoHandleCloseHKEY@PEAUHKEY__@@@Common@@YAXPEAUHKEY__@@@Z; Common::AutoHandleCloseHKEY<HKEY__ *>(HKEY__ *)
0x180279721  nop
0x180279722  lea     rcx, [rbp+57h+pszPathOut]; this
0x180279726  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x18027972b  mov     eax, edi
0x18027972d  lea     r11, [rsp+0A0h+var_10]
0x180279735  mov     rbx, [r11+20h]
0x180279739  mov     rsi, [r11+28h]
0x18027973d  mov     rsp, r11
0x180279740  pop     r14
0x180279742  pop     rdi
0x180279743  pop     rbp
0x180279744  retn
0x180279745  lea     rcx, [rbp+57h+var_48]; this
0x180279749  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x18027974e  lea     rcx, [rbp+57h+var_60]; this
0x180279752  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x180279757  nop
0x180279758  mov     rcx, [rbp+57h+phkResult]
0x18027975c  call    ??$AutoHandleCloseHKEY@PEAUHKEY__@@@Common@@YAXPEAUHKEY__@@@Z; Common::AutoHandleCloseHKEY<HKEY__ *>(HKEY__ *)
0x180279761  nop
0x180279762  lea     rcx, [rbp+57h+pszPathOut]; this
0x180279766  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x18027976b  xor     eax, eax
0x18027976d  jmp     short loc_18027972D
0x18027976f  cmp     r9d, 6
0x180279773  jnz     short loc_1802797A4
0x180279775  lea     rdx, aLocalAppdata; "Local AppData"
0x18027977c  mov     rcx, rsi; pszPathIn
0x18027977f  call    ?GetUserProfileFolderPathFromSid@@YAJPEBG0AEAVStringBuffer@Common@@@Z; GetUserProfileFolderPathFromSid(ushort const *,ushort const *,Common::StringBuffer &)
0x180279784  mov     edi, eax
0x180279786  test    eax, eax
0x180279788  jns     short loc_18027976B
0x18027978a  mov     rcx, [rbp+5Fh]; this
0x18027978e  mov     r9d, eax; char *
0x180279791  lea     r8, aOnecoreBaseApp_99; "onecore\\base\\appmodel\\common\\userpr"...
0x180279798  mov     edx, 0A5h; void *
0x18027979d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802797a2  jmp     short loc_18027972B
0x1802797a4  mov     rcx, [rbp+5Fh]; this
0x1802797a8  lea     r8, aOnecoreBaseApp_99; "onecore\\base\\appmodel\\common\\userpr"...
0x1802797af  mov     edx, 0CAh; void *
0x1802797b4  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
