# PrintCore::UserImpersonationHelpers::IsImpersonatingUser(void)

- ea: `0x180048158`
- end: `0x1800484e6`
- name: `?IsImpersonatingUser@UserImpersonationHelpers@PrintCore@@SA_NXZ`
- size: `910`
- prototype: `char(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180046d80`

## callees

- `0x180003400`
- `0x1800194ec`
- `0x180046a70`
- `0x180048158`
- `0x18004c474`
- `0x18004c574`
- `0x18004c5c4`

## import_xrefs

- `KERNEL32!GetCurrentThread` at `0x180048193`
- `KERNEL32!GetCurrentThread` at `0x180048254`
- `KERNEL32!GetCurrentThread` at `0x180048193`
- `KERNEL32!GetCurrentThread` at `0x180048254`
- `KERNEL32!GetCurrentProcess` at `0x180048300`
- `KERNEL32!GetCurrentProcess` at `0x180048300`
- `KERNEL32!CloseHandle` at `0x180048235`
- `KERNEL32!CloseHandle` at `0x1800482e1`
- `KERNEL32!CloseHandle` at `0x1800484af`
- `KERNEL32!CloseHandle` at `0x180048235`
- `KERNEL32!CloseHandle` at `0x1800482e1`
- `KERNEL32!CloseHandle` at `0x1800484af`
- `KERNEL32!SetLastError` at `0x180048243`
- `KERNEL32!SetLastError` at `0x1800482ef`
- `KERNEL32!SetLastError` at `0x180048243`
- `KERNEL32!SetLastError` at `0x1800482ef`
- `KERNEL32!GetLastError` at `0x1800481c3`
- `KERNEL32!GetLastError` at `0x180048224`
- `KERNEL32!GetLastError` at `0x180048284`
- `KERNEL32!GetLastError` at `0x1800482d0`
- `KERNEL32!GetLastError` at `0x1800481c3`
- `KERNEL32!GetLastError` at `0x180048224`
- `KERNEL32!GetLastError` at `0x180048284`
- `KERNEL32!GetLastError` at `0x1800482d0`
- `KERNEL32!LocalFree` at `0x1800483c1`
- `KERNEL32!LocalFree` at `0x180048493`
- `KERNEL32!LocalFree` at `0x1800483c1`
- `KERNEL32!LocalFree` at `0x180048493`
- `ADVAPI32!EqualSid` at `0x1800483ff`
- `ADVAPI32!EqualSid` at `0x180048452`
- `ADVAPI32!EqualSid` at `0x18004846c`
- `ADVAPI32!EqualSid` at `0x1800483ff`
- `ADVAPI32!EqualSid` at `0x180048452`
- `ADVAPI32!EqualSid` at `0x18004846c`
- `ADVAPI32!OpenProcessToken` at `0x180048319`
- `ADVAPI32!OpenProcessToken` at `0x180048319`
- `ADVAPI32!OpenThreadToken` at `0x1800481af`
- `ADVAPI32!OpenThreadToken` at `0x180048270`
- `ADVAPI32!OpenThreadToken` at `0x1800481af`
- `ADVAPI32!OpenThreadToken` at `0x180048270`

## string_xrefs

- `0x180048384`: `Failed to get the SID attached to the token!`
- `0x180048204`: `OneCoreUap\Internal\PrintScan\inc\UserImpersonationHelpers.h`
- `0x1800482b0`: `OneCoreUap\Internal\PrintScan\inc\UserImpersonationHelpers.h`
- `0x18004833c`: `OneCoreUap\Internal\PrintScan\inc\UserImpersonationHelpers.h`
- `0x180048393`: `OneCoreUap\Internal\PrintScan\inc\UserImpersonationHelpers.h`
- `0x1800481f4`: `OpenThreadToken (OpenAsSelf is FALSE) failed!`
- `0x18004832d`: `OpenProcessToken failed!`
- `0x1800482a0`: `OpenThreadToken (OpenAsSelf is TRUE) failed!`

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
        (void *)"OpenThreadToken (OpenAsSelf is FALSE) failed!",
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
          (void *)"OpenThreadToken (OpenAsSelf is TRUE) failed!",
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
          (void *)"OpenProcessToken failed!",
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
    if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled((wil::details *)`wil::Feature<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetImpl'::`2'::impl) )
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
      (int)"OneCoreUap\\Internal\\PrintScan\\inc\\UserImpersonationHelpers.h",
      v15);
    return v20;
  }
  return v0;
}

```

## disassembly

```asm
0x180048158  push    rbx
0x18004815a  push    rsi
0x18004815b  push    rdi
0x18004815c  push    r14
0x18004815e  push    r15
0x180048160  sub     rsp, 90h
0x180048167  mov     [rsp+0B8h+var_70], 0FFFFFFFFFFFFFFFEh
0x180048170  mov     rax, cs:__security_cookie
0x180048177  xor     rax, rsp
0x18004817a  mov     [rsp+0B8h+var_38], rax
0x180048182  xor     r15d, r15d
0x180048185  movzx   edi, r15b
0x180048189  mov     [rsp+0B8h+var_88], dil
0x18004818e  mov     [rsp+0B8h+TokenHandle], r15
0x180048193  call    cs:__imp_GetCurrentThread
0x18004819a  nop     dword ptr [rax+rax+00h]
0x18004819f  lea     r9, [rsp+0B8h+TokenHandle]; TokenHandle
0x1800481a4  xor     r8d, r8d; OpenAsSelf
0x1800481a7  mov     edx, 2000Ah; DesiredAccess
0x1800481ac  mov     rcx, rax; ThreadHandle
0x1800481af  call    cs:__imp_OpenThreadToken
0x1800481b6  nop     dword ptr [rax+rax+00h]
0x1800481bb  test    eax, eax
0x1800481bd  jnz     loc_18004834F
0x1800481c3  call    cs:__imp_GetLastError
0x1800481ca  nop     dword ptr [rax+rax+00h]
0x1800481cf  cmp     eax, 3F0h
0x1800481d4  jz      short loc_1800481E4
0x1800481d6  cmp     eax, 5
0x1800481d9  jz      short loc_1800481E4
0x1800481db  lea     esi, [r15+1]
0x1800481df  mov     al, sil
0x1800481e2  jmp     short loc_1800481EC
0x1800481e4  mov     al, r15b
0x1800481e7  mov     esi, 1
0x1800481ec  mov     rcx, [rsp+0B8h]; this
0x1800481f4  lea     rdx, aOpenthreadtoke_0; "OpenThreadToken (OpenAsSelf is FALSE) f"...
0x1800481fb  mov     qword ptr [rsp+0B8h+var_98], rdx; bool
0x180048200  movzx   r9d, al; char *
0x180048204  lea     r8, aOnecoreuapInte_0; "OneCoreUap\\Internal\\PrintScan\\inc\\U"...
0x18004820b  mov     edx, 0B1h; void *
0x180048210  call    ?Throw_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x180048215  mov     r14, [rsp+0B8h+TokenHandle]
0x18004821a  lea     rax, [r14-1]
0x18004821e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180048222  ja      short loc_18004824F
0x180048224  call    cs:__imp_GetLastError
0x18004822b  nop     dword ptr [rax+rax+00h]
0x180048230  mov     ebx, eax
0x180048232  mov     rcx, r14; hObject
0x180048235  call    cs:__imp_CloseHandle
0x18004823c  nop     dword ptr [rax+rax+00h]
0x180048241  mov     ecx, ebx; dwErrCode
0x180048243  call    cs:__imp_SetLastError
0x18004824a  nop     dword ptr [rax+rax+00h]
0x18004824f  mov     [rsp+0B8h+TokenHandle], r15
0x180048254  call    cs:__imp_GetCurrentThread
0x18004825b  nop     dword ptr [rax+rax+00h]
0x180048260  lea     r9, [rsp+0B8h+TokenHandle]; TokenHandle
0x180048265  mov     r8d, esi; OpenAsSelf
0x180048268  mov     edx, 2000Ah; DesiredAccess
0x18004826d  mov     rcx, rax; ThreadHandle
0x180048270  call    cs:__imp_OpenThreadToken
0x180048277  nop     dword ptr [rax+rax+00h]
0x18004827c  test    eax, eax
0x18004827e  jnz     loc_180048354
0x180048284  call    cs:__imp_GetLastError
0x18004828b  nop     dword ptr [rax+rax+00h]
0x180048290  cmp     eax, 3F0h
0x180048295  setnz   al
0x180048298  mov     rcx, [rsp+0B8h]; this
0x1800482a0  lea     rdx, aOpenthreadtoke; "OpenThreadToken (OpenAsSelf is TRUE) fa"...
0x1800482a7  mov     qword ptr [rsp+0B8h+var_98], rdx; bool
0x1800482ac  movzx   r9d, al; char *
0x1800482b0  lea     r8, aOnecoreuapInte_0; "OneCoreUap\\Internal\\PrintScan\\inc\\U"...
0x1800482b7  mov     edx, 0B6h; void *
0x1800482bc  call    ?Throw_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x1800482c1  mov     r14, [rsp+0B8h+TokenHandle]
0x1800482c6  lea     rax, [r14-1]
0x1800482ca  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800482ce  ja      short loc_1800482FB
0x1800482d0  call    cs:__imp_GetLastError
0x1800482d7  nop     dword ptr [rax+rax+00h]
0x1800482dc  mov     ebx, eax
0x1800482de  mov     rcx, r14; hObject
0x1800482e1  call    cs:__imp_CloseHandle
0x1800482e8  nop     dword ptr [rax+rax+00h]
0x1800482ed  mov     ecx, ebx; dwErrCode
0x1800482ef  call    cs:__imp_SetLastError
0x1800482f6  nop     dword ptr [rax+rax+00h]
0x1800482fb  mov     [rsp+0B8h+TokenHandle], r15
0x180048300  call    cs:__imp_GetCurrentProcess
0x180048307  nop     dword ptr [rax+rax+00h]
0x18004830c  lea     r8, [rsp+0B8h+TokenHandle]; TokenHandle
0x180048311  mov     edx, 2000Ah; DesiredAccess
0x180048316  mov     rcx, rax; ProcessHandle
0x180048319  call    cs:__imp_OpenProcessToken
0x180048320  nop     dword ptr [rax+rax+00h]
0x180048325  mov     rcx, [rsp+0B8h]; this
0x18004832d  lea     rdx, aOpenprocesstok; "OpenProcessToken failed!"
0x180048334  mov     qword ptr [rsp+0B8h+var_98], rdx; __int64
0x180048339  mov     r9d, eax; char *
0x18004833c  lea     r8, aOnecoreuapInte_0; "OneCoreUap\\Internal\\PrintScan\\inc\\U"...
0x180048343  mov     edx, 0B8h; void *
0x180048348  call    ?Throw_IfWin32BoolFalseMsg@in1diag3@details@wil@@YAHPEAXIPEBDH1ZZ; wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(void *,uint,char const *,int,char const *,...)
0x18004834d  jmp     short loc_180048354
0x18004834f  mov     esi, 1
0x180048354  mov     [rsp+0B8h+pSid1], r15
0x180048359  lea     rax, [rsp+0B8h+pSid1]
0x18004835e  mov     [rsp+0B8h+var_58], rax
0x180048363  mov     [rsp+0B8h+var_50], r15
0x180048368  mov     byte ptr [rsp+0B8h+var_48], sil
0x18004836d  lea     rdx, [rsp+0B8h+var_50]; void **
0x180048372  mov     rcx, [rsp+0B8h+TokenHandle]; TokenHandle
0x180048377  call    ?GetUserSidFromToken@TokenHelpers@PrintCore@@SAJPEAXPEAPEAX@Z; PrintCore::TokenHelpers::GetUserSidFromToken(void *,void * *)
0x18004837c  mov     rcx, [rsp+0B8h]; this
0x180048384  lea     rdx, aFailedToGetThe; "Failed to get the SID attached to the t"...
0x18004838b  mov     qword ptr [rsp+0B8h+var_98], rdx; int
0x180048390  mov     r9d, eax; char *
0x180048393  lea     r8, aOnecoreuapInte_0; "OneCoreUap\\Internal\\PrintScan\\inc\\U"...
0x18004839a  mov     edx, 0BDh; void *
0x18004839f  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800483a4  nop
0x1800483a5  cmp     byte ptr [rsp+0B8h+var_48], r15b
0x1800483aa  jz      short loc_1800483CD
0x1800483ac  mov     rdx, [rsp+0B8h+var_58]
0x1800483b1  mov     rcx, [rdx]; hMem
0x1800483b4  mov     rax, [rsp+0B8h+var_50]
0x1800483b9  mov     [rdx], rax
0x1800483bc  test    rcx, rcx
0x1800483bf  jz      short loc_1800483CD
0x1800483c1  call    cs:__imp_LocalFree
0x1800483c8  nop     dword ptr [rax+rax+00h]
0x1800483cd  mov     [rsp+0B8h+pSid2], 101h
0x1800483d5  mov     [rsp+0B8h+var_64], 5000000h
0x1800483dd  mov     [rsp+0B8h+var_60], 12h
0x1800483e5  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker> `wil::Feature<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetImpl(void)'::`2'::impl
0x1800483ec  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled(void)
0x1800483f1  lea     rdx, [rsp+0B8h+pSid2]; pSid2
0x1800483f6  mov     rcx, [rsp+0B8h+pSid1]; pSid1
0x1800483fb  test    al, al
0x1800483fd  jnz     short loc_180048412
0x1800483ff  call    cs:__imp_EqualSid
0x180048406  nop     dword ptr [rax+rax+00h]
0x18004840b  test    eax, eax
0x18004840d  cmovz   edi, esi
0x180048410  jmp     short loc_18004847F
0x180048412  mov     dword ptr [rsp+0B8h+var_58], 601h
0x18004841a  mov     dword ptr [rsp+0B8h+var_58+4], 5000000h
0x180048422  mov     dword ptr [rsp+0B8h+var_50], 63h ; 'c'
0x18004842a  mov     dword ptr [rsp+0B8h+var_50+4], 0CE5DBACh
0x180048432  mov     [rsp+0B8h+var_48], 76F17EC4h
0x18004843a  mov     [rsp+0B8h+var_44], 0E5F30EDBh
0x180048442  mov     [rsp+0B8h+var_40], 8F58C130h
0x18004844a  mov     [rsp+0B8h+var_3C], 9C65577Dh
0x180048452  call    cs:__imp_EqualSid
0x180048459  nop     dword ptr [rax+rax+00h]
0x18004845e  test    eax, eax
0x180048460  jnz     short loc_180048484
0x180048462  lea     rdx, [rsp+0B8h+var_58]; pSid2
0x180048467  mov     rcx, [rsp+0B8h+pSid1]; pSid1
0x18004846c  call    cs:__imp_EqualSid
0x180048473  nop     dword ptr [rax+rax+00h]
0x180048478  test    eax, eax
0x18004847a  jnz     short loc_180048484
0x18004847c  mov     dil, sil
0x18004847f  mov     [rsp+0B8h+var_88], dil
0x180048484  mov     rcx, [rsp+0B8h+pSid1]; hMem
0x180048489  mov     [rsp+0B8h+pSid1], r15
0x18004848e  test    rcx, rcx
0x180048491  jz      short loc_1800484A0
0x180048493  call    cs:__imp_LocalFree
0x18004849a  nop     dword ptr [rax+rax+00h]
0x18004849f  nop
0x1800484a0  mov     rcx, [rsp+0B8h+TokenHandle]; hObject
0x1800484a5  lea     rax, [rcx-1]
0x1800484a9  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800484ad  ja      short loc_1800484BC
0x1800484af  call    cs:__imp_CloseHandle
0x1800484b6  nop     dword ptr [rax+rax+00h]
0x1800484bb  nop
0x1800484bc  jmp     short loc_1800484C3
0x1800484be  mov     dil, [rsp+0B8h+var_88]
0x1800484c3  mov     al, dil
0x1800484c6  mov     rcx, [rsp+0B8h+var_38]
0x1800484ce  xor     rcx, rsp; StackCookie
0x1800484d1  call    __security_check_cookie
0x1800484d6  add     rsp, 90h
0x1800484dd  pop     r15
0x1800484df  pop     r14
0x1800484e1  pop     rdi
0x1800484e2  pop     rsi
0x1800484e3  pop     rbx
0x1800484e4  retn
```
