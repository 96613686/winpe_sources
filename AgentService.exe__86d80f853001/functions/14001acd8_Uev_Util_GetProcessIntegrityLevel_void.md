# Uev::Util::GetProcessIntegrityLevel(void *)

- ea: `0x14001acd8`
- end: `0x14001afe8`
- name: `?GetProcessIntegrityLevel@Util@Uev@@SA?AW4ProcessIntegrityLevel@12@PEAX@Z`
- size: `784`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x140014da0`

## callees

- `0x140003e50`
- `0x140003f88`
- `0x14000425c`
- `0x140004ab4`
- `0x14000ac88`
- `0x14000d1d8`
- `0x14000d2d8`
- `0x14000d448`
- `0x14001acd8`

## import_xrefs

- `ADVAPI32!GetTokenInformation` at `0x14001ad3b`
- `ADVAPI32!GetTokenInformation` at `0x14001ad9b`
- `ADVAPI32!GetTokenInformation` at `0x14001ad3b`
- `ADVAPI32!GetTokenInformation` at `0x14001ad9b`
- `ADVAPI32!GetSidSubAuthority` at `0x14001ade0`
- `ADVAPI32!GetSidSubAuthority` at `0x14001ade0`
- `ADVAPI32!GetSidSubAuthorityCount` at `0x14001adac`
- `ADVAPI32!GetSidSubAuthorityCount` at `0x14001adac`
- `KERNEL32!GetLastError` at `0x14001ad49`
- `KERNEL32!GetLastError` at `0x14001adb5`
- `KERNEL32!GetLastError` at `0x14001ade9`
- `KERNEL32!GetLastError` at `0x14001af2b`
- `KERNEL32!GetLastError` at `0x14001ad49`
- `KERNEL32!GetLastError` at `0x14001adb5`
- `KERNEL32!GetLastError` at `0x14001ade9`
- `KERNEL32!GetLastError` at `0x14001af2b`

## string_xrefs

- `0x14001ad07`: `AgentService.Util::GetProcessIntegrityLevel: Entry`
- `0x14001ae83`: `GetTokenInformation() should have failed and returned a buffer length value`
- `0x14001aeb6`: `Error obtaining security token information`
- `0x14001aef2`: `Unable to allocate heap memory for security token information`
- `0x14001af33`: `Unable to get the security token information`
- `0x14001afab`: `GetSidSubAuthorityCount() failed`
- `0x14001af6f`: `GetSidSubAuthority() failed`
- `0x14001ae4c`: `AgentService.Util::GetProcessIntegrityLevel: Exit`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall Uev::Util::GetProcessIntegrityLevel(void *a1)
{
  DWORD LastError; // ebx
  PSID *v3; // rbx
  PUCHAR SidSubAuthorityCount; // rdi
  DWORD v5; // esi
  PDWORD SidSubAuthority; // rdi
  DWORD v7; // esi
  DWORD v9; // ebx
  unsigned int v10; // [rsp+30h] [rbp-4A8h]
  _QWORD v11[7]; // [rsp+38h] [rbp-4A0h] BYREF
  _BYTE pExceptionObject[64]; // [rsp+70h] [rbp-468h] BYREF
  _BYTE v13[64]; // [rsp+B0h] [rbp-428h] BYREF
  _BYTE v14[112]; // [rsp+F0h] [rbp-3E8h] BYREF
  _BYTE v15[112]; // [rsp+160h] [rbp-378h] BYREF
  _BYTE v16[112]; // [rsp+1D0h] [rbp-308h] BYREF
  _BYTE v17[112]; // [rsp+240h] [rbp-298h] BYREF
  DWORD TokenInformationLength[132]; // [rsp+2B0h] [rbp-228h] BYREF

  DbgTrace<5>(L"AgentService.Util::GetProcessIntegrityLevel: Entry");
  TokenInformationLength[0] = 0;
  if ( GetTokenInformation(a1, TokenIntegrityLevel, 0, 0, TokenInformationLength) )
  {
    std::wstring::wstring(v11, L"GetTokenInformation() should have failed and returned a buffer length value");
    Uev::UevException::UevException((__int64)pExceptionObject, v11);
    throw (Uev::UevException *)pExceptionObject;
  }
  LastError = GetLastError();
  if ( LastError != 122 )
  {
    std::wstring::wstring(v11, L"Error obtaining security token information");
    Uev::SystemException::SystemException(v14, v11, LastError);
    throw (Uev::SystemException *)v14;
  }
  v3 = (PSID *)operator new[](TokenInformationLength[0], (const struct std::nothrow_t *)&std::nothrow);
  v11[4] = v3;
  if ( !v3 )
  {
    std::wstring::wstring(v11, L"Unable to allocate heap memory for security token information");
    Uev::UevException::UevException((__int64)v13, v11);
    throw (Uev::UevException *)v13;
  }
  if ( !GetTokenInformation(a1, TokenIntegrityLevel, v3, TokenInformationLength[0], TokenInformationLength) )
  {
    v9 = GetLastError();
    std::wstring::wstring(v11, L"Unable to get the security token information");
    Uev::SystemException::SystemException(v15, v11, v9);
    throw (Uev::SystemException *)v15;
  }
  SidSubAuthorityCount = GetSidSubAuthorityCount(*v3);
  v5 = GetLastError();
  if ( v5 || !SidSubAuthorityCount || !*SidSubAuthorityCount )
  {
    std::wstring::wstring(v11, L"GetSidSubAuthorityCount() failed");
    Uev::SystemException::SystemException(v17, v11, v5);
    throw (Uev::SystemException *)v17;
  }
  SidSubAuthority = GetSidSubAuthority(*v3, (unsigned __int8)(*SidSubAuthorityCount - 1));
  v7 = GetLastError();
  if ( v7 || !SidSubAuthority )
  {
    std::wstring::wstring(v11, L"GetSidSubAuthority() failed");
    Uev::SystemException::SystemException(v16, v11, v7);
    throw (Uev::SystemException *)v16;
  }
  if ( *SidSubAuthority >= 0x1000 )
  {
    if ( *SidSubAuthority >= 0x2000 )
    {
      if ( *SidSubAuthority >= 0x3000 )
        v10 = 4 - (*SidSubAuthority < 0x4000);
      else
        v10 = 2;
    }
    else
    {
      v10 = 1;
    }
  }
  else
  {
    v10 = 0;
  }
  operator delete(v3);
  DbgTrace<5>(L"AgentService.Util::GetProcessIntegrityLevel: Exit");
  return v10;
}

```

## disassembly

```asm
0x14001acd8  mov     [rsp+arg_8], rbx
0x14001acdd  mov     [rsp+arg_10], rsi
0x14001ace2  push    rdi
0x14001ace3  sub     rsp, 4D0h
0x14001acea  mov     rax, cs:__security_cookie
0x14001acf1  xor     rax, rsp
0x14001acf4  mov     [rsp+4D8h+var_18], rax
0x14001acfc  mov     rdi, rcx
0x14001acff  mov     [rsp+4D8h+var_4A8], 5
0x14001ad07  lea     rcx, aAgentserviceUt_33; "AgentService.Util::GetProcessIntegrityL"...
0x14001ad0e  call    ??$DbgTrace@$04@@YAXPEB_W@Z; DbgTrace<5>(wchar_t const *)
0x14001ad13  nop
0x14001ad14  mov     [rsp+4D8h+TokenInformationLength], 0
0x14001ad1f  lea     rax, [rsp+4D8h+TokenInformationLength]
0x14001ad27  mov     [rsp+4D8h+ReturnLength], rax; ReturnLength
0x14001ad2c  xor     r9d, r9d; TokenInformationLength
0x14001ad2f  xor     r8d, r8d; TokenInformation
0x14001ad32  lea     esi, [r9+19h]
0x14001ad36  mov     edx, esi; TokenInformationClass
0x14001ad38  mov     rcx, rdi; TokenHandle
0x14001ad3b  call    cs:__imp_GetTokenInformation
0x14001ad41  test    eax, eax
0x14001ad43  jnz     loc_14001AE83
0x14001ad49  call    cs:__imp_GetLastError
0x14001ad4f  mov     ebx, eax
0x14001ad51  cmp     eax, 7Ah ; 'z'
0x14001ad54  jnz     loc_14001AEB6
0x14001ad5a  mov     ecx, [rsp+4D8h+TokenInformationLength]; unsigned __int64
0x14001ad61  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14001ad68  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x14001ad6d  mov     rbx, rax
0x14001ad70  mov     [rsp+4D8h+var_480], rax
0x14001ad75  test    rax, rax
0x14001ad78  jz      loc_14001AEF2
0x14001ad7e  lea     rax, [rsp+4D8h+TokenInformationLength]
0x14001ad86  mov     [rsp+4D8h+ReturnLength], rax; ReturnLength
0x14001ad8b  mov     r9d, [rsp+4D8h+TokenInformationLength]; TokenInformationLength
0x14001ad93  mov     r8, rbx; TokenInformation
0x14001ad96  mov     edx, esi; TokenInformationClass
0x14001ad98  mov     rcx, rdi; TokenHandle
0x14001ad9b  call    cs:__imp_GetTokenInformation
0x14001ada1  test    eax, eax
0x14001ada3  jz      loc_14001AF2B
0x14001ada9  mov     rcx, [rbx]; pSid
0x14001adac  call    cs:__imp_GetSidSubAuthorityCount
0x14001adb2  mov     rdi, rax
0x14001adb5  call    cs:__imp_GetLastError
0x14001adbb  mov     esi, eax
0x14001adbd  test    eax, eax
0x14001adbf  jnz     loc_14001AFAB
0x14001adc5  test    rdi, rdi
0x14001adc8  jz      loc_14001AFAB
0x14001adce  mov     cl, [rdi]
0x14001add0  test    cl, cl
0x14001add2  jz      loc_14001AFAB
0x14001add8  dec     cl
0x14001adda  movzx   edx, cl; nSubAuthority
0x14001addd  mov     rcx, [rbx]; pSid
0x14001ade0  call    cs:__imp_GetSidSubAuthority
0x14001ade6  mov     rdi, rax
0x14001ade9  call    cs:__imp_GetLastError
0x14001adef  mov     esi, eax
0x14001adf1  test    eax, eax
0x14001adf3  jnz     loc_14001AF6F
0x14001adf9  test    rdi, rdi
0x14001adfc  jz      loc_14001AF6F
0x14001ae02  cmp     dword ptr [rdi], 1000h
0x14001ae08  jnb     short loc_14001AE10
0x14001ae0a  mov     [rsp+4D8h+var_4A8], eax
0x14001ae0e  jmp     short loc_14001AE43
0x14001ae10  cmp     dword ptr [rdi], 2000h
0x14001ae16  jnb     short loc_14001AE22
0x14001ae18  mov     [rsp+4D8h+var_4A8], 1
0x14001ae20  jmp     short loc_14001AE43
0x14001ae22  cmp     dword ptr [rdi], 3000h
0x14001ae28  jnb     short loc_14001AE34
0x14001ae2a  mov     [rsp+4D8h+var_4A8], 2
0x14001ae32  jmp     short loc_14001AE43
0x14001ae34  cmp     dword ptr [rdi], 4000h
0x14001ae3a  sbb     eax, eax
0x14001ae3c  add     eax, 4
0x14001ae3f  mov     [rsp+4D8h+var_4A8], eax
0x14001ae43  mov     rcx, rbx; Block
0x14001ae46  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14001ae4b  nop
0x14001ae4c  lea     rcx, aAgentserviceUt_13; "AgentService.Util::GetProcessIntegrityL"...
0x14001ae53  call    ??$DbgTrace@$04@@YAXPEB_W@Z; DbgTrace<5>(wchar_t const *)
0x14001ae58  mov     eax, [rsp+4D8h+var_4A8]
0x14001ae5c  mov     rcx, [rsp+4D8h+var_18]
0x14001ae64  xor     rcx, rsp; StackCookie
0x14001ae67  call    __security_check_cookie
0x14001ae6c  lea     r11, [rsp+4D8h+var_8]
0x14001ae74  mov     rbx, [r11+18h]
0x14001ae78  mov     rsi, [r11+20h]
0x14001ae7c  mov     rsp, r11
0x14001ae7f  pop     rdi
0x14001ae80  retn
0x14001ae81  jmp     short loc_14001AE4C
0x14001ae83  lea     rdx, aGettokeninform; "GetTokenInformation() should have faile"...
0x14001ae8a  lea     rcx, [rsp+4D8h+var_4A0]
0x14001ae8f  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x14001ae94  nop
0x14001ae95  lea     rdx, [rsp+4D8h+var_4A0]
0x14001ae9a  lea     rcx, [rsp+4D8h+pExceptionObject]
0x14001ae9f  call    ??0UevException@Uev@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Uev::UevException::UevException(std::wstring const &)
0x14001aea4  lea     rdx, _TI2?AVUevException@Uev@@; pThrowInfo
0x14001aeab  lea     rcx, [rsp+4D8h+pExceptionObject]; pExceptionObject
0x14001aeb0  call    _CxxThrowException_0
0x14001aeb6  lea     rdx, aErrorObtaining; "Error obtaining security token informat"...
0x14001aebd  lea     rcx, [rsp+4D8h+var_4A0]
0x14001aec2  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x14001aec7  nop
0x14001aec8  mov     r8d, ebx
0x14001aecb  lea     rdx, [rsp+4D8h+var_4A0]
0x14001aed0  lea     rcx, [rsp+4D8h+var_3E8]
0x14001aed8  call    ??0SystemException@Uev@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@K@Z; Uev::SystemException::SystemException(std::wstring const &,ulong)
0x14001aedd  lea     rdx, _TI3?AVSystemException@Uev@@; pThrowInfo
0x14001aee4  lea     rcx, [rsp+4D8h+var_3E8]; pExceptionObject
0x14001aeec  call    _CxxThrowException_0
0x14001aef2  lea     rdx, aUnableToAlloca; "Unable to allocate heap memory for secu"...
0x14001aef9  lea     rcx, [rsp+4D8h+var_4A0]
0x14001aefe  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x14001af03  nop
0x14001af04  lea     rdx, [rsp+4D8h+var_4A0]
0x14001af09  lea     rcx, [rsp+4D8h+var_428]
0x14001af11  call    ??0UevException@Uev@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Uev::UevException::UevException(std::wstring const &)
0x14001af16  lea     rdx, _TI2?AVUevException@Uev@@; pThrowInfo
0x14001af1d  lea     rcx, [rsp+4D8h+var_428]; pExceptionObject
0x14001af25  call    _CxxThrowException_0
0x14001af2b  call    cs:__imp_GetLastError
0x14001af31  mov     ebx, eax
0x14001af33  lea     rdx, aUnableToGetThe; "Unable to get the security token inform"...
0x14001af3a  lea     rcx, [rsp+4D8h+var_4A0]
0x14001af3f  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x14001af44  nop
0x14001af45  mov     r8d, ebx
0x14001af48  lea     rdx, [rsp+4D8h+var_4A0]
0x14001af4d  lea     rcx, [rsp+4D8h+var_378]
0x14001af55  call    ??0SystemException@Uev@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@K@Z; Uev::SystemException::SystemException(std::wstring const &,ulong)
0x14001af5a  lea     rdx, _TI3?AVSystemException@Uev@@; pThrowInfo
0x14001af61  lea     rcx, [rsp+4D8h+var_378]; pExceptionObject
0x14001af69  call    _CxxThrowException_0
0x14001af6f  lea     rdx, aGetsidsubautho; "GetSidSubAuthority() failed"
0x14001af76  lea     rcx, [rsp+4D8h+var_4A0]
0x14001af7b  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x14001af80  nop
0x14001af81  mov     r8d, esi
0x14001af84  lea     rdx, [rsp+4D8h+var_4A0]
0x14001af89  lea     rcx, [rsp+4D8h+var_308]
0x14001af91  call    ??0SystemException@Uev@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@K@Z; Uev::SystemException::SystemException(std::wstring const &,ulong)
0x14001af96  lea     rdx, _TI3?AVSystemException@Uev@@; pThrowInfo
0x14001af9d  lea     rcx, [rsp+4D8h+var_308]; pExceptionObject
0x14001afa5  call    _CxxThrowException_0
0x14001afab  lea     rdx, aGetsidsubautho_0; "GetSidSubAuthorityCount() failed"
0x14001afb2  lea     rcx, [rsp+4D8h+var_4A0]
0x14001afb7  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x14001afbc  nop
0x14001afbd  mov     r8d, esi
0x14001afc0  lea     rdx, [rsp+4D8h+var_4A0]
0x14001afc5  lea     rcx, [rsp+4D8h+var_298]
0x14001afcd  call    ??0SystemException@Uev@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@K@Z; Uev::SystemException::SystemException(std::wstring const &,ulong)
0x14001afd2  lea     rdx, _TI3?AVSystemException@Uev@@; pThrowInfo
0x14001afd9  lea     rcx, [rsp+4D8h+var_298]; pExceptionObject
0x14001afe1  call    _CxxThrowException_0
```
