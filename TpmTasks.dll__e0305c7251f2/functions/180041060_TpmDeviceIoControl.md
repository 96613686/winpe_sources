# TpmDeviceIoControl

- ea: `0x180041060`
- end: `0x18004117e`
- name: `TpmDeviceIoControl`
- size: `286`
- prototype: `__int64 __fastcall(HANDLE FileHandle, ULONG IoControlCode, PVOID InputBuffer, ULONG InputBufferLength, PVOID, __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800408c0`
- `0x180041264`

## callees

- `0x180041060`

## import_xrefs

- `ntdll!NtWaitForSingleObject` at `0x18004112a`
- `ntdll!NtWaitForSingleObject` at `0x18004112a`
- `ntdll!NtCreateEvent` at `0x1800410d4`
- `ntdll!NtCreateEvent` at `0x1800410d4`
- `ntdll!NtClose` at `0x180041150`
- `ntdll!NtClose` at `0x180041150`
- `ntdll!NtDeviceIoControlFile` at `0x180041112`
- `ntdll!NtDeviceIoControlFile` at `0x180041112`
- `ntdll!RtlNtStatusToDosError` at `0x180041158`
- `ntdll!RtlNtStatusToDosError` at `0x180041158`

## pseudocode

```c
signed int __fastcall TpmDeviceIoControl(
        HANDLE FileHandle,
        ULONG IoControlCode,
        PVOID InputBuffer,
        ULONG InputBufferLength,
        PVOID OutputBuffer,
        ULONG *a6)
{
  ULONG OutputBufferLength; // esi
  int Status; // ebx
  signed int result; // eax
  void *EventHandle; // [rsp+50h] [rbp-49h] BYREF
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+58h] [rbp-41h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+68h] [rbp-31h] BYREF

  EventHandle = 0;
  *(&ObjectAttributes.Length + 1) = 0;
  *(&ObjectAttributes.Attributes + 1) = 0;
  OutputBufferLength = 0;
  IoStatusBlock = 0;
  if ( a6 )
    OutputBufferLength = *a6;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  ObjectAttributes.ObjectName = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  Status = NtCreateEvent(&EventHandle, 0x10000000u, &ObjectAttributes, NotificationEvent, 0);
  if ( Status >= 0 )
  {
    Status = NtDeviceIoControlFile(
               FileHandle,
               EventHandle,
               0,
               0,
               &IoStatusBlock,
               IoControlCode,
               InputBuffer,
               InputBufferLength,
               OutputBuffer,
               OutputBufferLength);
    if ( Status == 259 )
      Status = NtWaitForSingleObject(EventHandle, 0, 0);
    if ( Status >= 0 )
    {
      Status = IoStatusBlock.Status;
      if ( IoStatusBlock.Status >= 0 )
      {
        if ( a6 )
          *a6 = IoStatusBlock.Information;
      }
    }
  }
  if ( EventHandle )
    NtClose(EventHandle);
  result = RtlNtStatusToDosError(Status);
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180041060  push    rbp
0x180041062  push    rbx
0x180041063  push    rsi
0x180041064  push    rdi
0x180041065  push    r12
0x180041067  push    r13
0x180041069  push    r14
0x18004106b  push    r15
0x18004106d  lea     rbp, [rsp-0Fh]
0x180041072  sub     rsp, 0A8h
0x180041079  mov     rdi, [rbp+47h+arg_28]
0x18004107d  xor     eax, eax
0x18004107f  mov     [rbp+47h+EventHandle], rax
0x180041083  xorps   xmm0, xmm0
0x180041086  mov     dword ptr [rbp+47h+ObjectAttributes+4], eax
0x180041089  mov     r14d, r9d
0x18004108c  mov     dword ptr [rbp+47h+ObjectAttributes+1Ch], eax
0x18004108f  mov     r15, r8
0x180041092  mov     r12d, edx
0x180041095  mov     r13, rcx
0x180041098  mov     esi, eax
0x18004109a  movups  xmmword ptr [rbp+47h+IoStatusBlock], xmm0
0x18004109e  test    rdi, rdi
0x1800410a1  jz      short loc_1800410A5
0x1800410a3  mov     esi, [rdi]
0x1800410a5  xor     r9d, r9d; EventType
0x1800410a8  mov     [rbp+47h+ObjectAttributes.Length], 30h ; '0'
0x1800410af  lea     r8, [rbp+47h+ObjectAttributes]; ObjectAttributes
0x1800410b3  mov     [rbp+47h+ObjectAttributes.RootDirectory], rax
0x1800410b7  mov     edx, 10000000h; DesiredAccess
0x1800410bc  mov     [rbp+47h+ObjectAttributes.Attributes], 240h
0x1800410c3  lea     rcx, [rbp+47h+EventHandle]; EventHandle
0x1800410c7  mov     [rbp+47h+ObjectAttributes.ObjectName], rax
0x1800410cb  movdqu  xmmword ptr [rbp+47h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800410d0  mov     [rsp+0E0h+InitialState], al; InitialState
0x1800410d4  call    cs:__imp_NtCreateEvent
0x1800410da  mov     ebx, eax
0x1800410dc  test    eax, eax
0x1800410de  js      short loc_180041147
0x1800410e0  mov     rax, [rbp+47h+arg_20]
0x1800410e4  xor     r9d, r9d; ApcContext
0x1800410e7  mov     rdx, [rbp+47h+EventHandle]; Event
0x1800410eb  xor     r8d, r8d; ApcRoutine
0x1800410ee  mov     [rsp+0E0h+OutputBufferLength], esi; OutputBufferLength
0x1800410f2  mov     rcx, r13; FileHandle
0x1800410f5  mov     [rsp+0E0h+OutputBuffer], rax; OutputBuffer
0x1800410fa  lea     rax, [rbp+47h+IoStatusBlock]
0x1800410fe  mov     [rsp+0E0h+InputBufferLength], r14d; InputBufferLength
0x180041103  mov     [rsp+0E0h+InputBuffer], r15; InputBuffer
0x180041108  mov     [rsp+0E0h+IoControlCode], r12d; IoControlCode
0x18004110d  mov     qword ptr [rsp+0E0h+InitialState], rax; IoStatusBlock
0x180041112  call    cs:__imp_NtDeviceIoControlFile
0x180041118  mov     ebx, eax
0x18004111a  cmp     eax, 103h
0x18004111f  jnz     short loc_180041132
0x180041121  mov     rcx, [rbp+47h+EventHandle]; Handle
0x180041125  xor     r8d, r8d; Timeout
0x180041128  xor     edx, edx; Alertable
0x18004112a  call    cs:__imp_NtWaitForSingleObject
0x180041130  mov     ebx, eax
0x180041132  test    ebx, ebx
0x180041134  js      short loc_180041147
0x180041136  mov     ebx, dword ptr [rbp+47h+IoStatusBlock]
0x180041139  test    ebx, ebx
0x18004113b  js      short loc_180041147
0x18004113d  test    rdi, rdi
0x180041140  jz      short loc_180041147
0x180041142  mov     eax, dword ptr [rbp+47h+IoStatusBlock.Information]
0x180041145  mov     [rdi], eax
0x180041147  mov     rcx, [rbp+47h+EventHandle]; Handle
0x18004114b  test    rcx, rcx
0x18004114e  jz      short loc_180041156
0x180041150  call    cs:__imp_NtClose
0x180041156  mov     ecx, ebx; Status
0x180041158  call    cs:__imp_RtlNtStatusToDosError
0x18004115e  test    eax, eax
0x180041160  jle     short loc_18004116A
0x180041162  movzx   eax, ax
0x180041165  or      eax, 80070000h
0x18004116a  add     rsp, 0A8h
0x180041171  pop     r15
0x180041173  pop     r14
0x180041175  pop     r13
0x180041177  pop     r12
0x180041179  pop     rdi
0x18004117a  pop     rsi
0x18004117b  pop     rbx
0x18004117c  pop     rbp
0x18004117d  retn
```
