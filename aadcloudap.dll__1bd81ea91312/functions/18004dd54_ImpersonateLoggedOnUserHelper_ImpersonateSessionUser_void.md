# ImpersonateLoggedOnUserHelper::ImpersonateSessionUser(void *)

- ea: `0x18004dd54`
- end: `0x18004dfa0`
- name: `?ImpersonateSessionUser@ImpersonateLoggedOnUserHelper@@QEAAJPEAX@Z`
- size: `588`
- prototype: `int(ImpersonateLoggedOnUserHelper *__hidden this, void *)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800487a8`
- `0x18004a654`

## callees

- `0x1800069c0`
- `0x180006ac4`
- `0x18004dd54`
- `0x180071e14`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004de84`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004def8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004de84`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004def8`
- `ntdll!RtlNtStatusToDosError` at `0x18004de35`
- `ntdll!RtlNtStatusToDosError` at `0x18004de35`
- `ntdll!NtQueryInformationToken` at `0x18004de24`
- `ntdll!NtQueryInformationToken` at `0x18004de24`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18004df73`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18004df73`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x18004de76`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x18004de76`

## string_xrefs

- `0x18004de98`: `No user token available for session`
- `0x18004dd89`: `ImpersonateLoggedOnUserHelper::ImpersonateSessionUser`
- `0x18004df3a`: `Impersonating logged on user for session`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ImpersonateLoggedOnUserHelper::ImpersonateSessionUser(ImpersonateLoggedOnUserHelper *this, void *a2)
{
  signed int LastError; // eax
  int v5; // eax
  unsigned int v6; // ebx
  PULONG ReturnLength; // [rsp+20h] [rbp-60h]
  __int64 v9; // [rsp+30h] [rbp-50h]
  const char *v10[6]; // [rsp+50h] [rbp-30h] BYREF
  signed int v11; // [rsp+B0h] [rbp+30h] BYREF
  ULONG TokenInformation; // [rsp+B8h] [rbp+38h] BYREF
  ULONG v13; // [rsp+C0h] [rbp+40h] BYREF

  v11 = 0;
  TokenInformation = 0;
  v13 = 0;
  DbgTracePrintHelper<unsigned long>::DbgTracePrintHelper<unsigned long>(
    (__int64)v10,
    (int)"unimpersonatehelper.cpp",
    (int)"ImpersonateLoggedOnUserHelper::ImpersonateSessionUser",
    (int)&v11);
  *(_DWORD *)this = 0;
  *((_QWORD *)this + 1) = 0;
  if ( a2 )
  {
    v5 = NtQueryInformationToken(a2, TokenSessionId, &TokenInformation, 4u, &v13);
    if ( v5 < 0 )
    {
      LastError = RtlNtStatusToDosError(v5);
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v11 = LastError;
      if ( LastError < 0 )
      {
        LODWORD(v9) = 104;
        goto LABEL_4;
      }
    }
    if ( !WTSQueryUserToken(TokenInformation, (PHANDLE)this + 1) )
    {
      if ( GetLastError() == 1008 )
      {
        WPPTraceLogA(
          4,
          0,
          "%x 0x%08x %s:%u : %s:%u",
          4,
          0,
          "unimpersonatehelper.cpp",
          111,
          "No user token available for session",
          TokenInformation);
        LastError = -2147187381;
        LODWORD(v9) = 112;
        goto LABEL_3;
      }
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v11 = LastError;
      if ( LastError < 0 )
      {
        LODWORD(v9) = 115;
        goto LABEL_4;
      }
    }
    WPPTraceLogA(
      4,
      0,
      "%x 0x%08x %s:%u : %s:%u",
      4,
      0,
      "unimpersonatehelper.cpp",
      118,
      "Impersonating logged on user for session",
      TokenInformation);
    *(_DWORD *)this = ImpersonateLoggedOnUser(*((HANDLE *)this + 1));
    goto LABEL_18;
  }
  LastError = -2147024809;
  LODWORD(v9) = 97;
LABEL_3:
  v11 = LastError;
LABEL_4:
  LODWORD(ReturnLength) = LastError;
  WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, ReturnLength, "unimpersonatehelper.cpp", v9, "HRESULT", &base);
LABEL_18:
  v6 = v11;
  DbgTracePrintHelper<long>::~DbgTracePrintHelper<long>(v10);
  return v6;
}

```

## disassembly

```asm
0x18004dd54  mov     [rsp-28h+arg_18], rbx
0x18004dd59  push    rbp
0x18004dd5a  push    rsi
0x18004dd5b  push    rdi
0x18004dd5c  push    r12
0x18004dd5e  push    r15
0x18004dd60  mov     rbp, rsp
0x18004dd63  sub     rsp, 80h
0x18004dd6a  mov     rsi, rdx
0x18004dd6d  mov     rdi, rcx
0x18004dd70  mov     [rbp+arg_0], 0
0x18004dd77  mov     [rbp+TokenInformation], 0
0x18004dd7e  mov     [rbp+arg_10], 0
0x18004dd85  lea     r9, [rbp+arg_0]
0x18004dd89  lea     r8, aImpersonatelog_0; "ImpersonateLoggedOnUserHelper::Imperson"...
0x18004dd90  lea     r15, aOnecoreuapDsEx_27+21h; "unimpersonatehelper.cpp"
0x18004dd97  mov     rdx, r15
0x18004dd9a  lea     rcx, [rbp+var_30]
0x18004dd9e  call    ??0?$DbgTracePrintHelper@K@@QEAA@PEBD0AEAKW4AadTracingEventType@@@Z; DbgTracePrintHelper<ulong>::DbgTracePrintHelper<ulong>(char const *,char const *,ulong &,AadTracingEventType)
0x18004dda3  nop
0x18004dda4  mov     dword ptr [rdi], 0
0x18004ddaa  lea     rbx, [rdi+8]
0x18004ddae  mov     qword ptr [rbx], 0
0x18004ddb5  test    rsi, rsi
0x18004ddb8  jnz     short loc_18004DE06
0x18004ddba  mov     eax, 80070057h
0x18004ddbf  lea     rcx, base
0x18004ddc6  mov     [rsp+80h+var_40], rcx
0x18004ddcb  lea     rcx, aHresult; "HRESULT"
0x18004ddd2  mov     [rsp+80h+var_48], rcx
0x18004ddd7  mov     dword ptr [rsp+80h+var_50], 61h ; 'a'
0x18004dddf  mov     [rbp+arg_0], eax
0x18004dde2  mov     [rsp+80h+var_58], r15
0x18004dde7  mov     dword ptr [rsp+80h+ReturnLength], eax
0x18004ddeb  mov     ecx, 2
0x18004ddf0  mov     r9d, ecx
0x18004ddf3  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x18004ddfa  xor     edx, edx
0x18004ddfc  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x18004de01  jmp     loc_18004DF7B
0x18004de06  lea     rax, [rbp+arg_10]
0x18004de0a  mov     [rsp+80h+ReturnLength], rax; ReturnLength
0x18004de0f  mov     r12d, 4
0x18004de15  mov     r9d, r12d; TokenInformationLength
0x18004de18  lea     r8, [rbp+TokenInformation]; TokenInformation
0x18004de1c  lea     edx, [r12+8]; TokenInformationClass
0x18004de21  mov     rcx, rsi; TokenHandle
0x18004de24  call    cs:__imp_NtQueryInformationToken
0x18004de2a  mov     esi, 80070000h
0x18004de2f  test    eax, eax
0x18004de31  jns     short loc_18004DE70
0x18004de33  mov     ecx, eax; Status
0x18004de35  call    cs:__imp_RtlNtStatusToDosError
0x18004de3b  test    eax, eax
0x18004de3d  jle     short loc_18004DE44
0x18004de3f  movzx   eax, ax
0x18004de42  or      eax, esi
0x18004de44  mov     [rbp+arg_0], eax
0x18004de47  test    eax, eax
0x18004de49  jns     short loc_18004DE70
0x18004de4b  lea     rcx, base
0x18004de52  mov     [rsp+80h+var_40], rcx
0x18004de57  lea     rcx, aHresult; "HRESULT"
0x18004de5e  mov     [rsp+80h+var_48], rcx
0x18004de63  mov     dword ptr [rsp+80h+var_50], 68h ; 'h'
0x18004de6b  jmp     loc_18004DDE2
0x18004de70  mov     rdx, rbx; phToken
0x18004de73  mov     ecx, [rbp+TokenInformation]; SessionId
0x18004de76  call    cs:__imp_WTSQueryUserToken
0x18004de7c  test    eax, eax
0x18004de7e  jnz     loc_18004DF33
0x18004de84  call    cs:__imp_GetLastError
0x18004de8a  cmp     eax, 3F0h
0x18004de8f  jnz     short loc_18004DEF8
0x18004de91  mov     eax, [rbp+TokenInformation]
0x18004de94  mov     dword ptr [rsp+80h+var_40], eax
0x18004de98  lea     rax, aNoUserTokenAva; "No user token available for session"
0x18004de9f  mov     [rsp+80h+var_48], rax
0x18004dea4  mov     dword ptr [rsp+80h+var_50], 6Fh ; 'o'
0x18004deac  mov     [rsp+80h+var_58], r15
0x18004deb1  mov     [rsp+80h+ReturnLength], 0
0x18004deba  mov     r9d, r12d
0x18004debd  lea     r8, aX0x08xSUSU; "%x 0x%08x %s:%u : %s:%u"
0x18004dec4  xor     edx, edx
0x18004dec6  mov     ecx, r12d
0x18004dec9  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x18004dece  mov     eax, 8004854Bh
0x18004ded3  lea     rcx, base
0x18004deda  mov     [rsp+80h+var_40], rcx
0x18004dedf  lea     rcx, aHresult; "HRESULT"
0x18004dee6  mov     [rsp+80h+var_48], rcx
0x18004deeb  mov     dword ptr [rsp+80h+var_50], 70h ; 'p'
0x18004def3  jmp     loc_18004DDDF
0x18004def8  call    cs:__imp_GetLastError
0x18004defe  test    eax, eax
0x18004df00  jle     short loc_18004DF07
0x18004df02  movzx   eax, ax
0x18004df05  or      eax, esi
0x18004df07  mov     [rbp+arg_0], eax
0x18004df0a  test    eax, eax
0x18004df0c  jns     short loc_18004DF33
0x18004df0e  lea     rcx, base
0x18004df15  mov     [rsp+80h+var_40], rcx
0x18004df1a  lea     rcx, aHresult; "HRESULT"
0x18004df21  mov     [rsp+80h+var_48], rcx
0x18004df26  mov     dword ptr [rsp+80h+var_50], 73h ; 's'
0x18004df2e  jmp     loc_18004DDE2
0x18004df33  mov     eax, [rbp+TokenInformation]
0x18004df36  mov     dword ptr [rsp+80h+var_40], eax
0x18004df3a  lea     rax, aImpersonatingL; "Impersonating logged on user for sessio"...
0x18004df41  mov     [rsp+80h+var_48], rax
0x18004df46  mov     dword ptr [rsp+80h+var_50], 76h ; 'v'
0x18004df4e  mov     [rsp+80h+var_58], r15
0x18004df53  mov     [rsp+80h+ReturnLength], 0
0x18004df5c  mov     r9d, r12d
0x18004df5f  lea     r8, aX0x08xSUSU; "%x 0x%08x %s:%u : %s:%u"
0x18004df66  xor     edx, edx
0x18004df68  mov     ecx, r12d
0x18004df6b  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x18004df70  mov     rcx, [rbx]; hToken
0x18004df73  call    cs:__imp_ImpersonateLoggedOnUser
0x18004df79  mov     [rdi], eax
0x18004df7b  mov     ebx, [rbp+arg_0]
0x18004df7e  lea     rcx, [rbp+var_30]
0x18004df82  call    ??1?$DbgTracePrintHelper@J@@QEAA@XZ; DbgTracePrintHelper<long>::~DbgTracePrintHelper<long>(void)
0x18004df87  mov     eax, ebx
0x18004df89  mov     rbx, [rsp+80h+arg_18]
0x18004df91  add     rsp, 80h
0x18004df98  pop     r15
0x18004df9a  pop     r12
0x18004df9c  pop     rdi
0x18004df9d  pop     rsi
0x18004df9e  pop     rbp
0x18004df9f  retn
```
