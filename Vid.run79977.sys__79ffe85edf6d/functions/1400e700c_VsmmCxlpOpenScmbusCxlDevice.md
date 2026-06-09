# VsmmCxlpOpenScmbusCxlDevice

- ea: `0x1400e700c`
- end: `0x1400e7240`
- name: `VsmmCxlpOpenScmbusCxlDevice`
- size: `564`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1400e7248`

## callees

- `0x1400029c0`
- `0x140006b68`
- `0x14000a010`
- `0x140021c60`
- `0x14002f724`
- `0x1400e700c`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x1400e70b9`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400e70b9`
- `ntoskrnl!ZwClose` at `0x1400e7201`
- `ntoskrnl!ZwClose` at `0x1400e7201`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400e7219`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400e7219`
- `ntoskrnl!IoGetDeviceInterfaces` at `0x1400e7068`
- `ntoskrnl!IoGetDeviceInterfaces` at `0x1400e7068`
- `ntoskrnl!ZwOpenFile` at `0x1400e710c`
- `ntoskrnl!ZwOpenFile` at `0x1400e710c`

## string_xrefs

- `0x1400e708a`: `VsmmCxlpOpenScmbusCxlDevice`
- `0x1400e714a`: `VsmmCxlpOpenScmbusCxlDevice`

## pseudocode

```c
__int64 __fastcall VsmmCxlpOpenScmbusCxlDevice(void **a1)
{
  NTSTATUS DeviceInterfaces; // eax
  NTSTATUS v3; // ebx
  void *FileHandle; // [rsp+30h] [rbp-D0h] BYREF
  PZZWSTR SymbolicLinkList; // [rsp+38h] [rbp-C8h] BYREF
  int v7; // [rsp+40h] [rbp-C0h] BYREF
  NTSTATUS v8; // [rsp+44h] [rbp-BCh] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-B8h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+58h] [rbp-A8h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+88h] [rbp-78h] BYREF
  char v12[32]; // [rsp+A0h] [rbp-60h] BYREF
  char v13[16]; // [rsp+C0h] [rbp-40h] BYREF
  char v14[16]; // [rsp+D0h] [rbp-30h] BYREF
  int *v15; // [rsp+E0h] [rbp-20h]
  __int64 v16; // [rsp+E8h] [rbp-18h]
  NTSTATUS *v17; // [rsp+F0h] [rbp-10h]
  __int64 v18; // [rsp+F8h] [rbp-8h]
  _DWORD *v19; // [rsp+100h] [rbp+0h]
  __int64 v20; // [rsp+108h] [rbp+8h]
  wchar_t *Buffer; // [rsp+110h] [rbp+10h]
  _DWORD v22[2]; // [rsp+118h] [rbp+18h] BYREF

  SymbolicLinkList = 0;
  FileHandle = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  DeviceInterfaces = IoGetDeviceInterfaces(&GUID_DEVINTERFACE_MTM_BUS, 0, 0, &SymbolicLinkList);
  v3 = DeviceInterfaces;
  if ( DeviceInterfaces >= 0 )
  {
    if ( *SymbolicLinkList )
    {
      RtlInitUnicodeString(&DestinationString, SymbolicLinkList);
      ObjectAttributes.ObjectName = &DestinationString;
      ObjectAttributes.Length = 48;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.Attributes = 576;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      v3 = ZwOpenFile(&FileHandle, 0x80100000, &ObjectAttributes, &IoStatusBlock, 3u, 0);
      if ( v3 >= 0 )
      {
        v3 = 0;
        *a1 = FileHandle;
        FileHandle = 0;
      }
      else if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
      {
        tlgCreate1Sz_char(v13, "VsmmCxlpOpenScmbusCxlDevice");
        tlgCreate1Sz_char(v14, "onecore\\vm\\vid\\sys\\vsmm\\vsmmcxl.c");
        v7 = 459;
        v15 = &v7;
        v16 = 4;
        v17 = &v8;
        v8 = v3;
        v19 = v22;
        Buffer = DestinationString.Buffer;
        v22[0] = DestinationString.Length;
        v18 = 4;
        v20 = 2;
        v22[1] = 0;
        tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, &unk_14005BA61, 0, 0, 8, v12);
      }
    }
    else
    {
      v3 = -1073741275;
    }
  }
  else
  {
    VidTraceErrorStatusInternal0(
      "VsmmCxlpOpenScmbusCxlDevice",
      "onecore\\vm\\vid\\sys\\vsmm\\vsmmcxl.c",
      429,
      (unsigned int)DeviceInterfaces);
  }
  if ( FileHandle )
    ZwClose(FileHandle);
  if ( SymbolicLinkList )
    ExFreePoolWithTag(SymbolicLinkList, 0);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1400e700c  push    rbp
0x1400e700e  push    rbx
0x1400e700f  push    rsi
0x1400e7010  push    rdi
0x1400e7011  lea     rbp, [rsp-38h]
0x1400e7016  sub     rsp, 138h
0x1400e701d  mov     rax, cs:__security_cookie
0x1400e7024  xor     rax, rsp
0x1400e7027  mov     [rbp+50h+var_30], rax
0x1400e702b  xorps   xmm0, xmm0
0x1400e702e  lea     r9, [rsp+150h+SymbolicLinkList]; SymbolicLinkList
0x1400e7033  mov     rdi, rcx
0x1400e7036  xor     esi, esi
0x1400e7038  movups  xmmword ptr [rsp+150h+ObjectAttributes.ObjectName], xmm0
0x1400e703d  xor     eax, eax
0x1400e703f  mov     [rsp+150h+SymbolicLinkList], rsi
0x1400e7044  xor     r8d, r8d; Flags
0x1400e7047  mov     [rsp+150h+FileHandle], rsi
0x1400e704c  xor     edx, edx; PhysicalDeviceObject
0x1400e704e  lea     rcx, GUID_DEVINTERFACE_MTM_BUS; InterfaceClassGuid
0x1400e7055  movups  xmmword ptr [rsp+150h+ObjectAttributes+1Ch], xmm0
0x1400e705a  movups  xmmword ptr [rsp+150h+DestinationString.Length], xmm0
0x1400e705f  movups  xmmword ptr [rsp+150h+ObjectAttributes.Length], xmm0
0x1400e7064  movups  xmmword ptr [rbp+50h+IoStatusBlock], xmm0
0x1400e7068  call    cs:__imp_IoGetDeviceInterfaces
0x1400e706f  nop     dword ptr [rax+rax+00h]
0x1400e7074  mov     ebx, eax
0x1400e7076  test    eax, eax
0x1400e7078  jns     short loc_1400E709B
0x1400e707a  mov     r9d, eax
0x1400e707d  lea     rdx, aOnecoreVmVidSy_23; "onecore\\vm\\vid\\sys\\vsmm\\vsmmcxl.c"
0x1400e7084  mov     r8d, 1ADh
0x1400e708a  lea     rcx, aVsmmcxlpopensc; "VsmmCxlpOpenScmbusCxlDevice"
0x1400e7091  call    VidTraceErrorStatusInternal0
0x1400e7096  jmp     loc_1400E71F7
0x1400e709b  mov     rax, [rsp+150h+SymbolicLinkList]
0x1400e70a0  cmp     [rax], si
0x1400e70a3  jnz     short loc_1400E70AF
0x1400e70a5  mov     ebx, 0C0000225h
0x1400e70aa  jmp     loc_1400E71F7
0x1400e70af  mov     rdx, [rsp+150h+SymbolicLinkList]; SourceString
0x1400e70b4  lea     rcx, [rsp+150h+DestinationString]; DestinationString
0x1400e70b9  call    cs:__imp_RtlInitUnicodeString
0x1400e70c0  nop     dword ptr [rax+rax+00h]
0x1400e70c5  lea     rax, [rsp+150h+DestinationString]
0x1400e70ca  mov     [rsp+150h+OpenOptions], esi; OpenOptions
0x1400e70ce  xorps   xmm0, xmm0
0x1400e70d1  mov     [rsp+150h+ObjectAttributes.ObjectName], rax
0x1400e70d6  lea     r9, [rbp+50h+IoStatusBlock]; IoStatusBlock
0x1400e70da  mov     [rsp+150h+ObjectAttributes.Length], 30h ; '0'
0x1400e70e2  lea     r8, [rsp+150h+ObjectAttributes]; ObjectAttributes
0x1400e70e7  mov     [rsp+150h+ObjectAttributes.RootDirectory], rsi
0x1400e70ec  mov     edx, 80100000h; DesiredAccess
0x1400e70f1  mov     [rsp+150h+ObjectAttributes.Attributes], 240h
0x1400e70f9  lea     rcx, [rsp+150h+FileHandle]; FileHandle
0x1400e70fe  mov     [rsp+150h+ShareAccess], 3; ShareAccess
0x1400e7106  movdqu  xmmword ptr [rsp+150h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400e710c  call    cs:__imp_ZwOpenFile
0x1400e7113  nop     dword ptr [rax+rax+00h]
0x1400e7118  mov     ebx, eax
0x1400e711a  test    eax, eax
0x1400e711c  jns     loc_1400E71E8
0x1400e7122  mov     eax, cs:dword_140065110
0x1400e7128  cmp     eax, 2
0x1400e712b  jbe     loc_1400E71F7
0x1400e7131  mov     edx, 100h
0x1400e7136  lea     rcx, dword_140065110
0x1400e713d  call    _tlgKeywordOn
0x1400e7142  test    al, al
0x1400e7144  jz      loc_1400E71F7
0x1400e714a  lea     rdx, aVsmmcxlpopensc; "VsmmCxlpOpenScmbusCxlDevice"
0x1400e7151  lea     rcx, [rbp+50h+var_90]
0x1400e7155  call    _tlgCreate1Sz_char
0x1400e715a  lea     rdx, aOnecoreVmVidSy_23; "onecore\\vm\\vid\\sys\\vsmm\\vsmmcxl.c"
0x1400e7161  lea     rcx, [rbp+50h+var_80]
0x1400e7165  call    _tlgCreate1Sz_char
0x1400e716a  lea     rax, [rsp+150h+var_110]
0x1400e716f  mov     [rsp+150h+var_110], 1CBh
0x1400e7177  mov     [rbp+50h+var_70], rax
0x1400e717b  lea     rdx, unk_14005BA61
0x1400e7182  lea     rax, [rsp+150h+var_10C]
0x1400e7187  mov     [rbp+50h+var_68], 4
0x1400e718f  mov     [rbp+50h+var_60], rax
0x1400e7193  lea     rcx, dword_140065110
0x1400e719a  lea     rax, [rbp+50h+var_38]
0x1400e719e  mov     [rsp+150h+var_10C], ebx
0x1400e71a2  mov     [rbp+50h+var_50], rax
0x1400e71a6  xor     r9d, r9d
0x1400e71a9  mov     rax, [rsp+150h+DestinationString.Buffer]
0x1400e71ae  xor     r8d, r8d
0x1400e71b1  mov     [rbp+50h+var_40], rax
0x1400e71b5  movzx   eax, [rsp+150h+DestinationString.Length]
0x1400e71ba  mov     [rbp+50h+var_38], eax
0x1400e71bd  lea     rax, [rbp+50h+var_B0]
0x1400e71c1  mov     qword ptr [rsp+150h+OpenOptions], rax
0x1400e71c6  mov     [rsp+150h+ShareAccess], 8
0x1400e71ce  mov     [rbp+50h+var_58], 4
0x1400e71d6  mov     [rbp+50h+var_48], 2
0x1400e71de  mov     [rbp+50h+var_34], esi
0x1400e71e1  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400e71e6  jmp     short loc_1400E71F7
0x1400e71e8  mov     rax, [rsp+150h+FileHandle]
0x1400e71ed  mov     ebx, esi
0x1400e71ef  mov     [rdi], rax
0x1400e71f2  mov     [rsp+150h+FileHandle], rsi
0x1400e71f7  mov     rcx, [rsp+150h+FileHandle]; Handle
0x1400e71fc  test    rcx, rcx
0x1400e71ff  jz      short loc_1400E720D
0x1400e7201  call    cs:__imp_ZwClose
0x1400e7208  nop     dword ptr [rax+rax+00h]
0x1400e720d  mov     rcx, [rsp+150h+SymbolicLinkList]; P
0x1400e7212  test    rcx, rcx
0x1400e7215  jz      short loc_1400E7225
0x1400e7217  xor     edx, edx; Tag
0x1400e7219  call    cs:__imp_ExFreePoolWithTag
0x1400e7220  nop     dword ptr [rax+rax+00h]
0x1400e7225  mov     eax, ebx
0x1400e7227  mov     rcx, [rbp+50h+var_30]
0x1400e722b  xor     rcx, rsp; StackCookie
0x1400e722e  call    __security_check_cookie
0x1400e7233  add     rsp, 138h
0x1400e723a  pop     rdi
0x1400e723b  pop     rsi
0x1400e723c  pop     rbx
0x1400e723d  pop     rbp
0x1400e723e  retn
```
