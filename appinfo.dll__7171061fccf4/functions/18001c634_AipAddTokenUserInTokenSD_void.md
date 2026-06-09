# AipAddTokenUserInTokenSD(void *)

- ea: `0x18001c634`
- end: `0x18001c87e`
- name: `?AipAddTokenUserInTokenSD@@YAKPEAX@Z`
- size: `586`
- prototype: `__int64 __fastcall(HANDLE Handle)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180040d64`

## callees

- `0x18001ba24`
- `0x18001c634`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c6f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c6f6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c837`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c841`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c84b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c854`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c85e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c867`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c837`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c841`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c84b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c854`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c85e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c867`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001c699`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001c72d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001c7b2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001c699`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001c72d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001c7b2`
- `ntdll!NtQueryInformationToken` at `0x18001c717`
- `ntdll!NtQueryInformationToken` at `0x18001c759`
- `ntdll!NtQueryInformationToken` at `0x18001c717`
- `ntdll!NtQueryInformationToken` at `0x18001c759`
- `ntdll!NtSetSecurityObject` at `0x18001c820`
- `ntdll!NtSetSecurityObject` at `0x18001c820`
- `ntdll!NtQuerySecurityObject` at `0x18001c67a`
- `ntdll!NtQuerySecurityObject` at `0x18001c6c9`
- `ntdll!NtQuerySecurityObject` at `0x18001c67a`
- `ntdll!NtQuerySecurityObject` at `0x18001c6c9`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18001c82c`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18001c82c`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18001c803`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18001c803`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x18001c6ec`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x18001c6ec`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18001c76e`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18001c76e`

## pseudocode

```c
__int64 __fastcall AipAddTokenUserInTokenSD(HANDLE Handle)
{
  WCHAR *v2; // rsi
  PSID *v3; // r15
  int v4; // eax
  HLOCAL v5; // rdi
  unsigned int v6; // ebx
  ULONG LastError; // eax
  __int64 v8; // rax
  __int64 v9; // rdx
  unsigned __int16 *v10; // rax
  LPWSTR StringSid; // [rsp+30h] [rbp-10h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+38h] [rbp-8h] BYREF
  ULONG Length; // [rsp+88h] [rbp+48h] BYREF
  ULONG ReturnLength; // [rsp+90h] [rbp+50h] BYREF
  LPWSTR StringSecurityDescriptor; // [rsp+98h] [rbp+58h] BYREF

  Length = 0;
  SecurityDescriptor = 0;
  StringSecurityDescriptor = 0;
  StringSid = 0;
  v2 = 0;
  ReturnLength = 0;
  v3 = 0;
  v4 = NtQuerySecurityObject(Handle, 4u, 0, 0, &Length);
  if ( v4 != -1073741789 )
  {
    v5 = 0;
LABEL_19:
    LastError = RtlNtStatusToDosErrorNoTeb(v4);
    goto LABEL_20;
  }
  v5 = LocalAlloc(0x40u, Length);
  if ( !v5 )
    goto LABEL_4;
  v4 = NtQuerySecurityObject(Handle, 4u, v5, Length, &Length);
  if ( v4 < 0 )
    goto LABEL_19;
  if ( !ConvertSecurityDescriptorToStringSecurityDescriptorW(v5, 1u, 4u, &StringSecurityDescriptor, 0) )
  {
LABEL_7:
    LastError = GetLastError();
LABEL_20:
    v6 = LastError;
    goto LABEL_21;
  }
  v4 = NtQueryInformationToken(Handle, TokenUser, 0, 0, &ReturnLength);
  if ( v4 != -1073741789 )
    goto LABEL_19;
  v3 = (PSID *)LocalAlloc(0x40u, ReturnLength);
  if ( !v3 )
    goto LABEL_4;
  v4 = NtQueryInformationToken(Handle, TokenUser, v3, ReturnLength, &ReturnLength);
  if ( v4 < 0 )
    goto LABEL_19;
  if ( !ConvertSidToStringSidW(*v3, &StringSid) )
    goto LABEL_7;
  v8 = -1;
  v9 = -1;
  do
    ++v9;
  while ( StringSecurityDescriptor[v9] );
  do
    ++v8;
  while ( StringSid[v8] );
  Length = 2 * (v9 + v8) + 24;
  v10 = (unsigned __int16 *)LocalAlloc(0x40u, Length);
  v2 = v10;
  if ( !v10 || (int)StringCbPrintfW(v10, Length, L"%s%s%s)", StringSecurityDescriptor, L"(A;;0xe;;;", StringSid) < 0 )
  {
LABEL_4:
    v6 = 8;
    goto LABEL_21;
  }
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(v2, 1u, &SecurityDescriptor, 0) )
    goto LABEL_7;
  v6 = 0;
  v4 = NtSetSecurityObject(Handle, 4u, SecurityDescriptor);
  if ( v4 < 0 )
    goto LABEL_19;
LABEL_21:
  LocalFree(v5);
  LocalFree(StringSecurityDescriptor);
  LocalFree(StringSid);
  LocalFree(v2);
  LocalFree(SecurityDescriptor);
  LocalFree(v3);
  return v6;
}

```

## disassembly

```asm
0x18001c634  push    rbp
0x18001c636  push    rbx
0x18001c637  push    rsi
0x18001c638  push    rdi
0x18001c639  push    r12
0x18001c63b  push    r14
0x18001c63d  push    r15
0x18001c63f  mov     rbp, rsp
0x18001c642  sub     rsp, 40h
0x18001c646  xor     r12d, r12d
0x18001c649  lea     rax, [rbp+Length]
0x18001c64d  xor     r9d, r9d; Length
0x18001c650  mov     [rbp+Length], r12d
0x18001c654  xor     r8d, r8d; SecurityDescriptor
0x18001c657  mov     [rbp+SecurityDescriptor], r12
0x18001c65b  mov     r14, rcx
0x18001c65e  mov     [rbp+StringSecurityDescriptor], r12
0x18001c662  lea     edx, [r12+4]; SecurityInformation
0x18001c667  mov     [rbp+StringSid], r12
0x18001c66b  mov     esi, r12d
0x18001c66e  mov     [rbp+ReturnLength], r12d
0x18001c672  mov     r15d, r12d
0x18001c675  mov     [rsp+40h+LengthNeeded], rax; LengthNeeded
0x18001c67a  call    cs:__imp_NtQuerySecurityObject
0x18001c680  mov     ebx, 0C0000023h
0x18001c685  cmp     eax, ebx
0x18001c687  jz      short loc_18001C691
0x18001c689  mov     edi, r12d
0x18001c68c  jmp     loc_18001C82A
0x18001c691  mov     edx, [rbp+Length]; uBytes
0x18001c694  mov     ecx, 40h ; '@'; uFlags
0x18001c699  call    cs:__imp_LocalAlloc
0x18001c69f  mov     rdi, rax
0x18001c6a2  test    rax, rax
0x18001c6a5  jnz     short loc_18001C6B1
0x18001c6a7  mov     ebx, 8
0x18001c6ac  jmp     loc_18001C834
0x18001c6b1  mov     r9d, [rbp+Length]; Length
0x18001c6b5  lea     rax, [rbp+Length]
0x18001c6b9  mov     r8, rdi; SecurityDescriptor
0x18001c6bc  mov     [rsp+40h+LengthNeeded], rax; LengthNeeded
0x18001c6c1  mov     edx, 4; SecurityInformation
0x18001c6c6  mov     rcx, r14; Handle
0x18001c6c9  call    cs:__imp_NtQuerySecurityObject
0x18001c6cf  test    eax, eax
0x18001c6d1  js      loc_18001C82A
0x18001c6d7  mov     edx, 1; RequestedStringSDRevision
0x18001c6dc  mov     [rsp+40h+LengthNeeded], r12; StringSecurityDescriptorLen
0x18001c6e1  lea     r9, [rbp+StringSecurityDescriptor]; StringSecurityDescriptor
0x18001c6e5  mov     rcx, rdi; SecurityDescriptor
0x18001c6e8  lea     r8d, [rdx+3]; SecurityInformation
0x18001c6ec  call    cs:__imp_ConvertSecurityDescriptorToStringSecurityDescriptorW
0x18001c6f2  test    eax, eax
0x18001c6f4  jnz     short loc_18001C701
0x18001c6f6  call    cs:__imp_GetLastError
0x18001c6fc  jmp     loc_18001C832
0x18001c701  xor     r9d, r9d; TokenInformationLength
0x18001c704  lea     rax, [rbp+ReturnLength]
0x18001c708  xor     r8d, r8d; TokenInformation
0x18001c70b  mov     [rsp+40h+LengthNeeded], rax; ReturnLength
0x18001c710  mov     rcx, r14; TokenHandle
0x18001c713  lea     edx, [r9+1]; TokenInformationClass
0x18001c717  call    cs:__imp_NtQueryInformationToken
0x18001c71d  cmp     eax, ebx
0x18001c71f  jnz     loc_18001C82A
0x18001c725  mov     edx, [rbp+ReturnLength]; uBytes
0x18001c728  mov     ecx, 40h ; '@'; uFlags
0x18001c72d  call    cs:__imp_LocalAlloc
0x18001c733  mov     r15, rax
0x18001c736  test    rax, rax
0x18001c739  jz      loc_18001C6A7
0x18001c73f  mov     r9d, [rbp+ReturnLength]; TokenInformationLength
0x18001c743  lea     rax, [rbp+ReturnLength]
0x18001c747  mov     ebx, 1
0x18001c74c  mov     [rsp+40h+LengthNeeded], rax; ReturnLength
0x18001c751  mov     edx, ebx; TokenInformationClass
0x18001c753  mov     r8, r15; TokenInformation
0x18001c756  mov     rcx, r14; TokenHandle
0x18001c759  call    cs:__imp_NtQueryInformationToken
0x18001c75f  test    eax, eax
0x18001c761  js      loc_18001C82A
0x18001c767  mov     rcx, [r15]; Sid
0x18001c76a  lea     rdx, [rbp+StringSid]; StringSid
0x18001c76e  call    cs:__imp_ConvertSidToStringSidW
0x18001c774  test    eax, eax
0x18001c776  jz      loc_18001C6F6
0x18001c77c  mov     rcx, [rbp+StringSecurityDescriptor]
0x18001c780  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001c784  mov     rdx, rax
0x18001c787  inc     rdx
0x18001c78a  cmp     [rcx+rdx*2], r12w
0x18001c78f  jnz     short loc_18001C787
0x18001c791  mov     r8, [rbp+StringSid]
0x18001c795  inc     rax
0x18001c798  cmp     [r8+rax*2], r12w
0x18001c79d  jnz     short loc_18001C795
0x18001c79f  add     eax, edx
0x18001c7a1  mov     ecx, 40h ; '@'; uFlags
0x18001c7a6  lea     eax, ds:18h[rax*2]
0x18001c7ad  mov     edx, eax; uBytes
0x18001c7af  mov     [rbp+Length], eax
0x18001c7b2  call    cs:__imp_LocalAlloc
0x18001c7b8  mov     rsi, rax
0x18001c7bb  test    rax, rax
0x18001c7be  jz      loc_18001C6A7
0x18001c7c4  mov     rax, [rbp+StringSid]
0x18001c7c8  lea     r8, aSSS; "%s%s%s)"
0x18001c7cf  mov     edx, [rbp+Length]; unsigned __int64
0x18001c7d2  mov     rcx, rsi; unsigned __int16 *
0x18001c7d5  mov     r9, [rbp+StringSecurityDescriptor]
0x18001c7d9  mov     [rsp+40h+var_18], rax
0x18001c7de  lea     rax, aA0xe; "(A;;0xe;;;"
0x18001c7e5  mov     [rsp+40h+LengthNeeded], rax
0x18001c7ea  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001c7ef  test    eax, eax
0x18001c7f1  js      loc_18001C6A7
0x18001c7f7  xor     r9d, r9d; SecurityDescriptorSize
0x18001c7fa  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x18001c7fe  mov     edx, ebx; StringSDRevision
0x18001c800  mov     rcx, rsi; StringSecurityDescriptor
0x18001c803  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18001c809  test    eax, eax
0x18001c80b  jz      loc_18001C6F6
0x18001c811  mov     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x18001c815  mov     edx, 4; SecurityInformation
0x18001c81a  mov     rcx, r14; Handle
0x18001c81d  mov     ebx, r12d
0x18001c820  call    cs:__imp_NtSetSecurityObject
0x18001c826  test    eax, eax
0x18001c828  jns     short loc_18001C834
0x18001c82a  mov     ecx, eax; Status
0x18001c82c  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x18001c832  mov     ebx, eax
0x18001c834  mov     rcx, rdi; hMem
0x18001c837  call    cs:__imp_LocalFree
0x18001c83d  mov     rcx, [rbp+StringSecurityDescriptor]; hMem
0x18001c841  call    cs:__imp_LocalFree
0x18001c847  mov     rcx, [rbp+StringSid]; hMem
0x18001c84b  call    cs:__imp_LocalFree
0x18001c851  mov     rcx, rsi; hMem
0x18001c854  call    cs:__imp_LocalFree
0x18001c85a  mov     rcx, [rbp+SecurityDescriptor]; hMem
0x18001c85e  call    cs:__imp_LocalFree
0x18001c864  mov     rcx, r15; hMem
0x18001c867  call    cs:__imp_LocalFree
0x18001c86d  mov     eax, ebx
0x18001c86f  add     rsp, 40h
0x18001c873  pop     r15
0x18001c875  pop     r14
0x18001c877  pop     r12
0x18001c879  pop     rdi
0x18001c87a  pop     rsi
0x18001c87b  pop     rbx
0x18001c87c  pop     rbp
0x18001c87d  retn
```
