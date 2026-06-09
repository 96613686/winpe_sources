# ClientContextFromTokenInformation

- ea: `0x1800362f0`
- end: `0x180036446`
- name: `ClientContextFromTokenInformation`
- size: `342`
- prototype: `__int64 __fastcall(PVOID DynamicGroupArgs, PAUTHZ_CLIENT_CONTEXT_HANDLE phAuthzClientContext)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18001b200`

## callees

- `0x18000f1a8`
- `0x180012950`
- `0x180018b74`
- `0x1800362f0`
- `0x180058b30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036366`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036366`
- `AUTHZ!AuthzInitializeContextFromSid` at `0x18003633b`
- `AUTHZ!AuthzInitializeContextFromSid` at `0x18003633b`

## string_xrefs

- `0x18003637c`: `AuthzInitializeContextFromSid`
- `0x1800363af`: `ClientContextFromTokenInformation`

## pseudocode

```c
__int64 __fastcall ClientContextFromTokenInformation(
        PSID **DynamicGroupArgs,
        PAUTHZ_CLIENT_CONTEXT_HANDLE phAuthzClientContext)
{
  __int64 v2; // rbx
  int v4; // r8d
  int v5; // [rsp+40h] [rbp-48h] BYREF
  _BYTE v6[16]; // [rsp+48h] [rbp-40h] BYREF
  const char *v7; // [rsp+58h] [rbp-30h]
  __int64 v8; // [rsp+60h] [rbp-28h]
  int *v9; // [rsp+68h] [rbp-20h]
  __int64 v10; // [rsp+70h] [rbp-18h]

  v2 = 0;
  if ( !AuthzInitializeContextFromSid(
          2u,
          *DynamicGroupArgs[1],
          *((AUTHZ_RESOURCE_MANAGER_HANDLE *)gWfpGlobal + 98),
          0,
          0,
          DynamicGroupArgs,
          phAuthzClientContext) )
  {
    LODWORD(v2) = GetLastError();
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_SsD(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, v4, 0, (__int64)"AuthzInitializeContextFromSid", v2);
    }
    if ( gWfpLogUserModeErrors && (byte_1800F30F5 & 1) != 0 )
    {
      v5 = v2;
      v9 = &v5;
      v7 = "AuthzInitializeContextFromSid";
      v8 = 30;
      v10 = 4;
      McGenEventWrite_EtwEventWriteTransfer(
        (unsigned int)&MICROSOFT_WFP_PROVIDER_Context,
        (unsigned int)WFP_USERMODE_ERROR,
        v4,
        3,
        (__int64)v6);
    }
    if ( (int)v2 > 0 )
      LODWORD(v2) = (unsigned __int16)v2 | 0x80070000;
    v2 = (int)v2;
    if ( (_DWORD)v2 )
      WfpReportError((int)v2, "ClientContextFromTokenInformation");
  }
  return v2;
}

```

## disassembly

```asm
0x1800362f0  push    rbx
0x1800362f2  sub     rsp, 80h
0x1800362f9  mov     rax, cs:__security_cookie
0x180036300  xor     rax, rsp
0x180036303  mov     [rsp+88h+var_10], rax
0x180036308  mov     r8, rdx
0x18003630b  xor     eax, eax
0x18003630d  mov     rdx, [rcx+8]
0x180036311  xor     r9d, r9d; pExpirationTime
0x180036314  mov     [rsp+88h+phAuthzClientContext], r8; phAuthzClientContext
0x180036319  xor     ebx, ebx
0x18003631b  mov     r8, cs:gWfpGlobal
0x180036322  mov     [rsp+88h+DynamicGroupArgs], rcx; DynamicGroupArgs
0x180036327  mov     ecx, 2; Flags
0x18003632c  mov     rdx, [rdx]; UserSid
0x18003632f  mov     qword ptr [rsp+88h+Identifier.LowPart], rax; Identifier
0x180036334  mov     r8, [r8+310h]; hAuthzResourceManager
0x18003633b  call    cs:__imp_AuthzInitializeContextFromSid
0x180036341  test    eax, eax
0x180036343  jz      short loc_18003635E
0x180036345  mov     rax, rbx
0x180036348  mov     rcx, [rsp+88h+var_10]
0x18003634d  xor     rcx, rsp; StackCookie
0x180036350  call    __security_check_cookie
0x180036355  add     rsp, 80h
0x18003635c  pop     rbx
0x18003635d  retn
0x18003635e  mov     [rsp+88h+arg_10], rdi
0x180036366  call    cs:__imp_GetLastError
0x18003636c  mov     ebx, eax
0x18003636e  mov     rcx, cs:WPP_GLOBAL_Control
0x180036375  lea     rax, WPP_GLOBAL_Control
0x18003637c  lea     rdi, aAuthzinitializ_0; "AuthzInitializeContextFromSid"
0x180036383  cmp     rcx, rax
0x180036386  jz      short loc_18003638E
0x180036388  cmp     byte ptr [rcx+19h], 2
0x18003638c  jnb     short loc_1800363C0
0x18003638e  cmp     cs:gWfpLogUserModeErrors, 0
0x180036395  jnz     short loc_1800363E2
0x180036397  mov     rdi, [rsp+88h+arg_10]
0x18003639f  test    ebx, ebx
0x1800363a1  jg      loc_180036438
0x1800363a7  movsxd  rbx, ebx
0x1800363aa  test    rbx, rbx
0x1800363ad  jz      short loc_180036345
0x1800363af  lea     rdx, aClientcontextf_0; "ClientContextFromTokenInformation"
0x1800363b6  mov     rcx, rbx
0x1800363b9  call    WfpReportError
0x1800363be  jmp     short loc_180036345
0x1800363c0  test    byte ptr [rcx+1Ch], 1
0x1800363c4  jz      short loc_18003638E
0x1800363c6  mov     rcx, [rcx+10h]
0x1800363ca  mov     edx, 17h
0x1800363cf  mov     dword ptr [rsp+88h+DynamicGroupArgs], ebx
0x1800363d3  xor     r9d, r9d
0x1800363d6  mov     qword ptr [rsp+88h+Identifier.LowPart], rdi
0x1800363db  call    WPP_SF_SsD
0x1800363e0  jmp     short loc_18003638E
0x1800363e2  test    cs:byte_1800F30F5, 1
0x1800363e9  jz      short loc_180036397
0x1800363eb  lea     rax, [rsp+88h+var_48]
0x1800363f0  mov     [rsp+88h+var_48], ebx
0x1800363f4  mov     [rsp+88h+var_20], rax
0x1800363f9  lea     rdx, WFP_USERMODE_ERROR
0x180036400  lea     rax, [rsp+88h+var_40]
0x180036405  mov     [rsp+88h+var_30], rdi
0x18003640a  mov     r9d, 3
0x180036410  mov     qword ptr [rsp+88h+Identifier.LowPart], rax
0x180036415  lea     rcx, MICROSOFT_WFP_PROVIDER_Context
0x18003641c  mov     [rsp+88h+var_28], 1Eh
0x180036425  mov     [rsp+88h+var_18], 4
0x18003642e  call    McGenEventWrite_EtwEventWriteTransfer
0x180036433  jmp     loc_180036397
0x180036438  movzx   ebx, bx
0x18003643b  or      ebx, 80070000h
0x180036441  jmp     loc_1800363A7
```
