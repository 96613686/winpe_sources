# WimWriteOverlayConfig

- ea: `0x14002be3c`
- end: `0x14002c2b7`
- name: `WimWriteOverlayConfig`
- size: `1147`
- prototype: `__int64 __fastcall(__int64, void *, struct _FILE_OBJECT *, void *, ULONG Length)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops, registry_config`

## callers

- `0x14002ad78`
- `0x14002b7cc`
- `0x14002badc`

## callees

- `0x14000d3b8`
- `0x14002ba10`
- `0x14002be3c`
- `0x14003cab0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14002c297`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002c297`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002be8b`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002be8b`
- `ntoskrnl!ObfDereferenceObject` at `0x14002c09b`
- `ntoskrnl!ObfDereferenceObject` at `0x14002c148`
- `ntoskrnl!ObfDereferenceObject` at `0x14002c243`
- `ntoskrnl!ObfDereferenceObject` at `0x14002c26c`
- `ntoskrnl!ObfDereferenceObject` at `0x14002c09b`
- `ntoskrnl!ObfDereferenceObject` at `0x14002c148`
- `ntoskrnl!ObfDereferenceObject` at `0x14002c243`
- `ntoskrnl!ObfDereferenceObject` at `0x14002c26c`
- `FLTMGR!FltFlushBuffers` at `0x14002c031`
- `FLTMGR!FltFlushBuffers` at `0x14002c128`
- `FLTMGR!FltFlushBuffers` at `0x14002c031`
- `FLTMGR!FltFlushBuffers` at `0x14002c128`
- `FLTMGR!FltWriteFile` at `0x14002bf5e`
- `FLTMGR!FltWriteFile` at `0x14002c1d9`
- `FLTMGR!FltWriteFile` at `0x14002bf5e`
- `FLTMGR!FltWriteFile` at `0x14002c1d9`
- `FLTMGR!FltSetInformationFile` at `0x14002bfb2`
- `FLTMGR!FltSetInformationFile` at `0x14002c08c`
- `FLTMGR!FltSetInformationFile` at `0x14002c226`
- `FLTMGR!FltSetInformationFile` at `0x14002bfb2`
- `FLTMGR!FltSetInformationFile` at `0x14002c08c`
- `FLTMGR!FltSetInformationFile` at `0x14002c226`
- `FLTMGR!FltFsControlFile` at `0x14002bff0`
- `FLTMGR!FltFsControlFile` at `0x14002bff0`
- `FLTMGR!FltClose` at `0x14002c0aa`
- `FLTMGR!FltClose` at `0x14002c138`
- `FLTMGR!FltClose` at `0x14002c257`
- `FLTMGR!FltClose` at `0x14002c281`
- `FLTMGR!FltClose` at `0x14002c0aa`
- `FLTMGR!FltClose` at `0x14002c138`
- `FLTMGR!FltClose` at `0x14002c257`
- `FLTMGR!FltClose` at `0x14002c281`

## string_xrefs

- `0x14002c0d4`: `WimOverlay.dat`
- `0x14002beed`: `WimOverlay.new`
- `0x14002c16a`: `WimOverlay.backup`

## pseudocode

```c
__int64 __fastcall WimWriteOverlayConfig(__int64 a1, void *a2, struct _FILE_OBJECT *a3, void *a4, ULONG Length)
{
  struct _FLT_INSTANCE *v5; // rdi
  char *PoolWithTag; // rsi
  NTSTATUS v11; // ebx
  PDEVICE_OBJECT v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // r9
  int v15; // eax
  __int64 v16; // r15
  PVOID Buffer; // [rsp+20h] [rbp-58h]
  PFILE_OBJECT FileObject; // [rsp+50h] [rbp-28h] BYREF
  HANDLE FileHandle; // [rsp+58h] [rbp-20h] BYREF
  union _LARGE_INTEGER ByteOffset; // [rsp+60h] [rbp-18h] BYREF
  _QWORD FileInformation[2]; // [rsp+68h] [rbp-10h] BYREF
  char v23; // [rsp+C0h] [rbp+48h] BYREF
  ULONG BytesWritten; // [rsp+C8h] [rbp+50h] BYREF
  ULONG LengthReturned; // [rsp+D0h] [rbp+58h] BYREF
  PVOID v26; // [rsp+D8h] [rbp+60h]

  v26 = a4;
  v5 = *(struct _FLT_INSTANCE **)(a1 + 120);
  BytesWritten = 0;
  FileInformation[0] = 0;
  ByteOffset.QuadPart = 0;
  v23 = 0;
  LengthReturned = 0;
  FileHandle = 0;
  FileObject = 0;
  PoolWithTag = (char *)ExAllocatePoolWithTag(PagedPool, 0x30u, 0x66637077u);
  if ( PoolWithTag )
  {
    v15 = WimOpenOverlayConfig(a1, L"WimOverlay.new", 1, &FileHandle, &FileObject);
    v11 = v15;
    if ( v15 >= 0 )
    {
      ByteOffset.QuadPart = 0;
      Buffer = a4;
      v16 = Length;
      v15 = FltWriteFile(v5, FileObject, &ByteOffset, Length, Buffer, 0, &BytesWritten, 0, 0);
      v11 = v15;
      if ( v15 >= 0 )
      {
        FileInformation[0] = v16;
        v11 = FltSetInformationFile(v5, FileObject, FileInformation, 8u, FileEndOfFileInformation);
        if ( v11 < 0 )
          goto LABEL_40;
        v15 = FltFsControlFile(v5, FileObject, 0x9004Fu, 0, 0, 0, 0, &LengthReturned);
        v11 = v15;
        if ( v15 >= 0 )
        {
          v15 = FltFlushBuffers(v5, FileObject);
          v11 = v15;
          if ( v15 >= 0 )
          {
            if ( a2 )
            {
              v23 = 1;
              FltSetInformationFile(v5, a3, &v23, 1u, FileDispositionInformation);
              ObfDereferenceObject(a3);
              FltClose(a2);
              a3 = 0;
              a2 = 0;
            }
            *PoolWithTag = 1;
            *((_QWORD *)PoolWithTag + 1) = 0;
            *((_DWORD *)PoolWithTag + 4) = 28;
            *(_OWORD *)(PoolWithTag + 20) = *(_OWORD *)L"WimOverlay.dat";
            *((_OWORD *)PoolWithTag + 2) = *(_OWORD *)L"rlay.dat";
            v15 = WimRenameOnSystemThread((__int64)v5, (__int64)FileObject, (__int64)PoolWithTag);
            v11 = v15;
            if ( v15 >= 0 )
            {
              FltFlushBuffers(v5, FileObject);
              FltClose(FileHandle);
              ObfDereferenceObject(FileObject);
              v11 = 0;
              FileHandle = 0;
              FileObject = 0;
              v15 = WimOpenOverlayConfig(a1, L"WimOverlay.backup", 1, &FileHandle, &FileObject);
              if ( v15 >= 0 )
              {
                ByteOffset.QuadPart = 0;
                v15 = FltWriteFile(v5, FileObject, &ByteOffset, v16, v26, 0, &BytesWritten, 0, 0);
                if ( v15 >= 0 )
                {
                  FileInformation[0] = v16;
                  v11 = FltSetInformationFile(v5, FileObject, FileInformation, 8u, FileEndOfFileInformation);
                  if ( v11 < 0 )
                    v11 = 0;
                  goto LABEL_40;
                }
                v12 = WPP_GLOBAL_Control;
                if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
                  goto LABEL_40;
                v13 = 25;
              }
              else
              {
                v12 = WPP_GLOBAL_Control;
                if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
                  goto LABEL_40;
                v13 = 24;
              }
            }
            else
            {
              v12 = WPP_GLOBAL_Control;
              if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
                goto LABEL_40;
              v13 = 23;
            }
          }
          else
          {
            v12 = WPP_GLOBAL_Control;
            if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
              goto LABEL_40;
            v13 = 22;
          }
        }
        else
        {
          v12 = WPP_GLOBAL_Control;
          if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
            goto LABEL_40;
          v13 = 21;
        }
      }
      else
      {
        v12 = WPP_GLOBAL_Control;
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
          goto LABEL_40;
        v13 = 20;
      }
    }
    else
    {
      v12 = WPP_GLOBAL_Control;
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        goto LABEL_40;
      v13 = 19;
    }
    v14 = (unsigned int)v15;
    goto LABEL_5;
  }
  v11 = -1073741670;
  v12 = WPP_GLOBAL_Control;
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    v13 = 18;
    v14 = 3221225626LL;
LABEL_5:
    WPP_SF_d(v12->AttachedDevice, v13, WPP_8be5f4e5626c39736f1e2e11a2a58b62_Traceguids, v14);
  }
LABEL_40:
  if ( a3 )
    ObfDereferenceObject(a3);
  if ( a2 )
    FltClose(a2);
  if ( FileObject )
    ObfDereferenceObject(FileObject);
  if ( FileHandle )
    FltClose(FileHandle);
  if ( PoolWithTag )
    ExFreePoolWithTag(PoolWithTag, 0);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x14002be3c  mov     [rsp-40h+arg_18], r9
0x14002be41  push    rbp
0x14002be42  push    rbx
0x14002be43  push    rsi
0x14002be44  push    rdi
0x14002be45  push    r12
0x14002be47  push    r13
0x14002be49  push    r14
0x14002be4b  push    r15
0x14002be4d  mov     rbp, rsp
0x14002be50  sub     rsp, 78h
0x14002be54  mov     rdi, [rcx+78h]
0x14002be58  xor     ebx, ebx
0x14002be5a  mov     r12, r8
0x14002be5d  mov     [rbp+arg_8], ebx
0x14002be60  mov     r14, rdx
0x14002be63  mov     [rbp+FileInformation], rbx
0x14002be67  mov     r13, rcx
0x14002be6a  mov     qword ptr [rbp+ByteOffset], rbx
0x14002be6e  lea     edx, [rbx+30h]; NumberOfBytes
0x14002be71  mov     [rbp+arg_0], bl
0x14002be74  lea     ecx, [rbx+1]; PoolType
0x14002be77  mov     [rbp+LengthReturned], ebx
0x14002be7a  mov     r8d, 66637077h; Tag
0x14002be80  mov     [rbp+FileHandle], rbx
0x14002be84  mov     r15, r9
0x14002be87  mov     [rbp+FileObject], rbx
0x14002be8b  call    cs:__imp_ExAllocatePoolWithTag
0x14002be92  nop     dword ptr [rax+rax+00h]
0x14002be97  mov     rsi, rax
0x14002be9a  test    rax, rax
0x14002be9d  jnz     short loc_14002BEDD
0x14002be9f  mov     ebx, 0C000009Ah
0x14002bea4  mov     rcx, cs:WPP_GLOBAL_Control
0x14002beab  test    dword ptr [rcx+2Ch], 400h
0x14002beb2  jz      loc_14002C23B
0x14002beb8  cmp     byte ptr [rcx+29h], 2
0x14002bebc  jb      loc_14002C23B
0x14002bec2  lea     edx, [rax+12h]
0x14002bec5  mov     r9d, ebx
0x14002bec8  mov     rcx, [rcx+18h]
0x14002becc  lea     r8, WPP_8be5f4e5626c39736f1e2e11a2a58b62_Traceguids
0x14002bed3  call    WPP_SF_d
0x14002bed8  jmp     loc_14002C23B
0x14002bedd  lea     rax, [rbp+FileObject]
0x14002bee1  mov     r8b, 1
0x14002bee4  lea     r9, [rbp+FileHandle]
0x14002bee8  mov     [rsp+78h+Buffer], rax
0x14002beed  lea     rdx, aWimoverlayNew; "WimOverlay.new"
0x14002bef4  mov     rcx, r13
0x14002bef7  call    WimOpenOverlayConfig
0x14002befc  xor     ecx, ecx
0x14002befe  mov     ebx, eax
0x14002bf00  test    eax, eax
0x14002bf02  jns     short loc_14002BF2C
0x14002bf04  mov     rcx, cs:WPP_GLOBAL_Control
0x14002bf0b  test    dword ptr [rcx+2Ch], 400h
0x14002bf12  jz      loc_14002C23B
0x14002bf18  cmp     byte ptr [rcx+29h], 2
0x14002bf1c  jb      loc_14002C23B
0x14002bf22  mov     edx, 13h
0x14002bf27  mov     r9d, eax
0x14002bf2a  jmp     short loc_14002BEC8
0x14002bf2c  mov     rdx, [rbp+FileObject]; FileObject
0x14002bf30  lea     rax, [rbp+arg_8]
0x14002bf34  mov     [rsp+78h+CallbackContext], rcx; CallbackContext
0x14002bf39  lea     r8, [rbp+ByteOffset]; ByteOffset
0x14002bf3d  mov     [rsp+78h+CallbackRoutine], rcx; CallbackRoutine
0x14002bf42  mov     [rsp+78h+BytesWritten], rax; BytesWritten
0x14002bf47  mov     [rsp+78h+Flags], ecx; Flags
0x14002bf4b  mov     qword ptr [rbp+ByteOffset], rcx
0x14002bf4f  mov     rcx, rdi; InitiatingInstance
0x14002bf52  mov     [rsp+78h+Buffer], r15; Buffer
0x14002bf57  mov     r15d, [rbp+Length]
0x14002bf5b  mov     r9d, r15d; Length
0x14002bf5e  call    cs:__imp_FltWriteFile
0x14002bf65  nop     dword ptr [rax+rax+00h]
0x14002bf6a  mov     ebx, eax
0x14002bf6c  test    eax, eax
0x14002bf6e  jns     short loc_14002BF95
0x14002bf70  mov     rcx, cs:WPP_GLOBAL_Control
0x14002bf77  test    dword ptr [rcx+2Ch], 400h
0x14002bf7e  jz      loc_14002C23B
0x14002bf84  cmp     byte ptr [rcx+29h], 2
0x14002bf88  jb      loc_14002C23B
0x14002bf8e  mov     edx, 14h
0x14002bf93  jmp     short loc_14002BF27
0x14002bf95  mov     rdx, [rbp+FileObject]; FileObject
0x14002bf99  lea     r8, [rbp+FileInformation]; FileInformation
0x14002bf9d  mov     r9d, 8; Length
0x14002bfa3  mov     [rbp+FileInformation], r15
0x14002bfa7  mov     rcx, rdi; Instance
0x14002bfaa  mov     dword ptr [rsp+78h+Buffer], 14h; FileInformationClass
0x14002bfb2  call    cs:__imp_FltSetInformationFile
0x14002bfb9  nop     dword ptr [rax+rax+00h]
0x14002bfbe  mov     ebx, eax
0x14002bfc0  test    eax, eax
0x14002bfc2  js      loc_14002C23B
0x14002bfc8  mov     rdx, [rbp+FileObject]; FileObject
0x14002bfcc  lea     rax, [rbp+LengthReturned]
0x14002bfd0  mov     [rsp+78h+CallbackRoutine], rax; LengthReturned
0x14002bfd5  xor     r9d, r9d; InputBuffer
0x14002bfd8  xor     eax, eax
0x14002bfda  mov     r8d, 9004Fh; FsControlCode
0x14002bfe0  mov     dword ptr [rsp+78h+BytesWritten], eax; OutputBufferLength
0x14002bfe4  mov     rcx, rdi; Instance
0x14002bfe7  mov     qword ptr [rsp+78h+Flags], rax; OutputBuffer
0x14002bfec  mov     dword ptr [rsp+78h+Buffer], eax; InputBufferLength
0x14002bff0  call    cs:__imp_FltFsControlFile
0x14002bff7  nop     dword ptr [rax+rax+00h]
0x14002bffc  mov     ebx, eax
0x14002bffe  test    eax, eax
0x14002c000  jns     short loc_14002C02A
0x14002c002  mov     rcx, cs:WPP_GLOBAL_Control
0x14002c009  test    dword ptr [rcx+2Ch], 400h
0x14002c010  jz      loc_14002C23B
0x14002c016  cmp     byte ptr [rcx+29h], 2
0x14002c01a  jb      loc_14002C23B
0x14002c020  mov     edx, 15h
0x14002c025  jmp     loc_14002BF27
0x14002c02a  mov     rdx, [rbp+FileObject]; FileObject
0x14002c02e  mov     rcx, rdi; Instance
0x14002c031  call    cs:__imp_FltFlushBuffers
0x14002c038  nop     dword ptr [rax+rax+00h]
0x14002c03d  mov     ebx, eax
0x14002c03f  test    eax, eax
0x14002c041  jns     short loc_14002C06B
0x14002c043  mov     rcx, cs:WPP_GLOBAL_Control
0x14002c04a  test    dword ptr [rcx+2Ch], 400h
0x14002c051  jz      loc_14002C23B
0x14002c057  cmp     byte ptr [rcx+29h], 2
0x14002c05b  jb      loc_14002C23B
0x14002c061  mov     edx, 16h
0x14002c066  jmp     loc_14002BF27
0x14002c06b  test    r14, r14
0x14002c06e  jz      short loc_14002C0BC
0x14002c070  mov     r9d, 1; Length
0x14002c076  mov     [rbp+arg_0], 1
0x14002c07a  lea     r8, [rbp+arg_0]; FileInformation
0x14002c07e  mov     dword ptr [rsp+78h+Buffer], 0Dh; FileInformationClass
0x14002c086  mov     rdx, r12; FileObject
0x14002c089  mov     rcx, rdi; Instance
0x14002c08c  call    cs:__imp_FltSetInformationFile
0x14002c093  nop     dword ptr [rax+rax+00h]
0x14002c098  mov     rcx, r12; Object
0x14002c09b  call    cs:__imp_ObfDereferenceObject
0x14002c0a2  nop     dword ptr [rax+rax+00h]
0x14002c0a7  mov     rcx, r14; FileHandle
0x14002c0aa  call    cs:__imp_FltClose
0x14002c0b1  nop     dword ptr [rax+rax+00h]
0x14002c0b6  xor     r12d, r12d
0x14002c0b9  xor     r14d, r14d
0x14002c0bc  mov     byte ptr [rsi], 1
0x14002c0bf  mov     r8, rsi
0x14002c0c2  mov     qword ptr [rsi+8], 0
0x14002c0ca  mov     rcx, rdi
0x14002c0cd  mov     dword ptr [rsi+10h], 1Ch
0x14002c0d4  movups  xmm0, xmmword ptr cs:aWimoverlayDat; "WimOverlay.dat"
0x14002c0db  movups  xmmword ptr [rsi+14h], xmm0
0x14002c0df  movups  xmm1, xmmword ptr cs:aWimoverlayDat+0Ch; "rlay.dat"
0x14002c0e6  movups  xmmword ptr [rsi+20h], xmm1
0x14002c0ea  mov     rdx, [rbp+FileObject]
0x14002c0ee  call    WimRenameOnSystemThread
0x14002c0f3  mov     ebx, eax
0x14002c0f5  test    eax, eax
0x14002c0f7  jns     short loc_14002C121
0x14002c0f9  mov     rcx, cs:WPP_GLOBAL_Control
0x14002c100  test    dword ptr [rcx+2Ch], 400h
0x14002c107  jz      loc_14002C23B
0x14002c10d  cmp     byte ptr [rcx+29h], 2
0x14002c111  jb      loc_14002C23B
0x14002c117  mov     edx, 17h
0x14002c11c  jmp     loc_14002BF27
0x14002c121  mov     rdx, [rbp+FileObject]; FileObject
0x14002c125  mov     rcx, rdi; Instance
0x14002c128  call    cs:__imp_FltFlushBuffers
0x14002c12f  nop     dword ptr [rax+rax+00h]
0x14002c134  mov     rcx, [rbp+FileHandle]; FileHandle
0x14002c138  call    cs:__imp_FltClose
0x14002c13f  nop     dword ptr [rax+rax+00h]
0x14002c144  mov     rcx, [rbp+FileObject]; Object
0x14002c148  call    cs:__imp_ObfDereferenceObject
0x14002c14f  nop     dword ptr [rax+rax+00h]
0x14002c154  lea     rax, [rbp+FileObject]
0x14002c158  xor     ebx, ebx
0x14002c15a  lea     r9, [rbp+FileHandle]
0x14002c15e  mov     [rsp+78h+Buffer], rax
0x14002c163  mov     r8b, 1
0x14002c166  mov     [rbp+FileHandle], rbx
0x14002c16a  lea     rdx, aWimoverlayBack; "WimOverlay.backup"
0x14002c171  mov     [rbp+FileObject], rbx
0x14002c175  mov     rcx, r13
0x14002c178  call    WimOpenOverlayConfig
0x14002c17d  test    eax, eax
0x14002c17f  jns     short loc_14002C1A7
0x14002c181  mov     rcx, cs:WPP_GLOBAL_Control
0x14002c188  test    dword ptr [rcx+2Ch], 400h
0x14002c18f  jz      loc_14002C23B
0x14002c195  cmp     byte ptr [rcx+29h], 2
0x14002c199  jb      loc_14002C23B
0x14002c19f  lea     edx, [rbx+18h]
0x14002c1a2  jmp     loc_14002BF27
0x14002c1a7  mov     rdx, [rbp+FileObject]; FileObject
0x14002c1ab  lea     rax, [rbp+arg_8]
0x14002c1af  mov     [rsp+78h+CallbackContext], rbx; CallbackContext
0x14002c1b4  lea     r8, [rbp+ByteOffset]; ByteOffset
0x14002c1b8  mov     [rsp+78h+CallbackRoutine], rbx; CallbackRoutine
0x14002c1bd  mov     r9d, r15d; Length
0x14002c1c0  mov     [rsp+78h+BytesWritten], rax; BytesWritten
0x14002c1c5  mov     rcx, rdi; InitiatingInstance
0x14002c1c8  mov     rax, [rbp+arg_18]
0x14002c1cc  mov     [rsp+78h+Flags], ebx; Flags
0x14002c1d0  mov     [rsp+78h+Buffer], rax; Buffer
0x14002c1d5  mov     qword ptr [rbp+ByteOffset], rbx
0x14002c1d9  call    cs:__imp_FltWriteFile
0x14002c1e0  nop     dword ptr [rax+rax+00h]
0x14002c1e5  test    eax, eax
0x14002c1e7  jns     short loc_14002C209
0x14002c1e9  mov     rcx, cs:WPP_GLOBAL_Control
0x14002c1f0  test    dword ptr [rcx+2Ch], 400h
0x14002c1f7  jz      short loc_14002C23B
0x14002c1f9  cmp     byte ptr [rcx+29h], 2
0x14002c1fd  jb      short loc_14002C23B
0x14002c1ff  mov     edx, 19h
0x14002c204  jmp     loc_14002BF27
0x14002c209  mov     rdx, [rbp+FileObject]; FileObject
0x14002c20d  lea     r8, [rbp+FileInformation]; FileInformation
0x14002c211  mov     r9d, 8; Length
0x14002c217  mov     [rbp+FileInformation], r15
0x14002c21b  mov     rcx, rdi; Instance
0x14002c21e  mov     dword ptr [rsp+78h+Buffer], 14h; FileInformationClass
0x14002c226  call    cs:__imp_FltSetInformationFile
0x14002c22d  nop     dword ptr [rax+rax+00h]
0x14002c232  mov     ebx, eax
0x14002c234  xor     eax, eax
0x14002c236  test    ebx, ebx
0x14002c238  cmovs   ebx, eax
0x14002c23b  test    r12, r12
0x14002c23e  jz      short loc_14002C24F
0x14002c240  mov     rcx, r12; Object
0x14002c243  call    cs:__imp_ObfDereferenceObject
0x14002c24a  nop     dword ptr [rax+rax+00h]
0x14002c24f  test    r14, r14
0x14002c252  jz      short loc_14002C263
0x14002c254  mov     rcx, r14; FileHandle
0x14002c257  call    cs:__imp_FltClose
0x14002c25e  nop     dword ptr [rax+rax+00h]
0x14002c263  mov     rcx, [rbp+FileObject]; Object
0x14002c267  test    rcx, rcx
0x14002c26a  jz      short loc_14002C278
0x14002c26c  call    cs:__imp_ObfDereferenceObject
0x14002c273  nop     dword ptr [rax+rax+00h]
0x14002c278  mov     rcx, [rbp+FileHandle]; FileHandle
0x14002c27c  test    rcx, rcx
0x14002c27f  jz      short loc_14002C28D
0x14002c281  call    cs:__imp_FltClose
0x14002c288  nop     dword ptr [rax+rax+00h]
0x14002c28d  test    rsi, rsi
0x14002c290  jz      short loc_14002C2A3
0x14002c292  xor     edx, edx; Tag
0x14002c294  mov     rcx, rsi; P
0x14002c297  call    cs:__imp_ExFreePoolWithTag
0x14002c29e  nop     dword ptr [rax+rax+00h]
0x14002c2a3  mov     eax, ebx
0x14002c2a5  add     rsp, 78h
0x14002c2a9  pop     r15
0x14002c2ab  pop     r14
0x14002c2ad  pop     r13
0x14002c2af  pop     r12
0x14002c2b1  pop     rdi
0x14002c2b2  pop     rsi
0x14002c2b3  pop     rbx
0x14002c2b4  pop     rbp
0x14002c2b5  retn
```
