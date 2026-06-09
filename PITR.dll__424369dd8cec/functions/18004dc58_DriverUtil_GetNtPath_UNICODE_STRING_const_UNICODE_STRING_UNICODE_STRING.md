# DriverUtil::GetNtPath(_UNICODE_STRING const *,_UNICODE_STRING *,_UNICODE_STRING *)

- ea: `0x18004dc58`
- end: `0x18004df1b`
- name: `?GetNtPath@DriverUtil@@YAJPEBU_UNICODE_STRING@@PEAU2@1@Z`
- size: `707`
- prototype: `__int64 __fastcall(PCUNICODE_STRING String2, PUNICODE_STRING DestinationString, struct _UNICODE_STRING *, struct _UNICODE_STRING *)`
- caller_count: `2`
- callee_count: `7`
- tags: `reparse_path, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18004df24`
- `0x18004e288`

## callees

- `0x18004da60`
- `0x18004dbe8`
- `0x18004dc58`
- `0x18004e358`
- `0x18004ead4`
- `0x18004edf0`
- `0x180050198`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x18004ddf7`
- `ntdll!RtlAllocateHeap` at `0x18004ddf7`
- `ntdll!RtlFreeHeap` at `0x18004deae`
- `ntdll!RtlFreeHeap` at `0x18004defc`
- `ntdll!RtlFreeHeap` at `0x18004deae`
- `ntdll!RtlFreeHeap` at `0x18004defc`
- `ntdll!NtOpenSymbolicLinkObject` at `0x18004dd83`
- `ntdll!NtOpenSymbolicLinkObject` at `0x18004dd83`
- `ntdll!NtQuerySymbolicLinkObject` at `0x18004ddbc`
- `ntdll!NtQuerySymbolicLinkObject` at `0x18004de25`
- `ntdll!NtQuerySymbolicLinkObject` at `0x18004ddbc`
- `ntdll!NtQuerySymbolicLinkObject` at `0x18004de25`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18004de5e`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18004de5e`
- `ntdll!NtClose` at `0x18004decb`
- `ntdll!NtClose` at `0x18004decb`

## string_xrefs

- `0x18004dce9`: `WinSetupMon::GetNtPath: Failed to duplicate for NtPath %wZ (0x%08X)`
- `0x18004dd9b`: `WinSetupMon::GetNtPath: Failed OpenSymbolicLinkObject (0x%08X)`
- `0x18004dd48`: `WinSetupMon::GetNtPath: Failed GetVolumeSymbolicLinkFromPath for Path %wZ (0x%08X)`
- `0x18004de31`: `WinSetupMon::GetNtPath: Failed QuerySymbolicLinkObject (0x%08X)`
- `0x18004de06`: `WinSetupMon::GetNtPath: Failed to allocate NtPath buffer`
- `0x18004de6d`: `WinSetupMon::GetNtPath: Failed RtlAppendUnicodeStringToString (0x%08X)`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall DriverUtil::GetNtPath(
        PCUNICODE_STRING String2,
        PUNICODE_STRING DestinationString,
        struct _UNICODE_STRING *a3,
        struct _UNICODE_STRING *a4)
{
  int VolumeDeviceInPath; // eax
  struct _UNICODE_STRING *v8; // r8
  NTSTATUS VolumeSymbolicLinkFromPath; // ebx
  const char *v10; // rdx
  NTSTATUS v11; // eax
  const char *v12; // rdx
  WCHAR *Heap; // rax
  PWSTR Buffer; // r8
  void *SymbolicLinkHandle; // [rsp+20h] [rbp-49h] BYREF
  struct _UNICODE_STRING v17; // [rsp+28h] [rbp-41h]
  UNICODE_STRING Source; // [rsp+38h] [rbp-31h] BYREF
  PVOID P[2]; // [rsp+48h] [rbp-21h] BYREF
  UNICODE_STRING SourceString; // [rsp+58h] [rbp-11h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+68h] [rbp-1h] BYREF
  ULONG DataWritten; // [rsp+E8h] [rbp+7Fh] BYREF

  DestinationString->Buffer = 0;
  SymbolicLinkHandle = 0;
  v17 = 0;
  *(_OWORD *)P = 0;
  Source = 0;
  VolumeDeviceInPath = GetVolumeDeviceInPath(String2);
  VolumeSymbolicLinkFromPath = VolumeDeviceInPath;
  if ( VolumeDeviceInPath < 0 )
  {
    if ( VolumeDeviceInPath != -1073741637 )
      goto LABEL_23;
    DataWritten = 0;
    memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
    VolumeSymbolicLinkFromPath = GetVolumeSymbolicLinkFromPath(String2, (PUNICODE_STRING)P);
    if ( VolumeSymbolicLinkFromPath < 0 )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs();
      if ( VolumeSymbolicLinkFromPath == -1073741637 )
        goto LABEL_26;
      v10 = "WinSetupMon::GetNtPath: Failed GetVolumeSymbolicLinkFromPath for Path %wZ (0x%08X)";
LABEL_4:
      WriteLog(0, v10);
LABEL_26:
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SetupPlatform_WinSetupBootVolumeIssue>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Servicing_SetupPlatform_WinSetupBootVolumeIssue>::GetImpl'::`2'::impl);
      Buffer = DestinationString->Buffer;
      if ( Buffer )
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Buffer);
      *DestinationString = 0;
      if ( a3 )
        *a3 = 0;
      goto LABEL_30;
    }
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = (PUNICODE_STRING)P;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 64;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v11 = NtOpenSymbolicLinkObject(&SymbolicLinkHandle, 0x80000000, &ObjectAttributes);
    VolumeSymbolicLinkFromPath = v11;
    if ( v11 >= 0 )
    {
      VolumeSymbolicLinkFromPath = NtQuerySymbolicLinkObject(SymbolicLinkHandle, DestinationString, &DataWritten);
      if ( VolumeSymbolicLinkFromPath == -1073741789 )
      {
        DestinationString->MaximumLength = Source.Length + DataWritten;
        wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SetupPlatform_WinSetupBootVolumeIssue>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Servicing_SetupPlatform_WinSetupBootVolumeIssue>::GetImpl'::`2'::impl);
        Heap = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, DestinationString->MaximumLength);
        DestinationString->Buffer = Heap;
        if ( !Heap )
        {
          WriteLog(0, "WinSetupMon::GetNtPath: Failed to allocate NtPath buffer");
          VolumeSymbolicLinkFromPath = -1073741670;
          goto LABEL_26;
        }
        VolumeSymbolicLinkFromPath = NtQuerySymbolicLinkObject(SymbolicLinkHandle, DestinationString, 0);
      }
      if ( VolumeSymbolicLinkFromPath >= 0 )
      {
        v17.Buffer = DestinationString->Buffer;
        v17.MaximumLength = DestinationString->Length;
        v17.Length = v17.MaximumLength;
        if ( !Source.Length )
          goto LABEL_23;
        VolumeSymbolicLinkFromPath = RtlAppendUnicodeStringToString(DestinationString, &Source);
        if ( VolumeSymbolicLinkFromPath >= 0 )
          goto LABEL_23;
        v12 = "WinSetupMon::GetNtPath: Failed RtlAppendUnicodeStringToString (0x%08X)";
      }
      else
      {
        v12 = "WinSetupMon::GetNtPath: Failed QuerySymbolicLinkObject (0x%08X)";
      }
    }
    else
    {
      if ( v11 != -1073741772 )
        MicrosoftTelemetryAssertTriggeredNoArgs();
      v12 = "WinSetupMon::GetNtPath: Failed OpenSymbolicLinkObject (0x%08X)";
    }
    WriteLog(0, v12);
    goto LABEL_26;
  }
  *(&SourceString.MaximumLength + 2) = 0;
  SourceString.Buffer = v17.Buffer;
  *(_DWORD *)&SourceString.MaximumLength = (unsigned __int16)(v17.Length + Source.Length);
  SourceString.Length = v17.Length + Source.Length;
  VolumeSymbolicLinkFromPath = DriverUtil::Duplicate(&SourceString, DestinationString, v8);
  if ( VolumeSymbolicLinkFromPath < 0 )
  {
    v10 = "WinSetupMon::GetNtPath: Failed to duplicate for NtPath %wZ (0x%08X)";
    goto LABEL_4;
  }
LABEL_23:
  if ( a3 )
    *a3 = v17;
  if ( VolumeSymbolicLinkFromPath < 0 )
    goto LABEL_26;
LABEL_30:
  if ( SymbolicLinkHandle )
    NtClose(SymbolicLinkHandle);
  return (unsigned int)VolumeSymbolicLinkFromPath;
}

```

## disassembly

```asm
0x18004dc58  mov     [rsp-8+arg_0], rbx
0x18004dc5d  push    rbp
0x18004dc5e  push    rsi
0x18004dc5f  push    rdi
0x18004dc60  push    r14
0x18004dc62  push    r15
0x18004dc64  lea     rbp, [rsp-37h]
0x18004dc69  sub     rsp, 0A0h
0x18004dc70  xor     r15d, r15d
0x18004dc73  xorps   xmm0, xmm0
0x18004dc76  mov     [rdx+8], r15
0x18004dc7a  mov     rsi, r8
0x18004dc7d  mov     rdi, rdx
0x18004dc80  mov     [rbp+57h+arg_8], r15b
0x18004dc84  xorps   xmm1, xmm1
0x18004dc87  mov     [rbp+57h+SymbolicLinkHandle], r15
0x18004dc8b  lea     rdx, [rbp+57h+var_98]
0x18004dc8f  mov     r14, rcx
0x18004dc92  lea     r8, [rbp+57h+Source]
0x18004dc96  movups  [rbp+57h+var_98], xmm0
0x18004dc9a  movups  xmmword ptr [rbp+57h+P], xmm1
0x18004dc9e  movups  xmmword ptr [rbp+57h+Source.Length], xmm0
0x18004dca2  call    GetVolumeDeviceInPath
0x18004dca7  mov     ebx, eax
0x18004dca9  test    eax, eax
0x18004dcab  js      short loc_18004DCFC
0x18004dcad  mov     rax, qword ptr [rbp+57h+var_98+8]
0x18004dcb1  lea     rcx, [rbp+57h+SourceString]; SourceString
0x18004dcb5  xorps   xmm0, xmm0
0x18004dcb8  mov     rdx, rdi; DestinationString
0x18004dcbb  movups  xmmword ptr [rbp+57h+SourceString.Length], xmm0
0x18004dcbf  mov     [rbp+57h+SourceString.Buffer], rax
0x18004dcc3  movzx   eax, [rbp+57h+Source.Length]
0x18004dcc7  add     ax, word ptr [rbp+57h+var_98]
0x18004dccb  mov     [rbp+57h+SourceString.MaximumLength], ax
0x18004dccf  mov     [rbp+57h+SourceString.Length], ax
0x18004dcd3  call    ?Duplicate@DriverUtil@@YAJPEBU_UNICODE_STRING@@PEAU2@@Z; DriverUtil::Duplicate(_UNICODE_STRING const *,_UNICODE_STRING *)
0x18004dcd8  mov     ebx, eax
0x18004dcda  test    eax, eax
0x18004dcdc  jns     loc_18004DE79
0x18004dce2  mov     r9d, eax
0x18004dce5  lea     r8, [rbp+57h+SourceString]
0x18004dce9  lea     rdx, aWinsetupmonGet_8; "WinSetupMon::GetNtPath: Failed to dupli"...
0x18004dcf0  xor     ecx, ecx
0x18004dcf2  call    WriteLog
0x18004dcf7  jmp     loc_18004DE8A
0x18004dcfc  cmp     eax, 0C00000BBh
0x18004dd01  jnz     loc_18004DE79
0x18004dd07  xorps   xmm0, xmm0
0x18004dd0a  mov     [rbp+57h+DataWritten], r15d
0x18004dd0e  lea     r9, [rbp+57h+Source]
0x18004dd12  mov     rcx, r14; String2
0x18004dd15  lea     r8, [rbp+57h+arg_8]
0x18004dd19  lea     rdx, [rbp+57h+P]; DestinationString
0x18004dd1d  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x18004dd21  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x18004dd25  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18004dd29  call    GetVolumeSymbolicLinkFromPath
0x18004dd2e  mov     ebx, eax
0x18004dd30  test    eax, eax
0x18004dd32  jns     short loc_18004DD54
0x18004dd34  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18004dd39  cmp     ebx, 0C00000BBh
0x18004dd3f  jz      loc_18004DE8A
0x18004dd45  mov     r9d, ebx
0x18004dd48  lea     rdx, aWinsetupmonGet_4; "WinSetupMon::GetNtPath: Failed GetVolum"...
0x18004dd4f  mov     r8, r14
0x18004dd52  jmp     short loc_18004DCF0
0x18004dd54  lea     rax, [rbp+57h+P]
0x18004dd58  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18004dd5f  xorps   xmm0, xmm0
0x18004dd62  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18004dd66  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18004dd6a  mov     [rbp+57h+ObjectAttributes.RootDirectory], r15
0x18004dd6e  mov     edx, 80000000h; DesiredAccess
0x18004dd73  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x18004dd7a  lea     rcx, [rbp+57h+SymbolicLinkHandle]; SymbolicLinkHandle
0x18004dd7e  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18004dd83  call    cs:__imp_NtOpenSymbolicLinkObject
0x18004dd89  mov     ebx, eax
0x18004dd8b  test    eax, eax
0x18004dd8d  jns     short loc_18004DDB1
0x18004dd8f  cmp     eax, 0C0000034h
0x18004dd94  jz      short loc_18004DD9B
0x18004dd96  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18004dd9b  lea     rdx, aWinsetupmonGet; "WinSetupMon::GetNtPath: Failed OpenSymb"...
0x18004dda2  mov     r8d, ebx
0x18004dda5  xor     ecx, ecx
0x18004dda7  call    WriteLog
0x18004ddac  jmp     loc_18004DE8A
0x18004ddb1  mov     rcx, [rbp+57h+SymbolicLinkHandle]; SymLinkObjHandle
0x18004ddb5  lea     r8, [rbp+57h+DataWritten]; DataWritten
0x18004ddb9  mov     rdx, rdi; LinkTarget
0x18004ddbc  call    cs:__imp_NtQuerySymbolicLinkObject
0x18004ddc2  mov     ebx, eax
0x18004ddc4  cmp     eax, 0C0000023h
0x18004ddc9  jnz     short loc_18004DE2D
0x18004ddcb  movzx   eax, word ptr [rbp+57h+DataWritten]
0x18004ddcf  add     ax, [rbp+57h+Source.Length]
0x18004ddd3  mov     [rdi+2], ax
0x18004ddd7  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_SetupPlatform_WinSetupBootVolumeIssue@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_SetupPlatform_WinSetupBootVolumeIssue@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SetupPlatform_WinSetupBootVolumeIssue> `wil::Feature<__WilFeatureTraits_Feature_Servicing_SetupPlatform_WinSetupBootVolumeIssue>::GetImpl(void)'::`2'::impl
0x18004ddde  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_SetupPlatform_WinSetupBootVolumeIssue@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SetupPlatform_WinSetupBootVolumeIssue>::__private_IsEnabled(void)
0x18004dde3  mov     rcx, gs:60h
0x18004ddec  xor     edx, edx; Flags
0x18004ddee  movzx   r8d, word ptr [rdi+2]; Size
0x18004ddf3  mov     rcx, [rcx+30h]; HeapHandle
0x18004ddf7  call    cs:__imp_RtlAllocateHeap
0x18004ddfd  mov     [rdi+8], rax
0x18004de01  test    rax, rax
0x18004de04  jnz     short loc_18004DE1B
0x18004de06  lea     rdx, aWinsetupmonGet_7; "WinSetupMon::GetNtPath: Failed to alloc"...
0x18004de0d  xor     ecx, ecx
0x18004de0f  call    WriteLog
0x18004de14  mov     ebx, 0C000009Ah
0x18004de19  jmp     short loc_18004DE8A
0x18004de1b  mov     rcx, [rbp+57h+SymbolicLinkHandle]; SymLinkObjHandle
0x18004de1f  xor     r8d, r8d; DataWritten
0x18004de22  mov     rdx, rdi; LinkTarget
0x18004de25  call    cs:__imp_NtQuerySymbolicLinkObject
0x18004de2b  mov     ebx, eax
0x18004de2d  test    ebx, ebx
0x18004de2f  jns     short loc_18004DE3D
0x18004de31  lea     rdx, aWinsetupmonGet_10; "WinSetupMon::GetNtPath: Failed QuerySym"...
0x18004de38  jmp     loc_18004DDA2
0x18004de3d  mov     rax, [rdi+8]
0x18004de41  mov     qword ptr [rbp+57h+var_98+8], rax
0x18004de45  movzx   eax, word ptr [rdi]
0x18004de48  mov     word ptr [rbp+57h+var_98+2], ax
0x18004de4c  mov     word ptr [rbp+57h+var_98], ax
0x18004de50  cmp     [rbp+57h+Source.Length], r15w
0x18004de55  jbe     short loc_18004DE79
0x18004de57  lea     rdx, [rbp+57h+Source]; Source
0x18004de5b  mov     rcx, rdi; Destination
0x18004de5e  call    cs:__imp_RtlAppendUnicodeStringToString
0x18004de64  mov     ebx, eax
0x18004de66  test    eax, eax
0x18004de68  jns     short loc_18004DE79
0x18004de6a  mov     r8d, eax
0x18004de6d  lea     rdx, aWinsetupmonGet_5; "WinSetupMon::GetNtPath: Failed RtlAppen"...
0x18004de74  jmp     loc_18004DDA5
0x18004de79  test    rsi, rsi
0x18004de7c  jz      short loc_18004DE86
0x18004de7e  movups  xmm0, [rbp+57h+var_98]
0x18004de82  movdqu  xmmword ptr [rsi], xmm0
0x18004de86  test    ebx, ebx
0x18004de88  jns     short loc_18004DEC2
0x18004de8a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_SetupPlatform_WinSetupBootVolumeIssue@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_SetupPlatform_WinSetupBootVolumeIssue@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SetupPlatform_WinSetupBootVolumeIssue> `wil::Feature<__WilFeatureTraits_Feature_Servicing_SetupPlatform_WinSetupBootVolumeIssue>::GetImpl(void)'::`2'::impl
0x18004de91  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_SetupPlatform_WinSetupBootVolumeIssue@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SetupPlatform_WinSetupBootVolumeIssue>::__private_IsEnabled(void)
0x18004de96  mov     r8, [rdi+8]; P
0x18004de9a  test    r8, r8
0x18004de9d  jz      short loc_18004DEB4
0x18004de9f  mov     rcx, gs:60h
0x18004dea8  xor     edx, edx; Flags
0x18004deaa  mov     rcx, [rcx+30h]; HeapHandle
0x18004deae  call    cs:__imp_RtlFreeHeap
0x18004deb4  xorps   xmm0, xmm0
0x18004deb7  movups  xmmword ptr [rdi], xmm0
0x18004deba  test    rsi, rsi
0x18004debd  jz      short loc_18004DEC2
0x18004debf  movups  xmmword ptr [rsi], xmm0
0x18004dec2  mov     rcx, [rbp+57h+SymbolicLinkHandle]; Handle
0x18004dec6  test    rcx, rcx
0x18004dec9  jz      short loc_18004DED1
0x18004decb  call    cs:__imp_NtClose
0x18004ded1  cmp     [rbp+57h+arg_8], r15b
0x18004ded5  jz      short loc_18004DF02
0x18004ded7  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_SetupPlatform_WinSetupBootVolumeIssue@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_SetupPlatform_WinSetupBootVolumeIssue@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SetupPlatform_WinSetupBootVolumeIssue> `wil::Feature<__WilFeatureTraits_Feature_Servicing_SetupPlatform_WinSetupBootVolumeIssue>::GetImpl(void)'::`2'::impl
0x18004dede  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_SetupPlatform_WinSetupBootVolumeIssue@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SetupPlatform_WinSetupBootVolumeIssue>::__private_IsEnabled(void)
0x18004dee3  cmp     [rbp+57h+P+8], r15
0x18004dee7  jz      short loc_18004DF02
0x18004dee9  mov     rcx, gs:60h
0x18004def2  xor     edx, edx; Flags
0x18004def4  mov     r8, [rbp+57h+P+8]; P
0x18004def8  mov     rcx, [rcx+30h]; HeapHandle
0x18004defc  call    cs:__imp_RtlFreeHeap
0x18004df02  mov     eax, ebx
0x18004df04  mov     rbx, [rsp+0C0h+arg_0]
0x18004df0c  add     rsp, 0A0h
0x18004df13  pop     r15
0x18004df15  pop     r14
0x18004df17  pop     rdi
0x18004df18  pop     rsi
0x18004df19  pop     rbp
0x18004df1a  retn
```
