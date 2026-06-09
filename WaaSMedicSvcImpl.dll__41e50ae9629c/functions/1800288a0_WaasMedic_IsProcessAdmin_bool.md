# WaasMedic::IsProcessAdmin(bool &)

- ea: `0x1800288a0`
- end: `0x180028b96`
- name: `?IsProcessAdmin@WaasMedic@@YAJAEA_N@Z`
- size: `758`
- prototype: `__int64 __fastcall(WaasMedic *__hidden this, bool *)`
- caller_count: `6`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180018d3c`
- `0x180049370`
- `0x1800552a0`
- `0x180055510`
- `0x180061790`
- `0x180061d00`

## callees

- `0x180020d88`
- `0x18002805c`
- `0x180028230`
- `0x1800288a0`
- `0x180028ed4`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028915`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028929`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002897f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028993`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028a00`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028a7f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028a93`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028afa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028b0e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028b21`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028b50`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028b64`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028b77`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028915`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028929`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002897f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028993`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028a00`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028a7f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028a93`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028afa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028b0e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028b21`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028b50`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028b64`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028b77`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800289a2`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180028b2f`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180028b85`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800289a2`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180028b2f`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180028b85`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800289ca`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800289ca`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180028a49`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180028a49`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180028ac4`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180028ac4`

## string_xrefs

- `0x1800288e7`: `GetCallerTokenAndRevertToSelf returned error.`
- `0x180028951`: `Failed to allocate local system SID`
- `0x1800288f6`: `onecore\enduser\waasmedic\lib\util\securityutil.cpp`
- `0x180028960`: `onecore\enduser\waasmedic\lib\util\securityutil.cpp`
- `0x1800289df`: `onecore\enduser\waasmedic\lib\util\securityutil.cpp`
- `0x180028a5e`: `onecore\enduser\waasmedic\lib\util\securityutil.cpp`
- `0x180028ad9`: `onecore\enduser\waasmedic\lib\util\securityutil.cpp`
- `0x180028a57`: `Failed to duplicate token`
- `0x1800289d8`: `Failed to get token information`
- `0x180028ad2`: `Failed to check token membership`

## pseudocode

```c
__int64 __fastcall WaasMedic::IsProcessAdmin(WaasMedic *this, bool *a2, __int64 a3, void **a4)
{
  int CallerTokenAndRevertToSelf; // ebx
  HANDLE v7; // rcx
  char *v8; // rdi
  bool v9; // cc
  HANDLE v10; // rcx
  PSID v11; // rbx
  unsigned int LastErrorMsg; // esi
  char *v13; // rcx
  const char *ReturnLength; // [rsp+20h] [rbp-38h]
  const char *phNewToken; // [rsp+28h] [rbp-30h]
  HANDLE v16; // [rsp+30h] [rbp-28h] BYREF
  PSID pSid; // [rsp+38h] [rbp-20h] BYREF
  HANDLE TokenHandle; // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+20h]
  int TokenInformation; // [rsp+80h] [rbp+28h] BYREF
  WINBOOL IsMember; // [rsp+88h] [rbp+30h] BYREF
  DWORD v22; // [rsp+90h] [rbp+38h] BYREF
  HANDLE hObject; // [rsp+98h] [rbp+40h] BYREF

  TokenInformation = 0;
  v22 = 0;
  *(_BYTE *)this = 0;
  hObject = 0;
  TokenHandle = 0;
  CallerTokenAndRevertToSelf = WaasMedic::GetCallerTokenAndRevertToSelf(this, (bool)&TokenHandle, &hObject, a4);
  if ( CallerTokenAndRevertToSelf < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x40C,
      (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\securityutil.cpp",
      (const char *)(unsigned int)CallerTokenAndRevertToSelf,
      (int)"GetCallerTokenAndRevertToSelf returned error.",
      phNewToken);
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(hObject);
    if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(TokenHandle);
    return (unsigned int)CallerTokenAndRevertToSelf;
  }
  pSid = 0;
  CallerTokenAndRevertToSelf = WaasMedic::AllocAdministratorsSid(&pSid);
  if ( CallerTokenAndRevertToSelf < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x40D,
      (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\securityutil.cpp",
      (const char *)(unsigned int)CallerTokenAndRevertToSelf,
      (int)"Failed to allocate local system SID",
      phNewToken);
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(hObject);
    v7 = TokenHandle;
    if ( (char *)TokenHandle - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
      goto LABEL_12;
    goto LABEL_11;
  }
  v8 = (char *)TokenHandle;
  if ( !GetTokenInformation(TokenHandle, TokenType, &TokenInformation, 4u, &v22) )
  {
    CallerTokenAndRevertToSelf = wil::details::in1diag3::Return_GetLastErrorMsg(
                                   retaddr,
                                   (void *)0x418,
                                   (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\securityutil.cpp",
                                   "Failed to get token information",
                                   ReturnLength);
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(hObject);
    v9 = (unsigned __int64)(v8 - 1) <= 0xFFFFFFFFFFFFFFFDuLL;
LABEL_18:
    if ( !v9 )
    {
LABEL_12:
      if ( pSid )
        FreeSid(pSid);
      return (unsigned int)CallerTokenAndRevertToSelf;
    }
    v7 = v8;
LABEL_11:
    CloseHandle(v7);
    goto LABEL_12;
  }
  v10 = v8;
  if ( TokenInformation == 2 )
  {
    v8 = 0;
    v16 = v10;
  }
  else
  {
    v16 = (HANDLE)-1LL;
    if ( !DuplicateTokenEx(v8, 8u, 0, SecurityIdentification, TokenImpersonation, &v16) )
    {
      CallerTokenAndRevertToSelf = wil::details::in1diag3::Return_GetLastErrorMsg(
                                     retaddr,
                                     (void *)0x429,
                                     (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\securityutil.cpp",
                                     "Failed to duplicate token",
                                     ReturnLength);
      if ( (char *)v16 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(v16);
      if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(hObject);
      v9 = (unsigned __int64)(v8 - 1) <= 0xFFFFFFFFFFFFFFFDuLL;
      goto LABEL_18;
    }
    v10 = v16;
  }
  v11 = pSid;
  IsMember = 0;
  if ( CheckTokenMembership(v10, pSid, &IsMember) )
  {
    v13 = (char *)v16;
    *(_BYTE *)this = IsMember != 0;
    if ( (unsigned __int64)(v13 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(v13);
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(hObject);
    if ( (unsigned __int64)(v8 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(v8);
    if ( v11 )
      FreeSid(v11);
    return 0;
  }
  else
  {
    LastErrorMsg = wil::details::in1diag3::Return_GetLastErrorMsg(
                     retaddr,
                     (void *)0x439,
                     (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\securityutil.cpp",
                     "Failed to check token membership",
                     ReturnLength);
    if ( (char *)v16 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(v16);
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(hObject);
    if ( (unsigned __int64)(v8 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(v8);
    if ( v11 )
      FreeSid(v11);
    return LastErrorMsg;
  }
}

```

## disassembly

```asm
0x1800288a0  push    rbp
0x1800288a2  push    rbx
0x1800288a3  push    rsi
0x1800288a4  push    rdi
0x1800288a5  mov     rbp, rsp
0x1800288a8  sub     rsp, 58h
0x1800288ac  lea     r8, [rbp+hObject]; void **
0x1800288b0  mov     [rbp+TokenInformation], 0
0x1800288b7  lea     rdx, [rbp+TokenHandle]; bool
0x1800288bb  mov     [rbp+arg_10], 0
0x1800288c2  mov     rsi, rcx
0x1800288c5  mov     byte ptr [rcx], 0
0x1800288c8  mov     [rbp+hObject], 0
0x1800288d0  mov     [rbp+TokenHandle], 0
0x1800288d8  call    ?GetCallerTokenAndRevertToSelf@WaasMedic@@YAJ_NPEAPEAX1@Z; WaasMedic::GetCallerTokenAndRevertToSelf(bool,void * *,void * *)
0x1800288dd  mov     ebx, eax
0x1800288df  test    eax, eax
0x1800288e1  jns     short loc_180028936
0x1800288e3  mov     rcx, [rbp+20h]; this
0x1800288e7  lea     rax, aGetcallertoken_0; "GetCallerTokenAndRevertToSelf returned "...
0x1800288ee  mov     r9d, ebx; char *
0x1800288f1  mov     [rsp+58h+ReturnLength], rax; int
0x1800288f6  lea     r8, aOnecoreEnduser; "onecore\\enduser\\waasmedic\\lib\\util"...
0x1800288fd  mov     edx, 40Ch; void *
0x180028902  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180028907  mov     rcx, [rbp+hObject]; hObject
0x18002890b  lea     rdx, [rcx-1]
0x18002890f  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180028913  ja      short loc_18002891B
0x180028915  call    cs:__imp_CloseHandle
0x18002891b  mov     rcx, [rbp+TokenHandle]; hObject
0x18002891f  lea     rax, [rcx-1]
0x180028923  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180028927  ja      short loc_18002892F
0x180028929  call    cs:__imp_CloseHandle
0x18002892f  mov     eax, ebx
0x180028931  jmp     loc_180028B8D
0x180028936  lea     rcx, [rbp+pSid]
0x18002893a  mov     [rbp+pSid], 0
0x180028942  call    WaasMedic__AllocAdministratorsSid
0x180028947  mov     ebx, eax
0x180028949  test    eax, eax
0x18002894b  jns     short loc_1800289AA
0x18002894d  mov     rcx, [rbp+20h]; this
0x180028951  lea     rax, aFailedToAlloca_26; "Failed to allocate local system SID"
0x180028958  mov     r9d, ebx; char *
0x18002895b  mov     [rsp+58h+ReturnLength], rax; int
0x180028960  lea     r8, aOnecoreEnduser; "onecore\\enduser\\waasmedic\\lib\\util"...
0x180028967  mov     edx, 40Dh; void *
0x18002896c  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180028971  mov     rcx, [rbp+hObject]; hObject
0x180028975  lea     rdx, [rcx-1]
0x180028979  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18002897d  ja      short loc_180028985
0x18002897f  call    cs:__imp_CloseHandle
0x180028985  mov     rcx, [rbp+TokenHandle]; hObject
0x180028989  lea     rax, [rcx-1]
0x18002898d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180028991  ja      short loc_180028999
0x180028993  call    cs:__imp_CloseHandle
0x180028999  mov     rcx, [rbp+pSid]; pSid
0x18002899d  test    rcx, rcx
0x1800289a0  jz      short loc_18002892F
0x1800289a2  call    cs:__imp_FreeSid
0x1800289a8  jmp     short loc_18002892F
0x1800289aa  mov     rdi, [rbp+TokenHandle]
0x1800289ae  lea     rax, [rbp+arg_10]
0x1800289b2  mov     r9d, 4; TokenInformationLength
0x1800289b8  mov     [rsp+58h+ReturnLength], rax; char *
0x1800289bd  lea     r8, [rbp+TokenInformation]; TokenInformation
0x1800289c1  mov     rcx, rdi; TokenHandle
0x1800289c4  lea     ebx, [r9+4]
0x1800289c8  mov     edx, ebx; TokenInformationClass
0x1800289ca  call    cs:__imp_GetTokenInformation
0x1800289d0  test    eax, eax
0x1800289d2  jnz     short loc_180028A18
0x1800289d4  mov     rcx, [rbp+20h]; this
0x1800289d8  lea     r9, aFailedToGetTok; "Failed to get token information"
0x1800289df  lea     r8, aOnecoreEnduser; "onecore\\enduser\\waasmedic\\lib\\util"...
0x1800289e6  mov     edx, 418h; void *
0x1800289eb  call    ?Return_GetLastErrorMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Return_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x1800289f0  mov     rcx, [rbp+hObject]; hObject
0x1800289f4  mov     ebx, eax
0x1800289f6  lea     rdx, [rcx-1]
0x1800289fa  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1800289fe  ja      short loc_180028A06
0x180028a00  call    cs:__imp_CloseHandle
0x180028a06  lea     rdx, [rdi-1]
0x180028a0a  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180028a0e  ja      short loc_180028999
0x180028a10  mov     rcx, rdi
0x180028a13  jmp     loc_180028993
0x180028a18  cmp     [rbp+TokenInformation], 2
0x180028a1c  mov     rcx, rdi; TokenHandle
0x180028a1f  jz      loc_180028AAC
0x180028a25  lea     rax, [rbp+var_28]
0x180028a29  mov     [rbp+var_28], 0FFFFFFFFFFFFFFFFh
0x180028a31  mov     [rsp+58h+phNewToken], rax; phNewToken
0x180028a36  mov     r9d, 1; ImpersonationLevel
0x180028a3c  xor     r8d, r8d; lpTokenAttributes
0x180028a3f  mov     dword ptr [rsp+58h+ReturnLength], 2; char *
0x180028a47  mov     edx, ebx; dwDesiredAccess
0x180028a49  call    cs:__imp_DuplicateTokenEx
0x180028a4f  test    eax, eax
0x180028a51  jnz     short loc_180028AA6
0x180028a53  mov     rcx, [rbp+20h]; this
0x180028a57  lea     r9, aFailedToDuplic; "Failed to duplicate token"
0x180028a5e  lea     r8, aOnecoreEnduser; "onecore\\enduser\\waasmedic\\lib\\util"...
0x180028a65  mov     edx, 429h; void *
0x180028a6a  call    ?Return_GetLastErrorMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Return_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x180028a6f  mov     rcx, [rbp+var_28]; hObject
0x180028a73  mov     ebx, eax
0x180028a75  lea     rdx, [rcx-1]
0x180028a79  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180028a7d  ja      short loc_180028A85
0x180028a7f  call    cs:__imp_CloseHandle
0x180028a85  mov     rcx, [rbp+hObject]; hObject
0x180028a89  lea     rdx, [rcx-1]
0x180028a8d  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180028a91  ja      short loc_180028A99
0x180028a93  call    cs:__imp_CloseHandle
0x180028a99  lea     rax, [rdi-1]
0x180028a9d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180028aa1  jmp     loc_180028A0E
0x180028aa6  mov     rcx, [rbp+var_28]
0x180028aaa  jmp     short loc_180028AB2
0x180028aac  xor     edi, edi
0x180028aae  mov     [rbp+var_28], rcx
0x180028ab2  mov     rbx, [rbp+pSid]
0x180028ab6  lea     r8, [rbp+IsMember]; IsMember
0x180028aba  mov     rdx, rbx; SidToCheck
0x180028abd  mov     [rbp+IsMember], 0
0x180028ac4  call    cs:__imp_CheckTokenMembership
0x180028aca  test    eax, eax
0x180028acc  jnz     short loc_180028B39
0x180028ace  mov     rcx, [rbp+20h]; this
0x180028ad2  lea     r9, aFailedToCheckT; "Failed to check token membership"
0x180028ad9  lea     r8, aOnecoreEnduser; "onecore\\enduser\\waasmedic\\lib\\util"...
0x180028ae0  mov     edx, 439h; void *
0x180028ae5  call    ?Return_GetLastErrorMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Return_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x180028aea  mov     rcx, [rbp+var_28]; hObject
0x180028aee  mov     esi, eax
0x180028af0  lea     rdx, [rcx-1]
0x180028af4  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180028af8  ja      short loc_180028B00
0x180028afa  call    cs:__imp_CloseHandle
0x180028b00  mov     rcx, [rbp+hObject]; hObject
0x180028b04  lea     rdx, [rcx-1]
0x180028b08  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180028b0c  ja      short loc_180028B14
0x180028b0e  call    cs:__imp_CloseHandle
0x180028b14  lea     rax, [rdi-1]
0x180028b18  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180028b1c  ja      short loc_180028B27
0x180028b1e  mov     rcx, rdi; hObject
0x180028b21  call    cs:__imp_CloseHandle
0x180028b27  test    rbx, rbx
0x180028b2a  jz      short loc_180028B35
0x180028b2c  mov     rcx, rbx; pSid
0x180028b2f  call    cs:__imp_FreeSid
0x180028b35  mov     eax, esi
0x180028b37  jmp     short loc_180028B8D
0x180028b39  cmp     [rbp+IsMember], 0
0x180028b3d  mov     rcx, [rbp+var_28]; hObject
0x180028b41  setnz   al
0x180028b44  mov     [rsi], al
0x180028b46  lea     rax, [rcx-1]
0x180028b4a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180028b4e  ja      short loc_180028B56
0x180028b50  call    cs:__imp_CloseHandle
0x180028b56  mov     rcx, [rbp+hObject]; hObject
0x180028b5a  lea     rax, [rcx-1]
0x180028b5e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180028b62  ja      short loc_180028B6A
0x180028b64  call    cs:__imp_CloseHandle
0x180028b6a  lea     rax, [rdi-1]
0x180028b6e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180028b72  ja      short loc_180028B7D
0x180028b74  mov     rcx, rdi; hObject
0x180028b77  call    cs:__imp_CloseHandle
0x180028b7d  test    rbx, rbx
0x180028b80  jz      short loc_180028B8B
0x180028b82  mov     rcx, rbx; pSid
0x180028b85  call    cs:__imp_FreeSid
0x180028b8b  xor     eax, eax
0x180028b8d  add     rsp, 58h
0x180028b91  pop     rdi
0x180028b92  pop     rsi
0x180028b93  pop     rbx
0x180028b94  pop     rbp
0x180028b95  retn
```
