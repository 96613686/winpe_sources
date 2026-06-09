# ClientContextFromTokenInformation

- ea: `0x180034240`
- end: `0x1800343a6`
- name: `ClientContextFromTokenInformation`
- size: `358`
- prototype: `__int64 __fastcall(PVOID DynamicGroupArgs, PAUTHZ_CLIENT_CONTEXT_HANDLE phAuthzClientContext)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18001bf10`

## callees

- `0x18000fb34`
- `0x1800133a0`
- `0x1800197d0`
- `0x180034240`
- `0x18005aa60`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800342bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800342bd`
- `AUTHZ!AuthzInitializeContextFromSid` at `0x18003428b`
- `AUTHZ!AuthzInitializeContextFromSid` at `0x18003428b`

## string_xrefs

- `0x1800342d9`: `AuthzInitializeContextFromSid`
- `0x18003430c`: `ClientContextFromTokenInformation`

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
    if ( gWfpLogUserModeErrors && (byte_1800F6115 & 1) != 0 )
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
0x180034240  push    rbx
0x180034242  sub     rsp, 80h
0x180034249  mov     rax, cs:__security_cookie
0x180034250  xor     rax, rsp
0x180034253  mov     [rsp+88h+var_10], rax
0x180034258  mov     r8, rdx
0x18003425b  xor     eax, eax
0x18003425d  mov     rdx, [rcx+8]
0x180034261  xor     r9d, r9d; pExpirationTime
0x180034264  mov     [rsp+88h+phAuthzClientContext], r8; phAuthzClientContext
0x180034269  xor     ebx, ebx
0x18003426b  mov     r8, cs:gWfpGlobal
0x180034272  mov     [rsp+88h+DynamicGroupArgs], rcx; DynamicGroupArgs
0x180034277  mov     ecx, 2; Flags
0x18003427c  mov     rdx, [rdx]; UserSid
0x18003427f  mov     qword ptr [rsp+88h+Identifier.LowPart], rax; Identifier
0x180034284  mov     r8, [r8+310h]; hAuthzResourceManager
0x18003428b  call    cs:__imp_AuthzInitializeContextFromSid
0x180034292  nop     dword ptr [rax+rax+00h]
0x180034297  test    eax, eax
0x180034299  jz      short loc_1800342B5
0x18003429b  mov     rax, rbx
0x18003429e  mov     rcx, [rsp+88h+var_10]
0x1800342a3  xor     rcx, rsp; StackCookie
0x1800342a6  call    __security_check_cookie
0x1800342ab  add     rsp, 80h
0x1800342b2  pop     rbx
0x1800342b3  retn
0x1800342b5  mov     [rsp+88h+arg_10], rdi
0x1800342bd  call    cs:__imp_GetLastError
0x1800342c4  nop     dword ptr [rax+rax+00h]
0x1800342c9  mov     ebx, eax
0x1800342cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800342d2  lea     rax, WPP_GLOBAL_Control
0x1800342d9  lea     rdi, aAuthzinitializ_0; "AuthzInitializeContextFromSid"
0x1800342e0  cmp     rcx, rax
0x1800342e3  jz      short loc_1800342EB
0x1800342e5  cmp     byte ptr [rcx+19h], 2
0x1800342e9  jnb     short loc_180034320
0x1800342eb  cmp     cs:gWfpLogUserModeErrors, 0
0x1800342f2  jnz     short loc_180034342
0x1800342f4  mov     rdi, [rsp+88h+arg_10]
0x1800342fc  test    ebx, ebx
0x1800342fe  jg      loc_180034398
0x180034304  movsxd  rbx, ebx
0x180034307  test    rbx, rbx
0x18003430a  jz      short loc_18003429B
0x18003430c  lea     rdx, aClientcontextf_0; "ClientContextFromTokenInformation"
0x180034313  mov     rcx, rbx
0x180034316  call    WfpReportError
0x18003431b  jmp     loc_18003429B
0x180034320  test    byte ptr [rcx+1Ch], 1
0x180034324  jz      short loc_1800342EB
0x180034326  mov     rcx, [rcx+10h]
0x18003432a  mov     edx, 17h
0x18003432f  mov     dword ptr [rsp+88h+DynamicGroupArgs], ebx
0x180034333  xor     r9d, r9d
0x180034336  mov     qword ptr [rsp+88h+Identifier.LowPart], rdi
0x18003433b  call    WPP_SF_SsD
0x180034340  jmp     short loc_1800342EB
0x180034342  test    cs:byte_1800F6115, 1
0x180034349  jz      short loc_1800342F4
0x18003434b  lea     rax, [rsp+88h+var_48]
0x180034350  mov     [rsp+88h+var_48], ebx
0x180034354  mov     [rsp+88h+var_20], rax
0x180034359  lea     rdx, WFP_USERMODE_ERROR
0x180034360  lea     rax, [rsp+88h+var_40]
0x180034365  mov     [rsp+88h+var_30], rdi
0x18003436a  mov     r9d, 3
0x180034370  mov     qword ptr [rsp+88h+Identifier.LowPart], rax
0x180034375  lea     rcx, MICROSOFT_WFP_PROVIDER_Context
0x18003437c  mov     [rsp+88h+var_28], 1Eh
0x180034385  mov     [rsp+88h+var_18], 4
0x18003438e  call    McGenEventWrite_EtwEventWriteTransfer
0x180034393  jmp     loc_1800342F4
0x180034398  movzx   ebx, bx
0x18003439b  or      ebx, 80070000h
0x1800343a1  jmp     loc_180034304
```
