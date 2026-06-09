# PerfpInitializeInstallationMutex

- ea: `0x180030480`
- end: `0x1800306f1`
- name: `PerfpInitializeInstallationMutex`
- size: `625`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180030430`

## callees

- `0x18001cbbc`
- `0x180030480`
- `0x180065090`

## import_xrefs

- `ntdll!NtClose` at `0x1800305fc`
- `ntdll!NtClose` at `0x180030690`
- `ntdll!NtClose` at `0x1800305fc`
- `ntdll!NtClose` at `0x180030690`
- `ntdll!RtlCreateBoundaryDescriptor` at `0x180030553`
- `ntdll!RtlCreateBoundaryDescriptor` at `0x180030553`
- `ntdll!RtlAddSIDToBoundaryDescriptor` at `0x180030572`
- `ntdll!RtlAddSIDToBoundaryDescriptor` at `0x180030572`
- `ntdll!NtCreatePrivateNamespace` at `0x1800305d3`
- `ntdll!NtCreatePrivateNamespace` at `0x1800305d3`
- `ntdll!NtOpenPrivateNamespace` at `0x1800305b8`
- `ntdll!NtOpenPrivateNamespace` at `0x1800305b8`
- `ntdll!NtCreateMutant` at `0x180030665`
- `ntdll!NtCreateMutant` at `0x180030665`
- `ntdll!RtlDeleteBoundaryDescriptor` at `0x1800306b0`
- `ntdll!RtlDeleteBoundaryDescriptor` at `0x1800306b0`
- `ntdll!RtlNtStatusToDosError` at `0x18003057e`
- `ntdll!RtlNtStatusToDosError` at `0x18003057e`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18003053f`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18003053f`
- `KERNEL32!LocalFree` at `0x1800306be`
- `KERNEL32!LocalFree` at `0x1800306be`
- `KERNEL32!GetLastError` at `0x18003069f`
- `KERNEL32!GetLastError` at `0x18003069f`
- `KERNEL32!SetLastError` at `0x1800304e3`
- `KERNEL32!SetLastError` at `0x1800304e3`

## string_xrefs

- `0x18003061a`: `Installing`

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
  Handle = (HANDLE)qword_1800A3298;
  if ( qword_1800A3298 )
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
  v7 = (void *)_InterlockedCompareExchange64(&qword_1800A3298, (signed __int64)Handle, 0);
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
0x180030480  mov     [rsp-8+arg_8], rbx
0x180030485  mov     [rsp-8+arg_10], rsi
0x18003048a  push    rbp
0x18003048b  push    rdi
0x18003048c  push    r14
0x18003048e  lea     rbp, [rsp-47h]
0x180030493  sub     rsp, 0E0h
0x18003049a  mov     rax, cs:__security_cookie
0x1800304a1  xor     rax, rsp
0x1800304a4  mov     [rbp+57h+var_18], rax
0x1800304a8  xor     r14d, r14d
0x1800304ab  lea     rax, [rbp+57h+cbSid]
0x1800304af  mov     rsi, rcx
0x1800304b2  mov     [rsp+0F0h+var_C8], r14
0x1800304b7  lea     r9, aDAGaBaAGaSy; "D:(A;;GA;;;BA)(A;;GA;;;SY)"
0x1800304be  mov     [rsp+0F0h+var_D0], rax
0x1800304c3  xor     r8d, r8d
0x1800304c6  mov     qword ptr [rbp+57h+cbSid], r14
0x1800304ca  xor     edx, edx
0x1800304cc  mov     [rbp+57h+var_B0], r14
0x1800304d0  xor     ecx, ecx
0x1800304d2  mov     [rbp+57h+Handle], r14
0x1800304d6  mov     [rbp+57h+MutantHandle], r14
0x1800304da  call    LocalConvertStringSDToSD_Rev1
0x1800304df  mov     ecx, eax; dwErrCode
0x1800304e1  mov     ebx, eax
0x1800304e3  call    cs:__imp_SetLastError
0x1800304e9  mov     rdi, qword ptr [rbp+57h+cbSid]
0x1800304ed  test    ebx, ebx
0x1800304ef  jnz     loc_18003069F
0x1800304f5  mov     rax, cs:qword_1800A3298
0x1800304fc  mov     [rbp+57h+Handle], rax
0x180030500  test    rax, rax
0x180030503  jnz     loc_180030606
0x180030509  xorps   xmm0, xmm0
0x18003050c  mov     [rbp+57h+cbSid], 44h ; 'D'
0x180030513  lea     rax, aLoadperf; "LoadPerf"
0x18003051a  mov     [rbp+57h+var_A0], 120010h
0x180030522  lea     r9, [rbp+57h+cbSid]; cbSid
0x180030526  mov     [rbp+57h+var_98], rax
0x18003052a  lea     r8, [rbp+57h+pSid]; pSid
0x18003052e  xor     edx, edx; DomainSid
0x180030530  lea     ecx, [rbx+1Ah]; WellKnownSidType
0x180030533  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x180030537  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x18003053b  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18003053f  call    cs:__imp_CreateWellKnownSid
0x180030545  test    eax, eax
0x180030547  jz      loc_18003069F
0x18003054d  xor     edx, edx
0x18003054f  lea     rcx, [rbp+57h+var_A0]
0x180030553  call    cs:__imp_RtlCreateBoundaryDescriptor
0x180030559  mov     [rbp+57h+var_B0], rax
0x18003055d  test    rax, rax
0x180030560  jnz     short loc_18003056A
0x180030562  lea     ebx, [rax+0Eh]
0x180030565  jmp     loc_1800306A7
0x18003056a  lea     rdx, [rbp+57h+pSid]
0x18003056e  lea     rcx, [rbp+57h+var_B0]
0x180030572  call    cs:__imp_RtlAddSIDToBoundaryDescriptor
0x180030578  test    eax, eax
0x18003057a  jns     short loc_180030589
0x18003057c  mov     ecx, eax; Status
0x18003057e  call    cs:__imp_RtlNtStatusToDosError
0x180030584  jmp     loc_1800306A5
0x180030589  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180030590  mov     ebx, 6
0x180030595  mov     [rbp+57h+ObjectAttributes.RootDirectory], r14
0x180030599  mov     [rbp+57h+ObjectAttributes.Attributes], r14d
0x18003059d  mov     [rbp+57h+ObjectAttributes.ObjectName], r14
0x1800305a1  mov     [rbp+57h+ObjectAttributes.SecurityDescriptor], rdi
0x1800305a5  mov     [rbp+57h+ObjectAttributes.SecurityQualityOfService], r14
0x1800305a9  jmp     short loc_1800305C5
0x1800305ab  mov     r9, [rbp+57h+var_B0]
0x1800305af  lea     rcx, [rbp+57h+Handle]
0x1800305b3  xor     r8d, r8d
0x1800305b6  mov     edx, ebx
0x1800305b8  call    cs:__imp_NtOpenPrivateNamespace
0x1800305be  cmp     eax, 0C000003Ah
0x1800305c3  jnz     short loc_1800305E0
0x1800305c5  mov     r9, [rbp+57h+var_B0]
0x1800305c9  lea     r8, [rbp+57h+ObjectAttributes]
0x1800305cd  mov     edx, ebx
0x1800305cf  lea     rcx, [rbp+57h+Handle]
0x1800305d3  call    cs:__imp_NtCreatePrivateNamespace
0x1800305d9  cmp     eax, 0C0000035h
0x1800305de  jz      short loc_1800305AB
0x1800305e0  test    eax, eax
0x1800305e2  js      short loc_18003057C
0x1800305e4  mov     rcx, [rbp+57h+Handle]
0x1800305e8  xor     eax, eax
0x1800305ea  lock cmpxchg cs:qword_1800A3298, rcx
0x1800305f3  mov     rbx, rax
0x1800305f6  jz      short loc_180030606
0x1800305f8  mov     rcx, [rbp+57h+Handle]; Handle
0x1800305fc  call    cs:__imp_NtClose
0x180030602  mov     [rbp+57h+Handle], rbx
0x180030606  mov     rax, cs:hHandle
0x18003060d  mov     [rbp+57h+MutantHandle], rax
0x180030611  test    rax, rax
0x180030614  jnz     loc_18003069A
0x18003061a  lea     rax, aInstalling; "Installing"
0x180030621  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180030629  mov     [rbp+57h+var_98], rax
0x18003062d  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180030631  mov     rax, [rbp+57h+Handle]
0x180030635  lea     rcx, [rbp+57h+MutantHandle]; MutantHandle
0x180030639  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x18003063d  xor     r9d, r9d; InitialOwner
0x180030640  lea     rax, [rbp+57h+var_A0]
0x180030644  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 80h
0x18003064c  mov     edx, 100001h; DesiredAccess
0x180030651  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x180030655  mov     [rbp+57h+var_A0], 160014h
0x18003065d  mov     [rbp+57h+ObjectAttributes.SecurityDescriptor], rdi
0x180030661  mov     [rbp+57h+ObjectAttributes.SecurityQualityOfService], r14
0x180030665  call    cs:__imp_NtCreateMutant
0x18003066b  test    eax, eax
0x18003066d  jns     short loc_180030678
0x18003066f  mov     [rbp+57h+MutantHandle], r14
0x180030673  jmp     loc_18003057C
0x180030678  mov     rcx, [rbp+57h+MutantHandle]
0x18003067c  xor     eax, eax
0x18003067e  lock cmpxchg cs:hHandle, rcx
0x180030687  mov     rbx, rax
0x18003068a  jz      short loc_18003069A
0x18003068c  mov     rcx, [rbp+57h+MutantHandle]; Handle
0x180030690  call    cs:__imp_NtClose
0x180030696  mov     [rbp+57h+MutantHandle], rbx
0x18003069a  mov     ebx, r14d
0x18003069d  jmp     short loc_1800306A7
0x18003069f  call    cs:__imp_GetLastError
0x1800306a5  mov     ebx, eax
0x1800306a7  mov     rcx, [rbp+57h+var_B0]
0x1800306ab  test    rcx, rcx
0x1800306ae  jz      short loc_1800306B6
0x1800306b0  call    cs:__imp_RtlDeleteBoundaryDescriptor
0x1800306b6  test    rdi, rdi
0x1800306b9  jz      short loc_1800306C4
0x1800306bb  mov     rcx, rdi; hMem
0x1800306be  call    cs:__imp_LocalFree
0x1800306c4  mov     rax, [rbp+57h+MutantHandle]
0x1800306c8  mov     [rsi], rax
0x1800306cb  mov     eax, ebx
0x1800306cd  mov     rcx, [rbp+57h+var_18]
0x1800306d1  xor     rcx, rsp; StackCookie
0x1800306d4  call    __security_check_cookie
0x1800306d9  lea     r11, [rsp+0F0h+var_10]
0x1800306e1  mov     rbx, [r11+28h]
0x1800306e5  mov     rsi, [r11+30h]
0x1800306e9  mov     rsp, r11
0x1800306ec  pop     r14
0x1800306ee  pop     rdi
0x1800306ef  pop     rbp
0x1800306f0  retn
```
