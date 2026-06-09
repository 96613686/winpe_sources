# SIPolicyPmGetPolicyFolderFiles

- ea: `0x18002247c`
- end: `0x1800226cf`
- name: `SIPolicyPmGetPolicyFolderFiles`
- size: `595`
- prototype: `__int64 __fastcall(__int64, __int64, struct _UNICODE_STRING *, __int64, char, __int64, unsigned int, _DWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002149c`
- `0x180021758`

## callees

- `0x180002a90`
- `0x18002247c`
- `0x180022ca4`
- `0x180024230`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022688`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022688`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180022521`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180022521`
- `ntdll!ZwQueryDirectoryFile` at `0x180022570`
- `ntdll!ZwQueryDirectoryFile` at `0x180022640`
- `ntdll!ZwQueryDirectoryFile` at `0x180022570`
- `ntdll!ZwQueryDirectoryFile` at `0x180022640`
- `ntdll!ZwOpenFile` at `0x180022508`
- `ntdll!ZwOpenFile` at `0x180022508`
- `ntdll!ZwClose` at `0x18002267f`
- `ntdll!ZwClose` at `0x18002267f`

## pseudocode

```c
__int64 __fastcall SIPolicyPmGetPolicyFolderFiles(
        __int64 a1,
        __int64 a2,
        struct _UNICODE_STRING *a3,
        __int64 a4,
        char a5,
        __int64 a6,
        unsigned int a7,
        _DWORD *a8)
{
  _DWORD *v8; // r14
  WCHAR *v11; // rdi
  NTSTATUS v12; // ebx
  __int64 v13; // rsi
  USHORT v14; // cx
  __int64 v15; // r14
  void *FileHandle; // [rsp+60h] [rbp-79h] BYREF
  _DWORD *v18; // [rsp+68h] [rbp-71h]
  UNICODE_STRING String2; // [rsp+70h] [rbp-69h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+80h] [rbp-59h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+90h] [rbp-49h] BYREF
  GUID Guid; // [rsp+C0h] [rbp-19h] BYREF

  v8 = a8;
  FileHandle = 0;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)a2;
  v11 = 0;
  v18 = a8;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 64;
  IoStatusBlock = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v12 = ZwOpenFile(&FileHandle, 0x100001u, &ObjectAttributes, &IoStatusBlock, 7u, 0x4021u);
  if ( v12 >= 0 )
  {
    v11 = (WCHAR *)LocalAlloc(0x40u, 0x250u);
    if ( !v11 )
    {
      v12 = -1073741801;
      goto LABEL_22;
    }
    v13 = 0;
    v12 = ZwQueryDirectoryFile(FileHandle, 0, 0, 0, &IoStatusBlock, v11, 0x250u, FileDirectoryInformation, 1u, a3, 1u);
    if ( v12 >= 0 )
    {
      while ( IoStatusBlock.Information )
      {
        if ( a6 && (unsigned int)v13 >= a7 )
        {
          v12 = -1073741670;
          goto LABEL_22;
        }
        v14 = v11[30];
        *(_DWORD *)(&String2.MaximumLength + 1) = 0;
        String2.Length = v14;
        String2.Buffer = v11 + 32;
        String2.MaximumLength = v14;
        if ( !a5 || (Guid = 0, (int)SIPolicyIsValidPolicyFileName(&String2, &Guid) >= 0) )
        {
          if ( a6 )
          {
            v15 = a6 + 24 * v13;
            v12 = SIPolicyBuildPath((PCUNICODE_STRING)a2, &String2);
            if ( v12 < 0 )
              goto LABEL_22;
            *(_BYTE *)(v15 + 16) = *(_BYTE *)(a2 + 16);
            *(_BYTE *)(v15 + 17) = *(_BYTE *)(a2 + 17);
          }
          v13 = (unsigned int)(v13 + 1);
        }
        v12 = ZwQueryDirectoryFile(
                FileHandle,
                0,
                0,
                0,
                &IoStatusBlock,
                v11,
                0x250u,
                FileDirectoryInformation,
                1u,
                a3,
                0);
        if ( v12 < 0 )
        {
          v8 = v18;
          goto LABEL_16;
        }
      }
      v8 = v18;
      goto LABEL_21;
    }
LABEL_16:
    if ( v12 == -2147483642 || v12 == -1073741809 )
    {
      v12 = 0;
LABEL_21:
      *v8 = v13;
    }
  }
LABEL_22:
  if ( FileHandle )
    ZwClose(FileHandle);
  LocalFree(v11);
  if ( v12 == -1073741772 || (unsigned int)(v12 + 1073741766) <= 1 )
    return (unsigned int)-1073741275;
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18002247c  mov     [rsp-8+arg_0], rbx
0x180022481  push    rbp
0x180022482  push    rsi
0x180022483  push    rdi
0x180022484  push    r12
0x180022486  push    r13
0x180022488  push    r14
0x18002248a  push    r15
0x18002248c  lea     rbp, [rsp-7]
0x180022491  sub     rsp, 0E0h
0x180022498  mov     rax, cs:__security_cookie
0x18002249f  xor     rax, rsp
0x1800224a2  mov     [rbp+37h+var_40], rax
0x1800224a6  mov     r14, [rbp+37h+arg_38]
0x1800224aa  lea     r9, [rbp+37h+IoStatusBlock]; IoStatusBlock
0x1800224ae  mov     r15, [rbp+37h+arg_28]
0x1800224b2  xor     ecx, ecx
0x1800224b4  xorps   xmm0, xmm0
0x1800224b7  mov     [rbp+37h+FileHandle], rcx
0x1800224bb  mov     r12, r8
0x1800224be  mov     [rbp+37h+ObjectAttributes.RootDirectory], rcx
0x1800224c2  mov     r13, rdx
0x1800224c5  mov     [rbp+37h+ObjectAttributes.ObjectName], rdx
0x1800224c9  lea     esi, [rcx+40h]
0x1800224cc  mov     [rsp+110h+OpenOptions], 4021h; OpenOptions
0x1800224d4  mov     edi, ecx
0x1800224d6  mov     [rbp+37h+var_A8], r14
0x1800224da  lea     rcx, [rbp+37h+FileHandle]; FileHandle
0x1800224de  mov     qword ptr [rbp+37h+ObjectAttributes.Length], 30h ; '0'
0x1800224e6  lea     r8, [rbp+37h+ObjectAttributes]; ObjectAttributes
0x1800224ea  mov     qword ptr [rbp+37h+ObjectAttributes.Attributes], 40h ; '@'
0x1800224f2  mov     edx, 100001h; DesiredAccess
0x1800224f7  mov     [rsp+110h+ShareAccess], 7; ShareAccess
0x1800224ff  movups  xmmword ptr [rbp+37h+IoStatusBlock], xmm0
0x180022503  movdqu  xmmword ptr [rbp+37h+ObjectAttributes.SecurityDescriptor], xmm0
0x180022508  call    cs:__imp_ZwOpenFile
0x18002250e  mov     ebx, eax
0x180022510  test    eax, eax
0x180022512  js      loc_180022676
0x180022518  mov     ebx, 250h
0x18002251d  mov     ecx, esi; uFlags
0x18002251f  mov     edx, ebx; uBytes
0x180022521  call    cs:__imp_LocalAlloc
0x180022527  mov     rdi, rax
0x18002252a  test    rax, rax
0x18002252d  jnz     short loc_180022539
0x18002252f  mov     ebx, 0C0000017h
0x180022534  jmp     loc_180022676
0x180022539  mov     rcx, [rbp+37h+FileHandle]; FileHandle
0x18002253d  lea     rax, [rbp+37h+IoStatusBlock]
0x180022541  mov     [rsp+110h+RestartScan], 1; RestartScan
0x180022546  xor     r9d, r9d; ApcContext
0x180022549  mov     [rsp+110h+FileName], r12; FileName
0x18002254e  xor     r8d, r8d; ApcRoutine
0x180022551  mov     [rsp+110h+ReturnSingleEntry], 1; ReturnSingleEntry
0x180022556  xor     edx, edx; Event
0x180022558  mov     [rsp+110h+FileInformationClass], 1; FileInformationClass
0x180022560  xor     esi, esi
0x180022562  mov     [rsp+110h+Length], ebx; Length
0x180022566  mov     qword ptr [rsp+110h+OpenOptions], rdi; FileInformation
0x18002256b  mov     qword ptr [rsp+110h+ShareAccess], rax; IoStatusBlock
0x180022570  call    cs:__imp_ZwQueryDirectoryFile
0x180022576  mov     ebx, eax
0x180022578  test    eax, eax
0x18002257a  js      loc_180022654
0x180022580  cmp     [rbp+37h+IoStatusBlock.Information], 0
0x180022585  jz      loc_18002266F
0x18002258b  test    r15, r15
0x18002258e  jz      short loc_180022599
0x180022590  cmp     esi, [rbp+37h+arg_30]
0x180022593  jnb     loc_180022668
0x180022599  cmp     [rbp+37h+arg_20], 0
0x18002259d  lea     rax, [rdi+40h]
0x1800225a1  movzx   ecx, word ptr [rdi+3Ch]
0x1800225a5  xorps   xmm0, xmm0
0x1800225a8  movups  xmmword ptr [rbp+37h+String2.Length], xmm0
0x1800225ac  mov     [rbp+37h+String2.Length], cx
0x1800225b0  mov     [rbp+37h+String2.Buffer], rax
0x1800225b4  mov     [rbp+37h+String2.MaximumLength], cx
0x1800225b8  jz      short loc_1800225CF
0x1800225ba  lea     rdx, [rbp+37h+Guid]; Guid
0x1800225be  lea     rcx, [rbp+37h+String2]; String2
0x1800225c2  movups  xmmword ptr [rbp+37h+Guid.Data1], xmm0
0x1800225c6  call    SIPolicyIsValidPolicyFileName
0x1800225cb  test    eax, eax
0x1800225cd  js      short loc_180022607
0x1800225cf  test    r15, r15
0x1800225d2  jz      short loc_180022605
0x1800225d4  lea     rcx, [rsi+rsi*2]
0x1800225d8  lea     r14, [r15+rcx*8]
0x1800225dc  mov     rcx, r13; Source
0x1800225df  mov     r8, r14
0x1800225e2  lea     rdx, [rbp+37h+String2]; PCUNICODE_STRING
0x1800225e6  call    SIPolicyBuildPath
0x1800225eb  mov     ebx, eax
0x1800225ed  test    eax, eax
0x1800225ef  js      loc_180022676
0x1800225f5  mov     al, [r13+10h]
0x1800225f9  mov     [r14+10h], al
0x1800225fd  mov     al, [r13+11h]
0x180022601  mov     [r14+11h], al
0x180022605  inc     esi
0x180022607  mov     rcx, [rbp+37h+FileHandle]; FileHandle
0x18002260b  lea     rax, [rbp+37h+IoStatusBlock]
0x18002260f  mov     [rsp+110h+RestartScan], 0; RestartScan
0x180022614  xor     r9d, r9d; ApcContext
0x180022617  mov     [rsp+110h+FileName], r12; FileName
0x18002261c  xor     r8d, r8d; ApcRoutine
0x18002261f  mov     [rsp+110h+ReturnSingleEntry], 1; ReturnSingleEntry
0x180022624  xor     edx, edx; Event
0x180022626  mov     [rsp+110h+FileInformationClass], 1; FileInformationClass
0x18002262e  mov     [rsp+110h+Length], 250h; Length
0x180022636  mov     qword ptr [rsp+110h+OpenOptions], rdi; FileInformation
0x18002263b  mov     qword ptr [rsp+110h+ShareAccess], rax; IoStatusBlock
0x180022640  call    cs:__imp_ZwQueryDirectoryFile
0x180022646  mov     ebx, eax
0x180022648  test    eax, eax
0x18002264a  jns     loc_180022580
0x180022650  mov     r14, [rbp+37h+var_A8]
0x180022654  cmp     ebx, 80000006h
0x18002265a  jz      short loc_180022664
0x18002265c  cmp     ebx, 0C000000Fh
0x180022662  jnz     short loc_180022676
0x180022664  xor     ebx, ebx
0x180022666  jmp     short loc_180022673
0x180022668  mov     ebx, 0C000009Ah
0x18002266d  jmp     short loc_180022676
0x18002266f  mov     r14, [rbp+37h+var_A8]
0x180022673  mov     [r14], esi
0x180022676  mov     rcx, [rbp+37h+FileHandle]; Handle
0x18002267a  test    rcx, rcx
0x18002267d  jz      short loc_180022685
0x18002267f  call    cs:__imp_ZwClose
0x180022685  mov     rcx, rdi; hMem
0x180022688  call    cs:__imp_LocalFree
0x18002268e  cmp     ebx, 0C0000034h
0x180022694  jz      short loc_1800226A1
0x180022696  lea     eax, [rbx+3FFFFFC6h]
0x18002269c  cmp     eax, 1
0x18002269f  ja      short loc_1800226A6
0x1800226a1  mov     ebx, 0C0000225h
0x1800226a6  mov     eax, ebx
0x1800226a8  mov     rcx, [rbp+37h+var_40]
0x1800226ac  xor     rcx, rsp; StackCookie
0x1800226af  call    __security_check_cookie
0x1800226b4  mov     rbx, [rsp+110h+arg_0]
0x1800226bc  add     rsp, 0E0h
0x1800226c3  pop     r15
0x1800226c5  pop     r14
0x1800226c7  pop     r13
0x1800226c9  pop     r12
0x1800226cb  pop     rdi
0x1800226cc  pop     rsi
0x1800226cd  pop     rbp
0x1800226ce  retn
```
