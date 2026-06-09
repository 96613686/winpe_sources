# CheckForEnterpriseOrChildAccount(void)

- ea: `0x180032f38`
- end: `0x1800330fc`
- name: `?CheckForEnterpriseOrChildAccount@@YA_NXZ`
- size: `452`
- prototype: `char(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180032e60`

## callees

- `0x180011e18`
- `0x180013270`
- `0x180032f38`
- `0x1800337d0`

## import_xrefs

- `NETAPI32!NetGetAadJoinInformation` at `0x180032f76`
- `NETAPI32!NetGetAadJoinInformation` at `0x180032f76`
- `NETAPI32!NetFreeAadJoinInformation` at `0x180032f8a`
- `NETAPI32!NetFreeAadJoinInformation` at `0x180032f8a`
- `NETAPI32!NetGetJoinInformation` at `0x18003300b`
- `NETAPI32!NetGetJoinInformation` at `0x18003300b`
- `NETAPI32!NetApiBufferFree` at `0x18003301d`
- `NETAPI32!NetApiBufferFree` at `0x18003301d`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180032fb1`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18003306f`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180032fb1`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18003306f`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180032f4c`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180032f4c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180032f43`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180033078`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180033089`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180032f43`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180033078`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180033089`

## string_xrefs

- `0x1800330ea`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`
- `0x180033054`: `Join status was %d, considering not domain joined.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char CheckForEnterpriseOrChildAccount(void)
{
  ULONGLONG TickCount64; // r14
  HRESULT v1; // eax
  unsigned int v2; // ebx
  int AadJoinInformation; // edi
  const wchar_t *v4; // rdx
  char v5; // si
  const wchar_t *v6; // rdx
  DWORD JoinInformation; // esi
  ULONGLONG v8; // rbx
  bool v9; // bp
  ULONGLONG v10; // rax
  int v12; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  _NETSETUP_JOIN_STATUS BufferType; // [rsp+58h] [rbp+10h] BYREF
  unsigned int *v15; // [rsp+60h] [rbp+18h] BYREF
  LPWSTR NameBuffer; // [rsp+68h] [rbp+20h] BYREF

  TickCount64 = GetTickCount64();
  v1 = CoImpersonateClient();
  if ( v1 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x14AA,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
      (const char *)(unsigned int)v1,
      v12);
  v15 = 0;
  v2 = 0;
  AadJoinInformation = NetGetAadJoinInformation(0, &v15);
  if ( v15 )
  {
    v2 = *v15;
    NetFreeAadJoinInformation();
  }
  if ( AadJoinInformation >= 0 && v2 )
  {
    if ( v2 == 1 )
    {
      v4 = L"Caller is AAD Device Joined (Enterprise Managed)";
LABEL_8:
      Log(4u, v4);
LABEL_9:
      CoRevertToSelf();
      v5 = 1;
      goto LABEL_24;
    }
    if ( v2 == 2 )
    {
      v4 = L"Caller is AAD Workplace Joined (Enterprise Managed)";
      goto LABEL_8;
    }
    v6 = L"Unknown joinType %d";
    AadJoinInformation = v2;
  }
  else
  {
    v6 = L"NetGetAadJoinInformation failed hr=%#x";
  }
  Log(4u, v6, (unsigned int)AadJoinInformation);
  NameBuffer = 0;
  BufferType = NetSetupUnknownStatus;
  JoinInformation = NetGetJoinInformation(0, &NameBuffer, &BufferType);
  if ( NameBuffer )
    NetApiBufferFree(NameBuffer);
  if ( JoinInformation )
  {
    Log(4u, L"NetGetJoinInformation failed result=%#x", JoinInformation);
  }
  else
  {
    if ( BufferType == NetSetupDomainName )
    {
      Log(4u, L"Caller is Domain Joined (Enterprise Managed)");
      goto LABEL_9;
    }
    if ( BufferType == NetSetupWorkgroupName )
      Log(4u, L"Caller is AD Workgroup Joined (not Enterprise Managed)");
    else
      Log(4u, L"Join status was %d, considering not domain joined.", v2);
  }
  CoRevertToSelf();
  v5 = 0;
LABEL_24:
  v8 = GetTickCount64();
  v9 = IsCallingProcessChildAccount();
  v10 = GetTickCount64();
  Log(4u, L"Enterprise check took %d ms, child account took %d ms", v8 - TickCount64, v10 - v8);
  if ( v5 )
  {
    Log(4u, L"Calling process is enterprise managed");
    return 1;
  }
  if ( v9 )
  {
    Log(4u, L"Calling process is a child account");
    return 1;
  }
  Log(4u, L"Verified caller is not Enterprise joined or Child account");
  return 0;
}

```

## disassembly

```asm
0x180032f38  push    rbx
0x180032f3a  push    rbp
0x180032f3b  push    rsi
0x180032f3c  push    rdi
0x180032f3d  push    r14; int
0x180032f3f  sub     rsp, 20h
0x180032f43  call    cs:__imp_GetTickCount64
0x180032f49  mov     r14, rax
0x180032f4c  call    cs:__imp_CoImpersonateClient
0x180032f52  mov     rcx, [rsp+48h]; this
0x180032f57  test    eax, eax
0x180032f59  js      loc_1800330E7
0x180032f5f  mov     [rsp+48h+arg_0], 1
0x180032f64  mov     [rsp+48h+arg_10], 0
0x180032f6d  xor     ebx, ebx
0x180032f6f  lea     rdx, [rsp+48h+arg_10]
0x180032f74  xor     ecx, ecx
0x180032f76  call    cs:__imp_NetGetAadJoinInformation
0x180032f7c  mov     edi, eax
0x180032f7e  mov     rcx, [rsp+48h+arg_10]
0x180032f83  test    rcx, rcx
0x180032f86  jz      short loc_180032F90
0x180032f88  mov     ebx, [rcx]
0x180032f8a  call    cs:__imp_NetFreeAadJoinInformation
0x180032f90  test    edi, edi
0x180032f92  js      short loc_180032FD8
0x180032f94  test    ebx, ebx
0x180032f96  jz      short loc_180032FD8
0x180032f98  cmp     ebx, 1
0x180032f9b  jnz     short loc_180032FBF
0x180032f9d  lea     rdx, aCallerIsAadDev; "Caller is AAD Device Joined (Enterprise"...
0x180032fa4  mov     edi, 4
0x180032fa9  mov     ecx, edi; unsigned __int8
0x180032fab  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x180032fb0  nop
0x180032fb1  call    cs:__imp_CoRevertToSelf
0x180032fb7  mov     sil, 1
0x180032fba  jmp     loc_180033078
0x180032fbf  cmp     ebx, 2
0x180032fc2  jnz     short loc_180032FCD
0x180032fc4  lea     rdx, aCallerIsAadWor; "Caller is AAD Workplace Joined (Enterpr"...
0x180032fcb  jmp     short loc_180032FA4
0x180032fcd  lea     rdx, aUnknownJointyp; "Unknown joinType %d"
0x180032fd4  mov     edi, ebx
0x180032fd6  jmp     short loc_180032FDF
0x180032fd8  lea     rdx, aNetgetaadjoini; "NetGetAadJoinInformation failed hr=%#x"
0x180032fdf  mov     r8d, edi
0x180032fe2  mov     edi, 4
0x180032fe7  mov     ecx, edi; unsigned __int8
0x180032fe9  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x180032fee  mov     [rsp+48h+NameBuffer], 0
0x180032ff7  mov     [rsp+48h+BufferType], 0
0x180032fff  lea     r8, [rsp+48h+BufferType]; BufferType
0x180033004  lea     rdx, [rsp+48h+NameBuffer]; lpNameBuffer
0x180033009  xor     ecx, ecx; lpServer
0x18003300b  call    cs:__imp_NetGetJoinInformation
0x180033011  mov     esi, eax
0x180033013  mov     rcx, [rsp+48h+NameBuffer]; Buffer
0x180033018  test    rcx, rcx
0x18003301b  jz      short loc_180033023
0x18003301d  call    cs:__imp_NetApiBufferFree
0x180033023  test    esi, esi
0x180033025  jnz     short loc_18003305D
0x180033027  cmp     [rsp+48h+BufferType], 3
0x18003302c  jnz     short loc_18003303A
0x18003302e  lea     rdx, aCallerIsDomain; "Caller is Domain Joined (Enterprise Man"...
0x180033035  jmp     loc_180032FA9
0x18003303a  mov     ecx, edi; unsigned __int8
0x18003303c  cmp     [rsp+48h+BufferType], 2
0x180033041  jnz     short loc_180033051
0x180033043  lea     rdx, aCallerIsAdWork; "Caller is AD Workgroup Joined (not Ente"...
0x18003304a  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x18003304f  jmp     short loc_18003306F
0x180033051  mov     r8d, ebx
0x180033054  lea     rdx, aJoinStatusWasD; "Join status was %d, considering not dom"...
0x18003305b  jmp     short loc_180033069
0x18003305d  mov     r8d, esi
0x180033060  lea     rdx, aNetgetjoininfo; "NetGetJoinInformation failed result=%#x"
0x180033067  mov     ecx, edi; unsigned __int8
0x180033069  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x18003306e  nop
0x18003306f  call    cs:__imp_CoRevertToSelf
0x180033075  xor     sil, sil
0x180033078  call    cs:__imp_GetTickCount64
0x18003307e  mov     rbx, rax
0x180033081  call    ?IsCallingProcessChildAccount@@YA_NXZ; IsCallingProcessChildAccount(void)
0x180033086  mov     bpl, al
0x180033089  call    cs:__imp_GetTickCount64
0x18003308f  sub     rax, rbx
0x180033092  sub     rbx, r14
0x180033095  mov     r9, rax
0x180033098  mov     r8, rbx
0x18003309b  lea     rdx, aEnterpriseChec; "Enterprise check took %d ms, child acco"...
0x1800330a2  mov     ecx, edi; unsigned __int8
0x1800330a4  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x1800330a9  mov     ecx, edi; unsigned __int8
0x1800330ab  test    sil, sil
0x1800330ae  jz      short loc_1800330C0
0x1800330b0  lea     rdx, aCallingProcess_0; "Calling process is enterprise managed"
0x1800330b7  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x1800330bc  mov     al, 1
0x1800330be  jmp     short loc_1800330DC
0x1800330c0  test    bpl, bpl
0x1800330c3  jz      short loc_1800330CE
0x1800330c5  lea     rdx, aCallingProcess; "Calling process is a child account"
0x1800330cc  jmp     short loc_1800330B7
0x1800330ce  lea     rdx, aVerifiedCaller; "Verified caller is not Enterprise joine"...
0x1800330d5  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x1800330da  xor     al, al
0x1800330dc  add     rsp, 20h
0x1800330e0  pop     r14
0x1800330e2  pop     rdi
0x1800330e3  pop     rsi
0x1800330e4  pop     rbp
0x1800330e5  pop     rbx
0x1800330e6  retn
0x1800330e7  mov     r9d, eax; char *
0x1800330ea  lea     r8, aOnecoreInterna_8; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800330f1  mov     edx, 14AAh; void *
0x1800330f6  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
```
