# Windows::Compat::Appraiser::Utilities::GetCredentialsForBasicProxyIfPresent(ushort const *,ushort *,unsigned __int64,ushort *,unsigned __int64)

- ea: `0x180089b2c`
- end: `0x180089e26`
- name: `?GetCredentialsForBasicProxyIfPresent@Utilities@Appraiser@Compat@Windows@@SAJPEBGPEAG_K12@Z`
- size: `762`
- prototype: `__int64 __fastcall(char *, unsigned __int16 *, unsigned __int64, unsigned __int16 *, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180092f40`

## callees

- `0x180011d20`
- `0x18001a2f4`
- `0x18002ebb8`
- `0x1800301d0`
- `0x18006a45c`
- `0x180089b2c`
- `0x1800a5d88`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180089b70`
- `KERNEL32!GetLastError` at `0x180089b85`
- `KERNEL32!GetLastError` at `0x180089bd8`
- `KERNEL32!GetLastError` at `0x180089c04`
- `KERNEL32!GetLastError` at `0x180089d5d`
- `KERNEL32!GetLastError` at `0x180089db0`
- `KERNEL32!GetLastError` at `0x180089dcb`
- `KERNEL32!GetLastError` at `0x180089b70`
- `KERNEL32!GetLastError` at `0x180089b85`
- `KERNEL32!GetLastError` at `0x180089bd8`
- `KERNEL32!GetLastError` at `0x180089c04`
- `KERNEL32!GetLastError` at `0x180089d5d`
- `KERNEL32!GetLastError` at `0x180089db0`
- `KERNEL32!GetLastError` at `0x180089dcb`
- `ADVAPI32!CredFree` at `0x180089e0b`
- `ADVAPI32!CredFree` at `0x180089e0b`
- `ADVAPI32!CredReadW` at `0x180089b62`
- `ADVAPI32!CredReadW` at `0x180089b62`

## string_xrefs

- `0x180089cfb`: `Failed to copy string: [0x%x]`
- `0x180089d19`: `Failed to copy string: [0x%x].`
- `0x180089d32`: `Failed to copy string: [0x%x].`
- `0x180089c8b`: `onecore\base\appcompat\appraiser\helpers\utilities.cpp`
- `0x180089cc8`: `onecore\base\appcompat\appraiser\helpers\utilities.cpp`
- `0x180089d40`: `onecore\base\appcompat\appraiser\helpers\utilities.cpp`
- `0x180089df5`: `onecore\base\appcompat\appraiser\helpers\utilities.cpp`
- `0x180089b8b`: `Windows::Compat::Appraiser::Utilities::GetCredentialsForBasicProxyIfPresent`
- `0x180089c50`: `Windows::Compat::Appraiser::Utilities::GetCredentialsForBasicProxyIfPresent`
- `0x180089d63`: `Windows::Compat::Appraiser::Utilities::GetCredentialsForBasicProxyIfPresent`
- `0x180089c5d`: `Failed to copy credential blob: [0x%x]`
- `0x180089c7b`: `Failed to copy credential blob: [0x%x].`
- `0x180089cba`: `Failed to copy credential blob: [0x%x].`

## pseudocode

```c
__int64 __fastcall Windows::Compat::Appraiser::Utilities::GetCredentialsForBasicProxyIfPresent(
        const wchar_t *a1,
        unsigned __int16 *a2,
        __int64 a3,
        unsigned __int16 *a4)
{
  signed int LastError; // eax
  unsigned int v8; // ebx
  DWORD v9; // eax
  char v10; // dl
  const char *v11; // rax
  char v12; // dl
  const char *v13; // rax
  const unsigned __int16 *v14; // r8
  int v15; // eax
  const char *v16; // r9
  char v17; // dl
  char v18; // si
  int v19; // eax
  DWORD v20; // eax
  char *v22; // [rsp+20h] [rbp-38h]
  char *v23; // [rsp+20h] [rbp-38h]
  char *v24; // [rsp+30h] [rbp-28h]
  DWORD v25; // [rsp+38h] [rbp-20h]
  DWORD v26; // [rsp+38h] [rbp-20h]
  PVOID Buffer; // [rsp+70h] [rbp+18h] BYREF

  Buffer = 0;
  if ( !CredReadW(a1, 1u, 0, (PCREDENTIALW *)&Buffer) )
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
    v9 = GetLastError();
    AslLogCallPrintf(
      3,
      "Windows::Compat::Appraiser::Utilities::GetCredentialsForBasicProxyIfPresent",
      3181,
      "Proxy did not have associated login credentials: [%d].",
      v9);
    AslLogCallPrintf(
      3,
      "Windows::Compat::Appraiser::Utilities::GetCredentialsForBasicProxyIfPresent",
      3182,
      "Proxy URL %ls.",
      a1);
    if ( Windows::Compat::Appraiser::AppraiserTestHooks::TreatWarningsAsErrors() )
    {
      v25 = GetLastError();
      v10 = 111;
      v11 = "Proxy %ls did not have associated login credentials: [%d].";
LABEL_6:
      LODWORD(v22) = v8;
      Windows::Compat::Appraiser::WriteLog(
        (Windows::Compat::Appraiser *)1,
        v10,
        (unsigned int)"onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
        "Windows::Compat::Appraiser::Utilities::GetCredentialsForBasicProxyIfPresent",
        v22,
        (int)v11,
        (const char *)a1,
        v25);
      goto LABEL_24;
    }
    v26 = GetLastError();
    v12 = 111;
    v13 = "Proxy %ls did not have associated login credentials: [%d].";
LABEL_23:
    Windows::Compat::Appraiser::WriteLog(
      0,
      v12,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
      "Windows::Compat::Appraiser::Utilities::GetCredentialsForBasicProxyIfPresent",
      0,
      (int)v13,
      (const char *)a1,
      v26);
    goto LABEL_24;
  }
  v14 = (const unsigned __int16 *)*((_QWORD *)Buffer + 5);
  if ( !v14 || !*((_QWORD *)Buffer + 9) )
  {
    v8 = -2147467259;
    v20 = GetLastError();
    AslLogCallPrintf(
      3,
      "Windows::Compat::Appraiser::Utilities::GetCredentialsForBasicProxyIfPresent",
      3191,
      "Proxy had null login credentials: [%d]",
      v20);
    AslLogCallPrintf(
      3,
      "Windows::Compat::Appraiser::Utilities::GetCredentialsForBasicProxyIfPresent",
      3192,
      "Proxy URL %ls.",
      a1);
    if ( Windows::Compat::Appraiser::AppraiserTestHooks::TreatWarningsAsErrors() )
    {
      v25 = GetLastError();
      v10 = 121;
      v11 = "Proxy %ls had null login credentials: [%d].";
      goto LABEL_6;
    }
    v26 = GetLastError();
    v12 = 121;
    v13 = "Proxy %ls had null login credentials: [%d].";
    goto LABEL_23;
  }
  v15 = StringCchCopyNW(a4, 0x104u, v14, (unsigned __int64)*((unsigned int *)Buffer + 8) >> 1);
  v8 = v15;
  if ( v15 < 0 )
  {
    AslLogCallPrintf(
      3,
      "Windows::Compat::Appraiser::Utilities::GetCredentialsForBasicProxyIfPresent",
      3202,
      "Failed to copy credential blob: [0x%x]",
      v15);
    v16 = "Failed to copy credential blob: [0x%x].";
    v17 = -125;
LABEL_12:
    LODWORD(v24) = v8;
    LODWORD(v23) = v8;
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      v17,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
      "Windows::Compat::Appraiser::Utilities::GetCredentialsForBasicProxyIfPresent",
      v23,
      (int)v16,
      v24);
    goto LABEL_24;
  }
  v18 = Windows::Compat::Appraiser::WicaFactory::TestingFlags;
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
  {
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0xC83u,
      "onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
      "Windows::Compat::Appraiser::Utilities::GetCredentialsForBasicProxyIfPresent",
      "Failed to copy credential blob: [0x%x].",
      v15);
    v18 = Windows::Compat::Appraiser::WicaFactory::TestingFlags;
  }
  v19 = StringCchCopyW(a2, 0x104u, *((const unsigned __int16 **)Buffer + 9));
  v8 = v19;
  if ( v19 < 0 )
  {
    AslLogCallPrintf(
      3,
      "Windows::Compat::Appraiser::Utilities::GetCredentialsForBasicProxyIfPresent",
      3206,
      "Failed to copy string: [0x%x]",
      v19);
    v16 = "Failed to copy string: [0x%x].";
    v17 = -121;
    goto LABEL_12;
  }
  if ( (v18 & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0xC87u,
      "onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
      "Windows::Compat::Appraiser::Utilities::GetCredentialsForBasicProxyIfPresent",
      "Failed to copy string: [0x%x].",
      v19);
  v8 = 0;
LABEL_24:
  if ( Buffer )
    CredFree(Buffer);
  return v8;
}

```

## disassembly

```asm
0x180089b2c  mov     rax, rsp
0x180089b2f  mov     [rax+8], rbx
0x180089b33  mov     [rax+10h], rbp
0x180089b37  mov     [rax+18h], r8
0x180089b3b  push    rsi
0x180089b3c  push    rdi
0x180089b3d  push    r15
0x180089b3f  sub     rsp, 40h
0x180089b43  xor     r8d, r8d; Flags
0x180089b46  mov     qword ptr [rax+18h], 0
0x180089b4e  mov     rbx, r9
0x180089b51  mov     rbp, rdx
0x180089b54  lea     r9, [rax+18h]; Credential
0x180089b58  mov     rsi, rcx
0x180089b5b  lea     r15d, [r8+1]
0x180089b5f  mov     edx, r15d; Type
0x180089b62  call    cs:__imp_CredReadW
0x180089b68  test    eax, eax
0x180089b6a  jnz     loc_180089C1F
0x180089b70  call    cs:__imp_GetLastError
0x180089b76  mov     ebx, eax
0x180089b78  test    eax, eax
0x180089b7a  jle     short loc_180089B85
0x180089b7c  movzx   ebx, ax
0x180089b7f  or      ebx, 80070000h
0x180089b85  call    cs:__imp_GetLastError
0x180089b8b  lea     rdi, aWindowsCompatA_389; "Windows::Compat::Appraiser::Utilities::"...
0x180089b92  mov     r8d, 0C6Dh
0x180089b98  lea     r9, aProxyDidNotHav; "Proxy did not have associated login cre"...
0x180089b9f  mov     dword ptr [rsp+58h+var_38], eax
0x180089ba3  mov     rdx, rdi
0x180089ba6  mov     ecx, 3
0x180089bab  call    AslLogCallPrintf
0x180089bb0  lea     r9, aProxyUrlLs; "Proxy URL %ls."
0x180089bb7  mov     [rsp+58h+var_38], rsi
0x180089bbc  mov     r8d, 0C6Eh
0x180089bc2  mov     rdx, rdi
0x180089bc5  mov     ecx, 3
0x180089bca  call    AslLogCallPrintf
0x180089bcf  call    ?TreatWarningsAsErrors@AppraiserTestHooks@Appraiser@Compat@Windows@@SA_NXZ; Windows::Compat::Appraiser::AppraiserTestHooks::TreatWarningsAsErrors(void)
0x180089bd4  test    al, al
0x180089bd6  jz      short loc_180089C04
0x180089bd8  call    cs:__imp_GetLastError
0x180089bde  mov     [rsp+58h+var_20], eax
0x180089be2  mov     edx, 0C6Fh
0x180089be7  lea     rax, aProxyLsDidNotH; "Proxy %ls did not have associated login"...
0x180089bee  mov     [rsp+58h+var_28], rsi
0x180089bf3  mov     ecx, r15d
0x180089bf6  mov     qword ptr [rsp+58h+var_30], rax
0x180089bfb  mov     dword ptr [rsp+58h+var_38], ebx
0x180089bff  jmp     loc_180089DF2
0x180089c04  call    cs:__imp_GetLastError
0x180089c0a  mov     [rsp+58h+var_20], eax
0x180089c0e  mov     edx, 0C6Fh
0x180089c13  lea     rax, aProxyLsDidNotH; "Proxy %ls did not have associated login"...
0x180089c1a  jmp     loc_180089DE1
0x180089c1f  mov     rax, [rsp+58h+Buffer]
0x180089c24  mov     r8, [rax+28h]; unsigned __int16 *
0x180089c28  test    r8, r8
0x180089c2b  jz      loc_180089D58
0x180089c31  cmp     qword ptr [rax+48h], 0
0x180089c36  jz      loc_180089D58
0x180089c3c  mov     r9d, [rax+20h]
0x180089c40  mov     edx, 104h; unsigned __int64
0x180089c45  shr     r9, 1; unsigned __int64
0x180089c48  mov     rcx, rbx; unsigned __int16 *
0x180089c4b  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x180089c50  lea     rdi, aWindowsCompatA_389; "Windows::Compat::Appraiser::Utilities::"...
0x180089c57  mov     ebx, eax
0x180089c59  test    eax, eax
0x180089c5b  jns     short loc_180089CAB
0x180089c5d  lea     r9, aFailedToCopyCr_0; "Failed to copy credential blob: [0x%x]"
0x180089c64  mov     dword ptr [rsp+58h+var_38], eax
0x180089c68  mov     r8d, 0C82h
0x180089c6e  mov     rdx, rdi
0x180089c71  mov     ecx, 3
0x180089c76  call    AslLogCallPrintf
0x180089c7b  lea     r9, aFailedToCopyCr; "Failed to copy credential blob: [0x%x]."
0x180089c82  mov     edx, 0C83h; bool
0x180089c87  mov     dword ptr [rsp+58h+var_28], ebx; char *
0x180089c8b  lea     r8, aOnecoreBaseApp_7; "onecore\\base\\appcompat\\appraiser\\he"...
0x180089c92  mov     qword ptr [rsp+58h+var_30], r9; int
0x180089c97  mov     ecx, r15d; this
0x180089c9a  mov     r9, rdi; char *
0x180089c9d  mov     dword ptr [rsp+58h+var_38], ebx; char *
0x180089ca1  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x180089ca6  jmp     loc_180089E01
0x180089cab  mov     esi, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x180089cb1  mov     eax, esi
0x180089cb3  and     eax, r15d
0x180089cb6  test    al, al
0x180089cb8  jz      short loc_180089CDF
0x180089cba  lea     r9, aFailedToCopyCr; "Failed to copy credential blob: [0x%x]."
0x180089cc1  mov     dword ptr [rsp+58h+var_38], ebx
0x180089cc5  mov     r8, rdi; char *
0x180089cc8  lea     rdx, aOnecoreBaseApp_7; "onecore\\base\\appcompat\\appraiser\\he"...
0x180089ccf  mov     ecx, 0C83h; unsigned int
0x180089cd4  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x180089cd9  mov     esi, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x180089cdf  mov     r8, [rsp+58h+Buffer]
0x180089ce4  mov     edx, 104h; unsigned __int64
0x180089ce9  mov     rcx, rbp; unsigned __int16 *
0x180089cec  mov     r8, [r8+48h]; unsigned __int16 *
0x180089cf0  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180089cf5  mov     ebx, eax
0x180089cf7  test    eax, eax
0x180089cf9  jns     short loc_180089D2A
0x180089cfb  lea     r9, aFailedToCopySt_2; "Failed to copy string: [0x%x]"
0x180089d02  mov     dword ptr [rsp+58h+var_38], eax
0x180089d06  mov     r8d, 0C86h
0x180089d0c  mov     rdx, rdi
0x180089d0f  mov     ecx, 3
0x180089d14  call    AslLogCallPrintf
0x180089d19  lea     r9, aFailedToCopySt_0; "Failed to copy string: [0x%x]."
0x180089d20  mov     edx, 0C87h
0x180089d25  jmp     loc_180089C87
0x180089d2a  and     esi, r15d
0x180089d2d  test    sil, sil
0x180089d30  jz      short loc_180089D51
0x180089d32  lea     r9, aFailedToCopySt_0; "Failed to copy string: [0x%x]."
0x180089d39  mov     dword ptr [rsp+58h+var_38], ebx
0x180089d3d  mov     r8, rdi; char *
0x180089d40  lea     rdx, aOnecoreBaseApp_7; "onecore\\base\\appcompat\\appraiser\\he"...
0x180089d47  mov     ecx, 0C87h; unsigned int
0x180089d4c  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x180089d51  xor     ebx, ebx
0x180089d53  jmp     loc_180089E01
0x180089d58  mov     ebx, 80004005h
0x180089d5d  call    cs:__imp_GetLastError
0x180089d63  lea     rdi, aWindowsCompatA_389; "Windows::Compat::Appraiser::Utilities::"...
0x180089d6a  mov     r8d, 0C77h
0x180089d70  lea     r9, aProxyHadNullLo; "Proxy had null login credentials: [%d]"
0x180089d77  mov     dword ptr [rsp+58h+var_38], eax
0x180089d7b  mov     rdx, rdi
0x180089d7e  mov     ecx, 3
0x180089d83  call    AslLogCallPrintf
0x180089d88  lea     r9, aProxyUrlLs; "Proxy URL %ls."
0x180089d8f  mov     [rsp+58h+var_38], rsi
0x180089d94  mov     r8d, 0C78h
0x180089d9a  mov     rdx, rdi
0x180089d9d  mov     ecx, 3
0x180089da2  call    AslLogCallPrintf
0x180089da7  call    ?TreatWarningsAsErrors@AppraiserTestHooks@Appraiser@Compat@Windows@@SA_NXZ; Windows::Compat::Appraiser::AppraiserTestHooks::TreatWarningsAsErrors(void)
0x180089dac  test    al, al
0x180089dae  jz      short loc_180089DCB
0x180089db0  call    cs:__imp_GetLastError
0x180089db6  mov     [rsp+58h+var_20], eax
0x180089dba  mov     edx, 0C79h
0x180089dbf  lea     rax, aProxyLsHadNull; "Proxy %ls had null login credentials: ["...
0x180089dc6  jmp     loc_180089BEE
0x180089dcb  call    cs:__imp_GetLastError
0x180089dd1  mov     [rsp+58h+var_20], eax
0x180089dd5  mov     edx, 0C79h; bool
0x180089dda  lea     rax, aProxyLsHadNull; "Proxy %ls had null login credentials: ["...
0x180089de1  mov     [rsp+58h+var_28], rsi; char *
0x180089de6  xor     ecx, ecx; this
0x180089de8  mov     qword ptr [rsp+58h+var_30], rax; int
0x180089ded  mov     [rsp+58h+var_38], rcx; char *
0x180089df2  mov     r9, rdi; char *
0x180089df5  lea     r8, aOnecoreBaseApp_7; "onecore\\base\\appcompat\\appraiser\\he"...
0x180089dfc  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x180089e01  mov     rcx, [rsp+58h+Buffer]; Buffer
0x180089e06  test    rcx, rcx
0x180089e09  jz      short loc_180089E11
0x180089e0b  call    cs:__imp_CredFree
0x180089e11  mov     rbp, [rsp+58h+arg_8]
0x180089e16  mov     eax, ebx
0x180089e18  mov     rbx, [rsp+58h+arg_0]
0x180089e1d  add     rsp, 40h
0x180089e21  pop     r15
0x180089e23  pop     rdi
0x180089e24  pop     rsi
0x180089e25  retn
```
