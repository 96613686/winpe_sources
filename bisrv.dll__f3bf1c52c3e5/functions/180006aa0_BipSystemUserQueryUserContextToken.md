# BipSystemUserQueryUserContextToken

- ea: `0x180006aa0`
- end: `0x180006db0`
- name: `BipSystemUserQueryUserContextToken`
- size: `784`
- prototype: `__int64 __fastcall(ULONG SessionId, PSID Sid1)`
- caller_count: `5`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800059a4`
- `0x1800069c4`
- `0x180037500`
- `0x180044908`
- `0x1800534f8`

## callees

- `0x180006aa0`
- `0x180039f18`
- `0x18006d364`
- `0x18007078c`
- `0x18009467a`
- `0x1800946a0`

## import_xrefs

- `ntdll!RtlEqualSid` at `0x180006bec`
- `ntdll!RtlEqualSid` at `0x180006bec`
- `ntdll!NtClose` at `0x180006c55`
- `ntdll!NtClose` at `0x180006c55`
- `ntdll!RtlConvertSidToUnicodeString` at `0x180006b51`
- `ntdll!RtlConvertSidToUnicodeString` at `0x180006b51`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006b9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006ba7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006bb4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006b9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006ba7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006bb4`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180006d82`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180006d82`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x180006c0c`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x180006c0c`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContextFromSid` at `0x180006b60`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContextFromSid` at `0x180006b60`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x180006b8e`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x180006b8e`

## pseudocode

```c
__int64 __fastcall BipSystemUserQueryUserContextToken(ULONG SessionId, PSID Sid1, _QWORD *a3)
{
  int v6; // eax
  signed int LastError; // ebx
  int v8; // edi
  unsigned int v9; // eax
  int v10; // eax
  unsigned int v11; // eax
  __int64 *v12; // rcx
  int v13; // eax
  __int64 v15; // [rsp+30h] [rbp-D0h] BYREF
  void *phToken; // [rsp+38h] [rbp-C8h] BYREF
  int v17; // [rsp+40h] [rbp-C0h] BYREF
  signed int v18; // [rsp+44h] [rbp-BCh] BYREF
  _DWORD v19[2]; // [rsp+48h] [rbp-B8h] BYREF
  _UNICODE_STRING UnicodeString; // [rsp+50h] [rbp-B0h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+60h] [rbp-A0h] BYREF
  _OWORD Sid2[4]; // [rsp+70h] [rbp-90h] BYREF
  int v23; // [rsp+B0h] [rbp-50h]
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+C0h] [rbp-40h] BYREF
  __int16 *v25; // [rsp+D0h] [rbp-30h]
  int v26; // [rsp+D8h] [rbp-28h]
  int v27; // [rsp+DCh] [rbp-24h]
  _DWORD *v28; // [rsp+E0h] [rbp-20h]
  __int64 v29; // [rsp+E8h] [rbp-18h]
  __int64 *v30; // [rsp+F0h] [rbp-10h]
  int v31; // [rsp+F8h] [rbp-8h]
  int v32; // [rsp+FCh] [rbp-4h]
  signed int *v33; // [rsp+100h] [rbp+0h]
  __int64 v34; // [rsp+108h] [rbp+8h]
  int *v35; // [rsp+110h] [rbp+10h]
  __int64 v36; // [rsp+118h] [rbp+18h]
  _BYTE v37[384]; // [rsp+120h] [rbp+20h] BYREF

  v15 = 0;
  UnicodeString = 0;
  v23 = 0;
  memset(Sid2, 0, sizeof(Sid2));
  phToken = 0;
  if ( !(unsigned __int8)IsUMgrQueryUserContextFromSidPresent()
    || !(unsigned __int8)IsUMgrQueryUserContextFromSidPresent() )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs();
    v8 = 1000;
    LastError = -1073741822;
    goto LABEL_22;
  }
  if ( !SessionId )
  {
    memset_0(v37, 0, 0x178u);
    *(_QWORD *)&UnicodeString.Length = 24641536;
    UnicodeString.Buffer = (PWSTR)v37;
    RtlConvertSidToUnicodeString(&UnicodeString, Sid1, 0);
    v6 = UMgrQueryUserContextFromSid(v37, &v15);
    if ( v6 < 0 )
    {
      LastError = (unsigned __int16)v6;
      v8 = 2000;
      v9 = (unsigned __int16)v6 | 0xC0070000;
      if ( LastError )
        LastError = v9;
      goto LABEL_22;
    }
LABEL_20:
    LastError = 0;
    *a3 = v15;
    v8 = 0;
    goto LABEL_22;
  }
  if ( !WTSQueryUserToken(SessionId, &phToken) )
  {
    v8 = 3000;
    if ( (int)GetLastError() > 0 )
      LastError = (unsigned __int16)GetLastError() | 0xC0070000;
    else
      LastError = GetLastError();
    goto LABEL_22;
  }
  LastError = BipSystemUserQueryUserSidFromTokenHandle(phToken, Sid2);
  if ( LastError < 0 )
  {
    v8 = 4000;
    goto LABEL_22;
  }
  if ( !RtlEqualSid(Sid1, Sid2) )
  {
    v8 = 5000;
    LastError = -1073741720;
    goto LABEL_22;
  }
  v10 = UMgrQueryUserContext(phToken, &v15);
  if ( v10 >= 0 )
    goto LABEL_20;
  LastError = (unsigned __int16)v10;
  v8 = 6000;
  v11 = (unsigned __int16)v10 | 0xC0070000;
  if ( LastError )
    LastError = v11;
LABEL_22:
  if ( phToken )
    NtClose(phToken);
  if ( LastError < 0
    && (unsigned int)dword_1800C3098 > 2
    && (qword_1800C30A8 & 3) != 0
    && (qword_1800C30B0 & 3) == qword_1800C30B0 )
  {
    v17 = v8;
    v35 = &v17;
    v12 = &BipTraceLoggingNullSid;
    v18 = LastError;
    v33 = &v18;
    v19[0] = SessionId;
    v36 = 4;
    if ( Sid1 )
      v12 = (__int64 *)Sid1;
    v34 = 4;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 3;
    v13 = *((unsigned __int8 *)v12 + 1);
    v30 = v12;
    v32 = 0;
    v29 = 4;
    v31 = 4 * v13 + 8;
    v28 = v19;
    *(_DWORD *)&EventDescriptor.Level = 2;
    UserData.Ptr = (ULONGLONG)off_1800C30A0;
    UserData.Size = *(unsigned __int16 *)off_1800C30A0;
    v25 = &word_1800AD32E;
    UserData.Reserved = 2;
    v26 = 94;
    v27 = 1;
    v19[1] = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 6u, &UserData);
  }
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180006aa0  mov     [rsp-8+arg_18], rbx
0x180006aa5  push    rbp
0x180006aa6  push    rsi
0x180006aa7  push    rdi
0x180006aa8  push    r14
0x180006aaa  push    r15
0x180006aac  lea     rbp, [rsp-1B0h]
0x180006ab4  sub     rsp, 2B0h
0x180006abb  mov     rax, cs:__security_cookie
0x180006ac2  xor     rax, rsp
0x180006ac5  mov     [rbp+1D0h+var_30], rax
0x180006acc  xorps   xmm0, xmm0
0x180006acf  xor     r15d, r15d
0x180006ad2  xor     eax, eax
0x180006ad4  mov     [rsp+2D0h+var_2A0], r15
0x180006ad9  movups  xmmword ptr [rsp+2D0h+UnicodeString.Length], xmm0
0x180006ade  mov     [rbp+1D0h+var_220], eax
0x180006ae1  mov     rdi, r8
0x180006ae4  movups  [rsp+2D0h+Sid2], xmm0
0x180006ae9  mov     [rsp+2D0h+phToken], r15
0x180006aee  mov     r14, rdx
0x180006af1  movups  [rbp+1D0h+var_250], xmm0
0x180006af5  mov     esi, ecx
0x180006af7  movups  [rbp+1D0h+var_240], xmm0
0x180006afb  movups  [rbp+1D0h+var_230], xmm0
0x180006aff  call    IsUMgrQueryUserContextFromSidPresent
0x180006b04  test    al, al
0x180006b06  jz      loc_180006C3C
0x180006b0c  call    IsUMgrQueryUserContextFromSidPresent
0x180006b11  test    al, al
0x180006b13  jz      loc_180006C3C
0x180006b19  test    esi, esi
0x180006b1b  jnz     short loc_180006B87
0x180006b1d  mov     ebx, 178h
0x180006b22  lea     rcx, [rbp+1D0h+var_1B0]; void *
0x180006b26  mov     r8d, ebx; Size
0x180006b29  xor     edx, edx; Val
0x180006b2b  call    memset_0
0x180006b30  xorps   xmm0, xmm0
0x180006b33  lea     rax, [rbp+1D0h+var_1B0]
0x180006b37  movups  xmmword ptr [rsp+2D0h+UnicodeString.Length], xmm0
0x180006b3c  xor     r8d, r8d; AllocateDestinationString
0x180006b3f  mov     [rsp+2D0h+UnicodeString.MaximumLength], bx
0x180006b44  mov     rdx, r14; Sid
0x180006b47  mov     [rsp+2D0h+UnicodeString.Buffer], rax
0x180006b4c  lea     rcx, [rsp+2D0h+UnicodeString]; UnicodeString
0x180006b51  call    cs:__imp_RtlConvertSidToUnicodeString
0x180006b57  lea     rdx, [rsp+2D0h+var_2A0]
0x180006b5c  lea     rcx, [rbp+1D0h+var_1B0]
0x180006b60  call    cs:__imp_UMgrQueryUserContextFromSid
0x180006b66  test    eax, eax
0x180006b68  jns     loc_180006C2C
0x180006b6e  movzx   ebx, ax
0x180006b71  mov     edi, 7D0h
0x180006b76  mov     eax, ebx
0x180006b78  or      eax, 0C0070000h
0x180006b7d  test    ebx, ebx
0x180006b7f  cmovnz  ebx, eax
0x180006b82  jmp     loc_180006C4B
0x180006b87  lea     rdx, [rsp+2D0h+phToken]; phToken
0x180006b8c  mov     ecx, esi; SessionId
0x180006b8e  call    cs:__imp_WTSQueryUserToken
0x180006b94  test    eax, eax
0x180006b96  jnz     short loc_180006BC8
0x180006b98  mov     edi, 0BB8h
0x180006b9d  call    cs:__imp_GetLastError
0x180006ba3  test    eax, eax
0x180006ba5  jg      short loc_180006BB4
0x180006ba7  call    cs:__imp_GetLastError
0x180006bad  mov     ebx, eax
0x180006baf  jmp     loc_180006C4B
0x180006bb4  call    cs:__imp_GetLastError
0x180006bba  movzx   ebx, ax
0x180006bbd  or      ebx, 0C0070000h
0x180006bc3  jmp     loc_180006C4B
0x180006bc8  mov     rcx, [rsp+2D0h+phToken]; TokenHandle
0x180006bcd  lea     rdx, [rsp+2D0h+Sid2]; DestinationSid
0x180006bd2  call    ?BipSystemUserQueryUserSidFromTokenHandle@@YAJPEAXPEAU_BI_SID@@@Z; BipSystemUserQueryUserSidFromTokenHandle(void *,_BI_SID *)
0x180006bd7  mov     ebx, eax
0x180006bd9  test    eax, eax
0x180006bdb  jns     short loc_180006BE4
0x180006bdd  mov     edi, 0FA0h
0x180006be2  jmp     short loc_180006C4B
0x180006be4  lea     rdx, [rsp+2D0h+Sid2]; Sid2
0x180006be9  mov     rcx, r14; Sid1
0x180006bec  call    cs:__imp_RtlEqualSid
0x180006bf2  test    al, al
0x180006bf4  jnz     short loc_180006C02
0x180006bf6  mov     edi, 1388h
0x180006bfb  mov     ebx, 0C0000068h
0x180006c00  jmp     short loc_180006C4B
0x180006c02  mov     rcx, [rsp+2D0h+phToken]
0x180006c07  lea     rdx, [rsp+2D0h+var_2A0]
0x180006c0c  call    cs:__imp_UMgrQueryUserContext
0x180006c12  test    eax, eax
0x180006c14  jns     short loc_180006C2C
0x180006c16  movzx   ebx, ax
0x180006c19  mov     edi, 1770h
0x180006c1e  mov     eax, ebx
0x180006c20  or      eax, 0C0070000h
0x180006c25  test    ebx, ebx
0x180006c27  cmovnz  ebx, eax
0x180006c2a  jmp     short loc_180006C4B
0x180006c2c  mov     rax, [rsp+2D0h+var_2A0]
0x180006c31  mov     ebx, r15d
0x180006c34  mov     [rdi], rax
0x180006c37  mov     edi, r15d
0x180006c3a  jmp     short loc_180006C4B
0x180006c3c  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180006c41  mov     edi, 3E8h
0x180006c46  mov     ebx, 0C0000002h
0x180006c4b  mov     rcx, [rsp+2D0h+phToken]; Handle
0x180006c50  test    rcx, rcx
0x180006c53  jz      short loc_180006C5B
0x180006c55  call    cs:__imp_NtClose
0x180006c5b  test    ebx, ebx
0x180006c5d  jns     loc_180006D88
0x180006c63  mov     eax, cs:dword_1800C3098
0x180006c69  cmp     eax, 2
0x180006c6c  jbe     loc_180006D88
0x180006c72  mov     rcx, cs:qword_1800C30B0
0x180006c79  mov     rax, cs:qword_1800C30A8
0x180006c80  test    al, 3
0x180006c82  jz      loc_180006D88
0x180006c88  mov     rax, rcx
0x180006c8b  and     eax, 3
0x180006c8e  cmp     rax, rcx
0x180006c91  jnz     loc_180006D88
0x180006c97  mov     [rsp+2D0h+var_290], edi
0x180006c9b  lea     rax, [rsp+2D0h+var_290]
0x180006ca0  mov     [rbp+1D0h+var_1C0], rax
0x180006ca4  lea     rcx, BipTraceLoggingNullSid
0x180006cab  mov     [rsp+2D0h+var_28C], ebx
0x180006caf  lea     rax, [rsp+2D0h+var_28C]
0x180006cb4  mov     [rbp+1D0h+var_1D0], rax
0x180006cb8  lea     rdx, [rsp+2D0h+EventDescriptor]; EventDescriptor
0x180006cbd  mov     [rsp+2D0h+var_288], esi
0x180006cc1  test    r14, r14
0x180006cc4  mov     [rbp+1D0h+var_1B8], 4
0x180006ccc  cmovnz  rcx, r14
0x180006cd0  mov     [rbp+1D0h+var_1C8], 4
0x180006cd8  mov     dword ptr [rsp+2D0h+EventDescriptor.Id], 0B000000h
0x180006ce0  xor     r9d, r9d; RelatedActivityId
0x180006ce3  mov     [rsp+2D0h+EventDescriptor.Keyword], 3
0x180006cec  xor     r8d, r8d; ActivityId
0x180006cef  movzx   eax, byte ptr [rcx+1]
0x180006cf3  mov     [rbp+1D0h+var_1E0], rcx
0x180006cf7  lea     rcx, _TraceLoggingMetadata
0x180006cfe  mov     [rbp+1D0h+var_1D4], r15d
0x180006d02  mov     [rbp+1D0h+var_1E8], 4
0x180006d0a  lea     eax, ds:8[rax*4]
0x180006d11  mov     [rbp+1D0h+var_1D8], eax
0x180006d14  lea     rax, [rsp+2D0h+var_288]
0x180006d19  mov     [rbp+1D0h+var_1F0], rax
0x180006d1d  movzx   eax, cs:word_1800AD324
0x180006d24  mov     dword ptr [rsp+2D0h+EventDescriptor.Level], eax
0x180006d28  mov     rax, cs:off_1800C30A0
0x180006d2f  mov     [rbp+1D0h+var_210.Ptr], rax
0x180006d33  movzx   eax, word ptr [rax]
0x180006d36  mov     [rbp+1D0h+var_210.Size], eax
0x180006d39  lea     rax, word_1800AD32E
0x180006d40  mov     [rbp+1D0h+var_200], rax
0x180006d44  lea     rax, _TraceLoggingMetadataEnd
0x180006d4b  sub     eax, ecx
0x180006d4d  mov     dword ptr [rbp+1D0h+var_210.0Ch], 2
0x180006d54  mov     [rbp+1D0h+var_1F8], 5Eh ; '^'
0x180006d5b  mov     [rbp+1D0h+var_1F4], 1
0x180006d62  mov     [rsp+2D0h+var_284], eax
0x180006d66  mov     eax, [rsp+2D0h+var_284]
0x180006d6a  mov     rcx, cs:RegHandle; RegHandle
0x180006d71  lea     rax, [rbp+1D0h+var_210]
0x180006d75  mov     [rsp+2D0h+UserData], rax; UserData
0x180006d7a  mov     [rsp+2D0h+UserDataCount], 6; UserDataCount
0x180006d82  call    cs:__imp_EventWriteTransfer
0x180006d88  mov     eax, ebx
0x180006d8a  mov     rcx, [rbp+1D0h+var_30]
0x180006d91  xor     rcx, rsp; StackCookie
0x180006d94  call    __security_check_cookie
0x180006d99  mov     rbx, [rsp+2D0h+arg_18]
0x180006da1  add     rsp, 2B0h
0x180006da8  pop     r15
0x180006daa  pop     r14
0x180006dac  pop     rdi
0x180006dad  pop     rsi
0x180006dae  pop     rbp
0x180006daf  retn
```
