# CCallerIdentity::GetDefAppsToken(void * *)

- ea: `0x140039010`
- end: `0x14003918a`
- name: `?GetDefAppsToken@CCallerIdentity@@AEBAJPEAPEAX@Z`
- size: `378`
- prototype: `__int64 __fastcall(CCallerIdentity *this, void **)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140038a68`

## callees

- `0x140008de4`
- `0x140008e08`
- `0x140010368`
- `0x140010a58`
- `0x1400190c0`
- `0x14001912c`
- `0x140039010`
- `0x140045dc0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140039090`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400390fc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140039166`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140039090`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400390fc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140039166`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1400390d4`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1400390d4`

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
  if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_HandleNullUserToken_57723278>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_HandleNullUserToken_57723278>::GetImpl'::`2'::impl) )
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
0x140039010  mov     [rsp-8+arg_0], rbx
0x140039015  mov     [rsp-8+arg_10], rdi
0x14003901a  push    rbp
0x14003901b  mov     rbp, rsp
0x14003901e  sub     rsp, 50h
0x140039022  mov     rax, cs:__security_cookie
0x140039029  xor     rax, rsp
0x14003902c  mov     [rbp+var_14+4], rax
0x140039030  mov     rdi, rdx
0x140039033  mov     [rbp+hObject], 0
0x14003903b  mov     dword ptr [rbp+var_14], 0
0x140039042  mov     [rbp+var_18], 0
0x140039049  lea     rcx, [rbp+var_18]; this
0x14003904d  call    ?IsQueryUserTokenPresent@WUSystemInterfaceHelper@@YAJPEAH@Z; WUSystemInterfaceHelper::IsQueryUserTokenPresent(int *)
0x140039052  mov     ebx, eax
0x140039054  test    eax, eax
0x140039056  jns     short loc_140039062
0x140039058  mov     edx, 289h
0x14003905d  jmp     loc_140039146
0x140039062  cmp     [rbp+var_18], 0
0x140039066  jnz     short loc_140039077
0x140039068  mov     ebx, 80240056h
0x14003906d  mov     edx, 28Ah
0x140039072  jmp     loc_140039146
0x140039077  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Containment_UUS_HandleNullUserToken_57723278@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_HandleNullUserToken_57723278@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_HandleNullUserToken_57723278> `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_HandleNullUserToken_57723278>::GetImpl(void)'::`2'::impl
0x14003907e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_HandleNullUserToken_57723278@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_HandleNullUserToken_57723278>::__private_IsEnabled(void)
0x140039083  mov     rcx, [rbp+hObject]; hObject
0x140039087  test    al, al
0x140039089  jz      short loc_1400390F7
0x14003908b  test    rcx, rcx
0x14003908e  jz      short loc_14003909E
0x140039090  call    cs:__imp_CloseHandle
0x140039096  mov     [rbp+hObject], 0
0x14003909e  lea     rdx, [rbp+hObject]
0x1400390a2  xor     ecx, ecx
0x1400390a4  call    QueryUserToken
0x1400390a9  mov     ebx, eax
0x1400390ab  test    eax, eax
0x1400390ad  jns     short loc_1400390B9
0x1400390af  mov     edx, 28Eh
0x1400390b4  jmp     loc_140039146
0x1400390b9  mov     rcx, [rbp+hObject]; hExistingToken
0x1400390bd  mov     [rsp+50h+phNewToken], rdi; phNewToken
0x1400390c2  mov     r9d, 2; ImpersonationLevel
0x1400390c8  mov     [rsp+50h+TokenType], r9d; TokenType
0x1400390cd  xor     r8d, r8d; lpTokenAttributes
0x1400390d0  lea     edx, [r9+0Ch]; dwDesiredAccess
0x1400390d4  call    cs:__imp_DuplicateTokenEx
0x1400390da  test    eax, eax
0x1400390dc  jnz     short loc_14003915B
0x1400390de  mov     edx, 29Dh; void *
0x1400390e3  lea     r8, aCW1SSrcClientE_3; "C:\\__w\\1\\s\\src\\Client\\Engine\\lib"...
0x1400390ea  mov     rcx, [rbp+8]; this
0x1400390ee  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1400390f3  mov     ebx, eax
0x1400390f5  jmp     short loc_14003915D
0x1400390f7  test    rcx, rcx
0x1400390fa  jz      short loc_14003910A
0x1400390fc  call    cs:__imp_CloseHandle
0x140039102  mov     [rbp+hObject], 0
0x14003910a  lea     r8, [rbp+var_14]; void **
0x14003910e  lea     rdx, [rbp+hObject]; unsigned int
0x140039112  xor     ecx, ecx; this
0x140039114  call    ?QueryUserToken@WUSystemInterfaceHelper@@YAJKPEAPEAXPEAH@Z; WUSystemInterfaceHelper::QueryUserToken(ulong,void * *,int *)
0x140039119  mov     ebx, eax
0x14003911b  test    eax, eax
0x14003911d  jns     short loc_140039126
0x14003911f  mov     edx, 293h
0x140039124  jmp     short loc_140039146
0x140039126  cmp     dword ptr [rbp+var_14], 0
0x14003912a  jnz     short loc_140039133
0x14003912c  mov     edx, 294h
0x140039131  jmp     short loc_1400390E3
0x140039133  mov     rcx, [rbp+hObject]
0x140039137  test    rcx, rcx
0x14003913a  jnz     short loc_1400390BD
0x14003913c  mov     ebx, 800703F0h
0x140039141  mov     edx, 295h; void *
0x140039146  lea     r8, aCW1SSrcClientE_3; "C:\\__w\\1\\s\\src\\Client\\Engine\\lib"...
0x14003914d  mov     r9d, ebx; char *
0x140039150  mov     rcx, [rbp+8]; this
0x140039154  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140039159  jmp     short loc_14003915D
0x14003915b  xor     ebx, ebx
0x14003915d  mov     rcx, [rbp+hObject]; hObject
0x140039161  test    rcx, rcx
0x140039164  jz      short loc_14003916C
0x140039166  call    cs:__imp_CloseHandle
0x14003916c  mov     eax, ebx
0x14003916e  mov     rcx, [rbp+var_14+4]
0x140039172  xor     rcx, rsp; StackCookie
0x140039175  call    __security_check_cookie
0x14003917a  mov     rbx, [rsp+50h+arg_0]
0x14003917f  mov     rdi, [rsp+50h+arg_10]
0x140039184  add     rsp, 50h
0x140039188  pop     rbp
0x140039189  retn
```
