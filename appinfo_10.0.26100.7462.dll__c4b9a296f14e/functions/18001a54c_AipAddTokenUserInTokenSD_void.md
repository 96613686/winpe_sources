# AipAddTokenUserInTokenSD(void *)

- ea: `0x18001a54c`
- end: `0x18001a7fd`
- name: `?AipAddTokenUserInTokenSD@@YAKPEAX@Z`
- size: `689`
- prototype: `unsigned int __fastcall(HANDLE Handle)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18003e5d4`

## callees

- `0x180019c28`
- `0x18001a54c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a61f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a61f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a791`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a7a1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a7b1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a7c0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a7d0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a7df`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a791`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a7a1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a7b1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a7c0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a7d0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a7df`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001a5af`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001a664`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001a6f6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001a5af`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001a664`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001a6f6`
- `ntdll!NtQueryInformationToken` at `0x18001a645`
- `ntdll!NtQueryInformationToken` at `0x18001a692`
- `ntdll!NtQueryInformationToken` at `0x18001a645`
- `ntdll!NtQueryInformationToken` at `0x18001a692`
- `ntdll!NtSetSecurityObject` at `0x18001a76e`
- `ntdll!NtSetSecurityObject` at `0x18001a76e`
- `ntdll!NtQuerySecurityObject` at `0x18001a592`
- `ntdll!NtQuerySecurityObject` at `0x18001a5e3`
- `ntdll!NtQuerySecurityObject` at `0x18001a592`
- `ntdll!NtQuerySecurityObject` at `0x18001a5e3`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18001a780`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18001a780`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x18001a60f`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x18001a60f`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18001a74e`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18001a74e`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18001a6ad`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18001a6ad`

## pseudocode

```c
__int64 __fastcall AipAddTokenUserInTokenSD(HANDLE Handle)
{
  unsigned int v1; // ebx
  HLOCAL v3; // r14
  WCHAR *v4; // rsi
  PSID *v5; // rdi
  int v6; // eax
  DWORD LastError; // eax
  __int64 v8; // rax
  __int64 v9; // rdx
  unsigned __int16 *v10; // rax
  LPWSTR StringSid; // [rsp+30h] [rbp-10h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+38h] [rbp-8h] BYREF
  ULONG Length; // [rsp+88h] [rbp+48h] BYREF
  ULONG ReturnLength; // [rsp+90h] [rbp+50h] BYREF
  LPWSTR StringSecurityDescriptor; // [rsp+98h] [rbp+58h] BYREF

  v1 = 0;
  Length = 0;
  SecurityDescriptor = 0;
  StringSecurityDescriptor = 0;
  StringSid = 0;
  ReturnLength = 0;
  v3 = 0;
  v4 = 0;
  v5 = 0;
  v6 = NtQuerySecurityObject(Handle, 4u, 0, 0, &Length);
  if ( v6 != -1073741789 )
    goto LABEL_18;
  v3 = LocalAlloc(0x40u, Length);
  if ( v3 )
  {
    v6 = NtQuerySecurityObject(Handle, 4u, v3, Length, &Length);
    if ( v6 >= 0 )
    {
      if ( !ConvertSecurityDescriptorToStringSecurityDescriptorW(v3, 1u, 4u, &StringSecurityDescriptor, 0) )
      {
LABEL_6:
        LastError = GetLastError();
LABEL_19:
        v1 = LastError;
        goto LABEL_20;
      }
      v6 = NtQueryInformationToken(Handle, TokenUser, 0, 0, &ReturnLength);
      if ( v6 == -1073741789 )
      {
        v5 = (PSID *)LocalAlloc(0x40u, ReturnLength);
        if ( !v5 )
          goto LABEL_3;
        v6 = NtQueryInformationToken(Handle, TokenUser, v5, ReturnLength, &ReturnLength);
        if ( v6 >= 0 )
        {
          if ( !ConvertSidToStringSidW(*v5, &StringSid) )
            goto LABEL_6;
          v8 = -1;
          v9 = -1;
          do
            ++v9;
          while ( StringSid[v9] );
          do
            ++v8;
          while ( StringSecurityDescriptor[v8] );
          Length = 2 * (v8 + v9) + 24;
          v10 = (unsigned __int16 *)LocalAlloc(0x40u, Length);
          v4 = v10;
          if ( !v10
            || (int)StringCbPrintfW(v10, Length, L"%s%s%s)", StringSecurityDescriptor, L"(A;;0xe;;;", StringSid) < 0 )
          {
            goto LABEL_3;
          }
          if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(v4, 1u, &SecurityDescriptor, 0) )
            goto LABEL_6;
          v6 = NtSetSecurityObject(Handle, 4u, SecurityDescriptor);
          if ( v6 >= 0 )
            goto LABEL_20;
        }
      }
    }
LABEL_18:
    LastError = RtlNtStatusToDosErrorNoTeb(v6);
    goto LABEL_19;
  }
LABEL_3:
  v1 = 8;
LABEL_20:
  LocalFree(v3);
  LocalFree(StringSecurityDescriptor);
  LocalFree(StringSid);
  LocalFree(v4);
  LocalFree(SecurityDescriptor);
  LocalFree(v5);
  return v1;
}

```

## disassembly

```asm
0x18001a54c  push    rbp
0x18001a54e  push    rbx
0x18001a54f  push    rsi
0x18001a550  push    rdi
0x18001a551  push    r13
0x18001a553  push    r14
0x18001a555  push    r15
0x18001a557  mov     rbp, rsp
0x18001a55a  sub     rsp, 40h
0x18001a55e  xor     ebx, ebx
0x18001a560  lea     rax, [rbp+Length]
0x18001a564  xor     r9d, r9d; Length
0x18001a567  mov     [rbp+Length], ebx
0x18001a56a  xor     r8d, r8d; SecurityDescriptor
0x18001a56d  mov     [rbp+SecurityDescriptor], rbx
0x18001a571  mov     r15, rcx
0x18001a574  mov     [rbp+StringSecurityDescriptor], rbx
0x18001a578  lea     r13d, [rbx+4]
0x18001a57c  mov     [rbp+StringSid], rbx
0x18001a580  mov     edx, r13d; SecurityInformation
0x18001a583  mov     [rbp+ReturnLength], ebx
0x18001a586  mov     r14d, ebx
0x18001a589  mov     [rsp+40h+LengthNeeded], rax; LengthNeeded
0x18001a58e  mov     esi, ebx
0x18001a590  mov     edi, ebx
0x18001a592  call    cs:__imp_NtQuerySecurityObject
0x18001a599  nop     dword ptr [rax+rax+00h]
0x18001a59e  cmp     eax, 0C0000023h
0x18001a5a3  jnz     loc_18001A77E
0x18001a5a9  mov     edx, [rbp+Length]; uBytes
0x18001a5ac  lea     ecx, [rbx+40h]; uFlags
0x18001a5af  call    cs:__imp_LocalAlloc
0x18001a5b6  nop     dword ptr [rax+rax+00h]
0x18001a5bb  mov     r14, rax
0x18001a5be  test    rax, rax
0x18001a5c1  jnz     short loc_18001A5CD
0x18001a5c3  mov     ebx, 8
0x18001a5c8  jmp     loc_18001A78E
0x18001a5cd  mov     r9d, [rbp+Length]; Length
0x18001a5d1  lea     rax, [rbp+Length]
0x18001a5d5  mov     r8, r14; SecurityDescriptor
0x18001a5d8  mov     [rsp+40h+LengthNeeded], rax; LengthNeeded
0x18001a5dd  mov     edx, r13d; SecurityInformation
0x18001a5e0  mov     rcx, r15; Handle
0x18001a5e3  call    cs:__imp_NtQuerySecurityObject
0x18001a5ea  nop     dword ptr [rax+rax+00h]
0x18001a5ef  test    eax, eax
0x18001a5f1  js      loc_18001A77E
0x18001a5f7  mov     r8d, r13d; SecurityInformation
0x18001a5fa  mov     [rsp+40h+LengthNeeded], rbx; StringSecurityDescriptorLen
0x18001a5ff  mov     r13d, 1
0x18001a605  lea     r9, [rbp+StringSecurityDescriptor]; StringSecurityDescriptor
0x18001a609  mov     edx, r13d; RequestedStringSDRevision
0x18001a60c  mov     rcx, r14; SecurityDescriptor
0x18001a60f  call    cs:__imp_ConvertSecurityDescriptorToStringSecurityDescriptorW
0x18001a616  nop     dword ptr [rax+rax+00h]
0x18001a61b  test    eax, eax
0x18001a61d  jnz     short loc_18001A630
0x18001a61f  call    cs:__imp_GetLastError
0x18001a626  nop     dword ptr [rax+rax+00h]
0x18001a62b  jmp     loc_18001A78C
0x18001a630  lea     rax, [rbp+ReturnLength]
0x18001a634  xor     r9d, r9d; TokenInformationLength
0x18001a637  xor     r8d, r8d; TokenInformation
0x18001a63a  mov     [rsp+40h+LengthNeeded], rax; ReturnLength
0x18001a63f  mov     edx, r13d; TokenInformationClass
0x18001a642  mov     rcx, r15; TokenHandle
0x18001a645  call    cs:__imp_NtQueryInformationToken
0x18001a64c  nop     dword ptr [rax+rax+00h]
0x18001a651  cmp     eax, 0C0000023h
0x18001a656  jnz     loc_18001A77E
0x18001a65c  mov     edx, [rbp+ReturnLength]; uBytes
0x18001a65f  mov     ecx, 40h ; '@'; uFlags
0x18001a664  call    cs:__imp_LocalAlloc
0x18001a66b  nop     dword ptr [rax+rax+00h]
0x18001a670  mov     rdi, rax
0x18001a673  test    rax, rax
0x18001a676  jz      loc_18001A5C3
0x18001a67c  mov     r9d, [rbp+ReturnLength]; TokenInformationLength
0x18001a680  lea     rax, [rbp+ReturnLength]
0x18001a684  mov     r8, rdi; TokenInformation
0x18001a687  mov     [rsp+40h+LengthNeeded], rax; ReturnLength
0x18001a68c  mov     edx, r13d; TokenInformationClass
0x18001a68f  mov     rcx, r15; TokenHandle
0x18001a692  call    cs:__imp_NtQueryInformationToken
0x18001a699  nop     dword ptr [rax+rax+00h]
0x18001a69e  test    eax, eax
0x18001a6a0  js      loc_18001A77E
0x18001a6a6  mov     rcx, [rdi]; Sid
0x18001a6a9  lea     rdx, [rbp+StringSid]; StringSid
0x18001a6ad  call    cs:__imp_ConvertSidToStringSidW
0x18001a6b4  nop     dword ptr [rax+rax+00h]
0x18001a6b9  test    eax, eax
0x18001a6bb  jz      loc_18001A61F
0x18001a6c1  mov     rcx, [rbp+StringSid]
0x18001a6c5  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001a6c9  mov     rdx, rax
0x18001a6cc  inc     rdx
0x18001a6cf  cmp     [rcx+rdx*2], bx
0x18001a6d3  jnz     short loc_18001A6CC
0x18001a6d5  mov     r8, [rbp+StringSecurityDescriptor]
0x18001a6d9  inc     rax
0x18001a6dc  cmp     [r8+rax*2], bx
0x18001a6e1  jnz     short loc_18001A6D9
0x18001a6e3  add     edx, eax
0x18001a6e5  mov     ecx, 40h ; '@'; uFlags
0x18001a6ea  lea     eax, ds:18h[rdx*2]
0x18001a6f1  mov     edx, eax; uBytes
0x18001a6f3  mov     [rbp+Length], eax
0x18001a6f6  call    cs:__imp_LocalAlloc
0x18001a6fd  nop     dword ptr [rax+rax+00h]
0x18001a702  mov     rsi, rax
0x18001a705  test    rax, rax
0x18001a708  jz      loc_18001A5C3
0x18001a70e  mov     rax, [rbp+StringSid]
0x18001a712  lea     r8, aSSS; "%s%s%s)"
0x18001a719  mov     edx, [rbp+Length]; unsigned __int64
0x18001a71c  mov     rcx, rsi; unsigned __int16 *
0x18001a71f  mov     r9, [rbp+StringSecurityDescriptor]
0x18001a723  mov     [rsp+40h+var_18], rax
0x18001a728  lea     rax, aA0xe; "(A;;0xe;;;"
0x18001a72f  mov     [rsp+40h+LengthNeeded], rax
0x18001a734  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001a739  test    eax, eax
0x18001a73b  js      loc_18001A5C3
0x18001a741  xor     r9d, r9d; SecurityDescriptorSize
0x18001a744  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x18001a748  mov     edx, r13d; StringSDRevision
0x18001a74b  mov     rcx, rsi; StringSecurityDescriptor
0x18001a74e  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18001a755  nop     dword ptr [rax+rax+00h]
0x18001a75a  test    eax, eax
0x18001a75c  jz      loc_18001A61F
0x18001a762  mov     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x18001a766  mov     edx, 4; SecurityInformation
0x18001a76b  mov     rcx, r15; Handle
0x18001a76e  call    cs:__imp_NtSetSecurityObject
0x18001a775  nop     dword ptr [rax+rax+00h]
0x18001a77a  test    eax, eax
0x18001a77c  jns     short loc_18001A78E
0x18001a77e  mov     ecx, eax; Status
0x18001a780  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x18001a787  nop     dword ptr [rax+rax+00h]
0x18001a78c  mov     ebx, eax
0x18001a78e  mov     rcx, r14; hMem
0x18001a791  call    cs:__imp_LocalFree
0x18001a798  nop     dword ptr [rax+rax+00h]
0x18001a79d  mov     rcx, [rbp+StringSecurityDescriptor]; hMem
0x18001a7a1  call    cs:__imp_LocalFree
0x18001a7a8  nop     dword ptr [rax+rax+00h]
0x18001a7ad  mov     rcx, [rbp+StringSid]; hMem
0x18001a7b1  call    cs:__imp_LocalFree
0x18001a7b8  nop     dword ptr [rax+rax+00h]
0x18001a7bd  mov     rcx, rsi; hMem
0x18001a7c0  call    cs:__imp_LocalFree
0x18001a7c7  nop     dword ptr [rax+rax+00h]
0x18001a7cc  mov     rcx, [rbp+SecurityDescriptor]; hMem
0x18001a7d0  call    cs:__imp_LocalFree
0x18001a7d7  nop     dword ptr [rax+rax+00h]
0x18001a7dc  mov     rcx, rdi; hMem
0x18001a7df  call    cs:__imp_LocalFree
0x18001a7e6  nop     dword ptr [rax+rax+00h]
0x18001a7eb  mov     eax, ebx
0x18001a7ed  add     rsp, 40h
0x18001a7f1  pop     r15
0x18001a7f3  pop     r14
0x18001a7f5  pop     r13
0x18001a7f7  pop     rdi
0x18001a7f8  pop     rsi
0x18001a7f9  pop     rbx
0x18001a7fa  pop     rbp
0x18001a7fb  retn
```
