# InitSecDescriptors

- ea: `0x180076340`
- end: `0x180076491`
- name: `InitSecDescriptors`
- size: `337`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180076610`
- `0x180076820`

## callees

- `0x180075f90`
- `0x180076340`
- `0x180076ce8`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800763bf`
- `KERNEL32!GetLastError` at `0x18007641f`
- `KERNEL32!GetLastError` at `0x1800763bf`
- `KERNEL32!GetLastError` at `0x18007641f`
- `KERNEL32!LocalFree` at `0x18007644a`
- `KERNEL32!LocalFree` at `0x18007646d`
- `KERNEL32!LocalFree` at `0x18007644a`
- `KERNEL32!LocalFree` at `0x18007646d`
- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800763af`
- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18007640f`
- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800763af`
- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18007640f`

## string_xrefs

- `0x18007637d`: `Failed to obtain necessary privileges\n`

## pseudocode

```c
__int64 InitSecDescriptors()
{
  DWORD v1; // ebx
  DWORD LastError; // eax
  int v3; // r8d
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+40h] [rbp+8h] BYREF
  PSECURITY_DESCRIPTOR hMem; // [rsp+48h] [rbp+10h] BYREF

  SecurityDescriptor = 0;
  hMem = 0;
  if ( g_bSecDescInitialized )
    return 0;
  v1 = EnableNecessaryPrivileges();
  if ( v1 )
  {
    dprintf(
      5,
      (unsigned int)L"onecore\\base\\subsys\\sm\\sfc\\wrpdisable\\wrpdisable.c",
      74,
      (unsigned int)L"Failed to obtain necessary privileges\n");
  }
  else
  {
    if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(L"O:BA", 1u, &SecurityDescriptor, 0) )
    {
      if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(
             L"O:BAG:BAD:(A;CIOI;GA;;;BA)(A;CIOI;GA;;;SY)(A;CIOI;GRGX;;;LS)(A;CIOI;GRGX;;;NS)(A;CIOI;GRGX;;;BU)(A;CIOI;GRG"
              "X;;;AC)(A;CIOI;GRGX;;;S-1-15-2-2)",
             1u,
             &hMem,
             0) )
      {
        if ( _InterlockedCompareExchange64((volatile signed __int64 *)&TempSd, (signed __int64)SecurityDescriptor, 0) )
          LocalFree(SecurityDescriptor);
        if ( _InterlockedCompareExchange64((volatile signed __int64 *)&TempSd2, (signed __int64)hMem, 0) )
          LocalFree(hMem);
        g_bSecDescInitialized = 1;
        return v1;
      }
      LastError = GetLastError();
      v3 = 102;
    }
    else
    {
      LastError = GetLastError();
      v3 = 88;
    }
    v1 = LastError;
    dprintf(
      5,
      (unsigned int)L"onecore\\base\\subsys\\sm\\sfc\\wrpdisable\\wrpdisable.c",
      v3,
      (unsigned int)L"Error %08d converting sddl [%ws]\n");
  }
  return v1;
}

```

## disassembly

```asm
0x180076340  mov     [rsp+arg_10], rbx
0x180076345  push    rbp
0x180076346  sub     rsp, 30h
0x18007634a  cmp     cs:g_bSecDescInitialized, 0
0x180076351  mov     [rsp+38h+SecurityDescriptor], 0
0x18007635a  mov     [rsp+38h+hMem], 0
0x180076363  jz      short loc_18007636C
0x180076365  xor     eax, eax
0x180076367  jmp     loc_180076485
0x18007636c  call    EnableNecessaryPrivileges
0x180076371  mov     ebx, eax
0x180076373  test    eax, eax
0x180076375  jz      short loc_180076399
0x180076377  mov     r8d, 4Ah ; 'J'
0x18007637d  lea     r9, aFailedToObtain; "Failed to obtain necessary privileges\n"
0x180076384  lea     rdx, aOnecoreBaseSub; "onecore\\base\\subsys\\sm\\sfc\\wrpdisa"...
0x18007638b  lea     ecx, [r8-45h]
0x18007638f  call    dprintf
0x180076394  jmp     loc_180076483
0x180076399  xor     r9d, r9d; SecurityDescriptorSize
0x18007639c  lea     rbp, StringSecurityDescriptor; "O:BA"
0x1800763a3  lea     r8, [rsp+38h+SecurityDescriptor]; SecurityDescriptor
0x1800763a8  mov     rcx, rbp; StringSecurityDescriptor
0x1800763ab  lea     edx, [r9+1]; StringSDRevision
0x1800763af  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800763b6  nop     dword ptr [rax+rax+00h]
0x1800763bb  test    eax, eax
0x1800763bd  jnz     short loc_1800763F9
0x1800763bf  call    cs:__imp_GetLastError
0x1800763c6  nop     dword ptr [rax+rax+00h]
0x1800763cb  mov     r8d, 58h ; 'X'
0x1800763d1  mov     [rsp+38h+var_10], rbp
0x1800763d6  lea     r9, aError08dConver; "Error %08d converting sddl [%ws]\n"
0x1800763dd  lea     rdx, aOnecoreBaseSub; "onecore\\base\\subsys\\sm\\sfc\\wrpdisa"...
0x1800763e4  mov     [rsp+38h+var_18], eax
0x1800763e8  mov     ecx, 5
0x1800763ed  mov     ebx, eax
0x1800763ef  call    dprintf
0x1800763f4  jmp     loc_180076483
0x1800763f9  xor     r9d, r9d; SecurityDescriptorSize
0x1800763fc  lea     rbp, aOBagBadACioiGa; "O:BAG:BAD:(A;CIOI;GA;;;BA)(A;CIOI;GA;;;"...
0x180076403  lea     r8, [rsp+38h+hMem]; SecurityDescriptor
0x180076408  mov     rcx, rbp; StringSecurityDescriptor
0x18007640b  lea     edx, [r9+1]; StringSDRevision
0x18007640f  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180076416  nop     dword ptr [rax+rax+00h]
0x18007641b  test    eax, eax
0x18007641d  jnz     short loc_180076433
0x18007641f  call    cs:__imp_GetLastError
0x180076426  nop     dword ptr [rax+rax+00h]
0x18007642b  mov     r8d, 66h ; 'f'
0x180076431  jmp     short loc_1800763D1
0x180076433  mov     rcx, [rsp+38h+SecurityDescriptor]
0x180076438  xor     eax, eax
0x18007643a  lock cmpxchg cs:TempSd, rcx
0x180076443  jz      short loc_180076456
0x180076445  mov     rcx, [rsp+38h+SecurityDescriptor]; hMem
0x18007644a  call    cs:__imp_LocalFree
0x180076451  nop     dword ptr [rax+rax+00h]
0x180076456  mov     rcx, [rsp+38h+hMem]
0x18007645b  xor     eax, eax
0x18007645d  lock cmpxchg cs:TempSd2, rcx
0x180076466  jz      short loc_180076479
0x180076468  mov     rcx, [rsp+38h+hMem]; hMem
0x18007646d  call    cs:__imp_LocalFree
0x180076474  nop     dword ptr [rax+rax+00h]
0x180076479  mov     cs:g_bSecDescInitialized, 1
0x180076483  mov     eax, ebx
0x180076485  mov     rbx, [rsp+38h+arg_10]
0x18007648a  add     rsp, 30h
0x18007648e  pop     rbp
0x18007648f  retn
```
