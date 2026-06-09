# CCallerIdentity::GetDefAppsToken(void * *)

- ea: `0x180046c7c`
- end: `0x180046df6`
- name: `?GetDefAppsToken@CCallerIdentity@@AEBAJPEAPEAX@Z`
- size: `378`
- prototype: `int(CCallerIdentity *__hidden this, void **)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800465f0`

## callees

- `0x180002214`
- `0x180003180`
- `0x180009d3c`
- `0x18000a694`
- `0x180045fa8`
- `0x180046014`
- `0x180046c7c`
- `0x180061960`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180046cfc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180046d68`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180046dd2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180046cfc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180046d68`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180046dd2`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180046d40`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180046d40`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CCallerIdentity::GetDefAppsToken(CCallerIdentity *this, void **a2)
{
  int IsQueryUserTokenPresent; // ebx
  __int64 v4; // rdx
  int *v5; // r9
  HANDLE v6; // rcx
  const char *v7; // r9
  __int64 v8; // rdx
  TOKEN_TYPE TokenType; // [rsp+20h] [rbp-30h]
  HANDLE hObject; // [rsp+30h] [rbp-20h] BYREF
  int v12; // [rsp+38h] [rbp-18h] BYREF
  void *v13; // [rsp+3Ch] [rbp-14h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+8h]

  hObject = 0;
  LODWORD(v13) = 0;
  v12 = 0;
  IsQueryUserTokenPresent = WUSystemInterfaceHelper::IsQueryUserTokenPresent((WUSystemInterfaceHelper *)&v12, (int *)a2);
  if ( IsQueryUserTokenPresent < 0 )
  {
    v4 = 649;
LABEL_18:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\lib\\susenginelib\\calleridentity.cpp",
      (const char *)(unsigned int)IsQueryUserTokenPresent,
      TokenType);
    goto LABEL_20;
  }
  if ( !v12 )
  {
    IsQueryUserTokenPresent = -2145124266;
    v4 = 650;
    goto LABEL_18;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_HandleNullUserToken_57723278>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_HandleNullUserToken_57723278>::GetImpl'::`2'::impl) )
  {
    IsQueryUserTokenPresent = QueryUserToken(0, &hObject);
    if ( IsQueryUserTokenPresent < 0 )
    {
      v4 = 654;
      goto LABEL_18;
    }
    v6 = hObject;
  }
  else
  {
    IsQueryUserTokenPresent = WUSystemInterfaceHelper::QueryUserToken(0, (unsigned int)&hObject, &v13, v5);
    if ( IsQueryUserTokenPresent < 0 )
    {
      v4 = 659;
      goto LABEL_18;
    }
    if ( !(_DWORD)v13 )
    {
      v8 = 660;
      goto LABEL_11;
    }
    v6 = hObject;
    if ( !hObject )
    {
      IsQueryUserTokenPresent = -2147023888;
      v4 = 661;
      goto LABEL_18;
    }
  }
  if ( !DuplicateTokenEx(v6, 0xEu, 0, SecurityImpersonation, TokenImpersonation, a2) )
  {
    v8 = 669;
LABEL_11:
    IsQueryUserTokenPresent = wil::details::in1diag3::Return_GetLastError(
                                retaddr,
                                (void *)v8,
                                (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\lib\\susenginelib\\calleridentity.cpp",
                                v7);
    goto LABEL_20;
  }
  IsQueryUserTokenPresent = 0;
LABEL_20:
  if ( hObject )
    CloseHandle(hObject);
  return (unsigned int)IsQueryUserTokenPresent;
}

```

## disassembly

```asm
0x180046c7c  mov     [rsp-8+arg_0], rbx
0x180046c81  mov     [rsp-8+arg_10], rdi
0x180046c86  push    rbp
0x180046c87  mov     rbp, rsp
0x180046c8a  sub     rsp, 50h
0x180046c8e  mov     rax, cs:__security_cookie
0x180046c95  xor     rax, rsp
0x180046c98  mov     [rbp+var_14+4], rax
0x180046c9c  mov     rdi, rdx
0x180046c9f  mov     [rbp+hObject], 0
0x180046ca7  mov     dword ptr [rbp+var_14], 0
0x180046cae  mov     [rbp+var_18], 0
0x180046cb5  lea     rcx, [rbp+var_18]; this
0x180046cb9  call    ?IsQueryUserTokenPresent@WUSystemInterfaceHelper@@YAJPEAH@Z; WUSystemInterfaceHelper::IsQueryUserTokenPresent(int *)
0x180046cbe  mov     ebx, eax
0x180046cc0  test    eax, eax
0x180046cc2  jns     short loc_180046CCE
0x180046cc4  mov     edx, 289h
0x180046cc9  jmp     loc_180046DB2
0x180046cce  cmp     [rbp+var_18], 0
0x180046cd2  jnz     short loc_180046CE3
0x180046cd4  mov     ebx, 80240056h
0x180046cd9  mov     edx, 28Ah
0x180046cde  jmp     loc_180046DB2
0x180046ce3  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Containment_UUS_HandleNullUserToken_57723278@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_HandleNullUserToken_57723278@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_HandleNullUserToken_57723278> `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_HandleNullUserToken_57723278>::GetImpl(void)'::`2'::impl
0x180046cea  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_HandleNullUserToken_57723278@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_HandleNullUserToken_57723278>::__private_IsEnabled(void)
0x180046cef  mov     rcx, [rbp+hObject]; hObject
0x180046cf3  test    al, al
0x180046cf5  jz      short loc_180046D63
0x180046cf7  test    rcx, rcx
0x180046cfa  jz      short loc_180046D0A
0x180046cfc  call    cs:__imp_CloseHandle
0x180046d02  mov     [rbp+hObject], 0
0x180046d0a  lea     rdx, [rbp+hObject]
0x180046d0e  xor     ecx, ecx
0x180046d10  call    QueryUserToken
0x180046d15  mov     ebx, eax
0x180046d17  test    eax, eax
0x180046d19  jns     short loc_180046D25
0x180046d1b  mov     edx, 28Eh
0x180046d20  jmp     loc_180046DB2
0x180046d25  mov     rcx, [rbp+hObject]; hExistingToken
0x180046d29  mov     [rsp+50h+phNewToken], rdi; phNewToken
0x180046d2e  mov     r9d, 2; ImpersonationLevel
0x180046d34  mov     [rsp+50h+TokenType], r9d; TokenType
0x180046d39  xor     r8d, r8d; lpTokenAttributes
0x180046d3c  lea     edx, [r9+0Ch]; dwDesiredAccess
0x180046d40  call    cs:__imp_DuplicateTokenEx
0x180046d46  test    eax, eax
0x180046d48  jnz     short loc_180046DC7
0x180046d4a  mov     edx, 29Dh; void *
0x180046d4f  lea     r8, aCW1SSrcClientE_8; "C:\\__w\\1\\s\\src\\Client\\Engine\\lib"...
0x180046d56  mov     rcx, [rbp+8]; this
0x180046d5a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180046d5f  mov     ebx, eax
0x180046d61  jmp     short loc_180046DC9
0x180046d63  test    rcx, rcx
0x180046d66  jz      short loc_180046D76
0x180046d68  call    cs:__imp_CloseHandle
0x180046d6e  mov     [rbp+hObject], 0
0x180046d76  lea     r8, [rbp+var_14]; void **
0x180046d7a  lea     rdx, [rbp+hObject]; unsigned int
0x180046d7e  xor     ecx, ecx; this
0x180046d80  call    ?QueryUserToken@WUSystemInterfaceHelper@@YAJKPEAPEAXPEAH@Z; WUSystemInterfaceHelper::QueryUserToken(ulong,void * *,int *)
0x180046d85  mov     ebx, eax
0x180046d87  test    eax, eax
0x180046d89  jns     short loc_180046D92
0x180046d8b  mov     edx, 293h
0x180046d90  jmp     short loc_180046DB2
0x180046d92  cmp     dword ptr [rbp+var_14], 0
0x180046d96  jnz     short loc_180046D9F
0x180046d98  mov     edx, 294h
0x180046d9d  jmp     short loc_180046D4F
0x180046d9f  mov     rcx, [rbp+hObject]
0x180046da3  test    rcx, rcx
0x180046da6  jnz     short loc_180046D29
0x180046da8  mov     ebx, 800703F0h
0x180046dad  mov     edx, 295h; void *
0x180046db2  lea     r8, aCW1SSrcClientE_8; "C:\\__w\\1\\s\\src\\Client\\Engine\\lib"...
0x180046db9  mov     r9d, ebx; char *
0x180046dbc  mov     rcx, [rbp+8]; this
0x180046dc0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180046dc5  jmp     short loc_180046DC9
0x180046dc7  xor     ebx, ebx
0x180046dc9  mov     rcx, [rbp+hObject]; hObject
0x180046dcd  test    rcx, rcx
0x180046dd0  jz      short loc_180046DD8
0x180046dd2  call    cs:__imp_CloseHandle
0x180046dd8  mov     eax, ebx
0x180046dda  mov     rcx, [rbp+var_14+4]
0x180046dde  xor     rcx, rsp; StackCookie
0x180046de1  call    __security_check_cookie
0x180046de6  mov     rbx, [rsp+50h+arg_0]
0x180046deb  mov     rdi, [rsp+50h+arg_10]
0x180046df0  add     rsp, 50h
0x180046df4  pop     rbp
0x180046df5  retn
```
