# AipAdjustTokenSD(void *,ulong)

- ea: `0x180019dfc`
- end: `0x18001a02c`
- name: `?AipAdjustTokenSD@@YAKPEAXK@Z`
- size: `560`
- prototype: `unsigned int __fastcall(HANDLE Handle, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18003c4c4`

## callees

- `0x180019858`
- `0x180019dfc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019ec8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019ec8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019fcd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019fdd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019fed`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019ffc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a00c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019fcd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019fdd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019fed`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019ffc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a00c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180019e59`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180019f31`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180019e59`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180019f31`
- `ntdll!NtSetSecurityObject` at `0x180019faa`
- `ntdll!NtSetSecurityObject` at `0x180019faa`
- `ntdll!NtQuerySecurityObject` at `0x180019e3c`
- `ntdll!NtQuerySecurityObject` at `0x180019e8f`
- `ntdll!NtQuerySecurityObject` at `0x180019e3c`
- `ntdll!NtQuerySecurityObject` at `0x180019e8f`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180019fbc`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180019fbc`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180019eec`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180019eec`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180019f8a`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180019f8a`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x180019eb8`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x180019eb8`

## pseudocode

```c
__int64 __fastcall AipAdjustTokenSD(HANDLE Handle, unsigned int a2)
{
  unsigned int v2; // ebx
  __int64 v3; // r14
  HLOCAL v5; // rsi
  WCHAR *v6; // rdi
  int v7; // eax
  DWORD LastError; // eax
  __int64 v9; // rax
  __int64 v10; // rdx
  unsigned __int16 *v11; // rax
  LPWSTR StringSid; // [rsp+30h] [rbp-10h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+38h] [rbp-8h] BYREF
  ULONG Length; // [rsp+80h] [rbp+40h] BYREF
  LPWSTR StringSecurityDescriptor; // [rsp+88h] [rbp+48h] BYREF

  v2 = 0;
  v3 = a2;
  Length = 0;
  SecurityDescriptor = 0;
  StringSecurityDescriptor = 0;
  StringSid = 0;
  v5 = 0;
  v6 = 0;
  v7 = NtQuerySecurityObject(Handle, 4u, 0, 0, &Length);
  if ( v7 != -1073741789 )
    goto LABEL_15;
  v5 = LocalAlloc(0x40u, Length);
  if ( v5 )
  {
    v7 = NtQuerySecurityObject(Handle, 4u, v5, Length, &Length);
    if ( v7 >= 0 )
    {
      if ( !ConvertSecurityDescriptorToStringSecurityDescriptorW(v5, 1u, 4u, &StringSecurityDescriptor, 0)
        || !ConvertSidToStringSidW((char *)&g_pServiceInfo + 72 * v3, &StringSid) )
      {
        goto LABEL_6;
      }
      v9 = -1;
      v10 = -1;
      do
        ++v10;
      while ( StringSid[v10] );
      do
        ++v9;
      while ( StringSecurityDescriptor[v9] );
      Length = 2 * (v9 + v10) + 24;
      v11 = (unsigned __int16 *)LocalAlloc(0x40u, Length);
      v6 = v11;
      if ( !v11 || (int)StringCbPrintfW(v11, Length, L"%s%s%s)", StringSecurityDescriptor, L"(A;;0xe;;;", StringSid) < 0 )
        goto LABEL_3;
      if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(v6, 1u, &SecurityDescriptor, 0) )
      {
LABEL_6:
        LastError = GetLastError();
LABEL_16:
        v2 = LastError;
        goto LABEL_17;
      }
      v7 = NtSetSecurityObject(Handle, 4u, SecurityDescriptor);
      if ( v7 >= 0 )
        goto LABEL_17;
    }
LABEL_15:
    LastError = RtlNtStatusToDosErrorNoTeb(v7);
    goto LABEL_16;
  }
LABEL_3:
  v2 = 8;
LABEL_17:
  LocalFree(v5);
  LocalFree(StringSecurityDescriptor);
  LocalFree(StringSid);
  LocalFree(v6);
  LocalFree(SecurityDescriptor);
  return v2;
}

```

## disassembly

```asm
0x180019dfc  mov     [rsp-28h+arg_0], rbx
0x180019e01  push    rbp
0x180019e02  push    rsi
0x180019e03  push    rdi
0x180019e04  push    r14
0x180019e06  push    r15
0x180019e08  mov     rbp, rsp
0x180019e0b  sub     rsp, 40h
0x180019e0f  xor     ebx, ebx
0x180019e11  mov     r14d, edx
0x180019e14  lea     rax, [rbp+Length]
0x180019e18  mov     [rbp+Length], ebx
0x180019e1b  xor     r9d, r9d; Length
0x180019e1e  mov     [rbp+SecurityDescriptor], rbx
0x180019e22  xor     r8d, r8d; SecurityDescriptor
0x180019e25  mov     [rbp+StringSecurityDescriptor], rbx
0x180019e29  lea     edx, [rbx+4]; SecurityInformation
0x180019e2c  mov     [rbp+StringSid], rbx
0x180019e30  mov     r15, rcx
0x180019e33  mov     [rsp+40h+LengthNeeded], rax; LengthNeeded
0x180019e38  mov     esi, ebx
0x180019e3a  mov     edi, ebx
0x180019e3c  call    cs:__imp_NtQuerySecurityObject
0x180019e43  nop     dword ptr [rax+rax+00h]
0x180019e48  cmp     eax, 0C0000023h
0x180019e4d  jnz     loc_180019FBA
0x180019e53  mov     edx, [rbp+Length]; uBytes
0x180019e56  lea     ecx, [rbx+40h]; uFlags
0x180019e59  call    cs:__imp_LocalAlloc
0x180019e60  nop     dword ptr [rax+rax+00h]
0x180019e65  mov     rsi, rax
0x180019e68  test    rax, rax
0x180019e6b  jnz     short loc_180019E77
0x180019e6d  mov     ebx, 8
0x180019e72  jmp     loc_180019FCA
0x180019e77  mov     r9d, [rbp+Length]; Length
0x180019e7b  lea     rax, [rbp+Length]
0x180019e7f  mov     r8, rsi; SecurityDescriptor
0x180019e82  mov     [rsp+40h+LengthNeeded], rax; LengthNeeded
0x180019e87  mov     edx, 4; SecurityInformation
0x180019e8c  mov     rcx, r15; Handle
0x180019e8f  call    cs:__imp_NtQuerySecurityObject
0x180019e96  nop     dword ptr [rax+rax+00h]
0x180019e9b  test    eax, eax
0x180019e9d  js      loc_180019FBA
0x180019ea3  mov     edx, 1; RequestedStringSDRevision
0x180019ea8  mov     [rsp+40h+LengthNeeded], rbx; StringSecurityDescriptorLen
0x180019ead  lea     r9, [rbp+StringSecurityDescriptor]; StringSecurityDescriptor
0x180019eb1  mov     rcx, rsi; SecurityDescriptor
0x180019eb4  lea     r8d, [rdx+3]; SecurityInformation
0x180019eb8  call    cs:__imp_ConvertSecurityDescriptorToStringSecurityDescriptorW
0x180019ebf  nop     dword ptr [rax+rax+00h]
0x180019ec4  test    eax, eax
0x180019ec6  jnz     short loc_180019ED9
0x180019ec8  call    cs:__imp_GetLastError
0x180019ecf  nop     dword ptr [rax+rax+00h]
0x180019ed4  jmp     loc_180019FC8
0x180019ed9  lea     rax, ?g_pServiceInfo@@3PAU_SERVICE_INFO@@A; _SERVICE_INFO near * g_pServiceInfo
0x180019ee0  lea     rcx, [r14+r14*8]
0x180019ee4  lea     rcx, [rax+rcx*8]; Sid
0x180019ee8  lea     rdx, [rbp+StringSid]; StringSid
0x180019eec  call    cs:__imp_ConvertSidToStringSidW
0x180019ef3  nop     dword ptr [rax+rax+00h]
0x180019ef8  test    eax, eax
0x180019efa  jz      short loc_180019EC8
0x180019efc  mov     rcx, [rbp+StringSid]
0x180019f00  or      rax, 0FFFFFFFFFFFFFFFFh
0x180019f04  mov     rdx, rax
0x180019f07  inc     rdx
0x180019f0a  cmp     [rcx+rdx*2], bx
0x180019f0e  jnz     short loc_180019F07
0x180019f10  mov     r8, [rbp+StringSecurityDescriptor]
0x180019f14  inc     rax
0x180019f17  cmp     [r8+rax*2], bx
0x180019f1c  jnz     short loc_180019F14
0x180019f1e  add     edx, eax
0x180019f20  mov     ecx, 40h ; '@'; uFlags
0x180019f25  lea     eax, ds:18h[rdx*2]
0x180019f2c  mov     edx, eax; uBytes
0x180019f2e  mov     [rbp+Length], eax
0x180019f31  call    cs:__imp_LocalAlloc
0x180019f38  nop     dword ptr [rax+rax+00h]
0x180019f3d  mov     rdi, rax
0x180019f40  test    rax, rax
0x180019f43  jz      loc_180019E6D
0x180019f49  mov     rax, [rbp+StringSid]
0x180019f4d  lea     r8, aSSS; "%s%s%s)"
0x180019f54  mov     edx, [rbp+Length]; unsigned __int64
0x180019f57  mov     rcx, rdi; unsigned __int16 *
0x180019f5a  mov     r9, [rbp+StringSecurityDescriptor]
0x180019f5e  mov     [rsp+40h+var_18], rax
0x180019f63  lea     rax, aA0xe; "(A;;0xe;;;"
0x180019f6a  mov     [rsp+40h+LengthNeeded], rax
0x180019f6f  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180019f74  test    eax, eax
0x180019f76  js      loc_180019E6D
0x180019f7c  xor     r9d, r9d; SecurityDescriptorSize
0x180019f7f  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x180019f83  mov     rcx, rdi; StringSecurityDescriptor
0x180019f86  lea     edx, [r9+1]; StringSDRevision
0x180019f8a  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180019f91  nop     dword ptr [rax+rax+00h]
0x180019f96  test    eax, eax
0x180019f98  jz      loc_180019EC8
0x180019f9e  mov     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x180019fa2  mov     edx, 4; SecurityInformation
0x180019fa7  mov     rcx, r15; Handle
0x180019faa  call    cs:__imp_NtSetSecurityObject
0x180019fb1  nop     dword ptr [rax+rax+00h]
0x180019fb6  test    eax, eax
0x180019fb8  jns     short loc_180019FCA
0x180019fba  mov     ecx, eax; Status
0x180019fbc  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x180019fc3  nop     dword ptr [rax+rax+00h]
0x180019fc8  mov     ebx, eax
0x180019fca  mov     rcx, rsi; hMem
0x180019fcd  call    cs:__imp_LocalFree
0x180019fd4  nop     dword ptr [rax+rax+00h]
0x180019fd9  mov     rcx, [rbp+StringSecurityDescriptor]; hMem
0x180019fdd  call    cs:__imp_LocalFree
0x180019fe4  nop     dword ptr [rax+rax+00h]
0x180019fe9  mov     rcx, [rbp+StringSid]; hMem
0x180019fed  call    cs:__imp_LocalFree
0x180019ff4  nop     dword ptr [rax+rax+00h]
0x180019ff9  mov     rcx, rdi; hMem
0x180019ffc  call    cs:__imp_LocalFree
0x18001a003  nop     dword ptr [rax+rax+00h]
0x18001a008  mov     rcx, [rbp+SecurityDescriptor]; hMem
0x18001a00c  call    cs:__imp_LocalFree
0x18001a013  nop     dword ptr [rax+rax+00h]
0x18001a018  mov     eax, ebx
0x18001a01a  mov     rbx, [rsp+40h+arg_0]
0x18001a01f  add     rsp, 40h
0x18001a023  pop     r15
0x18001a025  pop     r14
0x18001a027  pop     rdi
0x18001a028  pop     rsi
0x18001a029  pop     rbp
0x18001a02a  retn
```
