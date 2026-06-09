# NetworkIsolationDiagnoseConnectFailure

- ea: `0x18001bc60`
- end: `0x18001bfe0`
- name: `NetworkIsolationDiagnoseConnectFailure`
- size: `896`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180005954`
- `0x18000e960`
- `0x18001bc60`
- `0x18001f148`
- `0x180024c3c`
- `0x1800277b0`

## import_xrefs

- `RPCRT4!RpcExceptionFilter` at `0x18005ba2a`
- `RPCRT4!RpcExceptionFilter` at `0x18005ba2a`
- `RPCRT4!RpcBindingFree` at `0x18001bfc6`
- `RPCRT4!RpcBindingFree` at `0x18001bfc6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bee8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bf31`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bee8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bf31`
- `ntdll!RtlInitUnicodeString` at `0x18001bea1`
- `ntdll!RtlInitUnicodeString` at `0x18001bea1`
- `ntdll!RtlCapabilityCheck` at `0x18001beb8`
- `ntdll!RtlCapabilityCheck` at `0x18001beb8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001bfab`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001bfab`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18001bd59`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18001bd59`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001bd33`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001bd33`
- `api-ms-win-security-base-l1-2-0!CheckTokenCapability` at `0x18001bf27`
- `api-ms-win-security-base-l1-2-0!CheckTokenCapability` at `0x18001bf27`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18001bede`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18001bede`
- `api-ms-win-core-winrt-error-l1-1-0!RoGetErrorReportingFlags` at `0x18001bd3e`
- `api-ms-win-core-winrt-error-l1-1-0!RoGetErrorReportingFlags` at `0x18001bd3e`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoReportCapabilityCheckFailure` at `0x18001bf7e`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoReportCapabilityCheckFailure` at `0x18001bf7e`
- `fwbase!FwBaseFree` at `0x18001bfb6`
- `fwbase!FwBaseFree` at `0x18001bfb6`
- `fwbase!FwHResultToWindowsError` at `0x18001bd46`
- `fwbase!FwHResultToWindowsError` at `0x18001bd46`

## string_xrefs

- `0x18001bca6`: `A network capability is required to access this network resource`

## pseudocode

```c
__int64 __fastcall NetworkIsolationDiagnoseConnectFailure(__int64 a1)
{
  unsigned int ErrorReportingFlags; // eax
  unsigned int LastError; // ebx
  FwPolicy2 *v4; // rcx
  __int64 v6; // rdx
  __int64 v7; // r9
  unsigned int v8; // eax
  __int64 v9; // rcx
  RPC_BINDING_HANDLE Binding; // [rsp+28h] [rbp-E0h] BYREF
  PSID Sid; // [rsp+30h] [rbp-D8h] BYREF
  __int64 v12; // [rsp+38h] [rbp-D0h] BYREF
  _BYTE v13[4]; // [rsp+40h] [rbp-C8h] BYREF
  int v14; // [rsp+44h] [rbp-C4h] BYREF
  int v15; // [rsp+48h] [rbp-C0h] BYREF
  int v16; // [rsp+4Ch] [rbp-BCh] BYREF
  _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-B8h] BYREF
  _OWORD v18[8]; // [rsp+60h] [rbp-A8h] BYREF
  wchar_t v19; // [rsp+E0h] [rbp-28h]

  v15 = 0;
  Binding = 0;
  v16 = 0;
  v12 = 0;
  v18[0] = *(_OWORD *)L"A network capability is required to access this network resource";
  v18[1] = *(_OWORD *)L"k capability is required to access this network resource";
  v18[2] = *(_OWORD *)L"lity is required to access this network resource";
  v18[3] = *(_OWORD *)L"required to access this network resource";
  v18[4] = *(_OWORD *)L" to access this network resource";
  v18[5] = *(_OWORD *)L"ss this network resource";
  v18[6] = *(_OWORD *)L"network resource";
  v18[7] = *(_OWORD *)L"resource";
  v19 = aANetworkCapabi[64];
  v14 = 0;
  v13[0] = 0;
  Sid = 0;
  DestinationString = 0;
  GetTickCount64();
  ErrorReportingFlags = RoGetErrorReportingFlags(&v15);
  LastError = FwHResultToWindowsError(ErrorReportingFlags);
  if ( LastError )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v6 = 512;
LABEL_15:
      v7 = LastError;
      goto LABEL_38;
    }
  }
  else
  {
    if ( (v15 & 1) != 0 || !IsDebuggerPresent() )
    {
      LastError = 0;
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_6;
      v6 = 513;
      v7 = 0;
LABEL_38:
      WPP_SF_d(*((_QWORD *)v4 + 2), v6, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids, v7);
      goto LABEL_6;
    }
    LastError = Int_FWLocalRpcBindingCreate(&Binding);
    if ( LastError )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v6 = 514;
        goto LABEL_15;
      }
    }
    else
    {
      LastError = RPC_NetworkIsolationDiagnoseConnectFailure(Binding, a1, &v16, &v12);
      if ( LastError )
      {
        v4 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v6 = 515;
          goto LABEL_15;
        }
      }
      else
      {
        if ( !v16 )
          goto LABEL_6;
        RtlInitUnicodeString(&DestinationString, L"proximity");
        RtlCapabilityCheck(-4, &DestinationString, v13);
        if ( v13[0] == 1 )
        {
          v14 = 1;
          goto LABEL_6;
        }
        if ( ConvertStringSidToSidW(L"S-1-15-3-4214768333-1334025770-122408079-3919188833", &Sid) )
        {
          if ( (unsigned int)CheckTokenCapability(0, Sid, &v14) )
          {
            if ( !v14 )
            {
              RoReportCapabilityCheckFailure(2147942405LL, 65, v18, v12, 0);
              LastError = 5;
            }
          }
          else
          {
            LastError = GetLastError();
            v4 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v6 = 517;
              goto LABEL_15;
            }
          }
        }
        else
        {
          LastError = GetLastError();
          v4 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v6 = 516;
            goto LABEL_15;
          }
        }
      }
    }
  }
LABEL_6:
  if ( Sid )
    LocalFree(Sid);
  if ( v12 )
    FwBaseFree(v12);
  if ( Binding )
  {
    v8 = RpcBindingFree(&Binding);
    if ( v8 )
      MicrosoftTelemetryAssertTriggeredArgs(v9, v8);
  }
  return LastError;
}

```

## disassembly

```asm
0x18001bc60  mov     r11, rsp
0x18001bc63  mov     [r11+10h], rbx
0x18001bc67  push    rsi
0x18001bc68  sub     rsp, 100h
0x18001bc6f  mov     rax, cs:__security_cookie
0x18001bc76  xor     rax, rsp
0x18001bc79  mov     [rsp+108h+var_18], rax
0x18001bc81  mov     rsi, rcx
0x18001bc84  mov     [rsp+108h+var_C0], 0
0x18001bc8c  mov     [rsp+108h+Binding], 0
0x18001bc95  mov     [rsp+108h+var_BC], 0
0x18001bc9d  mov     [rsp+108h+var_D0], 0
0x18001bca6  movaps  xmm0, xmmword ptr cs:aANetworkCapabi; "A network capability is required to acc"...
0x18001bcad  movups  [rsp+108h+var_A8], xmm0
0x18001bcb2  movaps  xmm1, xmmword ptr cs:aANetworkCapabi+10h; "k capability is required to access this"...
0x18001bcb9  movups  [rsp+108h+var_98], xmm1
0x18001bcbe  movaps  xmm0, xmmword ptr cs:aANetworkCapabi+20h; "lity is required to access this network"...
0x18001bcc5  movups  [rsp+108h+var_88], xmm0
0x18001bccd  movaps  xmm1, xmmword ptr cs:aANetworkCapabi+30h; "required to access this network resourc"...
0x18001bcd4  movups  xmmword ptr [r11-78h], xmm1
0x18001bcd9  movaps  xmm0, xmmword ptr cs:aANetworkCapabi+40h; " to access this network resource"
0x18001bce0  movups  xmmword ptr [r11-68h], xmm0
0x18001bce5  movaps  xmm1, xmmword ptr cs:aANetworkCapabi+50h; "ss this network resource"
0x18001bcec  movups  xmmword ptr [r11-58h], xmm1
0x18001bcf1  movaps  xmm0, xmmword ptr cs:aANetworkCapabi+60h; "network resource"
0x18001bcf8  movups  xmmword ptr [r11-48h], xmm0
0x18001bcfd  movaps  xmm1, xmmword ptr cs:aANetworkCapabi+70h; "resource"
0x18001bd04  movups  xmmword ptr [r11-38h], xmm1
0x18001bd09  movzx   eax, word ptr cs:aANetworkCapabi+80h; ""
0x18001bd10  mov     [r11-28h], ax
0x18001bd15  mov     [rsp+108h+var_C4], 0
0x18001bd1d  mov     [rsp+108h+var_C8], 0
0x18001bd22  mov     [rsp+108h+Sid], 0
0x18001bd2b  xorps   xmm0, xmm0
0x18001bd2e  movups  xmmword ptr [rsp+108h+DestinationString.Length], xmm0
0x18001bd33  call    cs:__imp_GetTickCount64
0x18001bd39  lea     rcx, [rsp+108h+var_C0]
0x18001bd3e  call    cs:__imp_RoGetErrorReportingFlags
0x18001bd44  mov     ecx, eax
0x18001bd46  call    cs:__imp_FwHResultToWindowsError
0x18001bd4c  mov     ebx, eax
0x18001bd4e  test    eax, eax
0x18001bd50  jnz     short loc_18001BDD1
0x18001bd52  test    byte ptr [rsp+108h+var_C0], 1
0x18001bd57  jnz     short loc_18001BD67
0x18001bd59  call    cs:__imp_IsDebuggerPresent
0x18001bd5f  test    eax, eax
0x18001bd61  jnz     loc_18001BDFE
0x18001bd67  xor     ebx, ebx
0x18001bd69  lea     rax, WPP_GLOBAL_Control
0x18001bd70  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bd77  cmp     rcx, rax
0x18001bd7a  jz      short loc_18001BD86
0x18001bd7c  test    byte ptr [rcx+1Ch], 1
0x18001bd80  jnz     loc_18001BF8E
0x18001bd86  mov     rcx, [rsp+108h+Sid]; hMem
0x18001bd8b  test    rcx, rcx
0x18001bd8e  jnz     loc_18001BFAB
0x18001bd94  mov     rcx, [rsp+108h+var_D0]
0x18001bd99  test    rcx, rcx
0x18001bd9c  jnz     loc_18001BFB6
0x18001bda2  cmp     [rsp+108h+Binding], 0
0x18001bda8  jnz     loc_18001BFC1
0x18001bdae  mov     eax, ebx
0x18001bdb0  mov     rcx, [rsp+108h+var_18]
0x18001bdb8  xor     rcx, rsp; StackCookie
0x18001bdbb  call    __security_check_cookie
0x18001bdc0  mov     rbx, [rsp+108h+arg_8]
0x18001bdc8  add     rsp, 100h
0x18001bdcf  pop     rsi
0x18001bdd0  retn
0x18001bdd1  lea     rax, WPP_GLOBAL_Control
0x18001bdd8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bddf  cmp     rcx, rax
0x18001bde2  jz      short loc_18001BD86
0x18001bde4  test    byte ptr [rcx+1Ch], 1
0x18001bde8  jz      short loc_18001BD86
0x18001bdea  mov     edx, 200h
0x18001bdef  jmp     short loc_18001BDF6
0x18001bdf1  mov     edx, 205h
0x18001bdf6  mov     r9d, ebx
0x18001bdf9  jmp     loc_18001BF96
0x18001bdfe  lea     rcx, [rsp+108h+Binding]
0x18001be03  call    Int_FWLocalRpcBindingCreate
0x18001be08  mov     ebx, eax
0x18001be0a  test    eax, eax
0x18001be0c  jz      short loc_18001BE36
0x18001be0e  lea     rax, WPP_GLOBAL_Control
0x18001be15  mov     rcx, cs:WPP_GLOBAL_Control
0x18001be1c  cmp     rcx, rax
0x18001be1f  jz      loc_18001BD86
0x18001be25  test    byte ptr [rcx+1Ch], 1
0x18001be29  jz      loc_18001BD86
0x18001be2f  mov     edx, 202h
0x18001be34  jmp     short loc_18001BDF6
0x18001be36  lea     r9, [rsp+108h+var_D0]
0x18001be3b  lea     r8, [rsp+108h+var_BC]
0x18001be40  mov     rdx, rsi
0x18001be43  mov     rcx, [rsp+108h+Binding]
0x18001be48  call    RPC_NetworkIsolationDiagnoseConnectFailure
0x18001be4d  mov     ebx, eax
0x18001be4f  mov     [rsp+108h+var_E8], eax
0x18001be53  jmp     short loc_18001BE5B
0x18001be55  mov     ebx, eax
0x18001be57  mov     [rsp+108h+var_E8], eax
0x18001be5b  test    ebx, ebx
0x18001be5d  jz      short loc_18001BE8A
0x18001be5f  lea     rax, WPP_GLOBAL_Control
0x18001be66  mov     rcx, cs:WPP_GLOBAL_Control
0x18001be6d  cmp     rcx, rax
0x18001be70  jz      loc_18001BD86
0x18001be76  test    byte ptr [rcx+1Ch], 1
0x18001be7a  jz      loc_18001BD86
0x18001be80  mov     edx, 203h
0x18001be85  jmp     loc_18001BDF6
0x18001be8a  cmp     [rsp+108h+var_BC], 0
0x18001be8f  jz      loc_18001BD86
0x18001be95  lea     rdx, SourceString; "proximity"
0x18001be9c  lea     rcx, [rsp+108h+DestinationString]; DestinationString
0x18001bea1  call    cs:__imp_RtlInitUnicodeString
0x18001bea7  lea     r8, [rsp+108h+var_C8]
0x18001beac  lea     rdx, [rsp+108h+DestinationString]
0x18001beb1  mov     rcx, 0FFFFFFFFFFFFFFFCh
0x18001beb8  call    cs:__imp_RtlCapabilityCheck
0x18001bebe  cmp     [rsp+108h+var_C8], 1
0x18001bec3  jnz     short loc_18001BED2
0x18001bec5  mov     [rsp+108h+var_C4], 1
0x18001becd  jmp     loc_18001BD86
0x18001bed2  lea     rdx, [rsp+108h+Sid]; Sid
0x18001bed7  lea     rcx, StringSid; "S-1-15-3-4214768333-1334025770-12240807"...
0x18001bede  call    cs:__imp_ConvertStringSidToSidW
0x18001bee4  test    eax, eax
0x18001bee6  jnz     short loc_18001BF1B
0x18001bee8  call    cs:__imp_GetLastError
0x18001beee  mov     ebx, eax
0x18001bef0  lea     rax, WPP_GLOBAL_Control
0x18001bef7  mov     rcx, cs:WPP_GLOBAL_Control
0x18001befe  cmp     rcx, rax
0x18001bf01  jz      loc_18001BD86
0x18001bf07  test    byte ptr [rcx+1Ch], 1
0x18001bf0b  jz      loc_18001BD86
0x18001bf11  mov     edx, 204h
0x18001bf16  jmp     loc_18001BDF6
0x18001bf1b  lea     r8, [rsp+108h+var_C4]
0x18001bf20  mov     rdx, [rsp+108h+Sid]
0x18001bf25  xor     ecx, ecx
0x18001bf27  call    cs:__imp_CheckTokenCapability
0x18001bf2d  test    eax, eax
0x18001bf2f  jnz     short loc_18001BF5F
0x18001bf31  call    cs:__imp_GetLastError
0x18001bf37  mov     ebx, eax
0x18001bf39  lea     rax, WPP_GLOBAL_Control
0x18001bf40  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bf47  cmp     rcx, rax
0x18001bf4a  jz      loc_18001BD86
0x18001bf50  test    byte ptr [rcx+1Ch], 1
0x18001bf54  jz      loc_18001BD86
0x18001bf5a  jmp     loc_18001BDF1
0x18001bf5f  cmp     [rsp+108h+var_C4], 0
0x18001bf64  jnz     loc_18001BD86
0x18001bf6a  mov     r9, [rsp+108h+var_D0]
0x18001bf6f  lea     r8, [rsp+108h+var_A8]
0x18001bf74  mov     edx, 41h ; 'A'
0x18001bf79  mov     ecx, 80070005h
0x18001bf7e  call    cs:__imp_RoReportCapabilityCheckFailure
0x18001bf84  mov     ebx, 5
0x18001bf89  jmp     loc_18001BD86
0x18001bf8e  mov     edx, 201h
0x18001bf93  xor     r9d, r9d
0x18001bf96  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x18001bf9d  mov     rcx, [rcx+10h]
0x18001bfa1  call    WPP_SF_d
0x18001bfa6  jmp     loc_18001BD86
0x18001bfab  call    cs:__imp_LocalFree
0x18001bfb1  jmp     loc_18001BD94
0x18001bfb6  call    cs:__imp_FwBaseFree
0x18001bfbc  jmp     loc_18001BDA2
0x18001bfc1  lea     rcx, [rsp+108h+Binding]; Binding
0x18001bfc6  call    cs:__imp_RpcBindingFree
0x18001bfcc  test    eax, eax
0x18001bfce  jz      loc_18001BDAE
0x18001bfd4  mov     edx, eax
0x18001bfd6  call    MicrosoftTelemetryAssertTriggeredArgs
0x18001bfdb  jmp     loc_18001BDAE
0x18005ba1c  push    rbp
0x18005ba1e  sub     rsp, 20h
0x18005ba22  mov     rbp, rdx
0x18005ba25  mov     rcx, [rcx]
0x18005ba28  mov     ecx, [rcx]; ExceptionCode
0x18005ba2a  call    cs:__imp_RpcExceptionFilter
0x18005ba30  nop
0x18005ba31  add     rsp, 20h
0x18005ba35  pop     rbp
0x18005ba36  retn
```
