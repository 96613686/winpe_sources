# PerfpInitializeInstallationMutex

- ea: `0x18003452c`
- end: `0x1800347ec`
- name: `PerfpInitializeInstallationMutex`
- size: `704`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800344d4`

## callees

- `0x18001b744`
- `0x18003452c`
- `0x1800720b0`

## import_xrefs

- `ntdll!NtClose` at `0x1800346d2`
- `ntdll!NtClose` at `0x180034772`
- `ntdll!NtClose` at `0x1800346d2`
- `ntdll!NtClose` at `0x180034772`
- `ntdll!RtlCreateBoundaryDescriptor` at `0x18003460b`
- `ntdll!RtlCreateBoundaryDescriptor` at `0x18003460b`
- `ntdll!RtlAddSIDToBoundaryDescriptor` at `0x180034630`
- `ntdll!RtlAddSIDToBoundaryDescriptor` at `0x180034630`
- `ntdll!NtCreatePrivateNamespace` at `0x1800346a3`
- `ntdll!NtCreatePrivateNamespace` at `0x1800346a3`
- `ntdll!NtOpenPrivateNamespace` at `0x180034682`
- `ntdll!NtOpenPrivateNamespace` at `0x180034682`
- `ntdll!NtCreateMutant` at `0x180034741`
- `ntdll!NtCreateMutant` at `0x180034741`
- `ntdll!RtlDeleteBoundaryDescriptor` at `0x18003479e`
- `ntdll!RtlDeleteBoundaryDescriptor` at `0x18003479e`
- `ntdll!RtlNtStatusToDosError` at `0x180034642`
- `ntdll!RtlNtStatusToDosError` at `0x180034642`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800345f1`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800345f1`
- `KERNEL32!LocalFree` at `0x1800347b2`
- `KERNEL32!LocalFree` at `0x1800347b2`
- `KERNEL32!GetLastError` at `0x180034787`
- `KERNEL32!GetLastError` at `0x180034787`
- `KERNEL32!SetLastError` at `0x18003458f`
- `KERNEL32!SetLastError` at `0x18003458f`

## string_xrefs

- `0x1800346f6`: `Installing`

## pseudocode

```c
__int64 __fastcall PerfpInitializeInstallationMutex(HANDLE *a1)
{
  DWORD v2; // ebx
  void *v3; // rdi
  unsigned int v4; // ebx
  int v5; // eax
  DWORD LastError; // eax
  void *v7; // rbx
  void *v8; // rbx
  HANDLE Handle; // [rsp+30h] [rbp-69h] BYREF
  HANDLE MutantHandle; // [rsp+38h] [rbp-61h] BYREF
  __int64 v12; // [rsp+40h] [rbp-59h] BYREF
  DWORD cbSid[2]; // [rsp+48h] [rbp-51h] BYREF
  __int64 v14; // [rsp+50h] [rbp-49h] BYREF
  const wchar_t *v15; // [rsp+58h] [rbp-41h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp-39h] BYREF
  _BYTE pSid[72]; // [rsp+90h] [rbp-9h] BYREF

  *(_QWORD *)cbSid = 0;
  v12 = 0;
  Handle = 0;
  MutantHandle = 0;
  v2 = LocalConvertStringSDToSD_Rev1(0, 0, 0, (unsigned int)L"D:(A;;GA;;;BA)(A;;GA;;;SY)", (__int64)cbSid, 0);
  SetLastError(v2);
  v3 = *(void **)cbSid;
  if ( v2 )
    goto LABEL_20;
  Handle = (HANDLE)qword_1800B2498;
  if ( qword_1800B2498 )
    goto LABEL_14;
  cbSid[0] = 68;
  v14 = 1179664;
  v15 = L"LoadPerf";
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  if ( !CreateWellKnownSid(WinBuiltinAdministratorsSid, 0, pSid, cbSid) )
  {
LABEL_20:
    LastError = GetLastError();
    goto LABEL_21;
  }
  v12 = RtlCreateBoundaryDescriptor(&v14, 0);
  if ( !v12 )
  {
    v4 = 14;
    goto LABEL_22;
  }
  v5 = RtlAddSIDToBoundaryDescriptor(&v12, pSid);
  if ( v5 < 0 )
    goto LABEL_7;
  ObjectAttributes.Length = 48;
  memset(&ObjectAttributes.RootDirectory, 0, 20);
  ObjectAttributes.SecurityDescriptor = v3;
  ObjectAttributes.SecurityQualityOfService = 0;
  do
  {
    v5 = NtCreatePrivateNamespace(&Handle, 6, &ObjectAttributes, v12);
    if ( v5 != -1073741771 )
      break;
    v5 = NtOpenPrivateNamespace(&Handle, 6, 0, v12);
  }
  while ( v5 == -1073741766 );
  if ( v5 < 0 )
    goto LABEL_7;
  v7 = (void *)_InterlockedCompareExchange64(&qword_1800B2498, (signed __int64)Handle, 0);
  if ( v7 )
  {
    NtClose(Handle);
    Handle = v7;
  }
LABEL_14:
  MutantHandle = hHandle;
  if ( hHandle )
  {
LABEL_19:
    v4 = 0;
    goto LABEL_22;
  }
  *(_QWORD *)&ObjectAttributes.Length = 48;
  v15 = L"Installing";
  ObjectAttributes.RootDirectory = Handle;
  *(_QWORD *)&ObjectAttributes.Attributes = 128;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)&v14;
  v14 = 1441812;
  ObjectAttributes.SecurityDescriptor = v3;
  ObjectAttributes.SecurityQualityOfService = 0;
  v5 = NtCreateMutant(&MutantHandle, 0x100001u, &ObjectAttributes, 0);
  if ( v5 >= 0 )
  {
    v8 = (void *)_InterlockedCompareExchange64((volatile signed __int64 *)&hHandle, (signed __int64)MutantHandle, 0);
    if ( v8 )
    {
      NtClose(MutantHandle);
      MutantHandle = v8;
    }
    goto LABEL_19;
  }
  MutantHandle = 0;
LABEL_7:
  LastError = RtlNtStatusToDosError(v5);
LABEL_21:
  v4 = LastError;
LABEL_22:
  if ( v12 )
    RtlDeleteBoundaryDescriptor();
  if ( v3 )
    LocalFree(v3);
  *a1 = MutantHandle;
  return v4;
}

```

## disassembly

```asm
0x18003452c  mov     [rsp-8+arg_8], rbx
0x180034531  mov     [rsp-8+arg_10], rsi
0x180034536  push    rbp
0x180034537  push    rdi
0x180034538  push    r14
0x18003453a  lea     rbp, [rsp-47h]
0x18003453f  sub     rsp, 0E0h
0x180034546  mov     rax, cs:__security_cookie
0x18003454d  xor     rax, rsp
0x180034550  mov     [rbp+57h+var_18], rax
0x180034554  xor     r14d, r14d
0x180034557  lea     rax, [rbp+57h+cbSid]
0x18003455b  mov     rsi, rcx
0x18003455e  mov     [rsp+0F0h+var_C8], r14
0x180034563  lea     r9, aDAGaBaAGaSy; "D:(A;;GA;;;BA)(A;;GA;;;SY)"
0x18003456a  mov     [rsp+0F0h+var_D0], rax
0x18003456f  xor     r8d, r8d
0x180034572  mov     qword ptr [rbp+57h+cbSid], r14
0x180034576  xor     edx, edx
0x180034578  mov     [rbp+57h+var_B0], r14
0x18003457c  xor     ecx, ecx
0x18003457e  mov     [rbp+57h+Handle], r14
0x180034582  mov     [rbp+57h+MutantHandle], r14
0x180034586  call    LocalConvertStringSDToSD_Rev1
0x18003458b  mov     ecx, eax; dwErrCode
0x18003458d  mov     ebx, eax
0x18003458f  call    cs:__imp_SetLastError
0x180034596  nop     dword ptr [rax+rax+00h]
0x18003459b  mov     rdi, qword ptr [rbp+57h+cbSid]
0x18003459f  test    ebx, ebx
0x1800345a1  jnz     loc_180034787
0x1800345a7  mov     rax, cs:qword_1800B2498
0x1800345ae  mov     [rbp+57h+Handle], rax
0x1800345b2  test    rax, rax
0x1800345b5  jnz     loc_1800346E2
0x1800345bb  xorps   xmm0, xmm0
0x1800345be  mov     [rbp+57h+cbSid], 44h ; 'D'
0x1800345c5  lea     rax, aLoadperf; "LoadPerf"
0x1800345cc  mov     [rbp+57h+var_A0], 120010h
0x1800345d4  lea     r9, [rbp+57h+cbSid]; cbSid
0x1800345d8  mov     [rbp+57h+var_98], rax
0x1800345dc  lea     r8, [rbp+57h+pSid]; pSid
0x1800345e0  xor     edx, edx; DomainSid
0x1800345e2  lea     ecx, [rbx+1Ah]; WellKnownSidType
0x1800345e5  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x1800345e9  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x1800345ed  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800345f1  call    cs:__imp_CreateWellKnownSid
0x1800345f8  nop     dword ptr [rax+rax+00h]
0x1800345fd  test    eax, eax
0x1800345ff  jz      loc_180034787
0x180034605  xor     edx, edx
0x180034607  lea     rcx, [rbp+57h+var_A0]
0x18003460b  call    cs:__imp_RtlCreateBoundaryDescriptor
0x180034612  nop     dword ptr [rax+rax+00h]
0x180034617  mov     [rbp+57h+var_B0], rax
0x18003461b  test    rax, rax
0x18003461e  jnz     short loc_180034628
0x180034620  lea     ebx, [rax+0Eh]
0x180034623  jmp     loc_180034795
0x180034628  lea     rdx, [rbp+57h+pSid]
0x18003462c  lea     rcx, [rbp+57h+var_B0]
0x180034630  call    cs:__imp_RtlAddSIDToBoundaryDescriptor
0x180034637  nop     dword ptr [rax+rax+00h]
0x18003463c  test    eax, eax
0x18003463e  jns     short loc_180034653
0x180034640  mov     ecx, eax; Status
0x180034642  call    cs:__imp_RtlNtStatusToDosError
0x180034649  nop     dword ptr [rax+rax+00h]
0x18003464e  jmp     loc_180034793
0x180034653  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18003465a  mov     ebx, 6
0x18003465f  mov     [rbp+57h+ObjectAttributes.RootDirectory], r14
0x180034663  mov     [rbp+57h+ObjectAttributes.Attributes], r14d
0x180034667  mov     [rbp+57h+ObjectAttributes.ObjectName], r14
0x18003466b  mov     [rbp+57h+ObjectAttributes.SecurityDescriptor], rdi
0x18003466f  mov     [rbp+57h+ObjectAttributes.SecurityQualityOfService], r14
0x180034673  jmp     short loc_180034695
0x180034675  mov     r9, [rbp+57h+var_B0]
0x180034679  lea     rcx, [rbp+57h+Handle]
0x18003467d  xor     r8d, r8d
0x180034680  mov     edx, ebx
0x180034682  call    cs:__imp_NtOpenPrivateNamespace
0x180034689  nop     dword ptr [rax+rax+00h]
0x18003468e  cmp     eax, 0C000003Ah
0x180034693  jnz     short loc_1800346B6
0x180034695  mov     r9, [rbp+57h+var_B0]
0x180034699  lea     r8, [rbp+57h+ObjectAttributes]
0x18003469d  mov     edx, ebx
0x18003469f  lea     rcx, [rbp+57h+Handle]
0x1800346a3  call    cs:__imp_NtCreatePrivateNamespace
0x1800346aa  nop     dword ptr [rax+rax+00h]
0x1800346af  cmp     eax, 0C0000035h
0x1800346b4  jz      short loc_180034675
0x1800346b6  test    eax, eax
0x1800346b8  js      short loc_180034640
0x1800346ba  mov     rcx, [rbp+57h+Handle]
0x1800346be  xor     eax, eax
0x1800346c0  lock cmpxchg cs:qword_1800B2498, rcx
0x1800346c9  mov     rbx, rax
0x1800346cc  jz      short loc_1800346E2
0x1800346ce  mov     rcx, [rbp+57h+Handle]; Handle
0x1800346d2  call    cs:__imp_NtClose
0x1800346d9  nop     dword ptr [rax+rax+00h]
0x1800346de  mov     [rbp+57h+Handle], rbx
0x1800346e2  mov     rax, cs:hHandle
0x1800346e9  mov     [rbp+57h+MutantHandle], rax
0x1800346ed  test    rax, rax
0x1800346f0  jnz     loc_180034782
0x1800346f6  lea     rax, aInstalling; "Installing"
0x1800346fd  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180034705  mov     [rbp+57h+var_98], rax
0x180034709  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18003470d  mov     rax, [rbp+57h+Handle]
0x180034711  lea     rcx, [rbp+57h+MutantHandle]; MutantHandle
0x180034715  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x180034719  xor     r9d, r9d; InitialOwner
0x18003471c  lea     rax, [rbp+57h+var_A0]
0x180034720  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 80h
0x180034728  mov     edx, 100001h; DesiredAccess
0x18003472d  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x180034731  mov     [rbp+57h+var_A0], 160014h
0x180034739  mov     [rbp+57h+ObjectAttributes.SecurityDescriptor], rdi
0x18003473d  mov     [rbp+57h+ObjectAttributes.SecurityQualityOfService], r14
0x180034741  call    cs:__imp_NtCreateMutant
0x180034748  nop     dword ptr [rax+rax+00h]
0x18003474d  test    eax, eax
0x18003474f  jns     short loc_18003475A
0x180034751  mov     [rbp+57h+MutantHandle], r14
0x180034755  jmp     loc_180034640
0x18003475a  mov     rcx, [rbp+57h+MutantHandle]
0x18003475e  xor     eax, eax
0x180034760  lock cmpxchg cs:hHandle, rcx
0x180034769  mov     rbx, rax
0x18003476c  jz      short loc_180034782
0x18003476e  mov     rcx, [rbp+57h+MutantHandle]; Handle
0x180034772  call    cs:__imp_NtClose
0x180034779  nop     dword ptr [rax+rax+00h]
0x18003477e  mov     [rbp+57h+MutantHandle], rbx
0x180034782  mov     ebx, r14d
0x180034785  jmp     short loc_180034795
0x180034787  call    cs:__imp_GetLastError
0x18003478e  nop     dword ptr [rax+rax+00h]
0x180034793  mov     ebx, eax
0x180034795  mov     rcx, [rbp+57h+var_B0]
0x180034799  test    rcx, rcx
0x18003479c  jz      short loc_1800347AA
0x18003479e  call    cs:__imp_RtlDeleteBoundaryDescriptor
0x1800347a5  nop     dword ptr [rax+rax+00h]
0x1800347aa  test    rdi, rdi
0x1800347ad  jz      short loc_1800347BE
0x1800347af  mov     rcx, rdi; hMem
0x1800347b2  call    cs:__imp_LocalFree
0x1800347b9  nop     dword ptr [rax+rax+00h]
0x1800347be  mov     rax, [rbp+57h+MutantHandle]
0x1800347c2  mov     [rsi], rax
0x1800347c5  mov     eax, ebx
0x1800347c7  mov     rcx, [rbp+57h+var_18]
0x1800347cb  xor     rcx, rsp; StackCookie
0x1800347ce  call    __security_check_cookie
0x1800347d3  lea     r11, [rsp+0F0h+var_10]
0x1800347db  mov     rbx, [r11+28h]
0x1800347df  mov     rsi, [r11+30h]
0x1800347e3  mov     rsp, r11
0x1800347e6  pop     r14
0x1800347e8  pop     rdi
0x1800347e9  pop     rbp
0x1800347ea  retn
```
