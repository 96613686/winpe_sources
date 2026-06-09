# AppxAllUserStore::Internal::ResetLanguageOverlaySetupPhaseIfPresent(AppxAllUserStore::BasicLogFile &,Common::RegistryKey &,Common::StringBuffer &)

- ea: `0x180017330`
- end: `0x1800175bd`
- name: `?ResetLanguageOverlaySetupPhaseIfPresent@Internal@AppxAllUserStore@@YAJAEAVBasicLogFile@2@AEAVRegistryKey@Common@@AEAVStringBuffer@5@@Z`
- size: `653`
- prototype: `__int64 __fastcall(AppxAllUserStore::Internal *__hidden this, struct AppxAllUserStore::BasicLogFile *, struct Common::RegistryKey *, struct Common::StringBuffer *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180035bc8`

## callees

- `0x1800036d4`
- `0x180004968`
- `0x18000ce40`
- `0x18000d6a0`
- `0x180017330`
- `0x180017cd0`
- `0x180017f50`
- `0x180018248`
- `0x18001b8d0`
- `0x18004c98a`
- `0x18004c9d0`

## import_xrefs

- `msvcrt!wcsstr` at `0x180017461`
- `msvcrt!wcsstr` at `0x180017461`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180017447`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180017447`

## string_xrefs

- `0x180017381`: `Open %ls failed, 0x%0x.`
- `0x1800174d7`: `Updated SetupPhase to PreOOBE | PreRoaming for %ls.`
- `0x180017528`: `Failed to open LanguageOverlayPackage subkey, 0x%0x.`
- `0x180017512`: `Failed to update SetupPhase, 0x%0x.`

## pseudocode

```c
__int64 __fastcall AppxAllUserStore::Internal::ResetLanguageOverlaySetupPhaseIfPresent(
        AppxAllUserStore::Internal *this,
        HKEY *a2,
        struct Common::RegistryKey *a3,
        struct Common::StringBuffer *a4)
{
  HKEY v4; // rdx
  const WCHAR *v6; // r8
  LSTATUS v8; // eax
  unsigned int v9; // edi
  int v10; // eax
  __int64 v11; // rcx
  DWORD i; // esi
  int v13; // eax
  LSTATUS v14; // eax
  LSTATUS v15; // eax
  int v16; // eax
  int v17; // eax
  unsigned int v18; // esi
  int lpReserved; // [rsp+20h] [rbp-E0h]
  int lpReserveda; // [rsp+20h] [rbp-E0h]
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  HKEY v23; // [rsp+48h] [rbp-B8h] BYREF
  DWORD cchName; // [rsp+50h] [rbp-B0h] BYREF
  int v25; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR Name[128]; // [rsp+60h] [rbp-A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+98h]

  v4 = *a2;
  v6 = (const WCHAR *)*((_QWORD *)a3 + 1);
  hKey = 0;
  v8 = Common::RegistryKey::Open(&hKey, v4, v6, 0xF003Fu);
  v9 = v8;
  if ( v8 >= 0 )
  {
    for ( i = 0; ; ++i )
    {
      memset_0(Name, 0, sizeof(Name));
      cchName = 128;
      v13 = RegEnumKeyExW(hKey, i, Name, &cchName, 0, 0, 0, 0);
      if ( v13 )
        break;
      if ( wcsstr(Name, L"Microsoft.LanguageExperiencePack") )
      {
        v23 = 0;
        v14 = Common::RegistryKey::OpenSubKey(&hKey, Name, 0xF003Fu, &v23);
        v9 = v14;
        if ( v14 < 0 )
        {
          v17 = AppxAllUserStore::BasicLogFile::WriteMsg(
                  this,
                  L"Failed to open LanguageOverlayPackage subkey, 0x%0x.",
                  (unsigned int)v14);
          v18 = 1817;
          goto LABEL_18;
        }
        v25 = 33;
        v15 = Common::RegistryKey::SetValue(&v23, L"SetupPhase", (const BYTE *)&v25, 4u, 4u);
        v9 = v15;
        if ( v15 < 0 )
        {
          v17 = AppxAllUserStore::BasicLogFile::WriteMsg(
                  this,
                  L"Failed to update SetupPhase, 0x%0x.",
                  (unsigned int)v15);
          v18 = 1819;
LABEL_18:
          if ( v17 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)v18,
              (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
              (const char *)(unsigned int)v17);
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v18,
            (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
            (const char *)v9,
            lpReserveda);
          Common::RegistryKey::~RegistryKey(&v23);
          goto LABEL_25;
        }
        v16 = AppxAllUserStore::BasicLogFile::WriteMsg(
                this,
                L"Updated SetupPhase to PreOOBE | PreRoaming for %ls.",
                Name);
        if ( v16 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x71D,
            (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
            (const char *)(unsigned int)v16);
        Common::RegistryKey::~RegistryKey(&v23);
      }
    }
    if ( v13 == 259 )
    {
      Common::RegistryKey::~RegistryKey(&hKey);
      return 0;
    }
    if ( v13 > 0 )
      v13 = (unsigned __int16)v13 | 0x80070000;
    v9 = v13;
  }
  else
  {
    v10 = AppxAllUserStore::BasicLogFile::WriteMsg(
            this,
            L"Open %ls failed, 0x%0x.",
            *((_QWORD *)a3 + 1),
            (unsigned int)v8);
    if ( v10 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x6FD,
        (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
        (const char *)(unsigned int)v10);
    if ( Microsoft_Windows_AppXDeployment_ServerEnableBits < 0 )
      McTemplateU0zd_EventWriteTransfer(v11, AppxAllUserStoreOpenKeyError, *((_QWORD *)a3 + 1), v9);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6FD,
      (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
      (const char *)v9,
      lpReserved);
  }
LABEL_25:
  Common::RegistryKey::~RegistryKey(&hKey);
  return v9;
}

```

## disassembly

```asm
0x180017330  push    rbp
0x180017332  push    rbx
0x180017333  push    rsi
0x180017334  push    rdi
0x180017335  push    r14
0x180017337  lea     rbp, [rsp-70h]
0x18001733c  sub     rsp, 170h
0x180017343  mov     rax, cs:__security_cookie
0x18001734a  xor     rax, rsp
0x18001734d  mov     [rbp+90h+var_30], rax
0x180017351  mov     rdx, [rdx]; hKey
0x180017354  mov     rsi, r8
0x180017357  mov     r8, [r8+8]; lpSubKey
0x18001735b  mov     r14, rcx
0x18001735e  lea     rcx, [rsp+190h+hKey]; phkResult
0x180017363  mov     [rsp+190h+hKey], 0
0x18001736c  mov     r9d, 0F003Fh; samDesired
0x180017372  call    ?Open@RegistryKey@Common@@QEAAJQEAUHKEY__@@PEBGK@Z; Common::RegistryKey::Open(HKEY__ * const,ushort const *,ulong)
0x180017377  mov     edi, eax
0x180017379  test    eax, eax
0x18001737b  jns     short loc_1800173EF
0x18001737d  mov     r8, [rsi+8]
0x180017381  lea     rdx, aOpenLsFailed0x; "Open %ls failed, 0x%0x."
0x180017388  mov     r9d, eax
0x18001738b  mov     rcx, r14; this
0x18001738e  call    ?WriteMsg@BasicLogFile@AppxAllUserStore@@QEAAJPEBGZZ; AppxAllUserStore::BasicLogFile::WriteMsg(ushort const *,...)
0x180017393  lea     rbx, aOnecoreAdminAp_10; "onecore\\admin\\appmodel\\appxalluserst"...
0x18001739a  mov     r14d, 6FDh
0x1800173a0  test    eax, eax
0x1800173a2  jns     short loc_1800173B9
0x1800173a4  mov     rcx, [rbp+98h]; this
0x1800173ab  mov     r9d, eax; char *
0x1800173ae  mov     r8, rbx; unsigned int
0x1800173b1  mov     edx, r14d; void *
0x1800173b4  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800173b9  cmp     cs:Microsoft_Windows_AppXDeployment_ServerEnableBits, 0
0x1800173c0  jge     short loc_1800173D5
0x1800173c2  mov     r8, [rsi+8]
0x1800173c6  lea     rdx, AppxAllUserStoreOpenKeyError
0x1800173cd  mov     r9d, edi
0x1800173d0  call    McTemplateU0zd_EventWriteTransfer
0x1800173d5  mov     rcx, [rbp+98h]; this
0x1800173dc  mov     r9d, edi; char *
0x1800173df  mov     r8, rbx; unsigned int
0x1800173e2  mov     edx, r14d; void *
0x1800173e5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800173ea  jmp     loc_180017589
0x1800173ef  xor     esi, esi
0x1800173f1  lea     rbx, aOnecoreAdminAp_10; "onecore\\admin\\appmodel\\appxalluserst"...
0x1800173f8  xor     edx, edx; Val
0x1800173fa  lea     rcx, [rsp+190h+Name]; void *
0x1800173ff  mov     r8d, 100h; Size
0x180017405  call    memset_0
0x18001740a  mov     rcx, [rsp+190h+hKey]; hKey
0x18001740f  lea     r9, [rsp+190h+cchName]; lpcchName
0x180017414  mov     [rsp+190h+lpftLastWriteTime], 0; lpftLastWriteTime
0x18001741d  lea     r8, [rsp+190h+Name]; lpName
0x180017422  mov     [rsp+190h+lpcchClass], 0; lpcchClass
0x18001742b  mov     edx, esi; dwIndex
0x18001742d  mov     [rsp+190h+lpClass], 0; lpClass
0x180017436  mov     [rsp+190h+lpReserved], 0; int
0x18001743f  mov     [rsp+190h+cchName], 80h
0x180017447  call    cs:__imp_RegEnumKeyExW
0x18001744d  test    eax, eax
0x18001744f  jnz     loc_180017574
0x180017455  lea     rdx, aMicrosoftLangu; "Microsoft.LanguageExperiencePack"
0x18001745c  lea     rcx, [rsp+190h+Name]; Str
0x180017461  call    cs:__imp_wcsstr
0x180017467  test    rax, rax
0x18001746a  jz      loc_180017508
0x180017470  lea     r9, [rsp+190h+var_148]; struct Common::AutoHandleHKEY *
0x180017475  mov     [rsp+190h+var_148], 0
0x18001747e  mov     r8d, 0F003Fh; unsigned int
0x180017484  lea     rdx, [rsp+190h+Name]; unsigned __int16 *
0x180017489  lea     rcx, [rsp+190h+hKey]; this
0x18001748e  call    ?OpenSubKey@RegistryKey@Common@@QEAAJPEBGKAEAVAutoHandleHKEY@2@@Z; Common::RegistryKey::OpenSubKey(ushort const *,ulong,Common::AutoHandleHKEY &)
0x180017493  mov     edi, eax
0x180017495  test    eax, eax
0x180017497  js      loc_180017525
0x18001749d  mov     r9d, 4; unsigned int
0x1800174a3  mov     [rsp+190h+var_138], 21h ; '!'
0x1800174ab  lea     r8, [rsp+190h+var_138]; void *
0x1800174b0  mov     dword ptr [rsp+190h+lpReserved], 4; int
0x1800174b8  lea     rdx, aSetupphase; "SetupPhase"
0x1800174bf  lea     rcx, [rsp+190h+var_148]; this
0x1800174c4  call    ?SetValue@RegistryKey@Common@@QEAAJPEBGPEBXKK@Z; Common::RegistryKey::SetValue(ushort const *,void const *,ulong,ulong)
0x1800174c9  mov     edi, eax
0x1800174cb  mov     rcx, r14; this
0x1800174ce  test    eax, eax
0x1800174d0  js      short loc_18001750F
0x1800174d2  lea     r8, [rsp+190h+Name]
0x1800174d7  lea     rdx, aUpdatedSetupph; "Updated SetupPhase to PreOOBE | PreRoam"...
0x1800174de  call    ?WriteMsg@BasicLogFile@AppxAllUserStore@@QEAAJPEBGZZ; AppxAllUserStore::BasicLogFile::WriteMsg(ushort const *,...)
0x1800174e3  test    eax, eax
0x1800174e5  jns     short loc_1800174FE
0x1800174e7  mov     rcx, [rbp+98h]; this
0x1800174ee  mov     r9d, eax; char *
0x1800174f1  mov     r8, rbx; unsigned int
0x1800174f4  mov     edx, 71Dh; void *
0x1800174f9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800174fe  lea     rcx, [rsp+190h+var_148]; this
0x180017503  call    ??1RegistryKey@Common@@QEAA@XZ; Common::RegistryKey::~RegistryKey(void)
0x180017508  inc     esi
0x18001750a  jmp     loc_1800173F8
0x18001750f  mov     r8d, edi
0x180017512  lea     rdx, aFailedToUpdate; "Failed to update SetupPhase, 0x%0x."
0x180017519  call    ?WriteMsg@BasicLogFile@AppxAllUserStore@@QEAAJPEBGZZ; AppxAllUserStore::BasicLogFile::WriteMsg(ushort const *,...)
0x18001751e  mov     esi, 71Bh
0x180017523  jmp     short loc_18001753C
0x180017525  mov     r8d, edi
0x180017528  lea     rdx, aFailedToOpenLa; "Failed to open LanguageOverlayPackage s"...
0x18001752f  mov     rcx, r14; this
0x180017532  call    ?WriteMsg@BasicLogFile@AppxAllUserStore@@QEAAJPEBGZZ; AppxAllUserStore::BasicLogFile::WriteMsg(ushort const *,...)
0x180017537  mov     esi, 719h
0x18001753c  test    eax, eax
0x18001753e  jns     short loc_180017554
0x180017540  mov     rcx, [rbp+98h]; this
0x180017547  mov     r9d, eax; char *
0x18001754a  mov     r8, rbx; unsigned int
0x18001754d  mov     edx, esi; void *
0x18001754f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180017554  mov     rcx, [rbp+98h]; this
0x18001755b  mov     r9d, edi; char *
0x18001755e  mov     r8, rbx; unsigned int
0x180017561  mov     edx, esi; void *
0x180017563  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017568  lea     rcx, [rsp+190h+var_148]; this
0x18001756d  call    ??1RegistryKey@Common@@QEAA@XZ; Common::RegistryKey::~RegistryKey(void)
0x180017572  jmp     short loc_180017589
0x180017574  cmp     eax, 103h
0x180017579  jz      short loc_180017597
0x18001757b  test    eax, eax
0x18001757d  jle     short loc_180017587
0x18001757f  movzx   eax, ax
0x180017582  or      eax, 80070000h
0x180017587  mov     edi, eax
0x180017589  lea     rcx, [rsp+190h+hKey]; this
0x18001758e  call    ??1RegistryKey@Common@@QEAA@XZ; Common::RegistryKey::~RegistryKey(void)
0x180017593  mov     eax, edi
0x180017595  jmp     short loc_1800175A3
0x180017597  lea     rcx, [rsp+190h+hKey]; this
0x18001759c  call    ??1RegistryKey@Common@@QEAA@XZ; Common::RegistryKey::~RegistryKey(void)
0x1800175a1  xor     eax, eax
0x1800175a3  mov     rcx, [rbp+90h+var_30]
0x1800175a7  xor     rcx, rsp; StackCookie
0x1800175aa  call    __security_check_cookie
0x1800175af  add     rsp, 170h
0x1800175b6  pop     r14
0x1800175b8  pop     rdi
0x1800175b9  pop     rsi
0x1800175ba  pop     rbx
0x1800175bb  pop     rbp
0x1800175bc  retn
```
