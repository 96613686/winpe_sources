# PrjfPartiallyExpandDirectory

- ea: `0x14002aecc`
- end: `0x14002b0c7`
- name: `PrjfPartiallyExpandDirectory`
- size: `507`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData, PFLT_INSTANCE Instance, PFILE_OBJECT FileObject, PUNICODE_STRING FileName)`
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140007694`
- `0x140024184`
- `0x14003fdf0`

## callees

- `0x140002d9c`
- `0x14000b1d0`
- `0x14000ba20`
- `0x140029214`
- `0x14002aecc`
- `0x14002b0d0`

## import_xrefs

- `ntoskrnl!ExAcquireRundownProtection` at `0x14002af6b`
- `ntoskrnl!ExAcquireRundownProtection` at `0x14002af6b`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14002afcd`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14002afcd`
- `FLTMGR!FltQueryDirectoryFile` at `0x14002b042`
- `FLTMGR!FltQueryDirectoryFile` at `0x14002b042`
- `FLTMGR!FltReleaseContext` at `0x14002b06f`
- `FLTMGR!FltReleaseContext` at `0x14002b083`
- `FLTMGR!FltReleaseContext` at `0x14002b098`
- `FLTMGR!FltReleaseContext` at `0x14002b06f`
- `FLTMGR!FltReleaseContext` at `0x14002b083`
- `FLTMGR!FltReleaseContext` at `0x14002b098`

## pseudocode

```c
__int64 __fastcall PrjfPartiallyExpandDirectory(
        PFLT_CALLBACK_DATA CallbackData,
        PFLT_INSTANCE Instance,
        PFILE_OBJECT FileObject,
        PUNICODE_STRING FileName)
{
  char ContextFileObject; // al
  __int64 v9; // rcx
  _DWORD *v10; // rsi
  char *v11; // rdi
  __int64 v12; // rcx
  int v13; // ebx
  NTSTATUS v14; // eax
  PFLT_CONTEXT v16; // [rsp+50h] [rbp-29h] BYREF
  PFLT_CONTEXT v17; // [rsp+58h] [rbp-21h]
  PFLT_CONTEXT Context[2]; // [rsp+60h] [rbp-19h] BYREF
  __int128 FileInformation; // [rsp+70h] [rbp-9h] BYREF

  Context[0] = 0;
  v17 = 0;
  v16 = 0;
  FileInformation = 0;
  ContextFileObject = PrjfGetContextFileObjectEx(Instance, FileObject, &v16);
  v10 = v17;
  v11 = (char *)Context[0];
  if ( !ContextFileObject || !Context[0] || *((_DWORD *)Context[0] + 16) == 3 )
    goto LABEL_18;
  if ( *(_DWORD *)v17 != 1 )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(v9);
  if ( ExAcquireRundownProtection((PEX_RUNDOWN_REF)v11 + 10) )
  {
    if ( *((_DWORD *)v11 + 16) == 3 )
    {
      v13 = 0;
    }
    else
    {
      if ( *v10 == 1 )
      {
        *(_OWORD *)Context = *((_OWORD *)v11 + 6);
        v13 = PrjfPopulateFile(CallbackData, FileName, v11 + 120, Context, Instance, FileObject, v16);
LABEL_13:
        ExReleaseRundownProtection((PEX_RUNDOWN_REF)v11 + 10);
        goto LABEL_19;
      }
      v13 = 0;
    }
    MicrosoftTelemetryAssertTriggeredNoArgsKM(v12);
    goto LABEL_13;
  }
  v13 = PrjfExpandAndWait(CallbackData, 3, 2, 7, 0);
  if ( v13 >= 0 )
  {
    v14 = FltQueryDirectoryFile(
            Instance,
            FileObject,
            &FileInformation,
            0x10u,
            FileNamesInformation,
            1u,
            FileName,
            1u,
            0);
    v13 = v14;
    if ( v14 != -1073741809 )
    {
      if ( v14 == -2147483643 )
        v13 = 0;
      goto LABEL_19;
    }
LABEL_18:
    v13 = -1073741772;
  }
LABEL_19:
  if ( v11 )
    FltReleaseContext(v11);
  if ( v10 )
    FltReleaseContext(v10);
  if ( v16 )
    FltReleaseContext(v16);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x14002aecc  push    rbp
0x14002aece  push    rbx
0x14002aecf  push    rsi
0x14002aed0  push    rdi
0x14002aed1  push    r12
0x14002aed3  push    r13
0x14002aed5  push    r14
0x14002aed7  push    r15
0x14002aed9  lea     rbp, [rsp-1Fh]
0x14002aede  sub     rsp, 98h
0x14002aee5  mov     rax, cs:__security_cookie
0x14002aeec  xor     rax, rsp
0x14002aeef  mov     [rbp+57h+var_50], rax
0x14002aef3  mov     r12, r8
0x14002aef6  mov     [rbp+57h+Context], 0
0x14002aefe  mov     r15, rdx
0x14002af01  mov     [rbp+57h+var_78], 0
0x14002af09  mov     r13, r9
0x14002af0c  mov     [rbp+57h+var_80], 0
0x14002af14  mov     rbx, rcx
0x14002af17  lea     rax, [rbp+57h+var_80]
0x14002af1b  xorps   xmm0, xmm0
0x14002af1e  mov     qword ptr [rsp+0D0h+FileInformationClass], rax; Context
0x14002af23  mov     rdx, r12; FileObject
0x14002af26  lea     r9, [rbp+57h+var_78]
0x14002af2a  mov     rcx, r15; Instance
0x14002af2d  lea     r8, [rbp+57h+Context]
0x14002af31  movups  [rbp+57h+FileInformation], xmm0
0x14002af35  call    PrjfGetContextFileObjectEx
0x14002af3a  mov     rsi, [rbp+57h+var_78]
0x14002af3e  mov     rdi, [rbp+57h+Context]
0x14002af42  test    al, al
0x14002af44  jz      loc_14002B062
0x14002af4a  test    rdi, rdi
0x14002af4d  jz      loc_14002B062
0x14002af53  cmp     dword ptr [rdi+40h], 3
0x14002af57  jz      loc_14002B062
0x14002af5d  cmp     dword ptr [rsi], 1
0x14002af60  jz      short loc_14002AF67
0x14002af62  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14002af67  lea     rcx, [rdi+50h]; RunRef
0x14002af6b  call    cs:__imp_ExAcquireRundownProtection
0x14002af72  nop     dword ptr [rax+rax+00h]
0x14002af77  test    al, al
0x14002af79  jz      short loc_14002AFDE
0x14002af7b  cmp     dword ptr [rdi+40h], 3
0x14002af7f  jz      short loc_14002AFC2
0x14002af81  cmp     dword ptr [rsi], 1
0x14002af84  jnz     short loc_14002AFB9
0x14002af86  movups  xmm0, xmmword ptr [rdi+60h]
0x14002af8a  mov     rax, [rbp+57h+var_80]
0x14002af8e  lea     r8, [rdi+78h]
0x14002af92  mov     [rsp+0D0h+FileName], rax
0x14002af97  lea     r9, [rbp+57h+Context]
0x14002af9b  mov     qword ptr [rsp+0D0h+ReturnSingleEntry], r12
0x14002afa0  mov     rdx, r13
0x14002afa3  mov     rcx, rbx
0x14002afa6  mov     qword ptr [rsp+0D0h+FileInformationClass], r15
0x14002afab  movdqu  xmmword ptr [rbp+57h+Context], xmm0
0x14002afb0  call    PrjfPopulateFile
0x14002afb5  mov     ebx, eax
0x14002afb7  jmp     short loc_14002AFC9
0x14002afb9  xor     ebx, ebx
0x14002afbb  cmp     dword ptr [rsi], 1
0x14002afbe  jz      short loc_14002AFC9
0x14002afc0  jmp     short loc_14002AFC4
0x14002afc2  xor     ebx, ebx
0x14002afc4  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14002afc9  lea     rcx, [rdi+50h]; RunRef
0x14002afcd  call    cs:__imp_ExReleaseRundownProtection
0x14002afd4  nop     dword ptr [rax+rax+00h]
0x14002afd9  jmp     loc_14002B067
0x14002afde  mov     [rsp+0D0h+RestartScan], 0; char
0x14002afe3  mov     r9, rdi
0x14002afe6  mov     dword ptr [rsp+0D0h+FileName], 7; int
0x14002afee  mov     r8, r12
0x14002aff1  mov     dword ptr [rsp+0D0h+ReturnSingleEntry], 2; int
0x14002aff9  mov     rdx, r15
0x14002affc  mov     rcx, rbx; CallbackData
0x14002afff  mov     [rsp+0D0h+FileInformationClass], 3; int
0x14002b007  call    PrjfExpandAndWait
0x14002b00c  mov     ebx, eax
0x14002b00e  test    eax, eax
0x14002b010  js      short loc_14002B067
0x14002b012  mov     [rsp+0D0h+LengthReturned], 0; LengthReturned
0x14002b01b  lea     r8, [rbp+57h+FileInformation]; FileInformation
0x14002b01f  mov     [rsp+0D0h+RestartScan], 1; RestartScan
0x14002b024  mov     r9d, 10h; Length
0x14002b02a  mov     [rsp+0D0h+FileName], r13; FileName
0x14002b02f  mov     rdx, r12; FileObject
0x14002b032  mov     [rsp+0D0h+ReturnSingleEntry], 1; ReturnSingleEntry
0x14002b037  mov     rcx, r15; Instance
0x14002b03a  mov     [rsp+0D0h+FileInformationClass], 0Ch; FileInformationClass
0x14002b042  call    cs:__imp_FltQueryDirectoryFile
0x14002b049  nop     dword ptr [rax+rax+00h]
0x14002b04e  mov     ebx, eax
0x14002b050  cmp     eax, 0C000000Fh
0x14002b055  jz      short loc_14002B062
0x14002b057  cmp     eax, 80000005h
0x14002b05c  jnz     short loc_14002B067
0x14002b05e  xor     ebx, ebx
0x14002b060  jmp     short loc_14002B067
0x14002b062  mov     ebx, 0C0000034h
0x14002b067  test    rdi, rdi
0x14002b06a  jz      short loc_14002B07B
0x14002b06c  mov     rcx, rdi; Context
0x14002b06f  call    cs:__imp_FltReleaseContext
0x14002b076  nop     dword ptr [rax+rax+00h]
0x14002b07b  test    rsi, rsi
0x14002b07e  jz      short loc_14002B08F
0x14002b080  mov     rcx, rsi; Context
0x14002b083  call    cs:__imp_FltReleaseContext
0x14002b08a  nop     dword ptr [rax+rax+00h]
0x14002b08f  mov     rcx, [rbp+57h+var_80]; Context
0x14002b093  test    rcx, rcx
0x14002b096  jz      short loc_14002B0A4
0x14002b098  call    cs:__imp_FltReleaseContext
0x14002b09f  nop     dword ptr [rax+rax+00h]
0x14002b0a4  mov     eax, ebx
0x14002b0a6  mov     rcx, [rbp+57h+var_50]
0x14002b0aa  xor     rcx, rsp; StackCookie
0x14002b0ad  call    __security_check_cookie
0x14002b0b2  add     rsp, 98h
0x14002b0b9  pop     r15
0x14002b0bb  pop     r14
0x14002b0bd  pop     r13
0x14002b0bf  pop     r12
0x14002b0c1  pop     rdi
0x14002b0c2  pop     rsi
0x14002b0c3  pop     rbx
0x14002b0c4  pop     rbp
0x14002b0c5  retn
```
