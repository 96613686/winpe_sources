# AppxAllUserStore::Internal::LoadSoftwareHiveAndOpenKeyForSystemRoot(AppxAllUserStore::BasicLogFile &,ushort const *,ushort const *,ulong,AppxAllUserStore::AutoRegLoadHive &,Common::RegistryKey &)

- ea: `0x1800334f4`
- end: `0x180033762`
- name: `?LoadSoftwareHiveAndOpenKeyForSystemRoot@Internal@AppxAllUserStore@@YAJAEAVBasicLogFile@2@PEBG1KAEAVAutoRegLoadHive@2@AEAVRegistryKey@Common@@@Z`
- size: `622`
- prototype: `__int64 __fastcall(AppxAllUserStore::Internal *__hidden this, struct AppxAllUserStore::BasicLogFile *, LPCWSTR lpSubKey, REGSAM samDesired, unsigned int, PHKEY phkResult, struct Common::RegistryKey *)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800175c4`
- `0x180035bc8`

## callees

- `0x1800036d4`
- `0x180004920`
- `0x18000d6a0`
- `0x18000ed34`
- `0x180017cd0`
- `0x180017f50`
- `0x180018248`
- `0x18001a6a0`
- `0x1800334f4`
- `0x1800340d8`
- `0x18004682c`

## string_xrefs

- `0x180033513`: `In LoadSoftwareHiveAndOpenKeyForSystemRoot %ls %ls.`
- `0x180033576`: `Online open failed, 0x%0x.`
- `0x180033654`: `Hive path %ls, alias %ls.`
- `0x1800336dd`: `Offline open failed, 0x%0x.`
- `0x1800335ec`: `Windows\System32\Config\Software`

## pseudocode

```c
__int64 __fastcall AppxAllUserStore::Internal::LoadSoftwareHiveAndOpenKeyForSystemRoot(
        AppxAllUserStore::Internal *this,
        struct AppxAllUserStore::BasicLogFile *a2,
        LPCWSTR lpSubKey,
        REGSAM samDesired,
        AppxAllUserStore::AutoRegLoadHive *a5,
        PHKEY phkResult)
{
  int v10; // eax
  LSTATUS v11; // eax
  __int64 v12; // rbx
  int v13; // eax
  __int64 v14; // rcx
  HKEY v16; // rdx
  const char *v17; // rbx
  unsigned int Hive; // eax
  int v19; // eax
  __int64 v20; // rdx
  LSTATUS v21; // eax
  int v22; // eax
  __int64 v23; // rcx
  int v24; // [rsp+20h] [rbp-78h]
  int v25; // [rsp+20h] [rbp-78h]
  char *v26[2]; // [rsp+40h] [rbp-58h] BYREF
  int v27; // [rsp+50h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  v10 = AppxAllUserStore::BasicLogFile::WriteMsg(
          this,
          L"In LoadSoftwareHiveAndOpenKeyForSystemRoot %ls %ls.",
          a2,
          lpSubKey);
  if ( v10 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x621,
      (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
      (const char *)(unsigned int)v10);
  if ( a2 )
  {
    v27 = 0;
    *(_OWORD *)v26 = 0;
    LODWORD(v12) = Common::PathHelpers::CombinePaths(
                     (const unsigned __int16 *)a2,
                     L"Windows\\System32\\Config\\Software",
                     (struct Common::StringBuffer *)v26);
    if ( (int)v12 >= 0 )
    {
      v17 = v26[1];
      Hive = AppxAllUserStore::AutoRegLoadHive::RegLoadHive(a5, v16, lpSubKey, (const unsigned __int16 *)v26[1]);
      v12 = (unsigned int)wil::details::in1diag3::Log_IfFailedMsg(
                            retaddr,
                            (void *)0x633,
                            (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
                            (const char *)Hive,
                            (__int64)"Hive path %ls, alias %ls.",
                            v17);
      v19 = AppxAllUserStore::BasicLogFile::WriteMsg(this, L"RegLoadHive %ls, 0x%0x.", v26[1], v12);
      if ( v19 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x634,
          (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
          (const char *)(unsigned int)v19);
      if ( (int)v12 >= 0 )
      {
        v21 = Common::RegistryKey::Open(phkResult, HKEY_LOCAL_MACHINE, lpSubKey, samDesired);
        LODWORD(v12) = v21;
        if ( v21 >= 0 )
        {
          Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v26);
          return 0;
        }
        v22 = AppxAllUserStore::BasicLogFile::WriteMsg(this, L"Offline open failed, 0x%0x.", (unsigned int)v21);
        if ( v22 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x638,
            (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
            (const char *)(unsigned int)v22);
        if ( Microsoft_Windows_AppXDeployment_ServerEnableBits < 0 )
          McTemplateU0zd_EventWriteTransfer(v23, AppxAllUserStoreOpenKeyError, lpSubKey, (unsigned int)v12);
        v20 = 1592;
      }
      else
      {
        v20 = 1589;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v20,
        (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
        (const char *)(unsigned int)v12,
        v25);
    }
    else
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x62F,
        (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
        (const char *)(unsigned int)v12,
        (int)"System root %ls.",
        (const char *)a2);
    }
    Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v26);
    return (unsigned int)v12;
  }
  v11 = Common::RegistryKey::Open(phkResult, HKEY_LOCAL_MACHINE, L"Software", samDesired);
  LODWORD(v12) = v11;
  if ( v11 < 0 )
  {
    v13 = AppxAllUserStore::BasicLogFile::WriteMsg(this, L"Online open failed, 0x%0x.", (unsigned int)v11);
    if ( v13 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x629,
        (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
        (const char *)(unsigned int)v13);
    if ( Microsoft_Windows_AppXDeployment_ServerEnableBits < 0 )
      McTemplateU0zd_EventWriteTransfer(v14, AppxAllUserStoreOpenKeyError, L"Software", (unsigned int)v12);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x629,
      (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
      (const char *)(unsigned int)v12,
      v24);
    return (unsigned int)v12;
  }
  return 0;
}

```

## disassembly

```asm
0x1800334f4  push    rbx
0x1800334f6  push    rbp
0x1800334f7  push    rsi
0x1800334f8  push    rdi
0x1800334f9  push    r12
0x1800334fb  push    r14
0x1800334fd  sub     rsp, 68h
0x180033501  mov     r14d, r9d
0x180033504  mov     rsi, r8
0x180033507  mov     r9, r8
0x18003350a  mov     rdi, rdx
0x18003350d  mov     r8, rdx
0x180033510  mov     rbp, rcx
0x180033513  lea     rdx, aInLoadsoftware; "In LoadSoftwareHiveAndOpenKeyForSystemR"...
0x18003351a  call    ?WriteMsg@BasicLogFile@AppxAllUserStore@@QEAAJPEBGZZ; AppxAllUserStore::BasicLogFile::WriteMsg(ushort const *,...)
0x18003351f  lea     r12, aOnecoreAdminAp_10; "onecore\\admin\\appmodel\\appxalluserst"...
0x180033526  test    eax, eax
0x180033528  jns     short loc_180033542
0x18003352a  mov     rcx, [rsp+98h]; this
0x180033532  mov     r9d, eax; char *
0x180033535  mov     r8, r12; unsigned int
0x180033538  mov     edx, 621h; void *
0x18003353d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180033542  test    rdi, rdi
0x180033545  jnz     loc_1800335DE
0x18003354b  mov     rcx, [rsp+98h+phkResult]; phkResult
0x180033553  lea     r8, aSoftware_0; "Software"
0x18003355a  mov     r9d, r14d; samDesired
0x18003355d  mov     rdx, 0FFFFFFFF80000002h; hKey
0x180033564  call    ?Open@RegistryKey@Common@@QEAAJQEAUHKEY__@@PEBGK@Z; Common::RegistryKey::Open(HKEY__ * const,ushort const *,ulong)
0x180033569  mov     ebx, eax
0x18003356b  test    eax, eax
0x18003356d  jns     loc_180033753
0x180033573  mov     r8d, eax
0x180033576  lea     rdx, aOnlineOpenFail; "Online open failed, 0x%0x."
0x18003357d  mov     rcx, rbp; this
0x180033580  call    ?WriteMsg@BasicLogFile@AppxAllUserStore@@QEAAJPEBGZZ; AppxAllUserStore::BasicLogFile::WriteMsg(ushort const *,...)
0x180033585  mov     edi, 629h
0x18003358a  test    eax, eax
0x18003358c  jns     short loc_1800335A3
0x18003358e  mov     rcx, [rsp+98h]; this
0x180033596  mov     r9d, eax; char *
0x180033599  mov     r8, r12; unsigned int
0x18003359c  mov     edx, edi; void *
0x18003359e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800335a3  cmp     cs:Microsoft_Windows_AppXDeployment_ServerEnableBits, 0
0x1800335aa  jge     short loc_1800335C2
0x1800335ac  mov     r9d, ebx
0x1800335af  lea     r8, aSoftware_0; "Software"
0x1800335b6  lea     rdx, AppxAllUserStoreOpenKeyError
0x1800335bd  call    McTemplateU0zd_EventWriteTransfer
0x1800335c2  mov     rcx, [rsp+98h]; this
0x1800335ca  mov     r9d, ebx; char *
0x1800335cd  mov     r8, r12; unsigned int
0x1800335d0  mov     edx, edi; void *
0x1800335d2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800335d7  mov     eax, ebx
0x1800335d9  jmp     loc_180033755
0x1800335de  xor     eax, eax
0x1800335e0  lea     r8, [rsp+98h+var_58]; this
0x1800335e5  xorps   xmm0, xmm0
0x1800335e8  mov     [rsp+98h+var_48], eax
0x1800335ec  lea     rdx, aWindowsSystem3; "Windows\\System32\\Config\\Software"
0x1800335f3  mov     rcx, rdi; Src
0x1800335f6  movups  xmmword ptr [rsp+98h+var_58], xmm0
0x1800335fb  call    ?CombinePaths@PathHelpers@Common@@SAJPEBG0PEAVStringBuffer@2@@Z; Common::PathHelpers::CombinePaths(ushort const *,ushort const *,Common::StringBuffer *)
0x180033600  mov     ebx, eax
0x180033602  test    eax, eax
0x180033604  jns     short loc_180033634
0x180033606  mov     rcx, [rsp+98h]; this
0x18003360e  lea     rax, aSystemRootLs_0; "System root %ls."
0x180033615  mov     [rsp+98h+var_70], rdi; char *
0x18003361a  mov     r9d, ebx; char *
0x18003361d  mov     r8, r12; unsigned int
0x180033620  mov     [rsp+98h+var_78], rax; int
0x180033625  mov     edx, 62Fh; void *
0x18003362a  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18003362f  jmp     loc_18003373A
0x180033634  mov     rbx, [rsp+98h+var_58+8]
0x180033639  mov     r8, rsi; unsigned __int16 *
0x18003363c  mov     rcx, [rsp+98h+arg_20]; this
0x180033644  mov     r9, rbx; unsigned __int16 *
0x180033647  call    ?RegLoadHive@AutoRegLoadHive@AppxAllUserStore@@QEAAJQEAUHKEY__@@PEBG1@Z; AppxAllUserStore::AutoRegLoadHive::RegLoadHive(HKEY__ * const,ushort const *,ushort const *)
0x18003364c  mov     rcx, [rsp+98h]; this
0x180033654  lea     rdx, aHivePathLsAlia; "Hive path %ls, alias %ls."
0x18003365b  mov     [rsp+98h+var_68], rsi
0x180033660  mov     r9d, eax; char *
0x180033663  mov     [rsp+98h+var_70], rbx; char *
0x180033668  mov     r8, r12; unsigned int
0x18003366b  mov     [rsp+98h+var_78], rdx; int
0x180033670  mov     edx, 633h; void *
0x180033675  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18003367a  mov     r8, [rsp+98h+var_58+8]
0x18003367f  lea     rdx, aRegloadhiveLs0; "RegLoadHive %ls, 0x%0x."
0x180033686  mov     r9d, eax
0x180033689  mov     rcx, rbp; this
0x18003368c  mov     ebx, eax
0x18003368e  call    ?WriteMsg@BasicLogFile@AppxAllUserStore@@QEAAJPEBGZZ; AppxAllUserStore::BasicLogFile::WriteMsg(ushort const *,...)
0x180033693  test    eax, eax
0x180033695  jns     short loc_1800336AF
0x180033697  mov     rcx, [rsp+98h]; this
0x18003369f  mov     r9d, eax; char *
0x1800336a2  mov     r8, r12; unsigned int
0x1800336a5  mov     edx, 634h; void *
0x1800336aa  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800336af  test    ebx, ebx
0x1800336b1  jns     short loc_1800336BA
0x1800336b3  mov     edx, 635h
0x1800336b8  jmp     short loc_180033727
0x1800336ba  mov     rcx, [rsp+98h+phkResult]; phkResult
0x1800336c2  mov     r9d, r14d; samDesired
0x1800336c5  mov     r8, rsi; lpSubKey
0x1800336c8  mov     rdx, 0FFFFFFFF80000002h; hKey
0x1800336cf  call    ?Open@RegistryKey@Common@@QEAAJQEAUHKEY__@@PEBGK@Z; Common::RegistryKey::Open(HKEY__ * const,ushort const *,ulong)
0x1800336d4  mov     ebx, eax
0x1800336d6  test    eax, eax
0x1800336d8  jns     short loc_180033749
0x1800336da  mov     r8d, eax
0x1800336dd  lea     rdx, aOfflineOpenFai; "Offline open failed, 0x%0x."
0x1800336e4  mov     rcx, rbp; this
0x1800336e7  call    ?WriteMsg@BasicLogFile@AppxAllUserStore@@QEAAJPEBGZZ; AppxAllUserStore::BasicLogFile::WriteMsg(ushort const *,...)
0x1800336ec  mov     edi, 638h
0x1800336f1  test    eax, eax
0x1800336f3  jns     short loc_18003370A
0x1800336f5  mov     rcx, [rsp+98h]; this
0x1800336fd  mov     r9d, eax; char *
0x180033700  mov     r8, r12; unsigned int
0x180033703  mov     edx, edi; void *
0x180033705  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003370a  cmp     cs:Microsoft_Windows_AppXDeployment_ServerEnableBits, 0
0x180033711  jge     short loc_180033725
0x180033713  mov     r9d, ebx
0x180033716  lea     rdx, AppxAllUserStoreOpenKeyError
0x18003371d  mov     r8, rsi
0x180033720  call    McTemplateU0zd_EventWriteTransfer
0x180033725  mov     edx, edi; void *
0x180033727  mov     rcx, [rsp+98h]; this
0x18003372f  mov     r9d, ebx; char *
0x180033732  mov     r8, r12; unsigned int
0x180033735  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003373a  lea     rcx, [rsp+98h+var_58]; this
0x18003373f  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x180033744  jmp     loc_1800335D7
0x180033749  lea     rcx, [rsp+98h+var_58]; this
0x18003374e  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x180033753  xor     eax, eax
0x180033755  add     rsp, 68h
0x180033759  pop     r14
0x18003375b  pop     r12
0x18003375d  pop     rdi
0x18003375e  pop     rsi
0x18003375f  pop     rbp
0x180033760  pop     rbx
0x180033761  retn
```
