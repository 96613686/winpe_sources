# DfsGetDomainNameInfo

- ea: `0x18000a990`
- end: `0x18000ab9c`
- name: `DfsGetDomainNameInfo`
- size: `524`
- prototype: `__int64 __fastcall(PBYTE *Buffer)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000a6d0`

## callees

- `0x18000a990`

## import_xrefs

- `ntdll!NtOpenFile` at `0x18000a9f8`
- `ntdll!NtOpenFile` at `0x18000a9f8`
- `ntdll!RtlNtStatusToDosError` at `0x18000aa04`
- `ntdll!RtlNtStatusToDosError` at `0x18000ab92`
- `ntdll!RtlNtStatusToDosError` at `0x18000aa04`
- `ntdll!RtlNtStatusToDosError` at `0x18000ab92`
- `ntdll!NtFsControlFile` at `0x18000aa9d`
- `ntdll!NtFsControlFile` at `0x18000ab10`
- `ntdll!NtFsControlFile` at `0x18000aa9d`
- `ntdll!NtFsControlFile` at `0x18000ab10`
- `ntdll!NtClose` at `0x18000aa3e`
- `ntdll!NtClose` at `0x18000aa3e`
- `DSROLE!DsRoleGetPrimaryDomainInformation` at `0x18000aa26`
- `DSROLE!DsRoleGetPrimaryDomainInformation` at `0x18000aa26`

## pseudocode

```c
ULONG __fastcall DfsGetDomainNameInfo(PBYTE *Buffer)
{
  int Status; // eax
  DWORD PrimaryDomainInformation; // edi
  NTSTATUS v5; // ebp
  _WORD *v6; // rcx
  bool v7; // zf
  __int64 v8; // rbx
  NTSTATUS v9; // eax
  __int64 v10; // rax
  _WORD *InputBuffer; // rcx
  NTSTATUS v12; // ecx
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-58h] BYREF
  struct _OBJECT_ATTRIBUTES v14; // [rsp+60h] [rbp-48h] BYREF
  HANDLE Handle; // [rsp+B0h] [rbp+8h] BYREF

  *Buffer = 0;
  Handle = 0;
  *(_QWORD *)&v14.Length = 48;
  *(_QWORD *)&v14.Attributes = 64;
  v14.RootDirectory = 0;
  v14.ObjectName = (PUNICODE_STRING)LocalDfsName;
  IoStatusBlock = 0;
  *(_OWORD *)&v14.SecurityDescriptor = 0;
  Status = NtOpenFile(&Handle, 0x100002u, &v14, &IoStatusBlock, 7u, 0x20u);
  if ( Status < 0 )
    return RtlNtStatusToDosError(Status);
  Status = IoStatusBlock.Status;
  if ( IoStatusBlock.Status < 0 )
    return RtlNtStatusToDosError(Status);
  PrimaryDomainInformation = DsRoleGetPrimaryDomainInformation(0, DsRolePrimaryDomainInfoBasic, Buffer);
  if ( !PrimaryDomainInformation )
  {
    if ( *Buffer )
    {
      InputBuffer = (_WORD *)*((_QWORD *)*Buffer + 1);
      v8 = -1;
      if ( InputBuffer )
      {
        v10 = -1;
        do
          v7 = InputBuffer[++v10] == 0;
        while ( !v7 );
        IoStatusBlock = 0;
        v5 = NtFsControlFile(Handle, 0, 0, 0, &IoStatusBlock, 0x6811Cu, InputBuffer, 2 * v10 + 2, 0, 0);
        if ( v5 >= 0 )
          v5 = IoStatusBlock.Status;
      }
      else
      {
        v5 = 0;
      }
      v6 = (_WORD *)*((_QWORD *)*Buffer + 2);
      if ( v6 )
      {
        do
          v7 = v6[++v8] == 0;
        while ( !v7 );
        IoStatusBlock = 0;
        v9 = NtFsControlFile(Handle, 0, 0, 0, &IoStatusBlock, 0x68120u, v6, 2 * v8 + 2, 0, 0);
        if ( v9 >= 0 )
          v9 = IoStatusBlock.Status;
      }
      else
      {
        v9 = v5;
      }
      if ( v9 < 0 )
      {
        v12 = v9;
      }
      else
      {
        if ( v5 >= 0 )
          goto LABEL_5;
        v12 = v5;
      }
      PrimaryDomainInformation = RtlNtStatusToDosError(v12);
    }
    else
    {
      PrimaryDomainInformation = 59;
    }
  }
LABEL_5:
  NtClose(Handle);
  return PrimaryDomainInformation;
}

```

## disassembly

```asm
0x18000a990  mov     r11, rsp
0x18000a993  push    rsi
0x18000a994  push    r14
0x18000a996  sub     rsp, 98h
0x18000a99d  xor     r14d, r14d
0x18000a9a0  mov     [rsp+0A8h+OpenOptions], 20h ; ' '; OpenOptions
0x18000a9a8  xorps   xmm0, xmm0
0x18000a9ab  mov     [rcx], r14
0x18000a9ae  mov     rsi, rcx
0x18000a9b1  mov     [r11+8], r14
0x18000a9b5  lea     rax, LocalDfsName; "\"\""
0x18000a9bc  mov     qword ptr [r11-48h], 30h ; '0'
0x18000a9c4  lea     rcx, [r11+8]; FileHandle
0x18000a9c8  mov     qword ptr [r11-30h], 40h ; '@'
0x18000a9d0  lea     r9, [r11-58h]; IoStatusBlock
0x18000a9d4  mov     [r11-40h], r14
0x18000a9d8  lea     r8, [r11-48h]; ObjectAttributes
0x18000a9dc  mov     [r11-38h], rax
0x18000a9e0  mov     edx, 100002h; DesiredAccess
0x18000a9e5  mov     [rsp+0A8h+ShareAccess], 7; ShareAccess
0x18000a9ed  movups  xmmword ptr [rsp+0A8h+IoStatusBlock], xmm0
0x18000a9f2  movdqu  xmmword ptr [r11-28h], xmm0
0x18000a9f8  call    cs:__imp_NtOpenFile
0x18000a9fe  test    eax, eax
0x18000aa00  jns     short loc_18000AA0C
0x18000aa02  mov     ecx, eax; Status
0x18000aa04  call    cs:__imp_RtlNtStatusToDosError
0x18000aa0a  jmp     short loc_18000AA4E
0x18000aa0c  mov     eax, dword ptr [rsp+0A8h+IoStatusBlock]
0x18000aa10  test    eax, eax
0x18000aa12  js      short loc_18000AA02
0x18000aa14  mov     r8, rsi; Buffer
0x18000aa17  mov     [rsp+0A8h+var_18], rdi
0x18000aa1f  mov     edx, 1; InfoLevel
0x18000aa24  xor     ecx, ecx; lpServer
0x18000aa26  call    cs:__imp_DsRoleGetPrimaryDomainInformation
0x18000aa2c  mov     edi, eax
0x18000aa2e  test    eax, eax
0x18000aa30  jz      loc_18000AB7A
0x18000aa36  mov     rcx, [rsp+0A8h+Handle]; Handle
0x18000aa3e  call    cs:__imp_NtClose
0x18000aa44  mov     eax, edi
0x18000aa46  mov     rdi, [rsp+0A8h+var_18]
0x18000aa4e  add     rsp, 98h
0x18000aa55  pop     r14
0x18000aa57  pop     rsi
0x18000aa58  retn
0x18000aa59  mov     [rsp+0A8h+OutputBufferLength], r14d; OutputBufferLength
0x18000aa5e  lea     eax, ds:2[rax*2]
0x18000aa65  mov     [rsp+0A8h+OutputBuffer], r14; OutputBuffer
0x18000aa6a  xorps   xmm0, xmm0
0x18000aa6d  mov     [rsp+0A8h+InputBufferLength], eax; InputBufferLength
0x18000aa71  xor     r9d, r9d; ApcContext
0x18000aa74  mov     [rsp+0A8h+InputBuffer], rcx; InputBuffer
0x18000aa79  lea     rax, [rsp+0A8h+IoStatusBlock]
0x18000aa7e  mov     rcx, [rsp+0A8h+Handle]; FileHandle
0x18000aa86  xor     r8d, r8d; ApcRoutine
0x18000aa89  mov     [rsp+0A8h+OpenOptions], 6811Ch; FsControlCode
0x18000aa91  xor     edx, edx; Event
0x18000aa93  mov     qword ptr [rsp+0A8h+ShareAccess], rax; IoStatusBlock
0x18000aa98  movups  xmmword ptr [rsp+0A8h+IoStatusBlock], xmm0
0x18000aa9d  call    cs:__imp_NtFsControlFile
0x18000aaa3  test    eax, eax
0x18000aaa5  mov     ebp, eax
0x18000aaa7  cmovns  ebp, dword ptr [rsp+0A8h+IoStatusBlock]
0x18000aaac  mov     rax, [rsi]
0x18000aaaf  mov     rcx, [rax+10h]
0x18000aab3  test    rcx, rcx
0x18000aab6  jz      loc_18000AB3A
0x18000aabc  nop     dword ptr [rax+00h]
0x18000aac0  cmp     [rcx+rbx*2+2], r14w
0x18000aac6  lea     rbx, [rbx+1]
0x18000aaca  jnz     short loc_18000AAC0
0x18000aacc  mov     [rsp+0A8h+OutputBufferLength], r14d; OutputBufferLength
0x18000aad1  lea     rax, [rsp+0A8h+IoStatusBlock]
0x18000aad6  mov     [rsp+0A8h+OutputBuffer], r14; OutputBuffer
0x18000aadb  lea     ebx, ds:2[rbx*2]
0x18000aae2  mov     [rsp+0A8h+InputBufferLength], ebx; InputBufferLength
0x18000aae6  xorps   xmm0, xmm0
0x18000aae9  mov     [rsp+0A8h+InputBuffer], rcx; InputBuffer
0x18000aaee  xor     r9d, r9d; ApcContext
0x18000aaf1  mov     rcx, [rsp+0A8h+Handle]; FileHandle
0x18000aaf9  xor     r8d, r8d; ApcRoutine
0x18000aafc  mov     [rsp+0A8h+OpenOptions], 68120h; FsControlCode
0x18000ab04  xor     edx, edx; Event
0x18000ab06  mov     qword ptr [rsp+0A8h+ShareAccess], rax; IoStatusBlock
0x18000ab0b  movups  xmmword ptr [rsp+0A8h+IoStatusBlock], xmm0
0x18000ab10  call    cs:__imp_NtFsControlFile
0x18000ab16  test    eax, eax
0x18000ab18  cmovns  eax, dword ptr [rsp+0A8h+IoStatusBlock]
0x18000ab1d  mov     rbx, [rsp+0A8h+arg_8]
0x18000ab25  test    eax, eax
0x18000ab27  js      short loc_18000AB8C
0x18000ab29  test    ebp, ebp
0x18000ab2b  js      short loc_18000AB90
0x18000ab2d  mov     rbp, [rsp+0A8h+arg_10]
0x18000ab35  jmp     loc_18000AA36
0x18000ab3a  mov     eax, ebp
0x18000ab3c  jmp     short loc_18000AB1D
0x18000ab3e  mov     rax, rbx
0x18000ab41  cmp     [rcx+rax*2+2], r14w
0x18000ab47  lea     rax, [rax+1]
0x18000ab4b  jnz     short loc_18000AB41
0x18000ab4d  jmp     loc_18000AA59
0x18000ab52  mov     rcx, [rcx+8]
0x18000ab56  mov     [rsp+0A8h+arg_8], rbx
0x18000ab5e  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18000ab65  mov     [rsp+0A8h+arg_10], rbp
0x18000ab6d  test    rcx, rcx
0x18000ab70  jnz     short loc_18000AB3E
0x18000ab72  mov     ebp, r14d
0x18000ab75  jmp     loc_18000AAAC
0x18000ab7a  mov     rcx, [rsi]
0x18000ab7d  test    rcx, rcx
0x18000ab80  jnz     short loc_18000AB52
0x18000ab82  mov     edi, 3Bh ; ';'
0x18000ab87  jmp     loc_18000AA36
0x18000ab8c  mov     ecx, eax
0x18000ab8e  jmp     short loc_18000AB92
0x18000ab90  mov     ecx, ebp; Status
0x18000ab92  call    cs:__imp_RtlNtStatusToDosError
0x18000ab98  mov     edi, eax
0x18000ab9a  jmp     short loc_18000AB2D
```
