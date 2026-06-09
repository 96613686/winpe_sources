# NetworkIsolationDiagnoseConnectFailure

- ea: `0x18001c170`
- end: `0x18001c549`
- name: `NetworkIsolationDiagnoseConnectFailure`
- size: `985`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180005e0c`
- `0x18000ea10`
- `0x18001c170`
- `0x180020544`
- `0x180026798`
- `0x1800294b0`

## import_xrefs

- `RPCRT4!RpcExceptionFilter` at `0x18005fbe4`
- `RPCRT4!RpcExceptionFilter` at `0x18005fbe4`
- `RPCRT4!RpcBindingFree` at `0x18001c529`
- `RPCRT4!RpcBindingFree` at `0x18001c529`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c427`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c47c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c427`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c47c`
- `ntdll!RtlInitUnicodeString` at `0x18001c3ce`
- `ntdll!RtlInitUnicodeString` at `0x18001c3ce`
- `ntdll!RtlCapabilityCheck` at `0x18001c3eb`
- `ntdll!RtlCapabilityCheck` at `0x18001c3eb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c502`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c502`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18001c27f`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18001c27f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001c243`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001c243`
- `api-ms-win-security-base-l1-2-0!CheckTokenCapability` at `0x18001c46c`
- `api-ms-win-security-base-l1-2-0!CheckTokenCapability` at `0x18001c46c`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18001c417`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18001c417`
- `api-ms-win-core-winrt-error-l1-1-0!RoGetErrorReportingFlags` at `0x18001c254`
- `api-ms-win-core-winrt-error-l1-1-0!RoGetErrorReportingFlags` at `0x18001c254`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoReportCapabilityCheckFailure` at `0x18001c4cf`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoReportCapabilityCheckFailure` at `0x18001c4cf`
- `fwbase!FwBaseFree` at `0x18001c513`
- `fwbase!FwBaseFree` at `0x18001c513`
- `fwbase!FwHResultToWindowsError` at `0x18001c262`
- `fwbase!FwHResultToWindowsError` at `0x18001c262`

## string_xrefs

- `0x18001c1b6`: `A network capability is required to access this network resource`

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
      v6 = 511;
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
      v6 = 512;
      v7 = 0;
LABEL_38:
      WPP_SF_d(*((_QWORD *)v4 + 2), v6, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids, v7);
      goto LABEL_6;
    }
    LastError = Int_FWLocalRpcBindingCreate(&Binding);
    if ( LastError )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v6 = 513;
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
          v6 = 514;
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
              v6 = 516;
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
            v6 = 515;
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
0x18001c170  mov     r11, rsp
0x18001c173  mov     [r11+10h], rbx
0x18001c177  push    rsi
0x18001c178  sub     rsp, 100h
0x18001c17f  mov     rax, cs:__security_cookie
0x18001c186  xor     rax, rsp
0x18001c189  mov     [rsp+108h+var_18], rax
0x18001c191  mov     rsi, rcx
0x18001c194  mov     [rsp+108h+var_C0], 0
0x18001c19c  mov     [rsp+108h+Binding], 0
0x18001c1a5  mov     [rsp+108h+var_BC], 0
0x18001c1ad  mov     [rsp+108h+var_D0], 0
0x18001c1b6  movaps  xmm0, xmmword ptr cs:aANetworkCapabi; "A network capability is required to acc"...
0x18001c1bd  movups  [rsp+108h+var_A8], xmm0
0x18001c1c2  movaps  xmm1, xmmword ptr cs:aANetworkCapabi+10h; "k capability is required to access this"...
0x18001c1c9  movups  [rsp+108h+var_98], xmm1
0x18001c1ce  movaps  xmm0, xmmword ptr cs:aANetworkCapabi+20h; "lity is required to access this network"...
0x18001c1d5  movups  [rsp+108h+var_88], xmm0
0x18001c1dd  movaps  xmm1, xmmword ptr cs:aANetworkCapabi+30h; "required to access this network resourc"...
0x18001c1e4  movups  xmmword ptr [r11-78h], xmm1
0x18001c1e9  movaps  xmm0, xmmword ptr cs:aANetworkCapabi+40h; " to access this network resource"
0x18001c1f0  movups  xmmword ptr [r11-68h], xmm0
0x18001c1f5  movaps  xmm1, xmmword ptr cs:aANetworkCapabi+50h; "ss this network resource"
0x18001c1fc  movups  xmmword ptr [r11-58h], xmm1
0x18001c201  movaps  xmm0, xmmword ptr cs:aANetworkCapabi+60h; "network resource"
0x18001c208  movups  xmmword ptr [r11-48h], xmm0
0x18001c20d  movaps  xmm1, xmmword ptr cs:aANetworkCapabi+70h; "resource"
0x18001c214  movups  xmmword ptr [r11-38h], xmm1
0x18001c219  movzx   eax, word ptr cs:aANetworkCapabi+80h; ""
0x18001c220  mov     [r11-28h], ax
0x18001c225  mov     [rsp+108h+var_C4], 0
0x18001c22d  mov     [rsp+108h+var_C8], 0
0x18001c232  mov     [rsp+108h+Sid], 0
0x18001c23b  xorps   xmm0, xmm0
0x18001c23e  movups  xmmword ptr [rsp+108h+DestinationString.Length], xmm0
0x18001c243  call    cs:__imp_GetTickCount64
0x18001c24a  nop     dword ptr [rax+rax+00h]
0x18001c24f  lea     rcx, [rsp+108h+var_C0]
0x18001c254  call    cs:__imp_RoGetErrorReportingFlags
0x18001c25b  nop     dword ptr [rax+rax+00h]
0x18001c260  mov     ecx, eax
0x18001c262  call    cs:__imp_FwHResultToWindowsError
0x18001c269  nop     dword ptr [rax+rax+00h]
0x18001c26e  mov     ebx, eax
0x18001c270  test    eax, eax
0x18001c272  jnz     loc_18001C2FE
0x18001c278  test    byte ptr [rsp+108h+var_C0], 1
0x18001c27d  jnz     short loc_18001C293
0x18001c27f  call    cs:__imp_IsDebuggerPresent
0x18001c286  nop     dword ptr [rax+rax+00h]
0x18001c28b  test    eax, eax
0x18001c28d  jnz     loc_18001C32B
0x18001c293  xor     ebx, ebx
0x18001c295  lea     rax, WPP_GLOBAL_Control
0x18001c29c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c2a3  cmp     rcx, rax
0x18001c2a6  jz      short loc_18001C2B2
0x18001c2a8  test    byte ptr [rcx+1Ch], 1
0x18001c2ac  jnz     loc_18001C4E5
0x18001c2b2  mov     rcx, [rsp+108h+Sid]; hMem
0x18001c2b7  test    rcx, rcx
0x18001c2ba  jnz     loc_18001C502
0x18001c2c0  mov     rcx, [rsp+108h+var_D0]
0x18001c2c5  test    rcx, rcx
0x18001c2c8  jnz     loc_18001C513
0x18001c2ce  cmp     [rsp+108h+Binding], 0
0x18001c2d4  jnz     loc_18001C524
0x18001c2da  mov     eax, ebx
0x18001c2dc  mov     rcx, [rsp+108h+var_18]
0x18001c2e4  xor     rcx, rsp; StackCookie
0x18001c2e7  call    __security_check_cookie
0x18001c2ec  mov     rbx, [rsp+108h+arg_8]
0x18001c2f4  add     rsp, 100h
0x18001c2fb  pop     rsi
0x18001c2fc  retn
0x18001c2fe  lea     rax, WPP_GLOBAL_Control
0x18001c305  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c30c  cmp     rcx, rax
0x18001c30f  jz      short loc_18001C2B2
0x18001c311  test    byte ptr [rcx+1Ch], 1
0x18001c315  jz      short loc_18001C2B2
0x18001c317  mov     edx, 1FFh
0x18001c31c  jmp     short loc_18001C323
0x18001c31e  mov     edx, 204h
0x18001c323  mov     r9d, ebx
0x18001c326  jmp     loc_18001C4ED
0x18001c32b  lea     rcx, [rsp+108h+Binding]
0x18001c330  call    Int_FWLocalRpcBindingCreate
0x18001c335  mov     ebx, eax
0x18001c337  test    eax, eax
0x18001c339  jz      short loc_18001C363
0x18001c33b  lea     rax, WPP_GLOBAL_Control
0x18001c342  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c349  cmp     rcx, rax
0x18001c34c  jz      loc_18001C2B2
0x18001c352  test    byte ptr [rcx+1Ch], 1
0x18001c356  jz      loc_18001C2B2
0x18001c35c  mov     edx, 201h
0x18001c361  jmp     short loc_18001C323
0x18001c363  lea     r9, [rsp+108h+var_D0]
0x18001c368  lea     r8, [rsp+108h+var_BC]
0x18001c36d  mov     rdx, rsi
0x18001c370  mov     rcx, [rsp+108h+Binding]
0x18001c375  call    RPC_NetworkIsolationDiagnoseConnectFailure
0x18001c37a  mov     ebx, eax
0x18001c37c  mov     [rsp+108h+var_E8], eax
0x18001c380  jmp     short loc_18001C388
0x18001c382  mov     ebx, eax
0x18001c384  mov     [rsp+108h+var_E8], eax
0x18001c388  test    ebx, ebx
0x18001c38a  jz      short loc_18001C3B7
0x18001c38c  lea     rax, WPP_GLOBAL_Control
0x18001c393  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c39a  cmp     rcx, rax
0x18001c39d  jz      loc_18001C2B2
0x18001c3a3  test    byte ptr [rcx+1Ch], 1
0x18001c3a7  jz      loc_18001C2B2
0x18001c3ad  mov     edx, 202h
0x18001c3b2  jmp     loc_18001C323
0x18001c3b7  cmp     [rsp+108h+var_BC], 0
0x18001c3bc  jz      loc_18001C2B2
0x18001c3c2  lea     rdx, SourceString; "proximity"
0x18001c3c9  lea     rcx, [rsp+108h+DestinationString]; DestinationString
0x18001c3ce  call    cs:__imp_RtlInitUnicodeString
0x18001c3d5  nop     dword ptr [rax+rax+00h]
0x18001c3da  lea     r8, [rsp+108h+var_C8]
0x18001c3df  lea     rdx, [rsp+108h+DestinationString]
0x18001c3e4  mov     rcx, 0FFFFFFFFFFFFFFFCh
0x18001c3eb  call    cs:__imp_RtlCapabilityCheck
0x18001c3f2  nop     dword ptr [rax+rax+00h]
0x18001c3f7  cmp     [rsp+108h+var_C8], 1
0x18001c3fc  jnz     short loc_18001C40B
0x18001c3fe  mov     [rsp+108h+var_C4], 1
0x18001c406  jmp     loc_18001C2B2
0x18001c40b  lea     rdx, [rsp+108h+Sid]; Sid
0x18001c410  lea     rcx, StringSid; "S-1-15-3-4214768333-1334025770-12240807"...
0x18001c417  call    cs:__imp_ConvertStringSidToSidW
0x18001c41e  nop     dword ptr [rax+rax+00h]
0x18001c423  test    eax, eax
0x18001c425  jnz     short loc_18001C460
0x18001c427  call    cs:__imp_GetLastError
0x18001c42e  nop     dword ptr [rax+rax+00h]
0x18001c433  mov     ebx, eax
0x18001c435  lea     rax, WPP_GLOBAL_Control
0x18001c43c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c443  cmp     rcx, rax
0x18001c446  jz      loc_18001C2B2
0x18001c44c  test    byte ptr [rcx+1Ch], 1
0x18001c450  jz      loc_18001C2B2
0x18001c456  mov     edx, 203h
0x18001c45b  jmp     loc_18001C323
0x18001c460  lea     r8, [rsp+108h+var_C4]
0x18001c465  mov     rdx, [rsp+108h+Sid]
0x18001c46a  xor     ecx, ecx
0x18001c46c  call    cs:__imp_CheckTokenCapability
0x18001c473  nop     dword ptr [rax+rax+00h]
0x18001c478  test    eax, eax
0x18001c47a  jnz     short loc_18001C4B0
0x18001c47c  call    cs:__imp_GetLastError
0x18001c483  nop     dword ptr [rax+rax+00h]
0x18001c488  mov     ebx, eax
0x18001c48a  lea     rax, WPP_GLOBAL_Control
0x18001c491  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c498  cmp     rcx, rax
0x18001c49b  jz      loc_18001C2B2
0x18001c4a1  test    byte ptr [rcx+1Ch], 1
0x18001c4a5  jz      loc_18001C2B2
0x18001c4ab  jmp     loc_18001C31E
0x18001c4b0  cmp     [rsp+108h+var_C4], 0
0x18001c4b5  jnz     loc_18001C2B2
0x18001c4bb  mov     r9, [rsp+108h+var_D0]
0x18001c4c0  lea     r8, [rsp+108h+var_A8]
0x18001c4c5  mov     edx, 41h ; 'A'
0x18001c4ca  mov     ecx, 80070005h
0x18001c4cf  call    cs:__imp_RoReportCapabilityCheckFailure
0x18001c4d6  nop     dword ptr [rax+rax+00h]
0x18001c4db  mov     ebx, 5
0x18001c4e0  jmp     loc_18001C2B2
0x18001c4e5  mov     edx, 200h
0x18001c4ea  xor     r9d, r9d
0x18001c4ed  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x18001c4f4  mov     rcx, [rcx+10h]
0x18001c4f8  call    WPP_SF_d
0x18001c4fd  jmp     loc_18001C2B2
0x18001c502  call    cs:__imp_LocalFree
0x18001c509  nop     dword ptr [rax+rax+00h]
0x18001c50e  jmp     loc_18001C2C0
0x18001c513  call    cs:__imp_FwBaseFree
0x18001c51a  nop     dword ptr [rax+rax+00h]
0x18001c51f  jmp     loc_18001C2CE
0x18001c524  lea     rcx, [rsp+108h+Binding]; Binding
0x18001c529  call    cs:__imp_RpcBindingFree
0x18001c530  nop     dword ptr [rax+rax+00h]
0x18001c535  test    eax, eax
0x18001c537  jz      loc_18001C2DA
0x18001c53d  mov     edx, eax; __annotation("Debug", "TelemetryAssert", "status == RPC_S_OK", "RpcBindingFree")
0x18001c53f  call    MicrosoftTelemetryAssertTriggeredArgs
0x18001c544  jmp     loc_18001C2DA
0x18005fbd6  push    rbp
0x18005fbd8  sub     rsp, 20h
0x18005fbdc  mov     rbp, rdx
0x18005fbdf  mov     rcx, [rcx]
0x18005fbe2  mov     ecx, [rcx]; ExceptionCode
0x18005fbe4  call    cs:__imp_RpcExceptionFilter
0x18005fbeb  nop     dword ptr [rax+rax+00h]
0x18005fbf0  nop
0x18005fbf1  add     rsp, 20h
0x18005fbf5  pop     rbp
0x18005fbf6  retn
```
