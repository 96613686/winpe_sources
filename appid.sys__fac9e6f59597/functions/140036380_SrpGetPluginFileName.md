# SrpGetPluginFileName

- ea: `0x140036380`
- end: `0x1400365ea`
- name: `SrpGetPluginFileName`
- size: `618`
- prototype: `__int64 __fastcall(struct _UNICODE_STRING *)`
- caller_count: `2`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14001fef0`
- `0x14002459c`

## callees

- `0x140024494`
- `0x140032a50`
- `0x140036380`

## import_xrefs

- `ntoskrnl!ZwOpenFile` at `0x140036416`
- `ntoskrnl!ZwOpenFile` at `0x140036416`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003644d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140036585`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003644d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140036585`
- `ntoskrnl!ZwQueryDirectoryFile` at `0x1400364a6`
- `ntoskrnl!ZwQueryDirectoryFile` at `0x1400364a6`
- `ntoskrnl!RtlUnicodeStringToInt64` at `0x14003650b`
- `ntoskrnl!RtlUnicodeStringToInt64` at `0x14003650b`
- `ntoskrnl!ZwClose` at `0x1400365d1`
- `ntoskrnl!ZwClose` at `0x1400365d1`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400364ef`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400364ef`

## string_xrefs

- `0x1400363b7`: `\SystemRoot\System32\Applocker`

## pseudocode

```c
__int64 __fastcall SrpGetPluginFileName(struct _UNICODE_STRING *a1)
{
  __int64 v2; // rdi
  ULONG Length; // r14d
  __int64 v4; // rsi
  NTSTATUS PluginFileName; // ebx
  NTSTATUS v6; // eax
  unsigned __int64 v7; // rcx
  _QWORD v9[2]; // [rsp+68h] [rbp-39h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+78h] [rbp-29h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+88h] [rbp-19h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+98h] [rbp-9h] BYREF
  void *FileHandle; // [rsp+110h] [rbp+6Fh] BYREF
  __int64 Number; // [rsp+118h] [rbp+77h] BYREF

  v9[1] = L"\\SystemRoot\\System32\\Applocker";
  *(_QWORD *)&ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)v9;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  v2 = 0;
  IoStatusBlock = 0;
  FileHandle = 0;
  Length = 84;
  v4 = 0;
  v9[0] = 4063292;
  ObjectAttributes.RootDirectory = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  PluginFileName = ZwOpenFile(&FileHandle, 0x100001u, &ObjectAttributes, &IoStatusBlock, 7u, 0x4021u);
  if ( PluginFileName >= 0 )
  {
    while ( 1 )
    {
      if ( v2 )
      {
        if ( PluginFileName != -2147483643 )
          goto LABEL_6;
        ExFreePoolWithTag((PVOID)v2, 0);
        Length *= 2;
      }
      v2 = AiAlloc(Length);
      if ( !v2 )
      {
        PluginFileName = -1073741801;
        break;
      }
LABEL_6:
      v6 = ZwQueryDirectoryFile(
             FileHandle,
             0,
             0,
             0,
             &IoStatusBlock,
             (PVOID)v2,
             Length,
             FileNamesInformation,
             1u,
             (PUNICODE_STRING)&FileName,
             0);
      PluginFileName = v6;
      if ( v6 < 0 )
      {
        if ( v6 != -2147483643 )
        {
          if ( v6 == -2147483642 )
            goto LABEL_19;
          if ( v6 != -1073741809 )
            goto LABEL_20;
        }
        goto LABEL_17;
      }
      if ( IoStatusBlock.Information )
      {
        v7 = *(unsigned int *)(v2 + 8);
        if ( (*(_DWORD *)(v2 + 8) & 0xFFFFFFFE) > 0x1C )
        {
          Number = 0;
          DestinationString = 0;
          *(_WORD *)(v2 + 2 * (v7 >> 1) - 2) = 0;
          RtlInitUnicodeString(&DestinationString, (PCWSTR)(v2 + 26));
          PluginFileName = RtlUnicodeStringToInt64(&DestinationString, 0xAu, &Number, 0);
          if ( PluginFileName < 0 )
          {
LABEL_17:
            if ( PluginFileName == -2147483642 || PluginFileName == -1073741809 )
            {
LABEL_19:
              PluginFileName = SrpCreatePluginFileName(v4, a1);
LABEL_20:
              ExFreePoolWithTag((PVOID)v2, 0);
              break;
            }
          }
          else if ( Number >= 0 && Number > v4 )
          {
            v4 = Number;
          }
        }
      }
      else
      {
        PluginFileName = -2147483643;
      }
    }
  }
  if ( FileHandle )
    ZwClose(FileHandle);
  return (unsigned int)PluginFileName;
}

```

## disassembly

```asm
0x140036380  mov     rax, rsp
0x140036383  push    rbp
0x140036384  push    rbx
0x140036385  lea     rbp, [rax-5Fh]
0x140036389  sub     rsp, 0E8h
0x140036390  mov     [rax+8], rsi
0x140036394  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x140036398  mov     [rax-18h], rdi
0x14003639c  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1400363a0  mov     [rax-20h], r12
0x1400363a4  xorps   xmm0, xmm0
0x1400363a7  mov     [rax-30h], r14
0x1400363ab  xor     r12d, r12d
0x1400363ae  mov     [rax-38h], r15
0x1400363b2  mov     edx, 100001h; DesiredAccess
0x1400363b7  lea     rax, aSystemrootSyst_2; "\\SystemRoot\\System32\\Applocker"
0x1400363be  mov     [rsp+0F0h+OpenOptions], 4021h; OpenOptions
0x1400363c6  mov     [rbp+57h+var_88], rax
0x1400363ca  mov     r15, rcx
0x1400363cd  lea     rax, [rbp+57h+var_90]
0x1400363d1  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1400363d9  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x1400363dd  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1400363e1  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 240h
0x1400363e9  mov     edi, r12d
0x1400363ec  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x1400363f0  mov     [rbp+57h+FileHandle], r12
0x1400363f4  mov     r14d, 54h ; 'T'
0x1400363fa  mov     esi, r12d
0x1400363fd  mov     [rbp+57h+var_90], 3E003Ch
0x140036405  mov     [rbp+57h+ObjectAttributes.RootDirectory], r12
0x140036409  movdqu  xmmword ptr [rbp+17h], xmm0
0x14003640e  mov     [rsp+0F0h+ShareAccess], 7; ShareAccess
0x140036416  call    cs:__imp_ZwOpenFile
0x14003641d  nop     dword ptr [rax+rax+00h]
0x140036422  mov     ebx, eax
0x140036424  test    eax, eax
0x140036426  js      loc_1400365A0
0x14003642c  mov     [rsp+0F0h+var_20], r13
0x140036434  lea     r13, FileName
0x14003643b  test    rdi, rdi
0x14003643e  jz      short loc_14003645C
0x140036440  cmp     ebx, 80000005h
0x140036446  jnz     short loc_140036470
0x140036448  xor     edx, edx; Tag
0x14003644a  mov     rcx, rdi; P
0x14003644d  call    cs:__imp_ExFreePoolWithTag
0x140036454  nop     dword ptr [rax+rax+00h]
0x140036459  add     r14d, r14d
0x14003645c  mov     ecx, r14d
0x14003645f  call    AiAlloc
0x140036464  mov     rdi, rax
0x140036467  test    rax, rax
0x14003646a  jz      loc_140036593
0x140036470  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x140036474  lea     rax, [rbp+57h+IoStatusBlock]
0x140036478  mov     [rsp+50h], r12b; RestartScan
0x14003647d  xor     r9d, r9d; ApcContext
0x140036480  mov     [rsp+0F0h+FileName], r13; FileName
0x140036485  xor     r8d, r8d; ApcRoutine
0x140036488  mov     [rsp+0F0h+ReturnSingleEntry], 1; ReturnSingleEntry
0x14003648d  xor     edx, edx; Event
0x14003648f  mov     [rsp+0F0h+FileInformationClass], 0Ch; FileInformationClass
0x140036497  mov     [rsp+0F0h+Length], r14d; Length
0x14003649c  mov     qword ptr [rsp+0F0h+OpenOptions], rdi; FileInformation
0x1400364a1  mov     qword ptr [rsp+0F0h+ShareAccess], rax; IoStatusBlock
0x1400364a6  call    cs:__imp_ZwQueryDirectoryFile
0x1400364ad  nop     dword ptr [rax+rax+00h]
0x1400364b2  mov     ebx, eax
0x1400364b4  test    eax, eax
0x1400364b6  js      loc_140036545
0x1400364bc  cmp     [rbp+57h+IoStatusBlock.Information], r12
0x1400364c0  jz      short loc_14003653B
0x1400364c2  mov     ecx, [rdi+8]
0x1400364c5  mov     eax, ecx
0x1400364c7  and     eax, 0FFFFFFFEh
0x1400364ca  cmp     eax, 1Ch
0x1400364cd  jbe     loc_14003643B
0x1400364d3  shr     rcx, 1
0x1400364d6  lea     rdx, [rdi+1Ah]; SourceString
0x1400364da  xorps   xmm0, xmm0
0x1400364dd  mov     [rbp+57h+Number], r12
0x1400364e1  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1400364e5  mov     [rdi+rcx*2-2], r12w
0x1400364eb  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1400364ef  call    cs:__imp_RtlInitUnicodeString
0x1400364f6  nop     dword ptr [rax+rax+00h]
0x1400364fb  xor     r9d, r9d; EndPointer
0x1400364fe  lea     r8, [rbp+57h+Number]; Number
0x140036502  mov     edx, 0Ah; Base
0x140036507  lea     rcx, [rbp+57h+DestinationString]; String
0x14003650b  call    cs:__imp_RtlUnicodeStringToInt64
0x140036512  nop     dword ptr [rax+rax+00h]
0x140036517  mov     ebx, eax
0x140036519  test    eax, eax
0x14003651b  js      short loc_14003655A
0x14003651d  mov     rax, [rbp+57h+Number]
0x140036521  test    rax, rax
0x140036524  js      loc_14003643B
0x14003652a  cmp     rax, rsi
0x14003652d  jle     loc_14003643B
0x140036533  mov     rsi, rax
0x140036536  jmp     loc_14003643B
0x14003653b  mov     ebx, 80000005h
0x140036540  jmp     loc_14003643B
0x140036545  cmp     eax, 80000005h
0x14003654a  jz      short loc_14003655A
0x14003654c  cmp     eax, 80000006h
0x140036551  jz      short loc_14003656E
0x140036553  cmp     eax, 0C000000Fh
0x140036558  jnz     short loc_14003657B
0x14003655a  cmp     ebx, 80000006h
0x140036560  jz      short loc_14003656E
0x140036562  cmp     ebx, 0C000000Fh
0x140036568  jnz     loc_14003643B
0x14003656e  mov     rdx, r15
0x140036571  mov     rcx, rsi
0x140036574  call    SrpCreatePluginFileName
0x140036579  mov     ebx, eax
0x14003657b  test    rdi, rdi
0x14003657e  jz      short loc_140036598
0x140036580  xor     edx, edx; Tag
0x140036582  mov     rcx, rdi; P
0x140036585  call    cs:__imp_ExFreePoolWithTag
0x14003658c  nop     dword ptr [rax+rax+00h]
0x140036591  jmp     short loc_140036598
0x140036593  mov     ebx, 0C0000017h
0x140036598  mov     r13, [rsp+0F0h+var_20]
0x1400365a0  mov     rcx, [rbp+57h+FileHandle]; Handle
0x1400365a4  mov     r15, [rsp+0F0h+var_30]
0x1400365ac  mov     r14, [rsp+0F0h+var_28]
0x1400365b4  mov     r12, [rsp+0F0h+var_18]
0x1400365bc  mov     rdi, [rsp+0E0h]
0x1400365c4  mov     rsi, [rsp+0F0h+arg_0]
0x1400365cc  test    rcx, rcx
0x1400365cf  jz      short loc_1400365DD
0x1400365d1  call    cs:__imp_ZwClose
0x1400365d8  nop     dword ptr [rax+rax+00h]
0x1400365dd  mov     eax, ebx
0x1400365df  add     rsp, 0E8h
0x1400365e6  pop     rbx
0x1400365e7  pop     rbp
0x1400365e8  retn
```
