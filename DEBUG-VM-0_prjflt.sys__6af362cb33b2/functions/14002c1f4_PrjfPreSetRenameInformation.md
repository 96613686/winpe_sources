# PrjfPreSetRenameInformation

- ea: `0x14002c1f4`
- end: `0x14002c3ef`
- name: `PrjfPreSetRenameInformation`
- size: `507`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14002c030`

## callees

- `0x14000b1d0`
- `0x14000d008`
- `0x14000d128`
- `0x14002c1f4`
- `0x14002c98c`

## import_xrefs

- `FLTMGR!FltGetDestinationFileNameInformation` at `0x14002c2f1`
- `FLTMGR!FltGetDestinationFileNameInformation` at `0x14002c2f1`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14002c3b7`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14002c3b7`

## pseudocode

```c
__int64 __fastcall PrjfPreSetRenameInformation(PFLT_CALLBACK_DATA CallbackData, __int64 a2, _QWORD *a3)
{
  __int64 v4; // rbp
  PFLT_IO_PARAMETER_BLOCK Iopb; // rax
  unsigned int v7; // esi
  PVOID EaBuffer; // r8
  int DestinationFileNameInformation; // ebx
  int v10; // edx
  int v11; // r8d
  int v12; // eax
  __int64 v13; // rcx
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+80h] [rbp+8h] BYREF

  FileNameInformation = 0;
  *a3 = 0;
  v4 = a2;
  Iopb = CallbackData->Iopb;
  v7 = 1;
  EaBuffer = Iopb->Parameters.Create.EaBuffer;
  if ( Iopb->Parameters.Read.ByteOffset.QuadPart || *((_DWORD *)EaBuffer + 4) < 2u || *((_WORD *)EaBuffer + 10) != 58 )
  {
    DestinationFileNameInformation = FltGetDestinationFileNameInformation(
                                       *(PFLT_INSTANCE *)(a2 + 24),
                                       *(PFILE_OBJECT *)(a2 + 32),
                                       *((HANDLE *)EaBuffer + 1),
                                       (PWSTR)EaBuffer + 10,
                                       *((_DWORD *)EaBuffer + 4),
                                       0x101u,
                                       &FileNameInformation);
    if ( DestinationFileNameInformation >= 0 )
    {
      v12 = PrjfProcessPreRenameOrLinkInformation(CallbackData, v4, FileNameInformation, 32, a3);
      DestinationFileNameInformation = v12;
      if ( *a3 )
      {
        if ( v12 < 0 )
          MicrosoftTelemetryAssertTriggeredNoArgsKM(v13);
        v7 = 0;
      }
    }
    else if ( (BYTE1(xmmword_14001A3D0) & 0x20) != 0
           || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v10) = BYTE1(xmmword_14001A3D0) & 0x20;
      LOBYTE(v11) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sDL(
        525,
        v10,
        v11,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        2,
        13,
        32,
        (__int64)WPP_9aa94875f0ba3c84ae0a423dcca6636f_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\fileinfo.c",
        36,
        DestinationFileNameInformation);
    }
  }
  else
  {
    if ( (BYTE1(xmmword_14001A3E0) & 0x20) == 0 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return v7;
    DestinationFileNameInformation = 0;
    LOBYTE(a2) = BYTE1(xmmword_14001A3E0) & 0x20;
    LOBYTE(EaBuffer) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_sD(
      1037,
      a2,
      (_DWORD)EaBuffer,
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      4,
      13,
      31,
      (__int64)WPP_9aa94875f0ba3c84ae0a423dcca6636f_Traceguids,
      (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\fileinfo.c",
      19);
  }
  if ( FileNameInformation )
    FltReleaseFileNameInformation(FileNameInformation);
  if ( DestinationFileNameInformation < 0 )
  {
    CallbackData->IoStatus.Status = DestinationFileNameInformation;
    v7 = 4;
    CallbackData->IoStatus.Information = 0;
  }
  return v7;
}

```

## disassembly

```asm
0x14002c1f4  mov     rax, rsp
0x14002c1f7  mov     [rax+10h], rbx
0x14002c1fb  mov     [rax+18h], rbp
0x14002c1ff  push    rsi
0x14002c200  push    rdi
0x14002c201  push    r14
0x14002c203  sub     rsp, 60h
0x14002c207  mov     qword ptr [rax+8], 0
0x14002c20f  mov     r14, r8
0x14002c212  mov     qword ptr [r8], 0
0x14002c219  mov     rbp, rdx
0x14002c21c  mov     rax, [rcx+10h]
0x14002c220  mov     rdi, rcx
0x14002c223  mov     esi, 1
0x14002c228  cmp     qword ptr [rax+28h], 0
0x14002c22d  mov     r8, [rax+38h]
0x14002c231  jnz     loc_14002C2C4
0x14002c237  cmp     dword ptr [r8+10h], 2
0x14002c23c  jb      loc_14002C2C4
0x14002c242  cmp     word ptr [r8+14h], 3Ah ; ':'
0x14002c248  jnz     short loc_14002C2C4
0x14002c24a  mov     dl, byte ptr cs:xmmword_14001A3E0+1
0x14002c250  lea     rax, WPP_RECORDER_INITIALIZED
0x14002c257  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002c25e  lea     r9d, [rsi+1Fh]
0x14002c262  setnz   r8b
0x14002c266  and     dl, r9b
0x14002c269  jnz     short loc_14002C274
0x14002c26b  test    r8b, r8b
0x14002c26e  jz      loc_14002C3D7
0x14002c274  mov     r9, cs:WPP_GLOBAL_Control
0x14002c27b  lea     rax, aOnecoreBaseFsG_1; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14002c282  mov     [rsp+78h+var_30], 313h
0x14002c28a  xor     ebx, ebx
0x14002c28c  mov     [rsp+78h+var_38], rax
0x14002c291  mov     ecx, 40Dh
0x14002c296  lea     rax, WPP_9aa94875f0ba3c84ae0a423dcca6636f_Traceguids
0x14002c29d  mov     r9, [r9+40h]
0x14002c2a1  mov     [rsp+78h+var_40], rax
0x14002c2a6  mov     word ptr [rsp+78h+RetFileNameInformation], 1Fh
0x14002c2ad  mov     [rsp+78h+NameOptions], 0Dh
0x14002c2b5  mov     byte ptr [rsp+78h+FileNameLength], 4
0x14002c2ba  call    WPP_RECORDER_AND_TRACE_SF_sD
0x14002c2bf  jmp     loc_14002C3AA
0x14002c2c4  mov     rdx, [rdx+20h]; FileObject
0x14002c2c8  lea     rax, [rsp+78h+FileNameInformation]
0x14002c2d0  mov     rcx, [rbp+18h]; Instance
0x14002c2d4  lea     r9, [r8+14h]; FileName
0x14002c2d8  mov     [rsp+78h+RetFileNameInformation], rax; RetFileNameInformation
0x14002c2dd  mov     eax, [r8+10h]
0x14002c2e1  mov     r8, [r8+8]; RootDirectory
0x14002c2e5  mov     [rsp+78h+NameOptions], 101h; NameOptions
0x14002c2ed  mov     [rsp+78h+FileNameLength], eax; FileNameLength
0x14002c2f1  call    cs:__imp_FltGetDestinationFileNameInformation
0x14002c2f8  nop     dword ptr [rax+rax+00h]
0x14002c2fd  mov     ebx, eax
0x14002c2ff  test    eax, eax
0x14002c301  jns     short loc_14002C379
0x14002c303  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x14002c309  lea     rax, WPP_RECORDER_INITIALIZED
0x14002c310  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002c317  mov     r9d, 20h ; ' '
0x14002c31d  setnz   r8b
0x14002c321  and     dl, r9b
0x14002c324  jnz     short loc_14002C32B
0x14002c326  test    r8b, r8b
0x14002c329  jz      short loc_14002C3AA
0x14002c32b  mov     [rsp+78h+var_28], ebx
0x14002c32f  lea     rax, aOnecoreBaseFsG_1; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14002c336  mov     [rsp+78h+var_30], 324h
0x14002c33e  mov     ecx, 20Dh
0x14002c343  mov     [rsp+78h+var_38], rax
0x14002c348  lea     rax, WPP_9aa94875f0ba3c84ae0a423dcca6636f_Traceguids
0x14002c34f  mov     [rsp+78h+var_40], rax
0x14002c354  mov     word ptr [rsp+78h+RetFileNameInformation], r9w
0x14002c35a  mov     r9, cs:WPP_GLOBAL_Control
0x14002c361  mov     [rsp+78h+NameOptions], 0Dh
0x14002c369  mov     byte ptr [rsp+78h+FileNameLength], 2
0x14002c36e  mov     r9, [r9+40h]
0x14002c372  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x14002c377  jmp     short loc_14002C3AA
0x14002c379  mov     r8, [rsp+78h+FileNameInformation]
0x14002c381  mov     r9d, 20h ; ' '
0x14002c387  mov     rdx, rbp
0x14002c38a  mov     qword ptr [rsp+78h+FileNameLength], r14; __int64
0x14002c38f  mov     rcx, rdi; CallbackData
0x14002c392  call    PrjfProcessPreRenameOrLinkInformation
0x14002c397  cmp     qword ptr [r14], 0
0x14002c39b  mov     ebx, eax
0x14002c39d  jz      short loc_14002C3AA
0x14002c39f  test    eax, eax
0x14002c3a1  jns     short loc_14002C3A8
0x14002c3a3  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14002c3a8  xor     esi, esi
0x14002c3aa  mov     rcx, [rsp+78h+FileNameInformation]; FileNameInformation
0x14002c3b2  test    rcx, rcx
0x14002c3b5  jz      short loc_14002C3C3
0x14002c3b7  call    cs:__imp_FltReleaseFileNameInformation
0x14002c3be  nop     dword ptr [rax+rax+00h]
0x14002c3c3  test    ebx, ebx
0x14002c3c5  jns     short loc_14002C3D7
0x14002c3c7  mov     [rdi+18h], ebx
0x14002c3ca  mov     esi, 4
0x14002c3cf  mov     qword ptr [rdi+20h], 0
0x14002c3d7  lea     r11, [rsp+78h+var_18]
0x14002c3dc  mov     eax, esi
0x14002c3de  mov     rbx, [r11+28h]
0x14002c3e2  mov     rbp, [r11+30h]
0x14002c3e6  mov     rsp, r11
0x14002c3e9  pop     r14
0x14002c3eb  pop     rdi
0x14002c3ec  pop     rsi
0x14002c3ed  retn
```
