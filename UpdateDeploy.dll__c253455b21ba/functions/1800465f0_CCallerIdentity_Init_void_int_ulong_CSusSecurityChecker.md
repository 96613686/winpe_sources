# CCallerIdentity::Init(void *,int,ulong,CSusSecurityChecker *)

- ea: `0x1800465f0`
- end: `0x180046b4b`
- name: `?Init@CCallerIdentity@@QEAAJPEAXHKPEAVCSusSecurityChecker@@@Z`
- size: `1371`
- prototype: `__int64 __usercall@<rax>(CCallerIdentity *__hidden this@<rcx>, void *@<rdx>, int@<r8d>, unsigned int@<r9d>, struct CSusSecurityChecker *)`
- caller_count: `1`
- callee_count: `24`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180018124`

## callees

- `0x180003180`
- `0x180007b6c`
- `0x180009a80`
- `0x18000a06c`
- `0x18000dce4`
- `0x18000dff4`
- `0x18000e094`
- `0x18000e134`
- `0x18000e1dc`
- `0x18000e280`
- `0x18000e328`
- `0x18000e494`
- `0x18000e538`
- `0x18000e5dc`
- `0x18000e684`
- `0x1800110fc`
- `0x180046380`
- `0x180046444`
- `0x1800465f0`
- `0x180046b54`
- `0x180046c18`
- `0x180046c7c`
- `0x180047354`
- `0x180061960`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004699a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800469b0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180046a4c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180046a60`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004699a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800469b0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180046a4c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180046a60`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180046a90`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180046a90`

## string_xrefs

- `0x18004690d`: `TOKEN: CallerInteractiveSessionId = %d, hrEnumSessions = 0x%08x, Active = %ws`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CCallerIdentity::Init(
        CCallerIdentity *this,
        void *a2,
        __int64 a3,
        __int64 a4,
        struct CSusSecurityChecker *a5)
{
  int IsGuest; // ebx
  __int64 v8; // rdx
  __int64 v9; // r9
  wil::details::in1diag3 *v10; // rcx
  int v12; // ecx
  bool v13; // zf
  void **v14; // r12
  unsigned int *v15; // r14
  unsigned int v16; // ecx
  int TokenFromLoggedOnUser; // eax
  int IsAdmin; // r14d
  HANDLE v19; // rbx
  int active; // eax
  const wchar_t *v21; // rcx
  __int64 v22; // rdx
  unsigned __int64 v23; // r9
  int UserSidFromToken; // eax
  CCallerIdentity *v25; // rcx
  int DefAppsToken; // eax
  __int64 v27; // rdx
  int v28; // eax
  __int64 v29; // rax
  int v30; // [rsp+20h] [rbp-51h]
  bool v31; // [rsp+50h] [rbp-21h] BYREF
  int v32; // [rsp+54h] [rbp-1Dh] BYREF
  HANDLE hObject; // [rsp+58h] [rbp-19h] BYREF
  int v34; // [rsp+60h] [rbp-11h] BYREF
  int v35; // [rsp+64h] [rbp-Dh] BYREF
  int v36; // [rsp+68h] [rbp-9h] BYREF
  int v37; // [rsp+6Ch] [rbp-5h] BYREF
  int v38; // [rsp+70h] [rbp-1h] BYREF
  int v39; // [rsp+74h] [rbp+3h] BYREF
  int v40; // [rsp+78h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+57h]

  v34 = 1;
  v35 = 1;
  v36 = 0;
  v38 = 0;
  v39 = 0;
  v40 = 0;
  v32 = 0;
  v37 = 0;
  if ( !a5 )
  {
    IsGuest = -2147024809;
    v8 = 106;
LABEL_3:
    v9 = (unsigned int)IsGuest;
    v10 = retaddr;
LABEL_4:
    wil::details::in1diag3::Return_Hr(
      v10,
      (void *)v8,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\lib\\susenginelib\\calleridentity.cpp",
      (const char *)v9,
      v30);
    return (unsigned int)IsGuest;
  }
  CCallerIdentity::Uninit(this);
  IsGuest = CSusSecurityChecker::IsGuest(a5, &v34, a2);
  if ( IsGuest < 0 )
  {
    v8 = 142;
    goto LABEL_3;
  }
  IsGuest = CSusSecurityChecker::IsAnonymous(a5, &v35, a2);
  if ( IsGuest < 0 )
  {
    v8 = 143;
    goto LABEL_3;
  }
  IsGuest = CSusSecurityChecker::IsAuthenticated(a5, &v36, a2);
  if ( IsGuest < 0 )
  {
    v8 = 144;
    goto LABEL_3;
  }
  if ( v34 )
  {
    IsGuest = -2147024891;
    v8 = 145;
    goto LABEL_3;
  }
  if ( v35 )
  {
    IsGuest = -2147024891;
    v8 = 146;
    goto LABEL_3;
  }
  if ( !v36 )
  {
    IsGuest = -2147024891;
    v8 = 147;
    goto LABEL_3;
  }
  IsGuest = CSusSecurityChecker::IsAdmin(a5, &v38, a2);
  if ( IsGuest < 0 )
  {
    v8 = 148;
    goto LABEL_3;
  }
  IsGuest = CSusSecurityChecker::IsAdminCapable(a5, &v37, a2);
  if ( IsGuest < 0 )
  {
    v8 = 149;
    goto LABEL_3;
  }
  IsGuest = CSusSecurityChecker::IsLocalSystem(a5, (int *)this, a2);
  if ( IsGuest < 0 )
  {
    v8 = 150;
    goto LABEL_3;
  }
  IsGuest = CSusSecurityChecker::IsInteractive(a5, &v32, a2);
  if ( IsGuest < 0 )
  {
    v8 = 151;
    goto LABEL_3;
  }
  IsGuest = CSusSecurityChecker::IsPowerUser(a5, &v39, a2);
  if ( IsGuest < 0 )
  {
    v8 = 152;
    goto LABEL_3;
  }
  IsGuest = CSusSecurityChecker::IsRemote(a5, (int *)this + 3, a2);
  if ( IsGuest < 0 )
  {
    v8 = 153;
    goto LABEL_3;
  }
  IsGuest = CSusSecurityChecker::IsTrustedService(a5, (int *)this + 2, a2);
  if ( IsGuest < 0 )
  {
    v8 = 154;
    goto LABEL_3;
  }
  *((_DWORD *)this + 32) = v37;
  v12 = v38;
  *((_DWORD *)this + 1) = v38 == 0;
  if ( !v32 && !v12 && !*(_DWORD *)this && !*((_DWORD *)this + 2) )
  {
    IsGuest = -2147024891;
    v8 = 176;
    goto LABEL_3;
  }
  if ( *((_DWORD *)this + 3) )
  {
    IsGuest = -2147024891;
    v9 = 2147942405LL;
    v13 = v12 == 0;
    v10 = retaddr;
    if ( v13 )
      v8 = 197;
    else
      v8 = 198;
    goto LABEL_4;
  }
  v14 = (void **)((char *)this + 16);
  IsGuest = GetUserSidFromToken(a2, (_QWORD *)this + 2);
  if ( IsGuest < 0 )
  {
    v8 = 230;
    goto LABEL_3;
  }
  v15 = (unsigned int *)((char *)this + 104);
  if ( a2 )
  {
    IsGuest = GetSessionIdFromToken((char *)this + 104, a2);
    if ( IsGuest < 0 )
    {
      v8 = 236;
      goto LABEL_3;
    }
  }
  else
  {
    *v15 = 0;
  }
  if ( v32 )
  {
    hObject = 0;
    v16 = *v15;
    *((_DWORD *)this + 20) = *v15;
    TokenFromLoggedOnUser = GetTokenFromLoggedOnUser(v16, &hObject);
    IsAdmin = TokenFromLoggedOnUser;
    v19 = hObject;
    if ( TokenFromLoggedOnUser < 0
      && TokenFromLoggedOnUser != -2147023582
      && TokenFromLoggedOnUser != -2147023888
      && TokenFromLoggedOnUser != -2147023651
      && TokenFromLoggedOnUser != -2145124266 )
    {
      v31 = 0;
      active = IsActiveSessionId(*((_DWORD *)this + 20), &v31);
      v21 = L"No";
      if ( v31 )
        v21 = L"Yes";
      WUTrace(
        0,
        0,
        1,
        1,
        0,
        L"TOKEN: CallerInteractiveSessionId = %d, hrEnumSessions = 0x%08x, Active = %ws",
        *((_DWORD *)this + 20),
        active,
        v21);
      v22 = 272;
      goto LABEL_59;
    }
    if ( hObject )
    {
      IsAdmin = CSusSecurityChecker::IsAdmin(a5, &v40, hObject);
      if ( IsAdmin < 0 )
      {
        v22 = 277;
LABEL_59:
        v23 = (unsigned int)IsAdmin;
LABEL_62:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v22,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\lib\\susenginelib\\calleridentity.cpp",
          (const char *)v23,
          v30);
        if ( v19 )
          CloseHandle(v19);
        return (unsigned int)IsAdmin;
      }
      UserSidFromToken = GetUserSidFromToken(v19, (_QWORD *)this + 14);
      IsAdmin = UserSidFromToken;
      if ( UserSidFromToken < 0 )
      {
        v23 = (unsigned int)UserSidFromToken;
        v22 = 278;
        goto LABEL_62;
      }
    }
    if ( v19 )
      CloseHandle(v19);
  }
  else
  {
    *((_DWORD *)this + 20) = -1;
  }
  IsGuest = CTokenCache::Init((CCallerIdentity *)((char *)this + 24), a2);
  if ( IsGuest < 0 && *((_DWORD *)this + 25) )
  {
    v8 = 293;
    goto LABEL_3;
  }
  if ( CCallerIdentity::IsDefAppsTestHookEnabled(this) )
  {
    hObject = 0;
    DefAppsToken = CCallerIdentity::GetDefAppsToken(v25, &hObject);
    IsGuest = DefAppsToken;
    if ( DefAppsToken < 0 )
    {
      v27 = 298;
      goto LABEL_76;
    }
    SusFree(*v14);
    *v14 = 0;
    DefAppsToken = GetUserSidFromToken(hObject, (_QWORD *)this + 2);
    IsGuest = DefAppsToken;
    if ( DefAppsToken < 0 )
    {
      v27 = 300;
LABEL_76:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v27,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\lib\\susenginelib\\calleridentity.cpp",
        (const char *)(unsigned int)DefAppsToken,
        v30);
      if ( hObject )
        CloseHandle(hObject);
      return (unsigned int)IsGuest;
    }
    if ( hObject )
      CloseHandle(hObject);
  }
  if ( !*v14 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x134,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\lib\\susenginelib\\calleridentity.cpp",
      (const char *)0x80240FFFLL,
      v30);
  if ( !IsValidSid(*v14) )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x135,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\lib\\susenginelib\\calleridentity.cpp",
      (const char *)0x80240FFFLL,
      v30);
  v28 = v32;
  if ( v32 )
    goto LABEL_91;
  if ( *((_DWORD *)this + 20) != -1 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x138,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\lib\\susenginelib\\calleridentity.cpp",
      (const char *)0x80240FFFLL,
      v30);
    v28 = v32;
  }
  if ( v28 )
    goto LABEL_91;
  if ( *((_QWORD *)this + 14) )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x139,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\lib\\susenginelib\\calleridentity.cpp",
      (const char *)0x80240FFFLL,
      v30);
    v28 = v32;
  }
  if ( v28 )
  {
LABEL_91:
    if ( *((_DWORD *)this + 20) == -1 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x13F,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\lib\\susenginelib\\calleridentity.cpp",
        (const char *)0x80240FFFLL,
        v30);
  }
  v29 = *((_QWORD *)this + 14);
  if ( !v29 )
    v29 = *((_QWORD *)this + 2);
  *((_QWORD *)this + 11) = v29;
  return 0;
}

```

## disassembly

```asm
0x1800465f0  mov     [rsp-8+arg_10], rbx
0x1800465f5  push    rbp
0x1800465f6  push    rsi
0x1800465f7  push    rdi
0x1800465f8  push    r12
0x1800465fa  push    r13
0x1800465fc  push    r14
0x1800465fe  push    r15
0x180046600  lea     rbp, [rsp-1Fh]
0x180046605  sub     rsp, 90h
0x18004660c  mov     rax, cs:__security_cookie
0x180046613  xor     rax, rsp
0x180046616  mov     [rbp+4Fh+var_40], rax
0x18004661a  mov     rdi, rdx
0x18004661d  mov     rsi, rcx
0x180046620  mov     r15, [rbp+4Fh+arg_20]
0x180046624  mov     eax, 1
0x180046629  mov     [rbp+4Fh+var_60], eax
0x18004662c  mov     [rbp+4Fh+var_5C], eax
0x18004662f  xor     r13d, r13d
0x180046632  mov     [rbp+4Fh+var_58], r13d
0x180046636  mov     [rbp+4Fh+var_50], r13d
0x18004663a  mov     [rbp+4Fh+var_4C], r13d
0x18004663e  mov     [rbp+4Fh+var_48], r13d
0x180046642  mov     [rbp+4Fh+var_6C], r13d
0x180046646  mov     [rbp+4Fh+var_54], r13d
0x18004664a  test    r15, r15
0x18004664d  jnz     short loc_180046671
0x18004664f  mov     ebx, 80070057h
0x180046654  lea     edx, [rax+69h]; void *
0x180046657  lea     r8, aCW1SSrcClientE_8; "C:\\__w\\1\\s\\src\\Client\\Engine\\lib"...
0x18004665e  mov     r9d, ebx; char *
0x180046661  mov     rcx, [rbp+57h]; this
0x180046665  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004666a  mov     eax, ebx
0x18004666c  jmp     loc_180046B24
0x180046671  call    ?Uninit@CCallerIdentity@@QEAAXXZ; CCallerIdentity::Uninit(void)
0x180046676  mov     r8, rdi; void *
0x180046679  lea     rdx, [rbp+4Fh+var_60]; int *
0x18004667d  mov     rcx, r15; this
0x180046680  call    ?IsGuest@CSusSecurityChecker@@QEAAJPEAHPEAX@Z; CSusSecurityChecker::IsGuest(int *,void *)
0x180046685  mov     ebx, eax
0x180046687  test    eax, eax
0x180046689  jns     short loc_180046692
0x18004668b  mov     edx, 8Eh
0x180046690  jmp     short loc_180046657
0x180046692  mov     r8, rdi; void *
0x180046695  lea     rdx, [rbp+4Fh+var_5C]; int *
0x180046699  mov     rcx, r15; this
0x18004669c  call    ?IsAnonymous@CSusSecurityChecker@@QEAAJPEAHPEAX@Z; CSusSecurityChecker::IsAnonymous(int *,void *)
0x1800466a1  mov     ebx, eax
0x1800466a3  test    eax, eax
0x1800466a5  jns     short loc_1800466AE
0x1800466a7  mov     edx, 8Fh
0x1800466ac  jmp     short loc_180046657
0x1800466ae  mov     r8, rdi; void *
0x1800466b1  lea     rdx, [rbp+4Fh+var_58]; int *
0x1800466b5  mov     rcx, r15; this
0x1800466b8  call    ?IsAuthenticated@CSusSecurityChecker@@QEAAJPEAHPEAX@Z; CSusSecurityChecker::IsAuthenticated(int *,void *)
0x1800466bd  mov     ebx, eax
0x1800466bf  test    eax, eax
0x1800466c1  jns     short loc_1800466CA
0x1800466c3  mov     edx, 90h
0x1800466c8  jmp     short loc_180046657
0x1800466ca  cmp     [rbp+4Fh+var_60], r13d
0x1800466ce  jz      short loc_1800466DF
0x1800466d0  mov     ebx, 80070005h
0x1800466d5  mov     edx, 91h
0x1800466da  jmp     loc_180046657
0x1800466df  cmp     [rbp+4Fh+var_5C], r13d
0x1800466e3  jz      short loc_1800466F4
0x1800466e5  mov     ebx, 80070005h
0x1800466ea  mov     edx, 92h
0x1800466ef  jmp     loc_180046657
0x1800466f4  cmp     [rbp+4Fh+var_58], r13d
0x1800466f8  jnz     short loc_180046709
0x1800466fa  mov     ebx, 80070005h
0x1800466ff  mov     edx, 93h
0x180046704  jmp     loc_180046657
0x180046709  mov     r8, rdi; void *
0x18004670c  lea     rdx, [rbp+4Fh+var_50]; int *
0x180046710  mov     rcx, r15; this
0x180046713  call    ?IsAdmin@CSusSecurityChecker@@QEAAJPEAHPEAX@Z; CSusSecurityChecker::IsAdmin(int *,void *)
0x180046718  mov     ebx, eax
0x18004671a  test    eax, eax
0x18004671c  jns     short loc_180046728
0x18004671e  mov     edx, 94h
0x180046723  jmp     loc_180046657
0x180046728  mov     r8, rdi; void *
0x18004672b  lea     rdx, [rbp+4Fh+var_54]; int *
0x18004672f  mov     rcx, r15; this
0x180046732  call    ?IsAdminCapable@CSusSecurityChecker@@QEAAJPEAHPEAX@Z; CSusSecurityChecker::IsAdminCapable(int *,void *)
0x180046737  mov     ebx, eax
0x180046739  test    eax, eax
0x18004673b  jns     short loc_180046747
0x18004673d  mov     edx, 95h
0x180046742  jmp     loc_180046657
0x180046747  mov     r8, rdi; void *
0x18004674a  mov     rdx, rsi; int *
0x18004674d  mov     rcx, r15; this
0x180046750  call    ?IsLocalSystem@CSusSecurityChecker@@QEAAJPEAHPEAX@Z; CSusSecurityChecker::IsLocalSystem(int *,void *)
0x180046755  mov     ebx, eax
0x180046757  test    eax, eax
0x180046759  jns     short loc_180046765
0x18004675b  mov     edx, 96h
0x180046760  jmp     loc_180046657
0x180046765  mov     r8, rdi; void *
0x180046768  lea     rdx, [rbp+4Fh+var_6C]; int *
0x18004676c  mov     rcx, r15; this
0x18004676f  call    ?IsInteractive@CSusSecurityChecker@@QEAAJPEAHPEAX@Z; CSusSecurityChecker::IsInteractive(int *,void *)
0x180046774  mov     ebx, eax
0x180046776  test    eax, eax
0x180046778  jns     short loc_180046784
0x18004677a  mov     edx, 97h
0x18004677f  jmp     loc_180046657
0x180046784  mov     r8, rdi; void *
0x180046787  lea     rdx, [rbp+4Fh+var_4C]; int *
0x18004678b  mov     rcx, r15; this
0x18004678e  call    ?IsPowerUser@CSusSecurityChecker@@QEAAJPEAHPEAX@Z; CSusSecurityChecker::IsPowerUser(int *,void *)
0x180046793  mov     ebx, eax
0x180046795  test    eax, eax
0x180046797  jns     short loc_1800467A3
0x180046799  mov     edx, 98h
0x18004679e  jmp     loc_180046657
0x1800467a3  mov     r8, rdi; void *
0x1800467a6  lea     rdx, [rsi+0Ch]; int *
0x1800467aa  mov     rcx, r15; this
0x1800467ad  call    ?IsRemote@CSusSecurityChecker@@QEAAJPEAHPEAX@Z; CSusSecurityChecker::IsRemote(int *,void *)
0x1800467b2  mov     ebx, eax
0x1800467b4  test    eax, eax
0x1800467b6  jns     short loc_1800467C2
0x1800467b8  mov     edx, 99h
0x1800467bd  jmp     loc_180046657
0x1800467c2  mov     r8, rdi; void *
0x1800467c5  lea     rdx, [rsi+8]; int *
0x1800467c9  mov     rcx, r15; this
0x1800467cc  call    ?IsTrustedService@CSusSecurityChecker@@QEAAJPEAHPEAX@Z; CSusSecurityChecker::IsTrustedService(int *,void *)
0x1800467d1  mov     ebx, eax
0x1800467d3  test    eax, eax
0x1800467d5  jns     short loc_1800467E1
0x1800467d7  mov     edx, 9Ah
0x1800467dc  jmp     loc_180046657
0x1800467e1  mov     eax, [rbp+4Fh+var_54]
0x1800467e4  mov     [rsi+80h], eax
0x1800467ea  mov     eax, r13d
0x1800467ed  mov     ecx, [rbp+4Fh+var_50]
0x1800467f0  test    ecx, ecx
0x1800467f2  setz    al
0x1800467f5  mov     [rsi+4], eax
0x1800467f8  cmp     [rbp+4Fh+var_6C], r13d
0x1800467fc  jnz     short loc_18004681C
0x1800467fe  test    ecx, ecx
0x180046800  jnz     short loc_18004681C
0x180046802  cmp     [rsi], r13d
0x180046805  jnz     short loc_18004681C
0x180046807  cmp     [rsi+8], r13d
0x18004680b  jnz     short loc_18004681C
0x18004680d  mov     ebx, 80070005h
0x180046812  mov     edx, 0B0h
0x180046817  jmp     loc_180046657
0x18004681c  cmp     [rsi+0Ch], r13d
0x180046820  jz      short loc_18004684D
0x180046822  mov     ebx, 80070005h
0x180046827  lea     r8, aCW1SSrcClientE_8; "C:\\__w\\1\\s\\src\\Client\\Engine\\lib"...
0x18004682e  mov     r9d, ebx
0x180046831  test    ecx, ecx
0x180046833  mov     rcx, [rbp+57h]
0x180046837  jnz     short loc_180046843
0x180046839  mov     edx, 0C5h
0x18004683e  jmp     loc_180046665
0x180046843  mov     edx, 0C6h
0x180046848  jmp     loc_180046665
0x18004684d  lea     r12, [rsi+10h]
0x180046851  mov     rdx, r12
0x180046854  mov     rcx, rdi; TokenHandle
0x180046857  call    GetUserSidFromToken
0x18004685c  mov     ebx, eax
0x18004685e  test    eax, eax
0x180046860  jns     short loc_18004686C
0x180046862  mov     edx, 0E6h
0x180046867  jmp     loc_180046657
0x18004686c  lea     r14, [rsi+68h]
0x180046870  test    rdi, rdi
0x180046873  jz      short loc_180046890
0x180046875  mov     rdx, rdi; TokenHandle
0x180046878  mov     rcx, r14; TokenInformation
0x18004687b  call    GetSessionIdFromToken
0x180046880  mov     ebx, eax
0x180046882  test    eax, eax
0x180046884  jns     short loc_180046893
0x180046886  mov     edx, 0ECh
0x18004688b  jmp     loc_180046657
0x180046890  mov     [r14], r13d
0x180046893  cmp     [rbp+4Fh+var_6C], r13d
0x180046897  jz      loc_1800469B8
0x18004689d  mov     [rbp+4Fh+hObject], r13
0x1800468a1  mov     ecx, [r14]; unsigned int
0x1800468a4  mov     [rsi+50h], ecx
0x1800468a7  lea     rdx, [rbp+4Fh+hObject]; void **
0x1800468ab  call    ?GetTokenFromLoggedOnUser@@YAJKPEAPEAX@Z; GetTokenFromLoggedOnUser(ulong,void * *)
0x1800468b0  mov     r14d, eax
0x1800468b3  mov     rbx, [rbp+4Fh+hObject]
0x1800468b7  test    eax, eax
0x1800468b9  jns     short loc_180046937
0x1800468bb  cmp     eax, 80070522h
0x1800468c0  jz      short loc_180046937
0x1800468c2  cmp     eax, 800703F0h
0x1800468c7  jz      short loc_180046937
0x1800468c9  cmp     eax, 800704DDh
0x1800468ce  jz      short loc_180046937
0x1800468d0  cmp     eax, 80240056h
0x1800468d5  jz      short loc_180046937
0x1800468d7  mov     [rbp+4Fh+var_70], r13b
0x1800468db  lea     rdx, [rbp+4Fh+var_70]; bool *
0x1800468df  mov     ecx, [rsi+50h]; unsigned int
0x1800468e2  call    ?IsActiveSessionId@@YAJKPEA_N@Z; IsActiveSessionId(ulong,bool *)
0x1800468e7  lea     rdx, aYes_1; "Yes"
0x1800468ee  lea     rcx, aNo_2; "No"
0x1800468f5  cmp     [rbp+4Fh+var_70], r13b
0x1800468f9  cmovnz  rcx, rdx
0x1800468fd  mov     [rsp+0C0h+var_80], rcx
0x180046902  mov     [rsp+0C0h+var_88], eax
0x180046906  mov     eax, [rsi+50h]
0x180046909  mov     [rsp+0C0h+var_90], eax
0x18004690d  lea     rax, aTokenCallerint; "TOKEN: CallerInteractiveSessionId = %d,"...
0x180046914  mov     [rsp+0C0h+var_98], rax
0x180046919  mov     [rsp+0C0h+var_A0], r13
0x18004691e  mov     r8d, 1
0x180046924  mov     r9d, r8d
0x180046927  xor     edx, edx
0x180046929  xor     ecx, ecx
0x18004692b  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180046930  mov     edx, 110h
0x180046935  jmp     short loc_180046957
0x180046937  test    rbx, rbx
0x18004693a  jz      short loc_1800469A8
0x18004693c  mov     r8, rbx; void *
0x18004693f  lea     rdx, [rbp+4Fh+var_48]; int *
0x180046943  mov     rcx, r15; this
0x180046946  call    ?IsAdmin@CSusSecurityChecker@@QEAAJPEAHPEAX@Z; CSusSecurityChecker::IsAdmin(int *,void *)
0x18004694b  mov     r14d, eax
0x18004694e  test    eax, eax
0x180046950  jns     short loc_180046966
0x180046952  mov     edx, 115h
0x180046957  lea     rdi, aCW1SSrcClientE_8; "C:\\__w\\1\\s\\src\\Client\\Engine\\lib"...
0x18004695e  mov     r9d, r14d
0x180046961  mov     r8, rdi
0x180046964  jmp     short loc_180046988
0x180046966  lea     rdx, [rsi+70h]
0x18004696a  mov     rcx, rbx; TokenHandle
0x18004696d  call    GetUserSidFromToken
0x180046972  mov     r14d, eax
0x180046975  test    eax, eax
0x180046977  jns     short loc_1800469A8
0x180046979  mov     r9d, eax; char *
0x18004697c  lea     r8, aCW1SSrcClientE_8; "C:\\__w\\1\\s\\src\\Client\\Engine\\lib"...
0x180046983  mov     edx, 116h; void *
0x180046988  mov     rcx, [rbp+57h]; this
0x18004698c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180046991  nop
0x180046992  test    rbx, rbx
0x180046995  jz      short loc_1800469A0
0x180046997  mov     rcx, rbx; hObject
0x18004699a  call    cs:__imp_CloseHandle
0x1800469a0  mov     eax, r14d
0x1800469a3  jmp     loc_180046B24
0x1800469a8  test    rbx, rbx
0x1800469ab  jz      short loc_1800469BF
0x1800469ad  mov     rcx, rbx; hObject
0x1800469b0  call    cs:__imp_CloseHandle
0x1800469b6  jmp     short loc_1800469BF
0x1800469b8  mov     dword ptr [rsi+50h], 0FFFFFFFFh
0x1800469bf  lea     rcx, [rsi+18h]; this
0x1800469c3  mov     rdx, rdi; void *
0x1800469c6  call    ?Init@CTokenCache@@QEAAJPEAX@Z; CTokenCache::Init(void *)
0x1800469cb  mov     ebx, eax
0x1800469cd  test    eax, eax
0x1800469cf  jns     short loc_1800469E1
0x1800469d1  cmp     [rsi+64h], r13d
0x1800469d5  jz      short loc_1800469E1
0x1800469d7  mov     edx, 125h
0x1800469dc  jmp     loc_180046657
0x1800469e1  mov     rcx, rsi; this
0x1800469e4  call    ?IsDefAppsTestHookEnabled@CCallerIdentity@@AEBA_NXZ; CCallerIdentity::IsDefAppsTestHookEnabled(void)
0x1800469e9  test    al, al
0x1800469eb  jz      short loc_180046A66
0x1800469ed  mov     [rbp+4Fh+hObject], r13
0x1800469f1  lea     rdx, [rbp+4Fh+hObject]; void **
0x1800469f5  call    ?GetDefAppsToken@CCallerIdentity@@AEBAJPEAPEAX@Z; CCallerIdentity::GetDefAppsToken(void * *)
0x1800469fa  mov     ebx, eax
0x1800469fc  test    eax, eax
0x1800469fe  jns     short loc_180046A07
0x180046a00  mov     edx, 12Ah
0x180046a05  jmp     short loc_180046A2B
0x180046a07  mov     rcx, [r12]; lpMem
0x180046a0b  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x180046a10  mov     [r12], r13
0x180046a14  mov     rdx, r12
0x180046a17  mov     rcx, [rbp+4Fh+hObject]; TokenHandle
0x180046a1b  call    GetUserSidFromToken
  ... truncated ...
```
