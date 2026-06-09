# IsWinLogon(void *)

- ea: `0x18000fb34`
- end: `0x18000fcee`
- name: `?IsWinLogon@@YA_NPEAX@Z`
- size: `442`
- prototype: `char __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001495c`

## callees

- `0x180003160`
- `0x18000bb50`
- `0x18000d848`
- `0x18000fb34`
- `0x1800267c0`
- `0x180026c8c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fc00`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fc00`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000fbf6`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000fbf6`
- `SspiCli!LsaGetLogonSessionData` at `0x18000fc64`
- `SspiCli!LsaGetLogonSessionData` at `0x18000fc64`

## string_xrefs

- `0x18000fb5e`: `onecoreuap\ds\ext\live\identity\cloudapplugin\utils.cpp`
- `0x18000fbbf`: `hUserToken == nullptr, isWinLogon is false by default`
- `0x18000fc06`: `GetTokenInformation function failed with error %d, isWinLogon is false by default.`

## pseudocode

```c
char __fastcall IsWinLogon(HANDLE TokenHandle)
{
  int v2; // r8d
  NTSTATUS LogonSessionData; // eax
  char v4; // bl
  PDWORD ReturnLength; // [rsp+20h] [rbp-69h]
  __int64 v7; // [rsp+28h] [rbp-61h]
  char v8[4]; // [rsp+40h] [rbp-49h] BYREF
  DWORD v9; // [rsp+44h] [rbp-45h] BYREF
  _LUID LogonId; // [rsp+48h] [rbp-41h] BYREF
  PSECURITY_LOGON_SESSION_DATA ppLogonSessionData; // [rsp+50h] [rbp-39h] BYREF
  MsaTracingInternal *v12[4]; // [rsp+58h] [rbp-31h] BYREF
  int TokenInformation; // [rsp+78h] [rbp-11h] BYREF
  __int128 v14; // [rsp+7Ch] [rbp-Dh]
  __int128 v15; // [rsp+8Ch] [rbp+3h]
  __int128 v16; // [rsp+9Ch] [rbp+13h]
  int v17; // [rsp+ACh] [rbp+23h]

  v8[0] = 0;
  v17 = 0;
  v9 = 0;
  LogonId = 0;
  ppLogonSessionData = 0;
  TokenInformation = 0;
  v14 = 0;
  v15 = 0;
  v16 = 0;
  CTraceFuncW<long>::CTraceFuncW<long>(
    v12,
    "onecoreuap\\ds\\ext\\live\\identity\\cloudapplugin\\utils.cpp",
    2090,
    v8,
    "IsWinLogon",
    L"status=0x%x",
    0);
  if ( TokenHandle )
  {
    if ( GetTokenInformation(TokenHandle, TokenStatistics, &TokenInformation, 0x38u, &v9) )
    {
      LODWORD(v7) = DWORD1(v14);
      LogonId = *(_LUID *)((char *)&v14 + 4);
      LODWORD(ReturnLength) = DWORD2(v14);
      TracePrintW(
        5u,
        "onecoreuap\\ds\\ext\\live\\identity\\cloudapplugin\\utils.cpp",
        0x841u,
        L"LUID=[%d,%d]",
        ReturnLength,
        v7);
      LogonSessionData = LsaGetLogonSessionData(&LogonId, &ppLogonSessionData);
      if ( LogonSessionData >= 0 )
      {
        if ( (ppLogonSessionData->UserFlags & 0xC000) == 0xC000 )
        {
          TracePrintW(
            5u,
            "onecoreuap\\ds\\ext\\live\\identity\\cloudapplugin\\utils.cpp",
            0x849u,
            L"Checked LogonSessionData's UserFlags, isWinLogon is true.");
          v8[0] = 1;
        }
      }
      else
      {
        Telemetry::IfFailExit(
          (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\cloudapplugin\\utils.cpp",
          "IsWinLogon",
          66,
          LogonSessionData,
          "status = LsaGetLogonSessionData(&logonId, &pLogonSessionData)");
      }
    }
    else
    {
      LODWORD(ReturnLength) = GetLastError();
      TracePrintW(
        2u,
        "onecoreuap\\ds\\ext\\live\\identity\\cloudapplugin\\utils.cpp",
        0x83Cu,
        L"GetTokenInformation function failed with error %d, isWinLogon is false by default.",
        ReturnLength);
    }
  }
  else
  {
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\cloudapplugin\\utils.cpp",
      0x82Fu,
      L"hUserToken == nullptr, isWinLogon is false by default");
  }
  v4 = v8[0];
  MsaTracingInternal::TraceFunctionExit(v12[0], (const char *)*(unsigned __int8 *)v12[1], v2);
  return v4;
}

```

## disassembly

```asm
0x18000fb34  push    rbp
0x18000fb36  push    rbx
0x18000fb37  push    rdi
0x18000fb38  push    r14
0x18000fb3a  lea     rbp, [rsp-3Fh]
0x18000fb3f  sub     rsp, 0C8h
0x18000fb46  mov     rax, cs:__security_cookie
0x18000fb4d  xor     rax, rsp
0x18000fb50  mov     [rbp+57h+var_30], rax
0x18000fb54  xor     eax, eax
0x18000fb56  mov     [rbp+57h+var_A0], 0
0x18000fb5a  mov     [rsp+0E0h+var_B0], eax
0x18000fb5e  lea     rdi, aOnecoreuapDsEx_0; "onecoreuap\\ds\\ext\\live\\identity\\cl"...
0x18000fb65  xorps   xmm0, xmm0
0x18000fb68  mov     [rbp+57h+var_34], eax
0x18000fb6b  mov     [rbp+57h+var_9C], eax
0x18000fb6e  lea     r14, aIswinlogon; "IsWinLogon"
0x18000fb75  mov     qword ptr [rbp+57h+LogonId.LowPart], rax
0x18000fb79  lea     r9, [rbp+57h+var_A0]
0x18000fb7d  mov     [rbp+57h+ppLogonSessionData], rax
0x18000fb81  mov     rbx, rcx
0x18000fb84  lea     rax, aStatus0xX; "status=0x%x"
0x18000fb8b  mov     [rbp+57h+TokenInformation], 0
0x18000fb92  mov     [rsp+0E0h+var_B8], rax
0x18000fb97  lea     rcx, [rbp+57h+var_88]
0x18000fb9b  mov     r8d, 82Ah
0x18000fba1  mov     [rsp+0E0h+ReturnLength], r14
0x18000fba6  mov     rdx, rdi
0x18000fba9  movups  [rbp+57h+var_64], xmm0
0x18000fbad  movups  [rbp+57h+var_54], xmm0
0x18000fbb1  movups  [rbp+57h+var_44], xmm0
0x18000fbb5  call    ??0?$CTraceFuncW@J@@QEAA@PEBDKAEAJ0PEBGZZ; CTraceFuncW<long>::CTraceFuncW<long>(char const *,ulong,long &,char const *,ushort const *,...)
0x18000fbba  test    rbx, rbx
0x18000fbbd  jnz     short loc_18000FBDC
0x18000fbbf  lea     r9, aHusertokenNull; "hUserToken == nullptr, isWinLogon is fa"...
0x18000fbc6  mov     r8d, 82Fh; unsigned int
0x18000fbcc  mov     rdx, rdi; char *
0x18000fbcf  lea     ecx, [rbx+2]; unsigned __int8
0x18000fbd2  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18000fbd7  jmp     loc_18000FCC0
0x18000fbdc  mov     r9d, 38h ; '8'; TokenInformationLength
0x18000fbe2  lea     rax, [rbp+57h+var_9C]
0x18000fbe6  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x18000fbea  mov     [rsp+0E0h+ReturnLength], rax; ReturnLength
0x18000fbef  mov     rcx, rbx; TokenHandle
0x18000fbf2  lea     edx, [r9-2Eh]; TokenInformationClass
0x18000fbf6  call    cs:__imp_GetTokenInformation
0x18000fbfc  test    eax, eax
0x18000fbfe  jnz     short loc_18000FC29
0x18000fc00  call    cs:__imp_GetLastError
0x18000fc06  lea     r9, aGettokeninform; "GetTokenInformation function failed wit"...
0x18000fc0d  mov     r8d, 83Ch; unsigned int
0x18000fc13  mov     rdx, rdi; char *
0x18000fc16  mov     dword ptr [rsp+0E0h+ReturnLength], eax
0x18000fc1a  mov     ecx, 2; unsigned __int8
0x18000fc1f  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18000fc24  jmp     loc_18000FCC0
0x18000fc29  mov     rax, qword ptr [rbp+57h+var_64+4]
0x18000fc2d  lea     r9, aLuidDD; "LUID=[%d,%d]"
0x18000fc34  mov     ecx, dword ptr [rbp+57h+var_64+4]
0x18000fc37  mov     ebx, 5
0x18000fc3c  mov     dword ptr [rsp+0E0h+var_B8], ecx
0x18000fc40  mov     r8d, 841h; unsigned int
0x18000fc46  mov     qword ptr [rbp+57h+LogonId.LowPart], rax
0x18000fc4a  mov     rdx, rdi; char *
0x18000fc4d  shr     rax, 20h
0x18000fc51  mov     ecx, ebx; unsigned __int8
0x18000fc53  mov     dword ptr [rsp+0E0h+ReturnLength], eax
0x18000fc57  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18000fc5c  lea     rdx, [rbp+57h+ppLogonSessionData]; ppLogonSessionData
0x18000fc60  lea     rcx, [rbp+57h+LogonId]; LogonId
0x18000fc64  call    cs:__imp_LsaGetLogonSessionData
0x18000fc6a  test    eax, eax
0x18000fc6c  jns     short loc_18000FC90
0x18000fc6e  lea     rcx, aStatusLsagetlo; "status = LsaGetLogonSessionData(&logonI"...
0x18000fc75  mov     r9d, eax; int
0x18000fc78  mov     [rsp+0E0h+ReturnLength], rcx; char *
0x18000fc7d  mov     r8d, 842h; unsigned int
0x18000fc83  mov     rcx, rdi; char *
0x18000fc86  mov     rdx, r14; char *
0x18000fc89  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x18000fc8e  jmp     short loc_18000FCC0
0x18000fc90  mov     rax, [rbp+57h+ppLogonSessionData]
0x18000fc94  mov     edx, [rax+88h]
0x18000fc9a  mov     eax, 0C000h
0x18000fc9f  and     edx, eax
0x18000fca1  cmp     edx, eax
0x18000fca3  jnz     short loc_18000FCC0
0x18000fca5  lea     r9, aCheckedLogonse; "Checked LogonSessionData's UserFlags, i"...
0x18000fcac  mov     r8d, 849h; unsigned int
0x18000fcb2  mov     rdx, rdi; char *
0x18000fcb5  mov     ecx, ebx; unsigned __int8
0x18000fcb7  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18000fcbc  mov     [rbp+57h+var_A0], 1
0x18000fcc0  mov     rcx, [rbp+57h+var_80]
0x18000fcc4  mov     bl, [rbp+57h+var_A0]
0x18000fcc7  movzx   edx, byte ptr [rcx]; char *
0x18000fcca  mov     rcx, [rbp+57h+var_88]; this
0x18000fcce  call    ?TraceFunctionExit@MsaTracingInternal@@YAKPEBDJ@Z; MsaTracingInternal::TraceFunctionExit(char const *,long)
0x18000fcd3  mov     al, bl
0x18000fcd5  mov     rcx, [rbp+57h+var_30]
0x18000fcd9  xor     rcx, rsp; StackCookie
0x18000fcdc  call    __security_check_cookie
0x18000fce1  add     rsp, 0C8h
0x18000fce8  pop     r14
0x18000fcea  pop     rdi
0x18000fceb  pop     rbx
0x18000fcec  pop     rbp
0x18000fced  retn
```
