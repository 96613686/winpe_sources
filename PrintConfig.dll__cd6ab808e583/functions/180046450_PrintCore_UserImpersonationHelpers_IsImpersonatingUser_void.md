# PrintCore::UserImpersonationHelpers::IsImpersonatingUser(void)

- ea: `0x180046450`
- end: `0x180046765`
- name: `?IsImpersonatingUser@UserImpersonationHelpers@PrintCore@@SA_NXZ`
- size: `789`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180045194`

## callees

- `0x1800032e0`
- `0x1800188fc`
- `0x180044ecc`
- `0x180046450`
- `0x18004a588`
- `0x18004a688`
- `0x18004a6d8`

## import_xrefs

- `KERNEL32!GetCurrentThread` at `0x18004648b`
- `KERNEL32!GetCurrentThread` at `0x180046528`
- `KERNEL32!GetCurrentThread` at `0x18004648b`
- `KERNEL32!GetCurrentThread` at `0x180046528`
- `KERNEL32!GetCurrentProcess` at `0x1800465b0`
- `KERNEL32!GetCurrentProcess` at `0x1800465b0`
- `KERNEL32!CloseHandle` at `0x180046515`
- `KERNEL32!CloseHandle` at `0x18004659d`
- `KERNEL32!CloseHandle` at `0x180046735`
- `KERNEL32!CloseHandle` at `0x180046515`
- `KERNEL32!CloseHandle` at `0x18004659d`
- `KERNEL32!CloseHandle` at `0x180046735`
- `KERNEL32!SetLastError` at `0x18004651d`
- `KERNEL32!SetLastError` at `0x1800465a5`
- `KERNEL32!SetLastError` at `0x18004651d`
- `KERNEL32!SetLastError` at `0x1800465a5`
- `KERNEL32!GetLastError` at `0x1800464af`
- `KERNEL32!GetLastError` at `0x18004650a`
- `KERNEL32!GetLastError` at `0x18004654c`
- `KERNEL32!GetLastError` at `0x180046592`
- `KERNEL32!GetLastError` at `0x1800464af`
- `KERNEL32!GetLastError` at `0x18004650a`
- `KERNEL32!GetLastError` at `0x18004654c`
- `KERNEL32!GetLastError` at `0x180046592`
- `KERNEL32!LocalFree` at `0x180046665`
- `KERNEL32!LocalFree` at `0x18004671f`
- `KERNEL32!LocalFree` at `0x180046665`
- `KERNEL32!LocalFree` at `0x18004671f`
- `ADVAPI32!EqualSid` at `0x18004669d`
- `ADVAPI32!EqualSid` at `0x1800466ea`
- `ADVAPI32!EqualSid` at `0x1800466fe`
- `ADVAPI32!EqualSid` at `0x18004669d`
- `ADVAPI32!EqualSid` at `0x1800466ea`
- `ADVAPI32!EqualSid` at `0x1800466fe`
- `ADVAPI32!OpenProcessToken` at `0x1800465c3`
- `ADVAPI32!OpenProcessToken` at `0x1800465c3`
- `ADVAPI32!OpenThreadToken` at `0x1800464a1`
- `ADVAPI32!OpenThreadToken` at `0x18004653e`
- `ADVAPI32!OpenThreadToken` at `0x1800464a1`
- `ADVAPI32!OpenThreadToken` at `0x18004653e`

## string_xrefs

- `0x180046628`: `Failed to get the SID attached to the token!`
- `0x1800464ea`: `OneCoreUap\Internal\PrintScan\inc\UserImpersonationHelpers.h`
- `0x180046572`: `OneCoreUap\Internal\PrintScan\inc\UserImpersonationHelpers.h`
- `0x1800465e0`: `OneCoreUap\Internal\PrintScan\inc\UserImpersonationHelpers.h`
- `0x180046637`: `OneCoreUap\Internal\PrintScan\inc\UserImpersonationHelpers.h`
- `0x1800464da`: `OpenThreadToken (OpenAsSelf is FALSE) failed!`
- `0x1800465d1`: `OpenProcessToken failed!`
- `0x180046562`: `OpenThreadToken (OpenAsSelf is TRUE) failed!`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
char PrintCore::UserImpersonationHelpers::IsImpersonatingUser(void)
{
  char v0; // di
  HANDLE CurrentThread; // rax
  BOOL v2; // eax
  DWORD LastError; // eax
  bool v4; // al
  HANDLE v5; // r14
  DWORD v6; // ebx
  HANDLE v7; // rax
  DWORD v8; // eax
  HANDLE v9; // r14
  DWORD v10; // ebx
  HANDLE CurrentProcess; // rax
  unsigned int v12; // eax
  unsigned int UserSidFromToken; // eax
  void *v14; // rcx
  const char *v15; // r9
  PSID v16; // rcx
  const char *v18; // [rsp+28h] [rbp-90h]
  const char *v19; // [rsp+28h] [rbp-90h]
  char v20; // [rsp+30h] [rbp-88h]
  HANDLE TokenHandle; // [rsp+38h] [rbp-80h] BYREF
  PSID pSid1[2]; // [rsp+40h] [rbp-78h] BYREF
  _DWORD pSid2[4]; // [rsp+50h] [rbp-68h] BYREF
  PSID *v25; // [rsp+60h] [rbp-58h] BYREF
  void *v26; // [rsp+68h] [rbp-50h] BYREF
  int v27; // [rsp+70h] [rbp-48h]
  int v28; // [rsp+74h] [rbp-44h]
  int v29; // [rsp+78h] [rbp-40h]
  int v30; // [rsp+7Ch] [rbp-3Ch]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]

  pSid1[1] = (PSID)-2LL;
  v0 = 0;
  v20 = 0;
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  v2 = OpenThreadToken(CurrentThread, 0x2000Au, 0, &TokenHandle);
  try
  {
    if ( !v2 )
    {
      LastError = GetLastError();
      v4 = LastError != 1008 && LastError != 5;
      wil::details::in1diag3::Throw_GetLastErrorIfMsg(
        retaddr,
        (void *)0xB1,
        (unsigned int)"OneCoreUap\\Internal\\PrintScan\\inc\\UserImpersonationHelpers.h",
        (const char *)v4,
        (bool)"OpenThreadToken (OpenAsSelf is FALSE) failed!",
        v18);
      v5 = TokenHandle;
      if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      {
        v6 = GetLastError();
        CloseHandle(v5);
        SetLastError(v6);
      }
      TokenHandle = 0;
      v7 = GetCurrentThread();
      if ( !OpenThreadToken(v7, 0x2000Au, 1, &TokenHandle) )
      {
        v8 = GetLastError();
        wil::details::in1diag3::Throw_GetLastErrorIfMsg(
          retaddr,
          (void *)0xB6,
          (unsigned int)"OneCoreUap\\Internal\\PrintScan\\inc\\UserImpersonationHelpers.h",
          (const char *)(v8 != 1008),
          (bool)"OpenThreadToken (OpenAsSelf is TRUE) failed!",
          v18);
        v9 = TokenHandle;
        if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        {
          v10 = GetLastError();
          CloseHandle(v9);
          SetLastError(v10);
        }
        TokenHandle = 0;
        CurrentProcess = GetCurrentProcess();
        v12 = OpenProcessToken(CurrentProcess, 0x2000Au, &TokenHandle);
        wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(
          retaddr,
          (void *)0xB8,
          (unsigned int)"OneCoreUap\\Internal\\PrintScan\\inc\\UserImpersonationHelpers.h",
          (const char *)v12,
          (__int64)"OpenProcessToken failed!",
          v19);
      }
    }
    pSid1[0] = 0;
    v25 = pSid1;
    v26 = 0;
    LOBYTE(v27) = 1;
    UserSidFromToken = PrintCore::TokenHelpers::GetUserSidFromToken(TokenHandle, &v26);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0xBD,
      (unsigned int)"OneCoreUap\\Internal\\PrintScan\\inc\\UserImpersonationHelpers.h",
      (const char *)UserSidFromToken,
      (int)"Failed to get the SID attached to the token!",
      v18);
    if ( (_BYTE)v27 )
    {
      v14 = *v25;
      *v25 = v26;
      if ( v14 )
        LocalFree(v14);
    }
    pSid2[0] = 257;
    pSid2[1] = 83886080;
    pSid2[2] = 18;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetImpl'::`2'::impl) )
    {
      v25 = (PSID *)0x500000000000601LL;
      v26 = (void *)0xCE5DBAC00000063LL;
      v27 = 1995538116;
      v28 = -437055781;
      v29 = -1890008784;
      v30 = -1671080067;
      if ( EqualSid(pSid1[0], pSid2) || EqualSid(pSid1[0], &v25) )
        goto LABEL_24;
      v0 = 1;
    }
    else if ( !EqualSid(pSid1[0], pSid2) )
    {
      v0 = 1;
    }
    v20 = v0;
LABEL_24:
    v16 = pSid1[0];
    pSid1[0] = 0;
    if ( v16 )
      LocalFree(v16);
    if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(TokenHandle);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0xD2,
      (unsigned int)"OneCoreUap\\Internal\\PrintScan\\inc\\UserImpersonationHelpers.h",
      v15);
    return v20;
  }
  return v0;
}

```

## disassembly

```asm
0x180046450  push    rbx
0x180046452  push    rsi
0x180046453  push    rdi
0x180046454  push    r14
0x180046456  push    r15
0x180046458  sub     rsp, 90h
0x18004645f  mov     [rsp+0B8h+var_70], 0FFFFFFFFFFFFFFFEh
0x180046468  mov     rax, cs:__security_cookie
0x18004646f  xor     rax, rsp
0x180046472  mov     [rsp+0B8h+var_38], rax
0x18004647a  xor     r15d, r15d
0x18004647d  movzx   edi, r15b
0x180046481  mov     [rsp+0B8h+var_88], dil
0x180046486  mov     [rsp+0B8h+TokenHandle], r15
0x18004648b  call    cs:__imp_GetCurrentThread
0x180046491  lea     r9, [rsp+0B8h+TokenHandle]; TokenHandle
0x180046496  xor     r8d, r8d; OpenAsSelf
0x180046499  mov     edx, 2000Ah; DesiredAccess
0x18004649e  mov     rcx, rax; ThreadHandle
0x1800464a1  call    cs:__imp_OpenThreadToken
0x1800464a7  test    eax, eax
0x1800464a9  jnz     loc_1800465F3
0x1800464af  call    cs:__imp_GetLastError
0x1800464b5  cmp     eax, 3F0h
0x1800464ba  jz      short loc_1800464CA
0x1800464bc  cmp     eax, 5
0x1800464bf  jz      short loc_1800464CA
0x1800464c1  lea     esi, [r15+1]
0x1800464c5  mov     al, sil
0x1800464c8  jmp     short loc_1800464D2
0x1800464ca  mov     al, r15b
0x1800464cd  mov     esi, 1
0x1800464d2  mov     rcx, [rsp+0B8h]; this
0x1800464da  lea     rdx, aOpenthreadtoke_0; "OpenThreadToken (OpenAsSelf is FALSE) f"...
0x1800464e1  mov     qword ptr [rsp+0B8h+var_98], rdx; bool
0x1800464e6  movzx   r9d, al; char *
0x1800464ea  lea     r8, aOnecoreuapInte_0; "OneCoreUap\\Internal\\PrintScan\\inc\\U"...
0x1800464f1  mov     edx, 0B1h; void *
0x1800464f6  call    ?Throw_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x1800464fb  mov     r14, [rsp+0B8h+TokenHandle]
0x180046500  lea     rax, [r14-1]
0x180046504  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180046508  ja      short loc_180046523
0x18004650a  call    cs:__imp_GetLastError
0x180046510  mov     ebx, eax
0x180046512  mov     rcx, r14; hObject
0x180046515  call    cs:__imp_CloseHandle
0x18004651b  mov     ecx, ebx; dwErrCode
0x18004651d  call    cs:__imp_SetLastError
0x180046523  mov     [rsp+0B8h+TokenHandle], r15
0x180046528  call    cs:__imp_GetCurrentThread
0x18004652e  lea     r9, [rsp+0B8h+TokenHandle]; TokenHandle
0x180046533  mov     r8d, esi; OpenAsSelf
0x180046536  mov     edx, 2000Ah; DesiredAccess
0x18004653b  mov     rcx, rax; ThreadHandle
0x18004653e  call    cs:__imp_OpenThreadToken
0x180046544  test    eax, eax
0x180046546  jnz     loc_1800465F8
0x18004654c  call    cs:__imp_GetLastError
0x180046552  cmp     eax, 3F0h
0x180046557  setnz   al
0x18004655a  mov     rcx, [rsp+0B8h]; this
0x180046562  lea     rdx, aOpenthreadtoke; "OpenThreadToken (OpenAsSelf is TRUE) fa"...
0x180046569  mov     qword ptr [rsp+0B8h+var_98], rdx; bool
0x18004656e  movzx   r9d, al; char *
0x180046572  lea     r8, aOnecoreuapInte_0; "OneCoreUap\\Internal\\PrintScan\\inc\\U"...
0x180046579  mov     edx, 0B6h; void *
0x18004657e  call    ?Throw_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x180046583  mov     r14, [rsp+0B8h+TokenHandle]
0x180046588  lea     rax, [r14-1]
0x18004658c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180046590  ja      short loc_1800465AB
0x180046592  call    cs:__imp_GetLastError
0x180046598  mov     ebx, eax
0x18004659a  mov     rcx, r14; hObject
0x18004659d  call    cs:__imp_CloseHandle
0x1800465a3  mov     ecx, ebx; dwErrCode
0x1800465a5  call    cs:__imp_SetLastError
0x1800465ab  mov     [rsp+0B8h+TokenHandle], r15
0x1800465b0  call    cs:__imp_GetCurrentProcess
0x1800465b6  lea     r8, [rsp+0B8h+TokenHandle]; TokenHandle
0x1800465bb  mov     edx, 2000Ah; DesiredAccess
0x1800465c0  mov     rcx, rax; ProcessHandle
0x1800465c3  call    cs:__imp_OpenProcessToken
0x1800465c9  mov     rcx, [rsp+0B8h]; this
0x1800465d1  lea     rdx, aOpenprocesstok; "OpenProcessToken failed!"
0x1800465d8  mov     qword ptr [rsp+0B8h+var_98], rdx; __int64
0x1800465dd  mov     r9d, eax; char *
0x1800465e0  lea     r8, aOnecoreuapInte_0; "OneCoreUap\\Internal\\PrintScan\\inc\\U"...
0x1800465e7  mov     edx, 0B8h; void *
0x1800465ec  call    ?Throw_IfWin32BoolFalseMsg@in1diag3@details@wil@@YAHPEAXIPEBDH1ZZ; wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(void *,uint,char const *,int,char const *,...)
0x1800465f1  jmp     short loc_1800465F8
0x1800465f3  mov     esi, 1
0x1800465f8  mov     [rsp+0B8h+pSid1], r15
0x1800465fd  lea     rax, [rsp+0B8h+pSid1]
0x180046602  mov     [rsp+0B8h+var_58], rax
0x180046607  mov     [rsp+0B8h+var_50], r15
0x18004660c  mov     byte ptr [rsp+0B8h+var_48], sil
0x180046611  lea     rdx, [rsp+0B8h+var_50]; void **
0x180046616  mov     rcx, [rsp+0B8h+TokenHandle]; TokenHandle
0x18004661b  call    ?GetUserSidFromToken@TokenHelpers@PrintCore@@SAJPEAXPEAPEAX@Z; PrintCore::TokenHelpers::GetUserSidFromToken(void *,void * *)
0x180046620  mov     rcx, [rsp+0B8h]; this
0x180046628  lea     rdx, aFailedToGetThe; "Failed to get the SID attached to the t"...
0x18004662f  mov     qword ptr [rsp+0B8h+var_98], rdx; int
0x180046634  mov     r9d, eax; char *
0x180046637  lea     r8, aOnecoreuapInte_0; "OneCoreUap\\Internal\\PrintScan\\inc\\U"...
0x18004663e  mov     edx, 0BDh; void *
0x180046643  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180046648  nop
0x180046649  cmp     byte ptr [rsp+0B8h+var_48], r15b
0x18004664e  jz      short loc_18004666B
0x180046650  mov     rdx, [rsp+0B8h+var_58]
0x180046655  mov     rcx, [rdx]; hMem
0x180046658  mov     rax, [rsp+0B8h+var_50]
0x18004665d  mov     [rdx], rax
0x180046660  test    rcx, rcx
0x180046663  jz      short loc_18004666B
0x180046665  call    cs:__imp_LocalFree
0x18004666b  mov     [rsp+0B8h+pSid2], 101h
0x180046673  mov     [rsp+0B8h+var_64], 5000000h
0x18004667b  mov     [rsp+0B8h+var_60], 12h
0x180046683  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker> `wil::Feature<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetImpl(void)'::`2'::impl
0x18004668a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled(void)
0x18004668f  lea     rdx, [rsp+0B8h+pSid2]; pSid2
0x180046694  mov     rcx, [rsp+0B8h+pSid1]; pSid1
0x180046699  test    al, al
0x18004669b  jnz     short loc_1800466AA
0x18004669d  call    cs:__imp_EqualSid
0x1800466a3  test    eax, eax
0x1800466a5  cmovz   edi, esi
0x1800466a8  jmp     short loc_18004670B
0x1800466aa  mov     dword ptr [rsp+0B8h+var_58], 601h
0x1800466b2  mov     dword ptr [rsp+0B8h+var_58+4], 5000000h
0x1800466ba  mov     dword ptr [rsp+0B8h+var_50], 63h ; 'c'
0x1800466c2  mov     dword ptr [rsp+0B8h+var_50+4], 0CE5DBACh
0x1800466ca  mov     [rsp+0B8h+var_48], 76F17EC4h
0x1800466d2  mov     [rsp+0B8h+var_44], 0E5F30EDBh
0x1800466da  mov     [rsp+0B8h+var_40], 8F58C130h
0x1800466e2  mov     [rsp+0B8h+var_3C], 9C65577Dh
0x1800466ea  call    cs:__imp_EqualSid
0x1800466f0  test    eax, eax
0x1800466f2  jnz     short loc_180046710
0x1800466f4  lea     rdx, [rsp+0B8h+var_58]; pSid2
0x1800466f9  mov     rcx, [rsp+0B8h+pSid1]; pSid1
0x1800466fe  call    cs:__imp_EqualSid
0x180046704  test    eax, eax
0x180046706  jnz     short loc_180046710
0x180046708  mov     dil, sil
0x18004670b  mov     [rsp+0B8h+var_88], dil
0x180046710  mov     rcx, [rsp+0B8h+pSid1]; hMem
0x180046715  mov     [rsp+0B8h+pSid1], r15
0x18004671a  test    rcx, rcx
0x18004671d  jz      short loc_180046726
0x18004671f  call    cs:__imp_LocalFree
0x180046725  nop
0x180046726  mov     rcx, [rsp+0B8h+TokenHandle]; hObject
0x18004672b  lea     rax, [rcx-1]
0x18004672f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180046733  ja      short loc_18004673C
0x180046735  call    cs:__imp_CloseHandle
0x18004673b  nop
0x18004673c  jmp     short loc_180046743
0x18004673e  mov     dil, [rsp+0B8h+var_88]
0x180046743  mov     al, dil
0x180046746  mov     rcx, [rsp+0B8h+var_38]
0x18004674e  xor     rcx, rsp; StackCookie
0x180046751  call    __security_check_cookie
0x180046756  add     rsp, 90h
0x18004675d  pop     r15
0x18004675f  pop     r14
0x180046761  pop     rdi
0x180046762  pop     rsi
0x180046763  pop     rbx
0x180046764  retn
```
