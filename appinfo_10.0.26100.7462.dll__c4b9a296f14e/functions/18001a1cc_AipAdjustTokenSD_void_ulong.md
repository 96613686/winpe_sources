# AipAdjustTokenSD(void *,ulong)

- ea: `0x18001a1cc`
- end: `0x18001a3fc`
- name: `?AipAdjustTokenSD@@YAKPEAXK@Z`
- size: `560`
- prototype: `unsigned int __fastcall(HANDLE Handle, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18003e5d4`

## callees

- `0x180019c28`
- `0x18001a1cc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a298`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a298`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a39d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a3ad`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a3bd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a3cc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a3dc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a39d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a3ad`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a3bd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a3cc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a3dc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001a229`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001a301`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001a229`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001a301`
- `ntdll!NtSetSecurityObject` at `0x18001a37a`
- `ntdll!NtSetSecurityObject` at `0x18001a37a`
- `ntdll!NtQuerySecurityObject` at `0x18001a20c`
- `ntdll!NtQuerySecurityObject` at `0x18001a25f`
- `ntdll!NtQuerySecurityObject` at `0x18001a20c`
- `ntdll!NtQuerySecurityObject` at `0x18001a25f`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18001a38c`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18001a38c`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x18001a288`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x18001a288`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18001a35a`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18001a35a`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18001a2bc`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18001a2bc`

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
0x18001a1cc  mov     [rsp-28h+arg_0], rbx
0x18001a1d1  push    rbp
0x18001a1d2  push    rsi
0x18001a1d3  push    rdi
0x18001a1d4  push    r14
0x18001a1d6  push    r15
0x18001a1d8  mov     rbp, rsp
0x18001a1db  sub     rsp, 40h
0x18001a1df  xor     ebx, ebx
0x18001a1e1  mov     r14d, edx
0x18001a1e4  lea     rax, [rbp+Length]
0x18001a1e8  mov     [rbp+Length], ebx
0x18001a1eb  xor     r9d, r9d; Length
0x18001a1ee  mov     [rbp+SecurityDescriptor], rbx
0x18001a1f2  xor     r8d, r8d; SecurityDescriptor
0x18001a1f5  mov     [rbp+StringSecurityDescriptor], rbx
0x18001a1f9  lea     edx, [rbx+4]; SecurityInformation
0x18001a1fc  mov     [rbp+StringSid], rbx
0x18001a200  mov     r15, rcx
0x18001a203  mov     [rsp+40h+LengthNeeded], rax; LengthNeeded
0x18001a208  mov     esi, ebx
0x18001a20a  mov     edi, ebx
0x18001a20c  call    cs:__imp_NtQuerySecurityObject
0x18001a213  nop     dword ptr [rax+rax+00h]
0x18001a218  cmp     eax, 0C0000023h
0x18001a21d  jnz     loc_18001A38A
0x18001a223  mov     edx, [rbp+Length]; uBytes
0x18001a226  lea     ecx, [rbx+40h]; uFlags
0x18001a229  call    cs:__imp_LocalAlloc
0x18001a230  nop     dword ptr [rax+rax+00h]
0x18001a235  mov     rsi, rax
0x18001a238  test    rax, rax
0x18001a23b  jnz     short loc_18001A247
0x18001a23d  mov     ebx, 8
0x18001a242  jmp     loc_18001A39A
0x18001a247  mov     r9d, [rbp+Length]; Length
0x18001a24b  lea     rax, [rbp+Length]
0x18001a24f  mov     r8, rsi; SecurityDescriptor
0x18001a252  mov     [rsp+40h+LengthNeeded], rax; LengthNeeded
0x18001a257  mov     edx, 4; SecurityInformation
0x18001a25c  mov     rcx, r15; Handle
0x18001a25f  call    cs:__imp_NtQuerySecurityObject
0x18001a266  nop     dword ptr [rax+rax+00h]
0x18001a26b  test    eax, eax
0x18001a26d  js      loc_18001A38A
0x18001a273  mov     edx, 1; RequestedStringSDRevision
0x18001a278  mov     [rsp+40h+LengthNeeded], rbx; StringSecurityDescriptorLen
0x18001a27d  lea     r9, [rbp+StringSecurityDescriptor]; StringSecurityDescriptor
0x18001a281  mov     rcx, rsi; SecurityDescriptor
0x18001a284  lea     r8d, [rdx+3]; SecurityInformation
0x18001a288  call    cs:__imp_ConvertSecurityDescriptorToStringSecurityDescriptorW
0x18001a28f  nop     dword ptr [rax+rax+00h]
0x18001a294  test    eax, eax
0x18001a296  jnz     short loc_18001A2A9
0x18001a298  call    cs:__imp_GetLastError
0x18001a29f  nop     dword ptr [rax+rax+00h]
0x18001a2a4  jmp     loc_18001A398
0x18001a2a9  lea     rax, ?g_pServiceInfo@@3PAU_SERVICE_INFO@@A; _SERVICE_INFO near * g_pServiceInfo
0x18001a2b0  lea     rcx, [r14+r14*8]
0x18001a2b4  lea     rcx, [rax+rcx*8]; Sid
0x18001a2b8  lea     rdx, [rbp+StringSid]; StringSid
0x18001a2bc  call    cs:__imp_ConvertSidToStringSidW
0x18001a2c3  nop     dword ptr [rax+rax+00h]
0x18001a2c8  test    eax, eax
0x18001a2ca  jz      short loc_18001A298
0x18001a2cc  mov     rcx, [rbp+StringSid]
0x18001a2d0  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001a2d4  mov     rdx, rax
0x18001a2d7  inc     rdx
0x18001a2da  cmp     [rcx+rdx*2], bx
0x18001a2de  jnz     short loc_18001A2D7
0x18001a2e0  mov     r8, [rbp+StringSecurityDescriptor]
0x18001a2e4  inc     rax
0x18001a2e7  cmp     [r8+rax*2], bx
0x18001a2ec  jnz     short loc_18001A2E4
0x18001a2ee  add     edx, eax
0x18001a2f0  mov     ecx, 40h ; '@'; uFlags
0x18001a2f5  lea     eax, ds:18h[rdx*2]
0x18001a2fc  mov     edx, eax; uBytes
0x18001a2fe  mov     [rbp+Length], eax
0x18001a301  call    cs:__imp_LocalAlloc
0x18001a308  nop     dword ptr [rax+rax+00h]
0x18001a30d  mov     rdi, rax
0x18001a310  test    rax, rax
0x18001a313  jz      loc_18001A23D
0x18001a319  mov     rax, [rbp+StringSid]
0x18001a31d  lea     r8, aSSS; "%s%s%s)"
0x18001a324  mov     edx, [rbp+Length]; unsigned __int64
0x18001a327  mov     rcx, rdi; unsigned __int16 *
0x18001a32a  mov     r9, [rbp+StringSecurityDescriptor]
0x18001a32e  mov     [rsp+40h+var_18], rax
0x18001a333  lea     rax, aA0xe; "(A;;0xe;;;"
0x18001a33a  mov     [rsp+40h+LengthNeeded], rax
0x18001a33f  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001a344  test    eax, eax
0x18001a346  js      loc_18001A23D
0x18001a34c  xor     r9d, r9d; SecurityDescriptorSize
0x18001a34f  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x18001a353  mov     rcx, rdi; StringSecurityDescriptor
0x18001a356  lea     edx, [r9+1]; StringSDRevision
0x18001a35a  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18001a361  nop     dword ptr [rax+rax+00h]
0x18001a366  test    eax, eax
0x18001a368  jz      loc_18001A298
0x18001a36e  mov     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x18001a372  mov     edx, 4; SecurityInformation
0x18001a377  mov     rcx, r15; Handle
0x18001a37a  call    cs:__imp_NtSetSecurityObject
0x18001a381  nop     dword ptr [rax+rax+00h]
0x18001a386  test    eax, eax
0x18001a388  jns     short loc_18001A39A
0x18001a38a  mov     ecx, eax; Status
0x18001a38c  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x18001a393  nop     dword ptr [rax+rax+00h]
0x18001a398  mov     ebx, eax
0x18001a39a  mov     rcx, rsi; hMem
0x18001a39d  call    cs:__imp_LocalFree
0x18001a3a4  nop     dword ptr [rax+rax+00h]
0x18001a3a9  mov     rcx, [rbp+StringSecurityDescriptor]; hMem
0x18001a3ad  call    cs:__imp_LocalFree
0x18001a3b4  nop     dword ptr [rax+rax+00h]
0x18001a3b9  mov     rcx, [rbp+StringSid]; hMem
0x18001a3bd  call    cs:__imp_LocalFree
0x18001a3c4  nop     dword ptr [rax+rax+00h]
0x18001a3c9  mov     rcx, rdi; hMem
0x18001a3cc  call    cs:__imp_LocalFree
0x18001a3d3  nop     dword ptr [rax+rax+00h]
0x18001a3d8  mov     rcx, [rbp+SecurityDescriptor]; hMem
0x18001a3dc  call    cs:__imp_LocalFree
0x18001a3e3  nop     dword ptr [rax+rax+00h]
0x18001a3e8  mov     eax, ebx
0x18001a3ea  mov     rbx, [rsp+40h+arg_0]
0x18001a3ef  add     rsp, 40h
0x18001a3f3  pop     r15
0x18001a3f5  pop     r14
0x18001a3f7  pop     rdi
0x18001a3f8  pop     rsi
0x18001a3f9  pop     rbp
0x18001a3fa  retn
```
