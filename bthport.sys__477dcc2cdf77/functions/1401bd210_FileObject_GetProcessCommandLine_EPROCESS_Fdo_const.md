# FileObject::GetProcessCommandLine(_EPROCESS *,Fdo const &)

- ea: `0x1401bd210`
- end: `0x1401bd587`
- name: `?GetProcessCommandLine@FileObject@@CA?AV?$unique_ptr@U_UNICODE_STRING@@U?$default_delete@U_UNICODE_STRING@@@utl@@@utl@@PEAU_EPROCESS@@AEBVFdo@@@Z`
- size: `887`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `reparse_path, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1401bd640`

## callees

- `0x140004368`
- `0x140005b4c`
- `0x140005c04`
- `0x14000f27c`
- `0x14000fab4`
- `0x14002a504`
- `0x14002b904`
- `0x1401bd210`

## import_xrefs

- `ntoskrnl!PsIsSystemProcess` at `0x1401bd236`
- `ntoskrnl!PsIsSystemProcess` at `0x1401bd236`
- `ntoskrnl!PsGetProcessId` at `0x1401bd2f8`
- `ntoskrnl!PsGetProcessId` at `0x1401bd2f8`
- `ntoskrnl!ZwOpenProcess` at `0x1401bd33f`
- `ntoskrnl!ZwOpenProcess` at `0x1401bd33f`
- `ntoskrnl!ZwQueryInformationProcess` at `0x1401bd3d5`
- `ntoskrnl!ZwQueryInformationProcess` at `0x1401bd4da`
- `ntoskrnl!ZwQueryInformationProcess` at `0x1401bd3d5`
- `ntoskrnl!ZwQueryInformationProcess` at `0x1401bd4da`
- `ntoskrnl!ExAllocatePool2` at `0x1401bd442`
- `ntoskrnl!ExAllocatePool2` at `0x1401bd442`

## pseudocode

```c
struct _UNICODE_STRING **__fastcall FileObject::GetProcessCommandLine(
        struct _UNICODE_STRING **a1,
        struct _KPROCESS *a2,
        Fdo *a3)
{
  struct _UNICODE_STRING *v6; // rax
  unsigned int v7; // eax
  int v8; // r8d
  __int64 v9; // r10
  int v10; // edx
  HANDLE ProcessId; // rax
  void **v12; // rax
  unsigned int RecorderLog; // eax
  int v14; // edx
  __int64 v15; // r10
  char v16; // r8
  __int64 v17; // r8
  char v18; // r8
  struct _UNICODE_STRING *Pool2; // rax
  struct _UNICODE_STRING *v20; // rbx
  unsigned int v21; // eax
  __int64 v22; // r8
  __int64 v23; // r10
  int v24; // edx
  unsigned int v25; // eax
  char v26; // r8
  __int64 v27; // r8
  __int64 v28; // r10
  int v29; // edx
  __int16 v31; // [rsp+30h] [rbp-29h]
  __int64 v32; // [rsp+40h] [rbp-19h]
  char v33; // [rsp+48h] [rbp-11h]
  char v34; // [rsp+48h] [rbp-11h]
  HANDLE ProcessHandle; // [rsp+50h] [rbp-9h] BYREF
  struct _UNICODE_STRING *v36; // [rsp+58h] [rbp-1h] BYREF
  struct _CLIENT_ID ClientId; // [rsp+60h] [rbp+7h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp+17h] BYREF
  ULONG ProcessInformationLength; // [rsp+D8h] [rbp+7Fh] BYREF

  if ( !(unsigned __int8)PsIsSystemProcess(a2) )
  {
    ProcessHandle = 0;
    memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
    ClientId = 0;
    ProcessId = PsGetProcessId(a2);
    ObjectAttributes.Length = 48;
    ClientId.UniqueProcess = ProcessId;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 512;
    ObjectAttributes.ObjectName = 0;
    v12 = (void **)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::put(&ProcessHandle);
    if ( ZwOpenProcess(v12, 0x400u, &ObjectAttributes, &ClientId) < 0 )
    {
      RecorderLog = (unsigned int)Fdo::GetRecorderLog(a3);
      v33 = v16;
      v17 = *(_QWORD *)a3;
      v32 = *(_QWORD *)a3;
      v31 = 12;
LABEL_8:
      LOBYTE(v17) = 1;
      WPP_RECORDER_AND_TRACE_SF_qL(
        *(_QWORD *)(v15 + 24),
        v14,
        v17,
        RecorderLog,
        2,
        1,
        v31,
        (__int64)WPP_9d7b86e5d28c327c9a158146e6f0aca1_Traceguids,
        v32,
        v33);
      *a1 = 0;
LABEL_18:
      wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&ProcessHandle);
      return a1;
    }
    ProcessInformationLength = 0;
    if ( ZwQueryInformationProcess(
           ProcessHandle,
           ProcessImageFileMapping|ProcessUserModeIOPL,
           0,
           0,
           &ProcessInformationLength) != -1073741820 )
    {
      RecorderLog = (unsigned int)Fdo::GetRecorderLog(a3);
      v33 = v18;
      v17 = *(_QWORD *)a3;
      v32 = *(_QWORD *)a3;
      v31 = 13;
      goto LABEL_8;
    }
    Pool2 = (struct _UNICODE_STRING *)ExAllocatePool2(64, ProcessInformationLength, 1346917442);
    v36 = Pool2;
    v20 = Pool2;
    if ( Pool2 )
    {
      if ( ZwQueryInformationProcess(
             ProcessHandle,
             ProcessImageFileMapping|ProcessUserModeIOPL,
             Pool2,
             ProcessInformationLength,
             0) >= 0 )
      {
        v36 = 0;
        *a1 = v20;
        goto LABEL_17;
      }
      v25 = (unsigned int)Fdo::GetRecorderLog(a3);
      v34 = v26;
      v27 = *(_QWORD *)a3;
      LOBYTE(v27) = 1;
      WPP_RECORDER_AND_TRACE_SF_qL(
        *(_QWORD *)(v28 + 24),
        v29,
        v27,
        v25,
        2,
        1,
        15,
        (__int64)WPP_9d7b86e5d28c327c9a158146e6f0aca1_Traceguids,
        *(_QWORD *)a3,
        v34);
    }
    else
    {
      v21 = (unsigned int)Fdo::GetRecorderLog(a3);
      v22 = *(_QWORD *)a3;
      LOBYTE(v22) = 1;
      WPP_RECORDER_AND_TRACE_SF_qL(
        *(_QWORD *)(v23 + 24),
        v24,
        v22,
        v21,
        2,
        1,
        14,
        (__int64)WPP_9d7b86e5d28c327c9a158146e6f0aca1_Traceguids,
        *(_QWORD *)a3,
        ProcessInformationLength);
    }
    *a1 = 0;
LABEL_17:
    utl::_UninitializedAllocation<utl::allocator<utl::_DlistNode<LESelectiveConnectionEstablishmentProcedure::ProcedureUpdateRequest>>>::~_UninitializedAllocation<utl::allocator<utl::_DlistNode<LESelectiveConnectionEstablishmentProcedure::ProcedureUpdateRequest>>>(&v36);
    goto LABEL_18;
  }
  utl::make_unique<_UNICODE_STRING,,0>(&v36);
  v6 = v36;
  if ( v36 )
  {
    v36 = 0;
    *v6 = FileObject::c_systemProcessName;
    *a1 = v6;
  }
  else
  {
    v7 = (unsigned int)Fdo::GetRecorderLog(a3);
    LOBYTE(v8) = 1;
    WPP_RECORDER_AND_TRACE_SF_q(
      *(_QWORD *)(v9 + 24),
      v10,
      v8,
      v7,
      2,
      1,
      11,
      (__int64)WPP_9d7b86e5d28c327c9a158146e6f0aca1_Traceguids,
      *(_QWORD *)a3);
    *a1 = 0;
  }
  utl::_UninitializedAllocation<utl::allocator<utl::_DlistNode<LESelectiveConnectionEstablishmentProcedure::ProcedureUpdateRequest>>>::~_UninitializedAllocation<utl::allocator<utl::_DlistNode<LESelectiveConnectionEstablishmentProcedure::ProcedureUpdateRequest>>>(&v36);
  return a1;
}

```

## disassembly

```asm
0x1401bd210  mov     [rsp-8+arg_0], rbx
0x1401bd215  mov     [rsp-8+arg_8], rsi
0x1401bd21a  push    rbp
0x1401bd21b  push    rdi
0x1401bd21c  push    r14
0x1401bd21e  lea     rbp, [rsp-47h]
0x1401bd223  sub     rsp, 0A0h
0x1401bd22a  mov     rdi, rcx
0x1401bd22d  mov     rsi, r8
0x1401bd230  mov     rcx, rdx
0x1401bd233  mov     rbx, rdx
0x1401bd236  call    cs:__imp_PsIsSystemProcess
0x1401bd23d  nop     dword ptr [rax+rax+00h]
0x1401bd242  xor     r14d, r14d
0x1401bd245  test    al, al
0x1401bd247  jz      loc_1401BD2DE
0x1401bd24d  lea     rcx, [rbp+57h+var_58]
0x1401bd251  call    ??$make_unique@U_UNICODE_STRING@@$$V$0A@@utl@@YA?AV?$unique_ptr@U_UNICODE_STRING@@U?$default_delete@U_UNICODE_STRING@@@utl@@@0@XZ; utl::make_unique<_UNICODE_STRING,,0>(void)
0x1401bd256  mov     rax, [rbp+57h+var_58]
0x1401bd25a  test    rax, rax
0x1401bd25d  jnz     short loc_1401BD2CA
0x1401bd25f  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1401bd266  mov     eax, [r10+2Ch]
0x1401bd26a  test    al, 1
0x1401bd26c  jz      short loc_1401BD277
0x1401bd26e  cmp     byte ptr [r10+29h], 2
0x1401bd273  mov     dl, 1
0x1401bd275  jnb     short loc_1401BD27A
0x1401bd277  mov     dl, r14b
0x1401bd27a  mov     rcx, rsi; this
0x1401bd27d  call    ?GetRecorderLog@Fdo@@QEBAPEAURECORDER_LOG__@@XZ; Fdo::GetRecorderLog(void)
0x1401bd282  mov     r9, [rsi]
0x1401bd285  lea     rcx, WPP_9d7b86e5d28c327c9a158146e6f0aca1_Traceguids
0x1401bd28c  mov     [rsp+0B0h+var_70], r9
0x1401bd291  mov     r8b, 1
0x1401bd294  mov     [rsp+0B0h+var_78], rcx
0x1401bd299  mov     r9, rax
0x1401bd29c  mov     rcx, [r10+18h]
0x1401bd2a0  mov     [rsp+0B0h+var_80], 0Bh
0x1401bd2a7  mov     [rsp+0B0h+var_88], 1
0x1401bd2af  mov     byte ptr [rsp+0B0h+ReturnLength], 2
0x1401bd2b4  call    WPP_RECORDER_AND_TRACE_SF_q
0x1401bd2b9  mov     [rdi], r14
0x1401bd2bc  lea     rcx, [rbp+57h+var_58]
0x1401bd2c0  call    ??1?$_UninitializedAllocation@V?$allocator@U?$_DlistNode@UProcedureUpdateRequest@LESelectiveConnectionEstablishmentProcedure@@@utl@@@utl@@@utl@@QEAA@XZ; utl::_UninitializedAllocation<utl::allocator<utl::_DlistNode<LESelectiveConnectionEstablishmentProcedure::ProcedureUpdateRequest>>>::~_UninitializedAllocation<utl::allocator<utl::_DlistNode<LESelectiveConnectionEstablishmentProcedure::ProcedureUpdateRequest>>>(void)
0x1401bd2c5  jmp     loc_1401BD56B
0x1401bd2ca  movups  xmm0, xmmword ptr cs:?c_systemProcessName@FileObject@@0U_UNICODE_STRING@@B; _UNICODE_STRING const FileObject::c_systemProcessName
0x1401bd2d1  mov     [rbp+57h+var_58], r14
0x1401bd2d5  movdqu  xmmword ptr [rax], xmm0
0x1401bd2d9  mov     [rdi], rax
0x1401bd2dc  jmp     short loc_1401BD2BC
0x1401bd2de  xorps   xmm0, xmm0
0x1401bd2e1  mov     [rbp+57h+ProcessHandle], r14
0x1401bd2e5  mov     rcx, rbx; Process
0x1401bd2e8  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x1401bd2ec  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x1401bd2f0  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1401bd2f4  movups  xmmword ptr [rbp+57h+ClientId.UniqueProcess], xmm0
0x1401bd2f8  call    cs:__imp_PsGetProcessId
0x1401bd2ff  nop     dword ptr [rax+rax+00h]
0x1401bd304  xorps   xmm0, xmm0
0x1401bd307  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1401bd30e  lea     rcx, [rbp+57h+ProcessHandle]
0x1401bd312  mov     [rbp+57h+ClientId.UniqueProcess], rax
0x1401bd316  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1401bd31b  mov     [rbp+57h+ObjectAttributes.RootDirectory], r14
0x1401bd31f  mov     [rbp+57h+ObjectAttributes.Attributes], 200h
0x1401bd326  mov     [rbp+57h+ObjectAttributes.ObjectName], r14
0x1401bd32a  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?ZwClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::put(void)
0x1401bd32f  lea     r9, [rbp+57h+ClientId]; ClientId
0x1401bd333  mov     edx, 400h; DesiredAccess
0x1401bd338  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1401bd33c  mov     rcx, rax; ProcessHandle
0x1401bd33f  call    cs:__imp_ZwOpenProcess
0x1401bd346  nop     dword ptr [rax+rax+00h]
0x1401bd34b  mov     r8d, eax
0x1401bd34e  test    eax, eax
0x1401bd350  jns     short loc_1401BD3BA
0x1401bd352  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1401bd359  mov     ecx, [r10+2Ch]
0x1401bd35d  test    cl, 1
0x1401bd360  jz      short loc_1401BD36B
0x1401bd362  cmp     byte ptr [r10+29h], 2
0x1401bd367  mov     dl, 1
0x1401bd369  jnb     short loc_1401BD36E
0x1401bd36b  mov     dl, r14b
0x1401bd36e  mov     rcx, rsi; this
0x1401bd371  call    ?GetRecorderLog@Fdo@@QEBAPEAURECORDER_LOG__@@XZ; Fdo::GetRecorderLog(void)
0x1401bd376  mov     dword ptr [rsp+0B0h+var_68], r8d
0x1401bd37b  lea     rcx, WPP_9d7b86e5d28c327c9a158146e6f0aca1_Traceguids
0x1401bd382  mov     r8, [rsi]
0x1401bd385  mov     [rsp+0B0h+var_70], r8
0x1401bd38a  mov     [rsp+0B0h+var_78], rcx
0x1401bd38f  mov     [rsp+0B0h+var_80], 0Ch
0x1401bd396  mov     rcx, [r10+18h]
0x1401bd39a  mov     r9, rax
0x1401bd39d  mov     [rsp+0B0h+var_88], 1
0x1401bd3a5  mov     r8b, 1
0x1401bd3a8  mov     byte ptr [rsp+0B0h+ReturnLength], 2
0x1401bd3ad  call    WPP_RECORDER_AND_TRACE_SF_qL
0x1401bd3b2  mov     [rdi], r14
0x1401bd3b5  jmp     loc_1401BD562
0x1401bd3ba  mov     rcx, [rbp+57h+ProcessHandle]; ProcessHandle
0x1401bd3be  lea     rax, [rbp+57h+ProcessInformationLength]
0x1401bd3c2  xor     r9d, r9d; ProcessInformationLength
0x1401bd3c5  mov     [rbp+57h+ProcessInformationLength], r14d
0x1401bd3c9  xor     r8d, r8d; ProcessInformation
0x1401bd3cc  mov     [rsp+0B0h+ReturnLength], rax; ReturnLength
0x1401bd3d1  lea     edx, [r9+3Ch]; ProcessInformationClass
0x1401bd3d5  call    cs:__imp_ZwQueryInformationProcess
0x1401bd3dc  nop     dword ptr [rax+rax+00h]
0x1401bd3e1  mov     r8d, eax
0x1401bd3e4  cmp     eax, 0C0000004h
0x1401bd3e9  jz      short loc_1401BD434
0x1401bd3eb  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1401bd3f2  mov     ecx, [r10+2Ch]
0x1401bd3f6  test    cl, 1
0x1401bd3f9  jz      short loc_1401BD404
0x1401bd3fb  cmp     byte ptr [r10+29h], 2
0x1401bd400  mov     dl, 1
0x1401bd402  jnb     short loc_1401BD407
0x1401bd404  mov     dl, r14b
0x1401bd407  mov     rcx, rsi; this
0x1401bd40a  call    ?GetRecorderLog@Fdo@@QEBAPEAURECORDER_LOG__@@XZ; Fdo::GetRecorderLog(void)
0x1401bd40f  mov     dword ptr [rsp+0B0h+var_68], r8d
0x1401bd414  lea     rcx, WPP_9d7b86e5d28c327c9a158146e6f0aca1_Traceguids
0x1401bd41b  mov     r8, [rsi]
0x1401bd41e  mov     [rsp+0B0h+var_70], r8
0x1401bd423  mov     [rsp+0B0h+var_78], rcx
0x1401bd428  mov     [rsp+0B0h+var_80], 0Dh
0x1401bd42f  jmp     loc_1401BD396
0x1401bd434  mov     edx, [rbp+57h+ProcessInformationLength]
0x1401bd437  mov     ecx, 40h ; '@'
0x1401bd43c  mov     r8d, 50485442h
0x1401bd442  call    cs:__imp_ExAllocatePool2
0x1401bd449  nop     dword ptr [rax+rax+00h]
0x1401bd44e  mov     [rbp+57h+var_58], rax
0x1401bd452  mov     rbx, rax
0x1401bd455  test    rax, rax
0x1401bd458  jnz     short loc_1401BD4C5
0x1401bd45a  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1401bd461  mov     eax, [r10+2Ch]
0x1401bd465  test    al, 1
0x1401bd467  jz      short loc_1401BD472
0x1401bd469  cmp     byte ptr [r10+29h], 2
0x1401bd46e  mov     dl, 1
0x1401bd470  jnb     short loc_1401BD475
0x1401bd472  mov     dl, r14b
0x1401bd475  mov     rcx, rsi; this
0x1401bd478  call    ?GetRecorderLog@Fdo@@QEBAPEAURECORDER_LOG__@@XZ; Fdo::GetRecorderLog(void)
0x1401bd47d  mov     r8d, [rbp+57h+ProcessInformationLength]
0x1401bd481  lea     rcx, WPP_9d7b86e5d28c327c9a158146e6f0aca1_Traceguids
0x1401bd488  mov     dword ptr [rsp+0B0h+var_68], r8d
0x1401bd48d  mov     r9, rax
0x1401bd490  mov     r8, [rsi]
0x1401bd493  mov     [rsp+0B0h+var_70], r8
0x1401bd498  mov     r8b, 1
0x1401bd49b  mov     [rsp+0B0h+var_78], rcx
0x1401bd4a0  mov     rcx, [r10+18h]
0x1401bd4a4  mov     [rsp+0B0h+var_80], 0Eh
0x1401bd4ab  mov     [rsp+0B0h+var_88], 1
0x1401bd4b3  mov     byte ptr [rsp+0B0h+ReturnLength], 2
0x1401bd4b8  call    WPP_RECORDER_AND_TRACE_SF_qL
0x1401bd4bd  mov     [rdi], r14
0x1401bd4c0  jmp     loc_1401BD559
0x1401bd4c5  mov     r9d, [rbp+57h+ProcessInformationLength]; ProcessInformationLength
0x1401bd4c9  mov     r8, rbx; ProcessInformation
0x1401bd4cc  mov     rcx, [rbp+57h+ProcessHandle]; ProcessHandle
0x1401bd4d0  mov     edx, 3Ch ; '<'; ProcessInformationClass
0x1401bd4d5  mov     [rsp+0B0h+ReturnLength], r14; ReturnLength
0x1401bd4da  call    cs:__imp_ZwQueryInformationProcess
0x1401bd4e1  nop     dword ptr [rax+rax+00h]
0x1401bd4e6  mov     r8d, eax
0x1401bd4e9  test    eax, eax
0x1401bd4eb  jns     short loc_1401BD552
0x1401bd4ed  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1401bd4f4  mov     ecx, [r10+2Ch]
0x1401bd4f8  test    cl, 1
0x1401bd4fb  jz      short loc_1401BD506
0x1401bd4fd  cmp     byte ptr [r10+29h], 2
0x1401bd502  mov     dl, 1
0x1401bd504  jnb     short loc_1401BD509
0x1401bd506  mov     dl, r14b
0x1401bd509  mov     rcx, rsi; this
0x1401bd50c  call    ?GetRecorderLog@Fdo@@QEBAPEAURECORDER_LOG__@@XZ; Fdo::GetRecorderLog(void)
0x1401bd511  mov     dword ptr [rsp+0B0h+var_68], r8d
0x1401bd516  lea     rcx, WPP_9d7b86e5d28c327c9a158146e6f0aca1_Traceguids
0x1401bd51d  mov     r8, [rsi]
0x1401bd520  mov     r9, rax
0x1401bd523  mov     [rsp+0B0h+var_70], r8
0x1401bd528  mov     r8b, 1
0x1401bd52b  mov     [rsp+0B0h+var_78], rcx
0x1401bd530  mov     rcx, [r10+18h]
0x1401bd534  mov     [rsp+0B0h+var_80], 0Fh
0x1401bd53b  mov     [rsp+0B0h+var_88], 1
0x1401bd543  mov     byte ptr [rsp+0B0h+ReturnLength], 2
0x1401bd548  call    WPP_RECORDER_AND_TRACE_SF_qL
0x1401bd54d  jmp     loc_1401BD4BD
0x1401bd552  mov     [rbp+57h+var_58], r14
0x1401bd556  mov     [rdi], rbx
0x1401bd559  lea     rcx, [rbp+57h+var_58]
0x1401bd55d  call    ??1?$_UninitializedAllocation@V?$allocator@U?$_DlistNode@UProcedureUpdateRequest@LESelectiveConnectionEstablishmentProcedure@@@utl@@@utl@@@utl@@QEAA@XZ; utl::_UninitializedAllocation<utl::allocator<utl::_DlistNode<LESelectiveConnectionEstablishmentProcedure::ProcedureUpdateRequest>>>::~_UninitializedAllocation<utl::allocator<utl::_DlistNode<LESelectiveConnectionEstablishmentProcedure::ProcedureUpdateRequest>>>(void)
0x1401bd562  lea     rcx, [rbp+57h+ProcessHandle]
0x1401bd566  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?ZwClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1401bd56b  lea     r11, [rsp+0B0h+var_10]
0x1401bd573  mov     rax, rdi
0x1401bd576  mov     rbx, [r11+20h]
0x1401bd57a  mov     rsi, [r11+28h]
0x1401bd57e  mov     rsp, r11
0x1401bd581  pop     r14
0x1401bd583  pop     rdi
0x1401bd584  pop     rbp
0x1401bd585  retn
```
