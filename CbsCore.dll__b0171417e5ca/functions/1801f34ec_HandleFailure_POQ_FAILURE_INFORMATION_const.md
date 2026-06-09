# HandleFailure(_POQ_FAILURE_INFORMATION const &)

- ea: `0x1801f34ec`
- end: `0x1801f3ac7`
- name: `?HandleFailure@@YAJAEBU_POQ_FAILURE_INFORMATION@@@Z`
- size: `1499`
- prototype: `__int64 __fastcall(const struct _POQ_FAILURE_INFORMATION *)`
- caller_count: `1`
- callee_count: `9`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1801f5628`

## callees

- `0x180019bdc`
- `0x18003ec0c`
- `0x180070398`
- `0x1800704cc`
- `0x1800aa1a4`
- `0x1800eb920`
- `0x1800ef360`
- `0x1801f34ec`
- `0x1801f3cc4`

## import_xrefs

- `ntdll!NtClose` at `0x1801f363a`
- `ntdll!NtClose` at `0x1801f38e6`
- `ntdll!NtClose` at `0x1801f3917`
- `ntdll!NtClose` at `0x1801f39a7`
- `ntdll!NtClose` at `0x1801f3a1b`
- `ntdll!NtClose` at `0x1801f3a42`
- `ntdll!NtClose` at `0x1801f3aab`
- `ntdll!NtClose` at `0x1801f363a`
- `ntdll!NtClose` at `0x1801f38e6`
- `ntdll!NtClose` at `0x1801f3917`
- `ntdll!NtClose` at `0x1801f39a7`
- `ntdll!NtClose` at `0x1801f3a1b`
- `ntdll!NtClose` at `0x1801f3a42`
- `ntdll!NtClose` at `0x1801f3aab`
- `ntdll!NtOpenProcess` at `0x1801f3810`
- `ntdll!NtOpenProcess` at `0x1801f3810`
- `ntdll!NtQueryInformationFile` at `0x1801f3775`
- `ntdll!NtQueryInformationFile` at `0x1801f3775`
- `ntdll!NtOpenFile` at `0x1801f36d5`
- `ntdll!NtOpenFile` at `0x1801f36d5`
- `ntdll!NtQueryInformationProcess` at `0x1801f384e`
- `ntdll!NtQueryInformationProcess` at `0x1801f38a8`
- `ntdll!NtQueryInformationProcess` at `0x1801f384e`
- `ntdll!NtQueryInformationProcess` at `0x1801f38a8`

## string_xrefs

- `0x1801f370e`: `NtOpenFile( &FileHandle, (0x00100000L) | ( 0x0080 ), &ObjAttr, &IoStatusBlock, 0x00000001 | 0x00000002 | 0x00000004, 0x00000020 | 0x00004000)`
- `0x1801f3a7e`: `NtOpenProcess( &Process, (0x1000), &ProcessObjAttr, &ClientId)`
- `0x1801f37ae`: `NtQueryInformationFile( FileHandle, &IoStatusBlock, pInfo, cbInfoBlob, FileProcessIdsUsingFileInformation)`

## pseudocode

```c
__int64 __fastcall HandleFailure(const struct _POQ_FAILURE_INFORMATION *a1, __int64 a2, int a3, int a4)
{
  bool v5; // zf
  int v6; // ecx
  int v7; // ecx
  int v8; // ecx
  int v9; // ecx
  int v10; // ecx
  int v11; // ecx
  int v12; // ecx
  int v13; // ecx
  __int64 result; // rax
  char *UniqueProcess; // rax
  _WORD *v16; // rcx
  char *UniqueThread; // rdx
  _CLIENT_ID *p_ClientId; // rcx
  int inited; // ebx
  HANDLE v20; // rcx
  bool v21; // cc
  NTSTATUS v22; // eax
  _DWORD *v23; // rdi
  NTSTATUS v24; // eax
  int v25; // ebx
  NTSTATUS v26; // eax
  NTSTATUS v27; // eax
  int v28; // esi
  const struct _UNICODE_STRING *v29; // rsi
  void *v30; // rcx
  HANDLE v31; // rcx
  void *v32; // rcx
  void *v33; // rcx
  HANDLE v34; // rcx
  int v35; // eax
  void *v36; // rcx
  __int128 v37; // [rsp+40h] [rbp-C0h] BYREF
  PVOID ProcessInformation; // [rsp+50h] [rbp-B0h]
  const char *v39; // [rsp+58h] [rbp-A8h]
  const char *v40; // [rsp+60h] [rbp-A0h] BYREF
  const char *v41; // [rsp+68h] [rbp-98h]
  __int64 v42; // [rsp+70h] [rbp-90h]
  const char *v43; // [rsp+78h] [rbp-88h]
  __int128 v44; // [rsp+80h] [rbp-80h] BYREF
  PVOID FileInformation; // [rsp+90h] [rbp-70h]
  _CLIENT_ID ClientId; // [rsp+98h] [rbp-68h] BYREF
  _WORD *v47; // [rsp+A8h] [rbp-58h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+B0h] [rbp-50h] BYREF
  HANDLE Handle; // [rsp+E0h] [rbp-20h] BYREF
  void *ProcessHandle; // [rsp+E8h] [rbp-18h] BYREF
  int v51; // [rsp+F0h] [rbp-10h] BYREF
  ULONG ReturnLength; // [rsp+F4h] [rbp-Ch] BYREF
  __int128 v53; // [rsp+F8h] [rbp-8h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+108h] [rbp+8h] BYREF
  struct _OBJECT_ATTRIBUTES v55; // [rsp+118h] [rbp+18h] BYREF

  v5 = *(_DWORD *)a1 == -1073741757;
  v51 = 0;
  if ( !v5 && *(_DWORD *)a1 != -1072103423 )
    return 0;
  v6 = *((_DWORD *)a1 + 1);
  ProcessInformation = 0;
  v47 = 0;
  v37 = 0;
  ClientId = 0;
  v7 = v6 - 1;
  if ( v7 )
  {
    v8 = v7 - 1;
    if ( v8 )
    {
      v9 = v8 - 1;
      if ( !v9 )
        goto LABEL_26;
      v10 = v9 - 1;
      if ( v10 )
      {
        v11 = v10 - 2;
        if ( v11 )
        {
          v12 = v11 - 1;
          if ( v12 )
          {
            v13 = v12 - 1;
            if ( !v13 )
            {
              result = RtlSplitLUnicodeString(1, (int)a1 + 24, a3, a4, 44, (__int64)&v37, (__int64)&ClientId);
              if ( (int)result < 0 )
                return result;
              p_ClientId = (_CLIENT_ID *)&v37;
              goto LABEL_19;
            }
            if ( v13 != 9 )
              return 0;
            goto LABEL_11;
          }
        }
LABEL_26:
        p_ClientId = (_CLIENT_ID *)((char *)a1 + 24);
        goto LABEL_18;
      }
    }
  }
LABEL_11:
  result = RtlSplitLUnicodeString(1, (int)a1 + 24, a3, a4, 44, (__int64)&v37, (__int64)&ClientId);
  if ( (int)result < 0 )
    return result;
  UniqueProcess = (char *)ClientId.UniqueProcess;
  if ( ClientId.UniqueProcess )
  {
    v16 = v47;
    UniqueThread = (char *)ClientId.UniqueThread;
    do
    {
      if ( *v16 != 32 )
        break;
      UniqueThread -= 2;
      ++v16;
      UniqueProcess -= 2;
    }
    while ( UniqueProcess );
    ClientId.UniqueProcess = UniqueProcess;
    v47 = v16;
    ClientId.UniqueThread = UniqueThread;
  }
  p_ClientId = &ClientId;
LABEL_18:
  if ( !p_ClientId )
    return 0;
LABEL_19:
  Handle = 0;
  v53 = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  IoStatusBlock = 0;
  inited = RtlInitUnicodeStringFromLUnicodeString(p_ClientId, &v53);
  if ( inited < 0 )
    goto LABEL_20;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)&v53;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v22 = NtOpenFile(&Handle, 0x100080u, &ObjectAttributes, &IoStatusBlock, 7u, 0x4020u);
  if ( v22 < 0 )
  {
    ProcessInformation = (PVOID)1068;
    *(_QWORD *)&v37 = "onecore\\base\\wcp\\tools\\poqexec\\lib\\poqexec.cpp";
    *((_QWORD *)&v37 + 1) = "HandleFailure";
    v39 = "NtOpenFile( &FileHandle, (0x00100000L) | ( 0x0080 ), &ObjAttr, &IoStatusBlock, 0x00000001 | 0x00000002 | 0x000"
          "00004, 0x00000020 | 0x00004000)";
    inited = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
               &v51,
               &v37,
               (unsigned int)v22);
    goto LABEL_20;
  }
  FileInformation = 0;
  v44 = 0;
  inited = RtlAllocateLBlob(1024, &v44);
  if ( inited >= 0 )
  {
    v23 = FileInformation;
    v24 = NtQueryInformationFile(Handle, &IoStatusBlock, FileInformation, 0x400u, FileProcessIdsUsingFileInformation);
    if ( v24 < 0 )
    {
      ProcessInformation = (PVOID)1091;
      *(_QWORD *)&v37 = "onecore\\base\\wcp\\tools\\poqexec\\lib\\poqexec.cpp";
      *((_QWORD *)&v37 + 1) = "HandleFailure";
      v39 = "NtQueryInformationFile( FileHandle, &IoStatusBlock, pInfo, cbInfoBlob, FileProcessIdsUsingFileInformation)";
      inited = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
                 &v51,
                 &v37,
                 (unsigned int)v24);
      goto LABEL_30;
    }
    v25 = 0;
    if ( *v23 )
    {
      while ( 1 )
      {
        ProcessHandle = 0;
        *(_QWORD *)&v55.Length = 48;
        ClientId.UniqueThread = 0;
        memset(&v55.RootDirectory, 0, 40);
        ClientId.UniqueProcess = *(HANDLE *)&v23[2 * v25 + 2];
        v26 = NtOpenProcess(&ProcessHandle, 0x1000u, &v55, &ClientId);
        if ( v26 < 0 )
          break;
        ProcessInformation = 0;
        ReturnLength = 0;
        v37 = 0;
        v27 = NtQueryInformationProcess(ProcessHandle, ProcessImageFileName, 0, 0, &ReturnLength);
        if ( v27 != -2147483643 && v27 != -1073741789 && v27 != -1073741820 )
        {
          if ( v27 >= 0 )
          {
            INTERNAL_ERROR_ACTION(-1073741595);
            JUMPOUT(0x1801F3AC6LL);
          }
          v42 = 1131;
          v40 = "onecore\\base\\wcp\\tools\\poqexec\\lib\\poqexec.cpp";
          v41 = "HandleFailure";
          v43 = 0;
          goto LABEL_51;
        }
        v28 = RtlAllocateLBlob(ReturnLength, &v37);
        if ( v28 < 0 )
        {
          Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v37);
          v33 = ProcessHandle;
          if ( (char *)ProcessHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          {
            ProcessHandle = 0;
            NtClose(v33);
          }
          Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v44);
          v34 = Handle;
          if ( (char *)Handle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          {
            Handle = 0;
            NtClose(v34);
          }
          return (unsigned int)v28;
        }
        v29 = (const struct _UNICODE_STRING *)ProcessInformation;
        v27 = NtQueryInformationProcess(
                ProcessHandle,
                ProcessImageFileName,
                ProcessInformation,
                ReturnLength,
                &ReturnLength);
        if ( v27 < 0 )
        {
          v42 = 1142;
          v40 = "onecore\\base\\wcp\\tools\\poqexec\\lib\\poqexec.cpp";
          v41 = "HandleFailure";
          v43 = "NtQueryInformationProcess( Process, ProcessImageFileName, ProcessInfo.Buffer, cbProcessInfo, &cbProcessInfo)";
LABEL_51:
          inited = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
                     &v51,
                     &v40,
                     (unsigned int)v27);
          Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v37);
          v32 = ProcessHandle;
          if ( (char *)ProcessHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          {
            ProcessHandle = 0;
            NtClose(v32);
          }
          Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v44);
          v20 = Handle;
          v21 = (char *)Handle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL;
          goto LABEL_21;
        }
        if ( v29->Length )
          LogInterferingProcess(v29);
        Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v37);
        v30 = ProcessHandle;
        if ( (char *)ProcessHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        {
          ProcessHandle = 0;
          NtClose(v30);
        }
        if ( (unsigned int)++v25 >= *v23 )
          goto LABEL_45;
      }
      v42 = 1112;
      v40 = "onecore\\base\\wcp\\tools\\poqexec\\lib\\poqexec.cpp";
      v41 = "HandleFailure";
      v43 = "NtOpenProcess( &Process, (0x1000), &ProcessObjAttr, &ClientId)";
      v35 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
              &v51,
              &v40,
              (unsigned int)v26);
      v36 = ProcessHandle;
      inited = v35;
      if ( (char *)ProcessHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      {
        ProcessHandle = 0;
        NtClose(v36);
      }
      goto LABEL_30;
    }
LABEL_45:
    Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v44);
    v31 = Handle;
    if ( (char *)Handle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      Handle = 0;
      NtClose(v31);
    }
    return 0;
  }
LABEL_30:
  Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v44);
LABEL_20:
  v20 = Handle;
  v21 = (char *)Handle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL;
LABEL_21:
  if ( v21 )
  {
    Handle = 0;
    NtClose(v20);
  }
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x1801f34ec  mov     [rsp-8+arg_8], rbx
0x1801f34f1  mov     [rsp-8+arg_10], rsi
0x1801f34f6  push    rbp
0x1801f34f7  push    rdi
0x1801f34f8  push    r14
0x1801f34fa  lea     rbp, [rsp-50h]
0x1801f34ff  sub     rsp, 150h
0x1801f3506  mov     rax, cs:__security_cookie
0x1801f350d  xor     rax, rsp
0x1801f3510  mov     [rbp+60h+var_18], rax
0x1801f3514  xor     r14d, r14d
0x1801f3517  mov     rdx, rcx
0x1801f351a  cmp     dword ptr [rcx], 0C0000043h
0x1801f3520  mov     [rbp+60h+var_70], r14d
0x1801f3524  jz      short loc_1801F3532
0x1801f3526  cmp     dword ptr [rcx], 0C0190001h
0x1801f352c  jnz     loc_1801F3923
0x1801f3532  mov     ecx, [rcx+4]
0x1801f3535  xor     eax, eax
0x1801f3537  mov     [rsp+160h+ProcessInformation], rax
0x1801f353c  xorps   xmm0, xmm0
0x1801f353f  mov     [rbp+60h+var_B8], rax
0x1801f3543  xorps   xmm1, xmm1
0x1801f3546  movups  [rsp+160h+var_120], xmm0
0x1801f354b  movups  xmmword ptr [rbp+60h+ClientId.UniqueProcess], xmm1
0x1801f354f  sub     ecx, 1
0x1801f3552  jz      short loc_1801F358B
0x1801f3554  sub     ecx, 1
0x1801f3557  jz      short loc_1801F358B
0x1801f3559  sub     ecx, 1
0x1801f355c  jz      loc_1801F3689
0x1801f3562  sub     ecx, 1
0x1801f3565  jz      short loc_1801F358B
0x1801f3567  sub     ecx, 2
0x1801f356a  jz      loc_1801F3689
0x1801f3570  sub     ecx, 1
0x1801f3573  jz      loc_1801F3689
0x1801f3579  sub     ecx, 1
0x1801f357c  jz      loc_1801F364D
0x1801f3582  cmp     ecx, 9
0x1801f3585  jnz     loc_1801F3923
0x1801f358b  lea     rax, [rbp+60h+ClientId]
0x1801f358f  add     rdx, 18h
0x1801f3593  mov     [rsp+160h+var_130], rax
0x1801f3598  mov     ecx, 1
0x1801f359d  lea     rax, [rsp+160h+var_120]
0x1801f35a2  mov     qword ptr [rsp+160h+OpenOptions], rax
0x1801f35a7  mov     qword ptr [rsp+160h+ShareAccess], 2Ch ; ','
0x1801f35b0  call    RtlSplitLUnicodeString
0x1801f35b5  test    eax, eax
0x1801f35b7  js      loc_1801F3925
0x1801f35bd  mov     rax, [rbp+60h+ClientId.UniqueProcess]
0x1801f35c1  test    rax, rax
0x1801f35c4  jz      short loc_1801F35EE
0x1801f35c6  mov     rcx, [rbp+60h+var_B8]
0x1801f35ca  mov     rdx, [rbp+60h+ClientId.UniqueThread]
0x1801f35ce  cmp     word ptr [rcx], 20h ; ' '
0x1801f35d2  jnz     short loc_1801F35E2
0x1801f35d4  sub     rdx, 2
0x1801f35d8  add     rcx, 2
0x1801f35dc  sub     rax, 2
0x1801f35e0  jnz     short loc_1801F35CE
0x1801f35e2  mov     [rbp+60h+ClientId.UniqueProcess], rax
0x1801f35e6  mov     [rbp+60h+var_B8], rcx
0x1801f35ea  mov     [rbp+60h+ClientId.UniqueThread], rdx
0x1801f35ee  lea     rcx, [rbp+60h+ClientId]
0x1801f35f2  test    rcx, rcx
0x1801f35f5  jz      loc_1801F3923
0x1801f35fb  xorps   xmm1, xmm1
0x1801f35fe  mov     [rbp+60h+Handle], r14
0x1801f3602  xorps   xmm0, xmm0
0x1801f3605  lea     rdx, [rbp+60h+var_68]
0x1801f3609  movups  [rbp+60h+var_68], xmm0
0x1801f360d  movups  xmmword ptr [rbp+60h+ObjectAttributes.Length], xmm1
0x1801f3611  movups  xmmword ptr [rbp+60h+ObjectAttributes.ObjectName], xmm1
0x1801f3615  movups  xmmword ptr [rbp+60h+ObjectAttributes.SecurityDescriptor], xmm1
0x1801f3619  movups  xmmword ptr [rbp+60h+IoStatusBlock], xmm0
0x1801f361d  call    RtlInitUnicodeStringFromLUnicodeString
0x1801f3622  mov     ebx, eax
0x1801f3624  test    eax, eax
0x1801f3626  jns     short loc_1801F3692
0x1801f3628  mov     rcx, [rbp+60h+Handle]; Handle
0x1801f362c  lea     rdx, [rcx-1]
0x1801f3630  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1801f3634  ja      short loc_1801F3646
0x1801f3636  mov     [rbp+60h+Handle], r14
0x1801f363a  call    cs:__imp_NtClose
0x1801f3641  nop     dword ptr [rax+rax+00h]
0x1801f3646  mov     eax, ebx
0x1801f3648  jmp     loc_1801F3925
0x1801f364d  lea     rax, [rbp+60h+ClientId]
0x1801f3651  add     rdx, 18h
0x1801f3655  mov     [rsp+160h+var_130], rax
0x1801f365a  mov     ecx, 1
0x1801f365f  lea     rax, [rsp+160h+var_120]
0x1801f3664  mov     qword ptr [rsp+160h+OpenOptions], rax
0x1801f3669  mov     qword ptr [rsp+160h+ShareAccess], 2Ch ; ','
0x1801f3672  call    RtlSplitLUnicodeString
0x1801f3677  test    eax, eax
0x1801f3679  js      loc_1801F3925
0x1801f367f  lea     rcx, [rsp+160h+var_120]
0x1801f3684  jmp     loc_1801F35FB
0x1801f3689  lea     rcx, [rdx+18h]
0x1801f368d  jmp     loc_1801F35F2
0x1801f3692  lea     rax, [rbp+60h+var_68]
0x1801f3696  mov     [rsp+160h+OpenOptions], 4020h; OpenOptions
0x1801f369e  xorps   xmm0, xmm0
0x1801f36a1  mov     [rbp+60h+ObjectAttributes.ObjectName], rax
0x1801f36a5  lea     r9, [rbp+60h+IoStatusBlock]; IoStatusBlock
0x1801f36a9  mov     [rbp+60h+ObjectAttributes.Length], 30h ; '0'
0x1801f36b0  lea     r8, [rbp+60h+ObjectAttributes]; ObjectAttributes
0x1801f36b4  mov     [rbp+60h+ObjectAttributes.RootDirectory], r14
0x1801f36b8  mov     edx, 100080h; DesiredAccess
0x1801f36bd  mov     [rbp+60h+ObjectAttributes.Attributes], 40h ; '@'
0x1801f36c4  lea     rcx, [rbp+60h+Handle]; FileHandle
0x1801f36c8  mov     [rsp+160h+ShareAccess], 7; ShareAccess
0x1801f36d0  movdqu  xmmword ptr [rbp+60h+ObjectAttributes.SecurityDescriptor], xmm0
0x1801f36d5  call    cs:__imp_NtOpenFile
0x1801f36dc  nop     dword ptr [rax+rax+00h]
0x1801f36e1  test    eax, eax
0x1801f36e3  jns     short loc_1801F372A
0x1801f36e5  lea     rcx, aOnecoreBaseWcp_61; "onecore\\base\\wcp\\tools\\poqexec\\lib"...
0x1801f36ec  mov     [rsp+160h+ProcessInformation], 42Ch
0x1801f36f5  mov     qword ptr [rsp+160h+var_120], rcx
0x1801f36fa  lea     rdx, [rsp+160h+var_120]
0x1801f36ff  lea     rcx, aHandlefailure; "HandleFailure"
0x1801f3706  mov     r8d, eax
0x1801f3709  mov     qword ptr [rsp+160h+var_120+8], rcx
0x1801f370e  lea     rcx, aNtopenfileFile_0; "NtOpenFile( &FileHandle, (0x00100000L) "...
0x1801f3715  mov     [rsp+160h+var_108], rcx
0x1801f371a  lea     rcx, [rbp+60h+var_70]
0x1801f371e  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x1801f3723  mov     ebx, eax
0x1801f3725  jmp     loc_1801F3628
0x1801f372a  xorps   xmm0, xmm0
0x1801f372d  lea     rdx, [rbp+60h+var_E0]
0x1801f3731  xor     eax, eax
0x1801f3733  mov     esi, 400h
0x1801f3738  mov     ecx, esi
0x1801f373a  mov     [rbp+60h+FileInformation], rax
0x1801f373e  movups  [rbp+60h+var_E0], xmm0
0x1801f3742  call    RtlAllocateLBlob
0x1801f3747  mov     ebx, eax
0x1801f3749  test    eax, eax
0x1801f374b  jns     short loc_1801F375B
0x1801f374d  lea     rcx, [rbp+60h+var_E0]
0x1801f3751  call    ?Close@?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(void)
0x1801f3756  jmp     loc_1801F3628
0x1801f375b  mov     rdi, [rbp+60h+FileInformation]
0x1801f375f  lea     rdx, [rbp+60h+IoStatusBlock]; IoStatusBlock
0x1801f3763  mov     rcx, [rbp+60h+Handle]; FileHandle
0x1801f3767  mov     r8, rdi; FileInformation
0x1801f376a  mov     r9d, esi; Length
0x1801f376d  mov     [rsp+160h+ShareAccess], 2Fh ; '/'; FileInformationClass
0x1801f3775  call    cs:__imp_NtQueryInformationFile
0x1801f377c  nop     dword ptr [rax+rax+00h]
0x1801f3781  test    eax, eax
0x1801f3783  jns     short loc_1801F37C7
0x1801f3785  lea     rcx, aOnecoreBaseWcp_61; "onecore\\base\\wcp\\tools\\poqexec\\lib"...
0x1801f378c  mov     [rsp+160h+ProcessInformation], 443h
0x1801f3795  mov     qword ptr [rsp+160h+var_120], rcx
0x1801f379a  lea     rdx, [rsp+160h+var_120]
0x1801f379f  lea     rcx, aHandlefailure; "HandleFailure"
0x1801f37a6  mov     r8d, eax
0x1801f37a9  mov     qword ptr [rsp+160h+var_120+8], rcx
0x1801f37ae  lea     rcx, aNtqueryinforma_2; "NtQueryInformationFile( FileHandle, &Io"...
0x1801f37b5  mov     [rsp+160h+var_108], rcx
0x1801f37ba  lea     rcx, [rbp+60h+var_70]
0x1801f37be  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x1801f37c3  mov     ebx, eax
0x1801f37c5  jmp     short loc_1801F374D
0x1801f37c7  mov     ebx, r14d
0x1801f37ca  cmp     [rdi], r14d
0x1801f37cd  jbe     loc_1801F38FC
0x1801f37d3  xor     eax, eax
0x1801f37d5  mov     [rbp+60h+ProcessHandle], r14
0x1801f37d9  xorps   xmm0, xmm0
0x1801f37dc  mov     [rbp+60h+var_48.SecurityQualityOfService], rax
0x1801f37e0  mov     eax, ebx
0x1801f37e2  lea     r9, [rbp+60h+ClientId]; ClientId
0x1801f37e6  lea     r8, [rbp+60h+var_48]; ObjectAttributes
0x1801f37ea  mov     qword ptr [rbp+60h+var_48.Length], 30h ; '0'
0x1801f37f2  mov     edx, 1000h; DesiredAccess
0x1801f37f7  mov     [rbp+60h+ClientId.UniqueThread], r14
0x1801f37fb  movups  xmmword ptr [rbp+60h+var_48.RootDirectory], xmm0
0x1801f37ff  mov     rcx, [rdi+rax*8+8]
0x1801f3804  mov     [rbp+60h+ClientId.UniqueProcess], rcx
0x1801f3808  lea     rcx, [rbp+60h+ProcessHandle]; ProcessHandle
0x1801f380c  movups  xmmword ptr [rbp+60h+var_48.Attributes], xmm0
0x1801f3810  call    cs:__imp_NtOpenProcess
0x1801f3817  nop     dword ptr [rax+rax+00h]
0x1801f381c  test    eax, eax
0x1801f381e  js      loc_1801F3A55
0x1801f3824  mov     rcx, [rbp+60h+ProcessHandle]; ProcessHandle
0x1801f3828  xor     eax, eax
0x1801f382a  xor     r9d, r9d; ProcessInformationLength
0x1801f382d  mov     [rsp+160h+ProcessInformation], rax
0x1801f3832  xorps   xmm0, xmm0
0x1801f3835  mov     [rbp+60h+ReturnLength], r14d
0x1801f3839  lea     rax, [rbp+60h+ReturnLength]
0x1801f383d  xor     r8d, r8d; ProcessInformation
0x1801f3840  movups  [rsp+160h+var_120], xmm0
0x1801f3845  lea     edx, [r9+1Bh]; ProcessInformationClass
0x1801f3849  mov     qword ptr [rsp+160h+ShareAccess], rax; ReturnLength
0x1801f384e  call    cs:__imp_NtQueryInformationProcess
0x1801f3855  nop     dword ptr [rax+rax+00h]
0x1801f385a  cmp     eax, 80000005h
0x1801f385f  jz      short loc_1801F3873
0x1801f3861  cmp     eax, 0C0000023h
0x1801f3866  jz      short loc_1801F3873
0x1801f3868  cmp     eax, 0C0000004h
0x1801f386d  jnz     loc_1801F394A
0x1801f3873  mov     ecx, [rbp+60h+ReturnLength]
0x1801f3876  lea     rdx, [rsp+160h+var_120]
0x1801f387b  call    RtlAllocateLBlob
0x1801f3880  mov     esi, eax
0x1801f3882  test    eax, eax
0x1801f3884  js      loc_1801F39FF
0x1801f388a  mov     rsi, [rsp+160h+ProcessInformation]
0x1801f388f  lea     rax, [rbp+60h+ReturnLength]
0x1801f3893  mov     r9d, [rbp+60h+ReturnLength]; ProcessInformationLength
0x1801f3897  mov     r8, rsi; ProcessInformation
0x1801f389a  mov     rcx, [rbp+60h+ProcessHandle]; ProcessHandle
0x1801f389e  mov     edx, 1Bh; ProcessInformationClass
0x1801f38a3  mov     qword ptr [rsp+160h+ShareAccess], rax; ReturnLength
0x1801f38a8  call    cs:__imp_NtQueryInformationProcess
0x1801f38af  nop     dword ptr [rax+rax+00h]
0x1801f38b4  test    eax, eax
0x1801f38b6  js      loc_1801F39CD
0x1801f38bc  cmp     [rsi], r14w
0x1801f38c0  jbe     short loc_1801F38CA
0x1801f38c2  mov     rcx, rsi; struct _UNICODE_STRING *
0x1801f38c5  call    ?LogInterferingProcess@@YAXPEBU_UNICODE_STRING@@@Z; LogInterferingProcess(_UNICODE_STRING const *)
0x1801f38ca  lea     rcx, [rsp+160h+var_120]
0x1801f38cf  call    ?Close@?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(void)
0x1801f38d4  mov     rcx, [rbp+60h+ProcessHandle]; Handle
0x1801f38d8  lea     rax, [rcx-1]
0x1801f38dc  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1801f38e0  ja      short loc_1801F38F2
0x1801f38e2  mov     [rbp+60h+ProcessHandle], r14
0x1801f38e6  call    cs:__imp_NtClose
0x1801f38ed  nop     dword ptr [rax+rax+00h]
0x1801f38f2  inc     ebx
0x1801f38f4  cmp     ebx, [rdi]
0x1801f38f6  jb      loc_1801F37D3
0x1801f38fc  lea     rcx, [rbp+60h+var_E0]
0x1801f3900  call    ?Close@?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(void)
0x1801f3905  mov     rcx, [rbp+60h+Handle]; Handle
0x1801f3909  lea     rax, [rcx-1]
0x1801f390d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1801f3911  ja      short loc_1801F3923
0x1801f3913  mov     [rbp+60h+Handle], r14
0x1801f3917  call    cs:__imp_NtClose
0x1801f391e  nop     dword ptr [rax+rax+00h]
0x1801f3923  xor     eax, eax
0x1801f3925  mov     rcx, [rbp+60h+var_18]
0x1801f3929  xor     rcx, rsp; StackCookie
0x1801f392c  call    __security_check_cookie
0x1801f3931  lea     r11, [rsp+160h+var_10]
0x1801f3939  mov     rbx, [r11+28h]
0x1801f393d  mov     rsi, [r11+30h]
0x1801f3941  mov     rsp, r11
0x1801f3944  pop     r14
0x1801f3946  pop     rdi
0x1801f3947  pop     rbp
0x1801f3948  retn
0x1801f394a  test    eax, eax
0x1801f394c  jns     loc_1801F3ABC
0x1801f3952  lea     rcx, aOnecoreBaseWcp_61; "onecore\\base\\wcp\\tools\\poqexec\\lib"...
0x1801f3959  mov     [rsp+160h+var_F0], 46Bh
0x1801f3962  mov     [rsp+160h+var_100], rcx
0x1801f3967  lea     rcx, aHandlefailure; "HandleFailure"
0x1801f396e  mov     [rsp+160h+var_F8], rcx
0x1801f3973  mov     [rsp+160h+var_E8], r14
0x1801f3978  mov     r8d, eax
0x1801f397b  lea     rdx, [rsp+160h+var_100]
0x1801f3980  lea     rcx, [rbp+60h+var_70]
0x1801f3984  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x1801f3989  lea     rcx, [rsp+160h+var_120]
0x1801f398e  mov     ebx, eax
0x1801f3990  call    ?Close@?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(void)
0x1801f3995  mov     rcx, [rbp+60h+ProcessHandle]; Handle
0x1801f3999  lea     rdx, [rcx-1]
0x1801f399d  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1801f39a1  ja      short loc_1801F39B3
0x1801f39a3  mov     [rbp+60h+ProcessHandle], r14
0x1801f39a7  call    cs:__imp_NtClose
0x1801f39ae  nop     dword ptr [rax+rax+00h]
0x1801f39b3  lea     rcx, [rbp+60h+var_E0]
0x1801f39b7  call    ?Close@?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(void)
0x1801f39bc  mov     rcx, [rbp+60h+Handle]
0x1801f39c0  lea     rax, [rcx-1]
0x1801f39c4  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1801f39c8  jmp     loc_1801F3634
0x1801f39cd  lea     rcx, aOnecoreBaseWcp_61; "onecore\\base\\wcp\\tools\\poqexec\\lib"...
0x1801f39d4  mov     [rsp+160h+var_F0], 476h
0x1801f39dd  mov     [rsp+160h+var_100], rcx
0x1801f39e2  lea     rcx, aHandlefailure; "HandleFailure"
0x1801f39e9  mov     [rsp+160h+var_F8], rcx
0x1801f39ee  lea     rcx, aNtqueryinforma; "NtQueryInformationProcess( Process, Pro"...
  ... truncated ...
```
