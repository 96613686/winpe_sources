# DriverUtil::GetStablePath(_UNICODE_STRING const *,_UNICODE_STRING *,_UNICODE_STRING *,uchar)

- ea: `0x18004df24`
- end: `0x18004e27f`
- name: `?GetStablePath@DriverUtil@@YAJPEBU_UNICODE_STRING@@PEAU2@1E@Z`
- size: `859`
- prototype: `__int64 __fastcall(const UNICODE_STRING *this, struct _UNICODE_STRING *, struct _UNICODE_STRING *, struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18004e288`

## callees

- `0x18004da60`
- `0x18004dc58`
- `0x18004df24`
- `0x18004edf0`
- `0x180050198`
- `0x180050300`

## import_xrefs

- `ntdll!RtlStringFromGUID` at `0x18004e0ea`
- `ntdll!RtlStringFromGUID` at `0x18004e0ea`
- `ntdll!RtlAllocateHeap` at `0x18004e142`
- `ntdll!RtlAllocateHeap` at `0x18004e142`
- `ntdll!RtlFreeHeap` at `0x18004e1fe`
- `ntdll!RtlFreeHeap` at `0x18004e254`
- `ntdll!RtlFreeHeap` at `0x18004e1fe`
- `ntdll!RtlFreeHeap` at `0x18004e254`
- `ntdll!RtlFreeUnicodeString` at `0x18004e21d`
- `ntdll!RtlFreeUnicodeString` at `0x18004e21d`
- `ntdll!NtOpenFile` at `0x18004e03d`
- `ntdll!NtOpenFile` at `0x18004e03d`
- `ntdll!RtlCopyUnicodeString` at `0x18004e178`
- `ntdll!RtlCopyUnicodeString` at `0x18004e178`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18004e18d`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18004e1c7`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18004e18d`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18004e1c7`
- `ntdll!NtClose` at `0x18004e22c`
- `ntdll!NtClose` at `0x18004e22c`
- `ntdll!NtDeviceIoControlFile` at `0x18004e098`
- `ntdll!NtDeviceIoControlFile` at `0x18004e098`

## string_xrefs

- `0x18004dfb5`: `WinSetupMon::GetStablePath: Failed GetNtPath [%wZ] (0x%08X)`
- `0x18004e0d6`: `WinSetupMon::GetStablePath: Failed NtDeviceIoControlFile [%wZ] (0x%08X)`
- `0x18004e04d`: `WinSetupMon::GetStablePath: Failed NtOpenFile [%wZ] (0x%08X)`
- `0x18004e151`: `WinSetupMon::GetStablePath: Failed to allocate StablePath buffer`
- `0x18004e0f9`: `WinSetupMon::GetStablePath: Failed RtlStringFromGUID (0x%08X)`
- `0x18004e19d`: `WinSetupMon::GetStablePath: Failed RtlAppendUnicodeStringToString [%wZ] (0x%08X)`

## pseudocode

```c
__int64 __fastcall DriverUtil::GetStablePath(
        const UNICODE_STRING *this,
        struct _UNICODE_STRING *a2,
        struct _UNICODE_STRING *a3,
        struct _UNICODE_STRING *a4)
{
  int NtPath; // eax
  NTSTATUS appended; // ebx
  const char *v8; // rdx
  NTSTATUS v9; // eax
  WCHAR *Heap; // rax
  USHORT Length; // ax
  PWSTR Buffer; // r8
  PVOID P[2]; // [rsp+58h] [rbp-71h] BYREF
  void *FileHandle; // [rsp+68h] [rbp-61h] BYREF
  UNICODE_STRING Source; // [rsp+70h] [rbp-59h] BYREF
  struct _UNICODE_STRING GuidString; // [rsp+80h] [rbp-49h] BYREF
  struct _UNICODE_STRING v18; // [rsp+90h] [rbp-39h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+A0h] [rbp-29h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+B0h] [rbp-19h] BYREF
  GUID Guid; // [rsp+E0h] [rbp+17h] BYREF

  a2->Buffer = 0;
  FileHandle = 0;
  *(_OWORD *)P = 0;
  v18 = 0;
  Source = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  IoStatusBlock = 0;
  Guid = 0;
  GuidString = 0;
  NtPath = DriverUtil::GetNtPath(this, (PUNICODE_STRING)P, &v18, a4);
  appended = NtPath;
  if ( NtPath < 0 )
  {
    if ( NtPath == -1073741637 )
    {
LABEL_25:
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SetupPlatform_WinSetupBootVolumeIssue>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Servicing_SetupPlatform_WinSetupBootVolumeIssue>::GetImpl'::`2'::impl);
      Buffer = a2->Buffer;
      if ( Buffer )
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Buffer);
      *a2 = 0;
      if ( a3 )
        *a3 = 0;
      goto LABEL_29;
    }
    v8 = "WinSetupMon::GetStablePath: Failed GetNtPath [%wZ] (0x%08X)";
LABEL_4:
    WriteLog(0, v8);
    goto LABEL_25;
  }
  Source.Length = LOWORD(P[0]) - v18.Length;
  if ( LOWORD(P[0]) != v18.Length )
  {
    Source.MaximumLength = WORD1(P[0]) - v18.Length;
    Source.Buffer = (PWSTR)((char *)P[1] + 2 * ((unsigned __int64)v18.Length >> 1));
  }
  ObjectAttributes.ObjectName = &v18;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  appended = NtOpenFile(&FileHandle, 0x80u, &ObjectAttributes, &IoStatusBlock, 3u, 0x4000u);
  if ( appended < 0 )
  {
    v8 = "WinSetupMon::GetStablePath: Failed NtOpenFile [%wZ] (0x%08X)";
    goto LABEL_4;
  }
  appended = NtDeviceIoControlFile(FileHandle, 0, 0, 0, &IoStatusBlock, 0x4D0018u, 0, 0, &Guid, 0x10u);
  if ( (unsigned int)(appended + 0x3FFFFFFF) <= 1 || appended == -1073741808 )
  {
    appended = -1073741637;
    goto LABEL_25;
  }
  if ( appended < 0 )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs();
    if ( appended == -1073741637 )
      goto LABEL_25;
    v8 = "WinSetupMon::GetStablePath: Failed NtDeviceIoControlFile [%wZ] (0x%08X)";
    goto LABEL_4;
  }
  v9 = RtlStringFromGUID(&Guid, &GuidString);
  appended = v9;
  if ( v9 < 0 )
  {
    WriteLog(0, "WinSetupMon::GetStablePath: Failed RtlStringFromGUID (0x%08X)", v9);
    goto LABEL_25;
  }
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SetupPlatform_WinSetupBootVolumeIssue>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Servicing_SetupPlatform_WinSetupBootVolumeIssue>::GetImpl'::`2'::impl);
  a2->MaximumLength = Source.Length + GuidString.Length + 20;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SetupPlatform_WinSetupBootVolumeIssue>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Servicing_SetupPlatform_WinSetupBootVolumeIssue>::GetImpl'::`2'::impl);
  Heap = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, a2->MaximumLength);
  a2->Buffer = Heap;
  if ( !Heap )
  {
    WriteLog(0, "WinSetupMon::GetStablePath: Failed to allocate StablePath buffer");
    appended = -1073741670;
    goto LABEL_25;
  }
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SetupPlatform_WinSetupBootVolumeIssue>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Servicing_SetupPlatform_WinSetupBootVolumeIssue>::GetImpl'::`2'::impl);
  RtlCopyUnicodeString(a2, &SourceString);
  a2->Length -= 2;
  appended = RtlAppendUnicodeStringToString(a2, &GuidString);
  if ( appended < 0 )
    goto LABEL_19;
  if ( a3 )
  {
    a3->Buffer = a2->Buffer;
    Length = a2->Length;
    a3->MaximumLength = a2->Length;
    a3->Length = Length;
  }
  appended = RtlAppendUnicodeStringToString(a2, &Source);
  if ( appended < 0 )
  {
LABEL_19:
    v8 = "WinSetupMon::GetStablePath: Failed RtlAppendUnicodeStringToString [%wZ] (0x%08X)";
    goto LABEL_4;
  }
LABEL_29:
  if ( GuidString.Buffer )
    RtlFreeUnicodeString(&GuidString);
  if ( FileHandle )
    NtClose(FileHandle);
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SetupPlatform_WinSetupBootVolumeIssue>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Servicing_SetupPlatform_WinSetupBootVolumeIssue>::GetImpl'::`2'::impl);
  if ( P[1] )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P[1]);
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x18004df24  mov     [rsp-8+arg_18], rbx
0x18004df29  push    rbp
0x18004df2a  push    rsi
0x18004df2b  push    rdi
0x18004df2c  push    r12
0x18004df2e  push    r14
0x18004df30  lea     rbp, [rsp-37h]
0x18004df35  sub     rsp, 100h
0x18004df3c  mov     rax, cs:__security_cookie
0x18004df43  xor     rax, rsp
0x18004df46  mov     [rbp+57h+var_30], rax
0x18004df4a  xorps   xmm1, xmm1
0x18004df4d  mov     qword ptr [rdx+8], 0
0x18004df55  xorps   xmm0, xmm0
0x18004df58  mov     [rbp+57h+FileHandle], 0
0x18004df60  mov     rsi, r8
0x18004df63  mov     rdi, rdx
0x18004df66  lea     r8, [rbp+57h+var_90]; struct _UNICODE_STRING *
0x18004df6a  mov     r14, rcx
0x18004df6d  lea     rdx, [rbp+57h+P]; DestinationString
0x18004df71  movups  xmmword ptr [rbp+57h+P], xmm0
0x18004df75  movups  xmmword ptr [rbp+57h+var_90.Length], xmm1
0x18004df79  movups  xmmword ptr [rbp+57h+Source.Length], xmm0
0x18004df7d  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm1
0x18004df81  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm1
0x18004df85  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm1
0x18004df89  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x18004df8d  movups  xmmword ptr [rbp+57h+Guid.Data1], xmm1
0x18004df91  movups  xmmword ptr [rbp+57h+GuidString.Length], xmm0
0x18004df95  call    ?GetNtPath@DriverUtil@@YAJPEBU_UNICODE_STRING@@PEAU2@1@Z; DriverUtil::GetNtPath(_UNICODE_STRING const *,_UNICODE_STRING *,_UNICODE_STRING *)
0x18004df9a  lea     r12, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_SetupPlatform_WinSetupBootVolumeIssue@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_SetupPlatform_WinSetupBootVolumeIssue@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SetupPlatform_WinSetupBootVolumeIssue> `wil::Feature<__WilFeatureTraits_Feature_Servicing_SetupPlatform_WinSetupBootVolumeIssue>::GetImpl(void)'::`2'::impl
0x18004dfa1  mov     ebx, eax
0x18004dfa3  test    eax, eax
0x18004dfa5  jns     short loc_18004DFCB
0x18004dfa7  cmp     eax, 0C00000BBh
0x18004dfac  jz      loc_18004E1DE
0x18004dfb2  mov     r8, r14
0x18004dfb5  lea     rdx, aWinsetupmonGet_2; "WinSetupMon::GetStablePath: Failed GetN"...
0x18004dfbc  mov     r9d, eax
0x18004dfbf  xor     ecx, ecx
0x18004dfc1  call    WriteLog
0x18004dfc6  jmp     loc_18004E1DE
0x18004dfcb  movzx   eax, word ptr [rbp+57h+P]
0x18004dfcf  movzx   ecx, [rbp+57h+var_90.Length]
0x18004dfd3  sub     ax, cx
0x18004dfd6  mov     [rbp+57h+Source.Length], ax
0x18004dfda  jz      short loc_18004DFF6
0x18004dfdc  movzx   eax, word ptr [rbp+57h+P+2]
0x18004dfe0  sub     ax, cx
0x18004dfe3  mov     [rbp+57h+Source.MaximumLength], ax
0x18004dfe7  mov     rax, [rbp+57h+P+8]
0x18004dfeb  shr     rcx, 1
0x18004dfee  lea     rcx, [rax+rcx*2]
0x18004dff2  mov     [rbp+57h+Source.Buffer], rcx
0x18004dff6  lea     rax, [rbp+57h+var_90]
0x18004dffa  mov     [rsp+120h+OpenOptions], 4000h; OpenOptions
0x18004e002  xorps   xmm0, xmm0
0x18004e005  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18004e009  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x18004e00d  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18004e014  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18004e018  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x18004e020  mov     edx, 80h; DesiredAccess
0x18004e025  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x18004e02c  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x18004e030  mov     [rsp+120h+ShareAccess], 3; ShareAccess
0x18004e038  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18004e03d  call    cs:__imp_NtOpenFile
0x18004e043  mov     ebx, eax
0x18004e045  test    eax, eax
0x18004e047  jns     short loc_18004E059
0x18004e049  lea     r8, [rbp+57h+var_90]
0x18004e04d  lea     rdx, aWinsetupmonGet_0; "WinSetupMon::GetStablePath: Failed NtOp"...
0x18004e054  jmp     loc_18004DFBC
0x18004e059  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x18004e05d  lea     rax, [rbp+57h+Guid]
0x18004e061  mov     [rsp+120h+OutputBufferLength], 10h; OutputBufferLength
0x18004e069  xor     r9d, r9d; ApcContext
0x18004e06c  mov     [rsp+120h+OutputBuffer], rax; OutputBuffer
0x18004e071  xor     r8d, r8d; ApcRoutine
0x18004e074  mov     [rsp+120h+InputBufferLength], 0; InputBufferLength
0x18004e07c  lea     rax, [rbp+57h+IoStatusBlock]
0x18004e080  mov     [rsp+120h+InputBuffer], 0; InputBuffer
0x18004e089  xor     edx, edx; Event
0x18004e08b  mov     [rsp+120h+OpenOptions], 4D0018h; IoControlCode
0x18004e093  mov     qword ptr [rsp+120h+ShareAccess], rax; IoStatusBlock
0x18004e098  call    cs:__imp_NtDeviceIoControlFile
0x18004e09e  mov     ebx, eax
0x18004e0a0  add     eax, 3FFFFFFFh
0x18004e0a5  cmp     eax, 1
0x18004e0a8  jbe     loc_18004E1D9
0x18004e0ae  cmp     ebx, 0C0000010h
0x18004e0b4  jz      loc_18004E1D9
0x18004e0ba  test    ebx, ebx
0x18004e0bc  jns     short loc_18004E0E2
0x18004e0be  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18004e0c3  cmp     ebx, 0C00000BBh
0x18004e0c9  jz      loc_18004E1DE
0x18004e0cf  mov     r9d, ebx
0x18004e0d2  lea     r8, [rbp+57h+var_90]
0x18004e0d6  lea     rdx, aWinsetupmonGet_9; "WinSetupMon::GetStablePath: Failed NtDe"...
0x18004e0dd  jmp     loc_18004DFBF
0x18004e0e2  lea     rdx, [rbp+57h+GuidString]; GuidString
0x18004e0e6  lea     rcx, [rbp+57h+Guid]; Guid
0x18004e0ea  call    cs:__imp_RtlStringFromGUID
0x18004e0f0  mov     ebx, eax
0x18004e0f2  test    eax, eax
0x18004e0f4  jns     short loc_18004E10C
0x18004e0f6  mov     r8d, eax
0x18004e0f9  lea     rdx, aWinsetupmonGet_1; "WinSetupMon::GetStablePath: Failed RtlS"...
0x18004e100  xor     ecx, ecx
0x18004e102  call    WriteLog
0x18004e107  jmp     loc_18004E1DE
0x18004e10c  mov     rcx, r12
0x18004e10f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_SetupPlatform_WinSetupBootVolumeIssue@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SetupPlatform_WinSetupBootVolumeIssue>::__private_IsEnabled(void)
0x18004e114  test    al, al
0x18004e116  movzx   eax, [rbp+57h+GuidString.Length]
0x18004e11a  add     ax, [rbp+57h+Source.Length]
0x18004e11e  add     ax, 14h
0x18004e122  mov     rcx, r12
0x18004e125  mov     [rdi+2], ax
0x18004e129  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_SetupPlatform_WinSetupBootVolumeIssue@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SetupPlatform_WinSetupBootVolumeIssue>::__private_IsEnabled(void)
0x18004e12e  mov     rcx, gs:60h
0x18004e137  xor     edx, edx; Flags
0x18004e139  movzx   r8d, word ptr [rdi+2]; Size
0x18004e13e  mov     rcx, [rcx+30h]; HeapHandle
0x18004e142  call    cs:__imp_RtlAllocateHeap
0x18004e148  mov     [rdi+8], rax
0x18004e14c  test    rax, rax
0x18004e14f  jnz     short loc_18004E166
0x18004e151  lea     rdx, aWinsetupmonGet_6; "WinSetupMon::GetStablePath: Failed to a"...
0x18004e158  xor     ecx, ecx
0x18004e15a  call    WriteLog
0x18004e15f  mov     ebx, 0C000009Ah
0x18004e164  jmp     short loc_18004E1DE
0x18004e166  mov     rcx, r12
0x18004e169  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_SetupPlatform_WinSetupBootVolumeIssue@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SetupPlatform_WinSetupBootVolumeIssue>::__private_IsEnabled(void)
0x18004e16e  lea     rdx, SourceString; SourceString
0x18004e175  mov     rcx, rdi; DestinationString
0x18004e178  call    cs:__imp_RtlCopyUnicodeString
0x18004e17e  mov     eax, 0FFFEh
0x18004e183  lea     rdx, [rbp+57h+GuidString]; Source
0x18004e187  add     [rdi], ax
0x18004e18a  mov     rcx, rdi; Destination
0x18004e18d  call    cs:__imp_RtlAppendUnicodeStringToString
0x18004e193  mov     ebx, eax
0x18004e195  test    eax, eax
0x18004e197  jns     short loc_18004E1A9
0x18004e199  lea     r8, [rbp+57h+GuidString]
0x18004e19d  lea     rdx, aWinsetupmonGet_3; "WinSetupMon::GetStablePath: Failed RtlA"...
0x18004e1a4  jmp     loc_18004DFBC
0x18004e1a9  test    rsi, rsi
0x18004e1ac  jz      short loc_18004E1C0
0x18004e1ae  mov     rax, [rdi+8]
0x18004e1b2  mov     [rsi+8], rax
0x18004e1b6  movzx   eax, word ptr [rdi]
0x18004e1b9  mov     [rsi+2], ax
0x18004e1bd  mov     [rsi], ax
0x18004e1c0  lea     rdx, [rbp+57h+Source]; Source
0x18004e1c4  mov     rcx, rdi; Destination
0x18004e1c7  call    cs:__imp_RtlAppendUnicodeStringToString
0x18004e1cd  mov     ebx, eax
0x18004e1cf  test    eax, eax
0x18004e1d1  jns     short loc_18004E212
0x18004e1d3  lea     r8, [rbp+57h+Source]
0x18004e1d7  jmp     short loc_18004E19D
0x18004e1d9  mov     ebx, 0C00000BBh
0x18004e1de  mov     rcx, r12
0x18004e1e1  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_SetupPlatform_WinSetupBootVolumeIssue@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SetupPlatform_WinSetupBootVolumeIssue>::__private_IsEnabled(void)
0x18004e1e6  mov     r8, [rdi+8]; P
0x18004e1ea  test    r8, r8
0x18004e1ed  jz      short loc_18004E204
0x18004e1ef  mov     rcx, gs:60h
0x18004e1f8  xor     edx, edx; Flags
0x18004e1fa  mov     rcx, [rcx+30h]; HeapHandle
0x18004e1fe  call    cs:__imp_RtlFreeHeap
0x18004e204  xorps   xmm0, xmm0
0x18004e207  movups  xmmword ptr [rdi], xmm0
0x18004e20a  test    rsi, rsi
0x18004e20d  jz      short loc_18004E212
0x18004e20f  movups  xmmword ptr [rsi], xmm0
0x18004e212  cmp     [rbp+57h+GuidString.Buffer], 0
0x18004e217  jz      short loc_18004E223
0x18004e219  lea     rcx, [rbp+57h+GuidString]; UnicodeString
0x18004e21d  call    cs:__imp_RtlFreeUnicodeString
0x18004e223  mov     rcx, [rbp+57h+FileHandle]; Handle
0x18004e227  test    rcx, rcx
0x18004e22a  jz      short loc_18004E232
0x18004e22c  call    cs:__imp_NtClose
0x18004e232  mov     rcx, r12
0x18004e235  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_SetupPlatform_WinSetupBootVolumeIssue@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SetupPlatform_WinSetupBootVolumeIssue>::__private_IsEnabled(void)
0x18004e23a  cmp     [rbp+57h+P+8], 0
0x18004e23f  jz      short loc_18004E25A
0x18004e241  mov     rcx, gs:60h
0x18004e24a  xor     edx, edx; Flags
0x18004e24c  mov     r8, [rbp+57h+P+8]; P
0x18004e250  mov     rcx, [rcx+30h]; HeapHandle
0x18004e254  call    cs:__imp_RtlFreeHeap
0x18004e25a  mov     eax, ebx
0x18004e25c  mov     rcx, [rbp+57h+var_30]
0x18004e260  xor     rcx, rsp; StackCookie
0x18004e263  call    __security_check_cookie
0x18004e268  mov     rbx, [rsp+120h+arg_18]
0x18004e270  add     rsp, 100h
0x18004e277  pop     r14
0x18004e279  pop     r12
0x18004e27b  pop     rdi
0x18004e27c  pop     rsi
0x18004e27d  pop     rbp
0x18004e27e  retn
```
