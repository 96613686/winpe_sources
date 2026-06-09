# KerbLoadModpDH(void)

- ea: `0x180079a38`
- end: `0x180079bed`
- name: `?KerbLoadModpDH@@YAHXZ`
- size: `437`
- prototype: `int(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800799bc`

## callees

- `0x1800101c4`
- `0x1800101ec`
- `0x1800797c8`
- `0x180079a38`
- `0x180085168`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079b20`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079b20`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180079b56`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180079b56`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180079bd5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180079bd5`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptAcquireContextW` at `0x180079af6`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptAcquireContextW` at `0x180079af6`
- `ntdll!RtlInitializeCriticalSection` at `0x180079b65`
- `ntdll!RtlInitializeCriticalSection` at `0x180079b65`
- `ntdll!NtOpenThreadToken` at `0x180079a82`
- `ntdll!NtOpenThreadToken` at `0x180079a82`
- `ntdll!NtSetInformationThread` at `0x180079ace`
- `ntdll!NtSetInformationThread` at `0x180079bca`
- `ntdll!NtSetInformationThread` at `0x180079ace`
- `ntdll!NtSetInformationThread` at `0x180079bca`

## pseudocode

```c
__int64 KerbLoadModpDH(void)
{
  BOOL v1; // edi
  NTSTATUS v2; // ecx
  void *v3; // rax
  DWORD LastError; // eax
  void *TokenHandle; // [rsp+40h] [rbp+8h] BYREF
  __int64 ThreadInformation; // [rsp+48h] [rbp+10h] BYREF

  TokenHandle = 0;
  ThreadInformation = 0;
  if ( KerbGlobalWellknownDomainParamtersLockInitialized )
    return 1;
  v1 = 0;
  v2 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 0xCu, 1u, &TokenHandle);
  if ( (int)(v2 + 0x80000000) < 0 || v2 == -1073741700 )
  {
    if ( v2 == -1073741700 )
    {
      v3 = 0;
      TokenHandle = 0;
    }
    else
    {
      v3 = TokenHandle;
    }
    if ( !v3
      || NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &ThreadInformation, 8u) >= 0 )
    {
      if ( !CryptAcquireContextW(&KerbGlobalCSPProvider, 0, 0, 0xDu, 0xF0000040) )
      {
        if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          LastError = GetLastError();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_4256176c45563d9365687fae28cf9cb4_Traceguids, LastError);
        }
        goto LABEL_21;
      }
      if ( KerbGetGlobalEphemeralDHAlg() )
      {
        if ( RtlInitializeCriticalSection(&KerbGlobalWellknownDomainParamtersLock) >= 0 )
        {
          KerbGlobalWellknownDomainParamtersLockInitialized = 1;
          v1 = KerbInitDHWellknowDomainParametersDefaults() != 0;
          goto LABEL_21;
        }
        if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_4256176c45563d9365687fae28cf9cb4_Traceguids);
        }
      }
      SetLastError(0x5AAu);
    }
  }
LABEL_21:
  if ( TokenHandle )
  {
    NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &TokenHandle, 8u);
    CloseHandle(TokenHandle);
  }
  return v1;
}

```

## disassembly

```asm
0x180079a38  mov     rax, rsp
0x180079a3b  mov     [rax+18h], rbx
0x180079a3f  mov     [rax+20h], rbp
0x180079a43  push    rdi
0x180079a44  sub     rsp, 30h
0x180079a48  cmp     cs:?KerbGlobalWellknownDomainParamtersLockInitialized@@3HA, 0; int KerbGlobalWellknownDomainParamtersLockInitialized
0x180079a4f  mov     qword ptr [rax+8], 0
0x180079a57  mov     qword ptr [rax+10h], 0
0x180079a5f  jz      short loc_180079A6B
0x180079a61  mov     eax, 1
0x180079a66  jmp     loc_180079BDD
0x180079a6b  xor     edi, edi
0x180079a6d  lea     r9, [rsp+38h+TokenHandle]; TokenHandle
0x180079a72  lea     ebx, [rdi+1]
0x180079a75  lea     rbp, [rdi-2]
0x180079a79  mov     r8b, bl; OpenAsSelf
0x180079a7c  mov     rcx, rbp; ThreadHandle
0x180079a7f  lea     edx, [rdi+0Ch]; DesiredAccess
0x180079a82  call    cs:__imp_NtOpenThreadToken
0x180079a88  mov     edx, 80000000h
0x180079a8d  mov     r8d, 0C000007Ch
0x180079a93  mov     ecx, eax
0x180079a95  add     eax, edx
0x180079a97  test    edx, eax
0x180079a99  jnz     short loc_180079AA4
0x180079a9b  cmp     ecx, r8d
0x180079a9e  jnz     loc_180079BB0
0x180079aa4  cmp     ecx, r8d
0x180079aa7  jnz     short loc_180079AB2
0x180079aa9  xor     eax, eax
0x180079aab  mov     [rsp+38h+TokenHandle], rax
0x180079ab0  jmp     short loc_180079AB7
0x180079ab2  mov     rax, [rsp+38h+TokenHandle]
0x180079ab7  test    rax, rax
0x180079aba  jz      short loc_180079ADC
0x180079abc  mov     r9d, 8; ThreadInformationLength
0x180079ac2  lea     r8, [rsp+38h+ThreadInformation]; ThreadInformation
0x180079ac7  mov     rcx, rbp; ThreadHandle
0x180079aca  lea     edx, [r9-3]; ThreadInformationClass
0x180079ace  call    cs:__imp_NtSetInformationThread
0x180079ad4  test    eax, eax
0x180079ad6  js      loc_180079BB0
0x180079adc  mov     r9d, 0Dh; dwProvType
0x180079ae2  mov     [rsp+38h+dwFlags], 0F0000040h; dwFlags
0x180079aea  xor     r8d, r8d; szProvider
0x180079aed  lea     rcx, ?KerbGlobalCSPProvider@@3_KA; phProv
0x180079af4  xor     edx, edx; szContainer
0x180079af6  call    cs:__imp_CryptAcquireContextW
0x180079afc  test    eax, eax
0x180079afe  jnz     short loc_180079B47
0x180079b00  mov     rcx, cs:WPP_GLOBAL_Control
0x180079b07  lea     rax, WPP_GLOBAL_Control
0x180079b0e  cmp     rcx, rax
0x180079b11  jz      loc_180079BB0
0x180079b17  test    [rcx+1Ch], bl
0x180079b1a  jz      loc_180079BB0
0x180079b20  call    cs:__imp_GetLastError
0x180079b26  mov     rcx, cs:WPP_GLOBAL_Control
0x180079b2d  lea     r8, WPP_4256176c45563d9365687fae28cf9cb4_Traceguids
0x180079b34  mov     edx, 0Ah
0x180079b39  mov     r9d, eax
0x180079b3c  mov     rcx, [rcx+10h]
0x180079b40  call    WPP_SF_d
0x180079b45  jmp     short loc_180079BB0
0x180079b47  call    ?KerbGetGlobalEphemeralDHAlg@@YAPEAUKERB_ALGORITHM_IDENTIFIER@@XZ; KerbGetGlobalEphemeralDHAlg(void)
0x180079b4c  test    rax, rax
0x180079b4f  jnz     short loc_180079B5E
0x180079b51  mov     ecx, 5AAh; dwErrCode
0x180079b56  call    cs:__imp_SetLastError
0x180079b5c  jmp     short loc_180079BB0
0x180079b5e  lea     rcx, ?KerbGlobalWellknownDomainParamtersLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x180079b65  call    cs:__imp_RtlInitializeCriticalSection
0x180079b6b  test    eax, eax
0x180079b6d  jns     short loc_180079B9E
0x180079b6f  mov     rcx, cs:WPP_GLOBAL_Control
0x180079b76  lea     rax, WPP_GLOBAL_Control
0x180079b7d  cmp     rcx, rax
0x180079b80  jz      short loc_180079B51
0x180079b82  test    [rcx+1Ch], bl
0x180079b85  jz      short loc_180079B51
0x180079b87  mov     rcx, [rcx+10h]
0x180079b8b  lea     r8, WPP_4256176c45563d9365687fae28cf9cb4_Traceguids
0x180079b92  mov     edx, 0Bh
0x180079b97  call    WPP_SF_
0x180079b9c  jmp     short loc_180079B51
0x180079b9e  mov     cs:?KerbGlobalWellknownDomainParamtersLockInitialized@@3HA, ebx; int KerbGlobalWellknownDomainParamtersLockInitialized
0x180079ba4  call    ?KerbInitDHWellknowDomainParametersDefaults@@YAHXZ; KerbInitDHWellknowDomainParametersDefaults(void)
0x180079ba9  test    eax, eax
0x180079bab  mov     edi, eax
0x180079bad  cmovnz  edi, ebx
0x180079bb0  cmp     [rsp+38h+TokenHandle], 0
0x180079bb6  jz      short loc_180079BDB
0x180079bb8  mov     r9d, 8; ThreadInformationLength
0x180079bbe  lea     r8, [rsp+38h+TokenHandle]; ThreadInformation
0x180079bc3  mov     rcx, rbp; ThreadHandle
0x180079bc6  lea     edx, [r9-3]; ThreadInformationClass
0x180079bca  call    cs:__imp_NtSetInformationThread
0x180079bd0  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x180079bd5  call    cs:__imp_CloseHandle
0x180079bdb  mov     eax, edi
0x180079bdd  mov     rbx, [rsp+38h+arg_10]
0x180079be2  mov     rbp, [rsp+38h+arg_18]
0x180079be7  add     rsp, 30h
0x180079beb  pop     rdi
0x180079bec  retn
```
