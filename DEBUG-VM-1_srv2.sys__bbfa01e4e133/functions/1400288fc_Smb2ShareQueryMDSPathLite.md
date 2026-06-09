# Smb2ShareQueryMDSPathLite

- ea: `0x1400288fc`
- end: `0x140028ab1`
- name: `Smb2ShareQueryMDSPathLite`
- size: `437`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14000c070`

## callees

- `0x1400225c4`
- `0x1400288fc`
- `0x140038490`

## import_xrefs

- `ntoskrnl!ZwCreateEvent` at `0x14002897a`
- `ntoskrnl!ZwCreateEvent` at `0x14002897a`
- `ntoskrnl!ZwWaitForSingleObject` at `0x1400289eb`
- `ntoskrnl!ZwWaitForSingleObject` at `0x1400289eb`
- `ntoskrnl!NtClose` at `0x140028a7e`
- `ntoskrnl!NtClose` at `0x140028a7e`
- `ntoskrnl!ZwFsControlFile` at `0x1400289cd`
- `ntoskrnl!ZwFsControlFile` at `0x1400289cd`

## pseudocode

```c
__int64 __fastcall Smb2ShareQueryMDSPathLite(__int64 a1, void *a2)
{
  unsigned int Status; // ebx
  void *EventHandle; // [rsp+50h] [rbp-19h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+58h] [rbp-11h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+68h] [rbp-1h] BYREF
  __int128 InputBuffer; // [rsp+98h] [rbp+2Fh] BYREF

  EventHandle = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 512;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.ObjectName = 0;
  InputBuffer = 0;
  LODWORD(InputBuffer) = 23;
  IoStatusBlock = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  Status = ZwCreateEvent(&EventHandle, 0x1F0003u, &ObjectAttributes, NotificationEvent, 0);
  if ( (Status & 0x80000000) != 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_dq(WPP_GLOBAL_Control->AttachedDevice, 28, &WPP_4e8015138ece3414973dc97451d118ee_Traceguids, Status, a1);
    }
  }
  else
  {
    Status = ZwFsControlFile(
               *(HANDLE *)(a1 + 88),
               EventHandle,
               0,
               0,
               &IoStatusBlock,
               0x902D4u,
               &InputBuffer,
               0x10u,
               a2,
               0x10u);
    if ( Status == 259 )
    {
      ZwWaitForSingleObject(EventHandle, 0, 0);
      Status = IoStatusBlock.Status;
    }
  }
  if ( (Status & 0xC0000000) == 0xC0000000
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    WPP_SF_dq(WPP_GLOBAL_Control->AttachedDevice, 29, &WPP_4e8015138ece3414973dc97451d118ee_Traceguids, Status, a1);
  }
  if ( EventHandle )
    NtClose(EventHandle);
  return Status;
}

```

## disassembly

```asm
0x1400288fc  mov     [rsp-8+arg_10], rbx
0x140028901  mov     [rsp-8+arg_18], rsi
0x140028906  push    rbp
0x140028907  push    rdi
0x140028908  push    r12
0x14002890a  lea     rbp, [rsp-47h]
0x14002890f  sub     rsp, 0B0h
0x140028916  mov     rax, cs:__security_cookie
0x14002891d  xor     rax, rsp
0x140028920  mov     [rbp+57h+var_18], rax
0x140028924  xor     eax, eax
0x140028926  mov     [rbp+57h+EventHandle], 0
0x14002892e  xorps   xmm0, xmm0
0x140028931  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140028939  mov     rsi, rdx
0x14002893c  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 200h
0x140028944  mov     rdi, rcx
0x140028947  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x14002894b  xorps   xmm1, xmm1
0x14002894e  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x140028952  movups  [rbp+57h+var_28], xmm0
0x140028956  xor     r9d, r9d; EventType
0x140028959  mov     dword ptr [rbp+57h+var_28], 17h
0x140028960  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140028964  mov     [rsp+0C0h+InitialState], al; InitialState
0x140028968  mov     edx, 1F0003h; DesiredAccess
0x14002896d  lea     rcx, [rbp+57h+EventHandle]; EventHandle
0x140028971  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm1
0x140028975  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14002897a  call    cs:__imp_ZwCreateEvent
0x140028981  nop     dword ptr [rax+rax+00h]
0x140028986  lea     r12, WPP_GLOBAL_Control
0x14002898d  mov     ebx, eax
0x14002898f  test    eax, eax
0x140028991  js      short loc_1400289FC
0x140028993  mov     rdx, [rbp+57h+EventHandle]; Event
0x140028997  mov     eax, 10h
0x14002899c  mov     rcx, [rdi+58h]; FileHandle
0x1400289a0  xor     r9d, r9d; ApcContext
0x1400289a3  mov     [rsp+0C0h+OutputBufferLength], eax; OutputBufferLength
0x1400289a7  xor     r8d, r8d; ApcRoutine
0x1400289aa  mov     [rsp+0C0h+OutputBuffer], rsi; OutputBuffer
0x1400289af  mov     [rsp+0C0h+InputBufferLength], eax; InputBufferLength
0x1400289b3  lea     rax, [rbp+57h+var_28]
0x1400289b7  mov     [rsp+0C0h+InputBuffer], rax; InputBuffer
0x1400289bc  lea     rax, [rbp+57h+IoStatusBlock]
0x1400289c0  mov     [rsp+0C0h+FsControlCode], 902D4h; FsControlCode
0x1400289c8  mov     qword ptr [rsp+0C0h+InitialState], rax; IoStatusBlock
0x1400289cd  call    cs:__imp_ZwFsControlFile
0x1400289d4  nop     dword ptr [rax+rax+00h]
0x1400289d9  mov     ebx, eax
0x1400289db  cmp     eax, 103h
0x1400289e0  jnz     short loc_140028A32
0x1400289e2  mov     rcx, [rbp+57h+EventHandle]; Handle
0x1400289e6  xor     r8d, r8d; Timeout
0x1400289e9  xor     edx, edx; Alertable
0x1400289eb  call    cs:__imp_ZwWaitForSingleObject
0x1400289f2  nop     dword ptr [rax+rax+00h]
0x1400289f7  mov     ebx, dword ptr [rbp+57h+IoStatusBlock]
0x1400289fa  jmp     short loc_140028A32
0x1400289fc  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140028a03  cmp     rcx, r12
0x140028a06  jz      short loc_140028A32
0x140028a08  mov     eax, [rcx+2Ch]
0x140028a0b  test    al, 1
0x140028a0d  jz      short loc_140028A32
0x140028a0f  cmp     byte ptr [rcx+29h], 1
0x140028a13  jb      short loc_140028A32
0x140028a15  mov     rcx, [rcx+18h]
0x140028a19  lea     r8, WPP_4e8015138ece3414973dc97451d118ee_Traceguids
0x140028a20  mov     edx, 1Ch
0x140028a25  mov     qword ptr [rsp+0C0h+InitialState], rdi
0x140028a2a  mov     r9d, ebx
0x140028a2d  call    WPP_SF_dq
0x140028a32  mov     ecx, 0C0000000h
0x140028a37  mov     eax, ebx
0x140028a39  and     eax, ecx
0x140028a3b  cmp     eax, ecx
0x140028a3d  jnz     short loc_140028A75
0x140028a3f  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140028a46  cmp     rcx, r12
0x140028a49  jz      short loc_140028A75
0x140028a4b  mov     eax, [rcx+2Ch]
0x140028a4e  test    al, 1
0x140028a50  jz      short loc_140028A75
0x140028a52  cmp     byte ptr [rcx+29h], 1
0x140028a56  jb      short loc_140028A75
0x140028a58  mov     rcx, [rcx+18h]
0x140028a5c  lea     r8, WPP_4e8015138ece3414973dc97451d118ee_Traceguids
0x140028a63  mov     edx, 1Dh
0x140028a68  mov     qword ptr [rsp+0C0h+InitialState], rdi
0x140028a6d  mov     r9d, ebx
0x140028a70  call    WPP_SF_dq
0x140028a75  mov     rcx, [rbp+57h+EventHandle]; Handle
0x140028a79  test    rcx, rcx
0x140028a7c  jz      short loc_140028A8A
0x140028a7e  call    cs:__imp_NtClose
0x140028a85  nop     dword ptr [rax+rax+00h]
0x140028a8a  mov     eax, ebx
0x140028a8c  mov     rcx, [rbp+57h+var_18]
0x140028a90  xor     rcx, rsp; StackCookie
0x140028a93  call    __security_check_cookie
0x140028a98  lea     r11, [rsp+0C0h+var_10]
0x140028aa0  mov     rbx, [r11+30h]
0x140028aa4  mov     rsi, [r11+38h]
0x140028aa8  mov     rsp, r11
0x140028aab  pop     r12
0x140028aad  pop     rdi
0x140028aae  pop     rbp
0x140028aaf  retn
```
