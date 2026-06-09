# JScriptLib::CScriptReader::IsIntegrityLevelLow(void)

- ea: `0x18015ee98`
- end: `0x18015f17e`
- name: `?IsIntegrityLevelLow@CScriptReader@JScriptLib@@AEAAHXZ`
- size: `742`
- prototype: `__int64 __fastcall(JScriptLib::CScriptReader *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18015f184`

## callees

- `0x180003400`
- `0x180004558`
- `0x1800197b4`
- `0x180033598`
- `0x18015ee98`

## import_xrefs

- `KERNEL32!GetCurrentThread` at `0x18015eece`
- `KERNEL32!GetCurrentThread` at `0x18015ef3f`
- `KERNEL32!GetCurrentThread` at `0x18015eece`
- `KERNEL32!GetCurrentThread` at `0x18015ef3f`
- `KERNEL32!GetCurrentProcess` at `0x18015efc9`
- `KERNEL32!GetCurrentProcess` at `0x18015efc9`
- `KERNEL32!CloseHandle` at `0x18015f151`
- `KERNEL32!CloseHandle` at `0x18015f151`
- `KERNEL32!GetLastError` at `0x18015ef0f`
- `KERNEL32!GetLastError` at `0x18015ef97`
- `KERNEL32!GetLastError` at `0x18015f00d`
- `KERNEL32!GetLastError` at `0x18015f0a7`
- `KERNEL32!GetLastError` at `0x18015ef0f`
- `KERNEL32!GetLastError` at `0x18015ef97`
- `KERNEL32!GetLastError` at `0x18015f00d`
- `KERNEL32!GetLastError` at `0x18015f0a7`
- `ADVAPI32!GetTokenInformation` at `0x18015f097`
- `ADVAPI32!GetTokenInformation` at `0x18015f097`
- `ADVAPI32!OpenProcessToken` at `0x18015efe1`
- `ADVAPI32!OpenProcessToken` at `0x18015efe1`
- `ADVAPI32!OpenThreadToken` at `0x18015eeed`
- `ADVAPI32!OpenThreadToken` at `0x18015ef57`
- `ADVAPI32!OpenThreadToken` at `0x18015eeed`
- `ADVAPI32!OpenThreadToken` at `0x18015ef57`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18015f0ec`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18015f0ec`

## pseudocode

```c
__int64 __fastcall JScriptLib::CScriptReader::IsIntegrityLevelLow(JScriptLib::CScriptReader *this)
{
  unsigned int v1; // edi
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  HANDLE v4; // rax
  DWORD v5; // esi
  PrintConfig::CPageImageableSize *v6; // rbx
  USHORT v7; // dx
  DWORD v8; // eax
  HANDLE CurrentProcess; // rax
  DWORD v10; // eax
  HANDLE v11; // rcx
  DWORD v12; // eax
  DWORD TokenInformationLength; // [rsp+30h] [rbp-59h] BYREF
  HANDLE TokenHandle; // [rsp+38h] [rbp-51h] BYREF
  PSID TokenInformation[12]; // [rsp+40h] [rbp-49h] BYREF

  TokenHandle = (HANDLE)-1LL;
  v1 = 0;
  TokenInformationLength = 88;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0xEu, 1, &TokenHandle) )
  {
    v5 = 0;
    goto LABEL_22;
  }
  LastError = GetLastError();
  if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 0xAu, &WPP_9e5a8fd5af7d3ff7a0d6c0aaa8413012_Traceguids, LastError);
  }
  v4 = GetCurrentThread();
  if ( OpenThreadToken(v4, 0xEu, 0, &TokenHandle) )
  {
    v5 = 0;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      v7 = 11;
LABEL_9:
      WPP_SF_(*((_QWORD *)v6 + 2), v7, &WPP_9e5a8fd5af7d3ff7a0d6c0aaa8413012_Traceguids);
LABEL_22:
      v6 = WPP_GLOBAL_Control;
    }
  }
  else
  {
    v8 = GetLastError();
    if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 0xCu, &WPP_9e5a8fd5af7d3ff7a0d6c0aaa8413012_Traceguids, v8);
    }
    CurrentProcess = GetCurrentProcess();
    if ( OpenProcessToken(CurrentProcess, 0x2000Au, &TokenHandle) )
    {
      v5 = 0;
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        v7 = 13;
        goto LABEL_9;
      }
    }
    else
    {
      v10 = GetLastError();
      v5 = v10;
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 0xEu, &WPP_9e5a8fd5af7d3ff7a0d6c0aaa8413012_Traceguids, v10);
        v6 = WPP_GLOBAL_Control;
      }
      v1 = 1;
    }
  }
  memset_0(TokenInformation, 0, 0x58u);
  if ( !v5 && !v1 )
  {
    v11 = TokenHandle;
    if ( TokenHandle == (HANDLE)-1LL )
      v11 = 0;
    if ( GetTokenInformation(
           v11,
           TokenIntegrityLevel,
           TokenInformation,
           TokenInformationLength,
           &TokenInformationLength) )
    {
      if ( !IsWellKnownSid(TokenInformation[0], WinLowLabelSid) )
      {
        v6 = WPP_GLOBAL_Control;
        goto LABEL_38;
      }
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
      {
        goto LABEL_32;
      }
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x10u, &WPP_9e5a8fd5af7d3ff7a0d6c0aaa8413012_Traceguids);
    }
    else
    {
      v12 = GetLastError();
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
        goto LABEL_32;
      }
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 0xFu, &WPP_9e5a8fd5af7d3ff7a0d6c0aaa8413012_Traceguids, v12);
    }
    v6 = WPP_GLOBAL_Control;
LABEL_32:
    v1 = 1;
  }
LABEL_38:
  if ( v6 != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)v6 + 2), 0x11u, &WPP_9e5a8fd5af7d3ff7a0d6c0aaa8413012_Traceguids, v1);
  if ( TokenHandle != (HANDLE)-1LL )
    CloseHandle(TokenHandle);
  return v1;
}

```

## disassembly

```asm
0x18015ee98  push    rbp
0x18015ee9a  push    rbx
0x18015ee9b  push    rsi
0x18015ee9c  push    rdi
0x18015ee9d  push    r12
0x18015ee9f  push    r14
0x18015eea1  push    r15
0x18015eea3  lea     rbp, [rsp-27h]
0x18015eea8  sub     rsp, 0B0h
0x18015eeaf  mov     rax, cs:__security_cookie
0x18015eeb6  xor     rax, rsp
0x18015eeb9  mov     [rbp+57h+var_40], rax
0x18015eebd  mov     [rbp+57h+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x18015eec5  xor     edi, edi
0x18015eec7  mov     [rbp+57h+TokenInformationLength], 58h ; 'X'
0x18015eece  call    cs:__imp_GetCurrentThread
0x18015eed5  nop     dword ptr [rax+rax+00h]
0x18015eeda  lea     r15d, [rdi+1]
0x18015eede  mov     rcx, rax; ThreadHandle
0x18015eee1  lea     ebx, [rdi+0Eh]
0x18015eee4  mov     r8d, r15d; OpenAsSelf
0x18015eee7  mov     edx, ebx; DesiredAccess
0x18015eee9  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x18015eeed  call    cs:__imp_OpenThreadToken
0x18015eef4  nop     dword ptr [rax+rax+00h]
0x18015eef9  lea     r14, WPP_GLOBAL_Control
0x18015ef00  lea     r12, WPP_9e5a8fd5af7d3ff7a0d6c0aaa8413012_Traceguids
0x18015ef07  test    eax, eax
0x18015ef09  jnz     loc_18015F04D
0x18015ef0f  call    cs:__imp_GetLastError
0x18015ef16  nop     dword ptr [rax+rax+00h]
0x18015ef1b  mov     rcx, cs:WPP_GLOBAL_Control
0x18015ef22  cmp     rcx, r14
0x18015ef25  jz      short loc_18015EF3F
0x18015ef27  test    [rcx+1Ch], r15b
0x18015ef2b  jz      short loc_18015EF3F
0x18015ef2d  mov     rcx, [rcx+10h]
0x18015ef31  lea     edx, [rdi+0Ah]
0x18015ef34  mov     r9d, eax
0x18015ef37  mov     r8, r12
0x18015ef3a  call    WPP_SF_d
0x18015ef3f  call    cs:__imp_GetCurrentThread
0x18015ef46  nop     dword ptr [rax+rax+00h]
0x18015ef4b  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x18015ef4f  xor     r8d, r8d; OpenAsSelf
0x18015ef52  mov     rcx, rax; ThreadHandle
0x18015ef55  mov     edx, ebx; DesiredAccess
0x18015ef57  call    cs:__imp_OpenThreadToken
0x18015ef5e  nop     dword ptr [rax+rax+00h]
0x18015ef63  test    eax, eax
0x18015ef65  jz      short loc_18015EF97
0x18015ef67  xor     esi, esi
0x18015ef69  mov     rbx, cs:WPP_GLOBAL_Control
0x18015ef70  cmp     rbx, r14
0x18015ef73  jz      loc_18015F056
0x18015ef79  test    byte ptr [rbx+1Ch], 8
0x18015ef7d  jz      loc_18015F056
0x18015ef83  lea     edx, [rsi+0Bh]
0x18015ef86  mov     rcx, [rbx+10h]
0x18015ef8a  mov     r8, r12
0x18015ef8d  call    WPP_SF_
0x18015ef92  jmp     loc_18015F04F
0x18015ef97  call    cs:__imp_GetLastError
0x18015ef9e  nop     dword ptr [rax+rax+00h]
0x18015efa3  mov     rcx, cs:WPP_GLOBAL_Control
0x18015efaa  cmp     rcx, r14
0x18015efad  jz      short loc_18015EFC9
0x18015efaf  test    [rcx+1Ch], r15b
0x18015efb3  jz      short loc_18015EFC9
0x18015efb5  mov     rcx, [rcx+10h]
0x18015efb9  mov     edx, 0Ch
0x18015efbe  mov     r9d, eax
0x18015efc1  mov     r8, r12
0x18015efc4  call    WPP_SF_d
0x18015efc9  call    cs:__imp_GetCurrentProcess
0x18015efd0  nop     dword ptr [rax+rax+00h]
0x18015efd5  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x18015efd9  mov     edx, 2000Ah; DesiredAccess
0x18015efde  mov     rcx, rax; ProcessHandle
0x18015efe1  call    cs:__imp_OpenProcessToken
0x18015efe8  nop     dword ptr [rax+rax+00h]
0x18015efed  test    eax, eax
0x18015efef  jz      short loc_18015F00D
0x18015eff1  xor     esi, esi
0x18015eff3  mov     rbx, cs:WPP_GLOBAL_Control
0x18015effa  cmp     rbx, r14
0x18015effd  jz      short loc_18015F056
0x18015efff  test    byte ptr [rbx+1Ch], 8
0x18015f003  jz      short loc_18015F056
0x18015f005  lea     edx, [rsi+0Dh]
0x18015f008  jmp     loc_18015EF86
0x18015f00d  call    cs:__imp_GetLastError
0x18015f014  nop     dword ptr [rax+rax+00h]
0x18015f019  mov     esi, eax
0x18015f01b  mov     rbx, cs:WPP_GLOBAL_Control
0x18015f022  cmp     rbx, r14
0x18015f025  jz      short loc_18015F048
0x18015f027  test    [rbx+1Ch], r15b
0x18015f02b  jz      short loc_18015F048
0x18015f02d  mov     rcx, [rbx+10h]
0x18015f031  mov     edx, 0Eh
0x18015f036  mov     r9d, eax
0x18015f039  mov     r8, r12
0x18015f03c  call    WPP_SF_d
0x18015f041  mov     rbx, cs:WPP_GLOBAL_Control
0x18015f048  mov     edi, r15d
0x18015f04b  jmp     short loc_18015F056
0x18015f04d  xor     esi, esi
0x18015f04f  mov     rbx, cs:WPP_GLOBAL_Control
0x18015f056  xor     edx, edx; Val
0x18015f058  lea     rcx, [rbp+57h+TokenInformation]; void *
0x18015f05c  lea     r8d, [rdx+58h]; Size
0x18015f060  call    memset_0
0x18015f065  test    esi, esi
0x18015f067  jnz     loc_18015F128
0x18015f06d  test    edi, edi
0x18015f06f  jnz     loc_18015F128
0x18015f075  mov     rcx, [rbp+57h+TokenHandle]
0x18015f079  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x18015f07d  mov     r9d, [rbp+57h+TokenInformationLength]; TokenInformationLength
0x18015f081  lea     edx, [rsi+19h]; TokenInformationClass
0x18015f084  xor     eax, eax
0x18015f086  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18015f08a  cmovz   rcx, rax; TokenHandle
0x18015f08e  lea     rax, [rbp+57h+TokenInformationLength]
0x18015f092  mov     [rsp+0E0h+ReturnLength], rax; ReturnLength
0x18015f097  call    cs:__imp_GetTokenInformation
0x18015f09e  nop     dword ptr [rax+rax+00h]
0x18015f0a3  test    eax, eax
0x18015f0a5  jnz     short loc_18015F0E3
0x18015f0a7  call    cs:__imp_GetLastError
0x18015f0ae  nop     dword ptr [rax+rax+00h]
0x18015f0b3  mov     rbx, cs:WPP_GLOBAL_Control
0x18015f0ba  cmp     rbx, r14
0x18015f0bd  jz      short loc_18015F0DE
0x18015f0bf  test    [rbx+1Ch], r15b
0x18015f0c3  jz      short loc_18015F0DE
0x18015f0c5  mov     rcx, [rbx+10h]
0x18015f0c9  lea     edx, [rsi+0Fh]
0x18015f0cc  mov     r9d, eax
0x18015f0cf  mov     r8, r12
0x18015f0d2  call    WPP_SF_d
0x18015f0d7  mov     rbx, cs:WPP_GLOBAL_Control
0x18015f0de  mov     edi, r15d
0x18015f0e1  jmp     short loc_18015F128
0x18015f0e3  mov     rcx, [rbp+57h+TokenInformation]; pSid
0x18015f0e7  mov     edx, 42h ; 'B'; WellKnownSidType
0x18015f0ec  call    cs:__imp_IsWellKnownSid
0x18015f0f3  nop     dword ptr [rax+rax+00h]
0x18015f0f8  test    eax, eax
0x18015f0fa  jz      short loc_18015F121
0x18015f0fc  mov     rbx, cs:WPP_GLOBAL_Control
0x18015f103  cmp     rbx, r14
0x18015f106  jz      short loc_18015F0DE
0x18015f108  test    byte ptr [rbx+1Ch], 8
0x18015f10c  jz      short loc_18015F0DE
0x18015f10e  mov     rcx, [rbx+10h]
0x18015f112  mov     edx, 10h
0x18015f117  mov     r8, r12
0x18015f11a  call    WPP_SF_
0x18015f11f  jmp     short loc_18015F0D7
0x18015f121  mov     rbx, cs:WPP_GLOBAL_Control
0x18015f128  cmp     rbx, r14
0x18015f12b  jz      short loc_18015F147
0x18015f12d  test    byte ptr [rbx+1Ch], 8
0x18015f131  jz      short loc_18015F147
0x18015f133  mov     rcx, [rbx+10h]
0x18015f137  mov     edx, 11h
0x18015f13c  mov     r9d, edi
0x18015f13f  mov     r8, r12
0x18015f142  call    WPP_SF_d
0x18015f147  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x18015f14b  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18015f14f  jz      short loc_18015F15D
0x18015f151  call    cs:__imp_CloseHandle
0x18015f158  nop     dword ptr [rax+rax+00h]
0x18015f15d  mov     eax, edi
0x18015f15f  mov     rcx, [rbp+57h+var_40]
0x18015f163  xor     rcx, rsp; StackCookie
0x18015f166  call    __security_check_cookie
0x18015f16b  add     rsp, 0B0h
0x18015f172  pop     r15
0x18015f174  pop     r14
0x18015f176  pop     r12
0x18015f178  pop     rdi
0x18015f179  pop     rsi
0x18015f17a  pop     rbx
0x18015f17b  pop     rbp
0x18015f17c  retn
```
