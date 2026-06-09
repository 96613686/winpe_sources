# CLocationUserInfoHelper::ImpersonateActiveUser(bool,ATL::CAccessToken &)

- ea: `0x180011fa0`
- end: `0x18001218d`
- name: `?ImpersonateActiveUser@CLocationUserInfoHelper@@UEAAJ_NAEAVCAccessToken@ATL@@@Z`
- size: `493`
- prototype: `__int64 __fastcall(CLocationUserInfoHelper *__hidden this, bool, struct ATL::CAccessToken *)`
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800116f0`
- `0x180011bc0`

## callees

- `0x180011fa0`
- `0x180012194`
- `0x1800121bc`
- `0x18001e170`
- `0x18001efe0`
- `0x18001f09c`
- `0x18001f334`
- `0x18008f888`
- `0x1800a98c0`
- `0x1800aa5ac`
- `0x18015e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001210e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001210e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011fdc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011fdc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180012008`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180012015`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180012008`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180012015`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180012041`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180012041`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800120b4`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800120b4`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CLocationUserInfoHelper::ImpersonateActiveUser(
        CLocationUserInfoHelper *this,
        char a2,
        struct ATL::CAccessToken *a3)
{
  struct _RTL_CRITICAL_SECTION *v6; // rsi
  HANDLE CurrentProcess; // rbx
  void *v8; // rdi
  HANDLE v9; // rax
  wil::details *v10; // rcx
  unsigned int LastErrorFailHr; // ebx
  HANDLE v12; // rbx
  char *v14; // [rsp+40h] [rbp-C0h] BYREF
  char v15; // [rsp+48h] [rbp-B8h]
  HANDLE TargetHandle; // [rsp+50h] [rbp-B0h] BYREF
  void **v17; // [rsp+58h] [rbp-A8h] BYREF
  HANDLE v18; // [rsp+60h] [rbp-A0h]
  __int128 v19; // [rsp+68h] [rbp-98h]
  _BYTE v20[8]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE pSid[120]; // [rsp+88h] [rbp-78h] BYREF

  v6 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 24);
  v14 = (char *)this + 24;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  v15 = 1;
  TargetHandle = 0;
  if ( !*((_BYTE *)this + 80) || a2 && !*((_BYTE *)this + 120) )
  {
    LastErrorFailHr = -2147024664;
    goto LABEL_14;
  }
  CurrentProcess = GetCurrentProcess();
  v8 = (void *)*((_QWORD *)this + 13);
  v9 = GetCurrentProcess();
  if ( DuplicateHandle(v9, v8, CurrentProcess, &TargetHandle, 0, 0, 2u) )
  {
    v17 = &ATL::CAccessToken::`vftable';
    v19 = 0;
    v18 = TargetHandle;
    memset_0(v20, 0, 0x78u);
    ATL::CSid::CSid((ATL::CSid *)v20);
    if ( ATL::CAccessToken::GetInfoConvert<ATL::CSid,_TOKEN_USER>((__int64)&v17, (__int64)v20) )
    {
      if ( !pSid[68] || !IsValidSid(pSid) )
      {
        ATL::CSid::~CSid((ATL::CSid *)v20);
        v17 = &ATL::CAccessToken::`vftable';
        ATL::CAccessToken::Clear((ATL::CAccessToken *)&v17);
        LastErrorFailHr = -2147023559;
        goto LABEL_14;
      }
      if ( ATL::CAccessToken::ImpersonateLoggedOnUser((ATL::CAccessToken *)&v17) )
      {
        v12 = v18;
        v18 = 0;
        ((void (__fastcall *)(void ***))v17[1])(&v17);
        *((_QWORD *)a3 + 1) = v12;
        ATL::CSid::~CSid((ATL::CSid *)v20);
        v17 = &ATL::CAccessToken::`vftable';
        ATL::CAccessToken::Clear((ATL::CAccessToken *)&v17);
        LeaveCriticalSection(v6);
        return 0;
      }
    }
    ATL::CSid::~CSid((ATL::CSid *)v20);
    v17 = &ATL::CAccessToken::`vftable';
    ATL::CAccessToken::Clear((ATL::CAccessToken *)&v17);
    LastErrorFailHr = -2147023537;
    goto LABEL_14;
  }
  LastErrorFailHr = wil::details::GetLastErrorFailHr(v10);
LABEL_14:
  ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(&v14);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x180011fa0  mov     [rsp-8+arg_8], rbx
0x180011fa5  mov     [rsp-8+arg_18], rsi
0x180011faa  push    rbp
0x180011fab  push    rdi
0x180011fac  push    r14
0x180011fae  lea     rbp, [rsp-10h]
0x180011fb3  sub     rsp, 110h
0x180011fba  mov     rax, cs:__security_cookie
0x180011fc1  xor     rax, rsp
0x180011fc4  mov     [rbp+20h+var_20], rax
0x180011fc8  mov     r14, r8
0x180011fcb  mov     bl, dl
0x180011fcd  mov     rdi, rcx
0x180011fd0  lea     rsi, [rcx+18h]
0x180011fd4  mov     [rsp+120h+var_E0], rsi
0x180011fd9  mov     rcx, rsi; lpCriticalSection
0x180011fdc  call    cs:__imp_EnterCriticalSection
0x180011fe2  mov     [rsp+120h+var_D8], 1
0x180011fe7  mov     [rsp+120h+TargetHandle], 0
0x180011ff0  cmp     byte ptr [rdi+50h], 0
0x180011ff4  jz      loc_180012158
0x180011ffa  test    bl, bl
0x180011ffc  jz      short loc_180012008
0x180011ffe  cmp     byte ptr [rdi+78h], 0
0x180012002  jz      loc_180012158
0x180012008  call    cs:__imp_GetCurrentProcess
0x18001200e  mov     rbx, rax
0x180012011  mov     rdi, [rdi+68h]
0x180012015  call    cs:__imp_GetCurrentProcess
0x18001201b  mov     [rsp+120h+dwOptions], 2; dwOptions
0x180012023  mov     [rsp+120h+bInheritHandle], 0; bInheritHandle
0x18001202b  mov     [rsp+120h+dwDesiredAccess], 0; dwDesiredAccess
0x180012033  lea     r9, [rsp+120h+TargetHandle]; lpTargetHandle
0x180012038  mov     r8, rbx; hTargetProcessHandle
0x18001203b  mov     rdx, rdi; hSourceHandle
0x18001203e  mov     rcx, rax; hSourceProcessHandle
0x180012041  call    cs:__imp_DuplicateHandle
0x180012047  test    eax, eax
0x180012049  jnz     short loc_180012057
0x18001204b  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180012050  mov     ebx, eax
0x180012052  jmp     loc_18001215D
0x180012057  xorps   xmm0, xmm0
0x18001205a  movups  [rsp+120h+var_C8], xmm0
0x18001205f  lea     rdi, ??_7CAccessToken@ATL@@6B@; const ATL::CAccessToken::`vftable'
0x180012066  mov     qword ptr [rsp+120h+var_C8], rdi
0x18001206b  movdqu  [rsp+120h+var_B8], xmm0
0x180012071  mov     rax, [rsp+120h+TargetHandle]
0x180012076  mov     qword ptr [rsp+120h+var_C8+8], rax
0x18001207b  xor     edx, edx; Val
0x18001207d  lea     r8d, [rdx+78h]; Size
0x180012081  lea     rcx, [rbp+20h+var_A0]; void *
0x180012085  call    memset_0
0x18001208a  lea     rcx, [rbp+20h+var_A0]; this
0x18001208e  call    ??0CSid@ATL@@QEAA@XZ; ATL::CSid::CSid(void)
0x180012093  nop
0x180012094  lea     rdx, [rbp+20h+var_A0]
0x180012098  lea     rcx, [rsp+120h+var_C8]
0x18001209d  call    ??$GetInfoConvert@VCSid@ATL@@U_TOKEN_USER@@@CAccessToken@ATL@@IEBA_NPEAVCSid@1@W4_TOKEN_INFORMATION_CLASS@@PEAU_TOKEN_USER@@@Z; ATL::CAccessToken::GetInfoConvert<ATL::CSid,_TOKEN_USER>(ATL::CSid *,_TOKEN_INFORMATION_CLASS,_TOKEN_USER *)
0x1800120a2  test    al, al
0x1800120a4  jz      loc_180012138
0x1800120aa  cmp     [rbp+20h+var_54], 0
0x1800120ae  jz      short loc_180012118
0x1800120b0  lea     rcx, [rbp+20h+pSid]; pSid
0x1800120b4  call    cs:__imp_IsValidSid
0x1800120ba  test    eax, eax
0x1800120bc  jz      short loc_180012118
0x1800120be  lea     rcx, [rsp+120h+var_C8]; this
0x1800120c3  call    ?ImpersonateLoggedOnUser@CAccessToken@ATL@@QEBA_NXZ; ATL::CAccessToken::ImpersonateLoggedOnUser(void)
0x1800120c8  test    al, al
0x1800120ca  jz      short loc_180012138
0x1800120cc  mov     rbx, qword ptr [rsp+120h+var_C8+8]
0x1800120d1  mov     qword ptr [rsp+120h+var_C8+8], 0
0x1800120da  mov     rax, qword ptr [rsp+120h+var_C8]
0x1800120df  lea     rcx, [rsp+120h+var_C8]
0x1800120e4  mov     rax, [rax+8]
0x1800120e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800120ed  mov     [r14+8], rbx
0x1800120f1  lea     rcx, [rbp+20h+var_A0]; this
0x1800120f5  call    ??1CSid@ATL@@UEAA@XZ; ATL::CSid::~CSid(void)
0x1800120fa  nop
0x1800120fb  mov     qword ptr [rsp+120h+var_C8], rdi
0x180012100  lea     rcx, [rsp+120h+var_C8]; this
0x180012105  call    ?Clear@CAccessToken@ATL@@MEAAXXZ; ATL::CAccessToken::Clear(void)
0x18001210a  nop
0x18001210b  mov     rcx, rsi; lpCriticalSection
0x18001210e  call    cs:__imp_LeaveCriticalSection
0x180012114  xor     eax, eax
0x180012116  jmp     short loc_180012169
0x180012118  lea     rcx, [rbp+20h+var_A0]; this
0x18001211c  call    ??1CSid@ATL@@UEAA@XZ; ATL::CSid::~CSid(void)
0x180012121  nop
0x180012122  mov     qword ptr [rsp+120h+var_C8], rdi
0x180012127  lea     rcx, [rsp+120h+var_C8]; this
0x18001212c  call    ?Clear@CAccessToken@ATL@@MEAAXXZ; ATL::CAccessToken::Clear(void)
0x180012131  mov     ebx, 80070539h
0x180012136  jmp     short loc_18001215D
0x180012138  lea     rcx, [rbp+20h+var_A0]; this
0x18001213c  call    ??1CSid@ATL@@UEAA@XZ; ATL::CSid::~CSid(void)
0x180012141  nop
0x180012142  mov     qword ptr [rsp+120h+var_C8], rdi
0x180012147  lea     rcx, [rsp+120h+var_C8]; this
0x18001214c  call    ?Clear@CAccessToken@ATL@@MEAAXXZ; ATL::CAccessToken::Clear(void)
0x180012151  mov     ebx, 8007054Fh
0x180012156  jmp     short loc_18001215D
0x180012158  mov     ebx, 800700E8h
0x18001215d  lea     rcx, [rsp+120h+var_E0]
0x180012162  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x180012167  mov     eax, ebx
0x180012169  mov     rcx, [rbp+20h+var_20]
0x18001216d  xor     rcx, rsp; StackCookie
0x180012170  call    __security_check_cookie
0x180012175  lea     r11, [rsp+120h+var_10]
0x18001217d  mov     rbx, [r11+28h]
0x180012181  mov     rsi, [r11+38h]
0x180012185  mov     rsp, r11
0x180012188  pop     r14
0x18001218a  pop     rdi
0x18001218b  pop     rbp
0x18001218c  retn
```
