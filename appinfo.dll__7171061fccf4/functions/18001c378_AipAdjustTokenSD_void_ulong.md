# AipAdjustTokenSD(void *,ulong)

- ea: `0x18001c378`
- end: `0x18001c558`
- name: `?AipAdjustTokenSD@@YAKPEAXK@Z`
- size: `480`
- prototype: `__int64 __fastcall(HANDLE Handle, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180040d64`

## callees

- `0x18001ba24`
- `0x18001c378`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c433`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c433`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c518`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c522`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c52c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c535`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c53f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c518`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c522`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c52c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c535`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c53f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001c3d6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001c491`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001c3d6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001c491`
- `ntdll!NtSetSecurityObject` at `0x18001c501`
- `ntdll!NtSetSecurityObject` at `0x18001c501`
- `ntdll!NtQuerySecurityObject` at `0x18001c3b9`
- `ntdll!NtQuerySecurityObject` at `0x18001c406`
- `ntdll!NtQuerySecurityObject` at `0x18001c3b9`
- `ntdll!NtQuerySecurityObject` at `0x18001c406`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18001c50d`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18001c50d`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18001c4e4`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18001c4e4`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x18001c429`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x18001c429`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18001c451`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18001c451`

## pseudocode

```c
__int64 __fastcall AipAdjustTokenSD(HANDLE Handle, unsigned int a2)
{
  __int64 v2; // rbx
  WCHAR *v4; // rsi
  int v5; // eax
  HLOCAL v6; // rdi
  unsigned int v7; // ebx
  ULONG LastError; // eax
  __int64 v9; // rax
  __int64 v10; // rdx
  unsigned __int16 *v11; // rax
  LPWSTR StringSid; // [rsp+30h] [rbp-10h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+38h] [rbp-8h] BYREF
  ULONG Length; // [rsp+80h] [rbp+40h] BYREF
  LPWSTR StringSecurityDescriptor; // [rsp+88h] [rbp+48h] BYREF

  v2 = a2;
  Length = 0;
  SecurityDescriptor = 0;
  StringSecurityDescriptor = 0;
  StringSid = 0;
  v4 = 0;
  v5 = NtQuerySecurityObject(Handle, 4u, 0, 0, &Length);
  if ( v5 != -1073741789 )
  {
    v6 = 0;
LABEL_16:
    LastError = RtlNtStatusToDosErrorNoTeb(v5);
    goto LABEL_17;
  }
  v6 = LocalAlloc(0x40u, Length);
  if ( !v6 )
    goto LABEL_4;
  v5 = NtQuerySecurityObject(Handle, 4u, v6, Length, &Length);
  if ( v5 < 0 )
    goto LABEL_16;
  if ( !ConvertSecurityDescriptorToStringSecurityDescriptorW(v6, 1u, 4u, &StringSecurityDescriptor, 0)
    || !ConvertSidToStringSidW(&g_pServiceInfo + 9 * v2, &StringSid) )
  {
    goto LABEL_7;
  }
  v9 = -1;
  v10 = -1;
  do
    ++v10;
  while ( StringSecurityDescriptor[v10] );
  do
    ++v9;
  while ( StringSid[v9] );
  Length = 2 * (v10 + v9) + 24;
  v11 = (unsigned __int16 *)LocalAlloc(0x40u, Length);
  v4 = v11;
  if ( !v11 || (int)StringCbPrintfW(v11, Length, L"%s%s%s)", StringSecurityDescriptor, L"(A;;0xe;;;", StringSid) < 0 )
  {
LABEL_4:
    v7 = 8;
    goto LABEL_18;
  }
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(v4, 1u, &SecurityDescriptor, 0) )
  {
LABEL_7:
    LastError = GetLastError();
LABEL_17:
    v7 = LastError;
    goto LABEL_18;
  }
  v7 = 0;
  v5 = NtSetSecurityObject(Handle, 4u, SecurityDescriptor);
  if ( v5 < 0 )
    goto LABEL_16;
LABEL_18:
  LocalFree(v6);
  LocalFree(StringSecurityDescriptor);
  LocalFree(StringSid);
  LocalFree(v4);
  LocalFree(SecurityDescriptor);
  return v7;
}

```

## disassembly

```asm
0x18001c378  mov     [rsp-28h+arg_0], rbx
0x18001c37d  push    rbp
0x18001c37e  push    rsi
0x18001c37f  push    rdi
0x18001c380  push    r14
0x18001c382  push    r15
0x18001c384  mov     rbp, rsp
0x18001c387  sub     rsp, 40h
0x18001c38b  xor     r15d, r15d
0x18001c38e  mov     ebx, edx
0x18001c390  lea     rax, [rbp+Length]
0x18001c394  mov     [rbp+Length], r15d
0x18001c398  xor     r9d, r9d; Length
0x18001c39b  mov     [rbp+SecurityDescriptor], r15
0x18001c39f  xor     r8d, r8d; SecurityDescriptor
0x18001c3a2  mov     [rbp+StringSecurityDescriptor], r15
0x18001c3a6  lea     edx, [r15+4]; SecurityInformation
0x18001c3aa  mov     [rbp+StringSid], r15
0x18001c3ae  mov     r14, rcx
0x18001c3b1  mov     [rsp+40h+LengthNeeded], rax; LengthNeeded
0x18001c3b6  mov     esi, r15d
0x18001c3b9  call    cs:__imp_NtQuerySecurityObject
0x18001c3bf  cmp     eax, 0C0000023h
0x18001c3c4  jz      short loc_18001C3CE
0x18001c3c6  mov     edi, r15d
0x18001c3c9  jmp     loc_18001C50B
0x18001c3ce  mov     edx, [rbp+Length]; uBytes
0x18001c3d1  mov     ecx, 40h ; '@'; uFlags
0x18001c3d6  call    cs:__imp_LocalAlloc
0x18001c3dc  mov     rdi, rax
0x18001c3df  test    rax, rax
0x18001c3e2  jnz     short loc_18001C3EE
0x18001c3e4  mov     ebx, 8
0x18001c3e9  jmp     loc_18001C515
0x18001c3ee  mov     r9d, [rbp+Length]; Length
0x18001c3f2  lea     rax, [rbp+Length]
0x18001c3f6  mov     r8, rdi; SecurityDescriptor
0x18001c3f9  mov     [rsp+40h+LengthNeeded], rax; LengthNeeded
0x18001c3fe  mov     edx, 4; SecurityInformation
0x18001c403  mov     rcx, r14; Handle
0x18001c406  call    cs:__imp_NtQuerySecurityObject
0x18001c40c  test    eax, eax
0x18001c40e  js      loc_18001C50B
0x18001c414  mov     edx, 1; RequestedStringSDRevision
0x18001c419  mov     [rsp+40h+LengthNeeded], r15; StringSecurityDescriptorLen
0x18001c41e  lea     r9, [rbp+StringSecurityDescriptor]; StringSecurityDescriptor
0x18001c422  mov     rcx, rdi; SecurityDescriptor
0x18001c425  lea     r8d, [rdx+3]; SecurityInformation
0x18001c429  call    cs:__imp_ConvertSecurityDescriptorToStringSecurityDescriptorW
0x18001c42f  test    eax, eax
0x18001c431  jnz     short loc_18001C43E
0x18001c433  call    cs:__imp_GetLastError
0x18001c439  jmp     loc_18001C513
0x18001c43e  lea     rax, ?g_pServiceInfo@@3PAU_SERVICE_INFO@@A; _SERVICE_INFO near * g_pServiceInfo
0x18001c445  lea     rcx, [rbx+rbx*8]
0x18001c449  lea     rcx, [rax+rcx*8]; Sid
0x18001c44d  lea     rdx, [rbp+StringSid]; StringSid
0x18001c451  call    cs:__imp_ConvertSidToStringSidW
0x18001c457  test    eax, eax
0x18001c459  jz      short loc_18001C433
0x18001c45b  mov     rcx, [rbp+StringSecurityDescriptor]
0x18001c45f  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001c463  mov     rdx, rax
0x18001c466  inc     rdx
0x18001c469  cmp     [rcx+rdx*2], r15w
0x18001c46e  jnz     short loc_18001C466
0x18001c470  mov     r8, [rbp+StringSid]
0x18001c474  inc     rax
0x18001c477  cmp     [r8+rax*2], r15w
0x18001c47c  jnz     short loc_18001C474
0x18001c47e  add     eax, edx
0x18001c480  mov     ecx, 40h ; '@'; uFlags
0x18001c485  lea     eax, ds:18h[rax*2]
0x18001c48c  mov     edx, eax; uBytes
0x18001c48e  mov     [rbp+Length], eax
0x18001c491  call    cs:__imp_LocalAlloc
0x18001c497  mov     rsi, rax
0x18001c49a  test    rax, rax
0x18001c49d  jz      loc_18001C3E4
0x18001c4a3  mov     rax, [rbp+StringSid]
0x18001c4a7  lea     r8, aSSS; "%s%s%s)"
0x18001c4ae  mov     edx, [rbp+Length]; unsigned __int64
0x18001c4b1  mov     rcx, rsi; unsigned __int16 *
0x18001c4b4  mov     r9, [rbp+StringSecurityDescriptor]
0x18001c4b8  mov     [rsp+40h+var_18], rax
0x18001c4bd  lea     rax, aA0xe; "(A;;0xe;;;"
0x18001c4c4  mov     [rsp+40h+LengthNeeded], rax
0x18001c4c9  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001c4ce  test    eax, eax
0x18001c4d0  js      loc_18001C3E4
0x18001c4d6  xor     r9d, r9d; SecurityDescriptorSize
0x18001c4d9  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x18001c4dd  mov     rcx, rsi; StringSecurityDescriptor
0x18001c4e0  lea     edx, [r9+1]; StringSDRevision
0x18001c4e4  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18001c4ea  test    eax, eax
0x18001c4ec  jz      loc_18001C433
0x18001c4f2  mov     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x18001c4f6  mov     edx, 4; SecurityInformation
0x18001c4fb  mov     rcx, r14; Handle
0x18001c4fe  mov     ebx, r15d
0x18001c501  call    cs:__imp_NtSetSecurityObject
0x18001c507  test    eax, eax
0x18001c509  jns     short loc_18001C515
0x18001c50b  mov     ecx, eax; Status
0x18001c50d  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x18001c513  mov     ebx, eax
0x18001c515  mov     rcx, rdi; hMem
0x18001c518  call    cs:__imp_LocalFree
0x18001c51e  mov     rcx, [rbp+StringSecurityDescriptor]; hMem
0x18001c522  call    cs:__imp_LocalFree
0x18001c528  mov     rcx, [rbp+StringSid]; hMem
0x18001c52c  call    cs:__imp_LocalFree
0x18001c532  mov     rcx, rsi; hMem
0x18001c535  call    cs:__imp_LocalFree
0x18001c53b  mov     rcx, [rbp+SecurityDescriptor]; hMem
0x18001c53f  call    cs:__imp_LocalFree
0x18001c545  mov     eax, ebx
0x18001c547  mov     rbx, [rsp+40h+arg_0]
0x18001c54c  add     rsp, 40h
0x18001c550  pop     r15
0x18001c552  pop     r14
0x18001c554  pop     rdi
0x18001c555  pop     rsi
0x18001c556  pop     rbp
0x18001c557  retn
```
