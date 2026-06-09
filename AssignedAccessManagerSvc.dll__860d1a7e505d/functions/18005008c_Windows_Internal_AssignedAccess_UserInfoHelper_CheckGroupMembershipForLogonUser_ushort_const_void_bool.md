# Windows::Internal::AssignedAccess::UserInfoHelper::CheckGroupMembershipForLogonUser(ushort const *,void *,bool &)

- ea: `0x18005008c`
- end: `0x1800501d1`
- name: `?CheckGroupMembershipForLogonUser@UserInfoHelper@AssignedAccess@Internal@Windows@@CAJPEBGPEAXAEA_N@Z`
- size: `325`
- prototype: `static int(const unsigned __int16 *, void *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180050980`

## callees

- `0x180008e90`
- `0x18000b694`
- `0x18000b6b4`
- `0x180022cdc`
- `0x180025de8`
- `0x18004f4d4`
- `0x18005008c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18005019d`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18005019d`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x180050172`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x180050172`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x180050134`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x180050134`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Internal::AssignedAccess::UserInfoHelper::CheckGroupMembershipForLogonUser(
        const unsigned __int16 *a1,
        void *a2,
        bool *a3)
{
  int v5; // eax
  unsigned int LastError; // ebx
  __int64 v7; // r9
  __int64 v8; // rdx
  bool v9; // zf
  char *v10; // rax
  const char *v11; // r9
  __int64 v12; // rdx
  int v13; // eax
  WINBOOL IsMember; // [rsp+20h] [rbp-20h] BYREF
  void *phToken; // [rsp+28h] [rbp-18h] BYREF
  unsigned __int64 v17; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  bool v19; // [rsp+70h] [rbp+30h] BYREF
  ULONG SessionId; // [rsp+78h] [rbp+38h] BYREF

  v19 = 0;
  SessionId = 0;
  v17 = 0;
  phToken = 0;
  *a3 = 0;
  v5 = Windows::Internal::AssignedAccess::UserSessionHelper::LookupUserSession(a1, &v19, &SessionId, &v17);
  LastError = v5;
  if ( v5 >= 0 )
  {
    if ( !v19 )
    {
      LastError = -2147023584;
      v7 = 2147943712LL;
      v8 = 186;
      goto LABEL_5;
    }
    v9 = (unsigned __int8)IsWTSEnumerateSessionsWPresent() == 0;
    v10 = (char *)phToken - 1;
    if ( v9 )
    {
      if ( (unsigned __int64)v10 <= 0xFFFFFFFFFFFFFFFDuLL )
        wil::details::close_invoke_helper<1,int (*)(void *),&int CloseHandle(void *),void *>::close_reset(phToken);
      phToken = 0;
      v13 = UMgrQueryUserToken(v17, &phToken);
      LastError = v13;
      if ( v13 < 0 )
      {
        v7 = (unsigned int)v13;
        v8 = 194;
        goto LABEL_5;
      }
    }
    else
    {
      if ( (unsigned __int64)v10 <= 0xFFFFFFFFFFFFFFFDuLL )
        wil::details::close_invoke_helper<1,int (*)(void *),&int CloseHandle(void *),void *>::close_reset(phToken);
      phToken = 0;
      if ( !WTSQueryUserToken(SessionId, &phToken) )
      {
        v12 = 190;
LABEL_11:
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)v12,
                      (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\userinfohelper.cpp",
                      v11);
        goto LABEL_19;
      }
    }
    IsMember = 0;
    if ( CheckTokenMembership(phToken, a2, &IsMember) )
    {
      *a3 = IsMember != 0;
      LastError = 0;
      goto LABEL_19;
    }
    v12 = 198;
    goto LABEL_11;
  }
  v7 = (unsigned int)v5;
  v8 = 184;
LABEL_5:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v8,
    (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\userinfohelper.cpp",
    (const char *)v7,
    IsMember);
LABEL_19:
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&phToken);
  return LastError;
}

```

## disassembly

```asm
0x18005008c  mov     [rsp-18h+arg_0], rbx
0x180050091  push    rbp
0x180050092  push    rsi
0x180050093  push    rdi
0x180050094  mov     rbp, rsp
0x180050097  sub     rsp, 40h
0x18005009b  mov     rdi, r8
0x18005009e  mov     rsi, rdx
0x1800500a1  mov     [rbp+arg_10], 0
0x1800500a5  mov     [rbp+SessionId], 0
0x1800500ac  mov     [rbp+var_10], 0
0x1800500b4  mov     [rbp+phToken], 0
0x1800500bc  mov     byte ptr [r8], 0
0x1800500c0  lea     r9, [rbp+var_10]; unsigned __int64 *
0x1800500c4  lea     r8, [rbp+SessionId]; unsigned int *
0x1800500c8  lea     rdx, [rbp+arg_10]; bool *
0x1800500cc  call    ?LookupUserSession@UserSessionHelper@AssignedAccess@Internal@Windows@@SAJPEBGAEA_NAEAKAEA_K@Z; Windows::Internal::AssignedAccess::UserSessionHelper::LookupUserSession(ushort const *,bool &,ulong &,unsigned __int64 &)
0x1800500d1  mov     ebx, eax
0x1800500d3  test    eax, eax
0x1800500d5  jns     short loc_1800500E1
0x1800500d7  mov     r9d, eax
0x1800500da  mov     edx, 0B8h
0x1800500df  jmp     short loc_1800500F4
0x1800500e1  cmp     [rbp+arg_10], 0
0x1800500e5  jnz     short loc_180050109
0x1800500e7  mov     ebx, 80070520h
0x1800500ec  mov     r9d, ebx; char *
0x1800500ef  mov     edx, 0BAh; void *
0x1800500f4  mov     rcx, [rbp+18h]; this
0x1800500f8  lea     r8, aOnecoreuapBase_94; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x1800500ff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180050104  jmp     loc_1800501B9
0x180050109  call    IsWTSEnumerateSessionsWPresent
0x18005010e  mov     rcx, [rbp+phToken]; hObject
0x180050112  test    al, al
0x180050114  lea     rax, [rcx-1]
0x180050118  jz      short loc_180050157
0x18005011a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18005011e  ja      short loc_180050125
0x180050120  call    ?close_reset@?$close_invoke_helper@$00P6AHPEAX@Z$1?CloseHandle@@YAH0@ZPEAX@details@wil@@SAXPEAX@Z; wil::details::close_invoke_helper<1,int (*)(void *),&CloseHandle(void *),void *>::close_reset(void *)
0x180050125  mov     [rbp+phToken], 0
0x18005012d  lea     rdx, [rbp+phToken]; phToken
0x180050131  mov     ecx, [rbp+SessionId]; SessionId
0x180050134  call    cs:__imp_WTSQueryUserToken
0x18005013a  test    eax, eax
0x18005013c  jnz     short loc_18005018B
0x18005013e  mov     edx, 0BEh; void *
0x180050143  lea     r8, aOnecoreuapBase_94; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x18005014a  mov     rcx, [rbp+18h]; this
0x18005014e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180050153  mov     ebx, eax
0x180050155  jmp     short loc_1800501B9
0x180050157  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18005015b  ja      short loc_180050162
0x18005015d  call    ?close_reset@?$close_invoke_helper@$00P6AHPEAX@Z$1?CloseHandle@@YAH0@ZPEAX@details@wil@@SAXPEAX@Z; wil::details::close_invoke_helper<1,int (*)(void *),&CloseHandle(void *),void *>::close_reset(void *)
0x180050162  mov     [rbp+phToken], 0
0x18005016a  lea     rdx, [rbp+phToken]
0x18005016e  mov     rcx, [rbp+var_10]
0x180050172  call    cs:__imp_UMgrQueryUserToken
0x180050178  mov     ebx, eax
0x18005017a  test    eax, eax
0x18005017c  jns     short loc_18005018B
0x18005017e  mov     r9d, eax
0x180050181  mov     edx, 0C2h
0x180050186  jmp     loc_1800500F4
0x18005018b  mov     [rbp+IsMember], 0
0x180050192  lea     r8, [rbp+IsMember]; IsMember
0x180050196  mov     rdx, rsi; SidToCheck
0x180050199  mov     rcx, [rbp+phToken]; TokenHandle
0x18005019d  call    cs:__imp_CheckTokenMembership
0x1800501a3  test    eax, eax
0x1800501a5  jnz     short loc_1800501AE
0x1800501a7  mov     edx, 0C6h
0x1800501ac  jmp     short loc_180050143
0x1800501ae  cmp     [rbp+IsMember], 0
0x1800501b2  setnz   al
0x1800501b5  mov     [rdi], al
0x1800501b7  xor     ebx, ebx
0x1800501b9  lea     rcx, [rbp+phToken]
0x1800501bd  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800501c2  mov     eax, ebx
0x1800501c4  mov     rbx, [rsp+40h+arg_0]
0x1800501c9  add     rsp, 40h
0x1800501cd  pop     rdi
0x1800501ce  pop     rsi
0x1800501cf  pop     rbp
0x1800501d0  retn
```
