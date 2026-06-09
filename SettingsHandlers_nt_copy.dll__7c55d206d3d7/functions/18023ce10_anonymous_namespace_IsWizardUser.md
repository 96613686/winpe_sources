# _anonymous_namespace_::IsWizardUser

- ea: `0x18023ce10`
- end: `0x18023cf9c`
- name: `_anonymous_namespace_::IsWizardUser`
- size: `396`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18023b930`

## callees

- `0x18000c940`
- `0x18000cd28`
- `0x18004e7c0`
- `0x18023cd30`
- `0x18023ce10`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18023ce25`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18023ce25`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18023ce3d`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18023ce3d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18023ce83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18023ce83`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18023cf85`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18023cf85`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18023cf6d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18023cf6d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18023ce6f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18023cebc`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18023ce6f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18023cebc`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18023cedf`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18023cedf`

## pseudocode

```c
bool anonymous_namespace_::IsWizardUser()
{
  bool v0; // bl
  HANDLE CurrentProcess; // rax
  void **v2; // rdi
  void *v3; // rcx
  unsigned int v4; // r9d
  const unsigned __int16 *v5; // rbx
  unsigned int v6; // r9d
  DWORD TokenInformationLength; // [rsp+50h] [rbp+20h] BYREF
  int v9; // [rsp+58h] [rbp+28h] BYREF
  void *TokenHandle; // [rsp+60h] [rbp+30h] BYREF
  LPWSTR StringSid; // [rsp+68h] [rbp+38h] BYREF

  v0 = 0;
  TokenHandle = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
  {
    TokenInformationLength = 0;
    if ( !GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength) && GetLastError() == 122 )
    {
      v2 = (void **)operator new[](TokenInformationLength);
      if ( GetTokenInformation(TokenHandle, TokenUser, v2, TokenInformationLength, &TokenInformationLength) )
      {
        v3 = *v2;
        StringSid = 0;
        if ( ConvertSidToStringSidW(v3, &StringSid) )
        {
          v5 = StringSid;
          v9 = 0;
          SHRegGetBOOLWithREGSAM(
            HKEY_LOCAL_MACHINE,
            L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\OOBE",
            L"LaunchUserOOBE",
            v4,
            &v9);
          v0 = 1;
          if ( !v9 )
          {
            v9 = 0;
            SHRegGetBOOLWithREGSAM(
              HKEY_LOCAL_MACHINE,
              L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Authentication\\CFL\\ExperienceManagerData",
              L"LaunchCflScenario",
              v6,
              &v9);
            if ( !v9 && !IsCamCxhOnlyUser(v5) )
              v0 = 0;
          }
          LocalFree(StringSid);
        }
      }
      operator delete(v2);
    }
    CloseHandle(TokenHandle);
  }
  return v0;
}

```

## disassembly

```asm
0x18023ce10  push    rbp
0x18023ce12  push    rbx
0x18023ce13  push    rdi
0x18023ce14  mov     rbp, rsp
0x18023ce17  sub     rsp, 30h
0x18023ce1b  xor     bl, bl
0x18023ce1d  mov     [rbp+TokenHandle], 0
0x18023ce25  call    cs:__imp_GetCurrentProcess
0x18023ce2c  nop     dword ptr [rax+rax+00h]
0x18023ce31  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18023ce35  mov     edx, 8; DesiredAccess
0x18023ce3a  mov     rcx, rax; ProcessHandle
0x18023ce3d  call    cs:__imp_OpenProcessToken
0x18023ce44  nop     dword ptr [rax+rax+00h]
0x18023ce49  test    eax, eax
0x18023ce4b  jz      loc_18023CF91
0x18023ce51  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18023ce55  lea     rax, [rbp+TokenInformationLength]
0x18023ce59  xor     r9d, r9d; TokenInformationLength
0x18023ce5c  mov     [rbp+TokenInformationLength], 0
0x18023ce63  xor     r8d, r8d; TokenInformation
0x18023ce66  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x18023ce6b  lea     edx, [r9+1]; TokenInformationClass
0x18023ce6f  call    cs:__imp_GetTokenInformation
0x18023ce76  nop     dword ptr [rax+rax+00h]
0x18023ce7b  test    eax, eax
0x18023ce7d  jnz     loc_18023CF81
0x18023ce83  call    cs:__imp_GetLastError
0x18023ce8a  nop     dword ptr [rax+rax+00h]
0x18023ce8f  cmp     eax, 7Ah ; 'z'
0x18023ce92  jnz     loc_18023CF81
0x18023ce98  mov     ecx, [rbp+TokenInformationLength]; unsigned __int64
0x18023ce9b  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18023cea0  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x18023cea4  mov     rdi, rax
0x18023cea7  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18023ceab  lea     rax, [rbp+TokenInformationLength]
0x18023ceaf  mov     r8, rdi; TokenInformation
0x18023ceb2  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x18023ceb7  mov     edx, 1; TokenInformationClass
0x18023cebc  call    cs:__imp_GetTokenInformation
0x18023cec3  nop     dword ptr [rax+rax+00h]
0x18023cec8  test    eax, eax
0x18023ceca  jz      loc_18023CF79
0x18023ced0  mov     rcx, [rdi]; Sid
0x18023ced3  lea     rdx, [rbp+StringSid]; StringSid
0x18023ced7  mov     [rbp+StringSid], 0
0x18023cedf  call    cs:__imp_ConvertSidToStringSidW
0x18023cee6  nop     dword ptr [rax+rax+00h]
0x18023ceeb  test    eax, eax
0x18023ceed  jz      loc_18023CF79
0x18023cef3  mov     rbx, [rbp+StringSid]
0x18023cef7  lea     rax, [rbp+arg_8]
0x18023cefb  lea     r8, aLaunchuseroobe; "LaunchUserOOBE"
0x18023cf02  mov     [rsp+30h+ReturnLength], rax; int *
0x18023cf07  lea     rdx, aSoftwareMicros_9; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18023cf0e  mov     [rbp+arg_8], 0
0x18023cf15  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x18023cf1c  call    ?SHRegGetBOOLWithREGSAM@@YAJPEAUHKEY__@@PEBG1KPEAH@Z; SHRegGetBOOLWithREGSAM(HKEY__ *,ushort const *,ushort const *,ulong,int *)
0x18023cf21  cmp     [rbp+arg_8], 0
0x18023cf25  jnz     short loc_18023CF67
0x18023cf27  lea     rax, [rbp+arg_8]
0x18023cf2b  mov     [rbp+arg_8], 0
0x18023cf32  lea     r8, aLaunchcflscena; "LaunchCflScenario"
0x18023cf39  mov     [rsp+30h+ReturnLength], rax; int *
0x18023cf3e  lea     rdx, aSoftwareMicros_5; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18023cf45  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x18023cf4c  call    ?SHRegGetBOOLWithREGSAM@@YAJPEAUHKEY__@@PEBG1KPEAH@Z; SHRegGetBOOLWithREGSAM(HKEY__ *,ushort const *,ushort const *,ulong,int *)
0x18023cf51  cmp     [rbp+arg_8], 0
0x18023cf55  jnz     short loc_18023CF67
0x18023cf57  mov     rcx, rbx; unsigned __int16 *
0x18023cf5a  call    ?IsCamCxhOnlyUser@@YA_NPEBG@Z; IsCamCxhOnlyUser(ushort const *)
0x18023cf5f  test    al, al
0x18023cf61  jnz     short loc_18023CF67
0x18023cf63  xor     bl, bl
0x18023cf65  jmp     short loc_18023CF69
0x18023cf67  mov     bl, 1
0x18023cf69  mov     rcx, [rbp+StringSid]; hMem
0x18023cf6d  call    cs:__imp_LocalFree
0x18023cf74  nop     dword ptr [rax+rax+00h]
0x18023cf79  mov     rcx, rdi; Block
0x18023cf7c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18023cf81  mov     rcx, [rbp+TokenHandle]; hObject
0x18023cf85  call    cs:__imp_CloseHandle
0x18023cf8c  nop     dword ptr [rax+rax+00h]
0x18023cf91  mov     al, bl
0x18023cf93  add     rsp, 30h
0x18023cf97  pop     rdi
0x18023cf98  pop     rbx
0x18023cf99  pop     rbp
0x18023cf9a  retn
```
