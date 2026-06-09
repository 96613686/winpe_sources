# WriteACLToSetupLog

- ea: `0x18027d284`
- end: `0x18027d2d8`
- name: `WriteACLToSetupLog`
- size: `84`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800b83f4`
- `0x18027d110`
- `0x180373d50`

## callees

- `0x18027d284`
- `0x18027d2e0`
- `0x18027d4e0`
- `0x1803a4cb0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180654dde`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180654dde`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180654edb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180654edb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180654df3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180654df3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180654eaf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180654ed2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180654eaf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180654ed2`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180654da1`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180654da1`
- `api-ms-win-security-base-l1-1-0!QuerySecurityAccessMask` at `0x180654d76`
- `api-ms-win-security-base-l1-1-0!QuerySecurityAccessMask` at `0x180654d76`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x180654dd0`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x180654e1b`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x180654dd0`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x180654e1b`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180654e4e`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180654e4e`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x180654e8e`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x180654e8e`

## string_xrefs

- `0x180654eea`: `%s: Unable to open to get Dacl\n`
- `0x180654ec0`: `%s: Null Dacl\n`
- `0x180654e5e`: `%s: No Dacl\n`
- `0x180654eb7`: `%s: Failed to convert Dacl to Sddl\n`
- `0x180654e9f`: `%s: Dacl: %s\n`

## pseudocode

```c
int __fastcall WriteACLToSetupLog(LPCWSTR lpFileName)
{
  int result; // eax
  HANDLE FileW; // rsi
  HLOCAL v4; // rdi
  const wchar_t *v5; // rcx
  DWORD nLengthNeeded; // [rsp+40h] [rbp-30h] BYREF
  DWORD DesiredAccess; // [rsp+44h] [rbp-2Ch] BYREF
  LPWSTR StringSecurityDescriptor; // [rsp+48h] [rbp-28h] BYREF
  PACL pDacl; // [rsp+50h] [rbp-20h] BYREF
  WINBOOL bDaclPresent; // [rsp+58h] [rbp-18h] BYREF
  WINBOOL bDaclDefaulted; // [rsp+5Ch] [rbp-14h] BYREF

  result = IsGuimodeSetupRunning();
  if ( result )
  {
    DesiredAccess = 0;
    QuerySecurityAccessMask(7u, &DesiredAccess);
    FileW = CreateFileW(lpFileName, DesiredAccess, 7u, 0, 3u, 0, 0);
    if ( FileW != (HANDLE)-1LL )
    {
      nLengthNeeded = 0;
      if ( GetKernelObjectSecurity(FileW, 7u, 0, 0, &nLengthNeeded) )
        return CloseHandle(FileW);
      if ( GetLastError() != 122 )
        return CloseHandle(FileW);
      v4 = LocalAlloc(0x40u, nLengthNeeded);
      if ( !v4 )
        return CloseHandle(FileW);
      if ( GetKernelObjectSecurity(FileW, 7u, v4, nLengthNeeded, &nLengthNeeded) )
      {
        bDaclPresent = 0;
        bDaclDefaulted = 0;
        pDacl = 0;
        if ( GetSecurityDescriptorDacl(v4, &bDaclPresent, &pDacl, &bDaclDefaulted) )
        {
          if ( bDaclPresent )
          {
            if ( pDacl )
            {
              StringSecurityDescriptor = 0;
              if ( ConvertSecurityDescriptorToStringSecurityDescriptorW(v4, 1u, 7u, &StringSecurityDescriptor, 0) )
              {
                WriteSetupErrorLogEntry(L"%s: Dacl: %s\n", lpFileName, StringSecurityDescriptor);
                LocalFree(StringSecurityDescriptor);
              }
              else
              {
                WriteSetupErrorLogEntry(L"%s: Failed to convert Dacl to Sddl\n", lpFileName);
              }
              goto LABEL_16;
            }
            v5 = L"%s: Null Dacl\n";
          }
          else
          {
            v5 = L"%s: No Dacl\n";
          }
          WriteSetupErrorLogEntry(v5, lpFileName);
        }
      }
LABEL_16:
      LocalFree(v4);
      return CloseHandle(FileW);
    }
    return WriteSetupErrorLogEntry(L"%s: Unable to open to get Dacl\n", lpFileName);
  }
  return result;
}

```

## disassembly

```asm
0x18027d284  mov     [rsp-18h+arg_8], rbx
0x18027d289  mov     [rsp-18h+arg_10], rsi
0x18027d28e  push    rbp
0x18027d28f  push    rdi
0x18027d290  push    r15
0x18027d292  mov     rbp, rsp
0x18027d295  sub     rsp, 70h
0x18027d299  mov     rax, cs:__security_cookie
0x18027d2a0  xor     rax, rsp
0x18027d2a3  mov     [rbp+var_10], rax
0x18027d2a7  mov     rbx, rcx
0x18027d2aa  call    IsGuimodeSetupRunning
0x18027d2af  test    eax, eax
0x18027d2b1  jnz     loc_180654D62
0x18027d2b7  mov     rcx, [rbp+var_10]
0x18027d2bb  xor     rcx, rsp; StackCookie
0x18027d2be  call    __security_check_cookie
0x18027d2c3  lea     r11, [rsp+70h+var_s0]
0x18027d2c8  mov     rbx, [r11+28h]
0x18027d2cc  mov     rsi, [r11+30h]
0x18027d2d0  mov     rsp, r11
0x18027d2d3  pop     r15
0x18027d2d5  pop     rdi
0x18027d2d6  pop     rbp
0x18027d2d7  retn
0x180654d62  mov     r15d, 7
0x180654d68  mov     [rbp+DesiredAccess], 0
0x180654d6f  mov     ecx, r15d; SecurityInformation
0x180654d72  lea     rdx, [rbp+DesiredAccess]; DesiredAccess
0x180654d76  call    cs:__imp_QuerySecurityAccessMask
0x180654d7c  mov     edx, [rbp+DesiredAccess]; dwDesiredAccess
0x180654d7f  xor     r9d, r9d; lpSecurityAttributes
0x180654d82  mov     [rsp+70h+hTemplateFile], 0; hTemplateFile
0x180654d8b  mov     r8d, r15d; dwShareMode
0x180654d8e  mov     [rsp+70h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x180654d96  mov     rcx, rbx; lpFileName
0x180654d99  mov     [rsp+70h+dwCreationDisposition], 3; dwCreationDisposition
0x180654da1  call    cs:__imp_CreateFileW
0x180654da7  mov     rsi, rax
0x180654daa  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180654dae  jz      loc_180654EE7
0x180654db4  lea     rax, [rbp+nLengthNeeded]
0x180654db8  mov     [rbp+nLengthNeeded], 0
0x180654dbf  xor     r9d, r9d; nLength
0x180654dc2  mov     qword ptr [rsp+70h+dwCreationDisposition], rax; lpnLengthNeeded
0x180654dc7  xor     r8d, r8d; pSecurityDescriptor
0x180654dca  mov     edx, r15d; RequestedInformation
0x180654dcd  mov     rcx, rsi; Handle
0x180654dd0  call    cs:__imp_GetKernelObjectSecurity
0x180654dd6  test    eax, eax
0x180654dd8  jnz     loc_180654ED8
0x180654dde  call    cs:__imp_GetLastError
0x180654de4  cmp     eax, 7Ah ; 'z'
0x180654de7  jnz     loc_180654ED8
0x180654ded  mov     edx, [rbp+nLengthNeeded]; uBytes
0x180654df0  lea     ecx, [rax-3Ah]; uFlags
0x180654df3  call    cs:__imp_LocalAlloc
0x180654df9  mov     rdi, rax
0x180654dfc  test    rax, rax
0x180654dff  jz      loc_180654ED8
0x180654e05  mov     r9d, [rbp+nLengthNeeded]; nLength
0x180654e09  lea     rax, [rbp+nLengthNeeded]
0x180654e0d  mov     r8, rdi; pSecurityDescriptor
0x180654e10  mov     qword ptr [rsp+70h+dwCreationDisposition], rax; lpnLengthNeeded
0x180654e15  mov     edx, r15d; RequestedInformation
0x180654e18  mov     rcx, rsi; Handle
0x180654e1b  call    cs:__imp_GetKernelObjectSecurity
0x180654e21  test    eax, eax
0x180654e23  jz      loc_180654ECF
0x180654e29  lea     r9, [rbp+bDaclDefaulted]; lpbDaclDefaulted
0x180654e2d  mov     [rbp+bDaclPresent], 0
0x180654e34  lea     r8, [rbp+pDacl]; pDacl
0x180654e38  mov     [rbp+bDaclDefaulted], 0
0x180654e3f  lea     rdx, [rbp+bDaclPresent]; lpbDaclPresent
0x180654e43  mov     [rbp+pDacl], 0
0x180654e4b  mov     rcx, rdi; pSecurityDescriptor
0x180654e4e  call    cs:__imp_GetSecurityDescriptorDacl
0x180654e54  test    eax, eax
0x180654e56  jz      short loc_180654ECF
0x180654e58  cmp     [rbp+bDaclPresent], 0
0x180654e5c  jnz     short loc_180654E67
0x180654e5e  lea     rcx, aSNoDacl; "%s: No Dacl\n"
0x180654e65  jmp     short loc_180654EC7
0x180654e67  cmp     [rbp+pDacl], 0
0x180654e6c  jz      short loc_180654EC0
0x180654e6e  lea     r9, [rbp+StringSecurityDescriptor]; StringSecurityDescriptor
0x180654e72  mov     [rbp+StringSecurityDescriptor], 0
0x180654e7a  mov     r8d, r15d; SecurityInformation
0x180654e7d  mov     qword ptr [rsp+70h+dwCreationDisposition], 0; StringSecurityDescriptorLen
0x180654e86  mov     edx, 1; RequestedStringSDRevision
0x180654e8b  mov     rcx, rdi; SecurityDescriptor
0x180654e8e  call    cs:__imp_ConvertSecurityDescriptorToStringSecurityDescriptorW
0x180654e94  mov     rdx, rbx
0x180654e97  test    eax, eax
0x180654e99  jz      short loc_180654EB7
0x180654e9b  mov     r8, [rbp+StringSecurityDescriptor]
0x180654e9f  lea     rcx, aSDaclS; "%s: Dacl: %s\n"
0x180654ea6  call    WriteSetupErrorLogEntry
0x180654eab  mov     rcx, [rbp+StringSecurityDescriptor]; hMem
0x180654eaf  call    cs:__imp_LocalFree
0x180654eb5  jmp     short loc_180654ECF
0x180654eb7  lea     rcx, aSFailedToConve; "%s: Failed to convert Dacl to Sddl\n"
0x180654ebe  jmp     short loc_180654ECA
0x180654ec0  lea     rcx, aSNullDacl; "%s: Null Dacl\n"
0x180654ec7  mov     rdx, rbx
0x180654eca  call    WriteSetupErrorLogEntry
0x180654ecf  mov     rcx, rdi; hMem
0x180654ed2  call    cs:__imp_LocalFree
0x180654ed8  mov     rcx, rsi; hObject
0x180654edb  call    cs:__imp_CloseHandle
0x180654ee1  nop
0x180654ee2  jmp     loc_18027D2B7
0x180654ee7  mov     rdx, rbx
0x180654eea  lea     rcx, aSUnableToOpenT; "%s: Unable to open to get Dacl\n"
0x180654ef1  call    WriteSetupErrorLogEntry
0x180654ef6  nop
0x180654ef7  jmp     loc_18027D2B7
```
