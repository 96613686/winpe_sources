# AipAddTokenUserInTokenSD(void *)

- ea: `0x18001a17c`
- end: `0x18001a42d`
- name: `?AipAddTokenUserInTokenSD@@YAKPEAX@Z`
- size: `689`
- prototype: `unsigned int __fastcall(HANDLE Handle)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18003c4c4`

## callees

- `0x180019858`
- `0x18001a17c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a24f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a24f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a3c1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a3d1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a3e1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a3f0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a400`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a40f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a3c1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a3d1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a3e1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a3f0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a400`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a40f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001a1df`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001a294`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001a326`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001a1df`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001a294`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001a326`
- `ntdll!NtQueryInformationToken` at `0x18001a275`
- `ntdll!NtQueryInformationToken` at `0x18001a2c2`
- `ntdll!NtQueryInformationToken` at `0x18001a275`
- `ntdll!NtQueryInformationToken` at `0x18001a2c2`
- `ntdll!NtSetSecurityObject` at `0x18001a39e`
- `ntdll!NtSetSecurityObject` at `0x18001a39e`
- `ntdll!NtQuerySecurityObject` at `0x18001a1c2`
- `ntdll!NtQuerySecurityObject` at `0x18001a213`
- `ntdll!NtQuerySecurityObject` at `0x18001a1c2`
- `ntdll!NtQuerySecurityObject` at `0x18001a213`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18001a3b0`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18001a3b0`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18001a2dd`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18001a2dd`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18001a37e`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18001a37e`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x18001a23f`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x18001a23f`

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
0x18001a17c  push    rbp
0x18001a17e  push    rbx
0x18001a17f  push    rsi
0x18001a180  push    rdi
0x18001a181  push    r13
0x18001a183  push    r14
0x18001a185  push    r15
0x18001a187  mov     rbp, rsp
0x18001a18a  sub     rsp, 40h
0x18001a18e  xor     ebx, ebx
0x18001a190  lea     rax, [rbp+Length]
0x18001a194  xor     r9d, r9d; Length
0x18001a197  mov     [rbp+Length], ebx
0x18001a19a  xor     r8d, r8d; SecurityDescriptor
0x18001a19d  mov     [rbp+SecurityDescriptor], rbx
0x18001a1a1  mov     r15, rcx
0x18001a1a4  mov     [rbp+StringSecurityDescriptor], rbx
0x18001a1a8  lea     r13d, [rbx+4]
0x18001a1ac  mov     [rbp+StringSid], rbx
0x18001a1b0  mov     edx, r13d; SecurityInformation
0x18001a1b3  mov     [rbp+ReturnLength], ebx
0x18001a1b6  mov     r14d, ebx
0x18001a1b9  mov     [rsp+40h+LengthNeeded], rax; LengthNeeded
0x18001a1be  mov     esi, ebx
0x18001a1c0  mov     edi, ebx
0x18001a1c2  call    cs:__imp_NtQuerySecurityObject
0x18001a1c9  nop     dword ptr [rax+rax+00h]
0x18001a1ce  cmp     eax, 0C0000023h
0x18001a1d3  jnz     loc_18001A3AE
0x18001a1d9  mov     edx, [rbp+Length]; uBytes
0x18001a1dc  lea     ecx, [rbx+40h]; uFlags
0x18001a1df  call    cs:__imp_LocalAlloc
0x18001a1e6  nop     dword ptr [rax+rax+00h]
0x18001a1eb  mov     r14, rax
0x18001a1ee  test    rax, rax
0x18001a1f1  jnz     short loc_18001A1FD
0x18001a1f3  mov     ebx, 8
0x18001a1f8  jmp     loc_18001A3BE
0x18001a1fd  mov     r9d, [rbp+Length]; Length
0x18001a201  lea     rax, [rbp+Length]
0x18001a205  mov     r8, r14; SecurityDescriptor
0x18001a208  mov     [rsp+40h+LengthNeeded], rax; LengthNeeded
0x18001a20d  mov     edx, r13d; SecurityInformation
0x18001a210  mov     rcx, r15; Handle
0x18001a213  call    cs:__imp_NtQuerySecurityObject
0x18001a21a  nop     dword ptr [rax+rax+00h]
0x18001a21f  test    eax, eax
0x18001a221  js      loc_18001A3AE
0x18001a227  mov     r8d, r13d; SecurityInformation
0x18001a22a  mov     [rsp+40h+LengthNeeded], rbx; StringSecurityDescriptorLen
0x18001a22f  mov     r13d, 1
0x18001a235  lea     r9, [rbp+StringSecurityDescriptor]; StringSecurityDescriptor
0x18001a239  mov     edx, r13d; RequestedStringSDRevision
0x18001a23c  mov     rcx, r14; SecurityDescriptor
0x18001a23f  call    cs:__imp_ConvertSecurityDescriptorToStringSecurityDescriptorW
0x18001a246  nop     dword ptr [rax+rax+00h]
0x18001a24b  test    eax, eax
0x18001a24d  jnz     short loc_18001A260
0x18001a24f  call    cs:__imp_GetLastError
0x18001a256  nop     dword ptr [rax+rax+00h]
0x18001a25b  jmp     loc_18001A3BC
0x18001a260  lea     rax, [rbp+ReturnLength]
0x18001a264  xor     r9d, r9d; TokenInformationLength
0x18001a267  xor     r8d, r8d; TokenInformation
0x18001a26a  mov     [rsp+40h+LengthNeeded], rax; ReturnLength
0x18001a26f  mov     edx, r13d; TokenInformationClass
0x18001a272  mov     rcx, r15; TokenHandle
0x18001a275  call    cs:__imp_NtQueryInformationToken
0x18001a27c  nop     dword ptr [rax+rax+00h]
0x18001a281  cmp     eax, 0C0000023h
0x18001a286  jnz     loc_18001A3AE
0x18001a28c  mov     edx, [rbp+ReturnLength]; uBytes
0x18001a28f  mov     ecx, 40h ; '@'; uFlags
0x18001a294  call    cs:__imp_LocalAlloc
0x18001a29b  nop     dword ptr [rax+rax+00h]
0x18001a2a0  mov     rdi, rax
0x18001a2a3  test    rax, rax
0x18001a2a6  jz      loc_18001A1F3
0x18001a2ac  mov     r9d, [rbp+ReturnLength]; TokenInformationLength
0x18001a2b0  lea     rax, [rbp+ReturnLength]
0x18001a2b4  mov     r8, rdi; TokenInformation
0x18001a2b7  mov     [rsp+40h+LengthNeeded], rax; ReturnLength
0x18001a2bc  mov     edx, r13d; TokenInformationClass
0x18001a2bf  mov     rcx, r15; TokenHandle
0x18001a2c2  call    cs:__imp_NtQueryInformationToken
0x18001a2c9  nop     dword ptr [rax+rax+00h]
0x18001a2ce  test    eax, eax
0x18001a2d0  js      loc_18001A3AE
0x18001a2d6  mov     rcx, [rdi]; Sid
0x18001a2d9  lea     rdx, [rbp+StringSid]; StringSid
0x18001a2dd  call    cs:__imp_ConvertSidToStringSidW
0x18001a2e4  nop     dword ptr [rax+rax+00h]
0x18001a2e9  test    eax, eax
0x18001a2eb  jz      loc_18001A24F
0x18001a2f1  mov     rcx, [rbp+StringSid]
0x18001a2f5  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001a2f9  mov     rdx, rax
0x18001a2fc  inc     rdx
0x18001a2ff  cmp     [rcx+rdx*2], bx
0x18001a303  jnz     short loc_18001A2FC
0x18001a305  mov     r8, [rbp+StringSecurityDescriptor]
0x18001a309  inc     rax
0x18001a30c  cmp     [r8+rax*2], bx
0x18001a311  jnz     short loc_18001A309
0x18001a313  add     edx, eax
0x18001a315  mov     ecx, 40h ; '@'; uFlags
0x18001a31a  lea     eax, ds:18h[rdx*2]
0x18001a321  mov     edx, eax; uBytes
0x18001a323  mov     [rbp+Length], eax
0x18001a326  call    cs:__imp_LocalAlloc
0x18001a32d  nop     dword ptr [rax+rax+00h]
0x18001a332  mov     rsi, rax
0x18001a335  test    rax, rax
0x18001a338  jz      loc_18001A1F3
0x18001a33e  mov     rax, [rbp+StringSid]
0x18001a342  lea     r8, aSSS; "%s%s%s)"
0x18001a349  mov     edx, [rbp+Length]; unsigned __int64
0x18001a34c  mov     rcx, rsi; unsigned __int16 *
0x18001a34f  mov     r9, [rbp+StringSecurityDescriptor]
0x18001a353  mov     [rsp+40h+var_18], rax
0x18001a358  lea     rax, aA0xe; "(A;;0xe;;;"
0x18001a35f  mov     [rsp+40h+LengthNeeded], rax
0x18001a364  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001a369  test    eax, eax
0x18001a36b  js      loc_18001A1F3
0x18001a371  xor     r9d, r9d; SecurityDescriptorSize
0x18001a374  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x18001a378  mov     edx, r13d; StringSDRevision
0x18001a37b  mov     rcx, rsi; StringSecurityDescriptor
0x18001a37e  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18001a385  nop     dword ptr [rax+rax+00h]
0x18001a38a  test    eax, eax
0x18001a38c  jz      loc_18001A24F
0x18001a392  mov     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x18001a396  mov     edx, 4; SecurityInformation
0x18001a39b  mov     rcx, r15; Handle
0x18001a39e  call    cs:__imp_NtSetSecurityObject
0x18001a3a5  nop     dword ptr [rax+rax+00h]
0x18001a3aa  test    eax, eax
0x18001a3ac  jns     short loc_18001A3BE
0x18001a3ae  mov     ecx, eax; Status
0x18001a3b0  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x18001a3b7  nop     dword ptr [rax+rax+00h]
0x18001a3bc  mov     ebx, eax
0x18001a3be  mov     rcx, r14; hMem
0x18001a3c1  call    cs:__imp_LocalFree
0x18001a3c8  nop     dword ptr [rax+rax+00h]
0x18001a3cd  mov     rcx, [rbp+StringSecurityDescriptor]; hMem
0x18001a3d1  call    cs:__imp_LocalFree
0x18001a3d8  nop     dword ptr [rax+rax+00h]
0x18001a3dd  mov     rcx, [rbp+StringSid]; hMem
0x18001a3e1  call    cs:__imp_LocalFree
0x18001a3e8  nop     dword ptr [rax+rax+00h]
0x18001a3ed  mov     rcx, rsi; hMem
0x18001a3f0  call    cs:__imp_LocalFree
0x18001a3f7  nop     dword ptr [rax+rax+00h]
0x18001a3fc  mov     rcx, [rbp+SecurityDescriptor]; hMem
0x18001a400  call    cs:__imp_LocalFree
0x18001a407  nop     dword ptr [rax+rax+00h]
0x18001a40c  mov     rcx, rdi; hMem
0x18001a40f  call    cs:__imp_LocalFree
0x18001a416  nop     dword ptr [rax+rax+00h]
0x18001a41b  mov     eax, ebx
0x18001a41d  add     rsp, 40h
0x18001a421  pop     r15
0x18001a423  pop     r14
0x18001a425  pop     r13
0x18001a427  pop     rdi
0x18001a428  pop     rsi
0x18001a429  pop     rbx
0x18001a42a  pop     rbp
0x18001a42b  retn
```
