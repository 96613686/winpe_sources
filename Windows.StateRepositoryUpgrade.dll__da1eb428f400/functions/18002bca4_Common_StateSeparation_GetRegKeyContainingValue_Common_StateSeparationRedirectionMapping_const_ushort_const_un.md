# Common::StateSeparation::GetRegKeyContainingValue(Common::StateSeparationRedirectionMapping const &,ushort const * *,unsigned __int64,ushort const *,ulong,Common::RegistryKey *)

- ea: `0x18002bca4`
- end: `0x18002bf2e`
- name: `?GetRegKeyContainingValue@StateSeparation@Common@@SAJAEBUStateSeparationRedirectionMapping@2@PEAPEBG_KPEBGKPEAVRegistryKey@2@@Z`
- size: `650`
- prototype: `static int(const struct Common::StateSeparationRedirectionMapping *, const unsigned __int16 **, unsigned __int64, const unsigned __int16 *, unsigned int, struct Common::RegistryKey *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800236c4`

## callees

- `0x1800041cc`
- `0x18000a3c0`
- `0x18000d9a4`
- `0x18000f62c`
- `0x18002b6d0`
- `0x18002bb78`
- `0x18002bca4`
- `0x18002c304`
- `0x18002c35c`
- `0x18002d2dc`
- `0x18002d584`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002bdb1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002bdb1`

## string_xrefs

- `0x18002bcd7`: `onecore\base\appmodel\common\stateseparation.cpp`
- `0x18002bd25`: `onecore\base\appmodel\common\stateseparation.cpp`
- `0x18002bd6a`: `onecore\base\appmodel\common\stateseparation.cpp`
- `0x18002be2e`: `onecore\base\appmodel\common\stateseparation.cpp`
- `0x18002bea8`: `onecore\base\appmodel\common\stateseparation.cpp`

## pseudocode

```c
__int64 __fastcall Common::StateSeparation::GetRegKeyContainingValue(
        const struct Common::StateSeparationRedirectionMapping *a1,
        const unsigned __int16 **a2,
        void *a3,
        unsigned __int16 *a4,
        bool a5,
        HKEY *phkResult)
{
  int IsStateSeparationEnabled; // eax
  unsigned __int64 v8; // r8
  unsigned int v9; // ebx
  int PersistedRegKeyPath; // eax
  HKEY v12; // rdx
  void *v13; // rbx
  unsigned int v14; // edi
  int v15; // eax
  unsigned __int64 v16; // r9
  __int64 v17; // rdx
  HKEY v18; // rcx
  LSTATUS Value; // eax
  int v20; // eax
  HKEY v21; // rdi
  HKEY v22; // rcx
  HKEY *v23; // rsi
  __int64 i; // rbx
  int appended; // eax
  int v26; // edi
  int v27; // eax
  int v28; // eax
  unsigned int v29; // ecx
  int lpData; // [rsp+20h] [rbp-30h]
  LPCWSTR lpSubKey[2]; // [rsp+30h] [rbp-20h] BYREF
  int v32; // [rsp+40h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  void *Block; // [rsp+80h] [rbp+30h] BYREF
  HKEY hKey; // [rsp+88h] [rbp+38h] BYREF

  hKey = (HKEY)a4;
  Block = a3;
  a5 = 0;
  IsStateSeparationEnabled = Common::StateSeparation::GetIsStateSeparationEnabled(&a5);
  v9 = IsStateSeparationEnabled;
  if ( IsStateSeparationEnabled < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8A,
      (unsigned int)"onecore\\base\\appmodel\\common\\stateseparation.cpp",
      (const char *)(unsigned int)IsStateSeparationEnabled,
      lpData);
    return v9;
  }
  if ( a5 )
  {
    Block = 0;
    PersistedRegKeyPath = Common::StateSeparation::GetPersistedRegKeyPath(
                            (const struct Common::StateSeparationRedirectionMapping *)&Common::StateSeparation::AppxRoot,
                            a2,
                            v8,
                            (unsigned __int16 **)&Block);
    v13 = Block;
    v14 = PersistedRegKeyPath;
    if ( PersistedRegKeyPath < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x90,
        (unsigned int)"onecore\\base\\appmodel\\common\\stateseparation.cpp",
        (const char *)(unsigned int)PersistedRegKeyPath,
        lpData);
LABEL_26:
      operator delete(v13);
      return v14;
    }
    hKey = 0;
    v15 = Common::RegistryKey::OpenIfExists(
            (Common::RegistryKey *)&hKey,
            v12,
            (const unsigned __int16 *)Block,
            0x20119u);
    v14 = v15;
    if ( v15 < 0 )
    {
      v16 = (unsigned int)v15;
      v17 = 146;
LABEL_9:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v17,
        (unsigned int)"onecore\\base\\appmodel\\common\\stateseparation.cpp",
        (const char *)v16,
        lpData);
      Common::AutoHandleCloseHKEY<HKEY__ *>(hKey);
      goto LABEL_26;
    }
    v18 = hKey;
    if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      Value = RegQueryValueExW(hKey, L"PackageRepositoryRoot", 0, 0, 0, 0);
      v14 = Value;
      if ( !Value || Value == 234 )
      {
        v21 = hKey;
        v22 = 0;
        v23 = phkResult;
        hKey = 0;
        if ( *phkResult != v21 )
        {
          Common::AutoHandleCloseHKEY<HKEY__ *>(*phkResult);
          v22 = hKey;
          *v23 = v21;
        }
        Common::AutoHandleCloseHKEY<HKEY__ *>(v22);
        v14 = 0;
        goto LABEL_26;
      }
      if ( (unsigned int)(Value - 2) > 1 )
      {
        if ( Value > 0 )
          v14 = (unsigned __int16)Value | 0x80070000;
        if ( (v14 & 0x80000000) != 0 )
        {
          v16 = v14;
          v17 = 150;
          goto LABEL_9;
        }
      }
      v18 = hKey;
    }
    Common::AutoHandleCloseHKEY<HKEY__ *>(v18);
    operator delete(v13);
  }
  if ( a2 )
  {
    *(_OWORD *)lpSubKey = 0;
    v32 = 0;
    v20 = Common::StringBuffer::SetValueFromString(
            (Common::StringBuffer *)lpSubKey,
            L"Software\\Microsoft\\Windows\\CurrentVersion\\Appx");
    v9 = v20;
    if ( v20 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA7,
        (unsigned int)"onecore\\base\\appmodel\\common\\stateseparation.cpp",
        (const char *)(unsigned int)v20,
        lpData);
LABEL_35:
      Common::StringBuffer::~StringBuffer((Common::StringBuffer *)lpSubKey);
      return v9;
    }
    for ( i = 0; !i && *a2; i = 1 )
    {
      appended = Common::PathHelpers::AppendPathSegment((struct Common::StringBuffer *)lpSubKey, *a2);
      v26 = appended;
      if ( appended < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xAA,
          (unsigned int)"onecore\\base\\appmodel\\common\\stateseparation.cpp",
          (const char *)(unsigned int)appended,
          lpData);
        v9 = v26;
        goto LABEL_35;
      }
    }
    v27 = Common::RegistryKey::Open(phkResult, HKEY_LOCAL_MACHINE, lpSubKey[1], 0x20119u);
    if ( v27 < 0 )
    {
      v9 = v27;
      goto LABEL_35;
    }
    Common::StringBuffer::~StringBuffer((Common::StringBuffer *)lpSubKey);
    return 0;
  }
  else
  {
    v28 = Common::RegistryKey::Open(
            phkResult,
            HKEY_LOCAL_MACHINE,
            L"Software\\Microsoft\\Windows\\CurrentVersion\\Appx",
            0x20119u);
    v29 = 0;
    if ( v28 < 0 )
      return (unsigned int)v28;
    return v29;
  }
}

```

## disassembly

```asm
0x18002bca4  mov     [rsp-18h+arg_0], rbx
0x18002bca9  mov     [rsp-18h+hKey], r9
0x18002bcae  mov     [rsp-18h+Block], r8
0x18002bcb3  push    rbp
0x18002bcb4  push    rsi
0x18002bcb5  push    rdi
0x18002bcb6  mov     rbp, rsp
0x18002bcb9  sub     rsp, 50h
0x18002bcbd  lea     rcx, [rbp+arg_20]; bool *
0x18002bcc1  mov     [rbp+arg_20], 0
0x18002bcc5  mov     rsi, rdx
0x18002bcc8  call    ?GetIsStateSeparationEnabled@StateSeparation@Common@@SAJPEA_N@Z; Common::StateSeparation::GetIsStateSeparationEnabled(bool *)
0x18002bccd  mov     ebx, eax
0x18002bccf  test    eax, eax
0x18002bcd1  jns     short loc_18002BCF2
0x18002bcd3  mov     rcx, [rbp+18h]; this
0x18002bcd7  lea     r8, aOnecoreBaseApp_26; "onecore\\base\\appmodel\\common\\states"...
0x18002bcde  mov     r9d, eax; char *
0x18002bce1  mov     edx, 8Ah; void *
0x18002bce6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002bceb  mov     eax, ebx
0x18002bced  jmp     loc_18002BF21
0x18002bcf2  cmp     [rbp+arg_20], 0
0x18002bcf6  jz      loc_18002BDFF
0x18002bcfc  lea     r9, [rbp+Block]; unsigned __int16 **
0x18002bd00  mov     [rbp+Block], 0
0x18002bd08  mov     rdx, rsi; unsigned __int16 **
0x18002bd0b  lea     rcx, ?AppxRoot@StateSeparation@Common@@2UStateSeparationRedirectionMapping@2@B; struct Common::StateSeparationRedirectionMapping *
0x18002bd12  call    ?GetPersistedRegKeyPath@StateSeparation@Common@@SAJAEBUStateSeparationRedirectionMapping@2@PEAPEBG_KPEAPEAG@Z; Common::StateSeparation::GetPersistedRegKeyPath(Common::StateSeparationRedirectionMapping const &,ushort const * *,unsigned __int64,ushort * *)
0x18002bd17  mov     rbx, [rbp+Block]
0x18002bd1b  mov     edi, eax
0x18002bd1d  test    eax, eax
0x18002bd1f  jns     short loc_18002BD3E
0x18002bd21  mov     rcx, [rbp+18h]; this
0x18002bd25  lea     r8, aOnecoreBaseApp_26; "onecore\\base\\appmodel\\common\\states"...
0x18002bd2c  mov     r9d, eax; char *
0x18002bd2f  mov     edx, 90h; void *
0x18002bd34  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002bd39  jmp     loc_18002BE70
0x18002bd3e  mov     r9d, 20119h; unsigned int
0x18002bd44  mov     [rbp+hKey], 0
0x18002bd4c  mov     r8, rbx; unsigned __int16 *
0x18002bd4f  lea     rcx, [rbp+hKey]; this
0x18002bd53  call    ?OpenIfExists@RegistryKey@Common@@QEAAJQEAUHKEY__@@PEBGK@Z; Common::RegistryKey::OpenIfExists(HKEY__ * const,ushort const *,ulong)
0x18002bd58  mov     edi, eax
0x18002bd5a  test    eax, eax
0x18002bd5c  jns     short loc_18002BD84
0x18002bd5e  mov     r9d, eax; char *
0x18002bd61  mov     edx, 92h; void *
0x18002bd66  mov     rcx, [rbp+18h]; this
0x18002bd6a  lea     r8, aOnecoreBaseApp_26; "onecore\\base\\appmodel\\common\\states"...
0x18002bd71  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002bd76  mov     rcx, [rbp+hKey]
0x18002bd7a  call    ??$AutoHandleCloseHKEY@PEAUHKEY__@@@Common@@YAXPEAUHKEY__@@@Z; Common::AutoHandleCloseHKEY<HKEY__ *>(HKEY__ *)
0x18002bd7f  jmp     loc_18002BE70
0x18002bd84  mov     rcx, [rbp+hKey]; hKey
0x18002bd88  lea     rax, [rcx-1]
0x18002bd8c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002bd90  ja      short loc_18002BDF2
0x18002bd92  mov     [rsp+50h+lpcbData], 0; lpcbData
0x18002bd9b  lea     rdx, ?appRepositoryPath@StateRepository@@3QBGB; "PackageRepositoryRoot"
0x18002bda2  xor     r9d, r9d; lpType
0x18002bda5  mov     [rsp+50h+lpData], 0; int
0x18002bdae  xor     r8d, r8d; lpReserved
0x18002bdb1  call    cs:__imp_RegQueryValueExW
0x18002bdb7  mov     edi, eax
0x18002bdb9  test    eax, eax
0x18002bdbb  jz      loc_18002BE47
0x18002bdc1  cmp     eax, 0EAh
0x18002bdc6  jz      short loc_18002BE47
0x18002bdc8  lea     ecx, [rax-2]
0x18002bdcb  cmp     ecx, 1
0x18002bdce  jbe     short loc_18002BDEE
0x18002bdd0  test    eax, eax
0x18002bdd2  jle     short loc_18002BDDD
0x18002bdd4  movzx   edi, ax
0x18002bdd7  or      edi, 80070000h
0x18002bddd  test    edi, edi
0x18002bddf  jns     short loc_18002BDEE
0x18002bde1  mov     r9d, edi
0x18002bde4  mov     edx, 96h
0x18002bde9  jmp     loc_18002BD66
0x18002bdee  mov     rcx, [rbp+hKey]
0x18002bdf2  call    ??$AutoHandleCloseHKEY@PEAUHKEY__@@@Common@@YAXPEAUHKEY__@@@Z; Common::AutoHandleCloseHKEY<HKEY__ *>(HKEY__ *)
0x18002bdf7  mov     rcx, rbx; Block
0x18002bdfa  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002bdff  test    rsi, rsi
0x18002be02  jz      loc_18002BEFB
0x18002be08  mov     rdx, cs:off_180030DD8; unsigned __int16 *
0x18002be0f  lea     rcx, [rbp+lpSubKey]; this
0x18002be13  xor     eax, eax
0x18002be15  xorps   xmm0, xmm0
0x18002be18  movups  xmmword ptr [rbp+lpSubKey], xmm0
0x18002be1c  mov     [rbp+var_10], eax
0x18002be1f  call    ?SetValueFromString@StringBuffer@Common@@QEAAJPEBG@Z; Common::StringBuffer::SetValueFromString(ushort const *)
0x18002be24  mov     ebx, eax
0x18002be26  test    eax, eax
0x18002be28  jns     short loc_18002BE7F
0x18002be2a  mov     rcx, [rbp+18h]; this
0x18002be2e  lea     r8, aOnecoreBaseApp_26; "onecore\\base\\appmodel\\common\\states"...
0x18002be35  mov     r9d, eax; char *
0x18002be38  mov     edx, 0A7h; void *
0x18002be3d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002be42  jmp     loc_18002BEE0
0x18002be47  mov     rdi, [rbp+hKey]
0x18002be4b  xor     ecx, ecx
0x18002be4d  mov     rsi, [rbp+phkResult]
0x18002be51  mov     [rbp+hKey], rcx
0x18002be55  cmp     [rsi], rdi
0x18002be58  jz      short loc_18002BE69
0x18002be5a  mov     rcx, [rsi]
0x18002be5d  call    ??$AutoHandleCloseHKEY@PEAUHKEY__@@@Common@@YAXPEAUHKEY__@@@Z; Common::AutoHandleCloseHKEY<HKEY__ *>(HKEY__ *)
0x18002be62  mov     rcx, [rbp+hKey]
0x18002be66  mov     [rsi], rdi
0x18002be69  call    ??$AutoHandleCloseHKEY@PEAUHKEY__@@@Common@@YAXPEAUHKEY__@@@Z; Common::AutoHandleCloseHKEY<HKEY__ *>(HKEY__ *)
0x18002be6e  xor     edi, edi
0x18002be70  mov     rcx, rbx; Block
0x18002be73  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002be78  mov     eax, edi
0x18002be7a  jmp     loc_18002BF21
0x18002be7f  xor     ebx, ebx
0x18002be81  cmp     rbx, 1
0x18002be85  jnb     short loc_18002BEC0
0x18002be87  mov     rdx, [rsi+rbx*8]; unsigned __int16 *
0x18002be8b  test    rdx, rdx
0x18002be8e  jz      short loc_18002BEC0
0x18002be90  lea     rcx, [rbp+lpSubKey]; struct Common::StringBuffer *
0x18002be94  call    ?AppendPathSegment@PathHelpers@Common@@SAJPEAVStringBuffer@2@PEBG@Z; Common::PathHelpers::AppendPathSegment(Common::StringBuffer *,ushort const *)
0x18002be99  mov     edi, eax
0x18002be9b  test    eax, eax
0x18002be9d  js      short loc_18002BEA4
0x18002be9f  inc     rbx
0x18002bea2  jmp     short loc_18002BE81
0x18002bea4  mov     rcx, [rbp+18h]; this
0x18002bea8  lea     r8, aOnecoreBaseApp_26; "onecore\\base\\appmodel\\common\\states"...
0x18002beaf  mov     r9d, edi; char *
0x18002beb2  mov     edx, 0AAh; void *
0x18002beb7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002bebc  mov     ebx, edi
0x18002bebe  jmp     short loc_18002BEE0
0x18002bec0  mov     r8, [rbp+lpSubKey+8]; lpSubKey
0x18002bec4  mov     r9d, 20119h; samDesired
0x18002beca  mov     rcx, [rbp+phkResult]; phkResult
0x18002bece  mov     rdx, 0FFFFFFFF80000002h; hKey
0x18002bed5  call    ?Open@RegistryKey@Common@@QEAAJQEAUHKEY__@@PEBGK@Z; Common::RegistryKey::Open(HKEY__ * const,ushort const *,ulong)
0x18002beda  test    eax, eax
0x18002bedc  jns     short loc_18002BEEE
0x18002bede  mov     ebx, eax
0x18002bee0  lea     rcx, [rbp+lpSubKey]; this
0x18002bee4  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x18002bee9  jmp     loc_18002BCEB
0x18002beee  lea     rcx, [rbp+lpSubKey]; this
0x18002bef2  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x18002bef7  xor     eax, eax
0x18002bef9  jmp     short loc_18002BF21
0x18002befb  mov     r8, cs:off_180030DD8; lpSubKey
0x18002bf02  mov     r9d, 20119h; samDesired
0x18002bf08  mov     rcx, [rbp+phkResult]; phkResult
0x18002bf0c  mov     rdx, 0FFFFFFFF80000002h; hKey
0x18002bf13  call    ?Open@RegistryKey@Common@@QEAAJQEAUHKEY__@@PEBGK@Z; Common::RegistryKey::Open(HKEY__ * const,ushort const *,ulong)
0x18002bf18  xor     ecx, ecx
0x18002bf1a  test    eax, eax
0x18002bf1c  cmovs   ecx, eax
0x18002bf1f  mov     eax, ecx
0x18002bf21  mov     rbx, [rsp+50h+arg_0]
0x18002bf26  add     rsp, 50h
0x18002bf2a  pop     rdi
0x18002bf2b  pop     rsi
0x18002bf2c  pop     rbp
0x18002bf2d  retn
```
