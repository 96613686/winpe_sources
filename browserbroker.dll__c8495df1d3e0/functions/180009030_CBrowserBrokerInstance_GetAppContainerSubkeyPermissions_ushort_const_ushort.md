# CBrowserBrokerInstance::GetAppContainerSubkeyPermissions(ushort const *,ushort * *)

- ea: `0x180009030`
- end: `0x180009233`
- name: `?GetAppContainerSubkeyPermissions@CBrowserBrokerInstance@@UEAAJPEBGPEAPEAG@Z`
- size: `515`
- prototype: `int(CBrowserBrokerInstance *__hidden this, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180002ce0`
- `0x180009030`
- `0x18000a2dc`
- `0x18000e428`

## import_xrefs

- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x1800091a3`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x1800091a3`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18000907f`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18000907f`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800090a9`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180009209`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800090a9`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180009209`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800091b0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800091c4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800091b0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800091c4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800091dc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800091f4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800091dc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800091f4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800090e1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009115`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800090e1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009115`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x180009191`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x180009191`
- `profapi!__imp_GetAppContainerRegistryPath` at `0x180009099`
- `profapi!__imp_GetAppContainerRegistryPath` at `0x180009099`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x180009163`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x180009163`

## pseudocode

```c
__int64 __fastcall CBrowserBrokerInstance::GetAppContainerSubkeyPermissions(
        CBrowserBrokerInstance *this,
        const unsigned __int16 *a2,
        unsigned __int16 **a3)
{
  int PIC; // ebx
  LSTATUS v6; // eax
  LSTATUS v7; // eax
  signed int SecurityInfo; // eax
  LPWSTR StringSecurityDescriptor; // [rsp+40h] [rbp-C0h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+48h] [rbp-B8h] BYREF
  HKEY phkResult; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR SubKey[520]; // [rsp+60h] [rbp-A0h] BYREF

  LODWORD(StringSecurityDescriptor) = 0;
  PIC = BrokerAuthenticateAttachedCallerGetPIC(1, (unsigned int *)&StringSecurityDescriptor);
  if ( PIC >= 0 )
  {
    PIC = CoImpersonateClient();
    if ( PIC >= 0 )
    {
      PIC = GetAppContainerRegistryPath(SubKey, 520);
      if ( PIC < 0 )
      {
        CoRevertToSelf();
      }
      else
      {
        PIC = CoRevertToSelf();
        if ( PIC >= 0 )
        {
          hKey = 0;
          v6 = RegOpenKeyExW(HKEY_USERS, SubKey, 0, 0x20000u, &hKey);
          PIC = v6;
          if ( v6 )
          {
            if ( v6 > 0 )
              return (unsigned __int16)v6 | 0x80070000;
          }
          else
          {
            phkResult = 0;
            v7 = RegOpenKeyExW(hKey, a2, 0, 0x20000u, &phkResult);
            PIC = v7;
            if ( v7 )
            {
              if ( v7 > 0 )
                PIC = (unsigned __int16)v7 | 0x80070000;
            }
            else
            {
              SecurityDescriptor = 0;
              SecurityInfo = GetSecurityInfo(phkResult, SE_REGISTRY_KEY, 4u, 0, 0, 0, 0, &SecurityDescriptor);
              PIC = SecurityInfo;
              if ( SecurityInfo )
              {
                if ( SecurityInfo > 0 )
                  PIC = (unsigned __int16)SecurityInfo | 0x80070000;
              }
              else
              {
                StringSecurityDescriptor = 0;
                if ( ConvertSecurityDescriptorToStringSecurityDescriptorW(
                       SecurityDescriptor,
                       1u,
                       4u,
                       &StringSecurityDescriptor,
                       0) )
                {
                  PIC = SHStrDupW(StringSecurityDescriptor, a3);
                  LocalFree(StringSecurityDescriptor);
                }
                else
                {
                  PIC = HRESULTFromLastErrorError();
                }
                LocalFree(SecurityDescriptor);
              }
              RegCloseKey(phkResult);
            }
            RegCloseKey(hKey);
          }
        }
      }
    }
  }
  return (unsigned int)PIC;
}

```

## disassembly

```asm
0x180009030  mov     [rsp-8+arg_0], rbx
0x180009035  push    rbp
0x180009036  push    rsi
0x180009037  push    rdi
0x180009038  lea     rbp, [rsp-380h]
0x180009040  sub     rsp, 480h
0x180009047  mov     rax, cs:__security_cookie
0x18000904e  xor     rax, rsp
0x180009051  mov     [rbp+390h+var_20], rax
0x180009058  mov     rsi, rdx
0x18000905b  mov     dword ptr [rsp+490h+StringSecurityDescriptor], 0
0x180009063  lea     rdx, [rsp+490h+StringSecurityDescriptor]; unsigned int *
0x180009068  mov     ecx, 1; unsigned int
0x18000906d  mov     rdi, r8
0x180009070  call    ?BrokerAuthenticateAttachedCallerGetPIC@@YAJKPEAK@Z; BrokerAuthenticateAttachedCallerGetPIC(ulong,ulong *)
0x180009075  mov     ebx, eax
0x180009077  test    eax, eax
0x180009079  js      loc_18000920F
0x18000907f  call    cs:__imp_CoImpersonateClient
0x180009085  mov     ebx, eax
0x180009087  test    eax, eax
0x180009089  js      loc_18000920F
0x18000908f  mov     edx, 208h
0x180009094  lea     rcx, [rsp+490h+SubKey]
0x180009099  call    cs:__imp_GetAppContainerRegistryPath
0x18000909f  mov     ebx, eax
0x1800090a1  test    eax, eax
0x1800090a3  js      loc_180009209
0x1800090a9  call    cs:__imp_CoRevertToSelf
0x1800090af  mov     ebx, eax
0x1800090b1  test    eax, eax
0x1800090b3  js      loc_18000920F
0x1800090b9  lea     rax, [rsp+490h+hKey]
0x1800090be  mov     [rsp+490h+hKey], 0
0x1800090c7  mov     r9d, 20000h; samDesired
0x1800090cd  mov     [rsp+490h+phkResult], rax; phkResult
0x1800090d2  xor     r8d, r8d; ulOptions
0x1800090d5  lea     rdx, [rsp+490h+SubKey]; lpSubKey
0x1800090da  mov     rcx, 0FFFFFFFF80000003h; hKey
0x1800090e1  call    cs:__imp_RegOpenKeyExW
0x1800090e7  mov     ebx, eax
0x1800090e9  test    eax, eax
0x1800090eb  jnz     loc_1800091FC
0x1800090f1  mov     rcx, [rsp+490h+hKey]; hKey
0x1800090f6  lea     rax, [rsp+490h+var_440]
0x1800090fb  mov     r9d, 20000h; samDesired
0x180009101  mov     [rsp+490h+phkResult], rax; phkResult
0x180009106  xor     r8d, r8d; ulOptions
0x180009109  mov     [rsp+490h+var_440], 0
0x180009112  mov     rdx, rsi; lpSubKey
0x180009115  call    cs:__imp_RegOpenKeyExW
0x18000911b  mov     ebx, eax
0x18000911d  test    eax, eax
0x18000911f  jnz     loc_1800091E4
0x180009125  mov     rcx, [rsp+490h+var_440]; handle
0x18000912a  lea     rax, [rsp+490h+SecurityDescriptor]
0x18000912f  mov     [rsp+490h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x180009134  lea     esi, [rbx+4]
0x180009137  mov     [rsp+490h+ppSacl], 0; ppSacl
0x180009140  xor     r9d, r9d; ppsidOwner
0x180009143  mov     [rsp+490h+ppDacl], 0; ppDacl
0x18000914c  mov     r8d, esi; SecurityInfo
0x18000914f  mov     edx, esi; ObjectType
0x180009151  mov     [rsp+490h+phkResult], 0; ppsidGroup
0x18000915a  mov     [rsp+490h+SecurityDescriptor], 0
0x180009163  call    cs:__imp_GetSecurityInfo
0x180009169  mov     ebx, eax
0x18000916b  test    eax, eax
0x18000916d  jnz     short loc_1800091CC
0x18000916f  mov     rcx, [rsp+490h+SecurityDescriptor]; SecurityDescriptor
0x180009174  lea     r9, [rsp+490h+StringSecurityDescriptor]; StringSecurityDescriptor
0x180009179  mov     r8d, esi; SecurityInformation
0x18000917c  mov     [rsp+490h+StringSecurityDescriptor], 0
0x180009185  lea     edx, [rsi-3]; RequestedStringSDRevision
0x180009188  mov     [rsp+490h+phkResult], 0; StringSecurityDescriptorLen
0x180009191  call    cs:__imp_ConvertSecurityDescriptorToStringSecurityDescriptorW
0x180009197  test    eax, eax
0x180009199  jz      short loc_1800091B8
0x18000919b  mov     rcx, [rsp+490h+StringSecurityDescriptor]; psz
0x1800091a0  mov     rdx, rdi; ppwsz
0x1800091a3  call    cs:__imp_SHStrDupW
0x1800091a9  mov     rcx, [rsp+490h+StringSecurityDescriptor]; hMem
0x1800091ae  mov     ebx, eax
0x1800091b0  call    cs:__imp_LocalFree
0x1800091b6  jmp     short loc_1800091BF
0x1800091b8  call    ?HRESULTFromLastErrorError@@YAJXZ; HRESULTFromLastErrorError(void)
0x1800091bd  mov     ebx, eax
0x1800091bf  mov     rcx, [rsp+490h+SecurityDescriptor]; hMem
0x1800091c4  call    cs:__imp_LocalFree
0x1800091ca  jmp     short loc_1800091D7
0x1800091cc  jle     short loc_1800091D7
0x1800091ce  movzx   ebx, ax
0x1800091d1  or      ebx, 80070000h
0x1800091d7  mov     rcx, [rsp+490h+var_440]; hKey
0x1800091dc  call    cs:__imp_RegCloseKey
0x1800091e2  jmp     short loc_1800091EF
0x1800091e4  jle     short loc_1800091EF
0x1800091e6  movzx   ebx, ax
0x1800091e9  or      ebx, 80070000h
0x1800091ef  mov     rcx, [rsp+490h+hKey]; hKey
0x1800091f4  call    cs:__imp_RegCloseKey
0x1800091fa  jmp     short loc_18000920F
0x1800091fc  jle     short loc_18000920F
0x1800091fe  movzx   ebx, ax
0x180009201  or      ebx, 80070000h
0x180009207  jmp     short loc_18000920F
0x180009209  call    cs:__imp_CoRevertToSelf
0x18000920f  mov     eax, ebx
0x180009211  mov     rcx, [rbp+390h+var_20]
0x180009218  xor     rcx, rsp; StackCookie
0x18000921b  call    __security_check_cookie
0x180009220  mov     rbx, [rsp+490h+arg_0]
0x180009228  add     rsp, 480h
0x18000922f  pop     rdi
0x180009230  pop     rsi
0x180009231  pop     rbp
0x180009232  retn
```
