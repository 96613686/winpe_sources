# _anonymous_namespace_::IsWizardUser

- ea: `0x180022f24`
- end: `0x180023088`
- name: `_anonymous_namespace_::IsWizardUser`
- size: `356`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180021938`

## callees

- `0x180002018`
- `0x180002024`
- `0x180022e5c`
- `0x180022f24`
- `0x180023b00`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180022f39`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180022f39`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022f85`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022f85`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023078`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023078`
- `KERNEL32!LocalFree` at `0x180023066`
- `KERNEL32!LocalFree` at `0x180023066`
- `ADVAPI32!GetTokenInformation` at `0x180022f77`
- `ADVAPI32!GetTokenInformation` at `0x180022fc1`
- `ADVAPI32!GetTokenInformation` at `0x180022f77`
- `ADVAPI32!GetTokenInformation` at `0x180022fc1`
- `ADVAPI32!OpenProcessToken` at `0x180022f4b`
- `ADVAPI32!OpenProcessToken` at `0x180022f4b`
- `ADVAPI32!ConvertSidToStringSidW` at `0x180022fde`
- `ADVAPI32!ConvertSidToStringSidW` at `0x180022fde`

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
      if ( v2 )
      {
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
        operator delete[](v2);
      }
    }
    CloseHandle(TokenHandle);
  }
  return v0;
}

```

## disassembly

```asm
0x180022f24  push    rbp
0x180022f26  push    rbx
0x180022f27  push    rdi
0x180022f28  mov     rbp, rsp
0x180022f2b  sub     rsp, 30h
0x180022f2f  xor     bl, bl
0x180022f31  mov     [rbp+TokenHandle], 0
0x180022f39  call    cs:__imp_GetCurrentProcess
0x180022f3f  lea     r8, [rbp+TokenHandle]; TokenHandle
0x180022f43  mov     edx, 8; DesiredAccess
0x180022f48  mov     rcx, rax; ProcessHandle
0x180022f4b  call    cs:__imp_OpenProcessToken
0x180022f51  test    eax, eax
0x180022f53  jz      loc_18002307E
0x180022f59  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180022f5d  lea     rax, [rbp+TokenInformationLength]
0x180022f61  xor     r9d, r9d; TokenInformationLength
0x180022f64  mov     [rbp+TokenInformationLength], 0
0x180022f6b  xor     r8d, r8d; TokenInformation
0x180022f6e  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x180022f73  lea     edx, [r9+1]; TokenInformationClass
0x180022f77  call    cs:__imp_GetTokenInformation
0x180022f7d  test    eax, eax
0x180022f7f  jnz     loc_180023074
0x180022f85  call    cs:__imp_GetLastError
0x180022f8b  cmp     eax, 7Ah ; 'z'
0x180022f8e  jnz     loc_180023074
0x180022f94  mov     ecx, [rbp+TokenInformationLength]; unsigned __int64
0x180022f97  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180022f9c  mov     rdi, rax
0x180022f9f  test    rax, rax
0x180022fa2  jz      loc_180023074
0x180022fa8  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x180022fac  lea     rax, [rbp+TokenInformationLength]
0x180022fb0  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180022fb4  mov     r8, rdi; TokenInformation
0x180022fb7  mov     edx, 1; TokenInformationClass
0x180022fbc  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x180022fc1  call    cs:__imp_GetTokenInformation
0x180022fc7  test    eax, eax
0x180022fc9  jz      loc_18002306C
0x180022fcf  mov     rcx, [rdi]; Sid
0x180022fd2  lea     rdx, [rbp+StringSid]; StringSid
0x180022fd6  mov     [rbp+StringSid], 0
0x180022fde  call    cs:__imp_ConvertSidToStringSidW
0x180022fe4  test    eax, eax
0x180022fe6  jz      loc_18002306C
0x180022fec  mov     rbx, [rbp+StringSid]
0x180022ff0  lea     rax, [rbp+arg_8]
0x180022ff4  lea     r8, aLaunchuseroobe; "LaunchUserOOBE"
0x180022ffb  mov     [rsp+30h+ReturnLength], rax; int *
0x180023000  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180023007  mov     [rbp+arg_8], 0
0x18002300e  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x180023015  call    ?SHRegGetBOOLWithREGSAM@@YAJPEAUHKEY__@@PEBG1KPEAH@Z; SHRegGetBOOLWithREGSAM(HKEY__ *,ushort const *,ushort const *,ulong,int *)
0x18002301a  cmp     [rbp+arg_8], 0
0x18002301e  jnz     short loc_180023060
0x180023020  lea     rax, [rbp+arg_8]
0x180023024  mov     [rbp+arg_8], 0
0x18002302b  lea     r8, aLaunchcflscena; "LaunchCflScenario"
0x180023032  mov     [rsp+30h+ReturnLength], rax; int *
0x180023037  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18002303e  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x180023045  call    ?SHRegGetBOOLWithREGSAM@@YAJPEAUHKEY__@@PEBG1KPEAH@Z; SHRegGetBOOLWithREGSAM(HKEY__ *,ushort const *,ushort const *,ulong,int *)
0x18002304a  cmp     [rbp+arg_8], 0
0x18002304e  jnz     short loc_180023060
0x180023050  mov     rcx, rbx; unsigned __int16 *
0x180023053  call    ?IsCamCxhOnlyUser@@YA_NPEBG@Z; IsCamCxhOnlyUser(ushort const *)
0x180023058  test    al, al
0x18002305a  jnz     short loc_180023060
0x18002305c  xor     bl, bl
0x18002305e  jmp     short loc_180023062
0x180023060  mov     bl, 1
0x180023062  mov     rcx, [rbp+StringSid]; hMem
0x180023066  call    cs:__imp_LocalFree
0x18002306c  mov     rcx, rdi; void *
0x18002306f  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180023074  mov     rcx, [rbp+TokenHandle]; hObject
0x180023078  call    cs:__imp_CloseHandle
0x18002307e  mov     al, bl
0x180023080  add     rsp, 30h
0x180023084  pop     rdi
0x180023085  pop     rbx
0x180023086  pop     rbp
0x180023087  retn
```
