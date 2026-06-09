# CProcessStateManager::_UpdatePerUserHighContrastSetting(bool)

- ea: `0x18003bb6c`
- end: `0x18003be0d`
- name: `?_UpdatePerUserHighContrastSetting@CProcessStateManager@@AEAAX_N@Z`
- size: `673`
- prototype: `void __fastcall(CProcessStateManager *__hidden this, bool)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18007ecd0`

## callees

- `0x180004b70`
- `0x180004c00`
- `0x180014d24`
- `0x18003bb6c`
- `0x18003bec0`
- `0x18006c000`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18003bcba`
- `KERNEL32!LocalFree` at `0x18003bcce`
- `KERNEL32!LocalFree` at `0x18003bd87`
- `KERNEL32!LocalFree` at `0x18003bcba`
- `KERNEL32!LocalFree` at `0x18003bcce`
- `KERNEL32!LocalFree` at `0x18003bd87`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003bbb2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003bbb2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003bdc9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003bdc9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003bdbe`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003bdbe`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003bd6d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003bd6d`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x18003bbec`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x18003bbec`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18003bc16`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18003bc16`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18003bd08`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18003bd08`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18003bbc0`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18003bbc0`

## string_xrefs

- `0x18003bc35`: `SOFTWARE\Microsoft\Windows\CurrentVersion\SystemProtectedUserData`

## pseudocode

```c
void __fastcall CProcessStateManager::_UpdatePerUserHighContrastSetting(CProcessStateManager *this, char a2)
{
  HSTRING v2; // rcx
  const WCHAR *StringRawBuffer; // rax
  int v5; // edi
  int v6; // r14d
  __int64 v7; // rbx
  const wchar_t *v8; // rdx
  WCHAR *v9; // rax
  __int64 v10; // rcx
  WCHAR *v11; // rcx
  __int64 v12; // rdx
  BOOL v13; // eax
  LSTATUS v14; // eax
  signed int v15; // ebx
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+50h] [rbp-B0h] BYREF
  PSID Sid; // [rsp+58h] [rbp-A8h] BYREF
  LPWSTR pvParam[2]; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-90h] BYREF
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+78h] [rbp-88h] BYREF
  WCHAR StringSecurityDescriptor[264]; // [rsp+90h] [rbp-70h] BYREF
  WCHAR SubKey[264]; // [rsp+2A0h] [rbp+1A0h] BYREF

  v2 = (HSTRING)*((_QWORD *)this + 53);
  if ( v2 )
  {
    Sid = 0;
    StringRawBuffer = WindowsGetStringRawBuffer(v2, 0);
    if ( ConvertStringSidToSidW(StringRawBuffer, &Sid) )
    {
      pvParam[0] = (LPWSTR)16;
      pvParam[1] = 0;
      v5 = 0;
      if ( SystemParametersInfoW(0x42u, 0x10u, pvParam, 0) )
        v5 = BYTE4(pvParam[0]) & 1;
      pvParam[0] = 0;
      v6 = v5;
      if ( a2 )
        v6 = -1;
      if ( ConvertSidToStringSidW(Sid, pvParam) || (int)ResultFromKnownLastError() >= 0 )
      {
        v7 = 260;
        if ( (int)StringCchPrintfW(
                    SubKey,
                    0x104u,
                    L"%s\\%s\\%s\\%s",
                    L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\SystemProtectedUserData",
                    pvParam[0],
                    L"AnyoneRead",
                    L"Colors") >= 0 )
        {
          v8 = L"D:(A;CIOI;KA;;;SY)(A;CIOI;KA;;;LA)(A;CIOI;KR;;;WD)";
          v9 = StringSecurityDescriptor;
          hKey = 0;
          v10 = 2147483646;
          do
          {
            if ( !v10 )
              break;
            if ( !*v8 )
              break;
            *v9++ = *v8++;
            --v10;
            --v7;
          }
          while ( v7 );
          v11 = v9 - 1;
          if ( v7 )
            v11 = v9;
          *v11 = 0;
          if ( v7 )
          {
            SecurityDescriptor = 0;
            v13 = ConvertStringSecurityDescriptorToSecurityDescriptorW(
                    StringSecurityDescriptor,
                    1u,
                    &SecurityDescriptor,
                    0);
            if ( (int)ResultFromWin32Bool(v13) >= 0 )
            {
              SecurityAttributes.lpSecurityDescriptor = SecurityDescriptor;
              *(_QWORD *)&SecurityAttributes.nLength = 24;
              *(_QWORD *)&SecurityAttributes.bInheritHandle = 0;
              v14 = RegCreateKeyExW(
                      HKEY_LOCAL_MACHINE,
                      SubKey,
                      0,
                      (LPWSTR)&sourceString,
                      0,
                      0x2001Fu,
                      &SecurityAttributes,
                      &hKey,
                      0);
              v15 = v14;
              if ( v14 > 0 )
                v15 = (unsigned __int16)v14 | 0x80070000;
              LocalFree(SecurityDescriptor);
              if ( v15 >= 0 )
              {
                LODWORD(SecurityDescriptor) = v6;
                RegSetValueExW(hKey, L"HighContrastEnabledNew", 0, 4u, (const BYTE *)&SecurityDescriptor, 4u);
                RegCloseKey(hKey);
              }
            }
          }
        }
        LocalFree(pvParam[0]);
      }
      if ( !a2 )
        _WriteSystemDataRegistryDWORDForUser(Sid, v12, L"HighContrastEnabled");
      LocalFree(Sid);
    }
  }
}

```

## disassembly

```asm
0x18003bb6c  push    rbp
0x18003bb6e  push    rbx
0x18003bb6f  push    rsi
0x18003bb70  push    rdi
0x18003bb71  push    r14
0x18003bb73  push    r15
0x18003bb75  lea     rbp, [rsp-3C8h]
0x18003bb7d  sub     rsp, 4C8h
0x18003bb84  mov     rax, cs:__security_cookie
0x18003bb8b  xor     rax, rsp
0x18003bb8e  mov     [rbp+3F0h+var_40], rax
0x18003bb95  mov     rcx, [rcx+1A8h]; string
0x18003bb9c  xor     r15d, r15d
0x18003bb9f  mov     sil, dl
0x18003bba2  test    rcx, rcx
0x18003bba5  jz      loc_18003BCD4
0x18003bbab  xor     edx, edx; length
0x18003bbad  mov     [rsp+4F0h+Sid], r15
0x18003bbb2  call    cs:__imp_WindowsGetStringRawBuffer
0x18003bbb8  mov     rcx, rax; StringSid
0x18003bbbb  lea     rdx, [rsp+4F0h+Sid]; Sid
0x18003bbc0  call    cs:__imp_ConvertStringSidToSidW
0x18003bbc6  test    eax, eax
0x18003bbc8  jz      loc_18003BCD4
0x18003bbce  lea     edx, [r15+10h]; uiParam
0x18003bbd2  xor     eax, eax
0x18003bbd4  lea     ecx, [rdx+32h]; uiAction
0x18003bbd7  mov     [rsp+4F0h+pvParam], rdx
0x18003bbdc  xor     r9d, r9d; fWinIni
0x18003bbdf  mov     [rsp+4F0h+var_488], rax
0x18003bbe4  lea     r8, [rsp+4F0h+pvParam]; pvParam
0x18003bbe9  mov     edi, r15d
0x18003bbec  call    cs:__imp_SystemParametersInfoW
0x18003bbf2  test    eax, eax
0x18003bbf4  jnz     loc_18003BDE6
0x18003bbfa  mov     rcx, [rsp+4F0h+Sid]; Sid
0x18003bbff  lea     rdx, [rsp+4F0h+pvParam]; StringSid
0x18003bc04  or      eax, 0FFFFFFFFh
0x18003bc07  mov     [rsp+4F0h+pvParam], r15
0x18003bc0c  test    sil, sil
0x18003bc0f  mov     r14d, edi
0x18003bc12  cmovnz  r14d, eax
0x18003bc16  call    cs:__imp_ConvertSidToStringSidW
0x18003bc1c  test    eax, eax
0x18003bc1e  jz      loc_18003BDD4
0x18003bc24  mov     rcx, [rsp+4F0h+pvParam]
0x18003bc29  lea     rax, aColors; "Colors"
0x18003bc30  mov     [rsp+4F0h+lpSecurityAttributes], rax
0x18003bc35  lea     r9, aSoftwareMicros_10; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18003bc3c  mov     rax, cs:off_18009E008; "AnyoneRead"
0x18003bc43  lea     r8, aSSSS; "%s\\%s\\%s\\%s"
0x18003bc4a  mov     qword ptr [rsp+4F0h+samDesired], rax
0x18003bc4f  mov     ebx, 104h
0x18003bc54  mov     qword ptr [rsp+4F0h+dwOptions], rcx
0x18003bc59  mov     edx, ebx; unsigned __int64
0x18003bc5b  lea     rcx, [rbp+3F0h+SubKey]; unsigned __int16 *
0x18003bc62  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003bc67  test    eax, eax
0x18003bc69  js      short loc_18003BCB5
0x18003bc6b  mov     rdx, cs:off_1800A07D8; "D:(A;CIOI;KA;;;SY)(A;CIOI;KA;;;LA)(A;CI"...
0x18003bc72  lea     rax, [rbp+3F0h+StringSecurityDescriptor]
0x18003bc76  mov     [rsp+4F0h+hKey], r15
0x18003bc7b  mov     ecx, 7FFFFFFEh
0x18003bc80  test    rcx, rcx
0x18003bc83  jz      short loc_18003BCA4
0x18003bc85  movzx   r8d, word ptr [rdx]
0x18003bc89  test    r8w, r8w
0x18003bc8d  jz      short loc_18003BCA4
0x18003bc8f  mov     [rax], r8w
0x18003bc93  add     rdx, 2
0x18003bc97  add     rax, 2
0x18003bc9b  dec     rcx
0x18003bc9e  sub     rbx, 1
0x18003bca2  jnz     short loc_18003BC80
0x18003bca4  test    rbx, rbx
0x18003bca7  lea     rcx, [rax-2]
0x18003bcab  cmovnz  rcx, rax
0x18003bcaf  mov     [rcx], r15w
0x18003bcb3  jnz     short loc_18003BCF3
0x18003bcb5  mov     rcx, [rsp+4F0h+pvParam]; hMem
0x18003bcba  call    cs:__imp_LocalFree
0x18003bcc0  test    sil, sil
0x18003bcc3  jz      loc_18003BDF3
0x18003bcc9  mov     rcx, [rsp+4F0h+Sid]; hMem
0x18003bcce  call    cs:__imp_LocalFree
0x18003bcd4  mov     rcx, [rbp+3F0h+var_40]
0x18003bcdb  xor     rcx, rsp; StackCookie
0x18003bcde  call    __security_check_cookie
0x18003bce3  add     rsp, 4C8h
0x18003bcea  pop     r15
0x18003bcec  pop     r14
0x18003bcee  pop     rdi
0x18003bcef  pop     rsi
0x18003bcf0  pop     rbx
0x18003bcf1  pop     rbp
0x18003bcf2  retn
0x18003bcf3  xor     r9d, r9d; SecurityDescriptorSize
0x18003bcf6  mov     [rsp+4F0h+SecurityDescriptor], r15
0x18003bcfb  lea     r8, [rsp+4F0h+SecurityDescriptor]; SecurityDescriptor
0x18003bd00  lea     rcx, [rbp+3F0h+StringSecurityDescriptor]; StringSecurityDescriptor
0x18003bd04  lea     edx, [r9+1]; StringSDRevision
0x18003bd08  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18003bd0e  mov     ecx, eax; int
0x18003bd10  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x18003bd15  test    eax, eax
0x18003bd17  js      short loc_18003BCB5
0x18003bd19  mov     rax, [rsp+4F0h+SecurityDescriptor]
0x18003bd1e  lea     r9, sourceString; lpClass
0x18003bd25  mov     [rsp+4F0h+lpdwDisposition], r15; lpdwDisposition
0x18003bd2a  lea     rdx, [rbp+3F0h+SubKey]; lpSubKey
0x18003bd31  mov     [rbp+3F0h+SecurityAttributes.lpSecurityDescriptor], rax
0x18003bd35  xor     r8d, r8d; Reserved
0x18003bd38  lea     rax, [rsp+4F0h+hKey]
0x18003bd3d  mov     qword ptr [rsp+4F0h+SecurityAttributes.nLength], 18h
0x18003bd46  mov     [rsp+4F0h+phkResult], rax; phkResult
0x18003bd4b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003bd52  lea     rax, [rsp+4F0h+SecurityAttributes]
0x18003bd57  mov     qword ptr [rbp+3F0h+SecurityAttributes.bInheritHandle], r15
0x18003bd5b  mov     [rsp+4F0h+lpSecurityAttributes], rax; lpSecurityAttributes
0x18003bd60  mov     [rsp+4F0h+samDesired], 2001Fh; samDesired
0x18003bd68  mov     [rsp+4F0h+dwOptions], r15d; dwOptions
0x18003bd6d  call    cs:__imp_RegCreateKeyExW
0x18003bd73  mov     ebx, eax
0x18003bd75  test    eax, eax
0x18003bd77  jle     short loc_18003BD82
0x18003bd79  movzx   ebx, ax
0x18003bd7c  or      ebx, 80070000h
0x18003bd82  mov     rcx, [rsp+4F0h+SecurityDescriptor]; hMem
0x18003bd87  call    cs:__imp_LocalFree
0x18003bd8d  test    ebx, ebx
0x18003bd8f  js      loc_18003BCB5
0x18003bd95  mov     rcx, [rsp+4F0h+hKey]; hKey
0x18003bd9a  lea     rax, [rsp+4F0h+SecurityDescriptor]
0x18003bd9f  mov     r9d, 4; dwType
0x18003bda5  mov     dword ptr [rsp+4F0h+SecurityDescriptor], r14d
0x18003bdaa  mov     [rsp+4F0h+samDesired], r9d; cbData
0x18003bdaf  lea     rdx, aHighcontrasten_0; "HighContrastEnabledNew"
0x18003bdb6  xor     r8d, r8d; Reserved
0x18003bdb9  mov     qword ptr [rsp+4F0h+dwOptions], rax; lpData
0x18003bdbe  call    cs:__imp_RegSetValueExW
0x18003bdc4  mov     rcx, [rsp+4F0h+hKey]; hKey
0x18003bdc9  call    cs:__imp_RegCloseKey
0x18003bdcf  jmp     loc_18003BCB5
0x18003bdd4  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18003bdd9  test    eax, eax
0x18003bddb  jns     loc_18003BC24
0x18003bde1  jmp     loc_18003BCC0
0x18003bde6  movzx   edi, byte ptr [rsp+4F0h+pvParam+4]
0x18003bdeb  and     edi, 1
0x18003bdee  jmp     loc_18003BBFA
0x18003bdf3  mov     rcx, [rsp+4F0h+Sid]
0x18003bdf8  lea     r8, aHighcontrasten; "HighContrastEnabled"
0x18003bdff  mov     [rsp+4F0h+dwOptions], edi
0x18003be03  call    ?_WriteSystemDataRegistryDWORDForUser@@YAJPEAXPEBG1W4SYSTEM_DATA_REGKEY_USER_ACCESS@@K_N@Z; _WriteSystemDataRegistryDWORDForUser(void *,ushort const *,ushort const *,SYSTEM_DATA_REGKEY_USER_ACCESS,ulong,bool)
0x18003be08  jmp     loc_18003BCC9
```
