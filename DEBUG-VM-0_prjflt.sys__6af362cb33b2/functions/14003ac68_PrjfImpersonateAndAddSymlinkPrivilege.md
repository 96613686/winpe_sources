# PrjfImpersonateAndAddSymlinkPrivilege

- ea: `0x14003ac68`
- end: `0x14003b379`
- name: `PrjfImpersonateAndAddSymlinkPrivilege`
- size: `1809`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x140038f1c`

## callees

- `0x14000b1d0`
- `0x14000ba20`
- `0x14000d128`
- `0x14003ac68`
- `0x14003e548`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14003b2ae`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003b2ae`
- `ntoskrnl!ZwAdjustPrivilegesToken` at `0x14003b192`
- `ntoskrnl!ZwAdjustPrivilegesToken` at `0x14003b192`
- `ntoskrnl!ZwDuplicateToken` at `0x14003b07c`
- `ntoskrnl!ZwDuplicateToken` at `0x14003b07c`
- `ntoskrnl!ZwQuerySecurityObject` at `0x14003ae7b`
- `ntoskrnl!ZwQuerySecurityObject` at `0x14003af9d`
- `ntoskrnl!ZwQuerySecurityObject` at `0x14003ae7b`
- `ntoskrnl!ZwQuerySecurityObject` at `0x14003af9d`
- `ntoskrnl!ZwOpenProcessTokenEx` at `0x14003adf9`
- `ntoskrnl!ZwOpenProcessTokenEx` at `0x14003adf9`
- `ntoskrnl!ZwClose` at `0x14003ad72`
- `ntoskrnl!ZwClose` at `0x14003b2c6`
- `ntoskrnl!ZwClose` at `0x14003b34c`
- `ntoskrnl!ZwClose` at `0x14003ad72`
- `ntoskrnl!ZwClose` at `0x14003b2c6`
- `ntoskrnl!ZwClose` at `0x14003b34c`
- `ntoskrnl!ZwOpenThreadTokenEx` at `0x14003ad57`
- `ntoskrnl!ZwOpenThreadTokenEx` at `0x14003ad57`
- `ntoskrnl!ZwSetInformationThread` at `0x14003b0f5`
- `ntoskrnl!ZwSetInformationThread` at `0x14003b21d`
- `ntoskrnl!ZwSetInformationThread` at `0x14003b0f5`
- `ntoskrnl!ZwSetInformationThread` at `0x14003b21d`
- `ntoskrnl!ExAllocatePool2` at `0x14003af16`
- `ntoskrnl!ExAllocatePool2` at `0x14003af16`
- `ntoskrnl!IoGetCurrentProcess` at `0x14003acbf`
- `ntoskrnl!IoGetCurrentProcess` at `0x14003acbf`

## pseudocode

```c
__int64 __fastcall PrjfImpersonateAndAddSymlinkPrivilege(__int64 a1)
{
  struct _KPROCESS *v1; // rbx
  __int64 v3; // rcx
  int v4; // edx
  NTSTATUS v5; // ebx
  int v6; // r8d
  char v7; // r10
  __int64 v8; // rcx
  int v9; // edx
  int v10; // r8d
  HANDLE v11; // rdi
  int v12; // edx
  int v13; // r8d
  int v14; // edx
  void *Pool2; // rsi
  int v16; // r8d
  int v17; // edx
  int v18; // r8d
  int v19; // edx
  int v20; // r8d
  int v21; // edx
  int v22; // r8d
  __int64 v23; // rdx
  __int64 v24; // r8
  __int16 v26; // [rsp+30h] [rbp-99h]
  char v27; // [rsp+48h] [rbp-81h]
  char v28; // [rsp+50h] [rbp-79h]
  ULONG LengthNeeded; // [rsp+60h] [rbp-69h] BYREF
  void *ThreadInformation; // [rsp+68h] [rbp-61h] BYREF
  HANDLE Handle; // [rsp+70h] [rbp-59h] BYREF
  HANDLE ExistingTokenHandle; // [rsp+78h] [rbp-51h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+80h] [rbp-49h] BYREF
  __int64 v34; // [rsp+B0h] [rbp-19h] BYREF
  int v35; // [rsp+B8h] [rbp-11h]
  _TOKEN_PRIVILEGES NewState; // [rsp+C0h] [rbp-9h] BYREF
  __int64 v37; // [rsp+D0h] [rbp+7h]
  int v38; // [rsp+D8h] [rbp+Fh]

  v1 = *(struct _KPROCESS **)(a1 + 32);
  Handle = 0;
  ExistingTokenHandle = 0;
  ThreadInformation = 0;
  LengthNeeded = 0;
  v34 = 0;
  v35 = 0;
  memset(&ObjectAttributes, 0, 44);
  if ( IoGetCurrentProcess() != v1 )
  {
    MicrosoftTelemetryAssertTriggeredNoArgsKM(v3);
    v4 = -1073741555;
    v5 = -1073741555;
    LOBYTE(v6) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    v7 = xmmword_14001A3D0 & 0x20;
    if ( (xmmword_14001A3D0 & 0x20) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v28 = 13;
      v27 = 103;
      v26 = 203;
LABEL_5:
      LOBYTE(v4) = v7;
LABEL_54:
      WPP_RECORDER_AND_TRACE_SF_sDL(
        517,
        v4,
        v6,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        2,
        5,
        v26,
        (__int64)WPP_f518d8db80f83e9c1a62003295e898de_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\utils.c",
        v27,
        v28);
      goto LABEL_55;
    }
    goto LABEL_55;
  }
  v5 = ZwOpenThreadTokenEx((HANDLE)0xFFFFFFFFFFFFFFFELL, 0x20002u, 0, 0x200u, &Handle);
  if ( v5 < 0 )
  {
    if ( v5 != -1073741700 )
    {
      LOBYTE(v6) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      LOBYTE(v4) = xmmword_14001A3D0 & 0x20;
      if ( (xmmword_14001A3D0 & 0x20) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v28 = v5;
        v27 = -105;
        v26 = 206;
        goto LABEL_54;
      }
      goto LABEL_55;
    }
    v5 = ZwOpenProcessTokenEx((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0x20002u, 0x200u, &ExistingTokenHandle);
    if ( v5 < 0 )
    {
      if ( (xmmword_14001A3D0 & 0x20) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v9) = xmmword_14001A3D0 & 0x20;
        LOBYTE(v10) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sDL(
          517,
          v9,
          v10,
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          2,
          5,
          205,
          (__int64)WPP_f518d8db80f83e9c1a62003295e898de_Traceguids,
          (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\utils.c",
          143,
          v5);
      }
      goto LABEL_55;
    }
    v11 = ExistingTokenHandle;
    v5 = ZwQuerySecurityObject(ExistingTokenHandle, 4u, 0, 0, &LengthNeeded);
    if ( v5 != -1073741789 )
    {
      if ( (xmmword_14001A3D0 & 0x20) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v12) = xmmword_14001A3D0 & 0x20;
        LOBYTE(v13) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sDL(
          517,
          v12,
          v13,
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          2,
          5,
          207,
          (__int64)WPP_f518d8db80f83e9c1a62003295e898de_Traceguids,
          (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\utils.c",
          167,
          v5);
      }
      goto LABEL_49;
    }
    Pool2 = (void *)ExAllocatePool2(256, LengthNeeded, 1634749008);
    if ( !Pool2 )
    {
      v5 = -1073741670;
      if ( (xmmword_14001A3D0 & 0x20) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v14) = xmmword_14001A3D0 & 0x20;
        LOBYTE(v16) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sDL(
          517,
          v14,
          v16,
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          2,
          5,
          208,
          (__int64)WPP_f518d8db80f83e9c1a62003295e898de_Traceguids,
          (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\utils.c",
          178,
          154);
      }
      goto LABEL_49;
    }
    v5 = ZwQuerySecurityObject(v11, 4u, Pool2, LengthNeeded, &LengthNeeded);
    if ( v5 < 0 )
    {
      if ( (xmmword_14001A3D0 & 0x20) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v17) = xmmword_14001A3D0 & 0x20;
        LOBYTE(v18) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sDL(
          517,
          v17,
          v18,
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          2,
          5,
          209,
          (__int64)WPP_f518d8db80f83e9c1a62003295e898de_Traceguids,
          (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\utils.c",
          190,
          v5);
      }
      goto LABEL_48;
    }
    ObjectAttributes.Length = 48;
    ObjectAttributes.SecurityQualityOfService = &v34;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 512;
    ObjectAttributes.ObjectName = 0;
    ObjectAttributes.SecurityDescriptor = Pool2;
    v34 = 0x20000000CLL;
    LOWORD(v35) = 1;
    v5 = ZwDuplicateToken(v11, 0x2Cu, &ObjectAttributes, 0, TokenImpersonation, &ThreadInformation);
    if ( v5 < 0 )
    {
      if ( (xmmword_14001A3D0 & 0x20) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v19) = xmmword_14001A3D0 & 0x20;
        LOBYTE(v20) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sDL(
          517,
          v19,
          v20,
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          2,
          5,
          210,
          (__int64)WPP_f518d8db80f83e9c1a62003295e898de_Traceguids,
          (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\utils.c",
          216,
          v5);
      }
      goto LABEL_48;
    }
    v5 = ZwSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &ThreadInformation, 8u);
    if ( v5 < 0 )
    {
      if ( (xmmword_14001A3D0 & 0x20) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v21) = xmmword_14001A3D0 & 0x20;
        LOBYTE(v22) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sDL(
          517,
          v21,
          v22,
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          2,
          5,
          211,
          (__int64)WPP_f518d8db80f83e9c1a62003295e898de_Traceguids,
          (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\utils.c",
          231,
          v5);
      }
      goto LABEL_48;
    }
    v37 = 0;
    v38 = 0;
    NewState.PrivilegeCount = 1;
    NewState.Privileges[0].Luid = (LUID)35LL;
    NewState.Privileges[0].Attributes = 2;
    v5 = ZwAdjustPrivilegesToken(ThreadInformation, 0, &NewState, 0, 0, 0);
    if ( v5 >= 0 )
    {
      if ( v5 == 262 )
      {
        v5 = -1073741727;
      }
      else
      {
        v5 = ZwSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &ThreadInformation, 8u);
        if ( v5 >= 0 )
        {
LABEL_48:
          ExFreePoolWithTag(Pool2, 0x61704A50u);
LABEL_49:
          if ( v11 )
            ZwClose(v11);
          goto LABEL_55;
        }
        LOBYTE(v24) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        LOBYTE(v23) = xmmword_14001A3D0 & 0x20;
        if ( (xmmword_14001A3D0 & 0x20) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_AND_TRACE_SF_sDL(
            517,
            v23,
            v24,
            *((_QWORD *)WPP_GLOBAL_Control + 8),
            2,
            5,
            213,
            (__int64)WPP_f518d8db80f83e9c1a62003295e898de_Traceguids,
            (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\utils.c",
            26,
            v5);
      }
    }
    else
    {
      LOBYTE(v24) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      LOBYTE(v23) = xmmword_14001A3D0 & 0x20;
      if ( (xmmword_14001A3D0 & 0x20) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_AND_TRACE_SF_sDL(
          517,
          v23,
          v24,
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          2,
          5,
          212,
          (__int64)WPP_f518d8db80f83e9c1a62003295e898de_Traceguids,
          (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\utils.c",
          1,
          v5);
    }
    PrjfStopImpersonating(a1, v23, v24);
    goto LABEL_48;
  }
  MicrosoftTelemetryAssertTriggeredNoArgsKM(v8);
  ZwClose(Handle);
  v4 = -1073741555;
  v5 = -1073741555;
  LOBYTE(v6) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  v7 = xmmword_14001A3D0 & 0x20;
  if ( (xmmword_14001A3D0 & 0x20) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v28 = 13;
    v27 = 126;
    v26 = 204;
    goto LABEL_5;
  }
LABEL_55:
  if ( ThreadInformation )
    ZwClose(ThreadInformation);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x14003ac68  push    rbp
0x14003ac6a  push    rbx
0x14003ac6b  push    rsi
0x14003ac6c  push    rdi
0x14003ac6d  push    r13
0x14003ac6f  push    r14
0x14003ac71  push    r15
0x14003ac73  lea     rbp, [rsp-27h]
0x14003ac78  sub     rsp, 0F0h
0x14003ac7f  mov     rax, cs:__security_cookie
0x14003ac86  xor     rax, rsp
0x14003ac89  mov     [rbp+57h+var_40], rax
0x14003ac8d  mov     rbx, [rcx+20h]
0x14003ac91  xorps   xmm0, xmm0
0x14003ac94  xor     r15d, r15d
0x14003ac97  xor     eax, eax
0x14003ac99  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x14003ac9d  mov     r14, rcx
0x14003aca0  mov     [rbp+57h+Handle], r15
0x14003aca4  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x14003aca8  mov     [rbp+57h+ExistingTokenHandle], r15
0x14003acac  mov     [rbp+57h+ThreadInformation], r15
0x14003acb0  mov     [rbp+57h+LengthNeeded], r15d
0x14003acb4  mov     [rbp+57h+var_70], rax
0x14003acb8  mov     [rbp+57h+var_68], eax
0x14003acbb  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x14003acbf  call    cs:__imp_IoGetCurrentProcess
0x14003acc6  nop     dword ptr [rax+rax+00h]
0x14003accb  cmp     rax, rbx
0x14003acce  jz      short loc_14003AD37
0x14003acd0  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14003acd5  mov     edx, 0C000010Dh
0x14003acda  mov     ebx, edx
0x14003acdc  mov     r10b, byte ptr cs:xmmword_14001A3D0
0x14003ace3  lea     rax, WPP_RECORDER_INITIALIZED
0x14003acea  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14003acf1  setnz   r8b
0x14003acf5  and     r10b, 20h
0x14003acf9  jnz     short loc_14003AD04
0x14003acfb  test    r8b, r8b
0x14003acfe  jz      loc_14003B343
0x14003ad04  mov     dword ptr [rsp+120h+var_D0], edx
0x14003ad08  lea     rax, aOnecoreBaseFsG_2; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14003ad0f  mov     dword ptr [rsp+120h+var_D8], 2267h
0x14003ad17  mov     [rsp+120h+var_E0], rax
0x14003ad1c  lea     rax, WPP_f518d8db80f83e9c1a62003295e898de_Traceguids
0x14003ad23  mov     [rsp+120h+var_E8], rax
0x14003ad28  mov     [rsp+120h+var_F0], 0CBh
0x14003ad2f  mov     dl, r10b
0x14003ad32  jmp     loc_14003B321
0x14003ad37  xor     r8d, r8d; OpenAsSelf
0x14003ad3a  lea     rax, [rbp+57h+Handle]
0x14003ad3e  mov     edi, 20002h
0x14003ad43  mov     [rsp+120h+TokenHandle], rax; TokenHandle
0x14003ad48  mov     r9d, 200h; HandleAttributes
0x14003ad4e  mov     edx, edi; DesiredAccess
0x14003ad50  lea     r13, [r8-2]
0x14003ad54  mov     rcx, r13; ThreadHandle
0x14003ad57  call    cs:__imp_ZwOpenThreadTokenEx
0x14003ad5e  nop     dword ptr [rax+rax+00h]
0x14003ad63  mov     ebx, eax
0x14003ad65  test    eax, eax
0x14003ad67  js      short loc_14003ADDD
0x14003ad69  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14003ad6e  mov     rcx, [rbp+57h+Handle]; Handle
0x14003ad72  call    cs:__imp_ZwClose
0x14003ad79  nop     dword ptr [rax+rax+00h]
0x14003ad7e  mov     edx, 0C000010Dh
0x14003ad83  mov     ebx, edx
0x14003ad85  mov     r10b, byte ptr cs:xmmword_14001A3D0
0x14003ad8c  lea     rax, WPP_RECORDER_INITIALIZED
0x14003ad93  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14003ad9a  setnz   r8b
0x14003ad9e  and     r10b, 20h
0x14003ada2  jnz     short loc_14003ADAD
0x14003ada4  test    r8b, r8b
0x14003ada7  jz      loc_14003B343
0x14003adad  mov     dword ptr [rsp+120h+var_D0], edx
0x14003adb1  lea     rax, aOnecoreBaseFsG_2; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14003adb8  mov     dword ptr [rsp+120h+var_D8], 227Eh
0x14003adc0  mov     [rsp+120h+var_E0], rax
0x14003adc5  lea     rax, WPP_f518d8db80f83e9c1a62003295e898de_Traceguids
0x14003adcc  mov     [rsp+120h+var_E8], rax
0x14003add1  mov     [rsp+120h+var_F0], 0CCh
0x14003add8  jmp     loc_14003AD2F
0x14003addd  cmp     ebx, 0C000007Ch
0x14003ade3  jnz     loc_14003B2D4
0x14003ade9  lea     r9, [rbp+57h+ExistingTokenHandle]; TokenHandle
0x14003aded  mov     r8d, 200h; HandleAttributes
0x14003adf3  mov     edx, edi; DesiredAccess
0x14003adf5  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x14003adf9  call    cs:__imp_ZwOpenProcessTokenEx
0x14003ae00  nop     dword ptr [rax+rax+00h]
0x14003ae05  mov     ebx, eax
0x14003ae07  test    eax, eax
0x14003ae09  jns     short loc_14003AE61
0x14003ae0b  mov     dl, byte ptr cs:xmmword_14001A3D0
0x14003ae11  lea     rax, WPP_RECORDER_INITIALIZED
0x14003ae18  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14003ae1f  setnz   r8b
0x14003ae23  and     dl, 20h
0x14003ae26  jnz     short loc_14003AE31
0x14003ae28  test    r8b, r8b
0x14003ae2b  jz      loc_14003B343
0x14003ae31  mov     dword ptr [rsp+120h+var_D0], ebx
0x14003ae35  lea     rax, aOnecoreBaseFsG_2; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14003ae3c  mov     dword ptr [rsp+120h+var_D8], 228Fh
0x14003ae44  mov     [rsp+120h+var_E0], rax
0x14003ae49  lea     rax, WPP_f518d8db80f83e9c1a62003295e898de_Traceguids
0x14003ae50  mov     [rsp+120h+var_E8], rax
0x14003ae55  mov     [rsp+120h+var_F0], 0CDh
0x14003ae5c  jmp     loc_14003B321
0x14003ae61  mov     rdi, [rbp+57h+ExistingTokenHandle]
0x14003ae65  lea     rax, [rbp+57h+LengthNeeded]
0x14003ae69  xor     r9d, r9d; Length
0x14003ae6c  mov     [rsp+120h+TokenHandle], rax; LengthNeeded
0x14003ae71  xor     r8d, r8d; SecurityDescriptor
0x14003ae74  mov     rcx, rdi; Handle
0x14003ae77  lea     edx, [r9+4]; SecurityInformation
0x14003ae7b  call    cs:__imp_ZwQuerySecurityObject
0x14003ae82  nop     dword ptr [rax+rax+00h]
0x14003ae87  mov     ebx, eax
0x14003ae89  cmp     eax, 0C0000023h
0x14003ae8e  jz      short loc_14003AF08
0x14003ae90  mov     dl, byte ptr cs:xmmword_14001A3D0
0x14003ae96  lea     rax, WPP_RECORDER_INITIALIZED
0x14003ae9d  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14003aea4  setnz   r8b
0x14003aea8  and     dl, 20h
0x14003aeab  jnz     short loc_14003AEB6
0x14003aead  test    r8b, r8b
0x14003aeb0  jz      loc_14003B2BA
0x14003aeb6  mov     dword ptr [rsp+120h+var_D0], ebx
0x14003aeba  lea     rax, aOnecoreBaseFsG_2; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14003aec1  mov     dword ptr [rsp+120h+var_D8], 22A7h
0x14003aec9  mov     [rsp+120h+var_E0], rax
0x14003aece  lea     rax, WPP_f518d8db80f83e9c1a62003295e898de_Traceguids
0x14003aed5  mov     [rsp+120h+var_E8], rax
0x14003aeda  mov     [rsp+120h+var_F0], 0CFh
0x14003aee1  mov     r9, cs:WPP_GLOBAL_Control
0x14003aee8  mov     ecx, 205h
0x14003aeed  mov     dword ptr [rsp+120h+NewTokenHandle], 5
0x14003aef5  mov     byte ptr [rsp+120h+TokenHandle], 2
0x14003aefa  mov     r9, [r9+40h]
0x14003aefe  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x14003af03  jmp     loc_14003B2BA
0x14003af08  mov     edx, [rbp+57h+LengthNeeded]
0x14003af0b  mov     ecx, 100h
0x14003af10  mov     r8d, 61704A50h
0x14003af16  call    cs:__imp_ExAllocatePool2
0x14003af1d  nop     dword ptr [rax+rax+00h]
0x14003af22  mov     rsi, rax
0x14003af25  test    rax, rax
0x14003af28  jnz     short loc_14003AF85
0x14003af2a  mov     ebx, 0C000009Ah
0x14003af2f  mov     dl, byte ptr cs:xmmword_14001A3D0
0x14003af35  lea     rax, WPP_RECORDER_INITIALIZED
0x14003af3c  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14003af43  setnz   r8b
0x14003af47  and     dl, 20h
0x14003af4a  jnz     short loc_14003AF55
0x14003af4c  test    r8b, r8b
0x14003af4f  jz      loc_14003B2BA
0x14003af55  mov     dword ptr [rsp+120h+var_D0], ebx
0x14003af59  lea     rax, aOnecoreBaseFsG_2; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14003af60  mov     dword ptr [rsp+120h+var_D8], 22B2h
0x14003af68  mov     [rsp+120h+var_E0], rax
0x14003af6d  lea     rax, WPP_f518d8db80f83e9c1a62003295e898de_Traceguids
0x14003af74  mov     [rsp+120h+var_E8], rax
0x14003af79  mov     [rsp+120h+var_F0], 0D0h
0x14003af80  jmp     loc_14003AEE1
0x14003af85  mov     r9d, [rbp+57h+LengthNeeded]; Length
0x14003af89  lea     rax, [rbp+57h+LengthNeeded]
0x14003af8d  mov     r8, rsi; SecurityDescriptor
0x14003af90  mov     [rsp+120h+TokenHandle], rax; LengthNeeded
0x14003af95  mov     edx, 4; SecurityInformation
0x14003af9a  mov     rcx, rdi; Handle
0x14003af9d  call    cs:__imp_ZwQuerySecurityObject
0x14003afa4  nop     dword ptr [rax+rax+00h]
0x14003afa9  mov     ebx, eax
0x14003afab  test    eax, eax
0x14003afad  jns     short loc_14003B027
0x14003afaf  mov     dl, byte ptr cs:xmmword_14001A3D0
0x14003afb5  lea     rax, WPP_RECORDER_INITIALIZED
0x14003afbc  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14003afc3  setnz   r8b
0x14003afc7  and     dl, 20h
0x14003afca  jnz     short loc_14003AFD5
0x14003afcc  test    r8b, r8b
0x14003afcf  jz      loc_14003B2A6
0x14003afd5  mov     dword ptr [rsp+120h+var_D0], ebx
0x14003afd9  lea     rax, aOnecoreBaseFsG_2; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14003afe0  mov     dword ptr [rsp+120h+var_D8], 22BEh
0x14003afe8  mov     [rsp+120h+var_E0], rax
0x14003afed  lea     rax, WPP_f518d8db80f83e9c1a62003295e898de_Traceguids
0x14003aff4  mov     [rsp+120h+var_E8], rax
0x14003aff9  mov     [rsp+120h+var_F0], 0D1h
0x14003b000  mov     r9, cs:WPP_GLOBAL_Control
0x14003b007  mov     ecx, 205h
0x14003b00c  mov     dword ptr [rsp+120h+NewTokenHandle], 5
0x14003b014  mov     byte ptr [rsp+120h+TokenHandle], 2
0x14003b019  mov     r9, [r9+40h]
0x14003b01d  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x14003b022  jmp     loc_14003B2A6
0x14003b027  lea     rax, [rbp+57h+var_70]
0x14003b02b  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x14003b032  xor     r9d, r9d; EffectiveOnly
0x14003b035  mov     [rbp+57h+ObjectAttributes.SecurityQualityOfService], rax
0x14003b039  lea     rax, [rbp+57h+ThreadInformation]
0x14003b03d  mov     [rbp+57h+ObjectAttributes.RootDirectory], r15
0x14003b041  mov     [rsp+120h+NewTokenHandle], rax; NewTokenHandle
0x14003b046  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14003b04a  mov     rcx, rdi; ExistingTokenHandle
0x14003b04d  mov     dword ptr [rsp+120h+TokenHandle], 2; TokenType
0x14003b055  lea     edx, [r9+2Ch]; DesiredAccess
0x14003b059  mov     [rbp+57h+ObjectAttributes.Attributes], 200h
0x14003b060  mov     [rbp+57h+ObjectAttributes.ObjectName], r15
0x14003b064  mov     [rbp+57h+ObjectAttributes.SecurityDescriptor], rsi
0x14003b068  mov     dword ptr [rbp+57h+var_70], 0Ch
0x14003b06f  mov     dword ptr [rbp+57h+var_70+4], 2
0x14003b076  mov     word ptr [rbp+57h+var_68], 1
0x14003b07c  call    cs:__imp_ZwDuplicateToken
0x14003b083  nop     dword ptr [rax+rax+00h]
0x14003b088  mov     ebx, eax
0x14003b08a  test    eax, eax
0x14003b08c  jns     short loc_14003B0E4
0x14003b08e  mov     dl, byte ptr cs:xmmword_14001A3D0
0x14003b094  lea     rax, WPP_RECORDER_INITIALIZED
0x14003b09b  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14003b0a2  setnz   r8b
0x14003b0a6  and     dl, 20h
0x14003b0a9  jnz     short loc_14003B0B4
0x14003b0ab  test    r8b, r8b
0x14003b0ae  jz      loc_14003B2A6
0x14003b0b4  mov     dword ptr [rsp+120h+var_D0], ebx
0x14003b0b8  lea     rax, aOnecoreBaseFsG_2; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14003b0bf  mov     dword ptr [rsp+120h+var_D8], 22D8h
0x14003b0c7  mov     [rsp+120h+var_E0], rax
0x14003b0cc  lea     rax, WPP_f518d8db80f83e9c1a62003295e898de_Traceguids
0x14003b0d3  mov     [rsp+120h+var_E8], rax
0x14003b0d8  mov     [rsp+120h+var_F0], 0D2h
0x14003b0df  jmp     loc_14003B000
0x14003b0e4  mov     r9d, 8; ThreadInformationLength
0x14003b0ea  lea     r8, [rbp+57h+ThreadInformation]; ThreadInformation
0x14003b0ee  mov     rcx, r13; ThreadHandle
0x14003b0f1  lea     edx, [r9-3]; ThreadInformationClass
0x14003b0f5  call    cs:__imp_ZwSetInformationThread
0x14003b0fc  nop     dword ptr [rax+rax+00h]
0x14003b101  mov     ebx, eax
0x14003b103  test    eax, eax
0x14003b105  jns     short loc_14003B15D
0x14003b107  mov     dl, byte ptr cs:xmmword_14001A3D0
0x14003b10d  lea     rax, WPP_RECORDER_INITIALIZED
0x14003b114  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14003b11b  setnz   r8b
0x14003b11f  and     dl, 20h
0x14003b122  jnz     short loc_14003B12D
0x14003b124  test    r8b, r8b
0x14003b127  jz      loc_14003B2A6
0x14003b12d  mov     dword ptr [rsp+120h+var_D0], ebx
0x14003b131  lea     rax, aOnecoreBaseFsG_2; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14003b138  mov     dword ptr [rsp+120h+var_D8], 22E7h
0x14003b140  mov     [rsp+120h+var_E0], rax
0x14003b145  lea     rax, WPP_f518d8db80f83e9c1a62003295e898de_Traceguids
0x14003b14c  mov     [rsp+120h+var_E8], rax
0x14003b151  mov     [rsp+120h+var_F0], 0D3h
0x14003b158  jmp     loc_14003B000
0x14003b15d  mov     rcx, [rbp+57h+ThreadInformation]; TokenHandle
0x14003b161  lea     r8, [rbp+57h+NewState]; NewState
0x14003b165  mov     [rsp+120h+NewTokenHandle], r15; ReturnLength
0x14003b16a  xor     r9d, r9d; BufferLength
0x14003b16d  xor     edx, edx; DisableAllPrivileges
0x14003b16f  mov     [rsp+120h+TokenHandle], r15; PreviousState
0x14003b174  mov     [rbp+57h+var_50], r15
0x14003b178  mov     [rbp+57h+var_48], r15d
0x14003b17c  mov     [rbp+57h+NewState.PrivilegeCount], 1
0x14003b183  mov     qword ptr [rbp+57h+NewState.Privileges.Luid.LowPart], 23h ; '#'
0x14003b18b  mov     [rbp+57h+NewState.Privileges.Attributes], 2
0x14003b192  call    cs:__imp_ZwAdjustPrivilegesToken
0x14003b199  nop     dword ptr [rax+rax+00h]
0x14003b19e  mov     ebx, eax
0x14003b1a0  test    eax, eax
0x14003b1a2  jns     short loc_14003B1FA
0x14003b1a4  mov     dl, byte ptr cs:xmmword_14001A3D0
0x14003b1aa  lea     rax, WPP_RECORDER_INITIALIZED
0x14003b1b1  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14003b1b8  setnz   r8b
0x14003b1bc  and     dl, 20h
0x14003b1bf  jnz     short loc_14003B1CA
0x14003b1c1  test    r8b, r8b
0x14003b1c4  jz      loc_14003B29E
0x14003b1ca  mov     dword ptr [rsp+120h+var_D0], ebx
0x14003b1ce  lea     rax, aOnecoreBaseFsG_2; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14003b1d5  mov     dword ptr [rsp+120h+var_D8], 2301h
0x14003b1dd  mov     [rsp+120h+var_E0], rax
0x14003b1e2  lea     rax, WPP_f518d8db80f83e9c1a62003295e898de_Traceguids
0x14003b1e9  mov     [rsp+120h+var_E8], rax
0x14003b1ee  mov     [rsp+120h+var_F0], 0D4h
0x14003b1f5  jmp     loc_14003B27C
0x14003b1fa  cmp     ebx, 106h
  ... truncated ...
```
