# CNtfsBaseReplicaMetadata::GetFileIdFromFileSystem(ushort const *,_FILE_ID_128 *)

- ea: `0x18009bec0`
- end: `0x18009c0f2`
- name: `?GetFileIdFromFileSystem@CNtfsBaseReplicaMetadata@@CAJPEBGPEAU_FILE_ID_128@@@Z`
- size: `562`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct _FILE_ID_128 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18009b540`

## callees

- `0x180002ab0`
- `0x180007e10`
- `0x180008080`
- `0x180011314`
- `0x18009bec0`

## import_xrefs

- `ntdll!NtOpenFile` at `0x18009c025`
- `ntdll!NtOpenFile` at `0x18009c025`
- `ntdll!RtlFreeHeap` at `0x18009c0a6`
- `ntdll!RtlFreeHeap` at `0x18009c0a6`
- `ntdll!NtQueryInformationFile` at `0x18009c05a`
- `ntdll!NtQueryInformationFile` at `0x18009c05a`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x18009bfbd`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x18009bfbd`
- `ntdll!NtClose` at `0x18009c0b5`
- `ntdll!NtClose` at `0x18009c0b5`

## pseudocode

```c
__int64 __fastcall CNtfsBaseReplicaMetadata::GetFileIdFromFileSystem(
        const unsigned __int16 *a1,
        struct _FILE_ID_128 *a2)
{
  _BYTE *v4; // rax
  char v5; // cl
  __int16 v6; // ax
  unsigned int v7; // eax
  unsigned int v8; // eax
  unsigned int v9; // eax
  unsigned int v10; // ebx
  int v12; // [rsp+30h] [rbp-49h] BYREF
  int v13; // [rsp+34h] [rbp-45h]
  char v14; // [rsp+38h] [rbp-41h]
  const char *v15; // [rsp+40h] [rbp-39h]
  __int64 v16; // [rsp+48h] [rbp-31h]
  void *FileHandle; // [rsp+50h] [rbp-29h] BYREF
  PVOID P[2]; // [rsp+58h] [rbp-21h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+68h] [rbp-11h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+78h] [rbp-1h] BYREF
  _BYTE FileInformation[24]; // [rsp+A8h] [rbp+2Fh] BYREF

  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x40) == 0 )
    {
LABEL_8:
      v5 = 0;
      goto LABEL_9;
    }
    if ( *((_BYTE *)WPP_GLOBAL_Control + 65) >= 6u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 12, WPP_6fce54dcbad1353bfe0bc4457f274cf4_Traceguids);
      v4 = WPP_GLOBAL_Control;
    }
  }
  if ( (v4[68] & 0x40) == 0 || v4[65] < 6u )
    goto LABEL_8;
  v5 = 1;
LABEL_9:
  v13 = 124;
  v14 = v5;
  v15 = "CNtfsBaseReplicaMetadata::GetFileIdFromFileSystem";
  v16 = 0;
  v6 = 133;
  FileHandle = 0;
  *(_OWORD *)P = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  IoStatusBlock = 0;
  memset(FileInformation, 0, sizeof(FileInformation));
  if ( a2 && (LOWORD(v13) = 133, v6 = 134, *a2 = 0, a1) )
  {
    LOWORD(v13) = 134;
    v7 = RtlDosPathNameToNtPathName_U_WithStatus(a1, P, 0, 0);
    v12 = HRESULTFromNTSTATUS(v7);
    v6 = 136;
    if ( v12 >= 0 )
    {
      LOWORD(v13) = 136;
      ObjectAttributes.ObjectName = (PUNICODE_STRING)P;
      ObjectAttributes.Length = 48;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.Attributes = 64;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      v8 = NtOpenFile(&FileHandle, 0x100000u, &ObjectAttributes, &IoStatusBlock, 7u, 0x20u);
      v12 = HRESULTFromNTSTATUS(v8);
      v6 = 149;
      if ( v12 >= 0 )
      {
        LOWORD(v13) = 149;
        v9 = NtQueryInformationFile(
               FileHandle,
               &IoStatusBlock,
               FileInformation,
               0x18u,
               FileMaximumInformation|FileBothDirectoryInformation);
        v12 = HRESULTFromNTSTATUS(v9);
        v6 = 155;
        if ( v12 >= 0 )
        {
          LOWORD(v13) = 155;
          *a2 = *(struct _FILE_ID_128 *)&FileInformation[8];
          goto LABEL_17;
        }
      }
    }
  }
  else
  {
    v12 = -2147024809;
  }
  HIWORD(v13) = v6;
LABEL_17:
  if ( P[1] )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P[1]);
  if ( FileHandle )
  {
    NtClose(FileHandle);
    FileHandle = 0;
  }
  v10 = v12;
  CEcsFunctionTracer::~CEcsFunctionTracer((CEcsFunctionTracer *)&v12);
  return v10;
}

```

## disassembly

```asm
0x18009bec0  mov     [rsp-8+arg_10], rbx
0x18009bec5  mov     [rsp-8+arg_18], rdi
0x18009beca  push    rbp
0x18009becb  lea     rbp, [rsp-57h]
0x18009bed0  sub     rsp, 0D0h
0x18009bed7  mov     rax, cs:__security_cookie
0x18009bede  xor     rax, rsp
0x18009bee1  mov     [rbp+57h+var_10], rax
0x18009bee5  mov     rbx, rdx
0x18009bee8  mov     rdi, rcx
0x18009beeb  mov     rax, cs:WPP_GLOBAL_Control
0x18009bef2  lea     rcx, WPP_GLOBAL_Control
0x18009bef9  cmp     rax, rcx
0x18009befc  jz      short loc_18009BF26
0x18009befe  test    byte ptr [rax+44h], 40h
0x18009bf02  jz      short loc_18009BF36
0x18009bf04  cmp     byte ptr [rax+41h], 6
0x18009bf08  jb      short loc_18009BF26
0x18009bf0a  mov     rcx, [rax+38h]
0x18009bf0e  lea     r8, WPP_6fce54dcbad1353bfe0bc4457f274cf4_Traceguids
0x18009bf15  mov     edx, 0Ch
0x18009bf1a  call    WPP_SF_
0x18009bf1f  mov     rax, cs:WPP_GLOBAL_Control
0x18009bf26  test    byte ptr [rax+44h], 40h
0x18009bf2a  jz      short loc_18009BF36
0x18009bf2c  cmp     byte ptr [rax+41h], 6
0x18009bf30  jb      short loc_18009BF36
0x18009bf32  mov     cl, 1
0x18009bf34  jmp     short loc_18009BF38
0x18009bf36  xor     cl, cl
0x18009bf38  xorps   xmm1, xmm1
0x18009bf3b  mov     [rbp+57h+var_9C], 7Ch ; '|'
0x18009bf42  lea     rax, aCntfsbaserepli_0; "CNtfsBaseReplicaMetadata::GetFileIdFrom"...
0x18009bf49  mov     [rbp+57h+var_98], cl
0x18009bf4c  mov     [rbp+57h+var_90], rax
0x18009bf50  xorps   xmm0, xmm0
0x18009bf53  xor     eax, eax
0x18009bf55  mov     [rbp+57h+var_88], 0
0x18009bf5d  mov     [rbp+57h+var_18], rax
0x18009bf61  mov     eax, 85h
0x18009bf66  mov     [rbp+57h+FileHandle], 0
0x18009bf6e  movups  xmmword ptr [rbp+57h+P], xmm0
0x18009bf72  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm1
0x18009bf76  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm1
0x18009bf7a  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm1
0x18009bf7e  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x18009bf82  movups  [rbp+57h+FileInformation], xmm1
0x18009bf86  test    rbx, rbx
0x18009bf89  jz      loc_18009C081
0x18009bf8f  mov     word ptr [rbp+57h+var_9C], ax
0x18009bf93  mov     eax, 86h
0x18009bf98  movdqu  xmmword ptr [rbx], xmm0
0x18009bf9c  test    rdi, rdi
0x18009bf9f  jz      loc_18009C081
0x18009bfa5  xor     r9d, r9d
0x18009bfa8  mov     [rbp+57h+var_A0], 0
0x18009bfaf  xor     r8d, r8d
0x18009bfb2  mov     word ptr [rbp+57h+var_9C], ax
0x18009bfb6  lea     rdx, [rbp+57h+P]
0x18009bfba  mov     rcx, rdi
0x18009bfbd  call    cs:__imp_RtlDosPathNameToNtPathName_U_WithStatus
0x18009bfc3  mov     ecx, eax
0x18009bfc5  call    HRESULTFromNTSTATUS
0x18009bfca  mov     [rbp+57h+var_A0], eax
0x18009bfcd  test    eax, eax
0x18009bfcf  mov     eax, 88h
0x18009bfd4  js      loc_18009C088
0x18009bfda  mov     word ptr [rbp+57h+var_9C], ax
0x18009bfde  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x18009bfe2  lea     rax, [rbp+57h+P]
0x18009bfe6  mov     [rsp+0D0h+OpenOptions], 20h ; ' '; OpenOptions
0x18009bfee  xorps   xmm0, xmm0
0x18009bff1  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18009bff5  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18009bff9  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18009c000  mov     edx, 100000h; DesiredAccess
0x18009c005  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x18009c00d  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x18009c011  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x18009c018  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18009c01d  mov     [rsp+0D0h+ShareAccess], 7; ShareAccess
0x18009c025  call    cs:__imp_NtOpenFile
0x18009c02b  mov     ecx, eax
0x18009c02d  call    HRESULTFromNTSTATUS
0x18009c032  mov     [rbp+57h+var_A0], eax
0x18009c035  test    eax, eax
0x18009c037  mov     eax, 95h
0x18009c03c  js      short loc_18009C088
0x18009c03e  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x18009c042  lea     r9d, [rax-7Dh]; Length
0x18009c046  lea     r8, [rbp+57h+FileInformation]; FileInformation
0x18009c04a  mov     word ptr [rbp+57h+var_9C], ax
0x18009c04e  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x18009c052  mov     [rsp+0D0h+ShareAccess], 3Bh ; ';'; FileInformationClass
0x18009c05a  call    cs:__imp_NtQueryInformationFile
0x18009c060  mov     ecx, eax
0x18009c062  call    HRESULTFromNTSTATUS
0x18009c067  mov     [rbp+57h+var_A0], eax
0x18009c06a  test    eax, eax
0x18009c06c  mov     eax, 9Bh
0x18009c071  js      short loc_18009C088
0x18009c073  movups  xmm0, [rbp+57h+FileInformation+8]
0x18009c077  mov     word ptr [rbp+57h+var_9C], ax
0x18009c07b  movdqu  xmmword ptr [rbx], xmm0
0x18009c07f  jmp     short loc_18009C08C
0x18009c081  mov     [rbp+57h+var_A0], 80070057h
0x18009c088  mov     word ptr [rbp+57h+var_9C+2], ax
0x18009c08c  cmp     [rbp+57h+P+8], 0
0x18009c091  jz      short loc_18009C0AC
0x18009c093  mov     rcx, gs:60h
0x18009c09c  xor     edx, edx; Flags
0x18009c09e  mov     r8, [rbp+57h+P+8]; P
0x18009c0a2  mov     rcx, [rcx+30h]; HeapHandle
0x18009c0a6  call    cs:__imp_RtlFreeHeap
0x18009c0ac  mov     rcx, [rbp+57h+FileHandle]; Handle
0x18009c0b0  test    rcx, rcx
0x18009c0b3  jz      short loc_18009C0C3
0x18009c0b5  call    cs:__imp_NtClose
0x18009c0bb  mov     [rbp+57h+FileHandle], 0
0x18009c0c3  mov     ebx, [rbp+57h+var_A0]
0x18009c0c6  lea     rcx, [rbp+57h+var_A0]; this
0x18009c0ca  call    ??1CEcsFunctionTracer@@QEAA@XZ; CEcsFunctionTracer::~CEcsFunctionTracer(void)
0x18009c0cf  mov     eax, ebx
0x18009c0d1  mov     rcx, [rbp+57h+var_10]
0x18009c0d5  xor     rcx, rsp; StackCookie
0x18009c0d8  call    __security_check_cookie
0x18009c0dd  lea     r11, [rsp+0D0h+var_s0]
0x18009c0e5  mov     rbx, [r11+20h]
0x18009c0e9  mov     rdi, [r11+28h]
0x18009c0ed  mov     rsp, r11
0x18009c0f0  pop     rbp
0x18009c0f1  retn
```
