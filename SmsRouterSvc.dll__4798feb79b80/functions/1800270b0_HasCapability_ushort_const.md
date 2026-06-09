# HasCapability(ushort const *)

- ea: `0x1800270b0`
- end: `0x180027233`
- name: `?HasCapability@@YAHPEBG@Z`
- size: `387`
- prototype: `__int64 __fastcall(PCWSTR SourceString)`
- caller_count: `10`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180009b60`
- `0x180009d50`
- `0x180009f60`
- `0x18000a0c0`
- `0x18000a350`
- `0x18000a400`
- `0x18000a560`
- `0x18000a6e0`
- `0x18000a950`
- `0x18000aac0`

## callees

- `0x180003a60`
- `0x180004998`
- `0x180026a40`
- `0x1800270b0`
- `0x18002723c`
- `0x180051420`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180027162`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180027162`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800271ea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002720a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800271ea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002720a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180027140`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180027140`
- `ntdll!RtlInitUnicodeString` at `0x1800271c3`
- `ntdll!RtlInitUnicodeString` at `0x1800271c3`
- `ntdll!RtlCapabilityCheck` at `0x1800271d4`
- `ntdll!RtlCapabilityCheck` at `0x1800271d4`
- `api-ms-win-appmodel-runtime-l1-1-1!GetPackageFamilyNameFromToken` at `0x180027177`
- `api-ms-win-appmodel-runtime-l1-1-1!GetPackageFamilyNameFromToken` at `0x180027177`

## string_xrefs

- `0x18002718b`: `GetPackageFamilyNameFromToken failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=18
__int64 __fastcall HasCapability(PCWSTR SourceString)
{
  HANDLE v3; // rbx
  int PackageFamilyNameFromToken; // eax
  unsigned __int8 v5; // al
  unsigned int v6; // edi
  char v7[4]; // [rsp+30h] [rbp-79h] BYREF
  int TokenInformation; // [rsp+34h] [rbp-75h] BYREF
  DWORD ReturnLength; // [rsp+38h] [rbp-71h] BYREF
  UINT32 packageFamilyNameLength; // [rsp+3Ch] [rbp-6Dh] BYREF
  HANDLE TokenHandle; // [rsp+40h] [rbp-69h] BYREF
  _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-61h] BYREF
  WCHAR packageFamilyName[72]; // [rsp+60h] [rbp-49h] BYREF

  TokenHandle = 0;
  v7[0] = 0;
  TokenInformation = 0;
  ReturnLength = 0;
  memset_0(packageFamilyName, 0, 0x82u);
  packageFamilyNameLength = 65;
  if ( (int)ImpersonateAndGetToken(&TokenHandle) < 0 )
    return 0;
  v3 = TokenHandle;
  if ( GetTokenInformation(TokenHandle, TokenIsAppContainer, &TokenInformation, 4u, &ReturnLength) && TokenInformation )
  {
    if ( !(unsigned int)_o__wcsicmp(SourceString, L"cellularMessaging") )
    {
      PackageFamilyNameFromToken = GetPackageFamilyNameFromToken(v3, &packageFamilyNameLength, packageFamilyName);
      if ( PackageFamilyNameFromToken )
      {
        if ( PackageFamilyNameFromToken > 0 )
          PackageFamilyNameFromToken = (unsigned __int16)PackageFamilyNameFromToken | 0x80070000;
        LogSmsRouterError("HasCapability", 0x1B5u, PackageFamilyNameFromToken, "GetPackageFamilyNameFromToken failed");
        goto LABEL_12;
      }
      if ( !(unsigned int)CSmsRpcUtils::DoesAppMeetCTA(packageFamilyName) )
        goto LABEL_12;
    }
    DestinationString = 0;
    RtlInitUnicodeString(&DestinationString, SourceString);
    if ( (unsigned int)RtlCapabilityCheck(v3, &DestinationString, v7) )
    {
LABEL_12:
      if ( v3 )
        CloseHandle(v3);
      return 0;
    }
    v5 = v7[0];
  }
  else
  {
    v5 = 1;
    v7[0] = 1;
  }
  v6 = v5;
  if ( v3 )
    CloseHandle(v3);
  return v6;
}

```

## disassembly

```asm
0x1800270b0  mov     [rsp-8+arg_8], rbx
0x1800270b5  mov     [rsp-8+arg_10], rdi
0x1800270ba  push    rbp
0x1800270bb  lea     rbp, [rsp-57h]
0x1800270c0  sub     rsp, 100h
0x1800270c7  mov     rax, cs:__security_cookie
0x1800270ce  xor     rax, rsp
0x1800270d1  mov     [rbp+57h+var_10], rax
0x1800270d5  mov     rdi, rcx
0x1800270d8  mov     [rbp+57h+TokenHandle], 0
0x1800270e0  mov     [rbp+57h+var_D0], 0
0x1800270e4  mov     [rbp+57h+TokenInformation], 0
0x1800270eb  mov     [rbp+57h+var_C8], 0
0x1800270f2  xor     edx, edx; Val
0x1800270f4  mov     r8d, 82h; Size
0x1800270fa  lea     rcx, [rbp+57h+packageFamilyName]; void *
0x1800270fe  call    memset_0
0x180027103  mov     [rbp+57h+packageFamilyNameLength], 41h ; 'A'
0x18002710a  lea     rcx, [rbp+57h+TokenHandle]; void **
0x18002710e  call    ?ImpersonateAndGetToken@@YAJPEAPEAX@Z; ImpersonateAndGetToken(void * *)
0x180027113  test    eax, eax
0x180027115  jns     short loc_18002711E
0x180027117  xor     eax, eax
0x180027119  jmp     loc_180027212
0x18002711e  mov     rbx, [rbp+57h+TokenHandle]
0x180027122  mov     [rbp+57h+TokenHandle], rbx
0x180027126  lea     rax, [rbp+57h+var_C8]
0x18002712a  mov     [rsp+100h+ReturnLength], rax; ReturnLength
0x18002712f  mov     r9d, 4; TokenInformationLength
0x180027135  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x180027139  lea     edx, [r9+19h]; TokenInformationClass
0x18002713d  mov     rcx, rbx; TokenHandle
0x180027140  call    cs:__imp_GetTokenInformation
0x180027146  test    eax, eax
0x180027148  jz      loc_1800271FA
0x18002714e  cmp     [rbp+57h+TokenInformation], 0
0x180027152  jz      loc_1800271FA
0x180027158  lea     rdx, SourceString; "cellularMessaging"
0x18002715f  mov     rcx, rdi
0x180027162  call    cs:__imp__o__wcsicmp
0x180027168  test    eax, eax
0x18002716a  jnz     short loc_1800271B5
0x18002716c  lea     r8, [rbp+57h+packageFamilyName]; packageFamilyName
0x180027170  lea     rdx, [rbp+57h+packageFamilyNameLength]; packageFamilyNameLength
0x180027174  mov     rcx, rbx; token
0x180027177  call    cs:__imp_GetPackageFamilyNameFromToken
0x18002717d  test    eax, eax
0x18002717f  jz      short loc_1800271A8
0x180027181  jle     short loc_18002718B
0x180027183  movzx   eax, ax
0x180027186  or      eax, 80070000h
0x18002718b  lea     r9, aGetpackagefami_0; "GetPackageFamilyNameFromToken failed"
0x180027192  mov     r8d, eax; int
0x180027195  mov     edx, 1B5h; unsigned int
0x18002719a  lea     rcx, aHascapability; "HasCapability"
0x1800271a1  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x1800271a6  jmp     short loc_1800271DE
0x1800271a8  lea     rcx, [rbp+57h+packageFamilyName]; unsigned __int16 *
0x1800271ac  call    ?DoesAppMeetCTA@CSmsRpcUtils@@SAHPEBG@Z; CSmsRpcUtils::DoesAppMeetCTA(ushort const *)
0x1800271b1  test    eax, eax
0x1800271b3  jz      short loc_1800271DE
0x1800271b5  xorps   xmm0, xmm0
0x1800271b8  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1800271bc  mov     rdx, rdi; SourceString
0x1800271bf  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800271c3  call    cs:__imp_RtlInitUnicodeString
0x1800271c9  lea     r8, [rbp+57h+var_D0]
0x1800271cd  lea     rdx, [rbp+57h+DestinationString]
0x1800271d1  mov     rcx, rbx
0x1800271d4  call    cs:__imp_RtlCapabilityCheck
0x1800271da  test    eax, eax
0x1800271dc  jz      short loc_1800271F5
0x1800271de  test    rbx, rbx
0x1800271e1  jz      loc_180027117
0x1800271e7  mov     rcx, rbx; hObject
0x1800271ea  call    cs:__imp_CloseHandle
0x1800271f0  jmp     loc_180027117
0x1800271f5  mov     al, [rbp+57h+var_D0]
0x1800271f8  jmp     short loc_1800271FF
0x1800271fa  mov     al, 1
0x1800271fc  mov     [rbp+57h+var_D0], al
0x1800271ff  movzx   edi, al
0x180027202  test    rbx, rbx
0x180027205  jz      short loc_180027210
0x180027207  mov     rcx, rbx; hObject
0x18002720a  call    cs:__imp_CloseHandle
0x180027210  mov     eax, edi
0x180027212  mov     rcx, [rbp+57h+var_10]
0x180027216  xor     rcx, rsp; StackCookie
0x180027219  call    __security_check_cookie
0x18002721e  lea     r11, [rsp+100h+var_s0]
0x180027226  mov     rbx, [r11+18h]
0x18002722a  mov     rdi, [r11+20h]
0x18002722e  mov     rsp, r11
0x180027231  pop     rbp
0x180027232  retn
```
