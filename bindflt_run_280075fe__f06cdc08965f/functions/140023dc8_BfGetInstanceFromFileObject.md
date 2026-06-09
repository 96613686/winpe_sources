# BfGetInstanceFromFileObject

- ea: `0x140023dc8`
- end: `0x140024284`
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
- `0x140023dc8`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x140023ec4`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140023ec4`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14002400c`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14002400c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400241e8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140024207`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400241e8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140024207`
- `ntoskrnl!ObfDereferenceObject` at `0x140024239`
- `ntoskrnl!ObfDereferenceObject` at `0x140024239`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140023f27`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140023f79`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140023fc4`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140023f27`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140023f79`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140023fc4`
- `FLTMGR!FltGetVolumeFromFileObject` at `0x14002414d`
- `FLTMGR!FltGetVolumeFromFileObject` at `0x14002414d`
- `FLTMGR!FltGetVolumeInstanceFromName` at `0x140024198`
- `FLTMGR!FltGetVolumeInstanceFromName` at `0x140024198`
- `FLTMGR!FltCreateFileEx2` at `0x1400240c9`
- `FLTMGR!FltCreateFileEx2` at `0x1400240c9`
- `FLTMGR!FltClose` at `0x140024224`
- `FLTMGR!FltClose` at `0x140024224`
- `FLTMGR!FltObjectDereference` at `0x14002424e`
- `FLTMGR!FltObjectDereference` at `0x14002424e`

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
0x140023dc8  mov     [rsp-8+arg_8], rbx
0x140023dcd  push    rbp
0x140023dce  push    rsi
0x140023dcf  push    rdi
0x140023dd0  push    r12
0x140023dd2  push    r13
0x140023dd4  push    r14
0x140023dd6  push    r15
0x140023dd8  lea     rbp, [rsp-30h]
0x140023ddd  sub     rsp, 130h
0x140023de4  mov     rax, cs:__security_cookie
0x140023deb  xor     rax, rsp
0x140023dee  mov     [rbp+60h+var_40], rax
0x140023df2  movups  xmm1, xmmword ptr cs:aUnc; "\\??\\UNC"
0x140023df9  mov     qword ptr [rbp+60h+Source.Length], 10000Eh
0x140023e01  xor     r12d, r12d
0x140023e04  xorps   xmm0, xmm0
0x140023e07  mov     [rbp+60h+RetVolume], r12
0x140023e0b  mov     r14, rcx
0x140023e0e  mov     [rbp+60h+RetInstance], r12
0x140023e12  movzx   ecx, word ptr [rcx]
0x140023e15  xor     eax, eax
0x140023e17  mov     sil, dl
0x140023e1a  mov     [rbp+60h+FileHandle], r12
0x140023e1e  lea     rax, [rbp+60h+var_50]
0x140023e22  mov     [rbp+60h+FileObject], r12
0x140023e26  movups  xmmword ptr [rbp+60h+var_90.ObjectName], xmm0
0x140023e2a  lea     r13d, [r12+2]
0x140023e2f  mov     [rbp+60h+Source.Buffer], rax
0x140023e33  lea     rdx, [rbp+60h+DestinationString]
0x140023e37  mov     r15, r8
0x140023e3a  lea     edi, [rcx+r13]
0x140023e3e  movups  xmmword ptr [rbp+60h+Destination.Length], xmm0
0x140023e42  movups  xmmword ptr [rbp+60h+var_90.Length], xmm0
0x140023e46  movups  xmmword ptr [rbp+60h+var_90+1Ch], xmm0
0x140023e4a  movups  xmmword ptr [rbp+60h+var_60], xmm0
0x140023e4e  movups  xmmword ptr [rbp+60h+DestinationString.Length], xmm0
0x140023e52  movdqu  [rbp+60h+var_50], xmm1
0x140023e57  call    BfAllocateUnicodeString
0x140023e5c  mov     ebx, eax
0x140023e5e  test    eax, eax
0x140023e60  jns     short loc_140023EBD
0x140023e62  lea     rax, WPP_RECORDER_INITIALIZED
0x140023e69  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140023e70  jz      loc_1400241D8
0x140023e76  mov     dword ptr [rsp+160h+AllocationSize], ebx
0x140023e7a  lea     r9d, [r12+2Eh]
0x140023e7f  mov     dword ptr [rsp+160h+IoStatusBlock], 7D6h
0x140023e87  mov     rcx, cs:WPP_GLOBAL_Control
0x140023e8e  lea     rax, aOnecoreBaseFsW_0; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x140023e95  mov     [rsp+160h+ObjectAttributes], rax
0x140023e9a  mov     r8d, 3
0x140023ea0  lea     rax, WPP_529f93b0825532f67776c14f74ba0846_Traceguids
0x140023ea7  mov     dl, r13b
0x140023eaa  mov     qword ptr [rsp+160h+DesiredAccess], rax
0x140023eaf  mov     rcx, [rcx+40h]
0x140023eb3  call    WPP_RECORDER_SF_sDd
0x140023eb8  jmp     loc_1400241D8
0x140023ebd  mov     rdx, r14; SourceString
0x140023ec0  lea     rcx, [rbp+60h+DestinationString]; DestinationString
0x140023ec4  call    cs:__imp_RtlCopyUnicodeString
0x140023ecb  nop     dword ptr [rax+rax+00h]
0x140023ed0  test    sil, sil
0x140023ed3  jnz     short loc_140023ED9
0x140023ed5  add     di, [rbp+60h+Source.Length]
0x140023ed9  lea     rdx, [rbp+60h+Destination]
0x140023edd  movzx   ecx, di
0x140023ee0  call    BfAllocateUnicodeString
0x140023ee5  mov     ebx, eax
0x140023ee7  test    eax, eax
0x140023ee9  jns     short loc_140023F16
0x140023eeb  lea     rax, WPP_RECORDER_INITIALIZED
0x140023ef2  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140023ef9  jz      loc_1400241D8
0x140023eff  mov     dword ptr [rsp+160h+AllocationSize], ebx
0x140023f03  mov     r9d, 2Fh ; '/'
0x140023f09  mov     dword ptr [rsp+160h+IoStatusBlock], 7E3h
0x140023f11  jmp     loc_140023E87
0x140023f16  lea     rcx, [rbp+60h+Destination]; Destination
0x140023f1a  test    sil, sil
0x140023f1d  jnz     loc_140023FB6
0x140023f23  lea     rdx, [rbp+60h+Source]; Source
0x140023f27  call    cs:__imp_RtlAppendUnicodeStringToString
0x140023f2e  nop     dword ptr [rax+rax+00h]
0x140023f33  mov     ebx, eax
0x140023f35  test    eax, eax
0x140023f37  jns     short loc_140023F64
0x140023f39  lea     rax, WPP_RECORDER_INITIALIZED
0x140023f40  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140023f47  jz      loc_1400241D8
0x140023f4d  mov     dword ptr [rsp+160h+AllocationSize], ebx
0x140023f51  mov     r9d, 30h ; '0'
0x140023f57  mov     dword ptr [rsp+160h+IoStatusBlock], 7ECh
0x140023f5f  jmp     loc_140023E87
0x140023f64  add     [rbp+60h+DestinationString.Buffer], r13
0x140023f68  lea     rdx, [rbp+60h+DestinationString]; Source
0x140023f6c  mov     eax, 0FFFEh
0x140023f71  lea     rcx, [rbp+60h+Destination]; Destination
0x140023f75  add     [rbp+60h+DestinationString.Length], ax
0x140023f79  call    cs:__imp_RtlAppendUnicodeStringToString
0x140023f80  nop     dword ptr [rax+rax+00h]
0x140023f85  mov     ebx, eax
0x140023f87  test    eax, eax
0x140023f89  jns     short loc_140024001
0x140023f8b  lea     rax, WPP_RECORDER_INITIALIZED
0x140023f92  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140023f99  jz      loc_1400241D8
0x140023f9f  mov     dword ptr [rsp+160h+AllocationSize], ebx
0x140023fa3  mov     r9d, 31h ; '1'
0x140023fa9  mov     dword ptr [rsp+160h+IoStatusBlock], 7FBh
0x140023fb1  jmp     loc_140023E87
0x140023fb6  mov     rax, [rbp+60h+DestinationString.Buffer]
0x140023fba  lea     rdx, [rbp+60h+DestinationString]; Source
0x140023fbe  mov     word ptr [rax+2], 3Fh ; '?'
0x140023fc4  call    cs:__imp_RtlAppendUnicodeStringToString
0x140023fcb  nop     dword ptr [rax+rax+00h]
0x140023fd0  mov     ebx, eax
0x140023fd2  test    eax, eax
0x140023fd4  jns     short loc_140024001
0x140023fd6  lea     rax, WPP_RECORDER_INITIALIZED
0x140023fdd  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140023fe4  jz      loc_1400241D8
0x140023fea  mov     dword ptr [rsp+160h+AllocationSize], ebx
0x140023fee  mov     r9d, 32h ; '2'
0x140023ff4  mov     dword ptr [rsp+160h+IoStatusBlock], 80Bh
0x140023ffc  jmp     loc_140023E87
0x140024001  lea     rdx, Source; "\\"
0x140024008  lea     rcx, [rbp+60h+Destination]; Destination
0x14002400c  call    cs:__imp_RtlAppendUnicodeToString
0x140024013  nop     dword ptr [rax+rax+00h]
0x140024018  mov     ebx, eax
0x14002401a  test    eax, eax
0x14002401c  jns     short loc_140024049
0x14002401e  lea     rax, WPP_RECORDER_INITIALIZED
0x140024025  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002402c  jz      loc_1400241D8
0x140024032  mov     dword ptr [rsp+160h+AllocationSize], ebx
0x140024036  mov     r9d, 33h ; '3'
0x14002403c  mov     dword ptr [rsp+160h+IoStatusBlock], 813h
0x140024044  jmp     loc_140023E87
0x140024049  mov     rcx, cs:g_BindFltState; Filter
0x140024050  lea     rax, [rbp+60h+Destination]
0x140024054  mov     [rsp+160h+DriverContext], r12; DriverContext
0x140024059  lea     r9, [rbp+60h+FileObject]; FileObject
0x14002405d  mov     [rsp+160h+Flags], r12d; Flags
0x140024062  lea     r8, [rbp+60h+FileHandle]; FileHandle
0x140024066  mov     [rsp+160h+EaLength], r12d; EaLength
0x14002406b  xorps   xmm0, xmm0
0x14002406e  mov     [rsp+160h+EaBuffer], r12; EaBuffer
0x140024073  xor     edx, edx; Instance
0x140024075  mov     [rsp+160h+CreateOptions], r12d; CreateOptions
0x14002407a  mov     [rsp+160h+CreateDisposition], 1; CreateDisposition
0x140024082  mov     [rsp+160h+ShareAccess], 7; ShareAccess
0x14002408a  mov     [rsp+160h+FileAttributes], r12d; FileAttributes
0x14002408f  mov     [rbp+60h+var_90.ObjectName], rax
0x140024093  lea     rax, [rbp+60h+var_60]
0x140024097  mov     [rsp+160h+AllocationSize], r12; AllocationSize
0x14002409c  mov     [rsp+160h+IoStatusBlock], rax; IoStatusBlock
0x1400240a1  lea     rax, [rbp+60h+var_90]
0x1400240a5  mov     [rsp+160h+ObjectAttributes], rax; ObjectAttributes
0x1400240aa  mov     [rsp+160h+DesiredAccess], 80h; DesiredAccess
0x1400240b2  mov     [rbp+60h+var_90.Length], 30h ; '0'
0x1400240b9  mov     [rbp+60h+var_90.RootDirectory], r12
0x1400240bd  mov     [rbp+60h+var_90.Attributes], 240h
0x1400240c4  movdqu  xmmword ptr [rbp+60h+var_90.SecurityDescriptor], xmm0
0x1400240c9  call    cs:__imp_FltCreateFileEx2
0x1400240d0  nop     dword ptr [rax+rax+00h]
0x1400240d5  mov     ebx, eax
0x1400240d7  test    eax, eax
0x1400240d9  jns     short loc_14002413E
0x1400240db  lea     rax, WPP_RECORDER_INITIALIZED
0x1400240e2  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400240e9  jz      loc_1400241D8
0x1400240ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1400240f6  lea     rax, [rbp+60h+Destination]
0x1400240fa  mov     [rsp+160h+FileAttributes], ebx
0x1400240fe  mov     r9d, 34h ; '4'
0x140024104  mov     [rsp+160h+AllocationSize], rax
0x140024109  mov     dl, r13b
0x14002410c  lea     rax, aOnecoreBaseFsW_0; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x140024113  mov     dword ptr [rsp+160h+IoStatusBlock], 82Fh
0x14002411b  mov     rcx, [rcx+40h]
0x14002411f  mov     [rsp+160h+ObjectAttributes], rax
0x140024124  lea     r8d, [r9-31h]
0x140024128  lea     rax, WPP_529f93b0825532f67776c14f74ba0846_Traceguids
0x14002412f  mov     qword ptr [rsp+160h+DesiredAccess], rax
0x140024134  call    WPP_RECORDER_SF_sDZd
0x140024139  jmp     loc_1400241D8
0x14002413e  mov     rdx, [rbp+60h+FileObject]; FileObject
0x140024142  lea     r8, [rbp+60h+RetVolume]; RetVolume
0x140024146  mov     rcx, cs:g_BindFltState; Filter
0x14002414d  call    cs:__imp_FltGetVolumeFromFileObject
0x140024154  nop     dword ptr [rax+rax+00h]
0x140024159  mov     ebx, eax
0x14002415b  test    eax, eax
0x14002415d  jns     short loc_140024186
0x14002415f  lea     rax, WPP_RECORDER_INITIALIZED
0x140024166  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002416d  jz      short loc_1400241D8
0x14002416f  mov     dword ptr [rsp+160h+AllocationSize], ebx
0x140024173  mov     r9d, 35h ; '5'
0x140024179  mov     dword ptr [rsp+160h+IoStatusBlock], 836h
0x140024181  jmp     loc_140023E87
0x140024186  mov     rdx, [rbp+60h+RetVolume]; Volume
0x14002418a  lea     r9, [rbp+60h+RetInstance]; RetInstance
0x14002418e  mov     rcx, cs:g_BindFltState; Filter
0x140024195  xor     r8d, r8d; InstanceName
0x140024198  call    cs:__imp_FltGetVolumeInstanceFromName
0x14002419f  nop     dword ptr [rax+rax+00h]
0x1400241a4  mov     ebx, eax
0x1400241a6  test    eax, eax
0x1400241a8  jns     short loc_1400241D1
0x1400241aa  lea     rax, WPP_RECORDER_INITIALIZED
0x1400241b1  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400241b8  jz      short loc_1400241D8
0x1400241ba  mov     dword ptr [rsp+160h+AllocationSize], ebx
0x1400241be  mov     r9d, 36h ; '6'
0x1400241c4  mov     dword ptr [rsp+160h+IoStatusBlock], 83Dh
0x1400241cc  jmp     loc_140023E87
0x1400241d1  mov     rax, [rbp+60h+RetInstance]
0x1400241d5  mov     [r15], rax
0x1400241d8  mov     rcx, [rbp+60h+Destination.Buffer]; P
0x1400241dc  mov     edi, 74734642h
0x1400241e1  test    rcx, rcx
0x1400241e4  jz      short loc_1400241F8
0x1400241e6  mov     edx, edi; Tag
0x1400241e8  call    cs:__imp_ExFreePoolWithTag
0x1400241ef  nop     dword ptr [rax+rax+00h]
0x1400241f4  mov     [rbp+60h+Destination.Buffer], r12
0x1400241f8  mov     rcx, [rbp+60h+DestinationString.Buffer]; P
0x1400241fc  mov     dword ptr [rbp+60h+Destination.Length], r12d
0x140024200  test    rcx, rcx
0x140024203  jz      short loc_140024217
0x140024205  mov     edx, edi; Tag
0x140024207  call    cs:__imp_ExFreePoolWithTag
0x14002420e  nop     dword ptr [rax+rax+00h]
0x140024213  mov     [rbp+60h+DestinationString.Buffer], r12
0x140024217  mov     rcx, [rbp+60h+FileHandle]; FileHandle
0x14002421b  mov     dword ptr [rbp+60h+DestinationString.Length], r12d
0x14002421f  test    rcx, rcx
0x140024222  jz      short loc_140024230
0x140024224  call    cs:__imp_FltClose
0x14002422b  nop     dword ptr [rax+rax+00h]
0x140024230  mov     rcx, [rbp+60h+FileObject]; Object
0x140024234  test    rcx, rcx
0x140024237  jz      short loc_140024245
0x140024239  call    cs:__imp_ObfDereferenceObject
0x140024240  nop     dword ptr [rax+rax+00h]
0x140024245  mov     rcx, [rbp+60h+RetVolume]; FltObject
0x140024249  test    rcx, rcx
0x14002424c  jz      short loc_14002425A
0x14002424e  call    cs:__imp_FltObjectDereference
0x140024255  nop     dword ptr [rax+rax+00h]
0x14002425a  mov     eax, ebx
0x14002425c  mov     rcx, [rbp+60h+var_40]
0x140024260  xor     rcx, rsp; StackCookie
0x140024263  call    __security_check_cookie
0x140024268  mov     rbx, [rsp+160h+arg_8]
0x140024270  add     rsp, 130h
0x140024277  pop     r15
0x140024279  pop     r14
0x14002427b  pop     r13
0x14002427d  pop     r12
0x14002427f  pop     rdi
0x140024280  pop     rsi
0x140024281  pop     rbp
0x140024282  retn
```
