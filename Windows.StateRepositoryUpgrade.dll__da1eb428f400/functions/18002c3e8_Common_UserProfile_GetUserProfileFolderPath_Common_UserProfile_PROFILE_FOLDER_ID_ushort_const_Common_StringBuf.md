# Common::UserProfile::GetUserProfileFolderPath(Common::UserProfile::PROFILE_FOLDER_ID,ushort const *,Common::StringBuffer &)

- ea: `0x18002c3e8`
- end: `0x18002c6c3`
- name: `?GetUserProfileFolderPath@UserProfile@Common@@YAJW4PROFILE_FOLDER_ID@12@PEBGAEAVStringBuffer@2@@Z`
- size: `731`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `12`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180011a40`
- `0x18002c6cc`

## callees

- `0x180009088`
- `0x18000a3c0`
- `0x18000d9a4`
- `0x18000f62c`
- `0x180013728`
- `0x18002c1b0`
- `0x18002c304`
- `0x18002c3e8`
- `0x18002c6cc`
- `0x18002cffc`
- `0x18002d190`
- `0x18002d2dc`

## import_xrefs

- `ntdll!RtlExpandEnvironmentStrings` at `0x18002c53e`
- `ntdll!RtlExpandEnvironmentStrings` at `0x18002c5c2`
- `ntdll!RtlExpandEnvironmentStrings` at `0x18002c53e`
- `ntdll!RtlExpandEnvironmentStrings` at `0x18002c5c2`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18002c46d`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18002c46d`

## string_xrefs

- `0x18002c482`: `onecore\base\appmodel\common\userprofile.cpp`
- `0x18002c4be`: `onecore\base\appmodel\common\userprofile.cpp`
- `0x18002c504`: `onecore\base\appmodel\common\userprofile.cpp`
- `0x18002c553`: `onecore\base\appmodel\common\userprofile.cpp`
- `0x18002c5d0`: `onecore\base\appmodel\common\userprofile.cpp`
- `0x18002c603`: `onecore\base\appmodel\common\userprofile.cpp`
- `0x18002c697`: `onecore\base\appmodel\common\userprofile.cpp`
- `0x18002c6b1`: `onecore\base\appmodel\common\userprofile.cpp`
- `0x18002c4e6`: `ProfileImagePath`

## pseudocode

```c
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
  __int64 v18; // rdx
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
LABEL_32:
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
LABEL_31:
      Common::AutoHandleCloseHKEY<HKEY__ *>(phkResult);
      goto LABEL_32;
    }
    v27 = 0;
    v26 = 0;
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
LABEL_30:
      Common::StringBuffer::~StringBuffer((Common::StringBuffer *)&v26);
      goto LABEL_31;
    }
    v15 = (unsigned int)v26;
    v25 = 0;
    v16 = RtlExpandEnvironmentStrings(0, *((_QWORD *)&v26 + 1), (unsigned int)v26, 0);
    if ( v16 != -1073741789 && v16 < 0 )
    {
      v9 = wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)0x8E,
             (unsigned int)"onecore\\base\\appmodel\\common\\userprofile.cpp",
             (const char *)(unsigned int)v16,
             0);
      goto LABEL_30;
    }
    v29 = 0;
    *(_OWORD *)v28 = 0;
    v17 = Common::StringBuffer::SetLength((Common::StringBuffer *)v28, 0xFFFFFFFF);
    v9 = v17;
    if ( v17 < 0 )
    {
      v18 = 146;
LABEL_28:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v18,
        (unsigned int)"onecore\\base\\appmodel\\common\\userprofile.cpp",
        (const char *)(unsigned int)v17,
        v25);
      goto LABEL_29;
    }
    if ( v29 )
      v19 = v29 - 1;
    else
      v19 = 0;
    v25 = v19 + 1;
    v20 = RtlExpandEnvironmentStrings(0, *((_QWORD *)&v26 + 1), v15, v28[1]);
    if ( v20 < 0 )
    {
      v9 = wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)0x9B,
             (unsigned int)"onecore\\base\\appmodel\\common\\userprofile.cpp",
             (const char *)(unsigned int)v20,
             v25);
LABEL_29:
      Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v28);
      goto LABEL_30;
    }
    v17 = Common::StringBuffer::SetValueFromString(a3, v28[1]);
    v9 = v17;
    if ( v17 < 0 )
    {
      v18 = 157;
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
0x18002c3e8  mov     [rsp-8+arg_0], rbx
0x18002c3ed  mov     [rsp-8+arg_8], rsi
0x18002c3f2  push    rbp
0x18002c3f3  push    rdi
0x18002c3f4  push    r14
0x18002c3f6  lea     rbp, [rsp-47h]
0x18002c3fb  sub     rsp, 90h
0x18002c402  mov     r9d, ecx
0x18002c405  mov     r14, r8
0x18002c408  mov     rcx, r8; this
0x18002c40b  mov     rsi, rdx
0x18002c40e  call    ?Clear@StringBuffer@Common@@QEAAXXZ; Common::StringBuffer::Clear(void)
0x18002c413  cmp     r9d, 5
0x18002c417  jnz     loc_18002C678
0x18002c41d  xor     ebx, ebx
0x18002c41f  xorps   xmm0, xmm0
0x18002c422  movups  xmmword ptr [rbp+57h+pszPathOut], xmm0
0x18002c426  mov     [rbp+57h+var_20], ebx
0x18002c429  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18002c42d  inc     rdx
0x18002c430  cmp     [rsi+rdx*2], bx
0x18002c434  jnz     short loc_18002C42D
0x18002c436  add     edx, 39h ; '9'; unsigned int
0x18002c439  lea     rcx, [rbp+57h+pszPathOut]; this
0x18002c43d  call    ?SetLength@StringBuffer@Common@@QEAAJK@Z; Common::StringBuffer::SetLength(ulong)
0x18002c442  mov     edi, eax
0x18002c444  test    eax, eax
0x18002c446  jns     short loc_18002C44F
0x18002c448  mov     edx, 78h ; 'x'
0x18002c44d  jmp     short loc_18002C47E
0x18002c44f  mov     eax, [rbp+57h+var_20]
0x18002c452  test    eax, eax
0x18002c454  jnz     short loc_18002C45A
0x18002c456  mov     eax, ebx
0x18002c458  jmp     short loc_18002C45C
0x18002c45a  dec     eax
0x18002c45c  mov     rcx, [rbp+57h+pszPathOut+8]; pszPathOut
0x18002c460  lea     edx, [rax+1]; cchPathOut
0x18002c463  mov     r9, rsi; pszMore
0x18002c466  lea     r8, pszPathIn; "Software\\Microsoft\\Windows NT\\Curren"...
0x18002c46d  call    cs:__imp_PathCchCombine
0x18002c473  mov     edi, eax
0x18002c475  test    eax, eax
0x18002c477  jns     short loc_18002C496
0x18002c479  mov     edx, 7Dh ; '}'; void *
0x18002c47e  mov     rcx, [rbp+5Fh]; this
0x18002c482  lea     r8, aOnecoreBaseApp_14; "onecore\\base\\appmodel\\common\\userpr"...
0x18002c489  mov     r9d, eax; char *
0x18002c48c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c491  jmp     loc_18002C62D
0x18002c496  mov     r8, [rbp+57h+pszPathOut+8]; lpSubKey
0x18002c49a  lea     rcx, [rbp+57h+phkResult]; phkResult
0x18002c49e  mov     r9d, 20019h; samDesired
0x18002c4a4  mov     [rbp+57h+phkResult], rbx
0x18002c4a8  mov     rdx, 0FFFFFFFF80000002h; hKey
0x18002c4af  call    ?Open@RegistryKey@Common@@QEAAJQEAUHKEY__@@PEBGK@Z; Common::RegistryKey::Open(HKEY__ * const,ushort const *,ulong)
0x18002c4b4  mov     edi, eax
0x18002c4b6  test    eax, eax
0x18002c4b8  jns     short loc_18002C4D7
0x18002c4ba  mov     rcx, [rbp+5Fh]; this
0x18002c4be  lea     r8, aOnecoreBaseApp_14; "onecore\\base\\appmodel\\common\\userpr"...
0x18002c4c5  mov     r9d, eax; char *
0x18002c4c8  mov     edx, 80h; void *
0x18002c4cd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c4d2  jmp     loc_18002C624
0x18002c4d7  xorps   xmm0, xmm0
0x18002c4da  mov     [rbp+57h+var_50], ebx
0x18002c4dd  lea     r9, [rbp+57h+var_60]; struct Common::StringBuffer *
0x18002c4e1  mov     [rsp+0A0h+var_80], rbx; int
0x18002c4e6  lea     rdx, aProfileimagepa; "ProfileImagePath"
0x18002c4ed  lea     rcx, [rbp+57h+phkResult]; this
0x18002c4f1  movups  [rbp+57h+var_60], xmm0
0x18002c4f5  call    ?GetStringValue@RegistryKey@Common@@QEAAJPEBG_KAEAVStringBuffer@2@PEAK@Z; Common::RegistryKey::GetStringValue(ushort const *,unsigned __int64,Common::StringBuffer &,ulong *)
0x18002c4fa  mov     edi, eax
0x18002c4fc  test    eax, eax
0x18002c4fe  jns     short loc_18002C51D
0x18002c500  mov     rcx, [rbp+5Fh]; this
0x18002c504  lea     r8, aOnecoreBaseApp_14; "onecore\\base\\appmodel\\common\\userpr"...
0x18002c50b  mov     r9d, eax; char *
0x18002c50e  mov     edx, 82h; void *
0x18002c513  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c518  jmp     loc_18002C61B
0x18002c51d  mov     esi, dword ptr [rbp+57h+var_60]
0x18002c520  lea     rax, [rbp+57h+var_70]
0x18002c524  mov     rdx, qword ptr [rbp+57h+var_60+8]
0x18002c528  mov     r8d, esi
0x18002c52b  mov     [rsp+0A0h+var_78], rax
0x18002c530  xor     r9d, r9d
0x18002c533  xor     ecx, ecx
0x18002c535  mov     [rsp+0A0h+var_80], rbx; int
0x18002c53a  mov     [rbp+57h+var_70], rbx
0x18002c53e  call    cs:__imp_RtlExpandEnvironmentStrings
0x18002c544  cmp     eax, 0C0000023h
0x18002c549  jz      short loc_18002C56E
0x18002c54b  test    eax, eax
0x18002c54d  jns     short loc_18002C56E
0x18002c54f  mov     rcx, [rbp+5Fh]; this
0x18002c553  lea     r8, aOnecoreBaseApp_14; "onecore\\base\\appmodel\\common\\userpr"...
0x18002c55a  mov     r9d, eax; char *
0x18002c55d  mov     edx, 8Eh; void *
0x18002c562  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18002c567  mov     edi, eax
0x18002c569  jmp     loc_18002C61B
0x18002c56e  mov     edx, dword ptr [rbp+57h+var_70]
0x18002c571  lea     rcx, [rbp+57h+var_48]; this
0x18002c575  xorps   xmm0, xmm0
0x18002c578  mov     [rbp+57h+var_38], ebx
0x18002c57b  dec     edx; unsigned int
0x18002c57d  movups  xmmword ptr [rbp+57h+var_48], xmm0
0x18002c581  call    ?SetLength@StringBuffer@Common@@QEAAJK@Z; Common::StringBuffer::SetLength(ulong)
0x18002c586  mov     edi, eax
0x18002c588  test    eax, eax
0x18002c58a  jns     short loc_18002C593
0x18002c58c  mov     edx, 92h
0x18002c591  jmp     short loc_18002C5FF
0x18002c593  mov     eax, [rbp+57h+var_38]
0x18002c596  mov     [rbp+57h+var_68], rbx
0x18002c59a  test    eax, eax
0x18002c59c  jnz     short loc_18002C5A2
0x18002c59e  mov     eax, ebx
0x18002c5a0  jmp     short loc_18002C5A4
0x18002c5a2  dec     eax
0x18002c5a4  mov     r9, [rbp+57h+var_48+8]
0x18002c5a8  lea     ecx, [rax+1]
0x18002c5ab  mov     rdx, qword ptr [rbp+57h+var_60+8]
0x18002c5af  lea     rax, [rbp+57h+var_68]
0x18002c5b3  mov     [rsp+0A0h+var_78], rax
0x18002c5b8  mov     r8, rsi
0x18002c5bb  mov     [rsp+0A0h+var_80], rcx; int
0x18002c5c0  xor     ecx, ecx
0x18002c5c2  call    cs:__imp_RtlExpandEnvironmentStrings
0x18002c5c8  test    eax, eax
0x18002c5ca  jns     short loc_18002C5E8
0x18002c5cc  mov     rcx, [rbp+5Fh]; this
0x18002c5d0  lea     r8, aOnecoreBaseApp_14; "onecore\\base\\appmodel\\common\\userpr"...
0x18002c5d7  mov     r9d, eax; char *
0x18002c5da  mov     edx, 9Bh; void *
0x18002c5df  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18002c5e4  mov     edi, eax
0x18002c5e6  jmp     short loc_18002C612
0x18002c5e8  mov     rdx, [rbp+57h+var_48+8]; unsigned __int16 *
0x18002c5ec  mov     rcx, r14; this
0x18002c5ef  call    ?SetValueFromString@StringBuffer@Common@@QEAAJPEBG@Z; Common::StringBuffer::SetValueFromString(ushort const *)
0x18002c5f4  mov     edi, eax
0x18002c5f6  test    eax, eax
0x18002c5f8  jns     short loc_18002C650
0x18002c5fa  mov     edx, 9Dh; void *
0x18002c5ff  mov     rcx, [rbp+5Fh]; this
0x18002c603  lea     r8, aOnecoreBaseApp_14; "onecore\\base\\appmodel\\common\\userpr"...
0x18002c60a  mov     r9d, eax; char *
0x18002c60d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c612  lea     rcx, [rbp+57h+var_48]; this
0x18002c616  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x18002c61b  lea     rcx, [rbp+57h+var_60]; this
0x18002c61f  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x18002c624  mov     rcx, [rbp+57h+phkResult]
0x18002c628  call    ??$AutoHandleCloseHKEY@PEAUHKEY__@@@Common@@YAXPEAUHKEY__@@@Z; Common::AutoHandleCloseHKEY<HKEY__ *>(HKEY__ *)
0x18002c62d  lea     rcx, [rbp+57h+pszPathOut]; this
0x18002c631  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x18002c636  mov     eax, edi
0x18002c638  lea     r11, [rsp+0A0h+var_10]
0x18002c640  mov     rbx, [r11+20h]
0x18002c644  mov     rsi, [r11+28h]
0x18002c648  mov     rsp, r11
0x18002c64b  pop     r14
0x18002c64d  pop     rdi
0x18002c64e  pop     rbp
0x18002c64f  retn
0x18002c650  lea     rcx, [rbp+57h+var_48]; this
0x18002c654  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x18002c659  lea     rcx, [rbp+57h+var_60]; this
0x18002c65d  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x18002c662  mov     rcx, [rbp+57h+phkResult]
0x18002c666  call    ??$AutoHandleCloseHKEY@PEAUHKEY__@@@Common@@YAXPEAUHKEY__@@@Z; Common::AutoHandleCloseHKEY<HKEY__ *>(HKEY__ *)
0x18002c66b  lea     rcx, [rbp+57h+pszPathOut]; this
0x18002c66f  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x18002c674  xor     eax, eax
0x18002c676  jmp     short loc_18002C638
0x18002c678  cmp     r9d, 6
0x18002c67c  jnz     short loc_18002C6AD
0x18002c67e  lea     rdx, aLocalAppdata; "Local AppData"
0x18002c685  mov     rcx, rsi; pszPathIn
0x18002c688  call    ?GetUserProfileFolderPathFromSid@@YAJPEBG0AEAVStringBuffer@Common@@@Z; GetUserProfileFolderPathFromSid(ushort const *,ushort const *,Common::StringBuffer &)
0x18002c68d  mov     edi, eax
0x18002c68f  test    eax, eax
0x18002c691  jns     short loc_18002C674
0x18002c693  mov     rcx, [rbp+5Fh]; this
0x18002c697  lea     r8, aOnecoreBaseApp_14; "onecore\\base\\appmodel\\common\\userpr"...
0x18002c69e  mov     r9d, eax; char *
0x18002c6a1  mov     edx, 0A5h; void *
0x18002c6a6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c6ab  jmp     short loc_18002C636
0x18002c6ad  mov     rcx, [rbp+5Fh]; this
0x18002c6b1  lea     r8, aOnecoreBaseApp_14; "onecore\\base\\appmodel\\common\\userpr"...
0x18002c6b8  mov     edx, 0CAh; void *
0x18002c6bd  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
