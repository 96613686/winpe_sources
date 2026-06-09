# JScriptLib::CScriptReader::IsIntegrityLevelLow(void)

- ea: `0x180157ab4`
- end: `0x180157d48`
- name: `?IsIntegrityLevelLow@CScriptReader@JScriptLib@@AEAAHXZ`
- size: `660`
- prototype: `__int64 __fastcall(JScriptLib::CScriptReader *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180157d50`

## callees

- `0x1800032e0`
- `0x180004418`
- `0x180018bbc`
- `0x1800325a8`
- `0x180157ab4`

## import_xrefs

- `KERNEL32!GetCurrentThread` at `0x180157aea`
- `KERNEL32!GetCurrentThread` at `0x180157b49`
- `KERNEL32!GetCurrentThread` at `0x180157aea`
- `KERNEL32!GetCurrentThread` at `0x180157b49`
- `KERNEL32!GetCurrentProcess` at `0x180157bc1`
- `KERNEL32!GetCurrentProcess` at `0x180157bc1`
- `KERNEL32!CloseHandle` at `0x180157d22`
- `KERNEL32!CloseHandle` at `0x180157d22`
- `KERNEL32!GetLastError` at `0x180157b1f`
- `KERNEL32!GetLastError` at `0x180157b95`
- `KERNEL32!GetLastError` at `0x180157bf6`
- `KERNEL32!GetLastError` at `0x180157c84`
- `KERNEL32!GetLastError` at `0x180157b1f`
- `KERNEL32!GetLastError` at `0x180157b95`
- `KERNEL32!GetLastError` at `0x180157bf6`
- `KERNEL32!GetLastError` at `0x180157c84`
- `ADVAPI32!GetTokenInformation` at `0x180157c7a`
- `ADVAPI32!GetTokenInformation` at `0x180157c7a`
- `ADVAPI32!OpenProcessToken` at `0x180157bd3`
- `ADVAPI32!OpenProcessToken` at `0x180157bd3`
- `ADVAPI32!OpenThreadToken` at `0x180157b03`
- `ADVAPI32!OpenThreadToken` at `0x180157b5b`
- `ADVAPI32!OpenThreadToken` at `0x180157b03`
- `ADVAPI32!OpenThreadToken` at `0x180157b5b`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x180157cc3`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x180157cc3`

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
  __int64 v7; // rdx
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
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_9e5a8fd5af7d3ff7a0d6c0aaa8413012_Traceguids, LastError);
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
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_9e5a8fd5af7d3ff7a0d6c0aaa8413012_Traceguids, v8);
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
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_9e5a8fd5af7d3ff7a0d6c0aaa8413012_Traceguids, v10);
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
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_9e5a8fd5af7d3ff7a0d6c0aaa8413012_Traceguids);
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
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_9e5a8fd5af7d3ff7a0d6c0aaa8413012_Traceguids, v12);
    }
    v6 = WPP_GLOBAL_Control;
LABEL_32:
    v1 = 1;
  }
LABEL_38:
  if ( v6 != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)v6 + 2), 17, &WPP_9e5a8fd5af7d3ff7a0d6c0aaa8413012_Traceguids, v1);
  if ( TokenHandle != (HANDLE)-1LL )
    CloseHandle(TokenHandle);
  return v1;
}

```

## disassembly

```asm
0x180157ab4  push    rbp
0x180157ab6  push    rbx
0x180157ab7  push    rsi
0x180157ab8  push    rdi
0x180157ab9  push    r12
0x180157abb  push    r14
0x180157abd  push    r15
0x180157abf  lea     rbp, [rsp-27h]
0x180157ac4  sub     rsp, 0B0h
0x180157acb  mov     rax, cs:__security_cookie
0x180157ad2  xor     rax, rsp
0x180157ad5  mov     [rbp+57h+var_40], rax
0x180157ad9  mov     [rbp+57h+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x180157ae1  xor     edi, edi
0x180157ae3  mov     [rbp+57h+TokenInformationLength], 58h ; 'X'
0x180157aea  call    cs:__imp_GetCurrentThread
0x180157af0  lea     r15d, [rdi+1]
0x180157af4  mov     rcx, rax; ThreadHandle
0x180157af7  lea     ebx, [rdi+0Eh]
0x180157afa  mov     r8d, r15d; OpenAsSelf
0x180157afd  mov     edx, ebx; DesiredAccess
0x180157aff  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x180157b03  call    cs:__imp_OpenThreadToken
0x180157b09  lea     r14, WPP_GLOBAL_Control
0x180157b10  lea     r12, WPP_9e5a8fd5af7d3ff7a0d6c0aaa8413012_Traceguids
0x180157b17  test    eax, eax
0x180157b19  jnz     loc_180157C30
0x180157b1f  call    cs:__imp_GetLastError
0x180157b25  mov     rcx, cs:WPP_GLOBAL_Control
0x180157b2c  cmp     rcx, r14
0x180157b2f  jz      short loc_180157B49
0x180157b31  test    [rcx+1Ch], r15b
0x180157b35  jz      short loc_180157B49
0x180157b37  mov     rcx, [rcx+10h]
0x180157b3b  lea     edx, [rdi+0Ah]
0x180157b3e  mov     r9d, eax
0x180157b41  mov     r8, r12
0x180157b44  call    WPP_SF_d
0x180157b49  call    cs:__imp_GetCurrentThread
0x180157b4f  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x180157b53  xor     r8d, r8d; OpenAsSelf
0x180157b56  mov     rcx, rax; ThreadHandle
0x180157b59  mov     edx, ebx; DesiredAccess
0x180157b5b  call    cs:__imp_OpenThreadToken
0x180157b61  test    eax, eax
0x180157b63  jz      short loc_180157B95
0x180157b65  xor     esi, esi
0x180157b67  mov     rbx, cs:WPP_GLOBAL_Control
0x180157b6e  cmp     rbx, r14
0x180157b71  jz      loc_180157C39
0x180157b77  test    byte ptr [rbx+1Ch], 8
0x180157b7b  jz      loc_180157C39
0x180157b81  lea     edx, [rsi+0Bh]
0x180157b84  mov     rcx, [rbx+10h]
0x180157b88  mov     r8, r12
0x180157b8b  call    WPP_SF_
0x180157b90  jmp     loc_180157C32
0x180157b95  call    cs:__imp_GetLastError
0x180157b9b  mov     rcx, cs:WPP_GLOBAL_Control
0x180157ba2  cmp     rcx, r14
0x180157ba5  jz      short loc_180157BC1
0x180157ba7  test    [rcx+1Ch], r15b
0x180157bab  jz      short loc_180157BC1
0x180157bad  mov     rcx, [rcx+10h]
0x180157bb1  mov     edx, 0Ch
0x180157bb6  mov     r9d, eax
0x180157bb9  mov     r8, r12
0x180157bbc  call    WPP_SF_d
0x180157bc1  call    cs:__imp_GetCurrentProcess
0x180157bc7  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x180157bcb  mov     edx, 2000Ah; DesiredAccess
0x180157bd0  mov     rcx, rax; ProcessHandle
0x180157bd3  call    cs:__imp_OpenProcessToken
0x180157bd9  test    eax, eax
0x180157bdb  jz      short loc_180157BF6
0x180157bdd  xor     esi, esi
0x180157bdf  mov     rbx, cs:WPP_GLOBAL_Control
0x180157be6  cmp     rbx, r14
0x180157be9  jz      short loc_180157C39
0x180157beb  test    byte ptr [rbx+1Ch], 8
0x180157bef  jz      short loc_180157C39
0x180157bf1  lea     edx, [rsi+0Dh]
0x180157bf4  jmp     short loc_180157B84
0x180157bf6  call    cs:__imp_GetLastError
0x180157bfc  mov     esi, eax
0x180157bfe  mov     rbx, cs:WPP_GLOBAL_Control
0x180157c05  cmp     rbx, r14
0x180157c08  jz      short loc_180157C2B
0x180157c0a  test    [rbx+1Ch], r15b
0x180157c0e  jz      short loc_180157C2B
0x180157c10  mov     rcx, [rbx+10h]
0x180157c14  mov     edx, 0Eh
0x180157c19  mov     r9d, eax
0x180157c1c  mov     r8, r12
0x180157c1f  call    WPP_SF_d
0x180157c24  mov     rbx, cs:WPP_GLOBAL_Control
0x180157c2b  mov     edi, r15d
0x180157c2e  jmp     short loc_180157C39
0x180157c30  xor     esi, esi
0x180157c32  mov     rbx, cs:WPP_GLOBAL_Control
0x180157c39  xor     edx, edx; Val
0x180157c3b  lea     rcx, [rbp+57h+TokenInformation]; void *
0x180157c3f  lea     r8d, [rdx+58h]; Size
0x180157c43  call    memset_0
0x180157c48  test    esi, esi
0x180157c4a  jnz     loc_180157CF9
0x180157c50  test    edi, edi
0x180157c52  jnz     loc_180157CF9
0x180157c58  mov     rcx, [rbp+57h+TokenHandle]
0x180157c5c  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x180157c60  mov     r9d, [rbp+57h+TokenInformationLength]; TokenInformationLength
0x180157c64  lea     edx, [rsi+19h]; TokenInformationClass
0x180157c67  xor     eax, eax
0x180157c69  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180157c6d  cmovz   rcx, rax; TokenHandle
0x180157c71  lea     rax, [rbp+57h+TokenInformationLength]
0x180157c75  mov     [rsp+0E0h+ReturnLength], rax; ReturnLength
0x180157c7a  call    cs:__imp_GetTokenInformation
0x180157c80  test    eax, eax
0x180157c82  jnz     short loc_180157CBA
0x180157c84  call    cs:__imp_GetLastError
0x180157c8a  mov     rbx, cs:WPP_GLOBAL_Control
0x180157c91  cmp     rbx, r14
0x180157c94  jz      short loc_180157CB5
0x180157c96  test    [rbx+1Ch], r15b
0x180157c9a  jz      short loc_180157CB5
0x180157c9c  mov     rcx, [rbx+10h]
0x180157ca0  lea     edx, [rsi+0Fh]
0x180157ca3  mov     r9d, eax
0x180157ca6  mov     r8, r12
0x180157ca9  call    WPP_SF_d
0x180157cae  mov     rbx, cs:WPP_GLOBAL_Control
0x180157cb5  mov     edi, r15d
0x180157cb8  jmp     short loc_180157CF9
0x180157cba  mov     rcx, [rbp+57h+TokenInformation]; pSid
0x180157cbe  mov     edx, 42h ; 'B'; WellKnownSidType
0x180157cc3  call    cs:__imp_IsWellKnownSid
0x180157cc9  test    eax, eax
0x180157ccb  jz      short loc_180157CF2
0x180157ccd  mov     rbx, cs:WPP_GLOBAL_Control
0x180157cd4  cmp     rbx, r14
0x180157cd7  jz      short loc_180157CB5
0x180157cd9  test    byte ptr [rbx+1Ch], 8
0x180157cdd  jz      short loc_180157CB5
0x180157cdf  mov     rcx, [rbx+10h]
0x180157ce3  mov     edx, 10h
0x180157ce8  mov     r8, r12
0x180157ceb  call    WPP_SF_
0x180157cf0  jmp     short loc_180157CAE
0x180157cf2  mov     rbx, cs:WPP_GLOBAL_Control
0x180157cf9  cmp     rbx, r14
0x180157cfc  jz      short loc_180157D18
0x180157cfe  test    byte ptr [rbx+1Ch], 8
0x180157d02  jz      short loc_180157D18
0x180157d04  mov     rcx, [rbx+10h]
0x180157d08  mov     edx, 11h
0x180157d0d  mov     r9d, edi
0x180157d10  mov     r8, r12
0x180157d13  call    WPP_SF_d
0x180157d18  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x180157d1c  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180157d20  jz      short loc_180157D28
0x180157d22  call    cs:__imp_CloseHandle
0x180157d28  mov     eax, edi
0x180157d2a  mov     rcx, [rbp+57h+var_40]
0x180157d2e  xor     rcx, rsp; StackCookie
0x180157d31  call    __security_check_cookie
0x180157d36  add     rsp, 0B0h
0x180157d3d  pop     r15
0x180157d3f  pop     r14
0x180157d41  pop     r12
0x180157d43  pop     rdi
0x180157d44  pop     rsi
0x180157d45  pop     rbx
0x180157d46  pop     rbp
0x180157d47  retn
```
