# InitSecDescriptors

- ea: `0x1800766b0`
- end: `0x180076801`
- name: `InitSecDescriptors`
- size: `337`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180076980`
- `0x180076b90`

## callees

- `0x180076300`
- `0x1800766b0`
- `0x180077058`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18007672f`
- `KERNEL32!GetLastError` at `0x18007678f`
- `KERNEL32!GetLastError` at `0x18007672f`
- `KERNEL32!GetLastError` at `0x18007678f`
- `KERNEL32!LocalFree` at `0x1800767ba`
- `KERNEL32!LocalFree` at `0x1800767dd`
- `KERNEL32!LocalFree` at `0x1800767ba`
- `KERNEL32!LocalFree` at `0x1800767dd`
- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18007671f`
- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18007677f`
- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18007671f`
- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18007677f`

## string_xrefs

- `0x1800766ed`: `Failed to obtain necessary privileges\n`

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
0x1800766b0  mov     [rsp+arg_10], rbx
0x1800766b5  push    rbp
0x1800766b6  sub     rsp, 30h
0x1800766ba  cmp     cs:g_bSecDescInitialized, 0
0x1800766c1  mov     [rsp+38h+SecurityDescriptor], 0
0x1800766ca  mov     [rsp+38h+hMem], 0
0x1800766d3  jz      short loc_1800766DC
0x1800766d5  xor     eax, eax
0x1800766d7  jmp     loc_1800767F5
0x1800766dc  call    EnableNecessaryPrivileges
0x1800766e1  mov     ebx, eax
0x1800766e3  test    eax, eax
0x1800766e5  jz      short loc_180076709
0x1800766e7  mov     r8d, 4Ah ; 'J'
0x1800766ed  lea     r9, aFailedToObtain; "Failed to obtain necessary privileges\n"
0x1800766f4  lea     rdx, aOnecoreBaseSub; "onecore\\base\\subsys\\sm\\sfc\\wrpdisa"...
0x1800766fb  lea     ecx, [r8-45h]
0x1800766ff  call    dprintf
0x180076704  jmp     loc_1800767F3
0x180076709  xor     r9d, r9d; SecurityDescriptorSize
0x18007670c  lea     rbp, StringSecurityDescriptor; "O:BA"
0x180076713  lea     r8, [rsp+38h+SecurityDescriptor]; SecurityDescriptor
0x180076718  mov     rcx, rbp; StringSecurityDescriptor
0x18007671b  lea     edx, [r9+1]; StringSDRevision
0x18007671f  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180076726  nop     dword ptr [rax+rax+00h]
0x18007672b  test    eax, eax
0x18007672d  jnz     short loc_180076769
0x18007672f  call    cs:__imp_GetLastError
0x180076736  nop     dword ptr [rax+rax+00h]
0x18007673b  mov     r8d, 58h ; 'X'
0x180076741  mov     [rsp+38h+var_10], rbp
0x180076746  lea     r9, aError08dConver; "Error %08d converting sddl [%ws]\n"
0x18007674d  lea     rdx, aOnecoreBaseSub; "onecore\\base\\subsys\\sm\\sfc\\wrpdisa"...
0x180076754  mov     [rsp+38h+var_18], eax
0x180076758  mov     ecx, 5
0x18007675d  mov     ebx, eax
0x18007675f  call    dprintf
0x180076764  jmp     loc_1800767F3
0x180076769  xor     r9d, r9d; SecurityDescriptorSize
0x18007676c  lea     rbp, aOBagBadACioiGa; "O:BAG:BAD:(A;CIOI;GA;;;BA)(A;CIOI;GA;;;"...
0x180076773  lea     r8, [rsp+38h+hMem]; SecurityDescriptor
0x180076778  mov     rcx, rbp; StringSecurityDescriptor
0x18007677b  lea     edx, [r9+1]; StringSDRevision
0x18007677f  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180076786  nop     dword ptr [rax+rax+00h]
0x18007678b  test    eax, eax
0x18007678d  jnz     short loc_1800767A3
0x18007678f  call    cs:__imp_GetLastError
0x180076796  nop     dword ptr [rax+rax+00h]
0x18007679b  mov     r8d, 66h ; 'f'
0x1800767a1  jmp     short loc_180076741
0x1800767a3  mov     rcx, [rsp+38h+SecurityDescriptor]
0x1800767a8  xor     eax, eax
0x1800767aa  lock cmpxchg cs:TempSd, rcx
0x1800767b3  jz      short loc_1800767C6
0x1800767b5  mov     rcx, [rsp+38h+SecurityDescriptor]; hMem
0x1800767ba  call    cs:__imp_LocalFree
0x1800767c1  nop     dword ptr [rax+rax+00h]
0x1800767c6  mov     rcx, [rsp+38h+hMem]
0x1800767cb  xor     eax, eax
0x1800767cd  lock cmpxchg cs:TempSd2, rcx
0x1800767d6  jz      short loc_1800767E9
0x1800767d8  mov     rcx, [rsp+38h+hMem]; hMem
0x1800767dd  call    cs:__imp_LocalFree
0x1800767e4  nop     dword ptr [rax+rax+00h]
0x1800767e9  mov     cs:g_bSecDescInitialized, 1
0x1800767f3  mov     eax, ebx
0x1800767f5  mov     rbx, [rsp+38h+arg_10]
0x1800767fa  add     rsp, 30h
0x1800767fe  pop     rbp
0x1800767ff  retn
```
