# BfGetInstanceFromFileObject

- ea: `0x140023cd8`
- end: `0x140024194`
- name: `BfGetInstanceFromFileObject`
- size: `1212`
- prototype: `__int64 __fastcall(PCUNICODE_STRING SourceString)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14001d974`
- `0x14001f71c`

## callees

- `0x140001348`
- `0x140002e0c`
- `0x140004b90`
- `0x14001d130`
- `0x140023cd8`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x140023dd4`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140023dd4`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140023f1c`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140023f1c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400240f8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140024117`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400240f8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140024117`
- `ntoskrnl!ObfDereferenceObject` at `0x140024149`
- `ntoskrnl!ObfDereferenceObject` at `0x140024149`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140023e37`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140023e89`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140023ed4`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140023e37`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140023e89`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140023ed4`
- `FLTMGR!FltGetVolumeFromFileObject` at `0x14002405d`
- `FLTMGR!FltGetVolumeFromFileObject` at `0x14002405d`
- `FLTMGR!FltGetVolumeInstanceFromName` at `0x1400240a8`
- `FLTMGR!FltGetVolumeInstanceFromName` at `0x1400240a8`
- `FLTMGR!FltCreateFileEx2` at `0x140023fd9`
- `FLTMGR!FltCreateFileEx2` at `0x140023fd9`
- `FLTMGR!FltClose` at `0x140024134`
- `FLTMGR!FltClose` at `0x140024134`
- `FLTMGR!FltObjectDereference` at `0x14002415e`
- `FLTMGR!FltObjectDereference` at `0x14002415e`

## pseudocode

```c
__int64 __fastcall BfGetInstanceFromFileObject(PCUNICODE_STRING SourceString, char a2, PFLT_INSTANCE *a3)
{
  __int64 Length; // rcx
  unsigned __int16 v7; // di
  int v8; // edx
  NTSTATUS appended; // ebx
  int v10; // r9d
  int v11; // edx
  char IoStatusBlock; // [rsp+30h] [rbp-D0h]
  PLARGE_INTEGER AllocationSize; // [rsp+38h] [rbp-C8h]
  struct _UNICODE_STRING DestinationString; // [rsp+80h] [rbp-80h] BYREF
  struct _UNICODE_STRING Destination; // [rsp+90h] [rbp-70h] BYREF
  PFILE_OBJECT FileObject; // [rsp+A0h] [rbp-60h] BYREF
  PFLT_VOLUME RetVolume; // [rsp+A8h] [rbp-58h] BYREF
  PFLT_INSTANCE RetInstance; // [rsp+B0h] [rbp-50h] BYREF
  void *FileHandle; // [rsp+B8h] [rbp-48h] BYREF
  UNICODE_STRING Source; // [rsp+C0h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+D0h] [rbp-30h] BYREF
  struct _IO_STATUS_BLOCK v23; // [rsp+100h] [rbp+0h] BYREF
  __int128 v24; // [rsp+110h] [rbp+10h] BYREF

  *(_QWORD *)&Source.Length = 1048590;
  RetVolume = 0;
  RetInstance = 0;
  Length = SourceString->Length;
  FileHandle = 0;
  FileObject = 0;
  Source.Buffer = (PWSTR)&v24;
  v7 = Length + 2;
  Destination = 0;
  memset(&ObjectAttributes, 0, 44);
  v23 = 0;
  DestinationString = 0;
  v24 = *(_OWORD *)L"\\??\\UNC";
  appended = BfAllocateUnicodeString(Length, &DestinationString);
  if ( appended < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_33;
    LODWORD(AllocationSize) = appended;
    v10 = 46;
    IoStatusBlock = -42;
    goto LABEL_4;
  }
  RtlCopyUnicodeString(&DestinationString, SourceString);
  if ( !a2 )
    v7 += Source.Length;
  appended = BfAllocateUnicodeString(v7, &Destination);
  if ( appended < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LODWORD(AllocationSize) = appended;
      v10 = 47;
      IoStatusBlock = -29;
LABEL_4:
      LOBYTE(v8) = 2;
      WPP_RECORDER_SF_sDd(
        WPP_GLOBAL_Control->DeviceExtension,
        v8,
        3,
        v10,
        (__int64)WPP_529f93b0825532f67776c14f74ba0846_Traceguids,
        (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\utils.c",
        IoStatusBlock,
        AllocationSize);
      goto LABEL_33;
    }
    goto LABEL_33;
  }
  if ( a2 )
  {
    DestinationString.Buffer[1] = 63;
    appended = RtlAppendUnicodeStringToString(&Destination, &DestinationString);
    if ( appended < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LODWORD(AllocationSize) = appended;
        v10 = 50;
        IoStatusBlock = 11;
        goto LABEL_4;
      }
      goto LABEL_33;
    }
    goto LABEL_20;
  }
  appended = RtlAppendUnicodeStringToString(&Destination, &Source);
  if ( appended >= 0 )
  {
    ++DestinationString.Buffer;
    DestinationString.Length -= 2;
    appended = RtlAppendUnicodeStringToString(&Destination, &DestinationString);
    if ( appended < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LODWORD(AllocationSize) = appended;
        v10 = 49;
        IoStatusBlock = -5;
        goto LABEL_4;
      }
      goto LABEL_33;
    }
LABEL_20:
    appended = RtlAppendUnicodeToString(&Destination, L"\\");
    if ( appended >= 0 )
    {
      ObjectAttributes.ObjectName = &Destination;
      ObjectAttributes.Length = 48;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.Attributes = 576;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      appended = FltCreateFileEx2(
                   g_BindFltState,
                   0,
                   &FileHandle,
                   &FileObject,
                   0x80u,
                   &ObjectAttributes,
                   &v23,
                   0,
                   0,
                   7u,
                   1u,
                   0,
                   0,
                   0,
                   0,
                   0);
      if ( appended >= 0 )
      {
        appended = FltGetVolumeFromFileObject(g_BindFltState, FileObject, &RetVolume);
        if ( appended >= 0 )
        {
          appended = FltGetVolumeInstanceFromName(g_BindFltState, RetVolume, 0, &RetInstance);
          if ( appended >= 0 )
          {
            *a3 = RetInstance;
          }
          else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LODWORD(AllocationSize) = appended;
            v10 = 54;
            IoStatusBlock = 61;
            goto LABEL_4;
          }
        }
        else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LODWORD(AllocationSize) = appended;
          v10 = 53;
          IoStatusBlock = 54;
          goto LABEL_4;
        }
      }
      else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v11) = 2;
        WPP_RECORDER_SF_sDZd(
          WPP_GLOBAL_Control->DeviceExtension,
          v11,
          3,
          52,
          (__int64)WPP_529f93b0825532f67776c14f74ba0846_Traceguids,
          (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\utils.c",
          47,
          (__int64)&Destination,
          appended);
      }
    }
    else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LODWORD(AllocationSize) = appended;
      v10 = 51;
      IoStatusBlock = 19;
      goto LABEL_4;
    }
    goto LABEL_33;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LODWORD(AllocationSize) = appended;
    v10 = 48;
    IoStatusBlock = -20;
    goto LABEL_4;
  }
LABEL_33:
  if ( Destination.Buffer )
  {
    ExFreePoolWithTag(Destination.Buffer, 0x74734642u);
    Destination.Buffer = 0;
  }
  *(_DWORD *)&Destination.Length = 0;
  if ( DestinationString.Buffer )
  {
    ExFreePoolWithTag(DestinationString.Buffer, 0x74734642u);
    DestinationString.Buffer = 0;
  }
  *(_DWORD *)&DestinationString.Length = 0;
  if ( FileHandle )
    FltClose(FileHandle);
  if ( FileObject )
    ObfDereferenceObject(FileObject);
  if ( RetVolume )
    FltObjectDereference(RetVolume);
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x140023cd8  mov     [rsp-8+arg_8], rbx
0x140023cdd  push    rbp
0x140023cde  push    rsi
0x140023cdf  push    rdi
0x140023ce0  push    r12
0x140023ce2  push    r13
0x140023ce4  push    r14
0x140023ce6  push    r15
0x140023ce8  lea     rbp, [rsp-30h]
0x140023ced  sub     rsp, 130h
0x140023cf4  mov     rax, cs:__security_cookie
0x140023cfb  xor     rax, rsp
0x140023cfe  mov     [rbp+60h+var_40], rax
0x140023d02  movups  xmm1, xmmword ptr cs:aUnc; "\\??\\UNC"
0x140023d09  mov     qword ptr [rbp+60h+Source.Length], 10000Eh
0x140023d11  xor     r12d, r12d
0x140023d14  xorps   xmm0, xmm0
0x140023d17  mov     [rbp+60h+RetVolume], r12
0x140023d1b  mov     r14, rcx
0x140023d1e  mov     [rbp+60h+RetInstance], r12
0x140023d22  movzx   ecx, word ptr [rcx]
0x140023d25  xor     eax, eax
0x140023d27  mov     sil, dl
0x140023d2a  mov     [rbp+60h+FileHandle], r12
0x140023d2e  lea     rax, [rbp+60h+var_50]
0x140023d32  mov     [rbp+60h+FileObject], r12
0x140023d36  movups  xmmword ptr [rbp+60h+var_90.ObjectName], xmm0
0x140023d3a  lea     r13d, [r12+2]
0x140023d3f  mov     [rbp+60h+Source.Buffer], rax
0x140023d43  lea     rdx, [rbp+60h+DestinationString]
0x140023d47  mov     r15, r8
0x140023d4a  lea     edi, [rcx+r13]
0x140023d4e  movups  xmmword ptr [rbp+60h+Destination.Length], xmm0
0x140023d52  movups  xmmword ptr [rbp+60h+var_90.Length], xmm0
0x140023d56  movups  xmmword ptr [rbp+60h+var_90+1Ch], xmm0
0x140023d5a  movups  xmmword ptr [rbp+60h+var_60], xmm0
0x140023d5e  movups  xmmword ptr [rbp+60h+DestinationString.Length], xmm0
0x140023d62  movdqu  [rbp+60h+var_50], xmm1
0x140023d67  call    BfAllocateUnicodeString
0x140023d6c  mov     ebx, eax
0x140023d6e  test    eax, eax
0x140023d70  jns     short loc_140023DCD
0x140023d72  lea     rax, WPP_RECORDER_INITIALIZED
0x140023d79  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140023d80  jz      loc_1400240E8
0x140023d86  mov     dword ptr [rsp+160h+AllocationSize], ebx
0x140023d8a  lea     r9d, [r12+2Eh]
0x140023d8f  mov     dword ptr [rsp+160h+IoStatusBlock], 7D6h
0x140023d97  mov     rcx, cs:WPP_GLOBAL_Control
0x140023d9e  lea     rax, aOnecoreBaseFsW_0; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x140023da5  mov     [rsp+160h+ObjectAttributes], rax
0x140023daa  mov     r8d, 3
0x140023db0  lea     rax, WPP_529f93b0825532f67776c14f74ba0846_Traceguids
0x140023db7  mov     dl, r13b
0x140023dba  mov     qword ptr [rsp+160h+DesiredAccess], rax
0x140023dbf  mov     rcx, [rcx+40h]
0x140023dc3  call    WPP_RECORDER_SF_sDd
0x140023dc8  jmp     loc_1400240E8
0x140023dcd  mov     rdx, r14; SourceString
0x140023dd0  lea     rcx, [rbp+60h+DestinationString]; DestinationString
0x140023dd4  call    cs:__imp_RtlCopyUnicodeString
0x140023ddb  nop     dword ptr [rax+rax+00h]
0x140023de0  test    sil, sil
0x140023de3  jnz     short loc_140023DE9
0x140023de5  add     di, [rbp+60h+Source.Length]
0x140023de9  lea     rdx, [rbp+60h+Destination]
0x140023ded  movzx   ecx, di
0x140023df0  call    BfAllocateUnicodeString
0x140023df5  mov     ebx, eax
0x140023df7  test    eax, eax
0x140023df9  jns     short loc_140023E26
0x140023dfb  lea     rax, WPP_RECORDER_INITIALIZED
0x140023e02  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140023e09  jz      loc_1400240E8
0x140023e0f  mov     dword ptr [rsp+160h+AllocationSize], ebx
0x140023e13  mov     r9d, 2Fh ; '/'
0x140023e19  mov     dword ptr [rsp+160h+IoStatusBlock], 7E3h
0x140023e21  jmp     loc_140023D97
0x140023e26  lea     rcx, [rbp+60h+Destination]; Destination
0x140023e2a  test    sil, sil
0x140023e2d  jnz     loc_140023EC6
0x140023e33  lea     rdx, [rbp+60h+Source]; Source
0x140023e37  call    cs:__imp_RtlAppendUnicodeStringToString
0x140023e3e  nop     dword ptr [rax+rax+00h]
0x140023e43  mov     ebx, eax
0x140023e45  test    eax, eax
0x140023e47  jns     short loc_140023E74
0x140023e49  lea     rax, WPP_RECORDER_INITIALIZED
0x140023e50  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140023e57  jz      loc_1400240E8
0x140023e5d  mov     dword ptr [rsp+160h+AllocationSize], ebx
0x140023e61  mov     r9d, 30h ; '0'
0x140023e67  mov     dword ptr [rsp+160h+IoStatusBlock], 7ECh
0x140023e6f  jmp     loc_140023D97
0x140023e74  add     [rbp+60h+DestinationString.Buffer], r13
0x140023e78  lea     rdx, [rbp+60h+DestinationString]; Source
0x140023e7c  mov     eax, 0FFFEh
0x140023e81  lea     rcx, [rbp+60h+Destination]; Destination
0x140023e85  add     [rbp+60h+DestinationString.Length], ax
0x140023e89  call    cs:__imp_RtlAppendUnicodeStringToString
0x140023e90  nop     dword ptr [rax+rax+00h]
0x140023e95  mov     ebx, eax
0x140023e97  test    eax, eax
0x140023e99  jns     short loc_140023F11
0x140023e9b  lea     rax, WPP_RECORDER_INITIALIZED
0x140023ea2  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140023ea9  jz      loc_1400240E8
0x140023eaf  mov     dword ptr [rsp+160h+AllocationSize], ebx
0x140023eb3  mov     r9d, 31h ; '1'
0x140023eb9  mov     dword ptr [rsp+160h+IoStatusBlock], 7FBh
0x140023ec1  jmp     loc_140023D97
0x140023ec6  mov     rax, [rbp+60h+DestinationString.Buffer]
0x140023eca  lea     rdx, [rbp+60h+DestinationString]; Source
0x140023ece  mov     word ptr [rax+2], 3Fh ; '?'
0x140023ed4  call    cs:__imp_RtlAppendUnicodeStringToString
0x140023edb  nop     dword ptr [rax+rax+00h]
0x140023ee0  mov     ebx, eax
0x140023ee2  test    eax, eax
0x140023ee4  jns     short loc_140023F11
0x140023ee6  lea     rax, WPP_RECORDER_INITIALIZED
0x140023eed  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140023ef4  jz      loc_1400240E8
0x140023efa  mov     dword ptr [rsp+160h+AllocationSize], ebx
0x140023efe  mov     r9d, 32h ; '2'
0x140023f04  mov     dword ptr [rsp+160h+IoStatusBlock], 80Bh
0x140023f0c  jmp     loc_140023D97
0x140023f11  lea     rdx, Source; "\\"
0x140023f18  lea     rcx, [rbp+60h+Destination]; Destination
0x140023f1c  call    cs:__imp_RtlAppendUnicodeToString
0x140023f23  nop     dword ptr [rax+rax+00h]
0x140023f28  mov     ebx, eax
0x140023f2a  test    eax, eax
0x140023f2c  jns     short loc_140023F59
0x140023f2e  lea     rax, WPP_RECORDER_INITIALIZED
0x140023f35  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140023f3c  jz      loc_1400240E8
0x140023f42  mov     dword ptr [rsp+160h+AllocationSize], ebx
0x140023f46  mov     r9d, 33h ; '3'
0x140023f4c  mov     dword ptr [rsp+160h+IoStatusBlock], 813h
0x140023f54  jmp     loc_140023D97
0x140023f59  mov     rcx, cs:g_BindFltState; Filter
0x140023f60  lea     rax, [rbp+60h+Destination]
0x140023f64  mov     [rsp+160h+DriverContext], r12; DriverContext
0x140023f69  lea     r9, [rbp+60h+FileObject]; FileObject
0x140023f6d  mov     [rsp+160h+Flags], r12d; Flags
0x140023f72  lea     r8, [rbp+60h+FileHandle]; FileHandle
0x140023f76  mov     [rsp+160h+EaLength], r12d; EaLength
0x140023f7b  xorps   xmm0, xmm0
0x140023f7e  mov     [rsp+160h+EaBuffer], r12; EaBuffer
0x140023f83  xor     edx, edx; Instance
0x140023f85  mov     [rsp+160h+CreateOptions], r12d; CreateOptions
0x140023f8a  mov     [rsp+160h+CreateDisposition], 1; CreateDisposition
0x140023f92  mov     [rsp+160h+ShareAccess], 7; ShareAccess
0x140023f9a  mov     [rsp+160h+FileAttributes], r12d; FileAttributes
0x140023f9f  mov     [rbp+60h+var_90.ObjectName], rax
0x140023fa3  lea     rax, [rbp+60h+var_60]
0x140023fa7  mov     [rsp+160h+AllocationSize], r12; AllocationSize
0x140023fac  mov     [rsp+160h+IoStatusBlock], rax; IoStatusBlock
0x140023fb1  lea     rax, [rbp+60h+var_90]
0x140023fb5  mov     [rsp+160h+ObjectAttributes], rax; ObjectAttributes
0x140023fba  mov     [rsp+160h+DesiredAccess], 80h; DesiredAccess
0x140023fc2  mov     [rbp+60h+var_90.Length], 30h ; '0'
0x140023fc9  mov     [rbp+60h+var_90.RootDirectory], r12
0x140023fcd  mov     [rbp+60h+var_90.Attributes], 240h
0x140023fd4  movdqu  xmmword ptr [rbp+60h+var_90.SecurityDescriptor], xmm0
0x140023fd9  call    cs:__imp_FltCreateFileEx2
0x140023fe0  nop     dword ptr [rax+rax+00h]
0x140023fe5  mov     ebx, eax
0x140023fe7  test    eax, eax
0x140023fe9  jns     short loc_14002404E
0x140023feb  lea     rax, WPP_RECORDER_INITIALIZED
0x140023ff2  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140023ff9  jz      loc_1400240E8
0x140023fff  mov     rcx, cs:WPP_GLOBAL_Control
0x140024006  lea     rax, [rbp+60h+Destination]
0x14002400a  mov     [rsp+160h+FileAttributes], ebx
0x14002400e  mov     r9d, 34h ; '4'
0x140024014  mov     [rsp+160h+AllocationSize], rax
0x140024019  mov     dl, r13b
0x14002401c  lea     rax, aOnecoreBaseFsW_0; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x140024023  mov     dword ptr [rsp+160h+IoStatusBlock], 82Fh
0x14002402b  mov     rcx, [rcx+40h]
0x14002402f  mov     [rsp+160h+ObjectAttributes], rax
0x140024034  lea     r8d, [r9-31h]
0x140024038  lea     rax, WPP_529f93b0825532f67776c14f74ba0846_Traceguids
0x14002403f  mov     qword ptr [rsp+160h+DesiredAccess], rax
0x140024044  call    WPP_RECORDER_SF_sDZd
0x140024049  jmp     loc_1400240E8
0x14002404e  mov     rdx, [rbp+60h+FileObject]; FileObject
0x140024052  lea     r8, [rbp+60h+RetVolume]; RetVolume
0x140024056  mov     rcx, cs:g_BindFltState; Filter
0x14002405d  call    cs:__imp_FltGetVolumeFromFileObject
0x140024064  nop     dword ptr [rax+rax+00h]
0x140024069  mov     ebx, eax
0x14002406b  test    eax, eax
0x14002406d  jns     short loc_140024096
0x14002406f  lea     rax, WPP_RECORDER_INITIALIZED
0x140024076  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002407d  jz      short loc_1400240E8
0x14002407f  mov     dword ptr [rsp+160h+AllocationSize], ebx
0x140024083  mov     r9d, 35h ; '5'
0x140024089  mov     dword ptr [rsp+160h+IoStatusBlock], 836h
0x140024091  jmp     loc_140023D97
0x140024096  mov     rdx, [rbp+60h+RetVolume]; Volume
0x14002409a  lea     r9, [rbp+60h+RetInstance]; RetInstance
0x14002409e  mov     rcx, cs:g_BindFltState; Filter
0x1400240a5  xor     r8d, r8d; InstanceName
0x1400240a8  call    cs:__imp_FltGetVolumeInstanceFromName
0x1400240af  nop     dword ptr [rax+rax+00h]
0x1400240b4  mov     ebx, eax
0x1400240b6  test    eax, eax
0x1400240b8  jns     short loc_1400240E1
0x1400240ba  lea     rax, WPP_RECORDER_INITIALIZED
0x1400240c1  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400240c8  jz      short loc_1400240E8
0x1400240ca  mov     dword ptr [rsp+160h+AllocationSize], ebx
0x1400240ce  mov     r9d, 36h ; '6'
0x1400240d4  mov     dword ptr [rsp+160h+IoStatusBlock], 83Dh
0x1400240dc  jmp     loc_140023D97
0x1400240e1  mov     rax, [rbp+60h+RetInstance]
0x1400240e5  mov     [r15], rax
0x1400240e8  mov     rcx, [rbp+60h+Destination.Buffer]; P
0x1400240ec  mov     edi, 74734642h
0x1400240f1  test    rcx, rcx
0x1400240f4  jz      short loc_140024108
0x1400240f6  mov     edx, edi; Tag
0x1400240f8  call    cs:__imp_ExFreePoolWithTag
0x1400240ff  nop     dword ptr [rax+rax+00h]
0x140024104  mov     [rbp+60h+Destination.Buffer], r12
0x140024108  mov     rcx, [rbp+60h+DestinationString.Buffer]; P
0x14002410c  mov     dword ptr [rbp+60h+Destination.Length], r12d
0x140024110  test    rcx, rcx
0x140024113  jz      short loc_140024127
0x140024115  mov     edx, edi; Tag
0x140024117  call    cs:__imp_ExFreePoolWithTag
0x14002411e  nop     dword ptr [rax+rax+00h]
0x140024123  mov     [rbp+60h+DestinationString.Buffer], r12
0x140024127  mov     rcx, [rbp+60h+FileHandle]; FileHandle
0x14002412b  mov     dword ptr [rbp+60h+DestinationString.Length], r12d
0x14002412f  test    rcx, rcx
0x140024132  jz      short loc_140024140
0x140024134  call    cs:__imp_FltClose
0x14002413b  nop     dword ptr [rax+rax+00h]
0x140024140  mov     rcx, [rbp+60h+FileObject]; Object
0x140024144  test    rcx, rcx
0x140024147  jz      short loc_140024155
0x140024149  call    cs:__imp_ObfDereferenceObject
0x140024150  nop     dword ptr [rax+rax+00h]
0x140024155  mov     rcx, [rbp+60h+RetVolume]; FltObject
0x140024159  test    rcx, rcx
0x14002415c  jz      short loc_14002416A
0x14002415e  call    cs:__imp_FltObjectDereference
0x140024165  nop     dword ptr [rax+rax+00h]
0x14002416a  mov     eax, ebx
0x14002416c  mov     rcx, [rbp+60h+var_40]
0x140024170  xor     rcx, rsp; StackCookie
0x140024173  call    __security_check_cookie
0x140024178  mov     rbx, [rsp+160h+arg_8]
0x140024180  add     rsp, 130h
0x140024187  pop     r15
0x140024189  pop     r14
0x14002418b  pop     r13
0x14002418d  pop     r12
0x14002418f  pop     rdi
0x140024190  pop     rsi
0x140024191  pop     rbp
0x140024192  retn
```
