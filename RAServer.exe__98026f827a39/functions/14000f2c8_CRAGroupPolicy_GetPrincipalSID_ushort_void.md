# CRAGroupPolicy::GetPrincipalSID(ushort *,void * *)

- ea: `0x14000f2c8`
- end: `0x14000f452`
- name: `?GetPrincipalSID@CRAGroupPolicy@@AEAAKPEAGPEAPEAX@Z`
- size: `394`
- prototype: `__int64 __fastcall(CRAGroupPolicy *this, unsigned __int16 *, void **)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14000fc0c`
- `0x14000fcf4`

## callees

- `0x14000f2c8`
- `0x140015240`
- `0x140015aa0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14000f33e`
- `KERNEL32!GetLastError` at `0x14000f3d9`
- `KERNEL32!GetLastError` at `0x14000f33e`
- `KERNEL32!GetLastError` at `0x14000f3d9`
- `KERNEL32!HeapAlloc` at `0x14000f368`
- `KERNEL32!HeapAlloc` at `0x14000f368`
- `KERNEL32!GetProcessHeap` at `0x14000f35a`
- `KERNEL32!GetProcessHeap` at `0x14000f413`
- `KERNEL32!GetProcessHeap` at `0x14000f35a`
- `KERNEL32!GetProcessHeap` at `0x14000f413`
- `KERNEL32!HeapFree` at `0x14000f421`
- `KERNEL32!HeapFree` at `0x14000f421`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x14000f338`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x14000f3cf`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x14000f338`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x14000f3cf`

## string_xrefs

- `0x14000f390`: `base\diagnosis\ra\dcom\src\gpsettings.cpp`
- `0x14000f3f6`: `base\diagnosis\ra\dcom\src\gpsettings.cpp`
- `0x14000f376`: `CRAGroupPolicy::GetPrincipalSID`
- `0x14000f3e7`: `CRAGroupPolicy::GetPrincipalSID`

## pseudocode

```c
__int64 __fastcall CRAGroupPolicy::GetPrincipalSID(CRAGroupPolicy *this, unsigned __int16 *a2, void **a3)
{
  const struct _EVENT_DESCRIPTOR *v5; // rdx
  DWORD LastError; // ebx
  unsigned int v7; // r9d
  DWORD v8; // ebx
  HANDLE ProcessHeap; // rax
  void *v10; // rax
  const struct _EVENT_DESCRIPTOR *v11; // rdx
  void *v12; // rdi
  HANDLE v13; // rax
  DWORD cchReferencedDomainName; // [rsp+30h] [rbp-D0h] BYREF
  DWORD cbSid; // [rsp+34h] [rbp-CCh] BYREF
  enum _SID_NAME_USE peUse; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR ReferencedDomainName[512]; // [rsp+40h] [rbp-C0h] BYREF

  *a3 = 0;
  peUse = 0;
  cbSid = 0;
  cchReferencedDomainName = 512;
  LookupAccountNameLocalW(a2, 0, &cbSid, ReferencedDomainName, &cchReferencedDomainName, &peUse);
  LastError = GetLastError();
  if ( LastError != 122 )
  {
    v7 = 1448;
LABEL_7:
    CEventLogger::LogError(
      (CEventLogger *)L"CRAGroupPolicy::GetPrincipalSID",
      v5,
      L"base\\diagnosis\\ra\\dcom\\src\\gpsettings.cpp",
      v7,
      L"CRAGroupPolicy::GetPrincipalSID",
      0);
    if ( !LastError )
      return LastError;
    goto LABEL_8;
  }
  v8 = cbSid;
  ProcessHeap = GetProcessHeap();
  v10 = HeapAlloc(ProcessHeap, 0, v8);
  *a3 = v10;
  if ( v10 )
  {
    cchReferencedDomainName = 512;
    LastError = 0;
    if ( LookupAccountNameLocalW(a2, v10, &cbSid, ReferencedDomainName, &cchReferencedDomainName, &peUse) )
      return LastError;
    LastError = GetLastError();
    v7 = 1471;
    goto LABEL_7;
  }
  LastError = 8;
  CEventLogger::LogError(
    (CEventLogger *)L"CRAGroupPolicy::GetPrincipalSID",
    v11,
    L"base\\diagnosis\\ra\\dcom\\src\\gpsettings.cpp",
    0x5B1u,
    L"CRAGroupPolicy::GetPrincipalSID",
    0x8007000E);
LABEL_8:
  v12 = *a3;
  if ( *a3 )
  {
    v13 = GetProcessHeap();
    HeapFree(v13, 0, v12);
    *a3 = 0;
  }
  return LastError;
}

```

## disassembly

```asm
0x14000f2c8  mov     [rsp-8+arg_0], rbx
0x14000f2cd  push    rbp
0x14000f2ce  push    rsi
0x14000f2cf  push    rdi
0x14000f2d0  lea     rbp, [rsp-350h]
0x14000f2d8  sub     rsp, 450h
0x14000f2df  mov     rax, cs:__security_cookie
0x14000f2e6  xor     rax, rsp
0x14000f2e9  mov     [rbp+360h+var_20], rax
0x14000f2f0  mov     rdi, rdx
0x14000f2f3  mov     qword ptr [r8], 0
0x14000f2fa  lea     rax, [rsp+460h+var_428]
0x14000f2ff  mov     [rsp+460h+var_428], 0
0x14000f307  mov     [rsp+460h+peUse], rax; peUse
0x14000f30c  lea     r9, [rsp+460h+ReferencedDomainName]; ReferencedDomainName
0x14000f311  lea     rax, [rsp+460h+var_430]
0x14000f316  mov     [rsp+460h+cbSid], 0
0x14000f31e  mov     rsi, r8
0x14000f321  mov     [rsp+460h+cchReferencedDomainName], rax; cchReferencedDomainName
0x14000f326  lea     r8, [rsp+460h+cbSid]; cbSid
0x14000f32b  mov     [rsp+460h+var_430], 200h
0x14000f333  xor     edx, edx; Sid
0x14000f335  mov     rcx, rdi; lpAccountName
0x14000f338  call    cs:__imp_LookupAccountNameLocalW
0x14000f33e  call    cs:__imp_GetLastError
0x14000f344  mov     ebx, eax
0x14000f346  cmp     eax, 7Ah ; 'z'
0x14000f349  jz      short loc_14000F356
0x14000f34b  mov     r9d, 5A8h
0x14000f351  jmp     loc_14000F3E7
0x14000f356  mov     ebx, [rsp+460h+cbSid]
0x14000f35a  call    cs:__imp_GetProcessHeap
0x14000f360  mov     r8d, ebx; dwBytes
0x14000f363  xor     edx, edx; dwFlags
0x14000f365  mov     rcx, rax; hHeap
0x14000f368  call    cs:__imp_HeapAlloc
0x14000f36e  mov     [rsi], rax
0x14000f371  test    rax, rax
0x14000f374  jnz     short loc_14000F3A1
0x14000f376  lea     rcx, aCragrouppolicy_10; "CRAGroupPolicy::GetPrincipalSID"
0x14000f37d  mov     dword ptr [rsp+460h+peUse], 8007000Eh; unsigned int
0x14000f385  mov     r9d, 5B1h; unsigned int
0x14000f38b  mov     [rsp+460h+cchReferencedDomainName], rcx; unsigned __int16 *
0x14000f390  lea     r8, aBaseDiagnosisR_5; "base\\diagnosis\\ra\\dcom\\src\\gpsetti"...
0x14000f397  lea     ebx, [rax+8]
0x14000f39a  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14000f39f  jmp     short loc_14000F40B
0x14000f3a1  lea     rcx, [rsp+460h+var_428]
0x14000f3a6  mov     [rsp+460h+var_430], 200h
0x14000f3ae  mov     [rsp+460h+peUse], rcx; peUse
0x14000f3b3  lea     r9, [rsp+460h+ReferencedDomainName]; ReferencedDomainName
0x14000f3b8  lea     rcx, [rsp+460h+var_430]
0x14000f3bd  mov     rdx, rax; Sid
0x14000f3c0  mov     [rsp+460h+cchReferencedDomainName], rcx; cchReferencedDomainName
0x14000f3c5  lea     r8, [rsp+460h+cbSid]; cbSid
0x14000f3ca  mov     rcx, rdi; lpAccountName
0x14000f3cd  xor     ebx, ebx
0x14000f3cf  call    cs:__imp_LookupAccountNameLocalW
0x14000f3d5  test    eax, eax
0x14000f3d7  jnz     short loc_14000F42E
0x14000f3d9  call    cs:__imp_GetLastError
0x14000f3df  mov     ebx, eax
0x14000f3e1  mov     r9d, 5BFh; unsigned int
0x14000f3e7  lea     rcx, aCragrouppolicy_10; "CRAGroupPolicy::GetPrincipalSID"
0x14000f3ee  mov     dword ptr [rsp+460h+peUse], 0; unsigned int
0x14000f3f6  lea     r8, aBaseDiagnosisR_5; "base\\diagnosis\\ra\\dcom\\src\\gpsetti"...
0x14000f3fd  mov     [rsp+460h+cchReferencedDomainName], rcx; unsigned __int16 *
0x14000f402  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14000f407  test    ebx, ebx
0x14000f409  jz      short loc_14000F42E
0x14000f40b  mov     rdi, [rsi]
0x14000f40e  test    rdi, rdi
0x14000f411  jz      short loc_14000F42E
0x14000f413  call    cs:__imp_GetProcessHeap
0x14000f419  mov     r8, rdi; lpMem
0x14000f41c  xor     edx, edx; dwFlags
0x14000f41e  mov     rcx, rax; hHeap
0x14000f421  call    cs:__imp_HeapFree
0x14000f427  mov     qword ptr [rsi], 0
0x14000f42e  mov     eax, ebx
0x14000f430  mov     rcx, [rbp+360h+var_20]
0x14000f437  xor     rcx, rsp; StackCookie
0x14000f43a  call    __security_check_cookie
0x14000f43f  mov     rbx, [rsp+460h+arg_0]
0x14000f447  add     rsp, 450h
0x14000f44e  pop     rdi
0x14000f44f  pop     rsi
0x14000f450  pop     rbp
0x14000f451  retn
```
